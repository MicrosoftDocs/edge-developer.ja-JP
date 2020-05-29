---
title: Windows ランタイム API を使用する際の考慮事項
ms.custom: ''
ms.date: 04/01/2020
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
ms.openlocfilehash: 95b082e27c4f247b841a9540e13bd49bd4c8bd67
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570794"
---
# Windows ランタイム API を使用する際の考慮事項  

JavaScript では、Windows ランタイム API のほぼすべての要素を使うことができます。  ただし、Windows ランタイム要素の JavaScript 表現については、いくつかの点に注意する必要があります。  

> [!IMPORTANT]
> C++、C#、または Visual Basic での Windows ランタイムコンポーネントの作成と JavaScript での使用については、「 [c++ での Windows ランタイムコンポーネントの作成][WindowsUwpComponentsCreatingCpp]と[C# および Visual Basic での windows][WindowsUwpComponentsCreatingCsharpVb]ランタイムコンポーネントの作成」を参照してください。  

## Windows ランタイム型の JavaScript 表現での特殊なケース  

*   文字列: 初期化されていない文字列は、"undefined" という文字列として Windows ランタイムメソッドに渡し、文字列 `null` "null" として渡されます。  \ (A `null` または `undefined` 値が文字列に変換されるたびに true になります)。文字列を Windows ランタイムメソッドに渡す前に、空の文字列 \ ("") として初期化する必要があります。  
*   インターフェイス: JavaScript で Windows ランタイムインターフェイスを実装することはできません。  
*   配列: Windows ランタイム配列のサイズは変更できません。そのため、JavaScript で配列のサイズを変更するメソッドは、Windows ランタイム配列では動作しません。  
*   配列: JavaScript 配列値を Windows ランタイムメソッドに渡すと、配列がコピーされます。  Windows ランタイムメソッドでは、配列やそのメンバーを変更して JavaScript アプリに返すことはできません。  ただし、入力された配列を使うことができます (たとえば、 [Int32Array Object][MDNInt32array]\)。コピーされません。  
*   構造体: Windows ランタイム構造体は JavaScript のオブジェクトです。  Windows ランタイムメソッドに Windows ランタイム構造体を渡す場合、キーワードで構造体をインスタンス化しないで `new` ください。  代わりに、オブジェクトを作成し、関連するメンバーとその値を追加します。  メンバーの名前は camel 形式である必要があり `SomeStruct.firstMember` ます。  
*   オブジェクト: JavaScript オブジェクトは、マネージコードオブジェクト \ (\) とは異なり `System.Object` ます。  JavaScript オブジェクトは、を必要とする Windows ランタイムメソッドに渡すことはできません `System.Object` 。  
*   オブジェクト id: ほとんどの場合、Windows ランタイムと JavaScript の間でやり取りされるオブジェクトは変更されません。  JavaScript エンジンは既知のオブジェクトのマップを保持します。  Windows ランタイムから返されたオブジェクトは、マップと照合されます。存在しない場合は、新しいオブジェクトが作成されます。  Windows ランタイムメソッドによって返されるインターフェイスを表すオブジェクトの場合も、同じ手順に従います。  例外には次の2種類があります。  

    *   Windows ランタイム呼び出しから返されるオブジェクトで、新しい \ (expando \) プロパティが追加されている場合、Windows ランタイムに戻されたときに、新しいプロパティは保持されません。  ただし、JavaScript アプリに戻された場合は、既存のオブジェクトと一致しているため、返されるオブジェクトには expando プロパティがあります。  
    *   Windows ランタイムの構造とデリゲートは、以前に使用した構造体またはデリゲートと同一として識別することはできません。  構造体またはデリゲートが返されるたびに、新しい参照が取得されます。  

*   名前の競合: 複数の Windows ランタイムインターフェイスには、同じ名前のメンバーが含まれている場合があります。  1つの JavaScript オブジェクト (ランタイムクラスまたはインターフェイスの表現) で結合される場合、メンバーは完全修飾名で表されます。  次の構文を使用して、これらのメンバーを呼び出すことができます。  
    
    ```cpp
    Class["MemberName"](parameter)
    ```  
    
    次のコードでは、2つのインターフェイスに描画メソッドがあり、ランタイムクラスは両方のインターフェイスを実装しています。  
    
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
    
*   `Out` パラメーター: Windows ランタイムメソッドに複数のパラメーターがある場合 `out` 、javascript では、メソッドはその戻り値として JavaScript オブジェクトを持ち、オブジェクトにはパラメーターに対応するプロパティがあります `out` 。  たとえば、次のような Windows ランタイム署名を C++ で検討します。  
    
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
    
    この例では、" `returnValue` and" という2つのフィールドを持つ JavaScript オブジェクトを示し `first` `second` ます。  
    
*   静的メンバー: Windows ランタイムでは、静的メンバーとインスタンスメンバーの両方が定義されています。  JavaScript では、静的メンバーは、Windows ランタイムクラスまたはインターフェイスに関連付けられたオブジェクトに追加されます。  
    
    ```javascript
    // Static method.
    var accel = Windows.Devices.Sensors.Accelerometer.getDefault();
    // Instance method.
    var reading = accel.getCurrentReading();
    ```  
    
Windows ランタイムの基本型の JavaScript 表現の詳細については、「 [Windows ランタイム型の Javascript 表現][WindowsRuntimeJavascriptTypes]」を参照してください。  

<!-- image links -->  

<!-- links -->  
 
[WindowsRuntimeJavascriptTypes]: /microsoft-edge/windows-runtime/javascript-representation-of-windows-runtime-types "Windows ランタイム型の JavaScript 表現"

[WindowsUwpComponentsCreatingCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "C++/CX を備えた Windows ランタイムコンポーネント"  
[WindowsUwpComponentsCreatingCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "C# と Visual Basic を使った Windows ランタイムコンポーネント"  

[MDNInt32array]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Int32Array "Int32Array |MDN"  