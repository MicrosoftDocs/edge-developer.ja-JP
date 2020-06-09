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
ms.openlocfilehash: e8563bdd77972945a1e4b81662071d07d1efeb02
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698981"
---
# <span data-ttu-id="df999-104">CoreWebView2Matrix4x4 構造体 (WebView2)</span><span class="sxs-lookup"><span data-stu-id="df999-104">Microsoft.Web.WebView2.Core.CoreWebView2Matrix4x4 struct</span></span> 

> [!NOTE]
> <span data-ttu-id="df999-105">これは、SDK バージョン[0.9.538-プレリリース](../../../releasenotes.md#09538)で出荷される[実験的な API](../../../concepts/versioning.md#experimental-apis)です。</span><span class="sxs-lookup"><span data-stu-id="df999-105">This is an [experimental API](../../../concepts/versioning.md#experimental-apis) that shipped with our SDK version [0.9.538-prerelease](../../../releasenotes.md#09538).</span></span>

<span data-ttu-id="df999-106">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="df999-106">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="df999-107">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="df999-107">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="df999-108">この変換は、CreateCoreWebView2PointerInfoFromPointerId を呼び出したときに適切な座標を計算するために使われます。</span><span class="sxs-lookup"><span data-stu-id="df999-108">This transform is used to calculate correct coordinates when calling CreateCoreWebView2PointerInfoFromPointerId.</span></span>

## <span data-ttu-id="df999-109">まとめ</span><span class="sxs-lookup"><span data-stu-id="df999-109">Summary</span></span>

 <span data-ttu-id="df999-110">Members</span><span class="sxs-lookup"><span data-stu-id="df999-110">Members</span></span>                        | <span data-ttu-id="df999-111">説明</span><span class="sxs-lookup"><span data-stu-id="df999-111">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="df999-112">_11</span><span class="sxs-lookup"><span data-stu-id="df999-112">_11</span></span>](#_11) | <span data-ttu-id="df999-113">マトリックスの最初の行と最初の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-113">The value in the first row and first column of the matrix.</span></span>
[<span data-ttu-id="df999-114">_12</span><span class="sxs-lookup"><span data-stu-id="df999-114">_12</span></span>](#_12) | <span data-ttu-id="df999-115">マトリックスの最初の行と2番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-115">The value in the first row and second column of the matrix.</span></span>
[<span data-ttu-id="df999-116">_13</span><span class="sxs-lookup"><span data-stu-id="df999-116">_13</span></span>](#_13) | <span data-ttu-id="df999-117">マトリックスの最初の行と3番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-117">The value in the first row and third column of the matrix.</span></span>
[<span data-ttu-id="df999-118">_ 14</span><span class="sxs-lookup"><span data-stu-id="df999-118">_14</span></span>](#_14) | <span data-ttu-id="df999-119">マトリックスの最初の行と4番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-119">The value in the first row and fourth column of the matrix.</span></span>
[<span data-ttu-id="df999-120">_ 21</span><span class="sxs-lookup"><span data-stu-id="df999-120">_21</span></span>](#_21) | <span data-ttu-id="df999-121">マトリックスの2番目の行と最初の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-121">The value in the second row and first column of the matrix.</span></span>
[<span data-ttu-id="df999-122">_ 22</span><span class="sxs-lookup"><span data-stu-id="df999-122">_22</span></span>](#_22) | <span data-ttu-id="df999-123">マトリックスの2番目の行と2番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-123">The value in the second row and second column of the matrix.</span></span>
[<span data-ttu-id="df999-124">_ 23</span><span class="sxs-lookup"><span data-stu-id="df999-124">_23</span></span>](#_23) | <span data-ttu-id="df999-125">マトリックスの2行目と3列目の値。</span><span class="sxs-lookup"><span data-stu-id="df999-125">The value in the second row and third column of the matrix.</span></span>
[<span data-ttu-id="df999-126">_ 24</span><span class="sxs-lookup"><span data-stu-id="df999-126">_24</span></span>](#_24) | <span data-ttu-id="df999-127">マトリックスの2番目の行と4番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-127">The value in the second row and fourth column of the matrix.</span></span>
[<span data-ttu-id="df999-128">_ 31</span><span class="sxs-lookup"><span data-stu-id="df999-128">_31</span></span>](#_31) | <span data-ttu-id="df999-129">マトリックスの3番目の行と最初の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-129">The value in the third row and first column of the matrix.</span></span>
[<span data-ttu-id="df999-130">_ 32</span><span class="sxs-lookup"><span data-stu-id="df999-130">_32</span></span>](#_32) | <span data-ttu-id="df999-131">マトリックスの3番目の行と2番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-131">The value in the third row and second column of the matrix.</span></span>
[<span data-ttu-id="df999-132">_ 33</span><span class="sxs-lookup"><span data-stu-id="df999-132">_33</span></span>](#_33) | <span data-ttu-id="df999-133">マトリックスの3番目の行と3番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-133">The value in the third row and third column of the matrix.</span></span>
[<span data-ttu-id="df999-134">_ 34</span><span class="sxs-lookup"><span data-stu-id="df999-134">_34</span></span>](#_34) | <span data-ttu-id="df999-135">マトリックスの3行目と4列目の値。</span><span class="sxs-lookup"><span data-stu-id="df999-135">The value in the third row and fourth column of the matrix.</span></span>
[<span data-ttu-id="df999-136">_ 41</span><span class="sxs-lookup"><span data-stu-id="df999-136">_41</span></span>](#_41) | <span data-ttu-id="df999-137">マトリックスの4行目と1列目の値。</span><span class="sxs-lookup"><span data-stu-id="df999-137">The value in the fourth row and first column of the matrix.</span></span>
[<span data-ttu-id="df999-138">_ 42</span><span class="sxs-lookup"><span data-stu-id="df999-138">_42</span></span>](#_42) | <span data-ttu-id="df999-139">マトリックスの4番目の行と2番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-139">The value in the fourth row and second column of the matrix.</span></span>
[<span data-ttu-id="df999-140">_ 43</span><span class="sxs-lookup"><span data-stu-id="df999-140">_43</span></span>](#_43) | <span data-ttu-id="df999-141">マトリックスの4行目と3列目の値。</span><span class="sxs-lookup"><span data-stu-id="df999-141">The value in the fourth row and third column of the matrix.</span></span>
[<span data-ttu-id="df999-142">_ 44</span><span class="sxs-lookup"><span data-stu-id="df999-142">_44</span></span>](#_44) | <span data-ttu-id="df999-143">マトリックスの4番目の行と4番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-143">The value in the fourth row and fourth column of the matrix.</span></span>

<span data-ttu-id="df999-144">これは D2D1_MATRIX_4X4_F と同じです。</span><span class="sxs-lookup"><span data-stu-id="df999-144">This is equivalent to a D2D1_MATRIX_4X4_F.</span></span>

## <span data-ttu-id="df999-145">Members</span><span class="sxs-lookup"><span data-stu-id="df999-145">Members</span></span>

#### <span data-ttu-id="df999-146">_11</span><span class="sxs-lookup"><span data-stu-id="df999-146">_11</span></span> 

<span data-ttu-id="df999-147">マトリックスの最初の行と最初の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-147">The value in the first row and first column of the matrix.</span></span>

> <span data-ttu-id="df999-148">パブリックシングル[_11](#_11)</span><span class="sxs-lookup"><span data-stu-id="df999-148">public Single [_11](#_11)</span></span>

#### <span data-ttu-id="df999-149">_12</span><span class="sxs-lookup"><span data-stu-id="df999-149">_12</span></span> 

<span data-ttu-id="df999-150">マトリックスの最初の行と2番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-150">The value in the first row and second column of the matrix.</span></span>

> <span data-ttu-id="df999-151">パブリックシングル[_12](#_12)</span><span class="sxs-lookup"><span data-stu-id="df999-151">public Single [_12](#_12)</span></span>

#### <span data-ttu-id="df999-152">_13</span><span class="sxs-lookup"><span data-stu-id="df999-152">_13</span></span> 

<span data-ttu-id="df999-153">マトリックスの最初の行と3番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-153">The value in the first row and third column of the matrix.</span></span>

> <span data-ttu-id="df999-154">パブリックシングル[_13](#_13)</span><span class="sxs-lookup"><span data-stu-id="df999-154">public Single [_13](#_13)</span></span>

#### <span data-ttu-id="df999-155">_ 14</span><span class="sxs-lookup"><span data-stu-id="df999-155">_14</span></span> 

<span data-ttu-id="df999-156">マトリックスの最初の行と4番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-156">The value in the first row and fourth column of the matrix.</span></span>

> <span data-ttu-id="df999-157">パブリック (1 つ[)](#_14)</span><span class="sxs-lookup"><span data-stu-id="df999-157">public Single [_14](#_14)</span></span>

#### <span data-ttu-id="df999-158">_ 21</span><span class="sxs-lookup"><span data-stu-id="df999-158">_21</span></span> 

<span data-ttu-id="df999-159">マトリックスの2番目の行と最初の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-159">The value in the second row and first column of the matrix.</span></span>

> <span data-ttu-id="df999-160">公開 (1 つ[)](#_21)</span><span class="sxs-lookup"><span data-stu-id="df999-160">public Single [_21](#_21)</span></span>

#### <span data-ttu-id="df999-161">_ 22</span><span class="sxs-lookup"><span data-stu-id="df999-161">_22</span></span> 

<span data-ttu-id="df999-162">マトリックスの2番目の行と2番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-162">The value in the second row and second column of the matrix.</span></span>

> <span data-ttu-id="df999-163">公開 (1 つ[)](#_22)</span><span class="sxs-lookup"><span data-stu-id="df999-163">public Single [_22](#_22)</span></span>

#### <span data-ttu-id="df999-164">_ 23</span><span class="sxs-lookup"><span data-stu-id="df999-164">_23</span></span> 

<span data-ttu-id="df999-165">マトリックスの2行目と3列目の値。</span><span class="sxs-lookup"><span data-stu-id="df999-165">The value in the second row and third column of the matrix.</span></span>

> <span data-ttu-id="df999-166">パブリック (1 つ[)](#_23)</span><span class="sxs-lookup"><span data-stu-id="df999-166">public Single [_23](#_23)</span></span>

#### <span data-ttu-id="df999-167">_ 24</span><span class="sxs-lookup"><span data-stu-id="df999-167">_24</span></span> 

<span data-ttu-id="df999-168">マトリックスの2番目の行と4番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-168">The value in the second row and fourth column of the matrix.</span></span>

> <span data-ttu-id="df999-169">パブリック1つの[24](#_24)</span><span class="sxs-lookup"><span data-stu-id="df999-169">public Single [_24](#_24)</span></span>

#### <span data-ttu-id="df999-170">_ 31</span><span class="sxs-lookup"><span data-stu-id="df999-170">_31</span></span> 

<span data-ttu-id="df999-171">マトリックスの3番目の行と最初の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-171">The value in the third row and first column of the matrix.</span></span>

> <span data-ttu-id="df999-172">公開 (1 つ[)](#_31)</span><span class="sxs-lookup"><span data-stu-id="df999-172">public Single [_31](#_31)</span></span>

#### <span data-ttu-id="df999-173">_ 32</span><span class="sxs-lookup"><span data-stu-id="df999-173">_32</span></span> 

<span data-ttu-id="df999-174">マトリックスの3番目の行と2番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-174">The value in the third row and second column of the matrix.</span></span>

> <span data-ttu-id="df999-175">パブリック1つの[32](#_32)</span><span class="sxs-lookup"><span data-stu-id="df999-175">public Single [_32](#_32)</span></span>

#### <span data-ttu-id="df999-176">_ 33</span><span class="sxs-lookup"><span data-stu-id="df999-176">_33</span></span> 

<span data-ttu-id="df999-177">マトリックスの3番目の行と3番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-177">The value in the third row and third column of the matrix.</span></span>

> <span data-ttu-id="df999-178">パブリック1つの[33](#_33)</span><span class="sxs-lookup"><span data-stu-id="df999-178">public Single [_33](#_33)</span></span>

#### <span data-ttu-id="df999-179">_ 34</span><span class="sxs-lookup"><span data-stu-id="df999-179">_34</span></span> 

<span data-ttu-id="df999-180">マトリックスの3行目と4列目の値。</span><span class="sxs-lookup"><span data-stu-id="df999-180">The value in the third row and fourth column of the matrix.</span></span>

> <span data-ttu-id="df999-181">公開[(1) 34](#_34)</span><span class="sxs-lookup"><span data-stu-id="df999-181">public Single [_34](#_34)</span></span>

#### <span data-ttu-id="df999-182">_ 41</span><span class="sxs-lookup"><span data-stu-id="df999-182">_41</span></span> 

<span data-ttu-id="df999-183">マトリックスの4行目と1列目の値。</span><span class="sxs-lookup"><span data-stu-id="df999-183">The value in the fourth row and first column of the matrix.</span></span>

> <span data-ttu-id="df999-184">パブリック単一の[41](#_41)</span><span class="sxs-lookup"><span data-stu-id="df999-184">public Single [_41](#_41)</span></span>

#### <span data-ttu-id="df999-185">_ 42</span><span class="sxs-lookup"><span data-stu-id="df999-185">_42</span></span> 

<span data-ttu-id="df999-186">マトリックスの4番目の行と2番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-186">The value in the fourth row and second column of the matrix.</span></span>

> <span data-ttu-id="df999-187">パブリックの1つの[_](#_42)</span><span class="sxs-lookup"><span data-stu-id="df999-187">public Single [_42](#_42)</span></span>

#### <span data-ttu-id="df999-188">_ 43</span><span class="sxs-lookup"><span data-stu-id="df999-188">_43</span></span> 

<span data-ttu-id="df999-189">マトリックスの4行目と3列目の値。</span><span class="sxs-lookup"><span data-stu-id="df999-189">The value in the fourth row and third column of the matrix.</span></span>

> <span data-ttu-id="df999-190">公開 1[回](#_43)</span><span class="sxs-lookup"><span data-stu-id="df999-190">public Single [_43](#_43)</span></span>

#### <span data-ttu-id="df999-191">_ 44</span><span class="sxs-lookup"><span data-stu-id="df999-191">_44</span></span> 

<span data-ttu-id="df999-192">マトリックスの4番目の行と4番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="df999-192">The value in the fourth row and fourth column of the matrix.</span></span>

> <span data-ttu-id="df999-193">パブリックシングル[44](#_44)</span><span class="sxs-lookup"><span data-stu-id="df999-193">public Single [_44](#_44)</span></span>

