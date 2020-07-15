---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ExperimentalWindowFeatures
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalWindowFeatures
ms.openlocfilehash: 8b56d16e9c78738e9aa61e8c4c5b841b7fe4932f
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879906"
---
# <span data-ttu-id="d28f7-104">インターフェイス ICoreWebView2ExperimentalWindowFeatures</span><span class="sxs-lookup"><span data-stu-id="d28f7-104">interface ICoreWebView2ExperimentalWindowFeatures</span></span> 

> [!NOTE]
> <span data-ttu-id="d28f7-105">これは、プレリリース SDK バージョン0.9.538 に同梱されている実験的な API です。</span><span class="sxs-lookup"><span data-stu-id="d28f7-105">This an experimental API that is shipped with our prerelease SDK version 0.9.538.</span></span>

```
interface ICoreWebView2ExperimentalWindowFeatures
  : public IUnknown
```

<span data-ttu-id="d28f7-106">WebView ポップアップウィンドウのウィンドウ機能。</span><span class="sxs-lookup"><span data-stu-id="d28f7-106">Window features for a WebView popup window.</span></span>

## <span data-ttu-id="d28f7-107">まとめ</span><span class="sxs-lookup"><span data-stu-id="d28f7-107">Summary</span></span>

 <span data-ttu-id="d28f7-108">Members</span><span class="sxs-lookup"><span data-stu-id="d28f7-108">Members</span></span>                        | <span data-ttu-id="d28f7-109">説明</span><span class="sxs-lookup"><span data-stu-id="d28f7-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d28f7-110">get_Height</span><span class="sxs-lookup"><span data-stu-id="d28f7-110">get_Height</span></span>](#get_height) | <span data-ttu-id="d28f7-111">ウィンドウの高さ。</span><span class="sxs-lookup"><span data-stu-id="d28f7-111">The height of the window.</span></span>
[<span data-ttu-id="d28f7-112">get_Left</span><span class="sxs-lookup"><span data-stu-id="d28f7-112">get_Left</span></span>](#get_left) | <span data-ttu-id="d28f7-113">ウィンドウの左端。</span><span class="sxs-lookup"><span data-stu-id="d28f7-113">The left position of the window.</span></span> <span data-ttu-id="d28f7-114">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="d28f7-114">Will fail if HasPosition is false.</span></span>
[<span data-ttu-id="d28f7-115">get_MenuBar</span><span class="sxs-lookup"><span data-stu-id="d28f7-115">get_MenuBar</span></span>](#get_menubar) | <span data-ttu-id="d28f7-116">メニューバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="d28f7-116">Whether or not to display the menu bar.</span></span>
[<span data-ttu-id="d28f7-117">get_ScrollBars</span><span class="sxs-lookup"><span data-stu-id="d28f7-117">get_ScrollBars</span></span>](#get_scrollbars) | <span data-ttu-id="d28f7-118">スクロールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="d28f7-118">Whether or not to display scroll bars.</span></span>
[<span data-ttu-id="d28f7-119">get_Status</span><span class="sxs-lookup"><span data-stu-id="d28f7-119">get_Status</span></span>](#get_status) | <span data-ttu-id="d28f7-120">ステータスバーを追加するかどうか。</span><span class="sxs-lookup"><span data-stu-id="d28f7-120">Whether or not to add a status bar.</span></span>
[<span data-ttu-id="d28f7-121">get_Toolbar</span><span class="sxs-lookup"><span data-stu-id="d28f7-121">get_Toolbar</span></span>](#get_toolbar) | <span data-ttu-id="d28f7-122">ブラウザーのツールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="d28f7-122">Whether or not to display the browser toolbar.</span></span>
[<span data-ttu-id="d28f7-123">get_Top</span><span class="sxs-lookup"><span data-stu-id="d28f7-123">get_Top</span></span>](#get_top) | <span data-ttu-id="d28f7-124">ウィンドウの一番上の位置。</span><span class="sxs-lookup"><span data-stu-id="d28f7-124">The top position of the window.</span></span> <span data-ttu-id="d28f7-125">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="d28f7-125">Will fail if HasPosition is false.</span></span>
[<span data-ttu-id="d28f7-126">get_Width</span><span class="sxs-lookup"><span data-stu-id="d28f7-126">get_Width</span></span>](#get_width) | <span data-ttu-id="d28f7-127">ウィンドウの幅。</span><span class="sxs-lookup"><span data-stu-id="d28f7-127">The width of the window.</span></span>
[<span data-ttu-id="d28f7-128">HasPosition</span><span class="sxs-lookup"><span data-stu-id="d28f7-128">HasPosition</span></span>](#hasposition) | <span data-ttu-id="d28f7-129">は左と上の値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="d28f7-129">Has specified left and top values.</span></span>
[<span data-ttu-id="d28f7-130">HasSize</span><span class="sxs-lookup"><span data-stu-id="d28f7-130">HasSize</span></span>](#hassize) | <span data-ttu-id="d28f7-131">高さと幅の値を指定しました。</span><span class="sxs-lookup"><span data-stu-id="d28f7-131">Has specified height and width values.</span></span>

<span data-ttu-id="d28f7-132">これらのフィールドは、次のように指定されているときに、window に渡された "windowFeatures" と一致します。[https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features](https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features)</span><span class="sxs-lookup"><span data-stu-id="d28f7-132">These fields match the 'windowFeatures' passed to window.open as specified in [https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features](https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features)</span></span>

## <span data-ttu-id="d28f7-133">Members</span><span class="sxs-lookup"><span data-stu-id="d28f7-133">Members</span></span>

#### <span data-ttu-id="d28f7-134">get_Height</span><span class="sxs-lookup"><span data-stu-id="d28f7-134">get_Height</span></span> 

<span data-ttu-id="d28f7-135">ウィンドウの高さ。</span><span class="sxs-lookup"><span data-stu-id="d28f7-135">The height of the window.</span></span>

> <span data-ttu-id="d28f7-136">パブリック HRESULT [get_Height](#get_height)(UINT32 \* Height)</span><span class="sxs-lookup"><span data-stu-id="d28f7-136">public HRESULT [get_Height](#get_height)(UINT32 \* height)</span></span>

<span data-ttu-id="d28f7-137">最小値は100です。</span><span class="sxs-lookup"><span data-stu-id="d28f7-137">Minimum value is 100.</span></span> <span data-ttu-id="d28f7-138">HasSize が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="d28f7-138">Will fail if HasSize is false.</span></span>

#### <span data-ttu-id="d28f7-139">get_Left</span><span class="sxs-lookup"><span data-stu-id="d28f7-139">get_Left</span></span> 

<span data-ttu-id="d28f7-140">ウィンドウの左端。</span><span class="sxs-lookup"><span data-stu-id="d28f7-140">The left position of the window.</span></span> <span data-ttu-id="d28f7-141">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="d28f7-141">Will fail if HasPosition is false.</span></span>

> <span data-ttu-id="d28f7-142">パブリック HRESULT [get_Left](#get_left)(UINT32 \* Left)</span><span class="sxs-lookup"><span data-stu-id="d28f7-142">public HRESULT [get_Left](#get_left)(UINT32 \* left)</span></span>

#### <span data-ttu-id="d28f7-143">get_MenuBar</span><span class="sxs-lookup"><span data-stu-id="d28f7-143">get_MenuBar</span></span> 

<span data-ttu-id="d28f7-144">メニューバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="d28f7-144">Whether or not to display the menu bar.</span></span>

> <span data-ttu-id="d28f7-145">パブリック HRESULT [get_MenuBar](#get_menubar)(ブール \* MenuBar)</span><span class="sxs-lookup"><span data-stu-id="d28f7-145">public HRESULT [get_MenuBar](#get_menubar)(BOOL \* menuBar)</span></span>

#### <span data-ttu-id="d28f7-146">get_ScrollBars</span><span class="sxs-lookup"><span data-stu-id="d28f7-146">get_ScrollBars</span></span> 

<span data-ttu-id="d28f7-147">スクロールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="d28f7-147">Whether or not to display scroll bars.</span></span>

> <span data-ttu-id="d28f7-148">パブリック HRESULT [get_ScrollBars](#get_scrollbars)(ブール \* ScrollBars)</span><span class="sxs-lookup"><span data-stu-id="d28f7-148">public HRESULT [get_ScrollBars](#get_scrollbars)(BOOL \* scrollBars)</span></span>

#### <span data-ttu-id="d28f7-149">get_Status</span><span class="sxs-lookup"><span data-stu-id="d28f7-149">get_Status</span></span> 

<span data-ttu-id="d28f7-150">ステータスバーを追加するかどうか。</span><span class="sxs-lookup"><span data-stu-id="d28f7-150">Whether or not to add a status bar.</span></span>

> <span data-ttu-id="d28f7-151">パブリック HRESULT [get_Status](#get_status)(ブール \* 状態)</span><span class="sxs-lookup"><span data-stu-id="d28f7-151">public HRESULT [get_Status](#get_status)(BOOL \* status)</span></span>

#### <span data-ttu-id="d28f7-152">get_Toolbar</span><span class="sxs-lookup"><span data-stu-id="d28f7-152">get_Toolbar</span></span> 

<span data-ttu-id="d28f7-153">ブラウザーのツールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="d28f7-153">Whether or not to display the browser toolbar.</span></span>

> <span data-ttu-id="d28f7-154">パブリック HRESULT [get_Toolbar](#get_toolbar)(ブール \* ツールバー)</span><span class="sxs-lookup"><span data-stu-id="d28f7-154">public HRESULT [get_Toolbar](#get_toolbar)(BOOL \* toolbar)</span></span>

#### <span data-ttu-id="d28f7-155">get_Top</span><span class="sxs-lookup"><span data-stu-id="d28f7-155">get_Top</span></span> 

<span data-ttu-id="d28f7-156">ウィンドウの一番上の位置。</span><span class="sxs-lookup"><span data-stu-id="d28f7-156">The top position of the window.</span></span> <span data-ttu-id="d28f7-157">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="d28f7-157">Will fail if HasPosition is false.</span></span>

> <span data-ttu-id="d28f7-158">パブリック HRESULT [get_Top](#get_top)(UINT32 \* Top)</span><span class="sxs-lookup"><span data-stu-id="d28f7-158">public HRESULT [get_Top](#get_top)(UINT32 \* top)</span></span>

#### <span data-ttu-id="d28f7-159">get_Width</span><span class="sxs-lookup"><span data-stu-id="d28f7-159">get_Width</span></span> 

<span data-ttu-id="d28f7-160">ウィンドウの幅。</span><span class="sxs-lookup"><span data-stu-id="d28f7-160">The width of the window.</span></span>

> <span data-ttu-id="d28f7-161">パブリック HRESULT [get_Width](#get_width)(UINT32 \* Width)</span><span class="sxs-lookup"><span data-stu-id="d28f7-161">public HRESULT [get_Width](#get_width)(UINT32 \* width)</span></span>

<span data-ttu-id="d28f7-162">最小値は100です。</span><span class="sxs-lookup"><span data-stu-id="d28f7-162">Minimum value is 100.</span></span> <span data-ttu-id="d28f7-163">HasSize が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="d28f7-163">Will fail if HasSize is false.</span></span>

#### <span data-ttu-id="d28f7-164">HasPosition</span><span class="sxs-lookup"><span data-stu-id="d28f7-164">HasPosition</span></span> 

<span data-ttu-id="d28f7-165">は左と上の値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="d28f7-165">Has specified left and top values.</span></span>

> <span data-ttu-id="d28f7-166">パブリック HRESULT [hasposition](#hasposition)(ブール \* hasposition)</span><span class="sxs-lookup"><span data-stu-id="d28f7-166">public HRESULT [HasPosition](#hasposition)(BOOL \* hasPosition)</span></span>

#### <span data-ttu-id="d28f7-167">HasSize</span><span class="sxs-lookup"><span data-stu-id="d28f7-167">HasSize</span></span> 

<span data-ttu-id="d28f7-168">高さと幅の値を指定しました。</span><span class="sxs-lookup"><span data-stu-id="d28f7-168">Has specified height and width values.</span></span>

> <span data-ttu-id="d28f7-169">パブリック HRESULT [hassize](#hassize)(ブール \* hassize)</span><span class="sxs-lookup"><span data-stu-id="d28f7-169">public HRESULT [HasSize](#hassize)(BOOL \* hasSize)</span></span>

