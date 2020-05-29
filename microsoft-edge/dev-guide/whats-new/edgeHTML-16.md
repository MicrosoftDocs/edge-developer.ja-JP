---
ms.assetid: 476c4b7a-be24-434b-a051-83f19d741aaf
description: このガイドでは、Microsoft Edge に含まれている開発者向けの機能と標準の概要について説明します。
title: 開発ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: 36c5e6530ff584a97e4b42910757495362a1960d
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568849"
---
# <span data-ttu-id="af986-104">EdgeHTML 16 の新機能</span><span class="sxs-lookup"><span data-stu-id="af986-104">What's new in EdgeHTML 16</span></span>

<span data-ttu-id="af986-105">次に、 [EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/17/edgehtml-16-fall-creators-update/) web platform で出荷される新機能と更新された機能の一覧を示し[ます (10/2017](https://blogs.windows.com/windowsexperience/2017/10/17/whats-new-windows-10-fall-creators-update/) 、ビルド 16299)。</span><span class="sxs-lookup"><span data-stu-id="af986-105">Here's a list of the new and updated features shipped in [EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/17/edgehtml-16-fall-creators-update/) web platform, as part of the [Windows 10 Fall Creators Update](https://blogs.windows.com/windowsexperience/2017/10/17/whats-new-windows-10-fall-creators-update/) (10/2017, Build 16299).</span></span> <span data-ttu-id="af986-106">特定の Windows Insider Preview ビルドでの変更については、 [Microsoft Edge の Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog/)と[EdgeHTML の新機能](../whats-new.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="af986-106">For changes in specific Windows Insider Preview builds, see the [Microsoft Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog/) and [What's New in EdgeHTML](../whats-new.md).</span></span>

<span data-ttu-id="af986-107">次の変更の固定リンクを示し [https://aka.ms/devguide_edgehtml_16](https://aka.ms/devguide_edgehtml_16) ます。</span><span class="sxs-lookup"><span data-stu-id="af986-107">Here's the permalink for the following list of changes: [https://aka.ms/devguide_edgehtml_16](https://aka.ms/devguide_edgehtml_16).</span></span>

## <span data-ttu-id="af986-108">新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="af986-108">New and updated features</span></span>

### <span data-ttu-id="af986-109">CSS グリッドのレイアウト</span><span class="sxs-lookup"><span data-stu-id="af986-109">CSS Grid Layout</span></span>

<span data-ttu-id="af986-110">Microsoft Edge で、 [CSS グリッドレイアウト](https://www.w3.org/TR/css-grid-1/)のプレフィックスのない実装がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="af986-110">Microsoft Edge now supports the unprefixed implementation of [CSS Grid Layout](https://www.w3.org/TR/css-grid-1/).</span></span> <span data-ttu-id="af986-111">[Grid レイアウト](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout)では、2次元グリッドベースのレイアウトシステムが定義されています。これにより、フロートまたはスクリプトを使用した配置で、より多くのレイアウト適切な決まりが可能になります。</span><span class="sxs-lookup"><span data-stu-id="af986-111">[Grid Layout](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout) defines a two-dimensional grid-based layout system which enables more layout fluidity than possible with positioning using floats or scripts.</span></span> <span data-ttu-id="af986-112">次の例では、CSS Grid レイアウトを使って、基本的な web ページの構造を作成しています。</span><span class="sxs-lookup"><span data-stu-id="af986-112">The example below uses CSS Grid Layout to create the structure for a basic web page.</span></span>


<iframe height='303' scrolling='no' title='<span data-ttu-id="af986-113">CSS グリッドのレイアウト</span><span class="sxs-lookup"><span data-stu-id="af986-113">CSS Grid Layout</span></span>' src='//codepen.io/MSEdgeDev/embed/mMQqZX/?height=303&theme-id=23761&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'><span data-ttu-id="af986-114"><a href='https://codepen.io/MSEdgeDev/pen/mMQqZX/'> </a> CodePen の MSEdgeDev (@MSEdgeDev) でペン CSS グリッドレイアウトを参照してください <a href='https://codepen.io/MSEdgeDev'> </a> <a href='https://codepen.io'> </a> 。</span><span class="sxs-lookup"><span data-stu-id="af986-114">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/mMQqZX/'>CSS Grid Layout</a>by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span>
</iframe>


### <span data-ttu-id="af986-115">CSS `object-fit` と</span><span class="sxs-lookup"><span data-stu-id="af986-115">CSS `object-fit` and</span></span> `object-position`

<span data-ttu-id="af986-116">EdgeHTML 16 では、CSS プロパティとのサポートが導入さ [`object-fit`](https://developer.mozilla.org/docs/Web/CSS/object-fit) [`object-position`](https://developer.mozilla.org/docs/Web/CSS/object-position) れています。</span><span class="sxs-lookup"><span data-stu-id="af986-116">EdgeHTML 16 introduces support for CSS properties [`object-fit`](https://developer.mozilla.org/docs/Web/CSS/object-fit) and [`object-position`](https://developer.mozilla.org/docs/Web/CSS/object-position).</span></span>  <span data-ttu-id="af986-117">これらのプロパティは、コンテンツボックス内の置換されたコンテンツの位置とサイズを制御します。</span><span class="sxs-lookup"><span data-stu-id="af986-117">These properties control the position and size of replaced content within the content box.</span></span>  

### <span data-ttu-id="af986-118">開発者ツール</span><span class="sxs-lookup"><span data-stu-id="af986-118">Developer Tools</span></span>

<span data-ttu-id="af986-119">このリリースでは、優れた信頼性とパフォーマンスを向上させるための主要な Microsoft Edge DevTools リファクタリングの取り組みを開始しました。また、 [Windows Insider](https://insider.windows.com/)ビルドで今日使用できる新機能の多数を追加しました。</span><span class="sxs-lookup"><span data-stu-id="af986-119">This release we started a major Microsoft Edge DevTools refactoring effort for improved robustness and performance, and also added a bunch of new features you can start using today on [Windows Insider](https://insider.windows.com/) builds.</span></span>  <span data-ttu-id="af986-120">変更点については、 [Microsoft Edge DevTools のガイド](../../devtools-guide/whats-new.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="af986-120">Check out the [Microsoft Edge DevTools guide](../../devtools-guide/whats-new.md) for more on what's changed!</span></span>

### <span data-ttu-id="af986-121">JavaScript</span><span class="sxs-lookup"><span data-stu-id="af986-121">JavaScript</span></span>

<span data-ttu-id="af986-122">[EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/31/optimizations-webassembly-sharedarraybuffer-atomics-edgehtml-16/#FodxEPHxR4WkbtyA.97)は、以前のリリースの Javascript パフォーマンスの最適化について、Chakra エンジンの機能を拡張して、関数の遅延/再遅延、ポリモーフィックなインラインキャッシュの使用、 *try/finally*ブロックでの関数の最適化を実現しています。</span><span class="sxs-lookup"><span data-stu-id="af986-122">[EdgeHTML 16 builds on Javascript performance](https://blogs.windows.com/msedgedev/2017/10/31/optimizations-webassembly-sharedarraybuffer-atomics-edgehtml-16/#FodxEPHxR4WkbtyA.97) optimizations of previous releases by expanding the Chakra engine's ability to defer/re-defer functions, use polymorphic inline caches, and optimize functions with *try/finally* blocks.</span></span>

<span data-ttu-id="af986-123">さらに、EdgeHTML 15 で最初にプレビューされた機能は、既定で安定して有効になりました。</span><span class="sxs-lookup"><span data-stu-id="af986-123">Additionally, features first previewed in EdgeHTML 15 are now stable and enabled by default:</span></span>

#### <span data-ttu-id="af986-124">新機能 (既定でオン)</span><span class="sxs-lookup"><span data-stu-id="af986-124">New features (on by default)</span></span>

* <span data-ttu-id="af986-125">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly)おMVP ([デモ](https://webassembly.org/demo/))</span><span class="sxs-lookup"><span data-stu-id="af986-125">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) MVP ([demo](https://webassembly.org/demo/))</span></span>
* [<span data-ttu-id="af986-126">共有メモリと Atomics</span><span class="sxs-lookup"><span data-stu-id="af986-126">Shared Memory and Atomics</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)

### <span data-ttu-id="af986-127">支払い要求 API</span><span class="sxs-lookup"><span data-stu-id="af986-127">Payment Request API</span></span>

<span data-ttu-id="af986-128">[支払い要求 API](../windows-integration/payment-request-api.md)は、ユーザーがクラウドに保存されている商人、消費者、支払方法 (クレジットカードなど) との仲介としてブラウザーが機能するようにする、オープンなクロスブラウザー標準です。</span><span class="sxs-lookup"><span data-stu-id="af986-128">The [Payment Request API](../windows-integration/payment-request-api.md) is an open, cross-browser standard that enables browsers to act as an intermediary between merchants, consumers, and payment methods (e.g. credit cards) that consumers have stored in the cloud.</span></span>  <span data-ttu-id="af986-129">EdgeHTML 16 の API は、W3C の最新の[支払い要求 api](https://w3c.github.io/payment-request/)仕様と一致するように更新されました。</span><span class="sxs-lookup"><span data-stu-id="af986-129">The API in EdgeHTML 16 has been updated to match the latest W3C [Payment Request API](https://w3c.github.io/payment-request/) specification.</span></span> <span data-ttu-id="af986-130">次のようなシナリオが考えられます。</span><span class="sxs-lookup"><span data-stu-id="af986-130">This includes:</span></span>
* <span data-ttu-id="af986-131">メソッドのサポート `canMakePayment()`</span><span class="sxs-lookup"><span data-stu-id="af986-131">Support for the `canMakePayment()` method</span></span>
* <span data-ttu-id="af986-132">プロパティのサポート `requestId`</span><span class="sxs-lookup"><span data-stu-id="af986-132">Support for the `requestId` property</span></span>
* <span data-ttu-id="af986-133">プロパティのサポート `id`</span><span class="sxs-lookup"><span data-stu-id="af986-133">Support for the `id` property</span></span>
* <span data-ttu-id="af986-134">`complete()`メソッドのパラメーターの既定値が `result` "" から "不明" に変更されました。</span><span class="sxs-lookup"><span data-stu-id="af986-134">The default value for the `complete()` method's `result` parameter changed from " " to "unknown"</span></span>

### <span data-ttu-id="af986-135">サービス員</span><span class="sxs-lookup"><span data-stu-id="af986-135">Service Workers</span></span>

<span data-ttu-id="af986-136">[サービスワーカー](https://www.w3.org/TR/service-workers-1/)は、web ページのバックグラウンドで実行されるイベント駆動型のスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="af986-136">[Service Workers](https://www.w3.org/TR/service-workers-1/) are event-driven scripts that run in the background of a web page.</span></span> <span data-ttu-id="af986-137">サービスワーカーは、以前は、ネットワークからの要求の傍受と処理、バックグラウンド同期の管理と処理、ローカルストレージ、プッシュ通知などのネイティブアプリでのみ利用できる機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="af986-137">Service workers enable functionality previously only available with native apps like intercepting and handling requests from the network, managing and handling background sync, local storage, and push notifications.</span></span> <span data-ttu-id="af986-138">サービスワーカーのサポートはまだ開発段階ですが、Microsoft Edge で、サービスワーカー機能を [ **about: flags**] で有効にすることによって、実験的なサービスワーカーサポートで PWA をテストできます。</span><span class="sxs-lookup"><span data-stu-id="af986-138">Support for service worker is still in development, but you can test out your PWA in Microsoft Edge with our experimental service worker support by enabling the service worker feature in **about:flags**.</span></span>

### <span data-ttu-id="af986-139">WebVR</span><span class="sxs-lookup"><span data-stu-id="af986-139">WebVR</span></span>
<span data-ttu-id="af986-140">Microsoft Edge 用 WebVR では、[モーションコントローラー](https://developer.microsoft.com/windows/mixed-reality/motion_controllers)のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="af986-140">WebVR for Microsoft Edge has added support for [motion controllers](https://developer.microsoft.com/windows/mixed-reality/motion_controllers).</span></span> <span data-ttu-id="af986-141">これらのコントローラーは、空間内の正確な位置を持ち、仮想現実のデジタルオブジェクトのきめ細かな操作を実現します。</span><span class="sxs-lookup"><span data-stu-id="af986-141">These controllers have a precise position in space, allowing for fine grained interaction with digital objects in virtual reality.</span></span>

![モーションコントローラー](../media/MotionControllers.jpg)

<span data-ttu-id="af986-143">また、WebVR は、2種類のエクスペリエンスをサポートするように最適化されています。</span><span class="sxs-lookup"><span data-stu-id="af986-143">WebVR has also been optimized to support two different types of experiences.</span></span>

<span data-ttu-id="af986-144">**Windows Mixed Reality pc** -内蔵グラフィックス付きのデスクトップとノート pc。</span><span class="sxs-lookup"><span data-stu-id="af986-144">**Windows Mixed Reality PCs** - Desktops and laptops with integrated graphics.</span></span>  <span data-ttu-id="af986-145">これらのデバイスに接続すると、イマーシブヘッドセットは1秒あたり60フレームで動作します。</span><span class="sxs-lookup"><span data-stu-id="af986-145">When plugged into these devices, our immersive headsets will run at 60 frames per second.</span></span>  
<span data-ttu-id="af986-146">**Windows Mixed Reality ウルトラ pc** -個別のグラフィックスを備えたデスクトップとノート pc。</span><span class="sxs-lookup"><span data-stu-id="af986-146">**Windows Mixed Reality Ultra PCs** - Desktops and laptops with discrete graphics.</span></span> <span data-ttu-id="af986-147">これらのデバイスに接続すると、イマーシブヘッドセットは1秒あたり90フレームで動作します。</span><span class="sxs-lookup"><span data-stu-id="af986-147">When plugged into these devices, our immersive headsets will run at 90 frames per second.</span></span>   

<span data-ttu-id="af986-148">どちらのセットアップでも、同じイマーシブビデオとゲームエクスペリエンスがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="af986-148">Both setups will support the same immersive video and gaming experiences.</span></span> 

<span data-ttu-id="af986-149">今後の Windows Mixed Reality の更新について詳しくは、「 [Windows Mixed reality](https://blogs.windows.com/windowsexperience/2017/08/28/windows-mixed-reality-holiday-update/)の更新」のブログ投稿をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="af986-149">For more info about the upcoming Windows Mixed Reality updates, check out the [Windows Mixed Reality](https://blogs.windows.com/windowsexperience/2017/08/28/windows-mixed-reality-holiday-update/) holiday update blog post.</span></span> 

<span data-ttu-id="af986-150">ガイドとデモについては、「 [Webvr 開発者向けガイド」](https://docs.microsoft.com/microsoft-edge/webvr/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af986-150">For guides and demos, head over to the [WebVR Developer Guide](https://docs.microsoft.com/microsoft-edge/webvr/).</span></span>

 > [!NOTE] 
 > <span data-ttu-id="af986-151">WebVR の仕様はまだ開発段階のため、Microsoft Edge の実装は後で変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="af986-151">Since the WebVR spec is still in development, Microsoft Edge's implementation may change later down the line.</span></span>

## <span data-ttu-id="af986-152">EdgeHTML 16 の新しい Api</span><span class="sxs-lookup"><span data-stu-id="af986-152">New APIs in EdgeHTML 16</span></span>

<span data-ttu-id="af986-153">EdgeHTML 16 の新しい Api の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="af986-153">Here's the full list of new APIs in EdgeHTML 16.</span></span> <span data-ttu-id="af986-154">[Interface name] の形式で一覧表示され**ます。 [api 名]**。</span><span class="sxs-lookup"><span data-stu-id="af986-154">They are listed in the format of **[interface name].[api name]**.</span></span>

> [!NOTE] 
> <span data-ttu-id="af986-155">次の Api は DOM に公開されますが、一部のエンドツーエンドの動作はまだ開発中の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="af986-155">Although the following APIs are exposed in the DOM, the end-to-end behavior of some might still be in development.</span></span> <span data-ttu-id="af986-156">機能のサポートに関するオフィシャル単語については、 [Microsoft Edge プラットフォームの状態](https://developer.microsoft.com/microsoft-edge/platform/status/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af986-156">Refer to  [Microsoft Edge platform status](https://developer.microsoft.com/microsoft-edge/platform/status/) for the official word on feature support.</span></span>

<iframe height='559' scrolling='no' title='<span data-ttu-id="af986-157">EdgeHTML 16 の新しい Api</span><span class="sxs-lookup"><span data-stu-id="af986-157">New APIs in EdgeHTML 16</span></span>' src='//codepen.io/MSEdgeDev/embed/jLGZZY/?height=559&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'><span data-ttu-id="af986-158"><a href='https://codepen.io/MSEdgeDev/pen/jLGZZY/'>EdgeHTML 16 </a> x MSEdgeDev (@MSEdgeDev) の Pen 新しい api <a href='https://codepen.io/MSEdgeDev'> を </a> CodePen で <a href='https://codepen.io'> </a> 参照してください。</span><span class="sxs-lookup"><span data-stu-id="af986-158">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/jLGZZY/'>New APIs in EdgeHTML 16</a>by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe></p>

<h2 id="previous-edgehtml-releases"><span data-ttu-id="af986-159">以前の EdgeHTML リリース</span><span class="sxs-lookup"><span data-stu-id="af986-159">Previous EdgeHTML releases</span></span></h2>
<p><a href="https://aka.ms/devguide_edgehtml_12" data-raw-source="[EdgeHTML 12 / Windows build 10240 (7/2015)](https://aka.ms/devguide_edgehtml_12)"><span data-ttu-id="af986-160">EdgeHTML 12/Windows ビルド 10240 (7/2015)</span><span class="sxs-lookup"><span data-stu-id="af986-160">EdgeHTML 12 / Windows build 10240 (7/2015)</span></span></a>

[<span data-ttu-id="af986-161">EdgeHTML 13/Windows ビルド 10586 (11/2015)</span><span class="sxs-lookup"><span data-stu-id="af986-161">EdgeHTML 13 / Windows build 10586 (11/2015)</span></span>](https://aka.ms/devguide_edgehtml_13)

[<span data-ttu-id="af986-162">EdgeHTML 14/Windows ビルド 14393 (8/2016)</span><span class="sxs-lookup"><span data-stu-id="af986-162">EdgeHTML 14 / Windows build 14393 (8/2016)</span></span>](https://aka.ms/devguide_edgehtml_14)

[<span data-ttu-id="af986-163">EdgeHTML 15/Windows ビルド 15063 (4/2017)</span><span class="sxs-lookup"><span data-stu-id="af986-163">EdgeHTML 15 / Windows build 15063 (4/2017)</span></span>](https://aka.ms/devguide_edgehtml_15)
