---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ExperimentalWindowFeatures
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalWindowFeatures
ms.openlocfilehash: 2672f2aac842fd475f6148c439dbecdacd7793ee
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885404"
---
# <span data-ttu-id="adb83-104">インターフェイス ICoreWebView2ExperimentalWindowFeatures</span><span class="sxs-lookup"><span data-stu-id="adb83-104">interface ICoreWebView2ExperimentalWindowFeatures</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalWindowFeatures
  : public IUnknown
```

<span data-ttu-id="adb83-105">WebView ポップアップウィンドウのウィンドウ機能。</span><span class="sxs-lookup"><span data-stu-id="adb83-105">Window features for a WebView popup window.</span></span>

## <span data-ttu-id="adb83-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="adb83-106">Summary</span></span>

 <span data-ttu-id="adb83-107">Members</span><span class="sxs-lookup"><span data-stu-id="adb83-107">Members</span></span>                        | <span data-ttu-id="adb83-108">説明</span><span class="sxs-lookup"><span data-stu-id="adb83-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="adb83-109">get_Height</span><span class="sxs-lookup"><span data-stu-id="adb83-109">get_Height</span></span>](#get_height) | <span data-ttu-id="adb83-110">ウィンドウの高さ。</span><span class="sxs-lookup"><span data-stu-id="adb83-110">The height of the window.</span></span>
[<span data-ttu-id="adb83-111">get_Left</span><span class="sxs-lookup"><span data-stu-id="adb83-111">get_Left</span></span>](#get_left) | <span data-ttu-id="adb83-112">ウィンドウの左端。</span><span class="sxs-lookup"><span data-stu-id="adb83-112">The left position of the window.</span></span> <span data-ttu-id="adb83-113">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="adb83-113">Will fail if HasPosition is false.</span></span>
[<span data-ttu-id="adb83-114">get_MenuBar</span><span class="sxs-lookup"><span data-stu-id="adb83-114">get_MenuBar</span></span>](#get_menubar) | <span data-ttu-id="adb83-115">メニューバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="adb83-115">Whether or not to display the menu bar.</span></span>
[<span data-ttu-id="adb83-116">get_ScrollBars</span><span class="sxs-lookup"><span data-stu-id="adb83-116">get_ScrollBars</span></span>](#get_scrollbars) | <span data-ttu-id="adb83-117">スクロールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="adb83-117">Whether or not to display scroll bars.</span></span>
[<span data-ttu-id="adb83-118">get_Status</span><span class="sxs-lookup"><span data-stu-id="adb83-118">get_Status</span></span>](#get_status) | <span data-ttu-id="adb83-119">ステータスバーを追加するかどうか。</span><span class="sxs-lookup"><span data-stu-id="adb83-119">Whether or not to add a status bar.</span></span>
[<span data-ttu-id="adb83-120">get_Toolbar</span><span class="sxs-lookup"><span data-stu-id="adb83-120">get_Toolbar</span></span>](#get_toolbar) | <span data-ttu-id="adb83-121">ブラウザーのツールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="adb83-121">Whether or not to display the browser toolbar.</span></span>
[<span data-ttu-id="adb83-122">get_Top</span><span class="sxs-lookup"><span data-stu-id="adb83-122">get_Top</span></span>](#get_top) | <span data-ttu-id="adb83-123">ウィンドウの一番上の位置。</span><span class="sxs-lookup"><span data-stu-id="adb83-123">The top position of the window.</span></span> <span data-ttu-id="adb83-124">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="adb83-124">Will fail if HasPosition is false.</span></span>
[<span data-ttu-id="adb83-125">get_Width</span><span class="sxs-lookup"><span data-stu-id="adb83-125">get_Width</span></span>](#get_width) | <span data-ttu-id="adb83-126">ウィンドウの幅。</span><span class="sxs-lookup"><span data-stu-id="adb83-126">The width of the window.</span></span>
[<span data-ttu-id="adb83-127">HasPosition</span><span class="sxs-lookup"><span data-stu-id="adb83-127">HasPosition</span></span>](#hasposition) | <span data-ttu-id="adb83-128">は左と上の値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="adb83-128">Has specified left and top values.</span></span>
[<span data-ttu-id="adb83-129">HasSize</span><span class="sxs-lookup"><span data-stu-id="adb83-129">HasSize</span></span>](#hassize) | <span data-ttu-id="adb83-130">高さと幅の値を指定しました。</span><span class="sxs-lookup"><span data-stu-id="adb83-130">Has specified height and width values.</span></span>

<span data-ttu-id="adb83-131">これらのフィールドは、次のように指定されているときに、window に渡された "windowFeatures" と一致します。[https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features](https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features)</span><span class="sxs-lookup"><span data-stu-id="adb83-131">These fields match the 'windowFeatures' passed to window.open as specified in [https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features](https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features)</span></span>

## <span data-ttu-id="adb83-132">Members</span><span class="sxs-lookup"><span data-stu-id="adb83-132">Members</span></span>

#### <span data-ttu-id="adb83-133">get_Height</span><span class="sxs-lookup"><span data-stu-id="adb83-133">get_Height</span></span> 

<span data-ttu-id="adb83-134">ウィンドウの高さ。</span><span class="sxs-lookup"><span data-stu-id="adb83-134">The height of the window.</span></span>

> <span data-ttu-id="adb83-135">パブリック HRESULT [get_Height](#get_height)(UINT32 \* Height)</span><span class="sxs-lookup"><span data-stu-id="adb83-135">public HRESULT [get_Height](#get_height)(UINT32 \* height)</span></span>

<span data-ttu-id="adb83-136">最小値は100です。</span><span class="sxs-lookup"><span data-stu-id="adb83-136">Minimum value is 100.</span></span> <span data-ttu-id="adb83-137">HasSize が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="adb83-137">Will fail if HasSize is false.</span></span>

#### <span data-ttu-id="adb83-138">get_Left</span><span class="sxs-lookup"><span data-stu-id="adb83-138">get_Left</span></span> 

<span data-ttu-id="adb83-139">ウィンドウの左端。</span><span class="sxs-lookup"><span data-stu-id="adb83-139">The left position of the window.</span></span> <span data-ttu-id="adb83-140">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="adb83-140">Will fail if HasPosition is false.</span></span>

> <span data-ttu-id="adb83-141">パブリック HRESULT [get_Left](#get_left)(UINT32 \* Left)</span><span class="sxs-lookup"><span data-stu-id="adb83-141">public HRESULT [get_Left](#get_left)(UINT32 \* left)</span></span>

#### <span data-ttu-id="adb83-142">get_MenuBar</span><span class="sxs-lookup"><span data-stu-id="adb83-142">get_MenuBar</span></span> 

<span data-ttu-id="adb83-143">メニューバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="adb83-143">Whether or not to display the menu bar.</span></span>

> <span data-ttu-id="adb83-144">パブリック HRESULT [get_MenuBar](#get_menubar)(ブール \* MenuBar)</span><span class="sxs-lookup"><span data-stu-id="adb83-144">public HRESULT [get_MenuBar](#get_menubar)(BOOL \* menuBar)</span></span>

#### <span data-ttu-id="adb83-145">get_ScrollBars</span><span class="sxs-lookup"><span data-stu-id="adb83-145">get_ScrollBars</span></span> 

<span data-ttu-id="adb83-146">スクロールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="adb83-146">Whether or not to display scroll bars.</span></span>

> <span data-ttu-id="adb83-147">パブリック HRESULT [get_ScrollBars](#get_scrollbars)(ブール \* ScrollBars)</span><span class="sxs-lookup"><span data-stu-id="adb83-147">public HRESULT [get_ScrollBars](#get_scrollbars)(BOOL \* scrollBars)</span></span>

#### <span data-ttu-id="adb83-148">get_Status</span><span class="sxs-lookup"><span data-stu-id="adb83-148">get_Status</span></span> 

<span data-ttu-id="adb83-149">ステータスバーを追加するかどうか。</span><span class="sxs-lookup"><span data-stu-id="adb83-149">Whether or not to add a status bar.</span></span>

> <span data-ttu-id="adb83-150">パブリック HRESULT [get_Status](#get_status)(ブール \* 状態)</span><span class="sxs-lookup"><span data-stu-id="adb83-150">public HRESULT [get_Status](#get_status)(BOOL \* status)</span></span>

#### <span data-ttu-id="adb83-151">get_Toolbar</span><span class="sxs-lookup"><span data-stu-id="adb83-151">get_Toolbar</span></span> 

<span data-ttu-id="adb83-152">ブラウザーのツールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="adb83-152">Whether or not to display the browser toolbar.</span></span>

> <span data-ttu-id="adb83-153">パブリック HRESULT [get_Toolbar](#get_toolbar)(ブール \* ツールバー)</span><span class="sxs-lookup"><span data-stu-id="adb83-153">public HRESULT [get_Toolbar](#get_toolbar)(BOOL \* toolbar)</span></span>

#### <span data-ttu-id="adb83-154">get_Top</span><span class="sxs-lookup"><span data-stu-id="adb83-154">get_Top</span></span> 

<span data-ttu-id="adb83-155">ウィンドウの一番上の位置。</span><span class="sxs-lookup"><span data-stu-id="adb83-155">The top position of the window.</span></span> <span data-ttu-id="adb83-156">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="adb83-156">Will fail if HasPosition is false.</span></span>

> <span data-ttu-id="adb83-157">パブリック HRESULT [get_Top](#get_top)(UINT32 \* Top)</span><span class="sxs-lookup"><span data-stu-id="adb83-157">public HRESULT [get_Top](#get_top)(UINT32 \* top)</span></span>

#### <span data-ttu-id="adb83-158">get_Width</span><span class="sxs-lookup"><span data-stu-id="adb83-158">get_Width</span></span> 

<span data-ttu-id="adb83-159">ウィンドウの幅。</span><span class="sxs-lookup"><span data-stu-id="adb83-159">The width of the window.</span></span>

> <span data-ttu-id="adb83-160">パブリック HRESULT [get_Width](#get_width)(UINT32 \* Width)</span><span class="sxs-lookup"><span data-stu-id="adb83-160">public HRESULT [get_Width](#get_width)(UINT32 \* width)</span></span>

<span data-ttu-id="adb83-161">最小値は100です。</span><span class="sxs-lookup"><span data-stu-id="adb83-161">Minimum value is 100.</span></span> <span data-ttu-id="adb83-162">HasSize が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="adb83-162">Will fail if HasSize is false.</span></span>

#### <span data-ttu-id="adb83-163">HasPosition</span><span class="sxs-lookup"><span data-stu-id="adb83-163">HasPosition</span></span> 

<span data-ttu-id="adb83-164">は左と上の値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="adb83-164">Has specified left and top values.</span></span>

> <span data-ttu-id="adb83-165">パブリック HRESULT [hasposition](#hasposition)(ブール \* hasposition)</span><span class="sxs-lookup"><span data-stu-id="adb83-165">public HRESULT [HasPosition](#hasposition)(BOOL \* hasPosition)</span></span>

#### <span data-ttu-id="adb83-166">HasSize</span><span class="sxs-lookup"><span data-stu-id="adb83-166">HasSize</span></span> 

<span data-ttu-id="adb83-167">高さと幅の値を指定しました。</span><span class="sxs-lookup"><span data-stu-id="adb83-167">Has specified height and width values.</span></span>

> <span data-ttu-id="adb83-168">パブリック HRESULT [hassize](#hassize)(ブール \* hassize)</span><span class="sxs-lookup"><span data-stu-id="adb83-168">public HRESULT [HasSize](#hassize)(BOOL \* hasSize)</span></span>

