---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2WindowFeatures
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2WindowFeatures。
ms.openlocfilehash: 4866626111908eae9800da0baabec0356d5d4bf8
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879654"
---
# <span data-ttu-id="c2acb-104">WebView2 クラス (CoreWebView2WindowFeatures クラス)</span><span class="sxs-lookup"><span data-stu-id="c2acb-104">Microsoft.Web.WebView2.Core.CoreWebView2WindowFeatures class</span></span> 

> [!NOTE]
> <span data-ttu-id="c2acb-105">これは、SDK バージョン[0.9.538-プレリリース](../../../releasenotes.md#09538)で出荷される[実験的な API](../../../concepts/versioning.md#experimental-apis)です。</span><span class="sxs-lookup"><span data-stu-id="c2acb-105">This is an [experimental API](../../../concepts/versioning.md#experimental-apis) that shipped with our SDK version [0.9.538-prerelease](../../../releasenotes.md#09538).</span></span>

<span data-ttu-id="c2acb-106">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="c2acb-106">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="c2acb-107">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="c2acb-107">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="c2acb-108">WebView ポップアップウィンドウのウィンドウ機能。</span><span class="sxs-lookup"><span data-stu-id="c2acb-108">Window features for a WebView popup window.</span></span>

## <span data-ttu-id="c2acb-109">まとめ</span><span class="sxs-lookup"><span data-stu-id="c2acb-109">Summary</span></span>

 <span data-ttu-id="c2acb-110">Members</span><span class="sxs-lookup"><span data-stu-id="c2acb-110">Members</span></span>                        | <span data-ttu-id="c2acb-111">説明</span><span class="sxs-lookup"><span data-stu-id="c2acb-111">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c2acb-112">サイズ</span><span class="sxs-lookup"><span data-stu-id="c2acb-112">Height</span></span>](#height) | <span data-ttu-id="c2acb-113">ウィンドウの高さ。</span><span class="sxs-lookup"><span data-stu-id="c2acb-113">The height of the window.</span></span>
[<span data-ttu-id="c2acb-114">Left</span><span class="sxs-lookup"><span data-stu-id="c2acb-114">Left</span></span>](#left) | <span data-ttu-id="c2acb-115">ウィンドウの左端。</span><span class="sxs-lookup"><span data-stu-id="c2acb-115">The left position of the window.</span></span>
[<span data-ttu-id="c2acb-116">メニューバー</span><span class="sxs-lookup"><span data-stu-id="c2acb-116">MenuBar</span></span>](#menubar) | <span data-ttu-id="c2acb-117">メニューバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="c2acb-117">Whether or not to display the menu bar.</span></span>
[<span data-ttu-id="c2acb-118">スクロールバー</span><span class="sxs-lookup"><span data-stu-id="c2acb-118">ScrollBars</span></span>](#scrollbars) | <span data-ttu-id="c2acb-119">スクロールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="c2acb-119">Whether or not to display scroll bars.</span></span>
[<span data-ttu-id="c2acb-120">ステータス</span><span class="sxs-lookup"><span data-stu-id="c2acb-120">Status</span></span>](#status) | <span data-ttu-id="c2acb-121">ステータスバーを追加するかどうか。</span><span class="sxs-lookup"><span data-stu-id="c2acb-121">Whether or not to add a status bar.</span></span>
[<span data-ttu-id="c2acb-122">ツール バー</span><span class="sxs-lookup"><span data-stu-id="c2acb-122">Toolbar</span></span>](#toolbar) | <span data-ttu-id="c2acb-123">ブラウザーのツールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="c2acb-123">Whether or not to display the browser toolbar.</span></span>
[<span data-ttu-id="c2acb-124">先頭</span><span class="sxs-lookup"><span data-stu-id="c2acb-124">Top</span></span>](#top) | <span data-ttu-id="c2acb-125">ウィンドウの一番上の位置。</span><span class="sxs-lookup"><span data-stu-id="c2acb-125">The top position of the window.</span></span>
[<span data-ttu-id="c2acb-126">幅</span><span class="sxs-lookup"><span data-stu-id="c2acb-126">Width</span></span>](#width) | <span data-ttu-id="c2acb-127">ウィンドウの幅。</span><span class="sxs-lookup"><span data-stu-id="c2acb-127">The width of the window.</span></span>
[<span data-ttu-id="c2acb-128">HasPosition</span><span class="sxs-lookup"><span data-stu-id="c2acb-128">HasPosition</span></span>](#hasposition) | <span data-ttu-id="c2acb-129">は左と上の値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="c2acb-129">Has specified left and top values.</span></span>
[<span data-ttu-id="c2acb-130">HasSize</span><span class="sxs-lookup"><span data-stu-id="c2acb-130">HasSize</span></span>](#hassize) | <span data-ttu-id="c2acb-131">高さと幅の値を指定しました。</span><span class="sxs-lookup"><span data-stu-id="c2acb-131">Has specified height and width values.</span></span>

## <span data-ttu-id="c2acb-132">Members</span><span class="sxs-lookup"><span data-stu-id="c2acb-132">Members</span></span>

#### <span data-ttu-id="c2acb-133">サイズ</span><span class="sxs-lookup"><span data-stu-id="c2acb-133">Height</span></span> 

<span data-ttu-id="c2acb-134">ウィンドウの高さ。</span><span class="sxs-lookup"><span data-stu-id="c2acb-134">The height of the window.</span></span>

> <span data-ttu-id="c2acb-135">パブリック uint の[高さ](#height)</span><span class="sxs-lookup"><span data-stu-id="c2acb-135">public uint [Height](#height)</span></span>

#### <span data-ttu-id="c2acb-136">Left</span><span class="sxs-lookup"><span data-stu-id="c2acb-136">Left</span></span> 

<span data-ttu-id="c2acb-137">ウィンドウの左端。</span><span class="sxs-lookup"><span data-stu-id="c2acb-137">The left position of the window.</span></span>

> <span data-ttu-id="c2acb-138">公開 uint の[左](#left)</span><span class="sxs-lookup"><span data-stu-id="c2acb-138">public uint [Left](#left)</span></span>

<span data-ttu-id="c2acb-139">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="c2acb-139">Will fail if HasPosition is false.</span></span>

#### <span data-ttu-id="c2acb-140">メニューバー</span><span class="sxs-lookup"><span data-stu-id="c2acb-140">MenuBar</span></span> 

<span data-ttu-id="c2acb-141">メニューバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="c2acb-141">Whether or not to display the menu bar.</span></span>

> <span data-ttu-id="c2acb-142">パブリック int[メニューバー](#menubar)</span><span class="sxs-lookup"><span data-stu-id="c2acb-142">public int [MenuBar](#menubar)</span></span>

#### <span data-ttu-id="c2acb-143">スクロールバー</span><span class="sxs-lookup"><span data-stu-id="c2acb-143">ScrollBars</span></span> 

<span data-ttu-id="c2acb-144">スクロールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="c2acb-144">Whether or not to display scroll bars.</span></span>

> <span data-ttu-id="c2acb-145">パブリック int[スクロールバー](#scrollbars)</span><span class="sxs-lookup"><span data-stu-id="c2acb-145">public int [ScrollBars](#scrollbars)</span></span>

#### <span data-ttu-id="c2acb-146">ステータス</span><span class="sxs-lookup"><span data-stu-id="c2acb-146">Status</span></span> 

<span data-ttu-id="c2acb-147">ステータスバーを追加するかどうか。</span><span class="sxs-lookup"><span data-stu-id="c2acb-147">Whether or not to add a status bar.</span></span>

> <span data-ttu-id="c2acb-148">パブリック整数の[状態](#status)</span><span class="sxs-lookup"><span data-stu-id="c2acb-148">public int [Status](#status)</span></span>

#### <span data-ttu-id="c2acb-149">ツール バー</span><span class="sxs-lookup"><span data-stu-id="c2acb-149">Toolbar</span></span> 

<span data-ttu-id="c2acb-150">ブラウザーのツールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="c2acb-150">Whether or not to display the browser toolbar.</span></span>

> <span data-ttu-id="c2acb-151">パブリックの int[ツールバー](#toolbar)</span><span class="sxs-lookup"><span data-stu-id="c2acb-151">public int [Toolbar](#toolbar)</span></span>

#### <span data-ttu-id="c2acb-152">先頭</span><span class="sxs-lookup"><span data-stu-id="c2acb-152">Top</span></span> 

<span data-ttu-id="c2acb-153">ウィンドウの一番上の位置。</span><span class="sxs-lookup"><span data-stu-id="c2acb-153">The top position of the window.</span></span>

> <span data-ttu-id="c2acb-154">公開 uint の[最上位](#top)</span><span class="sxs-lookup"><span data-stu-id="c2acb-154">public uint [Top](#top)</span></span>

<span data-ttu-id="c2acb-155">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="c2acb-155">Will fail if HasPosition is false.</span></span>

#### <span data-ttu-id="c2acb-156">幅</span><span class="sxs-lookup"><span data-stu-id="c2acb-156">Width</span></span> 

<span data-ttu-id="c2acb-157">ウィンドウの幅。</span><span class="sxs-lookup"><span data-stu-id="c2acb-157">The width of the window.</span></span>

> <span data-ttu-id="c2acb-158">パブリック uint の[幅](#width)</span><span class="sxs-lookup"><span data-stu-id="c2acb-158">public uint [Width](#width)</span></span>

#### <span data-ttu-id="c2acb-159">HasPosition</span><span class="sxs-lookup"><span data-stu-id="c2acb-159">HasPosition</span></span> 

<span data-ttu-id="c2acb-160">は左と上の値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="c2acb-160">Has specified left and top values.</span></span>

> <span data-ttu-id="c2acb-161">公開 int [Hasposition](#hasposition)()</span><span class="sxs-lookup"><span data-stu-id="c2acb-161">public int [HasPosition](#hasposition)()</span></span>

#### <span data-ttu-id="c2acb-162">HasSize</span><span class="sxs-lookup"><span data-stu-id="c2acb-162">HasSize</span></span> 

<span data-ttu-id="c2acb-163">高さと幅の値を指定しました。</span><span class="sxs-lookup"><span data-stu-id="c2acb-163">Has specified height and width values.</span></span>

> <span data-ttu-id="c2acb-164">公開 int [Hassize](#hassize)()</span><span class="sxs-lookup"><span data-stu-id="c2acb-164">public int [HasSize](#hassize)()</span></span>

