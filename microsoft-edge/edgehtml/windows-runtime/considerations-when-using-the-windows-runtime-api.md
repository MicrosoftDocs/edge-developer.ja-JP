---
description: Windows ランタイム API を使用する際の考慮事項
title: Windows ランタイム API を使用する際の考慮事項
ms.custom: ''
ms.date: 11/03/2020
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime API
ms.assetid: 2f56d70c-c80d-4876-8e6a-8ae031d31c22
caps.latest.revision: 8
author: MSEdgeTeam
ms.author: msedgedevrel
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 170374fd109802bff0aa0fc93cea6c8d50c9d7c7
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399345"
---
# <a name="considerations-when-using-the-windows-runtime-api"></a>Windows ランタイム API を使用する際の考慮事項  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

JavaScript では、Windows ランタイム API のほぼ全要素を使用できます。  ただし、Windows ランタイム要素の JavaScript 表現には、いくつかの点に気を付ける必要があります。  

> [!IMPORTANT]
> C++、C#、または Visual Basic で Windows ランタイム コンポーネントを作成し、JavaScript で使用する方法については [、「C++][WindowsUwpComponentsCreatingCpp] での Windows ランタイム コンポーネントの作成」および [「C#][WindowsUwpComponentsCreatingCsharpVb]および Visual Basic での Windows ランタイム コンポーネントの作成」を参照してください。  

## <a name="special-cases-in-the-javascript-representation-of-windows-runtime-types"></a>Windows ランタイム型の JavaScript 表記の特殊なケース  

:::row:::
   :::column span="1":::
      文字列  
   :::column-end:::
   :::column span="3":::
      初期化されていない文字列は、"undefined" という文字列として Windows ランタイム メソッドに渡され、文字列セットが文字列 `null` "null" として渡されます。  \(これは、文字列または値が文字列に設定されるたびに true です。\) Windows ランタイム メソッドに文字列を渡す前に、空の文字列 `null` `undefined` \("\\) として初期化する必要があります。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      インターフェイス  
   :::column-end:::
   :::column span="3":::
      JavaScript で Windows ランタイム インターフェイスを実装することはできません。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      配列  
   :::column-end:::
   :::column span="3":::
      Windows ランタイム配列はサイズ変更できないので、JavaScript の配列のサイズを変更するメソッドは Windows ランタイム配列では機能しません。  
      *   配列: JavaScript 配列の値を Windows ランタイム メソッドに渡す場合、配列がコピーされます。  Windows ランタイム メソッドでは、配列またはメンバーを変更して JavaScript アプリに返す必要があります。  ただし、コピーされない型指定された配列 \( [たとえば、Int32Array Object][MDNInt32array]\) を使用できます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      構造体  
   :::column-end:::
   :::column span="3":::
      Windows ランタイム構造は JavaScript のオブジェクトです。  Windows ランタイム構造体を Windows ランタイム メソッドに渡す場合は、キーワードを使用して構造体をインスタンス化 `new` しない。  代わりに、オブジェクトを作成し、関連するメンバーとその値を追加します。  メンバーの名前は、キャメル ケースに含む必要 `SomeStruct.firstMember` があります。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      オブジェクト  
   :::column-end:::
   :::column span="3":::
      JavaScript オブジェクトはマネージ コード オブジェクト \( `System.Object` \) と同じではありません。  JavaScript オブジェクトを Windows ランタイム メソッドに渡す必要があります `System.Object` 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      オブジェクト ID  
   :::column-end:::
   :::column span="3":::
      ほとんどの場合、Windows ランタイムと JavaScript の間で前後に渡されるオブジェクトは変更されません。  JavaScript エンジンは、既知のオブジェクトのマップを維持します。  オブジェクトが Windows ランタイムから返されると、マップと一致し、存在しない場合は新しいオブジェクトが作成されます。  Windows ランタイム メソッドによって返されるインターフェイスを表すオブジェクトに対して、同じ手順が実行されます。  次の 2 種類の例外があります。  
      
      *   Windows ランタイム呼び出しから返され、新しい \(expando\) プロパティが追加されたオブジェクトは、新しいプロパティが Windows ランタイムに返された場合は保持されません。  ただし、JavaScript アプリに返されたオブジェクトは、既存のオブジェクトと一致するので、返されるオブジェクトには expando プロパティがあります。  
      *   Windows ランタイムの構造体とデリゲートは、以前に使用した構造体またはデリゲートと同じとして識別できません。  構造体またはデリゲートが返されるごとに、新しい参照が取得されます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      名前の競合  
   :::column-end:::
   :::column span="3":::
      複数の Windows ランタイム インターフェイスは、同じ名前のメンバーを持つ場合があります。  1 つの JavaScript オブジェクト (ランタイム クラスまたはインターフェイスを表す場合があります) で結合された場合、メンバーは完全修飾名で表されます。  これらのメンバーは、次の構文を使用して呼び出します。  
      
      ```cpp
      Class["MemberName"](parameter)
      ```  
      
      次のコードでは、2 つのインターフェイスに Draw メソッドが含まれます。ランタイム クラスは両方のインターフェイスを実装します。  
      
      ```cpp
      namespace CollisionExample {
          interface InterfaceA
          {
              HRESULT Draw([in] Int32 a);
          }
          interface InterfaceB
          {
              HRESULT Draw([in] HString a);
          }
          runtimeclass ExampleObject {
            interface InterfaceA
            interface InterfaceB
          }
      }
      ```  
      
      JavaScript で上記のコードを呼び出す方法を次に示します。  
      
      ```javascript
      var example = new ExampleObject();
      example["CollisionExample.InterfaceA.draw"](12);
      example["CollisionExample.InterfaceB.draw"]("hello");
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `Out` パラメーター  
   :::column-end:::
   :::column span="3":::
      Windows ランタイム メソッドに複数のパラメーターがある場合、JavaScript では、メソッドは戻り値として JavaScript オブジェクトを持ち、オブジェクトにはパラメーターに対応する `out` プロパティ `out` があります。  たとえば、C++ で次の Windows ランタイム署名を検討します。  
      
      ```cpp
      void ExampleMethod(
          [OutAttribute] char^ first,
          [OutAttribute] char^ second
      )
      ```  
      
      この署名の JavaScript バージョンは次の値です。  
      
      ```javascript
      var returnValue = exampleMethod();
      ```  
      
      この例では `returnValue` 、2 つのフィールドを持つ JavaScript オブジェクト `first` です `second` 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      静的メンバー  
   :::column-end:::
   :::column span="3":::
      Windows ランタイムは、静的メンバーとインスタンス メンバーの両方を定義します。  JavaScript では、Windows ランタイム クラスまたはインターフェイスに関連付けられているオブジェクトに静的メンバーが追加されます。  
      
      ```javascript
      // Static method.
      var accel = Windows.Devices.Sensors.Accelerometer.getDefault();
      // Instance method.
      var reading = accel.getCurrentReading();
      ```  
   :::column-end:::
:::row-end:::  
    
Windows ランタイムの基本型の JavaScript 表現の詳細については [、「JavaScript][WindowsRuntimeJavascriptTypes]の Windows ランタイム型の表現」を参照してください。  

<!-- links -->  
 
[WindowsRuntimeJavascriptTypes]: ./javascript-representation-of-windows-runtime-types.md "Windows ランタイム型の JavaScript 表現 |Microsoft Docs"  

[WindowsUwpComponentsCreatingCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "C++/CX の Windows ランタイム |Microsoft Docs"  
[WindowsUwpComponentsCreatingCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "Windows ランタイム コンポーネントとC#およびVisual Basic |Microsoft Docs"  

[MDNInt32array]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Int32Array "Int32Array |MDN"  
