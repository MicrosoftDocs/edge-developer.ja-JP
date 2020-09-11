---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2WindowFeatures
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2WindowFeatures
ms.openlocfilehash: 90b5a09a752250dc342e7eefad031c9b5b83d345
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012313"
---
# <span data-ttu-id="48964-104">インターフェイス ICoreWebView2WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="48964-104">interface ICoreWebView2WindowFeatures</span></span> 

```
interface ICoreWebView2WindowFeatures
  : public IUnknown
```

<span data-ttu-id="48964-105">WebView ポップアップウィンドウのウィンドウ機能。</span><span class="sxs-lookup"><span data-stu-id="48964-105">Window features for a WebView popup window.</span></span>

## <span data-ttu-id="48964-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="48964-106">Summary</span></span>

 <span data-ttu-id="48964-107">Members</span><span class="sxs-lookup"><span data-stu-id="48964-107">Members</span></span>                        | <span data-ttu-id="48964-108">説明</span><span class="sxs-lookup"><span data-stu-id="48964-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="48964-109">get_Height</span><span class="sxs-lookup"><span data-stu-id="48964-109">get_Height</span></span>](#get_height) | <span data-ttu-id="48964-110">ウィンドウの高さ。</span><span class="sxs-lookup"><span data-stu-id="48964-110">The height of the window.</span></span>
[<span data-ttu-id="48964-111">get_Left</span><span class="sxs-lookup"><span data-stu-id="48964-111">get_Left</span></span>](#get_left) | <span data-ttu-id="48964-112">ウィンドウの左端。</span><span class="sxs-lookup"><span data-stu-id="48964-112">The left position of the window.</span></span> <span data-ttu-id="48964-113">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="48964-113">Will fail if HasPosition is false.</span></span>
[<span data-ttu-id="48964-114">get_MenuBar</span><span class="sxs-lookup"><span data-stu-id="48964-114">get_MenuBar</span></span>](#get_menubar) | <span data-ttu-id="48964-115">メニューバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="48964-115">Whether or not to display the menu bar.</span></span>
[<span data-ttu-id="48964-116">get_ScrollBars</span><span class="sxs-lookup"><span data-stu-id="48964-116">get_ScrollBars</span></span>](#get_scrollbars) | <span data-ttu-id="48964-117">スクロールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="48964-117">Whether or not to display scroll bars.</span></span>
[<span data-ttu-id="48964-118">get_Status</span><span class="sxs-lookup"><span data-stu-id="48964-118">get_Status</span></span>](#get_status) | <span data-ttu-id="48964-119">ステータスバーを追加するかどうか。</span><span class="sxs-lookup"><span data-stu-id="48964-119">Whether or not to add a status bar.</span></span>
[<span data-ttu-id="48964-120">get_Toolbar</span><span class="sxs-lookup"><span data-stu-id="48964-120">get_Toolbar</span></span>](#get_toolbar) | <span data-ttu-id="48964-121">ブラウザーのツールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="48964-121">Whether or not to display the browser toolbar.</span></span>
[<span data-ttu-id="48964-122">get_Top</span><span class="sxs-lookup"><span data-stu-id="48964-122">get_Top</span></span>](#get_top) | <span data-ttu-id="48964-123">ウィンドウの一番上の位置。</span><span class="sxs-lookup"><span data-stu-id="48964-123">The top position of the window.</span></span> <span data-ttu-id="48964-124">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="48964-124">Will fail if HasPosition is false.</span></span>
[<span data-ttu-id="48964-125">get_Width</span><span class="sxs-lookup"><span data-stu-id="48964-125">get_Width</span></span>](#get_width) | <span data-ttu-id="48964-126">ウィンドウの幅。</span><span class="sxs-lookup"><span data-stu-id="48964-126">The width of the window.</span></span>
[<span data-ttu-id="48964-127">HasPosition</span><span class="sxs-lookup"><span data-stu-id="48964-127">HasPosition</span></span>](#hasposition) | <span data-ttu-id="48964-128">は左と上の値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="48964-128">Has specified left and top values.</span></span>
[<span data-ttu-id="48964-129">HasSize</span><span class="sxs-lookup"><span data-stu-id="48964-129">HasSize</span></span>](#hassize) | <span data-ttu-id="48964-130">高さと幅の値を指定しました。</span><span class="sxs-lookup"><span data-stu-id="48964-130">Has specified height and width values.</span></span>

<span data-ttu-id="48964-131">これらのフィールドは、次のように指定されているときに、window に渡された "windowFeatures" と一致します。 [https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features](https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features)</span><span class="sxs-lookup"><span data-stu-id="48964-131">These fields match the 'windowFeatures' passed to window.open as specified in [https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features](https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features)</span></span>

## <span data-ttu-id="48964-132">Members</span><span class="sxs-lookup"><span data-stu-id="48964-132">Members</span></span>

#### <span data-ttu-id="48964-133">get_Height</span><span class="sxs-lookup"><span data-stu-id="48964-133">get_Height</span></span> 

<span data-ttu-id="48964-134">ウィンドウの高さ。</span><span class="sxs-lookup"><span data-stu-id="48964-134">The height of the window.</span></span>

> <span data-ttu-id="48964-135">パブリック HRESULT [get_Height](#get_height)(UINT32 \* Height)</span><span class="sxs-lookup"><span data-stu-id="48964-135">public HRESULT [get_Height](#get_height)(UINT32 \* height)</span></span>

<span data-ttu-id="48964-136">最小値は100です。</span><span class="sxs-lookup"><span data-stu-id="48964-136">Minimum value is 100.</span></span> <span data-ttu-id="48964-137">HasSize が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="48964-137">Will fail if HasSize is false.</span></span>

#### <span data-ttu-id="48964-138">get_Left</span><span class="sxs-lookup"><span data-stu-id="48964-138">get_Left</span></span> 

<span data-ttu-id="48964-139">ウィンドウの左端。</span><span class="sxs-lookup"><span data-stu-id="48964-139">The left position of the window.</span></span> <span data-ttu-id="48964-140">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="48964-140">Will fail if HasPosition is false.</span></span>

> <span data-ttu-id="48964-141">パブリック HRESULT [get_Left](#get_left)(UINT32 \* Left)</span><span class="sxs-lookup"><span data-stu-id="48964-141">public HRESULT [get_Left](#get_left)(UINT32 \* left)</span></span>

#### <span data-ttu-id="48964-142">get_MenuBar</span><span class="sxs-lookup"><span data-stu-id="48964-142">get_MenuBar</span></span> 

<span data-ttu-id="48964-143">メニューバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="48964-143">Whether or not to display the menu bar.</span></span>

> <span data-ttu-id="48964-144">パブリック HRESULT [get_MenuBar](#get_menubar)(ブール \* MenuBar)</span><span class="sxs-lookup"><span data-stu-id="48964-144">public HRESULT [get_MenuBar](#get_menubar)(BOOL \* menuBar)</span></span>

#### <span data-ttu-id="48964-145">get_ScrollBars</span><span class="sxs-lookup"><span data-stu-id="48964-145">get_ScrollBars</span></span> 

<span data-ttu-id="48964-146">スクロールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="48964-146">Whether or not to display scroll bars.</span></span>

> <span data-ttu-id="48964-147">パブリック HRESULT [get_ScrollBars](#get_scrollbars)(ブール \* ScrollBars)</span><span class="sxs-lookup"><span data-stu-id="48964-147">public HRESULT [get_ScrollBars](#get_scrollbars)(BOOL \* scrollBars)</span></span>

#### <span data-ttu-id="48964-148">get_Status</span><span class="sxs-lookup"><span data-stu-id="48964-148">get_Status</span></span> 

<span data-ttu-id="48964-149">ステータスバーを追加するかどうか。</span><span class="sxs-lookup"><span data-stu-id="48964-149">Whether or not to add a status bar.</span></span>

> <span data-ttu-id="48964-150">パブリック HRESULT [get_Status](#get_status)(ブール \* 状態)</span><span class="sxs-lookup"><span data-stu-id="48964-150">public HRESULT [get_Status](#get_status)(BOOL \* status)</span></span>

#### <span data-ttu-id="48964-151">get_Toolbar</span><span class="sxs-lookup"><span data-stu-id="48964-151">get_Toolbar</span></span> 

<span data-ttu-id="48964-152">ブラウザーのツールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="48964-152">Whether or not to display the browser toolbar.</span></span>

> <span data-ttu-id="48964-153">パブリック HRESULT [get_Toolbar](#get_toolbar)(ブール \* ツールバー)</span><span class="sxs-lookup"><span data-stu-id="48964-153">public HRESULT [get_Toolbar](#get_toolbar)(BOOL \* toolbar)</span></span>

#### <span data-ttu-id="48964-154">get_Top</span><span class="sxs-lookup"><span data-stu-id="48964-154">get_Top</span></span> 

<span data-ttu-id="48964-155">ウィンドウの一番上の位置。</span><span class="sxs-lookup"><span data-stu-id="48964-155">The top position of the window.</span></span> <span data-ttu-id="48964-156">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="48964-156">Will fail if HasPosition is false.</span></span>

> <span data-ttu-id="48964-157">パブリック HRESULT [get_Top](#get_top)(UINT32 \* Top)</span><span class="sxs-lookup"><span data-stu-id="48964-157">public HRESULT [get_Top](#get_top)(UINT32 \* top)</span></span>

#### <span data-ttu-id="48964-158">get_Width</span><span class="sxs-lookup"><span data-stu-id="48964-158">get_Width</span></span> 

<span data-ttu-id="48964-159">ウィンドウの幅。</span><span class="sxs-lookup"><span data-stu-id="48964-159">The width of the window.</span></span>

> <span data-ttu-id="48964-160">パブリック HRESULT [get_Width](#get_width)(UINT32 \* Width)</span><span class="sxs-lookup"><span data-stu-id="48964-160">public HRESULT [get_Width](#get_width)(UINT32 \* width)</span></span>

<span data-ttu-id="48964-161">最小値は100です。</span><span class="sxs-lookup"><span data-stu-id="48964-161">Minimum value is 100.</span></span> <span data-ttu-id="48964-162">HasSize が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="48964-162">Will fail if HasSize is false.</span></span>

#### <span data-ttu-id="48964-163">HasPosition</span><span class="sxs-lookup"><span data-stu-id="48964-163">HasPosition</span></span> 

<span data-ttu-id="48964-164">は左と上の値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="48964-164">Has specified left and top values.</span></span>

> <span data-ttu-id="48964-165">パブリック HRESULT [hasposition](#hasposition)(ブール \* hasposition)</span><span class="sxs-lookup"><span data-stu-id="48964-165">public HRESULT [HasPosition](#hasposition)(BOOL \* hasPosition)</span></span>

#### <span data-ttu-id="48964-166">HasSize</span><span class="sxs-lookup"><span data-stu-id="48964-166">HasSize</span></span> 

<span data-ttu-id="48964-167">高さと幅の値を指定しました。</span><span class="sxs-lookup"><span data-stu-id="48964-167">Has specified height and width values.</span></span>

> <span data-ttu-id="48964-168">パブリック HRESULT [hassize](#hassize)(ブール \* hassize)</span><span class="sxs-lookup"><span data-stu-id="48964-168">public HRESULT [HasSize](#hassize)(BOOL \* hasSize)</span></span>

