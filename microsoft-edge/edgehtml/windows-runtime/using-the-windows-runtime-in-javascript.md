---
description: JavaScript での Windows ランタイムの使用。
title: JavaScript での Windows ランタイムの使用
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime
ms.assetid: 90658546-f746-4e34-a7d1-71cf9ee322a2
caps.latest.revision: 16
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 10c90a225816cf32e01bc33648571c13a1aae090
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234642"
---
# <span data-ttu-id="c6404-103">JavaScript での Windows ランタイムの使用</span><span class="sxs-lookup"><span data-stu-id="c6404-103">Using the Windows Runtime in JavaScript</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="c6404-104">ユニバーサル Windows プラットフォーム \(UWP\) アプリを作成する場合は、ネイティブの JavaScript オブジェクト、メソッド、およびプロパティを使うのと同じ方法で、Windows ランタイムのクラス、メソッド、およびプロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="c6404-104">When you write a Universal Windows Platform \(UWP\) app, you can use Windows Runtime classes, methods, and properties in much the same way that you would use native JavaScript objects, methods, and properties.</span></span>  <span data-ttu-id="c6404-105">このトピックでは、入門情報と、Windows ランタイム型の表現方法、非同期の Windows ランタイム メソッドの使い方、Windows ランタイム イベントをリッスンして処理する方法など、JavaScript での Windows ランタイム API の使用に関する基本的な概念について説明するトピックへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="c6404-105">This topic provides introductory information and links to topics that explain the basic concepts of using Windows Runtime APIs in JavaScript, including an explanation of how Windows Runtime types are represented, how to use asynchronous Windows Runtime methods, and how to listen to and handle Windows Runtime events.</span></span>  

<span data-ttu-id="c6404-106">一般的な言語のドキュメントについては、MDN の JavaScript リファレンス [ライブラリをご覧][MDNJavascriptReference] ください。</span><span class="sxs-lookup"><span data-stu-id="c6404-106">For general language documentation, check out MDN's [JavaScript reference][MDNJavascriptReference] library.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="c6404-107">Windows ランタイム機能は、アプリで実行されるアプリInternet Explorer。</span><span class="sxs-lookup"><span data-stu-id="c6404-107">Windows Runtime features are not available for apps that run in Internet Explorer.</span></span>  

## <span data-ttu-id="c6404-108">Windows ランタイムのリファレンス ドキュメント</span><span class="sxs-lookup"><span data-stu-id="c6404-108">Windows Runtime reference documentation</span></span>  

<span data-ttu-id="c6404-109">リファレンス ドキュメントについては [、「Windows ランタイム リファレンス」を参照してください][UwpApiIndex]。</span><span class="sxs-lookup"><span data-stu-id="c6404-109">For reference documentation, see [Windows Runtime Reference][UwpApiIndex].</span></span>  <span data-ttu-id="c6404-110">コード例は、JavaScript および C++、C#、および Visual Basic。</span><span class="sxs-lookup"><span data-stu-id="c6404-110">Code examples are available in JavaScript and also in C++, C#, and Visual Basic.</span></span>  

## <span data-ttu-id="c6404-111">C++、C#、または Windows ランタイム コンポーネントのVisual Basic</span><span class="sxs-lookup"><span data-stu-id="c6404-111">Writing Windows Runtime components in C++, C#, or Visual Basic</span></span>  

<span data-ttu-id="c6404-112">JavaScript で使用できる Windows ランタイム コンポーネントを記述するための手順とガイドラインについては [、「C++][WindowsUwpWinrtCpp] での Windows ランタイム コンポーネントの作成」と [「C#][WindowsUwpWinrtCsharpVb]と Visual Basic での Windows ランタイム コンポーネントの作成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6404-112">For instructions and guidelines for writing Windows Runtime components that can be consumed in JavaScript, see [Creating Windows Runtime Components in C++][WindowsUwpWinrtCpp] and [Creating Windows Runtime Components in C# and Visual Basic][WindowsUwpWinrtCsharpVb].</span></span>  

## <span data-ttu-id="c6404-113">Windows ランタイム機能の大文字と小文字の規則</span><span class="sxs-lookup"><span data-stu-id="c6404-113">Casing conventions with Windows Runtime features</span></span>  

<span data-ttu-id="c6404-114">JavaScript の Windows ランタイム機能の大文字と小文字の表記規則は、他の言語の場合と若干異なります。</span><span class="sxs-lookup"><span data-stu-id="c6404-114">Casing conventions for Windows Runtime features in JavaScript differ slightly from those for other languages:</span></span>  

*   <span data-ttu-id="c6404-115">パスカル語の場合、名前空間とクラスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c6404-115">Namespaces and classes are in Pascal case:</span></span>  
    
    ```javascript
    Windows.Deployment.PackageInfo;
    ```  
    
*   <span data-ttu-id="c6404-116">クラスのメンバー (メソッドとプロパティを含む) と構造体と列挙体のメンバーは、次の場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c6404-116">Members of classes, including methods and properties, and members of structures and enumerations, are in camel case:</span></span>  
    
    ```javascript
    Deployment.PackageInfo.createPackage();
    ```  
    
*   <span data-ttu-id="c6404-117">イベント名の小文字は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c6404-117">Event names are in lower case:</span></span>  
    
    ```javascript
    dataTransferManager.ontargetapplicationchosen;
    ```  

## <span data-ttu-id="c6404-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6404-118">See also</span></span>  

[<span data-ttu-id="c6404-119">Windows ランタイム API を使用する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="c6404-119">Considerations when Using the Windows Runtime API</span></span>][WindowsRuntimeConsiderationsApi]  
[<span data-ttu-id="c6404-120">Windows ランタイム非同期メソッドの使用</span><span class="sxs-lookup"><span data-stu-id="c6404-120">Using Windows Runtime Asynchronous Methods</span></span>][WindowsRuntimeAsynchronousMethods]   
[<span data-ttu-id="c6404-121">JavaScript での Windows ランタイム イベントの処理</span><span class="sxs-lookup"><span data-stu-id="c6404-121">Handling Windows Runtime Events in JavaScript</span></span>][WindowsRuntimeEventsJavascript]   
[<span data-ttu-id="c6404-122">Windows ランタイム型の JavaScript 表現</span><span class="sxs-lookup"><span data-stu-id="c6404-122">JavaScript Representation of Windows Runtime Types</span></span>][WindowsRuntimeJavascriptTypes]   
[<span data-ttu-id="c6404-123">Windows ランタイムの DateTime と TimeSpan の JavaScript プロジェクション</span><span class="sxs-lookup"><span data-stu-id="c6404-123">JavaScript Projection of Windows Runtime DateTime and TimeSpan</span></span>][WindowsRuntimeDatetimeTimespan]  

<!-- links  -->  

[WindowsRuntimeConsiderationsApi]: ./considerations-when-using-the-windows-runtime-api.md "Windows ランタイム API を使用する場合の考慮事項 |Microsoft Docs"  
[WindowsRuntimeEventsJavascript]: ./handling-windows-runtime-events-in-javascript.md "JavaScript での Windows ランタイム イベントの処理 |Microsoft Docs"  
[WindowsRuntimeJavascriptTypes]: ./javascript-representation-of-windows-runtime-types.md "Windows ランタイム型の JavaScript 表現 |Microsoft Docs"  
[WindowsRuntimeAsynchronousMethods]: ./using-windows-runtime-asynchronous-methods.md "Windows ランタイム非同期メソッドの使用 |Microsoft Docs"  
[WindowsRuntimeDatetimeTimespan]: ./windows-runtime-datetime-and-timespan-representations.md "Windows ランタイムの DateTime と TimeSpan の表現 |Microsoft Docs"  

[UwpApiIndex]: /uwp/api/index "Windows UWP 名前空間 |Microsoft Docs"  
[WindowsUwpWinrtCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "C++/CX を使った Windows ランタイム コンポーネント |Microsoft Docs"  
[WindowsUwpWinrtCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "C# と Visual Basic を使った Windows ランタイム コンポーネント |Microsoft Docs"  

[MDNJavascriptReference]: https://developer.mozilla.org/docs/Web/JavaScript/Reference "JavaScript リファレンス |MDN"  
