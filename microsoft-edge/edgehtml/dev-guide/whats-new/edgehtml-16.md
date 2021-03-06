---
description: このガイドでは、EdgeHTML 16 に含まれる開発者の機能と標準の概要を説明します。
title: EdgeHTML 16 の新機能と API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: article
ms.prod: microsoft-edge
ms.assetid: 476c4b7a-be24-434b-a051-83f19d741aaf
keywords: edge, Web 開発, html, css, javascript, developer
ms.openlocfilehash: e6ec2ec4a3152e9dfe73938784968fe3403d99cf
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399198"
---
# <a name="whats-new-in-edgehtml-16"></a><span data-ttu-id="08e69-104">EdgeHTML 16 の新機能</span><span class="sxs-lookup"><span data-stu-id="08e69-104">What's new in EdgeHTML 16</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="08e69-105">[Windows 10 Fall Creators Update \(10/2017,](https://blogs.windows.com/windowsexperience/2017/10/17/whats-new-windows-10-fall-creators-update) Build 16299\) の一部として[、EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/17) Web プラットフォームに同梱されている新機能と更新された機能の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="08e69-105">Here's a list of the new and updated features shipped in [EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/17) web platform, as part of the [Windows 10 Fall Creators Update](https://blogs.windows.com/windowsexperience/2017/10/17/whats-new-windows-10-fall-creators-update) \(10/2017, Build 16299\).</span></span>  <span data-ttu-id="08e69-106">特定の Windows Insider Preview ビルドの変更については [、「Microsoft Edge Changelog」](https://developer.microsoft.com/microsoft-edge/platform/changelog) および [「What's New in EdgeHTML」を参照してください](../whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="08e69-106">For changes in specific Windows Insider Preview builds, see the [Microsoft Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog) and [What's New in EdgeHTML](../whats-new.md).</span></span>  

<span data-ttu-id="08e69-107">次の変更の一覧の permalink を次に示します  [https://aka.ms/devguide_edgehtml_16](./edgehtml-16.md) 。</span><span class="sxs-lookup"><span data-stu-id="08e69-107">Here's the permalink for the following list of changes:  [https://aka.ms/devguide_edgehtml_16](./edgehtml-16.md).</span></span>  

## <a name="new-and-updated-features"></a><span data-ttu-id="08e69-108">新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="08e69-108">New and updated features</span></span>  

### <a name="css-grid-layout"></a><span data-ttu-id="08e69-109">CSS グリッド レイアウト</span><span class="sxs-lookup"><span data-stu-id="08e69-109">CSS Grid Layout</span></span>  

<span data-ttu-id="08e69-110">Microsoft Edge は、CSS グリッド レイアウトのプレフィックスのない [実装をサポートしています](https://www.w3.org/TR/css-grid-1)。</span><span class="sxs-lookup"><span data-stu-id="08e69-110">Microsoft Edge now supports the un-prefixed implementation of [CSS Grid Layout](https://www.w3.org/TR/css-grid-1).</span></span>  <span data-ttu-id="08e69-111">[グリッド レイアウトは](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout) 2 次元のグリッド ベースのレイアウト システムを定義し、フロートまたはスクリプトを使用した配置を使用して、レイアウトの流動性を可能にします。</span><span class="sxs-lookup"><span data-stu-id="08e69-111">[Grid Layout](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout) defines a two-dimensional grid-based layout system which enables more layout fluidity than possible with positioning using floats or scripts.</span></span>  <span data-ttu-id="08e69-112">次の例では、CSS グリッド レイアウトを使用して、基本的な Web ページの構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="08e69-112">The example below uses CSS Grid Layout to create the structure for a basic web page.</span></span>  

<iframe height='303' scrolling='no' title='<span data-ttu-id="08e69-113">CSS グリッド レイアウト</span><span class="sxs-lookup"><span data-stu-id="08e69-113">CSS Grid Layout</span></span>' src='//codepen.io/MSEdgeDev/embed/mMQqZX/?height=303&theme-id=23761&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'><span data-ttu-id="08e69-114">CodePen の <a href='https://codepen.io/MSEdgeDev/pen/mMQqZX/'> </a> MSEdgeDev によるペン CSS グリッド レイアウト ( @MSEdgeDev <a href='https://codepen.io/MSEdgeDev'> ) </a> <a href='https://codepen.io'> を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="08e69-114">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/mMQqZX/'>CSS Grid Layout</a>by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

### <a name="css-object-fit-and-object-position"></a><span data-ttu-id="08e69-115">CSS オブジェクトフィットとオブジェクト位置</span><span class="sxs-lookup"><span data-stu-id="08e69-115">CSS object-fit and object-position</span></span>  

<span data-ttu-id="08e69-116">EdgeHTML 16 では、CSS プロパティと . [`object-fit`](https://developer.mozilla.org/docs/Web/CSS/object-fit) [`object-position`](https://developer.mozilla.org/docs/Web/CSS/object-position)</span><span class="sxs-lookup"><span data-stu-id="08e69-116">EdgeHTML 16 introduces support for CSS properties [`object-fit`](https://developer.mozilla.org/docs/Web/CSS/object-fit) and [`object-position`](https://developer.mozilla.org/docs/Web/CSS/object-position).</span></span>  <span data-ttu-id="08e69-117">これらのプロパティは、コンテンツ ボックス内で置き換えられたコンテンツの位置とサイズを制御します。</span><span class="sxs-lookup"><span data-stu-id="08e69-117">These properties control the position and size of replaced content within the content box.</span></span>  

### <a name="developer-tools"></a><span data-ttu-id="08e69-118">開発者ツール</span><span class="sxs-lookup"><span data-stu-id="08e69-118">Developer Tools</span></span>  

<span data-ttu-id="08e69-119">このリリースでは、堅牢性とパフォーマンスを向上するための Microsoft Edge DevTools リファクタリングの主要な取り組みを開始し [、Windows Insider](https://insider.windows.com) ビルドで今日使い始める新機能も追加しました。</span><span class="sxs-lookup"><span data-stu-id="08e69-119">This release we started a major Microsoft Edge DevTools refactoring effort for improved robustness and performance, and also added a bunch of new features you can start using today on [Windows Insider](https://insider.windows.com) builds.</span></span>  <span data-ttu-id="08e69-120">変更された情報 [の詳細については、Microsoft Edge DevTools](../whats-new.md) ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="08e69-120">Check out the [Microsoft Edge DevTools guide](../whats-new.md) for more on what's changed!</span></span>  

### <a name="javascript"></a><span data-ttu-id="08e69-121">JavaScript</span><span class="sxs-lookup"><span data-stu-id="08e69-121">JavaScript</span></span>  

<span data-ttu-id="08e69-122">[EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/31)は、以前のリリースの Javascript パフォーマンスの最適化を基に、Chakra エンジンが関数の延期/再延期、多態インライン キャッシュの使用、ブロックによる関数の最適化を行う機能を拡張します。 `try` / `finally`</span><span class="sxs-lookup"><span data-stu-id="08e69-122">[EdgeHTML 16 builds on Javascript performance](https://blogs.windows.com/msedgedev/2017/10/31) optimizations of previous releases by expanding the Chakra engine's ability to defer/re-defer functions, use polymorphic inline caches, and optimize functions with `try`/`finally` blocks.</span></span>  

<span data-ttu-id="08e69-123">さらに、EdgeHTML 15 で最初にプレビューされた機能は、既定で安定して有効になっています。</span><span class="sxs-lookup"><span data-stu-id="08e69-123">Additionally, features first previewed in EdgeHTML 15 are now stable and enabled by default:</span></span>  

#### <a name="new-features"></a><span data-ttu-id="08e69-124">新機能</span><span class="sxs-lookup"><span data-stu-id="08e69-124">New features</span></span>  

<span data-ttu-id="08e69-125">既定でオン</span><span class="sxs-lookup"><span data-stu-id="08e69-125">On by default</span></span>  

*   <span data-ttu-id="08e69-126">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) MVP \([demo](https://webassembly.org/demo)\)</span><span class="sxs-lookup"><span data-stu-id="08e69-126">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) MVP \([demo](https://webassembly.org/demo)\)</span></span>  
*   [<span data-ttu-id="08e69-127">共有メモリとアトミック</span><span class="sxs-lookup"><span data-stu-id="08e69-127">Shared Memory and Atomics</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

### <a name="payment-request-api"></a><span data-ttu-id="08e69-128">支払い要求 API</span><span class="sxs-lookup"><span data-stu-id="08e69-128">Payment Request API</span></span>  

<span data-ttu-id="08e69-129">支払い [要求 API](../windows-integration/payment-request-api.md) は、ブラウザーがクラウドに保存したマーチャント、コンシューマー、支払い方法 \(クレジット カード\など) の間の仲介者としてブラウザーが機能するオープンなクロスブラウザー標準です。</span><span class="sxs-lookup"><span data-stu-id="08e69-129">The [Payment Request API](../windows-integration/payment-request-api.md) is an open, cross-browser standard that enables browsers to act as an intermediary between merchants, consumers, and payment methods \(such as credit cards\) that consumers have stored in the cloud.</span></span>  <span data-ttu-id="08e69-130">EdgeHTML 16 の API は、最新の W3C 支払い要求 API 仕様に合 [わせて更新](https://w3c.github.io/payment-request) されました。</span><span class="sxs-lookup"><span data-stu-id="08e69-130">The API in EdgeHTML 16 has been updated to match the latest W3C [Payment Request API](https://w3c.github.io/payment-request) specification.</span></span>  <span data-ttu-id="08e69-131">次のようなシナリオが考えられます。</span><span class="sxs-lookup"><span data-stu-id="08e69-131">This includes:</span></span>  

*   <span data-ttu-id="08e69-132">メソッドの `canMakePayment()` サポート</span><span class="sxs-lookup"><span data-stu-id="08e69-132">Support for the `canMakePayment()` method</span></span>  
*   <span data-ttu-id="08e69-133">プロパティの `requestId` サポート</span><span class="sxs-lookup"><span data-stu-id="08e69-133">Support for the `requestId` property</span></span>  
*   <span data-ttu-id="08e69-134">プロパティの `id` サポート</span><span class="sxs-lookup"><span data-stu-id="08e69-134">Support for the `id` property</span></span>  
*   <span data-ttu-id="08e69-135">メソッドのパラメーターの既定値が " `complete()` `result` " から "unknown" に変更されました</span><span class="sxs-lookup"><span data-stu-id="08e69-135">The default value for the `complete()` method's `result` parameter changed from " " to "unknown"</span></span>  

### <a name="service-workers"></a><span data-ttu-id="08e69-136">サービス ワーカー</span><span class="sxs-lookup"><span data-stu-id="08e69-136">Service Workers</span></span>  

<span data-ttu-id="08e69-137">[Service Workers は](https://www.w3.org/TR/service-workers-1) 、Web ページのバックグラウンドで実行されるイベント駆動型スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="08e69-137">[Service Workers](https://www.w3.org/TR/service-workers-1) are event-driven scripts that run in the background of a web page.</span></span>  <span data-ttu-id="08e69-138">サービス ワーカーは、ネットワークからの要求の傍受と処理、バックグラウンド同期、ローカル ストレージ、プッシュ通知の管理と処理など、以前はネイティブ アプリでのみ利用できる機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="08e69-138">Service workers enable functionality previously only available with native apps like intercepting and handling requests from the network, managing and handling background sync, local storage, and push notifications.</span></span>  <span data-ttu-id="08e69-139">サービス ワーカーのサポートはまだ開発中ですが、Microsoft Edge でサービス ワーカー機能を有効にすることで、Microsoft Edge で PWA をテストできます `about:flags` 。</span><span class="sxs-lookup"><span data-stu-id="08e69-139">Support for service worker is still in development, but you can test out your PWA in Microsoft Edge with our experimental service worker support by enabling the service worker feature in `about:flags`.</span></span>  

### <a name="webvr"></a><span data-ttu-id="08e69-140">WebVR</span><span class="sxs-lookup"><span data-stu-id="08e69-140">WebVR</span></span>  

<span data-ttu-id="08e69-141">Microsoft Edge の WebVR では、モーション コントローラーの [サポートが追加されました](https://developer.microsoft.com/windows/mixed-reality/motion_controllers)。</span><span class="sxs-lookup"><span data-stu-id="08e69-141">WebVR for Microsoft Edge has added support for [motion controllers](https://developer.microsoft.com/windows/mixed-reality/motion_controllers).</span></span>  <span data-ttu-id="08e69-142">これらのコントローラーは空間内の正確な位置を持ち、仮想現実のデジタル オブジェクトとの詳細な対話を可能にします。</span><span class="sxs-lookup"><span data-stu-id="08e69-142">These controllers have a precise position in space, allowing for fine grained interaction with digital objects in virtual reality.</span></span>  

:::image type="complex" source="../media/MotionControllers.jpg" alt-text="モーション コントローラー" lightbox="../media/MotionControllers.jpg":::
   <span data-ttu-id="08e69-144">モーション コントローラー</span><span class="sxs-lookup"><span data-stu-id="08e69-144">Motion controllers</span></span>  
:::image-end:::  

<span data-ttu-id="08e69-145">WebVR は、2 つの異なる種類のエクスペリエンスをサポートするために最適化されています。</span><span class="sxs-lookup"><span data-stu-id="08e69-145">WebVR has also been optimized to support two different types of experiences.</span></span>  

<span data-ttu-id="08e69-146">**Windows Mixed Reality PC** - 統合グラフィックスを備えたデスクトップとラップトップ。</span><span class="sxs-lookup"><span data-stu-id="08e69-146">**Windows Mixed Reality PCs** - Desktops and laptops with integrated graphics.</span></span>  <span data-ttu-id="08e69-147">これらのデバイスに接続すると、イマーシブ ヘッドセットは 1 秒あたり 60 フレームで実行されます。</span><span class="sxs-lookup"><span data-stu-id="08e69-147">When plugged into these devices, our immersive headsets will run at 60 frames per second.</span></span>  
<span data-ttu-id="08e69-148">**Windows Mixed Reality Ultra PC** - ディスクリート グラフィックスを備えるデスクトップとラップトップ。</span><span class="sxs-lookup"><span data-stu-id="08e69-148">**Windows Mixed Reality Ultra PCs** - Desktops and laptops with discrete graphics.</span></span>  <span data-ttu-id="08e69-149">これらのデバイスに接続すると、イマーシブ ヘッドセットは 1 秒あたり 90 フレームで実行されます。</span><span class="sxs-lookup"><span data-stu-id="08e69-149">When plugged into these devices, our immersive headsets will run at 90 frames per second.</span></span>  

<span data-ttu-id="08e69-150">どちらのセットアップも、同じイマーシブ ビデオとゲーム エクスペリエンスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="08e69-150">Both setups will support the same immersive video and gaming experiences.</span></span>  

<span data-ttu-id="08e69-151">今後の Windows Mixed Reality 更新プログラムの詳細については [、Windows Mixed Reality](https://blogs.windows.com/windowsexperience/2017/08/28/windows-mixed-reality-holiday-update) の休日の更新プログラムのブログ投稿を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08e69-151">For more info about the upcoming Windows Mixed Reality updates, check out the [Windows Mixed Reality](https://blogs.windows.com/windowsexperience/2017/08/28/windows-mixed-reality-holiday-update) holiday update blog post.</span></span>  

<span data-ttu-id="08e69-152">ガイドとデモについては、WebVR 開発者ガイド [にアクセスしてください](/microsoft-edge/webvr)。</span><span class="sxs-lookup"><span data-stu-id="08e69-152">For guides and demos, head over to the [WebVR Developer Guide](/microsoft-edge/webvr).</span></span>  

 > [!NOTE] 
 > <span data-ttu-id="08e69-153">WebVR 仕様はまだ開発中ですから、Microsoft Edge の実装は後で変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="08e69-153">Since the WebVR spec is still in development, Microsoft Edge's implementation may change later down the line.</span></span>  

## <a name="new-apis-in-edgehtml-16"></a><span data-ttu-id="08e69-154">EdgeHTML 16 の新しい API</span><span class="sxs-lookup"><span data-stu-id="08e69-154">New APIs in EdgeHTML 16</span></span>  

<span data-ttu-id="08e69-155">EdgeHTML 16 の新しい API の完全な一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="08e69-155">Here's the full list of new APIs in EdgeHTML 16.</span></span>  <span data-ttu-id="08e69-156">これらはの形式で一覧表示されます `[interface name].[api name]` 。</span><span class="sxs-lookup"><span data-stu-id="08e69-156">They are listed in the format of `[interface name].[api name]`.</span></span>

> [!NOTE] 
> <span data-ttu-id="08e69-157">次の API は DOM で公開されているが、一部のエンドツーエンドの動作はまだ開発中である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="08e69-157">Although the following APIs are exposed in the DOM, the end-to-end behavior of some might still be in development.</span></span>  <span data-ttu-id="08e69-158">機能の [サポートに関する公式な単語については、「Microsoft Edge](https://developer.microsoft.com/microsoft-edge/platform/status) プラットフォームの状態」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08e69-158">Refer to [Microsoft Edge platform status](https://developer.microsoft.com/microsoft-edge/platform/status) for the official word on feature support.</span></span>  

---  

<iframe height='559' scrolling='no' title='<span data-ttu-id="08e69-159">EdgeHTML 16 の新しい API</span><span class="sxs-lookup"><span data-stu-id="08e69-159">New APIs in EdgeHTML 16</span></span>' src='//codepen.io/MSEdgeDev/embed/jLGZZY/?height=559&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'><span data-ttu-id="08e69-160">CodePen の <a href='https://codepen.io/MSEdgeDev/pen/jLGZZY/'> EdgeHTML 16 </a> by MSEdgeDev ( @MSEdgeDev <a href='https://codepen.io/MSEdgeDev'> ) のペンの新しい API </a> を <a href='https://codepen.io'> 参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="08e69-160">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/jLGZZY/'>New APIs in EdgeHTML 16</a>by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

---  

## <a name="previous-edgehtml-releases"></a><span data-ttu-id="08e69-161">以前の EdgeHTML リリース</span><span class="sxs-lookup"><span data-stu-id="08e69-161">Previous EdgeHTML releases</span></span>  

[<span data-ttu-id="08e69-162">EdgeHTML 12 / Windows ビルド 10240 (2015/7)</span><span class="sxs-lookup"><span data-stu-id="08e69-162">EdgeHTML 12 / Windows build 10240 (7/2015)</span></span>](./edgehtml-12.md)  

[<span data-ttu-id="08e69-163">EdgeHTML 13 / Windows ビルド 10586 (2015/11)</span><span class="sxs-lookup"><span data-stu-id="08e69-163">EdgeHTML 13 / Windows build 10586 (11/2015)</span></span>](./edgehtml-13.md)  

[<span data-ttu-id="08e69-164">EdgeHTML 14 / Windows ビルド 14393 (2016/8)</span><span class="sxs-lookup"><span data-stu-id="08e69-164">EdgeHTML 14 / Windows build 14393 (8/2016)</span></span>](./edgehtml-14.md)  

[<span data-ttu-id="08e69-165">EdgeHTML 15 / Windows ビルド 15063 (2017/4)</span><span class="sxs-lookup"><span data-stu-id="08e69-165">EdgeHTML 15 / Windows build 15063 (4/2017)</span></span>](./edgehtml-15.md)  
