---
description: Windows ランタイム API を使用する場合の考慮事項。
title: Windows ランタイム API を使用する際の考慮事項
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime API
ms.assetid: 2f56d70c-c80d-4876-8e6a-8ae031d31c22
caps.latest.revision: 8
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 718a23646ec9a82c1d53a2669d7cdbf218647e41
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234706"
---
# Windows ランタイム API を使用する際の考慮事項  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

JavaScript では、Windows ランタイム API のほぼすべての要素を使用できます。  ただし、Windows ランタイム要素の JavaScript 表現には、念頭に置く必要があるいくつかの側面があります。  

> [!IMPORTANT]
> C++、C#、または Visual Basic で Windows ランタイム コンポーネントを作成し、JavaScript で使用する方法については [、「C++][WindowsUwpComponentsCreatingCpp] での Windows ランタイム コンポーネントの作成」および [「C#][WindowsUwpComponentsCreatingCsharpVb]と Visual Basic での Windows ランタイム コンポーネントの作成」を参照してください。  

## Windows ランタイム型の JavaScript 表現の特殊なケース  

:::row:::
   :::column span="1":::
      文字列  
   :::column-end:::
   :::column span="3":::
      初期化されていない文字列は Windows ランタイム メソッドに文字列 "undefined" として渡され、設定された文字列は `null` 文字列 "null" として渡されます。  \(this is truewhenever a `null` or `undefined` value is coerced to a string.\) Before you pass a string to a Windows Runtime method, you should initialize it as the empty string \(""\).  
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
      Windows ランタイム配列はサイズ変更できないので、JavaScript で配列をサイズ変更するメソッドは Windows ランタイム配列では動作しません。  
      *   配列: JavaScript 配列値を Windows ランタイム メソッドに渡した場合、配列がコピーされます。  Windows ランタイム メソッドは、配列またはメンバーを変更して JavaScript アプリに返したりすることはできません。  ただし、コピーされない型指定された配列 [\(Int32Array Object][MDNInt32array]\など) を使用できます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      構造体  
   :::column-end:::
   :::column span="3":::
      Windows ランタイム構造体は JavaScript のオブジェクトです。  Windows ランタイム構造体を Windows ランタイム メソッドに渡す場合は、キーワードを使って構造体をインスタンス化 `new` しない。  代わりに、オブジェクトを作成し、関連するメンバーとその値を追加します。  メンバーの名前は、次の場合に、camel にしてください `SomeStruct.firstMember` 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      オブジェクト  
   :::column-end:::
   :::column span="3":::
      JavaScript オブジェクトはマネージ コード オブジェクト \( \) と同じ `System.Object` ではありません。  JavaScript オブジェクトは、必要な Windows ランタイム メソッドに渡す必要があります `System.Object` 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      オブジェクト ID  
   :::column-end:::
   :::column span="3":::
      ほとんどの場合、Windows ランタイムと JavaScript の間で渡されるオブジェクトは変更されません。  JavaScript エンジンは、既知のオブジェクトのマップを保持します。  オブジェクトが Windows ランタイムから返されると、マップと一致し、存在しない場合は新しいオブジェクトが作成されます。  Windows ランタイム メソッドによって返されるインターフェイスを表すオブジェクトの場合も、同じ手順が実行されます。  次の 2 種類の例外があります。  
      
      *   Windows ランタイムの呼び出しから返され、新しい \(expando\) プロパティが追加されたオブジェクトは、Windows ランタイムに戻される際に新しいプロパティを保持しません。  ただし、JavaScript アプリに返される場合は、既存のオブジェクトに一致するオブジェクトなので、返されるオブジェクトには expando プロパティがあります。  
      *   Windows ランタイムの構造体とデリゲートは、以前に使用した構造体やデリゲートと同じとして識別することはできません。  構造体またはデリゲートが返されるたび、新しい参照を取得します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      名前の競合  
   :::column-end:::
   :::column span="3":::
      複数の Windows ランタイム インターフェイスは、同じ名前のメンバーを持つ場合があります。  1 つの JavaScript オブジェクト (ランタイム クラスまたはインターフェイスを表す場合があります) に組み合わせると、メンバーは完全修飾名で表されます。  これらのメンバーは、次の構文を使用して呼び出します。  
      
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
      `Out` parameters  
   :::column-end:::
   :::column span="3":::
      Windows ランタイム メソッドに複数のパラメーターがある場合、JavaScript では、メソッドは戻り値として JavaScript オブジェクトを持ち、オブジェクトにはパラメーターに対応する `out` プロパティ `out` があります。  たとえば、C++ で次の Windows ランタイム署名を考え出します。  
      
      ```cpp
      void ExampleMethod(
          [OutAttribute] char^ first,
          [OutAttribute] char^ second
      )
      ```  
      
      この署名の JavaScript バージョンは次の形式です。  
      
      ```javascript
      var returnValue = exampleMethod();
      ```  
      
      この例では、 `returnValue` 次の 2 つのフィールドを持つ JavaScript `first` オブジェクトです `second` 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      静的メンバー  
   :::column-end:::
   :::column span="3":::
      Windows ランタイムは、静的メンバーとインスタンス メンバーの両方を定義します。  JavaScript では、静的メンバーが、Windows ランタイム クラスまたはインターフェイスに関連付けられているオブジェクトに追加されます。  
      
      ```javascript
      // Static method.
      var accel = Windows.Devices.Sensors.Accelerometer.getDefault();
      // Instance method.
      var reading = accel.getCurrentReading();
      ```  
   :::column-end:::
:::row-end:::  
    
Windows ランタイムの基本型の JavaScript 表現の詳細については [、「JavaScript Representation of Windows Runtime Types」を参照してください][WindowsRuntimeJavascriptTypes]。  

<!-- links -->  
 
[WindowsRuntimeJavascriptTypes]: ./javascript-representation-of-windows-runtime-types.md "Windows ランタイム型の JavaScript 表現 |Microsoft Docs"

[WindowsUwpComponentsCreatingCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "C++/CX を使った Windows ランタイム コンポーネント |Microsoft Docs"  
[WindowsUwpComponentsCreatingCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "C# と Visual Basic を使った Windows ランタイム コンポーネント |Microsoft Docs"  

[MDNInt32array]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Int32Array "Int32Array |MDN"  
