---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 9ee85620ece653a2312076f7b6f4fe9f6ca3da92
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699094"
---
# <span data-ttu-id="fcbe3-104">WebView2 クラス (CoreWebView2WindowFeatures クラス)</span><span class="sxs-lookup"><span data-stu-id="fcbe3-104">Microsoft.Web.WebView2.Core.CoreWebView2WindowFeatures class</span></span> 

> [!NOTE]
> <span data-ttu-id="fcbe3-105">これは、SDK バージョン[0.9.538-プレリリース](../../../releasenotes.md#09538)で出荷される[実験的な API](../../../concepts/versioning.md#experimental-apis)です。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-105">This is an [experimental API](../../../concepts/versioning.md#experimental-apis) that shipped with our SDK version [0.9.538-prerelease](../../../releasenotes.md#09538).</span></span>

<span data-ttu-id="fcbe3-106">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="fcbe3-106">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="fcbe3-107">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-107">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="fcbe3-108">WebView ポップアップウィンドウのウィンドウ機能。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-108">Window features for a WebView popup window.</span></span>

## <span data-ttu-id="fcbe3-109">まとめ</span><span class="sxs-lookup"><span data-stu-id="fcbe3-109">Summary</span></span>

 <span data-ttu-id="fcbe3-110">Members</span><span class="sxs-lookup"><span data-stu-id="fcbe3-110">Members</span></span>                        | <span data-ttu-id="fcbe3-111">説明</span><span class="sxs-lookup"><span data-stu-id="fcbe3-111">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="fcbe3-112">サイズ</span><span class="sxs-lookup"><span data-stu-id="fcbe3-112">Height</span></span>](#height) | <span data-ttu-id="fcbe3-113">ウィンドウの高さ。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-113">The height of the window.</span></span>
[<span data-ttu-id="fcbe3-114">Left</span><span class="sxs-lookup"><span data-stu-id="fcbe3-114">Left</span></span>](#left) | <span data-ttu-id="fcbe3-115">ウィンドウの左端。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-115">The left position of the window.</span></span>
[<span data-ttu-id="fcbe3-116">メニューバー</span><span class="sxs-lookup"><span data-stu-id="fcbe3-116">MenuBar</span></span>](#menubar) | <span data-ttu-id="fcbe3-117">メニューバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-117">Whether or not to display the menu bar.</span></span>
[<span data-ttu-id="fcbe3-118">スクロールバー</span><span class="sxs-lookup"><span data-stu-id="fcbe3-118">ScrollBars</span></span>](#scrollbars) | <span data-ttu-id="fcbe3-119">スクロールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-119">Whether or not to display scroll bars.</span></span>
[<span data-ttu-id="fcbe3-120">ステータス</span><span class="sxs-lookup"><span data-stu-id="fcbe3-120">Status</span></span>](#status) | <span data-ttu-id="fcbe3-121">ステータスバーを追加するかどうか。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-121">Whether or not to add a status bar.</span></span>
[<span data-ttu-id="fcbe3-122">ツール バー</span><span class="sxs-lookup"><span data-stu-id="fcbe3-122">Toolbar</span></span>](#toolbar) | <span data-ttu-id="fcbe3-123">ブラウザーのツールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-123">Whether or not to display the browser toolbar.</span></span>
[<span data-ttu-id="fcbe3-124">先頭</span><span class="sxs-lookup"><span data-stu-id="fcbe3-124">Top</span></span>](#top) | <span data-ttu-id="fcbe3-125">ウィンドウの一番上の位置。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-125">The top position of the window.</span></span>
[<span data-ttu-id="fcbe3-126">幅</span><span class="sxs-lookup"><span data-stu-id="fcbe3-126">Width</span></span>](#width) | <span data-ttu-id="fcbe3-127">ウィンドウの幅。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-127">The width of the window.</span></span>
[<span data-ttu-id="fcbe3-128">HasPosition</span><span class="sxs-lookup"><span data-stu-id="fcbe3-128">HasPosition</span></span>](#hasposition) | <span data-ttu-id="fcbe3-129">は左と上の値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-129">Has specified left and top values.</span></span>
[<span data-ttu-id="fcbe3-130">HasSize</span><span class="sxs-lookup"><span data-stu-id="fcbe3-130">HasSize</span></span>](#hassize) | <span data-ttu-id="fcbe3-131">高さと幅の値を指定しました。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-131">Has specified height and width values.</span></span>

## <span data-ttu-id="fcbe3-132">Members</span><span class="sxs-lookup"><span data-stu-id="fcbe3-132">Members</span></span>

#### <span data-ttu-id="fcbe3-133">サイズ</span><span class="sxs-lookup"><span data-stu-id="fcbe3-133">Height</span></span> 

<span data-ttu-id="fcbe3-134">ウィンドウの高さ。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-134">The height of the window.</span></span>

> <span data-ttu-id="fcbe3-135">パブリック uint の[高さ](#height)</span><span class="sxs-lookup"><span data-stu-id="fcbe3-135">public uint [Height](#height)</span></span>

#### <span data-ttu-id="fcbe3-136">Left</span><span class="sxs-lookup"><span data-stu-id="fcbe3-136">Left</span></span> 

<span data-ttu-id="fcbe3-137">ウィンドウの左端。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-137">The left position of the window.</span></span>

> <span data-ttu-id="fcbe3-138">公開 uint の[左](#left)</span><span class="sxs-lookup"><span data-stu-id="fcbe3-138">public uint [Left](#left)</span></span>

<span data-ttu-id="fcbe3-139">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-139">Will fail if HasPosition is false.</span></span>

#### <span data-ttu-id="fcbe3-140">メニューバー</span><span class="sxs-lookup"><span data-stu-id="fcbe3-140">MenuBar</span></span> 

<span data-ttu-id="fcbe3-141">メニューバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-141">Whether or not to display the menu bar.</span></span>

> <span data-ttu-id="fcbe3-142">パブリック int[メニューバー](#menubar)</span><span class="sxs-lookup"><span data-stu-id="fcbe3-142">public int [MenuBar](#menubar)</span></span>

#### <span data-ttu-id="fcbe3-143">スクロールバー</span><span class="sxs-lookup"><span data-stu-id="fcbe3-143">ScrollBars</span></span> 

<span data-ttu-id="fcbe3-144">スクロールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-144">Whether or not to display scroll bars.</span></span>

> <span data-ttu-id="fcbe3-145">パブリック int[スクロールバー](#scrollbars)</span><span class="sxs-lookup"><span data-stu-id="fcbe3-145">public int [ScrollBars](#scrollbars)</span></span>

#### <span data-ttu-id="fcbe3-146">ステータス</span><span class="sxs-lookup"><span data-stu-id="fcbe3-146">Status</span></span> 

<span data-ttu-id="fcbe3-147">ステータスバーを追加するかどうか。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-147">Whether or not to add a status bar.</span></span>

> <span data-ttu-id="fcbe3-148">パブリック整数の[状態](#status)</span><span class="sxs-lookup"><span data-stu-id="fcbe3-148">public int [Status](#status)</span></span>

#### <span data-ttu-id="fcbe3-149">ツール バー</span><span class="sxs-lookup"><span data-stu-id="fcbe3-149">Toolbar</span></span> 

<span data-ttu-id="fcbe3-150">ブラウザーのツールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-150">Whether or not to display the browser toolbar.</span></span>

> <span data-ttu-id="fcbe3-151">パブリックの int[ツールバー](#toolbar)</span><span class="sxs-lookup"><span data-stu-id="fcbe3-151">public int [Toolbar](#toolbar)</span></span>

#### <span data-ttu-id="fcbe3-152">先頭</span><span class="sxs-lookup"><span data-stu-id="fcbe3-152">Top</span></span> 

<span data-ttu-id="fcbe3-153">ウィンドウの一番上の位置。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-153">The top position of the window.</span></span>

> <span data-ttu-id="fcbe3-154">公開 uint の[最上位](#top)</span><span class="sxs-lookup"><span data-stu-id="fcbe3-154">public uint [Top](#top)</span></span>

<span data-ttu-id="fcbe3-155">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-155">Will fail if HasPosition is false.</span></span>

#### <span data-ttu-id="fcbe3-156">幅</span><span class="sxs-lookup"><span data-stu-id="fcbe3-156">Width</span></span> 

<span data-ttu-id="fcbe3-157">ウィンドウの幅。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-157">The width of the window.</span></span>

> <span data-ttu-id="fcbe3-158">パブリック uint の[幅](#width)</span><span class="sxs-lookup"><span data-stu-id="fcbe3-158">public uint [Width](#width)</span></span>

#### <span data-ttu-id="fcbe3-159">HasPosition</span><span class="sxs-lookup"><span data-stu-id="fcbe3-159">HasPosition</span></span> 

<span data-ttu-id="fcbe3-160">は左と上の値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-160">Has specified left and top values.</span></span>

> <span data-ttu-id="fcbe3-161">公開 int [Hasposition](#hasposition)()</span><span class="sxs-lookup"><span data-stu-id="fcbe3-161">public int [HasPosition](#hasposition)()</span></span>

#### <span data-ttu-id="fcbe3-162">HasSize</span><span class="sxs-lookup"><span data-stu-id="fcbe3-162">HasSize</span></span> 

<span data-ttu-id="fcbe3-163">高さと幅の値を指定しました。</span><span class="sxs-lookup"><span data-stu-id="fcbe3-163">Has specified height and width values.</span></span>

> <span data-ttu-id="fcbe3-164">公開 int [Hassize](#hassize)()</span><span class="sxs-lookup"><span data-stu-id="fcbe3-164">public int [HasSize](#hassize)()</span></span>

