---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2WindowFeatures
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2WindowFeatures。
ms.openlocfilehash: d6d6f52456823488c07288c8ed07b9655a29883a
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884438"
---
# <span data-ttu-id="5d144-104">WebView2 クラス (CoreWebView2WindowFeatures クラス)</span><span class="sxs-lookup"><span data-stu-id="5d144-104">Microsoft.Web.WebView2.Core.CoreWebView2WindowFeatures class</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="5d144-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="5d144-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="5d144-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="5d144-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="5d144-107">WebView ポップアップウィンドウのウィンドウ機能。</span><span class="sxs-lookup"><span data-stu-id="5d144-107">Window features for a WebView popup window.</span></span>

## <span data-ttu-id="5d144-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="5d144-108">Summary</span></span>

 <span data-ttu-id="5d144-109">Members</span><span class="sxs-lookup"><span data-stu-id="5d144-109">Members</span></span>                        | <span data-ttu-id="5d144-110">説明</span><span class="sxs-lookup"><span data-stu-id="5d144-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5d144-111">サイズ</span><span class="sxs-lookup"><span data-stu-id="5d144-111">Height</span></span>](#height) | <span data-ttu-id="5d144-112">ウィンドウの高さ。</span><span class="sxs-lookup"><span data-stu-id="5d144-112">The height of the window.</span></span>
[<span data-ttu-id="5d144-113">Left</span><span class="sxs-lookup"><span data-stu-id="5d144-113">Left</span></span>](#left) | <span data-ttu-id="5d144-114">ウィンドウの左端。</span><span class="sxs-lookup"><span data-stu-id="5d144-114">The left position of the window.</span></span>
[<span data-ttu-id="5d144-115">メニューバー</span><span class="sxs-lookup"><span data-stu-id="5d144-115">MenuBar</span></span>](#menubar) | <span data-ttu-id="5d144-116">メニューバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="5d144-116">Whether or not to display the menu bar.</span></span>
[<span data-ttu-id="5d144-117">スクロールバー</span><span class="sxs-lookup"><span data-stu-id="5d144-117">ScrollBars</span></span>](#scrollbars) | <span data-ttu-id="5d144-118">スクロールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="5d144-118">Whether or not to display scroll bars.</span></span>
[<span data-ttu-id="5d144-119">ステータス</span><span class="sxs-lookup"><span data-stu-id="5d144-119">Status</span></span>](#status) | <span data-ttu-id="5d144-120">ステータスバーを追加するかどうか。</span><span class="sxs-lookup"><span data-stu-id="5d144-120">Whether or not to add a status bar.</span></span>
[<span data-ttu-id="5d144-121">ツール バー</span><span class="sxs-lookup"><span data-stu-id="5d144-121">Toolbar</span></span>](#toolbar) | <span data-ttu-id="5d144-122">ブラウザーのツールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="5d144-122">Whether or not to display the browser toolbar.</span></span>
[<span data-ttu-id="5d144-123">先頭</span><span class="sxs-lookup"><span data-stu-id="5d144-123">Top</span></span>](#top) | <span data-ttu-id="5d144-124">ウィンドウの一番上の位置。</span><span class="sxs-lookup"><span data-stu-id="5d144-124">The top position of the window.</span></span>
[<span data-ttu-id="5d144-125">幅</span><span class="sxs-lookup"><span data-stu-id="5d144-125">Width</span></span>](#width) | <span data-ttu-id="5d144-126">ウィンドウの幅。</span><span class="sxs-lookup"><span data-stu-id="5d144-126">The width of the window.</span></span>
[<span data-ttu-id="5d144-127">HasPosition</span><span class="sxs-lookup"><span data-stu-id="5d144-127">HasPosition</span></span>](#hasposition) | <span data-ttu-id="5d144-128">は左と上の値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="5d144-128">Has specified left and top values.</span></span>
[<span data-ttu-id="5d144-129">HasSize</span><span class="sxs-lookup"><span data-stu-id="5d144-129">HasSize</span></span>](#hassize) | <span data-ttu-id="5d144-130">高さと幅の値を指定しました。</span><span class="sxs-lookup"><span data-stu-id="5d144-130">Has specified height and width values.</span></span>

## <span data-ttu-id="5d144-131">Members</span><span class="sxs-lookup"><span data-stu-id="5d144-131">Members</span></span>

#### <span data-ttu-id="5d144-132">サイズ</span><span class="sxs-lookup"><span data-stu-id="5d144-132">Height</span></span> 

<span data-ttu-id="5d144-133">ウィンドウの高さ。</span><span class="sxs-lookup"><span data-stu-id="5d144-133">The height of the window.</span></span>

> <span data-ttu-id="5d144-134">パブリック uint の[高さ](#height)</span><span class="sxs-lookup"><span data-stu-id="5d144-134">public uint [Height](#height)</span></span>

#### <span data-ttu-id="5d144-135">Left</span><span class="sxs-lookup"><span data-stu-id="5d144-135">Left</span></span> 

<span data-ttu-id="5d144-136">ウィンドウの左端。</span><span class="sxs-lookup"><span data-stu-id="5d144-136">The left position of the window.</span></span>

> <span data-ttu-id="5d144-137">公開 uint の[左](#left)</span><span class="sxs-lookup"><span data-stu-id="5d144-137">public uint [Left](#left)</span></span>

<span data-ttu-id="5d144-138">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="5d144-138">Will fail if HasPosition is false.</span></span>

#### <span data-ttu-id="5d144-139">メニューバー</span><span class="sxs-lookup"><span data-stu-id="5d144-139">MenuBar</span></span> 

<span data-ttu-id="5d144-140">メニューバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="5d144-140">Whether or not to display the menu bar.</span></span>

> <span data-ttu-id="5d144-141">パブリック int[メニューバー](#menubar)</span><span class="sxs-lookup"><span data-stu-id="5d144-141">public int [MenuBar](#menubar)</span></span>

#### <span data-ttu-id="5d144-142">スクロールバー</span><span class="sxs-lookup"><span data-stu-id="5d144-142">ScrollBars</span></span> 

<span data-ttu-id="5d144-143">スクロールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="5d144-143">Whether or not to display scroll bars.</span></span>

> <span data-ttu-id="5d144-144">パブリック int[スクロールバー](#scrollbars)</span><span class="sxs-lookup"><span data-stu-id="5d144-144">public int [ScrollBars](#scrollbars)</span></span>

#### <span data-ttu-id="5d144-145">ステータス</span><span class="sxs-lookup"><span data-stu-id="5d144-145">Status</span></span> 

<span data-ttu-id="5d144-146">ステータスバーを追加するかどうか。</span><span class="sxs-lookup"><span data-stu-id="5d144-146">Whether or not to add a status bar.</span></span>

> <span data-ttu-id="5d144-147">パブリック整数の[状態](#status)</span><span class="sxs-lookup"><span data-stu-id="5d144-147">public int [Status](#status)</span></span>

#### <span data-ttu-id="5d144-148">ツール バー</span><span class="sxs-lookup"><span data-stu-id="5d144-148">Toolbar</span></span> 

<span data-ttu-id="5d144-149">ブラウザーのツールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="5d144-149">Whether or not to display the browser toolbar.</span></span>

> <span data-ttu-id="5d144-150">パブリックの int[ツールバー](#toolbar)</span><span class="sxs-lookup"><span data-stu-id="5d144-150">public int [Toolbar](#toolbar)</span></span>

#### <span data-ttu-id="5d144-151">先頭</span><span class="sxs-lookup"><span data-stu-id="5d144-151">Top</span></span> 

<span data-ttu-id="5d144-152">ウィンドウの一番上の位置。</span><span class="sxs-lookup"><span data-stu-id="5d144-152">The top position of the window.</span></span>

> <span data-ttu-id="5d144-153">公開 uint の[最上位](#top)</span><span class="sxs-lookup"><span data-stu-id="5d144-153">public uint [Top](#top)</span></span>

<span data-ttu-id="5d144-154">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="5d144-154">Will fail if HasPosition is false.</span></span>

#### <span data-ttu-id="5d144-155">幅</span><span class="sxs-lookup"><span data-stu-id="5d144-155">Width</span></span> 

<span data-ttu-id="5d144-156">ウィンドウの幅。</span><span class="sxs-lookup"><span data-stu-id="5d144-156">The width of the window.</span></span>

> <span data-ttu-id="5d144-157">パブリック uint の[幅](#width)</span><span class="sxs-lookup"><span data-stu-id="5d144-157">public uint [Width](#width)</span></span>

#### <span data-ttu-id="5d144-158">HasPosition</span><span class="sxs-lookup"><span data-stu-id="5d144-158">HasPosition</span></span> 

<span data-ttu-id="5d144-159">は左と上の値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="5d144-159">Has specified left and top values.</span></span>

> <span data-ttu-id="5d144-160">公開 int [Hasposition](#hasposition)()</span><span class="sxs-lookup"><span data-stu-id="5d144-160">public int [HasPosition](#hasposition)()</span></span>

#### <span data-ttu-id="5d144-161">HasSize</span><span class="sxs-lookup"><span data-stu-id="5d144-161">HasSize</span></span> 

<span data-ttu-id="5d144-162">高さと幅の値を指定しました。</span><span class="sxs-lookup"><span data-stu-id="5d144-162">Has specified height and width values.</span></span>

> <span data-ttu-id="5d144-163">公開 int [Hassize](#hassize)()</span><span class="sxs-lookup"><span data-stu-id="5d144-163">public int [HasSize](#hassize)()</span></span>

