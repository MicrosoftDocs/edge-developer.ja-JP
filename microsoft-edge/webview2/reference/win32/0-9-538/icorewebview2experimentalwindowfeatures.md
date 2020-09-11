---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2ExperimentalWindowFeatures
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalWindowFeatures
ms.openlocfilehash: ee740f7d227ae98d451ba1c5e8f1017fe92514a8
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011371"
---
# <span data-ttu-id="03f7b-104">0.9.579-インターフェイス ICoreWebView2ExperimentalWindowFeatures</span><span class="sxs-lookup"><span data-stu-id="03f7b-104">0.9.579 - interface ICoreWebView2ExperimentalWindowFeatures</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalWindowFeatures
  : public IUnknown
```

<span data-ttu-id="03f7b-105">WebView ポップアップウィンドウのウィンドウ機能。</span><span class="sxs-lookup"><span data-stu-id="03f7b-105">Window features for a WebView popup window.</span></span>

## <span data-ttu-id="03f7b-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="03f7b-106">Summary</span></span>

 <span data-ttu-id="03f7b-107">Members</span><span class="sxs-lookup"><span data-stu-id="03f7b-107">Members</span></span>                        | <span data-ttu-id="03f7b-108">説明</span><span class="sxs-lookup"><span data-stu-id="03f7b-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="03f7b-109">get_Height</span><span class="sxs-lookup"><span data-stu-id="03f7b-109">get_Height</span></span>](#get_height) | <span data-ttu-id="03f7b-110">ウィンドウの高さ。</span><span class="sxs-lookup"><span data-stu-id="03f7b-110">The height of the window.</span></span>
[<span data-ttu-id="03f7b-111">get_Left</span><span class="sxs-lookup"><span data-stu-id="03f7b-111">get_Left</span></span>](#get_left) | <span data-ttu-id="03f7b-112">ウィンドウの左端。</span><span class="sxs-lookup"><span data-stu-id="03f7b-112">The left position of the window.</span></span> <span data-ttu-id="03f7b-113">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="03f7b-113">Will fail if HasPosition is false.</span></span>
[<span data-ttu-id="03f7b-114">get_MenuBar</span><span class="sxs-lookup"><span data-stu-id="03f7b-114">get_MenuBar</span></span>](#get_menubar) | <span data-ttu-id="03f7b-115">メニューバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="03f7b-115">Whether or not to display the menu bar.</span></span>
[<span data-ttu-id="03f7b-116">get_ScrollBars</span><span class="sxs-lookup"><span data-stu-id="03f7b-116">get_ScrollBars</span></span>](#get_scrollbars) | <span data-ttu-id="03f7b-117">スクロールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="03f7b-117">Whether or not to display scroll bars.</span></span>
[<span data-ttu-id="03f7b-118">get_Status</span><span class="sxs-lookup"><span data-stu-id="03f7b-118">get_Status</span></span>](#get_status) | <span data-ttu-id="03f7b-119">ステータスバーを追加するかどうか。</span><span class="sxs-lookup"><span data-stu-id="03f7b-119">Whether or not to add a status bar.</span></span>
[<span data-ttu-id="03f7b-120">get_Toolbar</span><span class="sxs-lookup"><span data-stu-id="03f7b-120">get_Toolbar</span></span>](#get_toolbar) | <span data-ttu-id="03f7b-121">ブラウザーのツールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="03f7b-121">Whether or not to display the browser toolbar.</span></span>
[<span data-ttu-id="03f7b-122">get_Top</span><span class="sxs-lookup"><span data-stu-id="03f7b-122">get_Top</span></span>](#get_top) | <span data-ttu-id="03f7b-123">ウィンドウの一番上の位置。</span><span class="sxs-lookup"><span data-stu-id="03f7b-123">The top position of the window.</span></span> <span data-ttu-id="03f7b-124">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="03f7b-124">Will fail if HasPosition is false.</span></span>
[<span data-ttu-id="03f7b-125">get_Width</span><span class="sxs-lookup"><span data-stu-id="03f7b-125">get_Width</span></span>](#get_width) | <span data-ttu-id="03f7b-126">ウィンドウの幅。</span><span class="sxs-lookup"><span data-stu-id="03f7b-126">The width of the window.</span></span>
[<span data-ttu-id="03f7b-127">HasPosition</span><span class="sxs-lookup"><span data-stu-id="03f7b-127">HasPosition</span></span>](#hasposition) | <span data-ttu-id="03f7b-128">は左と上の値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="03f7b-128">Has specified left and top values.</span></span>
[<span data-ttu-id="03f7b-129">HasSize</span><span class="sxs-lookup"><span data-stu-id="03f7b-129">HasSize</span></span>](#hassize) | <span data-ttu-id="03f7b-130">高さと幅の値を指定しました。</span><span class="sxs-lookup"><span data-stu-id="03f7b-130">Has specified height and width values.</span></span>

<span data-ttu-id="03f7b-131">これらのフィールドは、次のように指定されているときに、window に渡された "windowFeatures" と一致します。 [https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features](https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features)</span><span class="sxs-lookup"><span data-stu-id="03f7b-131">These fields match the 'windowFeatures' passed to window.open as specified in [https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features](https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features)</span></span>

## <span data-ttu-id="03f7b-132">Members</span><span class="sxs-lookup"><span data-stu-id="03f7b-132">Members</span></span>

#### <span data-ttu-id="03f7b-133">get_Height</span><span class="sxs-lookup"><span data-stu-id="03f7b-133">get_Height</span></span> 

<span data-ttu-id="03f7b-134">ウィンドウの高さ。</span><span class="sxs-lookup"><span data-stu-id="03f7b-134">The height of the window.</span></span>

> <span data-ttu-id="03f7b-135">パブリック HRESULT [get_Height](#get_height)(UINT32 \* Height)</span><span class="sxs-lookup"><span data-stu-id="03f7b-135">public HRESULT [get_Height](#get_height)(UINT32 \* height)</span></span>

<span data-ttu-id="03f7b-136">最小値は100です。</span><span class="sxs-lookup"><span data-stu-id="03f7b-136">Minimum value is 100.</span></span> <span data-ttu-id="03f7b-137">HasSize が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="03f7b-137">Will fail if HasSize is false.</span></span>

#### <span data-ttu-id="03f7b-138">get_Left</span><span class="sxs-lookup"><span data-stu-id="03f7b-138">get_Left</span></span> 

<span data-ttu-id="03f7b-139">ウィンドウの左端。</span><span class="sxs-lookup"><span data-stu-id="03f7b-139">The left position of the window.</span></span> <span data-ttu-id="03f7b-140">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="03f7b-140">Will fail if HasPosition is false.</span></span>

> <span data-ttu-id="03f7b-141">パブリック HRESULT [get_Left](#get_left)(UINT32 \* Left)</span><span class="sxs-lookup"><span data-stu-id="03f7b-141">public HRESULT [get_Left](#get_left)(UINT32 \* left)</span></span>

#### <span data-ttu-id="03f7b-142">get_MenuBar</span><span class="sxs-lookup"><span data-stu-id="03f7b-142">get_MenuBar</span></span> 

<span data-ttu-id="03f7b-143">メニューバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="03f7b-143">Whether or not to display the menu bar.</span></span>

> <span data-ttu-id="03f7b-144">パブリック HRESULT [get_MenuBar](#get_menubar)(ブール \* MenuBar)</span><span class="sxs-lookup"><span data-stu-id="03f7b-144">public HRESULT [get_MenuBar](#get_menubar)(BOOL \* menuBar)</span></span>

#### <span data-ttu-id="03f7b-145">get_ScrollBars</span><span class="sxs-lookup"><span data-stu-id="03f7b-145">get_ScrollBars</span></span> 

<span data-ttu-id="03f7b-146">スクロールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="03f7b-146">Whether or not to display scroll bars.</span></span>

> <span data-ttu-id="03f7b-147">パブリック HRESULT [get_ScrollBars](#get_scrollbars)(ブール \* ScrollBars)</span><span class="sxs-lookup"><span data-stu-id="03f7b-147">public HRESULT [get_ScrollBars](#get_scrollbars)(BOOL \* scrollBars)</span></span>

#### <span data-ttu-id="03f7b-148">get_Status</span><span class="sxs-lookup"><span data-stu-id="03f7b-148">get_Status</span></span> 

<span data-ttu-id="03f7b-149">ステータスバーを追加するかどうか。</span><span class="sxs-lookup"><span data-stu-id="03f7b-149">Whether or not to add a status bar.</span></span>

> <span data-ttu-id="03f7b-150">パブリック HRESULT [get_Status](#get_status)(ブール \* 状態)</span><span class="sxs-lookup"><span data-stu-id="03f7b-150">public HRESULT [get_Status](#get_status)(BOOL \* status)</span></span>

#### <span data-ttu-id="03f7b-151">get_Toolbar</span><span class="sxs-lookup"><span data-stu-id="03f7b-151">get_Toolbar</span></span> 

<span data-ttu-id="03f7b-152">ブラウザーのツールバーを表示するかどうか。</span><span class="sxs-lookup"><span data-stu-id="03f7b-152">Whether or not to display the browser toolbar.</span></span>

> <span data-ttu-id="03f7b-153">パブリック HRESULT [get_Toolbar](#get_toolbar)(ブール \* ツールバー)</span><span class="sxs-lookup"><span data-stu-id="03f7b-153">public HRESULT [get_Toolbar](#get_toolbar)(BOOL \* toolbar)</span></span>

#### <span data-ttu-id="03f7b-154">get_Top</span><span class="sxs-lookup"><span data-stu-id="03f7b-154">get_Top</span></span> 

<span data-ttu-id="03f7b-155">ウィンドウの一番上の位置。</span><span class="sxs-lookup"><span data-stu-id="03f7b-155">The top position of the window.</span></span> <span data-ttu-id="03f7b-156">HasPosition が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="03f7b-156">Will fail if HasPosition is false.</span></span>

> <span data-ttu-id="03f7b-157">パブリック HRESULT [get_Top](#get_top)(UINT32 \* Top)</span><span class="sxs-lookup"><span data-stu-id="03f7b-157">public HRESULT [get_Top](#get_top)(UINT32 \* top)</span></span>

#### <span data-ttu-id="03f7b-158">get_Width</span><span class="sxs-lookup"><span data-stu-id="03f7b-158">get_Width</span></span> 

<span data-ttu-id="03f7b-159">ウィンドウの幅。</span><span class="sxs-lookup"><span data-stu-id="03f7b-159">The width of the window.</span></span>

> <span data-ttu-id="03f7b-160">パブリック HRESULT [get_Width](#get_width)(UINT32 \* Width)</span><span class="sxs-lookup"><span data-stu-id="03f7b-160">public HRESULT [get_Width](#get_width)(UINT32 \* width)</span></span>

<span data-ttu-id="03f7b-161">最小値は100です。</span><span class="sxs-lookup"><span data-stu-id="03f7b-161">Minimum value is 100.</span></span> <span data-ttu-id="03f7b-162">HasSize が false の場合は、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="03f7b-162">Will fail if HasSize is false.</span></span>

#### <span data-ttu-id="03f7b-163">HasPosition</span><span class="sxs-lookup"><span data-stu-id="03f7b-163">HasPosition</span></span> 

<span data-ttu-id="03f7b-164">は左と上の値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="03f7b-164">Has specified left and top values.</span></span>

> <span data-ttu-id="03f7b-165">パブリック HRESULT [hasposition](#hasposition)(ブール \* hasposition)</span><span class="sxs-lookup"><span data-stu-id="03f7b-165">public HRESULT [HasPosition](#hasposition)(BOOL \* hasPosition)</span></span>

#### <span data-ttu-id="03f7b-166">HasSize</span><span class="sxs-lookup"><span data-stu-id="03f7b-166">HasSize</span></span> 

<span data-ttu-id="03f7b-167">高さと幅の値を指定しました。</span><span class="sxs-lookup"><span data-stu-id="03f7b-167">Has specified height and width values.</span></span>

> <span data-ttu-id="03f7b-168">パブリック HRESULT [hassize](#hassize)(ブール \* hassize)</span><span class="sxs-lookup"><span data-stu-id="03f7b-168">public HRESULT [HasSize](#hassize)(BOOL \* hasSize)</span></span>

