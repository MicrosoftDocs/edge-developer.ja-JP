---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2Matrix4x4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2Matrix4x4。
ms.openlocfilehash: e8048bd51d717904ce2d220eb63db8de5d155885
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012213"
---
# <span data-ttu-id="6aa32-104">CoreWebView2Matrix4x4 構造体 (WebView2)</span><span class="sxs-lookup"><span data-stu-id="6aa32-104">Microsoft.Web.WebView2.Core.CoreWebView2Matrix4x4 struct</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="6aa32-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="6aa32-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="6aa32-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="6aa32-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="6aa32-107">この変換は、CreateCoreWebView2PointerInfoFromPointerId を呼び出したときに適切な座標を計算するために使われます。</span><span class="sxs-lookup"><span data-stu-id="6aa32-107">This transform is used to calculate correct coordinates when calling CreateCoreWebView2PointerInfoFromPointerId.</span></span>

## <span data-ttu-id="6aa32-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="6aa32-108">Summary</span></span>

 <span data-ttu-id="6aa32-109">Members</span><span class="sxs-lookup"><span data-stu-id="6aa32-109">Members</span></span>                        | <span data-ttu-id="6aa32-110">説明</span><span class="sxs-lookup"><span data-stu-id="6aa32-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6aa32-111">_11</span><span class="sxs-lookup"><span data-stu-id="6aa32-111">_11</span></span>](#_11) | <span data-ttu-id="6aa32-112">マトリックスの最初の行と最初の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-112">The value in the first row and first column of the matrix.</span></span>
[<span data-ttu-id="6aa32-113">_12</span><span class="sxs-lookup"><span data-stu-id="6aa32-113">_12</span></span>](#_12) | <span data-ttu-id="6aa32-114">マトリックスの最初の行と2番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-114">The value in the first row and second column of the matrix.</span></span>
[<span data-ttu-id="6aa32-115">_13</span><span class="sxs-lookup"><span data-stu-id="6aa32-115">_13</span></span>](#_13) | <span data-ttu-id="6aa32-116">マトリックスの最初の行と3番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-116">The value in the first row and third column of the matrix.</span></span>
[<span data-ttu-id="6aa32-117">_ 14</span><span class="sxs-lookup"><span data-stu-id="6aa32-117">_14</span></span>](#_14) | <span data-ttu-id="6aa32-118">マトリックスの最初の行と4番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-118">The value in the first row and fourth column of the matrix.</span></span>
[<span data-ttu-id="6aa32-119">_ 21</span><span class="sxs-lookup"><span data-stu-id="6aa32-119">_21</span></span>](#_21) | <span data-ttu-id="6aa32-120">マトリックスの2番目の行と最初の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-120">The value in the second row and first column of the matrix.</span></span>
[<span data-ttu-id="6aa32-121">_ 22</span><span class="sxs-lookup"><span data-stu-id="6aa32-121">_22</span></span>](#_22) | <span data-ttu-id="6aa32-122">マトリックスの2番目の行と2番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-122">The value in the second row and second column of the matrix.</span></span>
[<span data-ttu-id="6aa32-123">_ 23</span><span class="sxs-lookup"><span data-stu-id="6aa32-123">_23</span></span>](#_23) | <span data-ttu-id="6aa32-124">マトリックスの2行目と3列目の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-124">The value in the second row and third column of the matrix.</span></span>
[<span data-ttu-id="6aa32-125">_ 24</span><span class="sxs-lookup"><span data-stu-id="6aa32-125">_24</span></span>](#_24) | <span data-ttu-id="6aa32-126">マトリックスの2番目の行と4番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-126">The value in the second row and fourth column of the matrix.</span></span>
[<span data-ttu-id="6aa32-127">_ 31</span><span class="sxs-lookup"><span data-stu-id="6aa32-127">_31</span></span>](#_31) | <span data-ttu-id="6aa32-128">マトリックスの3番目の行と最初の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-128">The value in the third row and first column of the matrix.</span></span>
[<span data-ttu-id="6aa32-129">_ 32</span><span class="sxs-lookup"><span data-stu-id="6aa32-129">_32</span></span>](#_32) | <span data-ttu-id="6aa32-130">マトリックスの3番目の行と2番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-130">The value in the third row and second column of the matrix.</span></span>
[<span data-ttu-id="6aa32-131">_ 33</span><span class="sxs-lookup"><span data-stu-id="6aa32-131">_33</span></span>](#_33) | <span data-ttu-id="6aa32-132">マトリックスの3番目の行と3番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-132">The value in the third row and third column of the matrix.</span></span>
[<span data-ttu-id="6aa32-133">_ 34</span><span class="sxs-lookup"><span data-stu-id="6aa32-133">_34</span></span>](#_34) | <span data-ttu-id="6aa32-134">マトリックスの3行目と4列目の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-134">The value in the third row and fourth column of the matrix.</span></span>
[<span data-ttu-id="6aa32-135">_ 41</span><span class="sxs-lookup"><span data-stu-id="6aa32-135">_41</span></span>](#_41) | <span data-ttu-id="6aa32-136">マトリックスの4行目と1列目の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-136">The value in the fourth row and first column of the matrix.</span></span>
[<span data-ttu-id="6aa32-137">_ 42</span><span class="sxs-lookup"><span data-stu-id="6aa32-137">_42</span></span>](#_42) | <span data-ttu-id="6aa32-138">マトリックスの4番目の行と2番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-138">The value in the fourth row and second column of the matrix.</span></span>
[<span data-ttu-id="6aa32-139">_ 43</span><span class="sxs-lookup"><span data-stu-id="6aa32-139">_43</span></span>](#_43) | <span data-ttu-id="6aa32-140">マトリックスの4行目と3列目の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-140">The value in the fourth row and third column of the matrix.</span></span>
[<span data-ttu-id="6aa32-141">_ 44</span><span class="sxs-lookup"><span data-stu-id="6aa32-141">_44</span></span>](#_44) | <span data-ttu-id="6aa32-142">マトリックスの4番目の行と4番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-142">The value in the fourth row and fourth column of the matrix.</span></span>

<span data-ttu-id="6aa32-143">これは D2D1_MATRIX_4X4_F と同じです。</span><span class="sxs-lookup"><span data-stu-id="6aa32-143">This is equivalent to a D2D1_MATRIX_4X4_F.</span></span>

## <span data-ttu-id="6aa32-144">Members</span><span class="sxs-lookup"><span data-stu-id="6aa32-144">Members</span></span>

#### <span data-ttu-id="6aa32-145">_11</span><span class="sxs-lookup"><span data-stu-id="6aa32-145">_11</span></span> 

<span data-ttu-id="6aa32-146">マトリックスの最初の行と最初の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-146">The value in the first row and first column of the matrix.</span></span>

> <span data-ttu-id="6aa32-147">パブリックシングル [_11](#_11)</span><span class="sxs-lookup"><span data-stu-id="6aa32-147">public Single [_11](#_11)</span></span>

#### <span data-ttu-id="6aa32-148">_12</span><span class="sxs-lookup"><span data-stu-id="6aa32-148">_12</span></span> 

<span data-ttu-id="6aa32-149">マトリックスの最初の行と2番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-149">The value in the first row and second column of the matrix.</span></span>

> <span data-ttu-id="6aa32-150">パブリックシングル [_12](#_12)</span><span class="sxs-lookup"><span data-stu-id="6aa32-150">public Single [_12](#_12)</span></span>

#### <span data-ttu-id="6aa32-151">_13</span><span class="sxs-lookup"><span data-stu-id="6aa32-151">_13</span></span> 

<span data-ttu-id="6aa32-152">マトリックスの最初の行と3番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-152">The value in the first row and third column of the matrix.</span></span>

> <span data-ttu-id="6aa32-153">パブリックシングル [_13](#_13)</span><span class="sxs-lookup"><span data-stu-id="6aa32-153">public Single [_13](#_13)</span></span>

#### <span data-ttu-id="6aa32-154">_ 14</span><span class="sxs-lookup"><span data-stu-id="6aa32-154">_14</span></span> 

<span data-ttu-id="6aa32-155">マトリックスの最初の行と4番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-155">The value in the first row and fourth column of the matrix.</span></span>

> <span data-ttu-id="6aa32-156">パブリック (1 つ [)](#_14)</span><span class="sxs-lookup"><span data-stu-id="6aa32-156">public Single [_14](#_14)</span></span>

#### <span data-ttu-id="6aa32-157">_ 21</span><span class="sxs-lookup"><span data-stu-id="6aa32-157">_21</span></span> 

<span data-ttu-id="6aa32-158">マトリックスの2番目の行と最初の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-158">The value in the second row and first column of the matrix.</span></span>

> <span data-ttu-id="6aa32-159">公開 (1 つ [)](#_21)</span><span class="sxs-lookup"><span data-stu-id="6aa32-159">public Single [_21](#_21)</span></span>

#### <span data-ttu-id="6aa32-160">_ 22</span><span class="sxs-lookup"><span data-stu-id="6aa32-160">_22</span></span> 

<span data-ttu-id="6aa32-161">マトリックスの2番目の行と2番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-161">The value in the second row and second column of the matrix.</span></span>

> <span data-ttu-id="6aa32-162">公開 (1 つ [)](#_22)</span><span class="sxs-lookup"><span data-stu-id="6aa32-162">public Single [_22](#_22)</span></span>

#### <span data-ttu-id="6aa32-163">_ 23</span><span class="sxs-lookup"><span data-stu-id="6aa32-163">_23</span></span> 

<span data-ttu-id="6aa32-164">マトリックスの2行目と3列目の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-164">The value in the second row and third column of the matrix.</span></span>

> <span data-ttu-id="6aa32-165">パブリック (1 つ [)](#_23)</span><span class="sxs-lookup"><span data-stu-id="6aa32-165">public Single [_23](#_23)</span></span>

#### <span data-ttu-id="6aa32-166">_ 24</span><span class="sxs-lookup"><span data-stu-id="6aa32-166">_24</span></span> 

<span data-ttu-id="6aa32-167">マトリックスの2番目の行と4番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-167">The value in the second row and fourth column of the matrix.</span></span>

> <span data-ttu-id="6aa32-168">パブリック1つの [24](#_24)</span><span class="sxs-lookup"><span data-stu-id="6aa32-168">public Single [_24](#_24)</span></span>

#### <span data-ttu-id="6aa32-169">_ 31</span><span class="sxs-lookup"><span data-stu-id="6aa32-169">_31</span></span> 

<span data-ttu-id="6aa32-170">マトリックスの3番目の行と最初の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-170">The value in the third row and first column of the matrix.</span></span>

> <span data-ttu-id="6aa32-171">公開 (1 つ [)](#_31)</span><span class="sxs-lookup"><span data-stu-id="6aa32-171">public Single [_31](#_31)</span></span>

#### <span data-ttu-id="6aa32-172">_ 32</span><span class="sxs-lookup"><span data-stu-id="6aa32-172">_32</span></span> 

<span data-ttu-id="6aa32-173">マトリックスの3番目の行と2番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-173">The value in the third row and second column of the matrix.</span></span>

> <span data-ttu-id="6aa32-174">パブリック1つの [32](#_32)</span><span class="sxs-lookup"><span data-stu-id="6aa32-174">public Single [_32](#_32)</span></span>

#### <span data-ttu-id="6aa32-175">_ 33</span><span class="sxs-lookup"><span data-stu-id="6aa32-175">_33</span></span> 

<span data-ttu-id="6aa32-176">マトリックスの3番目の行と3番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-176">The value in the third row and third column of the matrix.</span></span>

> <span data-ttu-id="6aa32-177">パブリック1つの [33](#_33)</span><span class="sxs-lookup"><span data-stu-id="6aa32-177">public Single [_33](#_33)</span></span>

#### <span data-ttu-id="6aa32-178">_ 34</span><span class="sxs-lookup"><span data-stu-id="6aa32-178">_34</span></span> 

<span data-ttu-id="6aa32-179">マトリックスの3行目と4列目の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-179">The value in the third row and fourth column of the matrix.</span></span>

> <span data-ttu-id="6aa32-180">公開 [(1) 34](#_34)</span><span class="sxs-lookup"><span data-stu-id="6aa32-180">public Single [_34](#_34)</span></span>

#### <span data-ttu-id="6aa32-181">_ 41</span><span class="sxs-lookup"><span data-stu-id="6aa32-181">_41</span></span> 

<span data-ttu-id="6aa32-182">マトリックスの4行目と1列目の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-182">The value in the fourth row and first column of the matrix.</span></span>

> <span data-ttu-id="6aa32-183">パブリック単一の [41](#_41)</span><span class="sxs-lookup"><span data-stu-id="6aa32-183">public Single [_41](#_41)</span></span>

#### <span data-ttu-id="6aa32-184">_ 42</span><span class="sxs-lookup"><span data-stu-id="6aa32-184">_42</span></span> 

<span data-ttu-id="6aa32-185">マトリックスの4番目の行と2番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-185">The value in the fourth row and second column of the matrix.</span></span>

> <span data-ttu-id="6aa32-186">パブリックの1つの [_](#_42)</span><span class="sxs-lookup"><span data-stu-id="6aa32-186">public Single [_42](#_42)</span></span>

#### <span data-ttu-id="6aa32-187">_ 43</span><span class="sxs-lookup"><span data-stu-id="6aa32-187">_43</span></span> 

<span data-ttu-id="6aa32-188">マトリックスの4行目と3列目の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-188">The value in the fourth row and third column of the matrix.</span></span>

> <span data-ttu-id="6aa32-189">公開 1 [回](#_43)</span><span class="sxs-lookup"><span data-stu-id="6aa32-189">public Single [_43](#_43)</span></span>

#### <span data-ttu-id="6aa32-190">_ 44</span><span class="sxs-lookup"><span data-stu-id="6aa32-190">_44</span></span> 

<span data-ttu-id="6aa32-191">マトリックスの4番目の行と4番目の列の値。</span><span class="sxs-lookup"><span data-stu-id="6aa32-191">The value in the fourth row and fourth column of the matrix.</span></span>

> <span data-ttu-id="6aa32-192">パブリックシングル [44](#_44)</span><span class="sxs-lookup"><span data-stu-id="6aa32-192">public Single [_44](#_44)</span></span>

