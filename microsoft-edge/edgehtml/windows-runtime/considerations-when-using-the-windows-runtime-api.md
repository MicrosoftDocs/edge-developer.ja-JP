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
# <span data-ttu-id="6c7b0-103">Windows ランタイム API を使用する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="6c7b0-103">Considerations when using the Windows Runtime API</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="6c7b0-104">JavaScript では、Windows ランタイム API のほぼすべての要素を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-104">You can use nearly every element of the Windows Runtime API in JavaScript.</span></span>  <span data-ttu-id="6c7b0-105">ただし、Windows ランタイム要素の JavaScript 表現には、念頭に置く必要があるいくつかの側面があります。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-105">However, there are some aspects of the JavaScript representation of Windows Runtime elements that you should keep in mind.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="6c7b0-106">C++、C#、または Visual Basic で Windows ランタイム コンポーネントを作成し、JavaScript で使用する方法については [、「C++][WindowsUwpComponentsCreatingCpp] での Windows ランタイム コンポーネントの作成」および [「C#][WindowsUwpComponentsCreatingCsharpVb]と Visual Basic での Windows ランタイム コンポーネントの作成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-106">For information about creating Windows Runtime components in C++, C#, or Visual Basic and consuming them in JavaScript, see [Creating Windows Runtime Components in C++][WindowsUwpComponentsCreatingCpp] and [Creating Windows Runtime Components in C# and Visual Basic][WindowsUwpComponentsCreatingCsharpVb].</span></span>  

## <span data-ttu-id="6c7b0-107">Windows ランタイム型の JavaScript 表現の特殊なケース</span><span class="sxs-lookup"><span data-stu-id="6c7b0-107">Special cases in the JavaScript Representation of Windows Runtime types</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="6c7b0-108">文字列</span><span class="sxs-lookup"><span data-stu-id="6c7b0-108">Strings</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="6c7b0-109">初期化されていない文字列は Windows ランタイム メソッドに文字列 "undefined" として渡され、設定された文字列は `null` 文字列 "null" として渡されます。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-109">An uninitialized string is passed to a Windows Runtime method as the string "undefined", and a string set to `null` is passed as the string "null".</span></span>  <span data-ttu-id="6c7b0-110">\(this is truewhenever a `null` or `undefined` value is coerced to a string.\) Before you pass a string to a Windows Runtime method, you should initialize it as the empty string \(""\).</span><span class="sxs-lookup"><span data-stu-id="6c7b0-110">\(This is true whenever a `null` or `undefined` value is coerced to a string.\)  Before you pass a string to a Windows Runtime method, you should initialize it as the empty string \(""\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="6c7b0-111">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6c7b0-111">Interfaces</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="6c7b0-112">JavaScript で Windows ランタイム インターフェイスを実装することはできません。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-112">You cannot implement a Windows Runtime interface in JavaScript.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="6c7b0-113">配列</span><span class="sxs-lookup"><span data-stu-id="6c7b0-113">Arrays</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="6c7b0-114">Windows ランタイム配列はサイズ変更できないので、JavaScript で配列をサイズ変更するメソッドは Windows ランタイム配列では動作しません。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-114">Windows Runtime arrays are not resizable, so methods that resize arrays in JavaScript do not work on Windows Runtime arrays.</span></span>  
      *   <span data-ttu-id="6c7b0-115">配列: JavaScript 配列値を Windows ランタイム メソッドに渡した場合、配列がコピーされます。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-115">Arrays: If you pass a JavaScript array value to a Windows Runtime method, the array is copied.</span></span>  <span data-ttu-id="6c7b0-116">Windows ランタイム メソッドは、配列またはメンバーを変更して JavaScript アプリに返したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-116">The Windows Runtime method is not able to modify the array or its members and return it to your JavaScript app.</span></span>  <span data-ttu-id="6c7b0-117">ただし、コピーされない型指定された配列 [\(Int32Array Object][MDNInt32array]\など) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-117">However, you can use typed arrays \(for example, [Int32Array Object][MDNInt32array]\), which are not copied.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="6c7b0-118">構造体</span><span class="sxs-lookup"><span data-stu-id="6c7b0-118">Structures</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="6c7b0-119">Windows ランタイム構造体は JavaScript のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-119">Windows Runtime structures are objects in JavaScript.</span></span>  <span data-ttu-id="6c7b0-120">Windows ランタイム構造体を Windows ランタイム メソッドに渡す場合は、キーワードを使って構造体をインスタンス化 `new` しない。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-120">If you want to pass a Windows Runtime structure to a Windows Runtime method, don't instantiate the structure with the `new` keyword.</span></span>  <span data-ttu-id="6c7b0-121">代わりに、オブジェクトを作成し、関連するメンバーとその値を追加します。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-121">Instead, create an object and add the relevant members and their values.</span></span>  <span data-ttu-id="6c7b0-122">メンバーの名前は、次の場合に、camel にしてください `SomeStruct.firstMember` 。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-122">The names of the members should be in camel case: `SomeStruct.firstMember`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="6c7b0-123">オブジェクト</span><span class="sxs-lookup"><span data-stu-id="6c7b0-123">Objects</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="6c7b0-124">JavaScript オブジェクトはマネージ コード オブジェクト \( \) と同じ `System.Object` ではありません。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-124">JavaScript objects aren't the same as managed code objects \(`System.Object`\).</span></span>  <span data-ttu-id="6c7b0-125">JavaScript オブジェクトは、必要な Windows ランタイム メソッドに渡す必要があります `System.Object` 。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-125">You can't pass a JavaScript object to a Windows Runtime method that requires a `System.Object`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="6c7b0-126">オブジェクト ID</span><span class="sxs-lookup"><span data-stu-id="6c7b0-126">Object identity</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="6c7b0-127">ほとんどの場合、Windows ランタイムと JavaScript の間で渡されるオブジェクトは変更されません。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-127">In most cases, the objects passed back and forth between the Windows Runtime and JavaScript do not change.</span></span>  <span data-ttu-id="6c7b0-128">JavaScript エンジンは、既知のオブジェクトのマップを保持します。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-128">The JavaScript engine maintains a map of known objects.</span></span>  <span data-ttu-id="6c7b0-129">オブジェクトが Windows ランタイムから返されると、マップと一致し、存在しない場合は新しいオブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-129">When an object is returned from the Windows Runtime it is matched against the map, and if it does not exist a new object is created.</span></span>  <span data-ttu-id="6c7b0-130">Windows ランタイム メソッドによって返されるインターフェイスを表すオブジェクトの場合も、同じ手順が実行されます。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-130">The same procedure is followed for objects that represent interfaces that are returned by Windows Runtime methods.</span></span>  <span data-ttu-id="6c7b0-131">次の 2 種類の例外があります。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-131">There are two kinds of exceptions:</span></span>  
      
      *   <span data-ttu-id="6c7b0-132">Windows ランタイムの呼び出しから返され、新しい \(expando\) プロパティが追加されたオブジェクトは、Windows ランタイムに戻される際に新しいプロパティを保持しません。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-132">Objects that are returned from a Windows Runtime call, and then have new \(expando\) properties added, don't retain their new properties when they are passed back to the Windows Runtime.</span></span>  <span data-ttu-id="6c7b0-133">ただし、JavaScript アプリに返される場合は、既存のオブジェクトに一致するオブジェクトなので、返されるオブジェクトには expando プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-133">However, when they are returned to the JavaScript app, because they're matched to the existing object, the returned object does have the expando properties.</span></span>  
      *   <span data-ttu-id="6c7b0-134">Windows ランタイムの構造体とデリゲートは、以前に使用した構造体やデリゲートと同じとして識別することはできません。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-134">Structures and delegates in Windows Runtime can't be identified as identical to previously-used structures or delegates.</span></span>  <span data-ttu-id="6c7b0-135">構造体またはデリゲートが返されるたび、新しい参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-135">Every time a structure or delegate is returned, it gets a new reference.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="6c7b0-136">名前の競合</span><span class="sxs-lookup"><span data-stu-id="6c7b0-136">Name collisions</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="6c7b0-137">複数の Windows ランタイム インターフェイスは、同じ名前のメンバーを持つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-137">Multiple Windows Runtime interfaces may have members with the same names.</span></span>  <span data-ttu-id="6c7b0-138">1 つの JavaScript オブジェクト (ランタイム クラスまたはインターフェイスを表す場合があります) に組み合わせると、メンバーは完全修飾名で表されます。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-138">If they are combined in a single JavaScript object (which can be a representation of a runtime class or an interface), the members are represented with fully-qualified names.</span></span>  <span data-ttu-id="6c7b0-139">これらのメンバーは、次の構文を使用して呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-139">You can call these members by using the following syntax:</span></span>  
      
      ```cpp
      Class["MemberName"](parameter)
      ```  
      
      <span data-ttu-id="6c7b0-140">次のコードでは、2 つのインターフェイスに Draw メソッドが含まれます。ランタイム クラスは両方のインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-140">In the following code, two interfaces have a Draw method, and a runtime class implements both interfaces.</span></span>  
      
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
      
      <span data-ttu-id="6c7b0-141">JavaScript で上記のコードを呼び出す方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-141">Here is how you can call the above code in JavaScript.</span></span>  
      
      ```javascript
      var example = new ExampleObject();
      example["CollisionExample.InterfaceA.draw"](12);
      example["CollisionExample.InterfaceB.draw"]("hello");
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `Out` <span data-ttu-id="6c7b0-142">parameters</span><span class="sxs-lookup"><span data-stu-id="6c7b0-142">parameters</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="6c7b0-143">Windows ランタイム メソッドに複数のパラメーターがある場合、JavaScript では、メソッドは戻り値として JavaScript オブジェクトを持ち、オブジェクトにはパラメーターに対応する `out` プロパティ `out` があります。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-143">If a Windows Runtime method has multiple `out` parameters, in JavaScript the method has a JavaScript object as its return value, and the object has properties that correspond to the `out` parameter.</span></span>  <span data-ttu-id="6c7b0-144">たとえば、C++ で次の Windows ランタイム署名を考え出します。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-144">For example, consider the following Windows Runtime signature in C++.</span></span>  
      
      ```cpp
      void ExampleMethod(
          [OutAttribute] char^ first,
          [OutAttribute] char^ second
      )
      ```  
      
      <span data-ttu-id="6c7b0-145">この署名の JavaScript バージョンは次の形式です。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-145">The JavaScript version of this signature is:</span></span>  
      
      ```javascript
      var returnValue = exampleMethod();
      ```  
      
      <span data-ttu-id="6c7b0-146">この例では、 `returnValue` 次の 2 つのフィールドを持つ JavaScript `first` オブジェクトです `second` 。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-146">In this example, `returnValue` is a JavaScript object that has two fields: `first` and `second`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="6c7b0-147">静的メンバー</span><span class="sxs-lookup"><span data-stu-id="6c7b0-147">Static members</span></span>  
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="6c7b0-148">Windows ランタイムは、静的メンバーとインスタンス メンバーの両方を定義します。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-148">The Windows Runtime defines both static members and instance members.</span></span>  <span data-ttu-id="6c7b0-149">JavaScript では、静的メンバーが、Windows ランタイム クラスまたはインターフェイスに関連付けられているオブジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-149">In JavaScript, static members are added to the object that is associated with the Windows Runtime class or interface.</span></span>  
      
      ```javascript
      // Static method.
      var accel = Windows.Devices.Sensors.Accelerometer.getDefault();
      // Instance method.
      var reading = accel.getCurrentReading();
      ```  
   :::column-end:::
:::row-end:::  
    
<span data-ttu-id="6c7b0-150">Windows ランタイムの基本型の JavaScript 表現の詳細については [、「JavaScript Representation of Windows Runtime Types」を参照してください][WindowsRuntimeJavascriptTypes]。</span><span class="sxs-lookup"><span data-stu-id="6c7b0-150">For more information about the JavaScript representation of Windows Runtime basic types, see [JavaScript Representation of Windows Runtime Types][WindowsRuntimeJavascriptTypes].</span></span>  

<!-- links -->  
 
[WindowsRuntimeJavascriptTypes]: ./javascript-representation-of-windows-runtime-types.md "Windows ランタイム型の JavaScript 表現 |Microsoft Docs"

[WindowsUwpComponentsCreatingCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "C++/CX を使った Windows ランタイム コンポーネント |Microsoft Docs"  
[WindowsUwpComponentsCreatingCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "C# と Visual Basic を使った Windows ランタイム コンポーネント |Microsoft Docs"  

[MDNInt32array]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Int32Array "Int32Array |MDN"  
