---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2Deferral
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2Deferral。
ms.openlocfilehash: dcefefd37167b6ff78f2d994f84af6c707423bb4
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012290"
---
# <span data-ttu-id="69a87-104">WebView2 クラス (CoreWebView2Deferral クラス)</span><span class="sxs-lookup"><span data-stu-id="69a87-104">Microsoft.Web.WebView2.Core.CoreWebView2Deferral class</span></span> 

<span data-ttu-id="69a87-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="69a87-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="69a87-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="69a87-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="69a87-107">このクラスは、GetDeferral メソッドによる保留の取得をサポートするイベント引数で保留を完了するために使われます。</span><span class="sxs-lookup"><span data-stu-id="69a87-107">This class is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="69a87-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="69a87-108">Summary</span></span>

 <span data-ttu-id="69a87-109">Members</span><span class="sxs-lookup"><span data-stu-id="69a87-109">Members</span></span>                        | <span data-ttu-id="69a87-110">説明</span><span class="sxs-lookup"><span data-stu-id="69a87-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="69a87-111">Complete</span><span class="sxs-lookup"><span data-stu-id="69a87-111">Complete</span></span>](#complete) | <span data-ttu-id="69a87-112">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="69a87-112">Completes the associated deferred event.</span></span>

## <span data-ttu-id="69a87-113">Members</span><span class="sxs-lookup"><span data-stu-id="69a87-113">Members</span></span>

#### <span data-ttu-id="69a87-114">Complete</span><span class="sxs-lookup"><span data-stu-id="69a87-114">Complete</span></span> 

<span data-ttu-id="69a87-115">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="69a87-115">Completes the associated deferred event.</span></span>

> <span data-ttu-id="69a87-116">パブリックの void [完了](#complete)()</span><span class="sxs-lookup"><span data-stu-id="69a87-116">public void [Complete](#complete)()</span></span>

<span data-ttu-id="69a87-117">完了は、各繰延が行われるたびに1回のみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="69a87-117">Complete should only be called once for each deferral taken.</span></span>

