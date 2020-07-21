---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2Deferral の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 135289994bdfe5481018c479b7a1d9c372ecb256
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885110"
---
# <span data-ttu-id="5a9f8-104">0.9.515 クラスの WebView2 クラス (CoreWebView2Deferral)</span><span class="sxs-lookup"><span data-stu-id="5a9f8-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2Deferral class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="5a9f8-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="5a9f8-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="5a9f8-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="5a9f8-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="5a9f8-107">このクラスは、GetDeferral メソッドによる保留の取得をサポートするイベント引数で保留を完了するために使われます。</span><span class="sxs-lookup"><span data-stu-id="5a9f8-107">This class is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="5a9f8-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="5a9f8-108">Summary</span></span>

 <span data-ttu-id="5a9f8-109">Members</span><span class="sxs-lookup"><span data-stu-id="5a9f8-109">Members</span></span>                        | <span data-ttu-id="5a9f8-110">説明</span><span class="sxs-lookup"><span data-stu-id="5a9f8-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5a9f8-111">Complete</span><span class="sxs-lookup"><span data-stu-id="5a9f8-111">Complete</span></span>](#complete) | <span data-ttu-id="5a9f8-112">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="5a9f8-112">Completes the associated deferred event.</span></span>

## <span data-ttu-id="5a9f8-113">Members</span><span class="sxs-lookup"><span data-stu-id="5a9f8-113">Members</span></span>

#### <span data-ttu-id="5a9f8-114">Complete</span><span class="sxs-lookup"><span data-stu-id="5a9f8-114">Complete</span></span> 

<span data-ttu-id="5a9f8-115">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="5a9f8-115">Completes the associated deferred event.</span></span>

> <span data-ttu-id="5a9f8-116">パブリックの void[完了](#complete)()</span><span class="sxs-lookup"><span data-stu-id="5a9f8-116">public void [Complete](#complete)()</span></span>

<span data-ttu-id="5a9f8-117">完了は、各繰延が行われるたびに1回のみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5a9f8-117">Complete should only be called once for each deferral taken.</span></span>

