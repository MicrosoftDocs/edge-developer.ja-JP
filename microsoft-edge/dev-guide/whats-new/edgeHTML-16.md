---
ms.assetid: 476c4b7a-be24-434b-a051-83f19d741aaf
description: このガイドでは、Microsoft Edge に含まれる開発者の機能と標準の概要を説明します。
title: EdgeHTML 16 の新機能と API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、Web 開発、html、cs、javascript、開発者
ms.openlocfilehash: a15888bc8c1314d61d436759e5d63be942174ea4
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941937"
---
# <span data-ttu-id="8e2e0-104">Microsoft EdgeHTML 16 の新機能</span><span class="sxs-lookup"><span data-stu-id="8e2e0-104">What's new in EdgeHTML 16</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="8e2e0-105">[Windows 10 Fall Creators Update](https://blogs.windows.com/windowsexperience/2017/10/17/whats-new-windows-10-fall-creators-update) \(10/2017, ビルド 16299\)[の一部として、EdgeHTML 16 Web](https://blogs.windows.com/msedgedev/2017/10/17)プラットフォームで出荷された新機能と更新された機能の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-105">Here's a list of the new and updated features shipped in [EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/17) web platform, as part of the [Windows 10 Fall Creators Update](https://blogs.windows.com/windowsexperience/2017/10/17/whats-new-windows-10-fall-creators-update) \(10/2017, Build 16299\).</span></span>  <span data-ttu-id="8e2e0-106">特定の Windows Insider Preview ビルドの変更内容については [、Microsoft Edge の変更履歴と](https://developer.microsoft.com/microsoft-edge/platform/changelog) [EdgeHTML の新機能を参照してください](../whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-106">For changes in specific Windows Insider Preview builds, see the [Microsoft Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog) and [What's New in EdgeHTML](../whats-new.md).</span></span>  

<span data-ttu-id="8e2e0-107">次の一覧を行うと、この機能が利用できます  [https://aka.ms/devguide_edgehtml_16](./edgehtml-16.md) 。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-107">Here's the permalink for the following list of changes:  [https://aka.ms/devguide_edgehtml_16](./edgehtml-16.md).</span></span>  

## <span data-ttu-id="8e2e0-108">新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="8e2e0-108">New and updated features</span></span>  

### <span data-ttu-id="8e2e0-109">CSS グリッド レイアウト</span><span class="sxs-lookup"><span data-stu-id="8e2e0-109">CSS Grid Layout</span></span>  

<span data-ttu-id="8e2e0-110">Microsoft Edge では、CSS グリッド レイアウトの先頭フィックスなし [の実装がサポートされるようになりました](https://www.w3.org/TR/css-grid-1)。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-110">Microsoft Edge now supports the un-prefixed implementation of [CSS Grid Layout](https://www.w3.org/TR/css-grid-1).</span></span>  <span data-ttu-id="8e2e0-111">[グリッ](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout) ド レイアウトは 2 次次のグリッドベース レイアウト システムを定義し、フロートやスクリプトを使用した位置よりもレイアウトのフラデリングが可能になります。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-111">[Grid Layout](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout) defines a two-dimensional grid-based layout system which enables more layout fluidity than possible with positioning using floats or scripts.</span></span>  <span data-ttu-id="8e2e0-112">次の例では、CSS グリッド レイアウトを使用して、基本的な Web ページ用の構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-112">The example below uses CSS Grid Layout to create the structure for a basic web page.</span></span>  

<iframe height='303' scrolling='no' title='<span data-ttu-id="8e2e0-113">CSS グリッド レイアウト</span><span class="sxs-lookup"><span data-stu-id="8e2e0-113">CSS Grid Layout</span></span>' src='//codepen.io/MSEdgeDev/embed/mMQqZX/?height=303&theme-id=23761&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'><span data-ttu-id="8e2e0-114">CodePen の Pen <a href='https://codepen.io/MSEdgeDev/pen/mMQqZX/'> CSS </a> <a href='https://codepen.io/MSEdgeDev'> グリッド レイアウト </a> @MSEdgeDev) <a href='https://codepen.io'> を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-114">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/mMQqZX/'>CSS Grid Layout</a>by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

### <span data-ttu-id="8e2e0-115">CSS オブジェクトに合うオブジェクト位置とオブジェクト位置</span><span class="sxs-lookup"><span data-stu-id="8e2e0-115">CSS object-fit and object-position</span></span>  

<span data-ttu-id="8e2e0-116">Microsoft EdgeHTML 16 では、CSS のプロパティとサポートが追加 [`object-fit`](https://developer.mozilla.org/docs/Web/CSS/object-fit) されました [`object-position`](https://developer.mozilla.org/docs/Web/CSS/object-position) 。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-116">EdgeHTML 16 introduces support for CSS properties [`object-fit`](https://developer.mozilla.org/docs/Web/CSS/object-fit) and [`object-position`](https://developer.mozilla.org/docs/Web/CSS/object-position).</span></span>  <span data-ttu-id="8e2e0-117">これらのプロパティは、置換されたコンテンツ ボックス内のコンテンツの位置とサイズを制御します。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-117">These properties control the position and size of replaced content within the content box.</span></span>  

### <span data-ttu-id="8e2e0-118">開発者ツール</span><span class="sxs-lookup"><span data-stu-id="8e2e0-118">Developer Tools</span></span>  

<span data-ttu-id="8e2e0-119">このリリースでは、強化された強力な機能とパフォーマンス向上のための主な Microsoft Edge DevTools の取り戻り機能を開始しました。 [また、Windows Insider ビルド](https://insider.windows.com) で今日の使用を開始できる新機能が数多く加えられました。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-119">This release we started a major Microsoft Edge DevTools refactoring effort for improved robustness and performance, and also added a bunch of new features you can start using today on [Windows Insider](https://insider.windows.com) builds.</span></span>  <span data-ttu-id="8e2e0-120">[変更内容の詳細については、Microsoft Edge DevTools](../whats-new.md)ガイドをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-120">Check out the [Microsoft Edge DevTools guide](../whats-new.md) for more on what's changed!</span></span>  

### <span data-ttu-id="8e2e0-121">JavaScript</span><span class="sxs-lookup"><span data-stu-id="8e2e0-121">JavaScript</span></span>  

<span data-ttu-id="8e2e0-122">[EdgeHTML 16 は、以前のリリースの Javascript パ](https://blogs.windows.com/msedgedev/2017/10/31)フォーマンス最適化に基するビルドで、キャクラエンド関数を Defer/re dedefer 関数の使用し、ブロック付きの関数を最適化 `try` / `finally` します。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-122">[EdgeHTML 16 builds on Javascript performance](https://blogs.windows.com/msedgedev/2017/10/31) optimizations of previous releases by expanding the Chakra engine's ability to defer/re-defer functions, use polymorphic inline caches, and optimize functions with `try`/`finally` blocks.</span></span>  

<span data-ttu-id="8e2e0-123">さらに、Microsoft EdgeHTML 15 で最初にプレビューした機能が、既定で有効になり、既定で有効になりました。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-123">Additionally, features first previewed in EdgeHTML 15 are now stable and enabled by default:</span></span>  

#### <span data-ttu-id="8e2e0-124">新機能</span><span class="sxs-lookup"><span data-stu-id="8e2e0-124">New features</span></span>  

<span data-ttu-id="8e2e0-125">既定でオン</span><span class="sxs-lookup"><span data-stu-id="8e2e0-125">On by default</span></span>  

*   <span data-ttu-id="8e2e0-126">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) MVP \([デモ](https://webassembly.org/demo)\)</span><span class="sxs-lookup"><span data-stu-id="8e2e0-126">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) MVP \([demo](https://webassembly.org/demo)\)</span></span>  
*   [<span data-ttu-id="8e2e0-127">共有メモリとアトミックス</span><span class="sxs-lookup"><span data-stu-id="8e2e0-127">Shared Memory and Atomics</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

### <span data-ttu-id="8e2e0-128">支払い要求 API</span><span class="sxs-lookup"><span data-stu-id="8e2e0-128">Payment Request API</span></span>  

<span data-ttu-id="8e2e0-129">[支払要求 API は開発者](../windows-integration/payment-request-api.md)がクラウドに保存されているメッカー、コンシューマー、支払方法 \(クレジット カード\) 間の中間として機能する開いています。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-129">The [Payment Request API](../windows-integration/payment-request-api.md) is an open, cross-browser standard that enables browsers to act as an intermediary between merchants, consumers, and payment methods \(such as credit cards\) that consumers have stored in the cloud.</span></span>  <span data-ttu-id="8e2e0-130">Microsoft EdgeHTML 16 の API が最新の W3C [Payment Request API の指定と一致するように更新](https://w3c.github.io/payment-request) されました。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-130">The API in EdgeHTML 16 has been updated to match the latest W3C [Payment Request API](https://w3c.github.io/payment-request) specification.</span></span>  <span data-ttu-id="8e2e0-131">次のようなシナリオが考えられます。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-131">This includes:</span></span>  

*   <span data-ttu-id="8e2e0-132">方法の `canMakePayment()` サポート</span><span class="sxs-lookup"><span data-stu-id="8e2e0-132">Support for the `canMakePayment()` method</span></span>  
*   <span data-ttu-id="8e2e0-133">プロパティの `requestId` サポート</span><span class="sxs-lookup"><span data-stu-id="8e2e0-133">Support for the `requestId` property</span></span>  
*   <span data-ttu-id="8e2e0-134">プロパティの `id` サポート</span><span class="sxs-lookup"><span data-stu-id="8e2e0-134">Support for the `id` property</span></span>  
*   <span data-ttu-id="8e2e0-135">メソッドのパラ `complete()` メーターの既定値 `result` は、"" から "不明" に変更されます。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-135">The default value for the `complete()` method's `result` parameter changed from " " to "unknown"</span></span>  

### <span data-ttu-id="8e2e0-136">サービス ワーカー</span><span class="sxs-lookup"><span data-stu-id="8e2e0-136">Service Workers</span></span>  

<span data-ttu-id="8e2e0-137">[サービス ワーカーは](https://www.w3.org/TR/service-workers-1) 、Web ページのバックグラウンドで実行されるイベント ベースのスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-137">[Service Workers](https://www.w3.org/TR/service-workers-1) are event-driven scripts that run in the background of a web page.</span></span>  <span data-ttu-id="8e2e0-138">サービスワーカーは、以前はネットワークから要求を取り消す、バックグラウンド同期の管理と取り付け、ローカル ストレージ、プッシュ通知など、以前はネイティブ アプリでのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-138">Service workers enable functionality previously only available with native apps like intercepting and handling requests from the network, managing and handling background sync, local storage, and push notifications.</span></span>  <span data-ttu-id="8e2e0-139">サービス ワーカーのサポートは現在開発中ですが、サービス ワーカー機能を有効にすることで、Microsoft Edge の実用サービス ワーカー サポートをテストすることができます `about:flags` 。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-139">Support for service worker is still in development, but you can test out your PWA in Microsoft Edge with our experimental service worker support by enabling the service worker feature in `about:flags`.</span></span>  

### <span data-ttu-id="8e2e0-140">WebVR</span><span class="sxs-lookup"><span data-stu-id="8e2e0-140">WebVR</span></span>  

<span data-ttu-id="8e2e0-141">WebVR for Microsoft Edge では、モーション コントロー [ラーのサポートが追加されました](https://developer.microsoft.com/windows/mixed-reality/motion_controllers)。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-141">WebVR for Microsoft Edge has added support for [motion controllers](https://developer.microsoft.com/windows/mixed-reality/motion_controllers).</span></span>  <span data-ttu-id="8e2e0-142">これらのコントローラーはスペースで正確な位置であり、仮想リアルティでデジタル オブジェクトとのやり取りをきれいにすることができます。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-142">These controllers have a precise position in space, allowing for fine grained interaction with digital objects in virtual reality.</span></span>  

:::image type="complex" source="../media/MotionControllers.jpg" alt-text="モーション コントローラー" lightbox="../media/MotionControllers.jpg":::
   <span data-ttu-id="8e2e0-144">モーション コントローラー</span><span class="sxs-lookup"><span data-stu-id="8e2e0-144">Motion controllers</span></span>  
:::image-end:::  

<span data-ttu-id="8e2e0-145">また、WebVR は、2 種類の異なるエクスペリエンスをサポートする最適化されています。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-145">WebVR has also been optimized to support two different types of experiences.</span></span>  

<span data-ttu-id="8e2e0-146">**Windows Mixed Reality PC** - 統合グラフィック付きのデスクトップとノート PC。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-146">**Windows Mixed Reality PCs** - Desktops and laptops with integrated graphics.</span></span>  <span data-ttu-id="8e2e0-147">これらのデバイスに接続すると、イマーシブ ヘッドセットは 1 秒あたり 60 フレームで実行されます。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-147">When plugged into these devices, our immersive headsets will run at 60 frames per second.</span></span>  
<span data-ttu-id="8e2e0-148">**Windows Mixed Reality Ultra PC** - グラフィックとノート PC に、グラフィックが分けされたデスクトップやノート PC。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-148">**Windows Mixed Reality Ultra PCs** - Desktops and laptops with discrete graphics.</span></span>  <span data-ttu-id="8e2e0-149">これらのデバイスに接続すると、イマーシブ ヘッドセットは 1 秒あたり 90 フレームで実行されます。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-149">When plugged into these devices, our immersive headsets will run at 90 frames per second.</span></span>  

<span data-ttu-id="8e2e0-150">どちらのセットアップも、同じイマーシブ ビデオとゲーム エクスペリエンスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-150">Both setups will support the same immersive video and gaming experiences.</span></span>  

<span data-ttu-id="8e2e0-151">以降の Windows Mixed Reality の更新プログラムの詳細については [、Windows Mixed Reality](https://blogs.windows.com/windowsexperience/2017/08/28/windows-mixed-reality-holiday-update) の祝日の更新プログラムのブログを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-151">For more info about the upcoming Windows Mixed Reality updates, check out the [Windows Mixed Reality](https://blogs.windows.com/windowsexperience/2017/08/28/windows-mixed-reality-holiday-update) holiday update blog post.</span></span>  

<span data-ttu-id="8e2e0-152">ガイドやデモについては [、WebVR](/microsoft-edge/webvr)開発者ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-152">For guides and demos, head over to the [WebVR Developer Guide](/microsoft-edge/webvr).</span></span>  

 > [!NOTE] 
 > <span data-ttu-id="8e2e0-153">WebVR の速度は開発中であるため、Microsoft Edge の実装は後で行直す場合があります。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-153">Since the WebVR spec is still in development, Microsoft Edge's implementation may change later down the line.</span></span>  

## <span data-ttu-id="8e2e0-154">EdgeHTML 16 の新しい API</span><span class="sxs-lookup"><span data-stu-id="8e2e0-154">New APIs in EdgeHTML 16</span></span>  

<span data-ttu-id="8e2e0-155">EdgeHTML 16 の新しい API の完全な一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-155">Here's the full list of new APIs in EdgeHTML 16.</span></span>  <span data-ttu-id="8e2e0-156">これらは形式で表示されます `[interface name].[api name]` 。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-156">They are listed in the format of `[interface name].[api name]`.</span></span>

> [!NOTE] 
> <span data-ttu-id="8e2e0-157">次の API は DOM で予定されていますが、一部の開発中のエンドツーエンド動作がまだあります。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-157">Although the following APIs are exposed in the DOM, the end-to-end behavior of some might still be in development.</span></span>  <span data-ttu-id="8e2e0-158">機能サポート  [のコーサル語については、Microsoft Edge](https://developer.microsoft.com/microsoft-edge/platform/status) プラットフォームの状態を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-158">Refer to  [Microsoft Edge platform status](https://developer.microsoft.com/microsoft-edge/platform/status) for the official word on feature support.</span></span>  

---  

<iframe height='559' scrolling='no' title='<span data-ttu-id="8e2e0-159">EdgeHTML 16 の新しい API</span><span class="sxs-lookup"><span data-stu-id="8e2e0-159">New APIs in EdgeHTML 16</span></span>' src='//codepen.io/MSEdgeDev/embed/jLGZZY/?height=559&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'><span data-ttu-id="8e2e0-160"><a href='https://codepen.io/MSEdgeDev/pen/jLGZZY/'>CodePen の EdgeHTML 16 の Pen New API </a> <a href='https://codepen.io/MSEdgeDev'> @MSEdgeDev </a> <a href='https://codepen.io'> 参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="8e2e0-160">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/jLGZZY/'>New APIs in EdgeHTML 16</a>by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

---  

## <span data-ttu-id="8e2e0-161">以前の EdgeHTML リリース</span><span class="sxs-lookup"><span data-stu-id="8e2e0-161">Previous EdgeHTML releases</span></span>  

[<span data-ttu-id="8e2e0-162">Microsoft EdgeHTML 12 / Windows ビルド 10240 (7/2015)</span><span class="sxs-lookup"><span data-stu-id="8e2e0-162">EdgeHTML 12 / Windows build 10240 (7/2015)</span></span>](./edgehtml-12.md)  

[<span data-ttu-id="8e2e0-163">Microsoft EdgeHTML 13 / Windows ビルド 10586 (2015/11)</span><span class="sxs-lookup"><span data-stu-id="8e2e0-163">EdgeHTML 13 / Windows build 10586 (11/2015)</span></span>](./edgehtml-13.md)  

[<span data-ttu-id="8e2e0-164">EdgeHTML 14 / Windows ビルド 14393 (8/2016)</span><span class="sxs-lookup"><span data-stu-id="8e2e0-164">EdgeHTML 14 / Windows build 14393 (8/2016)</span></span>](./edgehtml-14.md)  

[<span data-ttu-id="8e2e0-165">Microsoft EdgeHTML 15 / Windows ビルド 15063 (4/2017)</span><span class="sxs-lookup"><span data-stu-id="8e2e0-165">EdgeHTML 15 / Windows build 15063 (4/2017)</span></span>](./edgehtml-15.md)  
