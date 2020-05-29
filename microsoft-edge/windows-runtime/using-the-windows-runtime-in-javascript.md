---
title: JavaScript での Windows ランタイムの使用
ms.custom: ''
ms.date: 04/01/2020
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.technology: windows-integration
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime
ms.assetid: 90658546-f746-4e34-a7d1-71cf9ee322a2
caps.latest.revision: 16
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: bffde93aa973f492189aedcfcaa9c3694d9e61bc
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570779"
---
# <span data-ttu-id="ff6ad-102">JavaScript での Windows ランタイムの使用</span><span class="sxs-lookup"><span data-stu-id="ff6ad-102">Using the Windows Runtime in JavaScript</span></span>  

<span data-ttu-id="ff6ad-103">ユニバーサル Windows プラットフォーム \ (UWP) アプリを作成するときに、ネイティブ JavaScript オブジェクト、メソッド、プロパティを使うのと同じように Windows ランタイムクラス、メソッド、プロパティを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="ff6ad-103">When you write a Universal Windows Platform \(UWP\) app, you can use Windows Runtime classes, methods, and properties in much the same way that you would use native JavaScript objects, methods, and properties.</span></span>  <span data-ttu-id="ff6ad-104">このトピックでは、JavaScript での Windows ランタイム Api の基本的な概念について説明しているトピックへのリンクを提供します。これには、Windows ランタイム型の表現方法、非同期 Windows ランタイムメソッドの使い方、Windows ランタイムイベントをリッスンして処理する方法などがあります。</span><span class="sxs-lookup"><span data-stu-id="ff6ad-104">This topic provides introductory information and links to topics that explain the basic concepts of using Windows Runtime APIs in JavaScript, including an explanation of how Windows Runtime types are represented, how to use asynchronous Windows Runtime methods, and how to listen to and handle Windows Runtime events.</span></span>  

<span data-ttu-id="ff6ad-105">一般的な言語のドキュメントについては、「MDN の[JavaScript リファレンス][MDNJavascriptReference]ライブラリ」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ff6ad-105">For general language documentation, check out MDN's [JavaScript reference][MDNJavascriptReference] library.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="ff6ad-106">Windows ランタイム機能は、Internet Explorer で実行されるアプリでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="ff6ad-106">Windows Runtime features are not available for apps that run in Internet Explorer.</span></span>  

## <span data-ttu-id="ff6ad-107">Windows ランタイムリファレンスドキュメント</span><span class="sxs-lookup"><span data-stu-id="ff6ad-107">Windows Runtime Reference Documentation</span></span>  

<span data-ttu-id="ff6ad-108">参考資料については、「 [Windows ランタイムリファレンス][UwpApiIndex]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ff6ad-108">For reference documentation, see [Windows Runtime Reference][UwpApiIndex].</span></span>  <span data-ttu-id="ff6ad-109">コード例は JavaScript でも、C++、C#、Visual Basic でも利用できます。</span><span class="sxs-lookup"><span data-stu-id="ff6ad-109">Code examples are available in JavaScript and also in C++, C#, and Visual Basic.</span></span>  

## <span data-ttu-id="ff6ad-110">C++、C#、または Visual Basic での Windows ランタイムコンポーネントの作成</span><span class="sxs-lookup"><span data-stu-id="ff6ad-110">Writing Windows Runtime Components in C++, C#, or Visual Basic</span></span>  

<span data-ttu-id="ff6ad-111">JavaScript で利用できる Windows ランタイムコンポーネントを作成するための手順とガイドラインについては、「 [C++ での Windows ランタイムコンポーネントの作成][WindowsUwpWinrtCpp]」および「 [C# と Visual Basic での][WindowsUwpWinrtCsharpVb]Windows ランタイムコンポーネントの作成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff6ad-111">For instructions and guidelines for writing Windows Runtime components that can be consumed in JavaScript, see [Creating Windows Runtime Components in C++][WindowsUwpWinrtCpp] and [Creating Windows Runtime Components in C# and Visual Basic][WindowsUwpWinrtCsharpVb].</span></span>  

## <span data-ttu-id="ff6ad-112">Windows ランタイム機能を使用した大文字と小文字の規則</span><span class="sxs-lookup"><span data-stu-id="ff6ad-112">Casing Conventions with Windows Runtime Features</span></span>  

<span data-ttu-id="ff6ad-113">JavaScript での Windows ランタイム機能の大文字と小文字の規則は、他の言語とは若干異なります。</span><span class="sxs-lookup"><span data-stu-id="ff6ad-113">Casing conventions for Windows Runtime features in JavaScript differ slightly from those for other languages:</span></span>  

*   <span data-ttu-id="ff6ad-114">名前空間とクラスは Pascal の場合にあります。</span><span class="sxs-lookup"><span data-stu-id="ff6ad-114">Namespaces and classes are in Pascal case:</span></span>  
    
    ```javascript
    Windows.Deployment.PackageInfo;
    ```  
    
*   <span data-ttu-id="ff6ad-115">メソッドやプロパティ、構造体と列挙体のメンバーなどのクラスのメンバーは、camel 形式で実行されます。</span><span class="sxs-lookup"><span data-stu-id="ff6ad-115">Members of classes, including methods and properties, and members of structures and enumerations, are in camel case:</span></span>  
    
    ```javascript
    Deployment.PackageInfo.createPackage();
    ```  
    
*   <span data-ttu-id="ff6ad-116">イベント名は小文字で示します。</span><span class="sxs-lookup"><span data-stu-id="ff6ad-116">Event names are in lower case:</span></span>  
    
    ```javascript
    dataTransferManager.ontargetapplicationchosen;
    ```  

## <span data-ttu-id="ff6ad-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff6ad-117">See Also</span></span>  

[<span data-ttu-id="ff6ad-118">Windows ランタイム API を使用する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="ff6ad-118">Considerations when Using the Windows Runtime API</span></span>][WindowsRuntimeConsiderationsApi]  
[<span data-ttu-id="ff6ad-119">Windows ランタイム非同期メソッドの使用</span><span class="sxs-lookup"><span data-stu-id="ff6ad-119">Using Windows Runtime Asynchronous Methods</span></span>][WindowsRuntimeAsynchronousMethods]   
[<span data-ttu-id="ff6ad-120">JavaScript での Windows ランタイムイベントの処理</span><span class="sxs-lookup"><span data-stu-id="ff6ad-120">Handling Windows Runtime Events in JavaScript</span></span>][WindowsRuntimeEventsJavascript]   
[<span data-ttu-id="ff6ad-121">Windows ランタイム型の JavaScript 表現</span><span class="sxs-lookup"><span data-stu-id="ff6ad-121">JavaScript Representation of Windows Runtime Types</span></span>][WindowsRuntimeJavascriptTypes]   
[<span data-ttu-id="ff6ad-122">Windows ランタイムの DateTime と TimeSpan の JavaScript のプロジェクション</span><span class="sxs-lookup"><span data-stu-id="ff6ad-122">JavaScript Projection of Windows Runtime DateTime and TimeSpan</span></span>][WindowsRuntimeDatetimeTimespan]  
 
<!-- image links -->  

<!-- links  -->  

[WindowsRuntimeConsiderationsApi]: /microsoft-edge/windows-runtime/considerations-when-using-the-windows-runtime-api "Windows ランタイム API を使用する際の考慮事項"  
[WindowsRuntimeEventsJavascript]: /microsoft-edge/windows-runtime/handling-windows-runtime-events-in-javascript "JavaScript での Windows ランタイムイベントの処理"  
[WindowsRuntimeJavascriptTypes]: /microsoft-edge/windows-runtime/javascript-representation-of-windows-runtime-types "Windows ランタイム型の JavaScript 表現"  
[WindowsRuntimeAsynchronousMethods]: /microsoft-edge/windows-runtime/using-windows-runtime-asynchronous-methods "Windows ランタイム非同期メソッドの使用"  
[WindowsRuntimeDatetimeTimespan]: /microsoft-edge/windows-runtime/windows-runtime-datetime-and-timespan-representations "Windows ランタイムの DateTime と TimeSpan の表現"  

[UwpApiIndex]: /uwp/api/index "Windows UWP の名前空間"  
[WindowsUwpWinrtCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "C++/CX を備えた Windows ランタイムコンポーネント"  
[WindowsUwpWinrtCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "C# と Visual Basic を使った Windows ランタイムコンポーネント"  

[MDNJavascriptReference]: https://developer.mozilla.org/docs/Web/JavaScript/Reference "JavaScript リファレンス |MDN"  
