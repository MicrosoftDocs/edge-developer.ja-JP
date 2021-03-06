---
description: JavaScript での Windows ランタイムの使用
title: JavaScript での Windows ランタイムの使用
ms.custom: ''
ms.date: 11/03/2020
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime
ms.assetid: 90658546-f746-4e34-a7d1-71cf9ee322a2
caps.latest.revision: 16
author: MSEdgeTeam
ms.author: msedgedevrel
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 4e137526ce147cdeb82749474bd43d1b3697361b
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399324"
---
# <a name="using-the-windows-runtime-in-javascript"></a><span data-ttu-id="1d020-103">JavaScript での Windows ランタイムの使用</span><span class="sxs-lookup"><span data-stu-id="1d020-103">Using the Windows Runtime in JavaScript</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="1d020-104">ユニバーサル Windows プラットフォーム \(UWP\) アプリを作成する場合は、ネイティブ JavaScript オブジェクト、メソッド、およびプロパティを使用するのと同じ方法で Windows ランタイム クラス、メソッド、およびプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d020-104">When you write a Universal Windows Platform \(UWP\) app, you can use Windows Runtime classes, methods, and properties in much the same way that you would use native JavaScript objects, methods, and properties.</span></span>  <span data-ttu-id="1d020-105">このトピックでは、Windows ランタイムの種類の表現方法、非同期 Windows ランタイム メソッドの使い方、Windows ランタイム イベントのリッスンおよび処理方法など、JavaScript で Windows ランタイム API を使用する基本的な概念を説明するトピックへの入門情報とリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="1d020-105">This topic provides introductory information and links to topics that explain the basic concepts of using Windows Runtime APIs in JavaScript, including an explanation of how Windows Runtime types are represented, how to use asynchronous Windows Runtime methods, and how to listen to and handle Windows Runtime events.</span></span>  

<span data-ttu-id="1d020-106">一般的な言語のドキュメントについては、MDN の [JavaScript リファレンス ライブラリを参照][MDNJavascriptReference] してください。</span><span class="sxs-lookup"><span data-stu-id="1d020-106">For general language documentation, check out MDN's [JavaScript reference][MDNJavascriptReference] library.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="1d020-107">Windows ランタイム機能は、アプリで実行されるアプリInternet Explorer。</span><span class="sxs-lookup"><span data-stu-id="1d020-107">Windows Runtime features are not available for apps that run in Internet Explorer.</span></span>  

## <a name="windows-runtime-reference-documentation"></a><span data-ttu-id="1d020-108">Windows ランタイムのリファレンス ドキュメント</span><span class="sxs-lookup"><span data-stu-id="1d020-108">Windows Runtime reference documentation</span></span>  

<span data-ttu-id="1d020-109">リファレンス ドキュメントについては [、「Windows ランタイム リファレンス」を参照してください][UwpApiIndex]。</span><span class="sxs-lookup"><span data-stu-id="1d020-109">For reference documentation, see [Windows Runtime Reference][UwpApiIndex].</span></span>  <span data-ttu-id="1d020-110">コード例は、JavaScript および C++、C#、およびVisual Basic。</span><span class="sxs-lookup"><span data-stu-id="1d020-110">Code examples are available in JavaScript and also in C++, C#, and Visual Basic.</span></span>  

## <a name="writing-windows-runtime-components-in-c-c-or-visual-basic"></a><span data-ttu-id="1d020-111">Windows ランタイム コンポーネントの C++、C#、またはVisual Basic</span><span class="sxs-lookup"><span data-stu-id="1d020-111">Writing Windows Runtime components in C++, C#, or Visual Basic</span></span>  

<span data-ttu-id="1d020-112">JavaScript で使用できる Windows ランタイム コンポーネントを記述する手順とガイドラインについては [、「C++][WindowsUwpWinrtCpp] での Windows ランタイム コンポーネントの作成」および「C# および Visual Basic での Windows ランタイム コンポーネントの作成」 [を参照してください][WindowsUwpWinrtCsharpVb]。</span><span class="sxs-lookup"><span data-stu-id="1d020-112">For instructions and guidelines for writing Windows Runtime components that can be consumed in JavaScript, see [Creating Windows Runtime Components in C++][WindowsUwpWinrtCpp] and [Creating Windows Runtime Components in C# and Visual Basic][WindowsUwpWinrtCsharpVb].</span></span>  

## <a name="casing-conventions-with-windows-runtime-features"></a><span data-ttu-id="1d020-113">Windows ランタイム機能を使用した大文字と小文字の規則</span><span class="sxs-lookup"><span data-stu-id="1d020-113">Casing conventions with Windows Runtime features</span></span>  

<span data-ttu-id="1d020-114">JavaScript の Windows ランタイム機能の大文字と小文字の表記規則は、他の言語とは若干異なります。</span><span class="sxs-lookup"><span data-stu-id="1d020-114">Casing conventions for Windows Runtime features in JavaScript differ slightly from those for other languages:</span></span>  

*   <span data-ttu-id="1d020-115">名前空間とクラスは Pascal の場合です。</span><span class="sxs-lookup"><span data-stu-id="1d020-115">Namespaces and classes are in Pascal case:</span></span>  
    
    ```javascript
    Windows.Deployment.PackageInfo;
    ```  
    
*   <span data-ttu-id="1d020-116">メソッドとプロパティを含むクラスのメンバー、および構造体と列挙体のメンバーは、camel の場合です。</span><span class="sxs-lookup"><span data-stu-id="1d020-116">Members of classes, including methods and properties, and members of structures and enumerations, are in camel case:</span></span>  
    
    ```javascript
    Deployment.PackageInfo.createPackage();
    ```  
    
*   <span data-ttu-id="1d020-117">イベント名は小文字です。</span><span class="sxs-lookup"><span data-stu-id="1d020-117">Event names are in lower case:</span></span>  
    
    ```javascript
    dataTransferManager.ontargetapplicationchosen;
    ```  
    
## <a name="see-also"></a><span data-ttu-id="1d020-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d020-118">See also</span></span>  

[<span data-ttu-id="1d020-119">Windows ランタイム API を使用する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="1d020-119">Considerations when Using the Windows Runtime API</span></span>][WindowsRuntimeConsiderationsApi]  
[<span data-ttu-id="1d020-120">Windows ランタイム非同期メソッドの使用</span><span class="sxs-lookup"><span data-stu-id="1d020-120">Using Windows Runtime Asynchronous Methods</span></span>][WindowsRuntimeAsynchronousMethods]   
[<span data-ttu-id="1d020-121">JavaScript での Windows ランタイム イベントの処理</span><span class="sxs-lookup"><span data-stu-id="1d020-121">Handling Windows Runtime Events in JavaScript</span></span>][WindowsRuntimeEventsJavascript]   
[<span data-ttu-id="1d020-122">Windows ランタイム型の JavaScript 表現</span><span class="sxs-lookup"><span data-stu-id="1d020-122">JavaScript Representation of Windows Runtime Types</span></span>][WindowsRuntimeJavascriptTypes]   
[<span data-ttu-id="1d020-123">Windows ランタイムの DateTime と TimeSpan の JavaScript プロジェクション</span><span class="sxs-lookup"><span data-stu-id="1d020-123">JavaScript Projection of Windows Runtime DateTime and TimeSpan</span></span>][WindowsRuntimeDatetimeTimespan]  

<!-- links -->  

[WindowsRuntimeConsiderationsApi]: ./considerations-when-using-the-windows-runtime-api.md "Windows ランタイム API を使用する場合の考慮事項|Microsoft Docs"  
[WindowsRuntimeEventsJavascript]: ./handling-windows-runtime-events-in-javascript.md "JavaScript の Windows ランタイム イベントの処理|Microsoft Docs"  
[WindowsRuntimeJavascriptTypes]: ./javascript-representation-of-windows-runtime-types.md "Windows ランタイム型の JavaScript 表現 |Microsoft Docs"  
[WindowsRuntimeAsynchronousMethods]: ./using-windows-runtime-asynchronous-methods.md "Windows ランタイム非同期メソッドの使用|Microsoft Docs"  
[WindowsRuntimeDatetimeTimespan]: ./windows-runtime-datetime-and-timespan-representations.md "Windows ランタイム DateTime および TimeSpan リプレゼンテーション |Microsoft Docs"  

[UwpApiIndex]: /uwp/api/index "Windows UWP 名前空間 |Microsoft Docs"  
[WindowsUwpWinrtCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "C++/CX の Windows ランタイム |Microsoft Docs"  
[WindowsUwpWinrtCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "Windows ランタイム コンポーネントとC#およびVisual Basic |Microsoft Docs"  

[MDNJavascriptReference]: https://developer.mozilla.org/docs/Web/JavaScript/Reference "JavaScript リファレンス |MDN"  
