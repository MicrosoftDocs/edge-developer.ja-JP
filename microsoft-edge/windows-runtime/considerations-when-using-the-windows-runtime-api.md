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
# <span data-ttu-id="86ca5-102">Windows ランタイム API を使用する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="86ca5-102">Considerations when Using the Windows Runtime API</span></span>  

<span data-ttu-id="86ca5-103">JavaScript では、Windows ランタイム API のほぼすべての要素を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="86ca5-103">You can use nearly every element of the Windows Runtime API in JavaScript.</span></span>  <span data-ttu-id="86ca5-104">ただし、Windows ランタイム要素の JavaScript 表現については、いくつかの点に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86ca5-104">However, there are some aspects of the JavaScript representation of Windows Runtime elements that you should keep in mind.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="86ca5-105">C++、C#、または Visual Basic での Windows ランタイムコンポーネントの作成と JavaScript での使用については、「 [c++ での Windows ランタイムコンポーネントの作成][WindowsUwpComponentsCreatingCpp]と[C# および Visual Basic での windows][WindowsUwpComponentsCreatingCsharpVb]ランタイムコンポーネントの作成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86ca5-105">For information about creating Windows Runtime components in C++, C#, or Visual Basic and consuming them in JavaScript, see [Creating Windows Runtime Components in C++][WindowsUwpComponentsCreatingCpp] and [Creating Windows Runtime Components in C# and Visual Basic][WindowsUwpComponentsCreatingCsharpVb].</span></span>  

## <span data-ttu-id="86ca5-106">Windows ランタイム型の JavaScript 表現での特殊なケース</span><span class="sxs-lookup"><span data-stu-id="86ca5-106">Special Cases in the JavaScript Representation of Windows Runtime Types</span></span>  

*   <span data-ttu-id="86ca5-107">文字列: 初期化されていない文字列は、"undefined" という文字列として Windows ランタイムメソッドに渡し、文字列 `null` "null" として渡されます。</span><span class="sxs-lookup"><span data-stu-id="86ca5-107">Strings: An uninitialized string is passed to a Windows Runtime method as the string "undefined", and a string set to `null` is passed as the string "null".</span></span>  <span data-ttu-id="86ca5-108">\ (A `null` または `undefined` 値が文字列に変換されるたびに true になります)。文字列を Windows ランタイムメソッドに渡す前に、空の文字列 \ ("") として初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86ca5-108">\(This is true whenever a `null` or `undefined` value is coerced to a string.\)  Before you pass a string to a Windows Runtime method, you should initialize it as the empty string \(""\).</span></span>  
*   <span data-ttu-id="86ca5-109">インターフェイス: JavaScript で Windows ランタイムインターフェイスを実装することはできません。</span><span class="sxs-lookup"><span data-stu-id="86ca5-109">Interfaces: You cannot implement a Windows Runtime interface in JavaScript.</span></span>  
*   <span data-ttu-id="86ca5-110">配列: Windows ランタイム配列のサイズは変更できません。そのため、JavaScript で配列のサイズを変更するメソッドは、Windows ランタイム配列では動作しません。</span><span class="sxs-lookup"><span data-stu-id="86ca5-110">Arrays: Windows Runtime arrays are not resizable, so methods that resize arrays in JavaScript do not work on Windows Runtime arrays.</span></span>  
*   <span data-ttu-id="86ca5-111">配列: JavaScript 配列値を Windows ランタイムメソッドに渡すと、配列がコピーされます。</span><span class="sxs-lookup"><span data-stu-id="86ca5-111">Arrays: If you pass a JavaScript array value to a Windows Runtime method, the array is copied.</span></span>  <span data-ttu-id="86ca5-112">Windows ランタイムメソッドでは、配列やそのメンバーを変更して JavaScript アプリに返すことはできません。</span><span class="sxs-lookup"><span data-stu-id="86ca5-112">The Windows Runtime method is not able to modify the array or its members and return it to your JavaScript app.</span></span>  <span data-ttu-id="86ca5-113">ただし、入力された配列を使うことができます (たとえば、 [Int32Array Object][MDNInt32array]\)。コピーされません。</span><span class="sxs-lookup"><span data-stu-id="86ca5-113">However, you can use typed arrays \(for example, [Int32Array Object][MDNInt32array]\), which are not copied.</span></span>  
*   <span data-ttu-id="86ca5-114">構造体: Windows ランタイム構造体は JavaScript のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="86ca5-114">Structures: Windows Runtime structures are objects in JavaScript.</span></span>  <span data-ttu-id="86ca5-115">Windows ランタイムメソッドに Windows ランタイム構造体を渡す場合、キーワードで構造体をインスタンス化しないで `new` ください。</span><span class="sxs-lookup"><span data-stu-id="86ca5-115">If you want to pass a Windows Runtime structure to a Windows Runtime method, don't instantiate the structure with the `new` keyword.</span></span>  <span data-ttu-id="86ca5-116">代わりに、オブジェクトを作成し、関連するメンバーとその値を追加します。</span><span class="sxs-lookup"><span data-stu-id="86ca5-116">Instead, create an object and add the relevant members and their values.</span></span>  <span data-ttu-id="86ca5-117">メンバーの名前は camel 形式である必要があり `SomeStruct.firstMember` ます。</span><span class="sxs-lookup"><span data-stu-id="86ca5-117">The names of the members should be in camel case: `SomeStruct.firstMember`.</span></span>  
*   <span data-ttu-id="86ca5-118">オブジェクト: JavaScript オブジェクトは、マネージコードオブジェクト \ (\) とは異なり `System.Object` ます。</span><span class="sxs-lookup"><span data-stu-id="86ca5-118">Objects: JavaScript objects aren't the same as managed code objects \(`System.Object`\).</span></span>  <span data-ttu-id="86ca5-119">JavaScript オブジェクトは、を必要とする Windows ランタイムメソッドに渡すことはできません `System.Object` 。</span><span class="sxs-lookup"><span data-stu-id="86ca5-119">You can't pass a JavaScript object to a Windows Runtime method that requires a `System.Object`.</span></span>  
*   <span data-ttu-id="86ca5-120">オブジェクト id: ほとんどの場合、Windows ランタイムと JavaScript の間でやり取りされるオブジェクトは変更されません。</span><span class="sxs-lookup"><span data-stu-id="86ca5-120">Object identity: In most cases, the objects passed back and forth between the Windows Runtime and JavaScript do not change.</span></span>  <span data-ttu-id="86ca5-121">JavaScript エンジンは既知のオブジェクトのマップを保持します。</span><span class="sxs-lookup"><span data-stu-id="86ca5-121">The JavaScript engine maintains a map of known objects.</span></span>  <span data-ttu-id="86ca5-122">Windows ランタイムから返されたオブジェクトは、マップと照合されます。存在しない場合は、新しいオブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="86ca5-122">When an object is returned from the Windows Runtime it is matched against the map, and if it does not exist a new object is created.</span></span>  <span data-ttu-id="86ca5-123">Windows ランタイムメソッドによって返されるインターフェイスを表すオブジェクトの場合も、同じ手順に従います。</span><span class="sxs-lookup"><span data-stu-id="86ca5-123">The same procedure is followed for objects that represent interfaces that are returned by Windows Runtime methods.</span></span>  <span data-ttu-id="86ca5-124">例外には次の2種類があります。</span><span class="sxs-lookup"><span data-stu-id="86ca5-124">There are two kinds of exceptions:</span></span>  

    *   <span data-ttu-id="86ca5-125">Windows ランタイム呼び出しから返されるオブジェクトで、新しい \ (expando \) プロパティが追加されている場合、Windows ランタイムに戻されたときに、新しいプロパティは保持されません。</span><span class="sxs-lookup"><span data-stu-id="86ca5-125">Objects that are returned from a Windows Runtime call, and then have new \(expando\) properties added, don't retain their new properties when they are passed back to the Windows Runtime.</span></span>  <span data-ttu-id="86ca5-126">ただし、JavaScript アプリに戻された場合は、既存のオブジェクトと一致しているため、返されるオブジェクトには expando プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="86ca5-126">However, when they are returned to the JavaScript app, because they're matched to the existing object, the returned object does have the expando properties.</span></span>  
    *   <span data-ttu-id="86ca5-127">Windows ランタイムの構造とデリゲートは、以前に使用した構造体またはデリゲートと同一として識別することはできません。</span><span class="sxs-lookup"><span data-stu-id="86ca5-127">Structures and delegates in Windows Runtime can't be identified as identical to previously-used structures or delegates.</span></span>  <span data-ttu-id="86ca5-128">構造体またはデリゲートが返されるたびに、新しい参照が取得されます。</span><span class="sxs-lookup"><span data-stu-id="86ca5-128">Every time a structure or delegate is returned, it gets a new reference.</span></span>  

*   <span data-ttu-id="86ca5-129">名前の競合: 複数の Windows ランタイムインターフェイスには、同じ名前のメンバーが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="86ca5-129">Name collisions: Multiple Windows Runtime interfaces may have members with the same names.</span></span>  <span data-ttu-id="86ca5-130">1つの JavaScript オブジェクト (ランタイムクラスまたはインターフェイスの表現) で結合される場合、メンバーは完全修飾名で表されます。</span><span class="sxs-lookup"><span data-stu-id="86ca5-130">If they are combined in a single JavaScript object (which can be a representation of a runtime class or an interface), the members are represented with fully-qualified names.</span></span>  <span data-ttu-id="86ca5-131">次の構文を使用して、これらのメンバーを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="86ca5-131">You can call these members by using the following syntax:</span></span>  
    
    ```cpp
    Class["MemberName"](parameter)
    ```  
    
    <span data-ttu-id="86ca5-132">次のコードでは、2つのインターフェイスに描画メソッドがあり、ランタイムクラスは両方のインターフェイスを実装しています。</span><span class="sxs-lookup"><span data-stu-id="86ca5-132">In the following code, two interfaces have a Draw method, and a runtime class implements both interfaces.</span></span>  
    
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
    
    <span data-ttu-id="86ca5-133">JavaScript で上記のコードを呼び出す方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="86ca5-133">Here is how you can call the above code in JavaScript.</span></span>  
    
    ```javascript
    var example = new ExampleObject();
    example["CollisionExample.InterfaceA.draw"](12);
    example["CollisionExample.InterfaceB.draw"]("hello");
    ```  
    
*   `Out` <span data-ttu-id="86ca5-134">パラメーター: Windows ランタイムメソッドに複数のパラメーターがある場合 `out` 、javascript では、メソッドはその戻り値として JavaScript オブジェクトを持ち、オブジェクトにはパラメーターに対応するプロパティがあります `out` 。</span><span class="sxs-lookup"><span data-stu-id="86ca5-134">parameters: If a Windows Runtime method has multiple `out` parameters, in JavaScript the method has a JavaScript object as its return value, and the object has properties that correspond to the `out` parameter.</span></span>  <span data-ttu-id="86ca5-135">たとえば、次のような Windows ランタイム署名を C++ で検討します。</span><span class="sxs-lookup"><span data-stu-id="86ca5-135">For example, consider the following Windows Runtime signature in C++.</span></span>  
    
    ```cpp
    void ExampleMethod(
      [OutAttribute] char^ first,
      [OutAttribute] char^ second
    )
    ```  
    
    <span data-ttu-id="86ca5-136">この署名の JavaScript バージョンは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="86ca5-136">The JavaScript version of this signature is:</span></span>  
    
    ```javascript
    var returnValue = exampleMethod();
    ```  
    
    <span data-ttu-id="86ca5-137">この例では、" `returnValue` and" という2つのフィールドを持つ JavaScript オブジェクトを示し `first` `second` ます。</span><span class="sxs-lookup"><span data-stu-id="86ca5-137">In this example, `returnValue` is a JavaScript object that has two fields: `first` and `second`.</span></span>  
    
*   <span data-ttu-id="86ca5-138">静的メンバー: Windows ランタイムでは、静的メンバーとインスタンスメンバーの両方が定義されています。</span><span class="sxs-lookup"><span data-stu-id="86ca5-138">Static members: The Windows Runtime defines both static members and instance members.</span></span>  <span data-ttu-id="86ca5-139">JavaScript では、静的メンバーは、Windows ランタイムクラスまたはインターフェイスに関連付けられたオブジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="86ca5-139">In JavaScript, static members are added to the object that is associated with the Windows Runtime class or interface.</span></span>  
    
    ```javascript
    // Static method.
    var accel = Windows.Devices.Sensors.Accelerometer.getDefault();
    // Instance method.
    var reading = accel.getCurrentReading();
    ```  
    
<span data-ttu-id="86ca5-140">Windows ランタイムの基本型の JavaScript 表現の詳細については、「 [Windows ランタイム型の Javascript 表現][WindowsRuntimeJavascriptTypes]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86ca5-140">For more information about the JavaScript representation of Windows Runtime basic types, see [JavaScript Representation of Windows Runtime Types][WindowsRuntimeJavascriptTypes].</span></span>  

<!-- image links -->  

<!-- links -->  
 
[WindowsRuntimeJavascriptTypes]: /microsoft-edge/windows-runtime/javascript-representation-of-windows-runtime-types "Windows ランタイム型の JavaScript 表現"

[WindowsUwpComponentsCreatingCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "C++/CX を備えた Windows ランタイムコンポーネント"  
[WindowsUwpComponentsCreatingCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "C# と Visual Basic を使った Windows ランタイムコンポーネント"  

[MDNInt32array]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Int32Array "Int32Array |MDN"  