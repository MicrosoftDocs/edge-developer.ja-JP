---
title: Windows ランタイム API を使用する際の考慮事項
ms.custom: ''
ms.date: 07/29/2020
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.technology: windows-integration
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime API
ms.assetid: 2f56d70c-c80d-4876-8e6a-8ae031d31c22
caps.latest.revision: 8
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 6b460fe514927590382613b7454a69c89a5a5f8b
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942218"
---
# Windows ランタイム API を使用する場合の考慮事例  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

JavaScript では、Windows ランタイム API のうら、近くすべての要素を使用できます。  ただし、Windows ランタイム要素の JavaScript 表現には、いくつかの点にごご安をおかけください。  

> [!IMPORTANT]
> C++、C#、または Visual Basic で Windows ランタイム コンポーントを作成し、JavaScript で使用する方法については [、「C++ コン][WindowsUwpComponentsCreatingCpp] ポーントを C++ に作成し、C# と Visual Basic で Windows ランタイム コンポー [ポントを作成する」を参照してください][WindowsUwpComponentsCreatingCsharpVb]。  

## Windows ランタイムの種類の JavaScript Representation の特殊なケース  

:::row:::
   :::column span="1":::
      文字列  
   :::column-end:::
   :::column span="3":::
      Windows ランタイムメソッドに渡され、文字列セットは文字列 `null` "null" として渡されます。  \(これは、文字列に 1 または値が同時に変換されるたびに true です) \ (文字列を Windows ランタイム メソッドに入力する前に、その文字列を `null` `undefined` "\"\) として初めて使用する必要があります。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      インターフェイス  
   :::column-end:::
   :::column span="3":::
      JavaScript では Windows ランタイム インターフェイスを実装することはできません。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      配列  
   :::column-end:::
   :::column span="3":::
      Windows ランタイム配列はサイズ変更できません。そのため、JavaScript 内の配列のサイズを変更するメソッドは、Windows ランタイム配列では機能しません。  
      *   配列: JavaScript 配列値を Windows ランタイムメソッドにパスすると、配列がコピーされます。  Windows ランタイムのメソッドは、配列またはそのメンバーを変更して、JavaScript アプリに返すことはできません。  ただし、タイプ指定された配列 [\(Int32Array Object][MDNInt32array]\) はコピーしないで使用できます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      構造体  
   :::column-end:::
   :::column span="3":::
      Windows ランタイム構造体は、JavaScript のオブジェクトです。  Windows ランタイム構造を Windows ランタイムメソッドに合理化する場合は、キーワードを使用して構造をインスタンス化しない `new` でください。  代わりに、オブジェクトを作成し、メンバーとその値を追加します。  メンバーの名前は、カメセル ケースに含める必要があります `SomeStruct.firstMember` 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      オブジェクト  
   :::column-end:::
   :::column span="3":::
      JavaScript オブジェクトは、管理コード オブジェクト \( \) と同じで `System.Object` はありません。  JavaScript オブジェクトを、必要な Windows ランタイム メソッドに変換することはできません `System.Object` 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      オブジェクト ID  
   :::column-end:::
   :::column span="3":::
      ほとんどの場合、Windows ランタイムと JavaScript の間で戻っても、オブジェクトは変わりません。  JavaScript エンジンでは、既知のオブジェクトのマップが保持されます。  Windows ランタイムからオブジェクトがマップと一致した場合、新しいオブジェクトが作成されない場合は、オブジェクトが Windows ランタイムから返されます。  同じ手順は、Windows ランタイムの方法によって返されるインターフェイスを表すオブジェクトに対しても適用されます。  例外には 2 種類の例外があります。  
      
      *   Windows ランタイム呼び出しから返されたオブジェクトを追加した後、新しい \(expando\) プロパティが追加された後に、Windows ランタイムに戻したときに新しいプロパティを残していません。  ただし、JavaScript アプリに戻ると、返されるオブジェクトは拡張プロパティになります。  
      *   Windows ランタイムの構造と代理人は、以前使用されている構造体または代理人と同じと識別することはできません。  構造または代理人が返されるたびに、新しい参照が取得されます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      名前の選択  
   :::column-end:::
   :::column span="3":::
      複数の Windows ランタイム インターフェイスには、同じ名前のメンバーを割り当てることができます。  それらを単一の JavaScript オブジェクト (ランタイム クラスまたはインターフェイスの表現になる) 場合、メンバーは完全に完全な一飾名で表されます。  これらのメンバーは次の構文を使用して呼び出すことができます。  
      
      ```cpp
      Class["MemberName"](parameter)
      ```  
      
      次のコードでは、2 つのインターフェイスには描画方法があり、ランタイム クラスには両方のインターフェイスが実装されています。  
      
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
      
      JavaScript で上述のコードを呼び出す方法を示します。  
      
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
      Windows ランタイム メソッドに複数のパラ `out` メーターがある場合、JavaScript では、メソッドに戻り値として JavaScript オブジェクトが含まれています。そのオブジェクトには、パラメーターに対応するプロパティがあります `out` 。  たとえば、C++ で、次の Windows ランタイム署名を検定します。  
      
      ```cpp
      void ExampleMethod(
          [OutAttribute] char^ first,
          [OutAttribute] char^ second
      )
      ```  
      
      この署名の JavaScript バージョンは次のとおりです。  
      
      ```javascript
      var returnValue = exampleMethod();
      ```  
      
      この例では `returnValue` 、JavaScript オブジェクトで、次の 2 つのフィールドがあります `first` `second` 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      スタティック メンバー  
   :::column-end:::
   :::column span="3":::
      Windows ランタイムでは、スタティック メンバーとインスタンス メンバーの両方が定義されます。  JavaScript では、Windows ランタイム クラスまたはインターフェイスに関連付けられているオブジェクトにスタティック メンバーが追加されます。  
      
      ```javascript
      // Static method.
      var accel = Windows.Devices.Sensors.Accelerometer.getDefault();
      // Instance method.
      var reading = accel.getCurrentReading();
      ```  
   :::column-end:::
:::row-end:::  
    
Windows ランタイムの基本種類の JavaScript 表現の詳細については [、Windows ランタイムの種類の JavaScript 表現を参照してください][WindowsRuntimeJavascriptTypes]。  

<!-- links -->  
 
[WindowsRuntimeJavascriptTypes]: ./javascript-representation-of-windows-runtime-types.md "Windows ランタイムの種類の JavaScript 表記 |Microsoft ドキュメント"

[WindowsUwpComponentsCreatingCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "C++/CX を使用した Windows ランタイム コンポーネント |Microsoft ドキュメント"  
[WindowsUwpComponentsCreatingCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "C# およびデバイスを使用した Windows ランタイム コンポーVisual BasicンVisual Basic |Microsoft ドキュメント"  

[MDNInt32array]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Int32Array "Int32Array |MDN"  