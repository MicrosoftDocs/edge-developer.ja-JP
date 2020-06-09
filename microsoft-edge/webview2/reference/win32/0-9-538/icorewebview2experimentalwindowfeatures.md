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
ms.openlocfilehash: 576f54f2a7ecc2e1e99758719e80cc589c5bc791
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699114"
---
# <span data-ttu-id="7aec2-104">インターフェイス ICoreWebView2ExperimentalWindowFeatures</span><span class="sxs-lookup"><span data-stu-id="7aec2-104">interface ICoreWebView2ExperimentalWindowFeatures</span></span> 

> [!NOTE]
> <span data-ttu-id="7aec2-105">これは、プレリリース SDK バージョン0.9.538 に同梱されている実験的な API です。</span><span class="sxs-lookup"><span data-stu-id="7aec2-105">This an experimental API that is shipped with our prerelease SDK version 0.9.538.</span></span>

```
interface ICoreWebView2ExperimentalWindowFeatures
  : public IUnknown
```

<span data-ttu-id="7aec2-106">WebView ポップアップウィンドウのウィンドウ機能。</span><span class="sxs-lookup"><span data-stu-id="7aec2-106">Window features for a WebView popup window.</span></span>

## <span data-ttu-id="7aec2-107">まとめ</span><span class="sxs-lookup"><span data-stu-id="7aec2-107">Summary</span></span>

 <span data-ttu-id="7aec2-108">Members</span><span class="sxs-lookup"><span data-stu-id="7aec2-108">Members</span></span>                        | <span data-ttu-id="7aec2-109">説明</span><span class="sxs-lookup"><span data-stu-id="7aec2-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7aec2-110">get_Height</span><span class="sxs-lookup"><span data-stu-id="7aec2-110">get_Height</span></span>](#get_height) | <span data-ttu-id="7aec2-111">ウィンドウの高さ。</span><span class="sxs-lookup"><span data-stu-id="7aec2-111">The height of the window.</span></span>
[<span data-ttu-id="7aec2-112">get_Left</span><span class="sxs-lookup"><span data-stu-id="7aec2-112">get_Left</span></span>](#get_left) | <span data-ttu-id="7aec2-113">ウィンドウの左端。</span><span class="sxs-lookup"><span data-stu-id="7aec2-113">The left position of the window.</span></span> <span data-ttu-id="7aec2-114">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="7aec2-114">Will fail if HasPosition is false.</span></span>
[<span data-ttu-id="7aec2-115">get_MenuBar</span><span class="sxs-lookup"><span data-stu-id="7aec2-115">get_MenuBar</span></span>](#get_menubar) | <span data-ttu-id="7aec2-116">メニューバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="7aec2-116">Whether or not to display the menu bar.</span></span>
[<span data-ttu-id="7aec2-117">get_ScrollBars</span><span class="sxs-lookup"><span data-stu-id="7aec2-117">get_ScrollBars</span></span>](#get_scrollbars) | <span data-ttu-id="7aec2-118">スクロールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="7aec2-118">Whether or not to display scroll bars.</span></span>
[<span data-ttu-id="7aec2-119">get_Status</span><span class="sxs-lookup"><span data-stu-id="7aec2-119">get_Status</span></span>](#get_status) | <span data-ttu-id="7aec2-120">ステータスバーを追加するかどうか。</span><span class="sxs-lookup"><span data-stu-id="7aec2-120">Whether or not to add a status bar.</span></span>
[<span data-ttu-id="7aec2-121">get_Toolbar</span><span class="sxs-lookup"><span data-stu-id="7aec2-121">get_Toolbar</span></span>](#get_toolbar) | <span data-ttu-id="7aec2-122">ブラウザーのツールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="7aec2-122">Whether or not to display the browser toolbar.</span></span>
[<span data-ttu-id="7aec2-123">get_Top</span><span class="sxs-lookup"><span data-stu-id="7aec2-123">get_Top</span></span>](#get_top) | <span data-ttu-id="7aec2-124">ウィンドウの一番上の位置。</span><span class="sxs-lookup"><span data-stu-id="7aec2-124">The top position of the window.</span></span> <span data-ttu-id="7aec2-125">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="7aec2-125">Will fail if HasPosition is false.</span></span>
[<span data-ttu-id="7aec2-126">get_Width</span><span class="sxs-lookup"><span data-stu-id="7aec2-126">get_Width</span></span>](#get_width) | <span data-ttu-id="7aec2-127">ウィンドウの幅。</span><span class="sxs-lookup"><span data-stu-id="7aec2-127">The width of the window.</span></span>
[<span data-ttu-id="7aec2-128">HasPosition</span><span class="sxs-lookup"><span data-stu-id="7aec2-128">HasPosition</span></span>](#hasposition) | <span data-ttu-id="7aec2-129">は左と上の値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="7aec2-129">Has specified left and top values.</span></span>
[<span data-ttu-id="7aec2-130">HasSize</span><span class="sxs-lookup"><span data-stu-id="7aec2-130">HasSize</span></span>](#hassize) | <span data-ttu-id="7aec2-131">高さと幅の値を指定しました。</span><span class="sxs-lookup"><span data-stu-id="7aec2-131">Has specified height and width values.</span></span>

<span data-ttu-id="7aec2-132">これらのフィールドは、次のように指定されているときに、window に渡された "windowFeatures" と一致します。[https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features](https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features)</span><span class="sxs-lookup"><span data-stu-id="7aec2-132">These fields match the 'windowFeatures' passed to window.open as specified in [https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features](https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features)</span></span>

## <span data-ttu-id="7aec2-133">Members</span><span class="sxs-lookup"><span data-stu-id="7aec2-133">Members</span></span>

#### <span data-ttu-id="7aec2-134">get_Height</span><span class="sxs-lookup"><span data-stu-id="7aec2-134">get_Height</span></span> 

<span data-ttu-id="7aec2-135">ウィンドウの高さ。</span><span class="sxs-lookup"><span data-stu-id="7aec2-135">The height of the window.</span></span>

> <span data-ttu-id="7aec2-136">パブリック HRESULT [get_Height](#get_height)(UINT32 \* Height)</span><span class="sxs-lookup"><span data-stu-id="7aec2-136">public HRESULT [get_Height](#get_height)(UINT32 \* height)</span></span>

<span data-ttu-id="7aec2-137">最小値は100です。</span><span class="sxs-lookup"><span data-stu-id="7aec2-137">Minimum value is 100.</span></span> <span data-ttu-id="7aec2-138">HasSize が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="7aec2-138">Will fail if HasSize is false.</span></span>

#### <span data-ttu-id="7aec2-139">get_Left</span><span class="sxs-lookup"><span data-stu-id="7aec2-139">get_Left</span></span> 

<span data-ttu-id="7aec2-140">ウィンドウの左端。</span><span class="sxs-lookup"><span data-stu-id="7aec2-140">The left position of the window.</span></span> <span data-ttu-id="7aec2-141">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="7aec2-141">Will fail if HasPosition is false.</span></span>

> <span data-ttu-id="7aec2-142">パブリック HRESULT [get_Left](#get_left)(UINT32 \* Left)</span><span class="sxs-lookup"><span data-stu-id="7aec2-142">public HRESULT [get_Left](#get_left)(UINT32 \* left)</span></span>

#### <span data-ttu-id="7aec2-143">get_MenuBar</span><span class="sxs-lookup"><span data-stu-id="7aec2-143">get_MenuBar</span></span> 

<span data-ttu-id="7aec2-144">メニューバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="7aec2-144">Whether or not to display the menu bar.</span></span>

> <span data-ttu-id="7aec2-145">パブリック HRESULT [get_MenuBar](#get_menubar)(ブール \* MenuBar)</span><span class="sxs-lookup"><span data-stu-id="7aec2-145">public HRESULT [get_MenuBar](#get_menubar)(BOOL \* menuBar)</span></span>

#### <span data-ttu-id="7aec2-146">get_ScrollBars</span><span class="sxs-lookup"><span data-stu-id="7aec2-146">get_ScrollBars</span></span> 

<span data-ttu-id="7aec2-147">スクロールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="7aec2-147">Whether or not to display scroll bars.</span></span>

> <span data-ttu-id="7aec2-148">パブリック HRESULT [get_ScrollBars](#get_scrollbars)(ブール \* ScrollBars)</span><span class="sxs-lookup"><span data-stu-id="7aec2-148">public HRESULT [get_ScrollBars](#get_scrollbars)(BOOL \* scrollBars)</span></span>

#### <span data-ttu-id="7aec2-149">get_Status</span><span class="sxs-lookup"><span data-stu-id="7aec2-149">get_Status</span></span> 

<span data-ttu-id="7aec2-150">ステータスバーを追加するかどうか。</span><span class="sxs-lookup"><span data-stu-id="7aec2-150">Whether or not to add a status bar.</span></span>

> <span data-ttu-id="7aec2-151">パブリック HRESULT [get_Status](#get_status)(ブール \* 状態)</span><span class="sxs-lookup"><span data-stu-id="7aec2-151">public HRESULT [get_Status](#get_status)(BOOL \* status)</span></span>

#### <span data-ttu-id="7aec2-152">get_Toolbar</span><span class="sxs-lookup"><span data-stu-id="7aec2-152">get_Toolbar</span></span> 

<span data-ttu-id="7aec2-153">ブラウザーのツールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="7aec2-153">Whether or not to display the browser toolbar.</span></span>

> <span data-ttu-id="7aec2-154">パブリック HRESULT [get_Toolbar](#get_toolbar)(ブール \* ツールバー)</span><span class="sxs-lookup"><span data-stu-id="7aec2-154">public HRESULT [get_Toolbar](#get_toolbar)(BOOL \* toolbar)</span></span>

#### <span data-ttu-id="7aec2-155">get_Top</span><span class="sxs-lookup"><span data-stu-id="7aec2-155">get_Top</span></span> 

<span data-ttu-id="7aec2-156">ウィンドウの一番上の位置。</span><span class="sxs-lookup"><span data-stu-id="7aec2-156">The top position of the window.</span></span> <span data-ttu-id="7aec2-157">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="7aec2-157">Will fail if HasPosition is false.</span></span>

> <span data-ttu-id="7aec2-158">パブリック HRESULT [get_Top](#get_top)(UINT32 \* Top)</span><span class="sxs-lookup"><span data-stu-id="7aec2-158">public HRESULT [get_Top](#get_top)(UINT32 \* top)</span></span>

#### <span data-ttu-id="7aec2-159">get_Width</span><span class="sxs-lookup"><span data-stu-id="7aec2-159">get_Width</span></span> 

<span data-ttu-id="7aec2-160">ウィンドウの幅。</span><span class="sxs-lookup"><span data-stu-id="7aec2-160">The width of the window.</span></span>

> <span data-ttu-id="7aec2-161">パブリック HRESULT [get_Width](#get_width)(UINT32 \* Width)</span><span class="sxs-lookup"><span data-stu-id="7aec2-161">public HRESULT [get_Width](#get_width)(UINT32 \* width)</span></span>

<span data-ttu-id="7aec2-162">最小値は100です。</span><span class="sxs-lookup"><span data-stu-id="7aec2-162">Minimum value is 100.</span></span> <span data-ttu-id="7aec2-163">HasSize が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="7aec2-163">Will fail if HasSize is false.</span></span>

#### <span data-ttu-id="7aec2-164">HasPosition</span><span class="sxs-lookup"><span data-stu-id="7aec2-164">HasPosition</span></span> 

<span data-ttu-id="7aec2-165">は左と上の値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="7aec2-165">Has specified left and top values.</span></span>

> <span data-ttu-id="7aec2-166">パブリック HRESULT [hasposition](#hasposition)(ブール \* hasposition)</span><span class="sxs-lookup"><span data-stu-id="7aec2-166">public HRESULT [HasPosition](#hasposition)(BOOL \* hasPosition)</span></span>

#### <span data-ttu-id="7aec2-167">HasSize</span><span class="sxs-lookup"><span data-stu-id="7aec2-167">HasSize</span></span> 

<span data-ttu-id="7aec2-168">高さと幅の値を指定しました。</span><span class="sxs-lookup"><span data-stu-id="7aec2-168">Has specified height and width values.</span></span>

> <span data-ttu-id="7aec2-169">パブリック HRESULT [hassize](#hassize)(ブール \* hassize)</span><span class="sxs-lookup"><span data-stu-id="7aec2-169">public HRESULT [HasSize](#hassize)(BOOL \* hasSize)</span></span>

