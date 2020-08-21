---
title: JavaScript での Windows ランタイムの使用
ms.custom: ''
ms.date: 07/29/2020
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
ms.openlocfilehash: 444008598a2f7a2f5257544304bed87fbfaa203a
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942170"
---
# <span data-ttu-id="a32b4-102">JavaScript での Windows ランタイムの使用</span><span class="sxs-lookup"><span data-stu-id="a32b4-102">Using the Windows Runtime in JavaScript</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="a32b4-103">ユニバーサル Windows プラットフォーム \(UWP\) アプリを作成する場合、ネイティブ JavaScript オブジェクト、メソッド、プロパティを使用する場合と同様に、Windows ランタイム クラス、メソッド、プロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a32b4-103">When you write a Universal Windows Platform \(UWP\) app, you can use Windows Runtime classes, methods, and properties in much the same way that you would use native JavaScript objects, methods, and properties.</span></span>  <span data-ttu-id="a32b4-104">このトピックでは、Windows ランタイム API を使用する方法、Windows ランタイム API の使用方法、非同期の Windows ランタイムメソッドの使用方法、Windows ランタイム イベントをリッスンおよび操作する方法など、Windows ランタイム API を使用する基本的な概念について説明するトピックとトピックへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="a32b4-104">This topic provides introductory information and links to topics that explain the basic concepts of using Windows Runtime APIs in JavaScript, including an explanation of how Windows Runtime types are represented, how to use asynchronous Windows Runtime methods, and how to listen to and handle Windows Runtime events.</span></span>  

<span data-ttu-id="a32b4-105">一般的な言語ドキュメントについては、MDN の [JavaScript][MDNJavascriptReference] リファレンス ライブラリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a32b4-105">For general language documentation, check out MDN's [JavaScript reference][MDNJavascriptReference] library.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="a32b4-106">Internet Explorer で実行されているアプリでは、Windows ランタイム機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="a32b4-106">Windows Runtime features are not available for apps that run in Internet Explorer.</span></span>  

## <span data-ttu-id="a32b4-107">Windows ランタイム リファレンス ドキュメント</span><span class="sxs-lookup"><span data-stu-id="a32b4-107">Windows Runtime reference documentation</span></span>  

<span data-ttu-id="a32b4-108">参照ドキュメントについては [、Windows ランタイム リファレンスを参照してください][UwpApiIndex]。</span><span class="sxs-lookup"><span data-stu-id="a32b4-108">For reference documentation, see [Windows Runtime Reference][UwpApiIndex].</span></span>  <span data-ttu-id="a32b4-109">コード例は、JavaScript でも C++、C#、およびVisual Basic。</span><span class="sxs-lookup"><span data-stu-id="a32b4-109">Code examples are available in JavaScript and also in C++, C#, and Visual Basic.</span></span>  

## <span data-ttu-id="a32b4-110">C++、C#、またはステートで Windows ランタイム コンポーポーンを書き Visual Basic込む</span><span class="sxs-lookup"><span data-stu-id="a32b4-110">Writing Windows Runtime components in C++, C#, or Visual Basic</span></span>  

<span data-ttu-id="a32b4-111">JavaScript で使用できる Windows ランタイム コンポーンを記述するための手順とガイドラインについては、C++ コンポーントの [作成、C#][WindowsUwpWinrtCpp] および Visual Basic で [Windows ランタイム コンポーントを作成する方法を参照してください][WindowsUwpWinrtCsharpVb]。</span><span class="sxs-lookup"><span data-stu-id="a32b4-111">For instructions and guidelines for writing Windows Runtime components that can be consumed in JavaScript, see [Creating Windows Runtime Components in C++][WindowsUwpWinrtCpp] and [Creating Windows Runtime Components in C# and Visual Basic][WindowsUwpWinrtCsharpVb].</span></span>  

## <span data-ttu-id="a32b4-112">Windows ランタイム機能を使用した基本的な操作</span><span class="sxs-lookup"><span data-stu-id="a32b4-112">Casing conventions with Windows Runtime features</span></span>  

<span data-ttu-id="a32b4-113">JavaScript の Windows ランタイム機能の基本的な操作は、他の言語と少し異なります。</span><span class="sxs-lookup"><span data-stu-id="a32b4-113">Casing conventions for Windows Runtime features in JavaScript differ slightly from those for other languages:</span></span>  

*   <span data-ttu-id="a32b4-114">名前空間とクラスは、Pascal case の場合:</span><span class="sxs-lookup"><span data-stu-id="a32b4-114">Namespaces and classes are in Pascal case:</span></span>  
    
    ```javascript
    Windows.Deployment.PackageInfo;
    ```  
    
*   <span data-ttu-id="a32b4-115">メソッドやプロパティ、構造と列挙のメンバーなど、クラスのメンバーにはカメラケムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a32b4-115">Members of classes, including methods and properties, and members of structures and enumerations, are in camel case:</span></span>  
    
    ```javascript
    Deployment.PackageInfo.createPackage();
    ```  
    
*   <span data-ttu-id="a32b4-116">イベント名は小文字で表示されます。</span><span class="sxs-lookup"><span data-stu-id="a32b4-116">Event names are in lower case:</span></span>  
    
    ```javascript
    dataTransferManager.ontargetapplicationchosen;
    ```  

## <span data-ttu-id="a32b4-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a32b4-117">See also</span></span>  

[<span data-ttu-id="a32b4-118">Windows ランタイム API を使用する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="a32b4-118">Considerations when Using the Windows Runtime API</span></span>][WindowsRuntimeConsiderationsApi]  
[<span data-ttu-id="a32b4-119">Windows ランタイム非同期メソッドの使用</span><span class="sxs-lookup"><span data-stu-id="a32b4-119">Using Windows Runtime Asynchronous Methods</span></span>][WindowsRuntimeAsynchronousMethods]   
[<span data-ttu-id="a32b4-120">JavaScript での Windows ランタイム イベントの処理</span><span class="sxs-lookup"><span data-stu-id="a32b4-120">Handling Windows Runtime Events in JavaScript</span></span>][WindowsRuntimeEventsJavascript]   
[<span data-ttu-id="a32b4-121">Windows ランタイム型の JavaScript 表現</span><span class="sxs-lookup"><span data-stu-id="a32b4-121">JavaScript Representation of Windows Runtime Types</span></span>][WindowsRuntimeJavascriptTypes]   
[<span data-ttu-id="a32b4-122">JavaScript プロジェクト (Windows ランタイム日付Time と TimeSpan の JavaScript プロジェクション)</span><span class="sxs-lookup"><span data-stu-id="a32b4-122">JavaScript Projection of Windows Runtime DateTime and TimeSpan</span></span>][WindowsRuntimeDatetimeTimespan]  

<!-- links  -->  

[WindowsRuntimeConsiderationsApi]: ./considerations-when-using-the-windows-runtime-api.md "Windows ランタイム API を使用する場合の考慮事例 |Microsoft ドキュメント"  
[WindowsRuntimeEventsJavascript]: ./handling-windows-runtime-events-in-javascript.md "JavaScript での Windows ランタイム イベントの使用 |Microsoft ドキュメント"  
[WindowsRuntimeJavascriptTypes]: ./javascript-representation-of-windows-runtime-types.md "Windows ランタイムの種類の JavaScript 表記 |Microsoft ドキュメント"  
[WindowsRuntimeAsynchronousMethods]: ./using-windows-runtime-asynchronous-methods.md "Windows ランタイム非同期の方法を使用する |Microsoft ドキュメント"  
[WindowsRuntimeDatetimeTimespan]: ./windows-runtime-datetime-and-timespan-representations.md "Windows ランタイムの DateTime と TimeSpan Representations |Microsoft ドキュメント"  

[UwpApiIndex]: /uwp/api/index "Windows UWP 名前空間 |Microsoft ドキュメント"  
[WindowsUwpWinrtCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "C++/CX を使用した Windows ランタイム コンポーネント |Microsoft ドキュメント"  
[WindowsUwpWinrtCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "C# およびデバイスを使用した Windows ランタイム コンポーVisual BasicンVisual Basic |Microsoft ドキュメント"  

[MDNJavascriptReference]: https://developer.mozilla.org/docs/Web/JavaScript/Reference "JavaScript リファレンス |MDN"  
