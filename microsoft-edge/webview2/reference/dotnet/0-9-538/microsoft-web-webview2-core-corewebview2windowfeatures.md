---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 (CoreWebView2WindowFeatures の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2WindowFeatures。
ms.openlocfilehash: 59e051c0537357fed89d6300db69ea479b656c7e
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010517"
---
# <span data-ttu-id="d4bea-104">0.9.579 クラスの WebView2 クラス (CoreWebView2WindowFeatures)</span><span class="sxs-lookup"><span data-stu-id="d4bea-104">0.9.579 - Microsoft.Web.WebView2.Core.CoreWebView2WindowFeatures class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="d4bea-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="d4bea-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="d4bea-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="d4bea-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="d4bea-107">WebView ポップアップウィンドウのウィンドウ機能。</span><span class="sxs-lookup"><span data-stu-id="d4bea-107">Window features for a WebView popup window.</span></span>

## <span data-ttu-id="d4bea-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="d4bea-108">Summary</span></span>

 <span data-ttu-id="d4bea-109">Members</span><span class="sxs-lookup"><span data-stu-id="d4bea-109">Members</span></span>                        | <span data-ttu-id="d4bea-110">説明</span><span class="sxs-lookup"><span data-stu-id="d4bea-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d4bea-111">サイズ</span><span class="sxs-lookup"><span data-stu-id="d4bea-111">Height</span></span>](#height) | <span data-ttu-id="d4bea-112">ウィンドウの高さ。</span><span class="sxs-lookup"><span data-stu-id="d4bea-112">The height of the window.</span></span>
[<span data-ttu-id="d4bea-113">Left</span><span class="sxs-lookup"><span data-stu-id="d4bea-113">Left</span></span>](#left) | <span data-ttu-id="d4bea-114">ウィンドウの左端。</span><span class="sxs-lookup"><span data-stu-id="d4bea-114">The left position of the window.</span></span>
[<span data-ttu-id="d4bea-115">メニューバー</span><span class="sxs-lookup"><span data-stu-id="d4bea-115">MenuBar</span></span>](#menubar) | <span data-ttu-id="d4bea-116">メニューバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="d4bea-116">Whether or not to display the menu bar.</span></span>
[<span data-ttu-id="d4bea-117">スクロールバー</span><span class="sxs-lookup"><span data-stu-id="d4bea-117">ScrollBars</span></span>](#scrollbars) | <span data-ttu-id="d4bea-118">スクロールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="d4bea-118">Whether or not to display scroll bars.</span></span>
[<span data-ttu-id="d4bea-119">ステータス</span><span class="sxs-lookup"><span data-stu-id="d4bea-119">Status</span></span>](#status) | <span data-ttu-id="d4bea-120">ステータスバーを追加するかどうか。</span><span class="sxs-lookup"><span data-stu-id="d4bea-120">Whether or not to add a status bar.</span></span>
[<span data-ttu-id="d4bea-121">ツール バー</span><span class="sxs-lookup"><span data-stu-id="d4bea-121">Toolbar</span></span>](#toolbar) | <span data-ttu-id="d4bea-122">ブラウザーのツールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="d4bea-122">Whether or not to display the browser toolbar.</span></span>
[<span data-ttu-id="d4bea-123">先頭</span><span class="sxs-lookup"><span data-stu-id="d4bea-123">Top</span></span>](#top) | <span data-ttu-id="d4bea-124">ウィンドウの一番上の位置。</span><span class="sxs-lookup"><span data-stu-id="d4bea-124">The top position of the window.</span></span>
[<span data-ttu-id="d4bea-125">幅</span><span class="sxs-lookup"><span data-stu-id="d4bea-125">Width</span></span>](#width) | <span data-ttu-id="d4bea-126">ウィンドウの幅。</span><span class="sxs-lookup"><span data-stu-id="d4bea-126">The width of the window.</span></span>
[<span data-ttu-id="d4bea-127">HasPosition</span><span class="sxs-lookup"><span data-stu-id="d4bea-127">HasPosition</span></span>](#hasposition) | <span data-ttu-id="d4bea-128">は左と上の値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="d4bea-128">Has specified left and top values.</span></span>
[<span data-ttu-id="d4bea-129">HasSize</span><span class="sxs-lookup"><span data-stu-id="d4bea-129">HasSize</span></span>](#hassize) | <span data-ttu-id="d4bea-130">高さと幅の値を指定しました。</span><span class="sxs-lookup"><span data-stu-id="d4bea-130">Has specified height and width values.</span></span>

## <span data-ttu-id="d4bea-131">Members</span><span class="sxs-lookup"><span data-stu-id="d4bea-131">Members</span></span>

#### <span data-ttu-id="d4bea-132">サイズ</span><span class="sxs-lookup"><span data-stu-id="d4bea-132">Height</span></span> 

<span data-ttu-id="d4bea-133">ウィンドウの高さ。</span><span class="sxs-lookup"><span data-stu-id="d4bea-133">The height of the window.</span></span>

> <span data-ttu-id="d4bea-134">パブリック uint の [高さ](#height)</span><span class="sxs-lookup"><span data-stu-id="d4bea-134">public uint [Height](#height)</span></span>

#### <span data-ttu-id="d4bea-135">Left</span><span class="sxs-lookup"><span data-stu-id="d4bea-135">Left</span></span> 

<span data-ttu-id="d4bea-136">ウィンドウの左端。</span><span class="sxs-lookup"><span data-stu-id="d4bea-136">The left position of the window.</span></span>

> <span data-ttu-id="d4bea-137">公開 uint の [左](#left)</span><span class="sxs-lookup"><span data-stu-id="d4bea-137">public uint [Left](#left)</span></span>

<span data-ttu-id="d4bea-138">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="d4bea-138">Will fail if HasPosition is false.</span></span>

#### <span data-ttu-id="d4bea-139">メニューバー</span><span class="sxs-lookup"><span data-stu-id="d4bea-139">MenuBar</span></span> 

<span data-ttu-id="d4bea-140">メニューバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="d4bea-140">Whether or not to display the menu bar.</span></span>

> <span data-ttu-id="d4bea-141">パブリック int [メニューバー](#menubar)</span><span class="sxs-lookup"><span data-stu-id="d4bea-141">public int [MenuBar](#menubar)</span></span>

#### <span data-ttu-id="d4bea-142">スクロールバー</span><span class="sxs-lookup"><span data-stu-id="d4bea-142">ScrollBars</span></span> 

<span data-ttu-id="d4bea-143">スクロールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="d4bea-143">Whether or not to display scroll bars.</span></span>

> <span data-ttu-id="d4bea-144">パブリック int [スクロールバー](#scrollbars)</span><span class="sxs-lookup"><span data-stu-id="d4bea-144">public int [ScrollBars](#scrollbars)</span></span>

#### <span data-ttu-id="d4bea-145">ステータス</span><span class="sxs-lookup"><span data-stu-id="d4bea-145">Status</span></span> 

<span data-ttu-id="d4bea-146">ステータスバーを追加するかどうか。</span><span class="sxs-lookup"><span data-stu-id="d4bea-146">Whether or not to add a status bar.</span></span>

> <span data-ttu-id="d4bea-147">パブリック整数の [状態](#status)</span><span class="sxs-lookup"><span data-stu-id="d4bea-147">public int [Status](#status)</span></span>

#### <span data-ttu-id="d4bea-148">ツール バー</span><span class="sxs-lookup"><span data-stu-id="d4bea-148">Toolbar</span></span> 

<span data-ttu-id="d4bea-149">ブラウザーのツールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="d4bea-149">Whether or not to display the browser toolbar.</span></span>

> <span data-ttu-id="d4bea-150">パブリックの int [ツールバー](#toolbar)</span><span class="sxs-lookup"><span data-stu-id="d4bea-150">public int [Toolbar](#toolbar)</span></span>

#### <span data-ttu-id="d4bea-151">先頭</span><span class="sxs-lookup"><span data-stu-id="d4bea-151">Top</span></span> 

<span data-ttu-id="d4bea-152">ウィンドウの一番上の位置。</span><span class="sxs-lookup"><span data-stu-id="d4bea-152">The top position of the window.</span></span>

> <span data-ttu-id="d4bea-153">公開 uint の [最上位](#top)</span><span class="sxs-lookup"><span data-stu-id="d4bea-153">public uint [Top](#top)</span></span>

<span data-ttu-id="d4bea-154">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="d4bea-154">Will fail if HasPosition is false.</span></span>

#### <span data-ttu-id="d4bea-155">幅</span><span class="sxs-lookup"><span data-stu-id="d4bea-155">Width</span></span> 

<span data-ttu-id="d4bea-156">ウィンドウの幅。</span><span class="sxs-lookup"><span data-stu-id="d4bea-156">The width of the window.</span></span>

> <span data-ttu-id="d4bea-157">パブリック uint の [幅](#width)</span><span class="sxs-lookup"><span data-stu-id="d4bea-157">public uint [Width](#width)</span></span>

#### <span data-ttu-id="d4bea-158">HasPosition</span><span class="sxs-lookup"><span data-stu-id="d4bea-158">HasPosition</span></span> 

<span data-ttu-id="d4bea-159">は左と上の値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="d4bea-159">Has specified left and top values.</span></span>

> <span data-ttu-id="d4bea-160">公開 int [Hasposition](#hasposition)()</span><span class="sxs-lookup"><span data-stu-id="d4bea-160">public int [HasPosition](#hasposition)()</span></span>

#### <span data-ttu-id="d4bea-161">HasSize</span><span class="sxs-lookup"><span data-stu-id="d4bea-161">HasSize</span></span> 

<span data-ttu-id="d4bea-162">高さと幅の値を指定しました。</span><span class="sxs-lookup"><span data-stu-id="d4bea-162">Has specified height and width values.</span></span>

> <span data-ttu-id="d4bea-163">公開 int [Hassize](#hassize)()</span><span class="sxs-lookup"><span data-stu-id="d4bea-163">public int [HasSize](#hassize)()</span></span>

