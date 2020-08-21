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
# <span data-ttu-id="3a53b-102">Windows ランタイム API を使用する場合の考慮事例</span><span class="sxs-lookup"><span data-stu-id="3a53b-102">Considerations when using the Windows Runtime API</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="3a53b-103">JavaScript では、Windows ランタイム API のうら、近くすべての要素を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a53b-103">You can use nearly every element of the Windows Runtime API in JavaScript.</span></span>  <span data-ttu-id="3a53b-104">ただし、Windows ランタイム要素の JavaScript 表現には、いくつかの点にごご安をおかけください。</span><span class="sxs-lookup"><span data-stu-id="3a53b-104">However, there are some aspects of the JavaScript representation of Windows Runtime elements that you should keep in mind.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="3a53b-105">C++、C#、または Visual Basic で Windows ランタイム コンポーントを作成し、JavaScript で使用する方法については [、「C++ コン][WindowsUwpComponentsCreatingCpp] ポーントを C++ に作成し、C# と Visual Basic で Windows ランタイム コンポー [ポントを作成する」を参照してください][WindowsUwpComponentsCreatingCsharpVb]。</span><span class="sxs-lookup"><span data-stu-id="3a53b-105">For information about creating Windows Runtime components in C++, C#, or Visual Basic and consuming them in JavaScript, see [Creating Windows Runtime Components in C++][WindowsUwpComponentsCreatingCpp] and [Creating Windows Runtime Components in C# and Visual Basic][WindowsUwpComponentsCreatingCsharpVb].</span></span>  

## <span data-ttu-id="3a53b-106">Windows ランタイムの種類の JavaScript Representation の特殊なケース</span><span class="sxs-lookup"><span data-stu-id="3a53b-106">Special cases in the JavaScript Representation of Windows Runtime types</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="3a53b-107">文字列</span><span class="sxs-lookup"><span data-stu-id="3a53b-107">Strings</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="3a53b-108">Windows ランタイムメソッドに渡され、文字列セットは文字列 `null` "null" として渡されます。</span><span class="sxs-lookup"><span data-stu-id="3a53b-108">An uninitialized string is passed to a Windows Runtime method as the string "undefined", and a string set to `null` is passed as the string "null".</span></span>  <span data-ttu-id="3a53b-109">\(これは、文字列に 1 または値が同時に変換されるたびに true です) \ (文字列を Windows ランタイム メソッドに入力する前に、その文字列を `null` `undefined` "\"\) として初めて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a53b-109">\(This is true whenever a `null` or `undefined` value is coerced to a string.\)  Before you pass a string to a Windows Runtime method, you should initialize it as the empty string \(""\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="3a53b-110">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a53b-110">Interfaces</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="3a53b-111">JavaScript では Windows ランタイム インターフェイスを実装することはできません。</span><span class="sxs-lookup"><span data-stu-id="3a53b-111">You cannot implement a Windows Runtime interface in JavaScript.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="3a53b-112">配列</span><span class="sxs-lookup"><span data-stu-id="3a53b-112">Arrays</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="3a53b-113">Windows ランタイム配列はサイズ変更できません。そのため、JavaScript 内の配列のサイズを変更するメソッドは、Windows ランタイム配列では機能しません。</span><span class="sxs-lookup"><span data-stu-id="3a53b-113">Windows Runtime arrays are not resizable, so methods that resize arrays in JavaScript do not work on Windows Runtime arrays.</span></span>  
      *   <span data-ttu-id="3a53b-114">配列: JavaScript 配列値を Windows ランタイムメソッドにパスすると、配列がコピーされます。</span><span class="sxs-lookup"><span data-stu-id="3a53b-114">Arrays: If you pass a JavaScript array value to a Windows Runtime method, the array is copied.</span></span>  <span data-ttu-id="3a53b-115">Windows ランタイムのメソッドは、配列またはそのメンバーを変更して、JavaScript アプリに返すことはできません。</span><span class="sxs-lookup"><span data-stu-id="3a53b-115">The Windows Runtime method is not able to modify the array or its members and return it to your JavaScript app.</span></span>  <span data-ttu-id="3a53b-116">ただし、タイプ指定された配列 [\(Int32Array Object][MDNInt32array]\) はコピーしないで使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a53b-116">However, you can use typed arrays \(for example, [Int32Array Object][MDNInt32array]\), which are not copied.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="3a53b-117">構造体</span><span class="sxs-lookup"><span data-stu-id="3a53b-117">Structures</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="3a53b-118">Windows ランタイム構造体は、JavaScript のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="3a53b-118">Windows Runtime structures are objects in JavaScript.</span></span>  <span data-ttu-id="3a53b-119">Windows ランタイム構造を Windows ランタイムメソッドに合理化する場合は、キーワードを使用して構造をインスタンス化しない `new` でください。</span><span class="sxs-lookup"><span data-stu-id="3a53b-119">If you want to pass a Windows Runtime structure to a Windows Runtime method, don't instantiate the structure with the `new` keyword.</span></span>  <span data-ttu-id="3a53b-120">代わりに、オブジェクトを作成し、メンバーとその値を追加します。</span><span class="sxs-lookup"><span data-stu-id="3a53b-120">Instead, create an object and add the relevant members and their values.</span></span>  <span data-ttu-id="3a53b-121">メンバーの名前は、カメセル ケースに含める必要があります `SomeStruct.firstMember` 。</span><span class="sxs-lookup"><span data-stu-id="3a53b-121">The names of the members should be in camel case: `SomeStruct.firstMember`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="3a53b-122">オブジェクト</span><span class="sxs-lookup"><span data-stu-id="3a53b-122">Objects</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="3a53b-123">JavaScript オブジェクトは、管理コード オブジェクト \( \) と同じで `System.Object` はありません。</span><span class="sxs-lookup"><span data-stu-id="3a53b-123">JavaScript objects aren't the same as managed code objects \(`System.Object`\).</span></span>  <span data-ttu-id="3a53b-124">JavaScript オブジェクトを、必要な Windows ランタイム メソッドに変換することはできません `System.Object` 。</span><span class="sxs-lookup"><span data-stu-id="3a53b-124">You can't pass a JavaScript object to a Windows Runtime method that requires a `System.Object`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="3a53b-125">オブジェクト ID</span><span class="sxs-lookup"><span data-stu-id="3a53b-125">Object identity</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="3a53b-126">ほとんどの場合、Windows ランタイムと JavaScript の間で戻っても、オブジェクトは変わりません。</span><span class="sxs-lookup"><span data-stu-id="3a53b-126">In most cases, the objects passed back and forth between the Windows Runtime and JavaScript do not change.</span></span>  <span data-ttu-id="3a53b-127">JavaScript エンジンでは、既知のオブジェクトのマップが保持されます。</span><span class="sxs-lookup"><span data-stu-id="3a53b-127">The JavaScript engine maintains a map of known objects.</span></span>  <span data-ttu-id="3a53b-128">Windows ランタイムからオブジェクトがマップと一致した場合、新しいオブジェクトが作成されない場合は、オブジェクトが Windows ランタイムから返されます。</span><span class="sxs-lookup"><span data-stu-id="3a53b-128">When an object is returned from the Windows Runtime it is matched against the map, and if it does not exist a new object is created.</span></span>  <span data-ttu-id="3a53b-129">同じ手順は、Windows ランタイムの方法によって返されるインターフェイスを表すオブジェクトに対しても適用されます。</span><span class="sxs-lookup"><span data-stu-id="3a53b-129">The same procedure is followed for objects that represent interfaces that are returned by Windows Runtime methods.</span></span>  <span data-ttu-id="3a53b-130">例外には 2 種類の例外があります。</span><span class="sxs-lookup"><span data-stu-id="3a53b-130">There are two kinds of exceptions:</span></span>  
      
      *   <span data-ttu-id="3a53b-131">Windows ランタイム呼び出しから返されたオブジェクトを追加した後、新しい \(expando\) プロパティが追加された後に、Windows ランタイムに戻したときに新しいプロパティを残していません。</span><span class="sxs-lookup"><span data-stu-id="3a53b-131">Objects that are returned from a Windows Runtime call, and then have new \(expando\) properties added, don't retain their new properties when they are passed back to the Windows Runtime.</span></span>  <span data-ttu-id="3a53b-132">ただし、JavaScript アプリに戻ると、返されるオブジェクトは拡張プロパティになります。</span><span class="sxs-lookup"><span data-stu-id="3a53b-132">However, when they are returned to the JavaScript app, because they're matched to the existing object, the returned object does have the expando properties.</span></span>  
      *   <span data-ttu-id="3a53b-133">Windows ランタイムの構造と代理人は、以前使用されている構造体または代理人と同じと識別することはできません。</span><span class="sxs-lookup"><span data-stu-id="3a53b-133">Structures and delegates in Windows Runtime can't be identified as identical to previously-used structures or delegates.</span></span>  <span data-ttu-id="3a53b-134">構造または代理人が返されるたびに、新しい参照が取得されます。</span><span class="sxs-lookup"><span data-stu-id="3a53b-134">Every time a structure or delegate is returned, it gets a new reference.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="3a53b-135">名前の選択</span><span class="sxs-lookup"><span data-stu-id="3a53b-135">Name collisions</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="3a53b-136">複数の Windows ランタイム インターフェイスには、同じ名前のメンバーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3a53b-136">Multiple Windows Runtime interfaces may have members with the same names.</span></span>  <span data-ttu-id="3a53b-137">それらを単一の JavaScript オブジェクト (ランタイム クラスまたはインターフェイスの表現になる) 場合、メンバーは完全に完全な一飾名で表されます。</span><span class="sxs-lookup"><span data-stu-id="3a53b-137">If they are combined in a single JavaScript object (which can be a representation of a runtime class or an interface), the members are represented with fully-qualified names.</span></span>  <span data-ttu-id="3a53b-138">これらのメンバーは次の構文を使用して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="3a53b-138">You can call these members by using the following syntax:</span></span>  
      
      ```cpp
      Class["MemberName"](parameter)
      ```  
      
      <span data-ttu-id="3a53b-139">次のコードでは、2 つのインターフェイスには描画方法があり、ランタイム クラスには両方のインターフェイスが実装されています。</span><span class="sxs-lookup"><span data-stu-id="3a53b-139">In the following code, two interfaces have a Draw method, and a runtime class implements both interfaces.</span></span>  
      
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
      
      <span data-ttu-id="3a53b-140">JavaScript で上述のコードを呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3a53b-140">Here is how you can call the above code in JavaScript.</span></span>  
      
      ```javascript
      var example = new ExampleObject();
      example["CollisionExample.InterfaceA.draw"](12);
      example["CollisionExample.InterfaceB.draw"]("hello");
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `Out` <span data-ttu-id="3a53b-141">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3a53b-141">parameters</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="3a53b-142">Windows ランタイム メソッドに複数のパラ `out` メーターがある場合、JavaScript では、メソッドに戻り値として JavaScript オブジェクトが含まれています。そのオブジェクトには、パラメーターに対応するプロパティがあります `out` 。</span><span class="sxs-lookup"><span data-stu-id="3a53b-142">If a Windows Runtime method has multiple `out` parameters, in JavaScript the method has a JavaScript object as its return value, and the object has properties that correspond to the `out` parameter.</span></span>  <span data-ttu-id="3a53b-143">たとえば、C++ で、次の Windows ランタイム署名を検定します。</span><span class="sxs-lookup"><span data-stu-id="3a53b-143">For example, consider the following Windows Runtime signature in C++.</span></span>  
      
      ```cpp
      void ExampleMethod(
          [OutAttribute] char^ first,
          [OutAttribute] char^ second
      )
      ```  
      
      <span data-ttu-id="3a53b-144">この署名の JavaScript バージョンは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3a53b-144">The JavaScript version of this signature is:</span></span>  
      
      ```javascript
      var returnValue = exampleMethod();
      ```  
      
      <span data-ttu-id="3a53b-145">この例では `returnValue` 、JavaScript オブジェクトで、次の 2 つのフィールドがあります `first` `second` 。</span><span class="sxs-lookup"><span data-stu-id="3a53b-145">In this example, `returnValue` is a JavaScript object that has two fields: `first` and `second`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="3a53b-146">スタティック メンバー</span><span class="sxs-lookup"><span data-stu-id="3a53b-146">Static members</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="3a53b-147">Windows ランタイムでは、スタティック メンバーとインスタンス メンバーの両方が定義されます。</span><span class="sxs-lookup"><span data-stu-id="3a53b-147">The Windows Runtime defines both static members and instance members.</span></span>  <span data-ttu-id="3a53b-148">JavaScript では、Windows ランタイム クラスまたはインターフェイスに関連付けられているオブジェクトにスタティック メンバーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="3a53b-148">In JavaScript, static members are added to the object that is associated with the Windows Runtime class or interface.</span></span>  
      
      ```javascript
      // Static method.
      var accel = Windows.Devices.Sensors.Accelerometer.getDefault();
      // Instance method.
      var reading = accel.getCurrentReading();
      ```  
   :::column-end:::
:::row-end:::  
    
<span data-ttu-id="3a53b-149">Windows ランタイムの基本種類の JavaScript 表現の詳細については [、Windows ランタイムの種類の JavaScript 表現を参照してください][WindowsRuntimeJavascriptTypes]。</span><span class="sxs-lookup"><span data-stu-id="3a53b-149">For more information about the JavaScript representation of Windows Runtime basic types, see [JavaScript Representation of Windows Runtime Types][WindowsRuntimeJavascriptTypes].</span></span>  

<!-- links -->  
 
[WindowsRuntimeJavascriptTypes]: ./javascript-representation-of-windows-runtime-types.md "Windows ランタイムの種類の JavaScript 表記 |Microsoft ドキュメント"

[WindowsUwpComponentsCreatingCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "C++/CX を使用した Windows ランタイム コンポーネント |Microsoft ドキュメント"  
[WindowsUwpComponentsCreatingCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "C# およびデバイスを使用した Windows ランタイム コンポーVisual BasicンVisual Basic |Microsoft ドキュメント"  

[MDNInt32array]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Int32Array "Int32Array |MDN"  