---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2Deferral
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2Deferral。
ms.openlocfilehash: 77a3540a64c9894f10cb0c03998dafda90e4f15b
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878933"
---
# <span data-ttu-id="1ef4c-104">WebView2 クラス (CoreWebView2Deferral クラス)</span><span class="sxs-lookup"><span data-stu-id="1ef4c-104">Microsoft.Web.WebView2.Core.CoreWebView2Deferral class</span></span> 

<span data-ttu-id="1ef4c-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="1ef4c-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="1ef4c-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="1ef4c-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="1ef4c-107">このクラスは、GetDeferral メソッドによる保留の取得をサポートするイベント引数で保留を完了するために使われます。</span><span class="sxs-lookup"><span data-stu-id="1ef4c-107">This class is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="1ef4c-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="1ef4c-108">Summary</span></span>

 <span data-ttu-id="1ef4c-109">Members</span><span class="sxs-lookup"><span data-stu-id="1ef4c-109">Members</span></span>                        | <span data-ttu-id="1ef4c-110">説明</span><span class="sxs-lookup"><span data-stu-id="1ef4c-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="1ef4c-111">Complete</span><span class="sxs-lookup"><span data-stu-id="1ef4c-111">Complete</span></span>](#complete) | <span data-ttu-id="1ef4c-112">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="1ef4c-112">Completes the associated deferred event.</span></span>

## <span data-ttu-id="1ef4c-113">Members</span><span class="sxs-lookup"><span data-stu-id="1ef4c-113">Members</span></span>

#### <span data-ttu-id="1ef4c-114">Complete</span><span class="sxs-lookup"><span data-stu-id="1ef4c-114">Complete</span></span> 

<span data-ttu-id="1ef4c-115">関連付けられている遅延イベントを完了します。</span><span class="sxs-lookup"><span data-stu-id="1ef4c-115">Completes the associated deferred event.</span></span>

> <span data-ttu-id="1ef4c-116">パブリックの void[完了](#complete)()</span><span class="sxs-lookup"><span data-stu-id="1ef4c-116">public void [Complete](#complete)()</span></span>

<span data-ttu-id="1ef4c-117">完了は、各繰延が行われるたびに1回のみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1ef4c-117">Complete should only be called once for each deferral taken.</span></span>

