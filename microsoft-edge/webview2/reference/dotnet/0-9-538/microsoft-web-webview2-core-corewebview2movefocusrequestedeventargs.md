---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2MoveFocusRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2MoveFocusRequestedEventArgs。
ms.openlocfilehash: dd141e135275d815458ce66a93dfc9ef3e7b33a8
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878863"
---
# <span data-ttu-id="54442-104">WebView2 クラス (CoreWebView2MoveFocusRequestedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="54442-104">Microsoft.Web.WebView2.Core.CoreWebView2MoveFocusRequestedEventArgs class</span></span> 

<span data-ttu-id="54442-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="54442-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="54442-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="54442-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="54442-107">MoveFocusRequested されたイベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="54442-107">Event args for the MoveFocusRequested event.</span></span>

## <span data-ttu-id="54442-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="54442-108">Summary</span></span>

 <span data-ttu-id="54442-109">Members</span><span class="sxs-lookup"><span data-stu-id="54442-109">Members</span></span>                        | <span data-ttu-id="54442-110">説明</span><span class="sxs-lookup"><span data-stu-id="54442-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="54442-111">Handled</span><span class="sxs-lookup"><span data-stu-id="54442-111">Handled</span></span>](#handled) | <span data-ttu-id="54442-112">イベントがアプリによって処理されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="54442-112">Indicate whether the event has been handled by the app.</span></span>
[<span data-ttu-id="54442-113">理由</span><span class="sxs-lookup"><span data-stu-id="54442-113">Reason</span></span>](#reason) | <span data-ttu-id="54442-114">MoveFocus 要求されたイベントを WebView が発生させる理由。</span><span class="sxs-lookup"><span data-stu-id="54442-114">The reason for WebView to fire the MoveFocus Requested event.</span></span>

## <span data-ttu-id="54442-115">Members</span><span class="sxs-lookup"><span data-stu-id="54442-115">Members</span></span>

#### <span data-ttu-id="54442-116">Handled</span><span class="sxs-lookup"><span data-stu-id="54442-116">Handled</span></span> 

<span data-ttu-id="54442-117">イベントがアプリによって処理されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="54442-117">Indicate whether the event has been handled by the app.</span></span>

> <span data-ttu-id="54442-118">パブリックブール[処理](#handled)</span><span class="sxs-lookup"><span data-stu-id="54442-118">public bool [Handled](#handled)</span></span>

<span data-ttu-id="54442-119">アプリがフォーカスを目的の場所に移動した場合は、Handled プロパティを TRUE に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54442-119">If the app has moved the focus to its desired location, it should set Handled property to TRUE.</span></span> <span data-ttu-id="54442-120">イベントハンドラーから制御が返された後、Handled プロパティが false の場合は、既定のアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="54442-120">When Handled property is false after the event handler returns, default action will be taken.</span></span> <span data-ttu-id="54442-121">既定のアクションでは、アプリで次のタブ位置の子ウィンドウを検索し、フォーカスをそのウィンドウに移動しようとします。</span><span class="sxs-lookup"><span data-stu-id="54442-121">The default action is to try to find the next tab stop child window in the app and try to move focus to that window.</span></span> <span data-ttu-id="54442-122">フォーカスを移動できるその他のウィンドウがない場合は、WebView の web コンテンツ内でフォーカスが変更されます。</span><span class="sxs-lookup"><span data-stu-id="54442-122">If there is no other such window to move focus to, focus will be cycled within the WebView's web content.</span></span>

#### <span data-ttu-id="54442-123">理由</span><span class="sxs-lookup"><span data-stu-id="54442-123">Reason</span></span> 

<span data-ttu-id="54442-124">MoveFocus 要求されたイベントを WebView が発生させる理由。</span><span class="sxs-lookup"><span data-stu-id="54442-124">The reason for WebView to fire the MoveFocus Requested event.</span></span>

> <span data-ttu-id="54442-125">パブリック CoreWebView2MoveFocusReason の[理由](#reason)</span><span class="sxs-lookup"><span data-stu-id="54442-125">public CoreWebView2MoveFocusReason [Reason](#reason)</span></span>

