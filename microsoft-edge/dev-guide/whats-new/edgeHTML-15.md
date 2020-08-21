---
description: このガイドでは、EdgeHTML 15 に含まれている開発者の機能と標準の概要を示します。
title: EdgeHTML 15 の新機能と API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、Web 開発、html、cs、javascript、開発者
ms.custom: seodec18
ms.openlocfilehash: 4febe4be1fce29207de7a57b61d96eae0a5c02ab
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941919"
---
# <span data-ttu-id="85a91-104">Microsoft EdgeHTML 15 の新機能</span><span class="sxs-lookup"><span data-stu-id="85a91-104">What's new in EdgeHTML 15</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="85a91-105">[Windows 10 Creators Update](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) \(04/2017, ビルド 15063\) に含めた変更は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="85a91-105">Here are the changes shipped with the current release of the Microsoft Edge platform, as of the [Windows 10 Creators Update](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) \(04/2017, Build 15063\).</span></span>  <span data-ttu-id="85a91-106">Microsoft Edge ブラウザー全体の変更の概要については [、Windows 10 Creators Update の Microsoft Edge の新機能をご覧ください](https://blogs.windows.com/msedgedev/2017/04/11)。</span><span class="sxs-lookup"><span data-stu-id="85a91-106">For an overview of changes to the overall Microsoft Edge browser, see [What's new in Microsoft Edge in the Windows 10 Creators Update](https://blogs.windows.com/msedgedev/2017/04/11).</span></span>  

<span data-ttu-id="85a91-107">以降の Windows Insider Preview ビルドの変更については [、EdgeHTML の新機能を参照してください](../whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="85a91-107">For changes in subsequent Windows Insider Preview builds, see [What's New in EdgeHTML](../whats-new.md).</span></span>  

<span data-ttu-id="85a91-108">次の一覧を行うと、この機能が利用できます  [https://aka.ms/devguide_edgehtml_15](./edgehtml-15.md) 。</span><span class="sxs-lookup"><span data-stu-id="85a91-108">Here's the permalink for the following list of changes:  [https://aka.ms/devguide_edgehtml_15](./edgehtml-15.md).</span></span>  

## <span data-ttu-id="85a91-109">新機能</span><span class="sxs-lookup"><span data-stu-id="85a91-109">New features</span></span>  

### <span data-ttu-id="85a91-110">CSS カスタム プロパティ</span><span class="sxs-lookup"><span data-stu-id="85a91-110">CSS Custom Properties</span></span>  

<span data-ttu-id="85a91-111">Microsoft Edge では [、CSS](https://drafts.csswg.org/css-variables)のカスタム プロパティ (A.k.a CSS 変数) がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="85a91-111">Microsoft Edge now supports [CSS Custom Properties](https://drafts.csswg.org/css-variables), a.k.a CSS Variables.</span></span>  <span data-ttu-id="85a91-112">CSS 変数を使用すると、スタイルシート全体で再利用できるカスタム CSS プロパティを作成して、繰り返しカラーなど、重複データの量を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="85a91-112">CSS Variables allow you to create custom CSS properties that can be reused throughout stylesheets to help reduce the amount of duplicate data, like repeated colors.</span></span>  <span data-ttu-id="85a91-113">CSS 変数は簡単に使用できます。</span><span class="sxs-lookup"><span data-stu-id="85a91-113">Using CSS Variables is simple:</span></span>  

```css
/* define a custom property by using two dashes and assign it a value */
body {   
   --default-color: #3390b1
}

/* reference it in your stylesheet with the "var()" function */
h1 {
   color: var(--default-color);
}
```  

### <span data-ttu-id="85a91-114">Intersection Observer</span><span class="sxs-lookup"><span data-stu-id="85a91-114">Intersection Observer</span></span>  

<span data-ttu-id="85a91-115">EdgeHTML 15 では [、Intersection Observer API](https://w3c.github.io/IntersectionObserver) の指定が追加されました。</span><span class="sxs-lookup"><span data-stu-id="85a91-115">EdgeHTML 15 introduces the [Intersection Observer API](https://w3c.github.io/IntersectionObserver) specification.</span></span>  <span data-ttu-id="85a91-116">Intersection Observer API を使用すると、他の要素またはグローバル ビューポートとの間で DOM 要素の位置と表示を非同期で実行できます。</span><span class="sxs-lookup"><span data-stu-id="85a91-116">The Intersection Observer API allows you to asynchronously query the position and visibility of DOM elements relative to other elements or the global viewport.</span></span>  <span data-ttu-id="85a91-117">この API では、ユーザーがビューにいるときに要素を効果的に知らすための方法を作成することで、カスタムの経用コードが必要なくなります。</span><span class="sxs-lookup"><span data-stu-id="85a91-117">This API eliminates the need for custom expensive code by creating a method to efficiently notify elements when they are in view.</span></span>  

### <span data-ttu-id="85a91-118">JavaScript</span><span class="sxs-lookup"><span data-stu-id="85a91-118">JavaScript</span></span>  

<span data-ttu-id="85a91-119">Chakra JavaScript エンジンの EdgeHTML 15 Reva によってパフォーマンス最適化が行われます。</span><span class="sxs-lookup"><span data-stu-id="85a91-119">Performance optimizations take center stage with the EdgeHTML 15 rev of the Chakra JavaScript engine.</span></span>  <span data-ttu-id="85a91-120">Windows 10 Creators Update では、Chakra は関数を再度段階的に定義し、ヒープ引数を最適化することでメモリを保存し、ミニされたコードのパフォーマンスを改善します。</span><span class="sxs-lookup"><span data-stu-id="85a91-120">With the Windows 10 Creators Update, Chakra saves memory by re-deferring functions and optimizing away heap arguments and improves performance for minified code.</span></span>  

<span data-ttu-id="85a91-121">さらに、Microsoft EdgeHTML 15 では、次の機能プレビューが追加されました。</span><span class="sxs-lookup"><span data-stu-id="85a91-121">Additionally, EdgeHTML 15 introduces the following feature previews:</span></span>  

#### <span data-ttu-id="85a91-122">実用 JavaScript 機能</span><span class="sxs-lookup"><span data-stu-id="85a91-122">Experimental JavaScript features</span></span>  

<span data-ttu-id="85a91-123">有効</span><span class="sxs-lookup"><span data-stu-id="85a91-123">Enabled with</span></span> `about:flags`  

*   <span data-ttu-id="85a91-124">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) \([デモ](https://webassembly.org/demo)ル \)</span><span class="sxs-lookup"><span data-stu-id="85a91-124">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) \([demo](https://webassembly.org/demo)\)</span></span>  
*   [<span data-ttu-id="85a91-125">共有メモリとアトミックス</span><span class="sxs-lookup"><span data-stu-id="85a91-125">Shared Memory and Atomics</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

<span data-ttu-id="85a91-126">[詳細については、Microsoft Edge で JavaScript のパフォーマンス、WebAssembly、共有メモ](https://blogs.windows.com/msedgedev/2017/04/20)リを改善して詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="85a91-126">See [Improved JavaScript performance, WebAssembly, and Shared Memory in Microsoft Edge](https://blogs.windows.com/msedgedev/2017/04/20) for further details.</span></span>  

### <span data-ttu-id="85a91-127">支払い要求 API</span><span class="sxs-lookup"><span data-stu-id="85a91-127">Payment Request API</span></span>  

<span data-ttu-id="85a91-128">[Payment Request API](https://w3.org/TR/payment-request)がサポートされるようになりました。Windows 10 PC およびスマートフォンで Web 上で簡単なチェックアウトと支払いを有効にできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="85a91-128">The [Payment Request API](https://w3.org/TR/payment-request) is now supported, enabling simpler checkout and payments on the web on Windows 10 PCs and Phones.</span></span>  <span data-ttu-id="85a91-129">この API により、Microsoft Edge は、クラウドに保存されている一部のコンシューマー、コンシューマー、支払方法 \(クレジット カード\) 間の中間として機能します。</span><span class="sxs-lookup"><span data-stu-id="85a91-129">This API enables Microsoft Edge to act as an intermediary between merchants, consumers, and the payment methods \(such as credit cards\) that consumers have stored in the cloud.</span></span>  <span data-ttu-id="85a91-130">支払い要求 API の詳細については、シンプルな Web ペイリングを [確認してください。支払要求 API と](https://blogs.windows.com/msedgedev/2016/12/15) [Payment Request API 開発者ガイドの](/microsoft-edge/dev-guide/device/payment-request-api) 説明を追加してください。</span><span class="sxs-lookup"><span data-stu-id="85a91-130">For more information on the Payment Request API, check out [Simpler web payments: Introducing the Payment Request API](https://blogs.windows.com/msedgedev/2016/12/15) and the [Payment Request API](/microsoft-edge/dev-guide/device/payment-request-api) developer guide.</span></span>  

### <span data-ttu-id="85a91-131">TCP ファースト オープン (TFO)</span><span class="sxs-lookup"><span data-stu-id="85a91-131">TCP Fast Open (TFO)</span></span>  
<span data-ttu-id="85a91-132">TCP ファースト オープンは、ブラウザー ネットワークのパフォーマンスを向上させるために必要なラウンド トリップの数を減らす機能です。</span><span class="sxs-lookup"><span data-stu-id="85a91-132">TCP Fast Open is a feature that reduces the number of round trips required to open a TCP connection, improving browser networking performance.</span></span>  <span data-ttu-id="85a91-133">[詳細については、TCP ファ](https://blogs.windows.com/msedgedev/2016/06/15)ースト オープンを使用して、高速でより高度な Web を構築してください。</span><span class="sxs-lookup"><span data-stu-id="85a91-133">For more details, see [Building a faster and more secure web with TCP Fast Open](https://blogs.windows.com/msedgedev/2016/06/15).</span></span>  <span data-ttu-id="85a91-134">ネットワーク トポロジの不整合のため、Microsoft Edge では、この機能は既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="85a91-134">Due to interoperability differences in various network topologies, this features is not enabled by default in Microsoft Edge.</span></span>  <span data-ttu-id="85a91-135">これを有効にするには、アドレス バーに入力し、[ `about:flags` **ネットワーク] セクションの下にある [TCP ファーストオーストを有効** にする] チェック ボックスを **オンに** します。</span><span class="sxs-lookup"><span data-stu-id="85a91-135">To enable it, type `about:flags` in your address bar, and select the checkbox for **Enable TCP Fast Open** under the **Networking** section.</span></span>  

### <span data-ttu-id="85a91-136">WebRTC と操作可能な RTC ビデオ コーデック サポート</span><span class="sxs-lookup"><span data-stu-id="85a91-136">WebRTC and interoperable RTC video codec support</span></span>  

<span data-ttu-id="85a91-137">Microsoft EDGEHTML 15 は、以前のバージョンの W3C WebRTC-PC API 円で作成されたアプリケーションとの互換性を保つために、WebRTC 1.0 API のサブセットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="85a91-137">EdgeHTML 15 supports a subset of the WebRTC 1.0 API for interoperability with applications built with earlier versions of the W3C WebRTC-PC API circa 2015.</span></span>  <span data-ttu-id="85a91-138">[詳細については、WebRTC API リ](/previous-versions//mt806139(v=vs.85))ファレンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="85a91-138">See the [WebRTC API reference](/previous-versions//mt806139(v=vs.85)) for details.</span></span>  

<span data-ttu-id="85a91-139">ピア間の音声とビデオ通信で最も高度な機能を活用するには [、Object Real-Time Communication) API を使用することをお勧めします](https://ortc.org)。</span><span class="sxs-lookup"><span data-stu-id="85a91-139">To take advantage of our most advanced features in peer-to-peer audio and video communication, we recommend using the [Object Real-Time Communication) API](https://ortc.org).</span></span>  <span data-ttu-id="85a91-140">ORTC API は、グループの音声通話やビデオ通話をセットアップする場合や、個々のトランスポート、送信者、受信者オブジェクトを直接制御する必要がある場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="85a91-140">The ORTC API is better suited for situations where you want to set up group audio and video calls, or directly control individual transport, sender, and receiver objects.</span></span>  

<span data-ttu-id="85a91-141">Microsoft Edge は、ORTC と WebRTC 1.0 が付いた H.264/AVC と VP8 のビデオの両方をサポートしており、両方のコーデックの種類 ([送信](https://webrtc.org/experiments/rtp-hdrext/abs-send-time)時、[良](https://tools.ietf.org/html/draft-alvestrand-rmcat-remb-03)いリマブ、画像損失インジケーションと[汎用 NACK フィードバック](https://tools.ietf.org/html/rfc4585)[、RTP リミュ](https://tools.ietf.org/html/rfc4588)ーション) のサポートに対応しています。</span><span class="sxs-lookup"><span data-stu-id="85a91-141">The Microsoft Edge supports both H.264/AVC and VP8 video with ORTC and WebRTC 1.0, and provides the following features in support of both codec types: [abs-send-time](https://webrtc.org/experiments/rtp-hdrext/abs-send-time), [goog-remb](https://tools.ietf.org/html/draft-alvestrand-rmcat-remb-03), [Picture Loss Indication and Generic NACK feedback](https://tools.ietf.org/html/rfc4585), [RTP Retransmission](https://tools.ietf.org/html/rfc4588).</span></span>  

<span data-ttu-id="85a91-142">詳細については、Microsoft Edge で [WebRTC 1.0 の概要と、WebRTC の](https://blogs.windows.com/msedgedev/2017/01/31)知識ややすいリアルタイム通信を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85a91-142">For more info, see [Introducing WebRTC 1.0 and interoperable real-time communications in Microsoft Edge](https://blogs.windows.com/msedgedev/2017/01/31).</span></span>  

### <span data-ttu-id="85a91-143">WebVR</span><span class="sxs-lookup"><span data-stu-id="85a91-143">WebVR</span></span>  

<span data-ttu-id="85a91-144">Microsoft Edge では [、Windows](https://immersive-web.github.io/webxr)Mixed Reality Headed ディスプレイと Microsoft Edge を接続する実用的 API をサポートできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="85a91-144">Microsoft Edge now has support for [WebVR](https://immersive-web.github.io/webxr), an experimental API that connects Windows Mixed Reality head mounted displays and Microsoft Edge.</span></span>  <span data-ttu-id="85a91-145">この接続により、VR コンテンツは Web サイト内での経験ができるため、VR エクスペリエンスが高いデスクトップ アプリケーションに制限がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="85a91-145">This connection enables VR content to be experienced within a website, meaning immersive VR experiences are no longer limited to desktop applications.</span></span>  

<span data-ttu-id="85a91-146">Microsoft Edge の仮想リアルティは WebGL を利用しています。これは WebGL を利用することで、3D グラフィックと 2D グラフィックをレンダリングするための JavaScript API。</span><span class="sxs-lookup"><span data-stu-id="85a91-146">Virtual reality in Microsoft Edge is powered by WebGL, a JavaScript API for rendering 3D and 2D graphics.</span></span>  <span data-ttu-id="85a91-147">WebGL ライブラリ (BabylonJS など) ライブラリで作成された WebGL アプリケーションとアプリケーションがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="85a91-147">WebGL applications and applications built with WebGL libraries like BabylonJS are supported.</span></span>  <span data-ttu-id="85a91-148">接続すると、WebVR はヘッドセットの位置と上下に表示される位置と情報を視覚的に送信します。</span><span class="sxs-lookup"><span data-stu-id="85a91-148">Once connected, WebVR sends visuals corresponding to the position and sensor information around the headset.</span></span>  <span data-ttu-id="85a91-149">WebVR API は、ゲームパッド API の拡張機能にかかって、バティカル コントローラ [ーもサポートしています](../dom/gamepad-api.md)。</span><span class="sxs-lookup"><span data-stu-id="85a91-149">The WebVR API also supports spatial controllers thanks to an extension to the [Gamepad API](../dom/gamepad-api.md).</span></span>  <span data-ttu-id="85a91-150">この API は既定でオンになっているため、フラグを切り替えなくてもかなりません。</span><span class="sxs-lookup"><span data-stu-id="85a91-150">This API is on by default, so no need to toggle a flag.</span></span>  

<span data-ttu-id="85a91-151">詳細 [については、WebVR API](/previous-versions//mt806281(v=vs.85)) リファレ [ンスとゲームパッド API リファレン](https://developer.mozilla.org/docs/Web/API/Gamepad_API) スを参照してください。</span><span class="sxs-lookup"><span data-stu-id="85a91-151">See the [WebVR API reference](/previous-versions//mt806281(v=vs.85)) and [Gamepad API reference](https://developer.mozilla.org/docs/Web/API/Gamepad_API) for details.</span></span>  

 > [!NOTE] 
 > <span data-ttu-id="85a91-152">WebVR の速度は開発中であるため、Microsoft Edge の実装は後で行直す場合があります。</span><span class="sxs-lookup"><span data-stu-id="85a91-152">Since the WebVR spec is still in development, Microsoft Edge's implementation may change later down the line.</span></span>  

## <span data-ttu-id="85a91-153">更新された機能</span><span class="sxs-lookup"><span data-stu-id="85a91-153">Updated features</span></span>  

### <span data-ttu-id="85a91-154">コンテンツ セキュリティ ポリシー (レベル 2)</span><span class="sxs-lookup"><span data-stu-id="85a91-154">Content Security Policy (Level 2)</span></span>  

<span data-ttu-id="85a91-155">既に CSP 1 を使用しているサイトは、CSP 2 の Microsoft Edge サポートに連絡する必要がありますが、ワーカー スクリプトを読み込むディレクティブを、現在のサイトの正しい正常性に向けて新しいディレクティブ `frame-src` `child-src` に切り替えることをおすすめします。</span><span class="sxs-lookup"><span data-stu-id="85a91-155">Sites already using CSP 1 should continue to work with Microsoft Edge support for CSP 2, however it's best to switch any `frame-src` directives that load worker scripts to the new `child-src` directive to future-proof your site.</span></span>  <span data-ttu-id="85a91-156">\(CSP 3 では `frame-src` 、workers.\) CSP 2 にも次の情報が追加されます。</span><span class="sxs-lookup"><span data-stu-id="85a91-156">\(In CSP 3, `frame-src` will no longer apply to workers.\) CSP 2 also adds the following:</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="85a91-157">新しいダイレクト</span><span class="sxs-lookup"><span data-stu-id="85a91-157">New directives</span></span>  
   :::column-end:::
   :::column span="2":::
      `base-uri`<span data-ttu-id="85a91-158">、 `child-src` `form-action` および `frame-ancestors` `plugin-types` .</span><span class="sxs-lookup"><span data-stu-id="85a91-158">, `child-src`, `form-action`, `frame-ancestors` and `plugin-types`.</span></span>  <span data-ttu-id="85a91-159">[詳細については、Microsoft Edge で CSP ディレクティブをサポート](../security/content-security-policy.md)している Microsoft Edge を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85a91-159">See [Microsoft Edge supported CSP directives](../security/content-security-policy.md) for more.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="85a91-160">作業者のサポート</span><span class="sxs-lookup"><span data-stu-id="85a91-160">Workers support</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="85a91-161">バックグラウンド ワーカー スクリプトは、ドキュメントの読み込みポリシーとは別に、それぞれのポリシーによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="85a91-161">Background worker scripts are governed by their own policy, separate from the policy of the document loading them.</span></span>  <span data-ttu-id="85a91-162">ホスト ドキュメントと同じように、応答ヘッダーに作業者の CSP を設定できます。</span><span class="sxs-lookup"><span data-stu-id="85a91-162">As with host documents, you can set the CSP for a worker in the response header.</span></span>  <span data-ttu-id="85a91-163">また、CSP 2 の新機能は、ワーカー スレッドの作成に影響を与える  `allow-scripts` `allow-same-origin` `sandbox` ことです。</span><span class="sxs-lookup"><span data-stu-id="85a91-163">Also new in CSP 2 is that  `allow-scripts` and `allow-same-origin` flags of the `sandbox` directive now affect worker thread creation.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="85a91-164">インライン スクリプトとスタイル</span><span class="sxs-lookup"><span data-stu-id="85a91-164">Inline scripts and styles</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="85a91-165">CSP 2 では、ニーズとハッシュをホワイトリスト メカニズムとして指定することで、インライン スクリプトとスタイルのブロックの実行を行えます。</span><span class="sxs-lookup"><span data-stu-id="85a91-165">CSP 2 allows for the execution of inline scripts and style blocks by providing nonces and hashes as a whitelisting mechanism.</span></span>  <span data-ttu-id="85a91-166">Nonce は、各ページ読み込みに対して生成されるランダム 64 値であり、ページ内のスクリプト タグの両方に表示されます。</span><span class="sxs-lookup"><span data-stu-id="85a91-166">Nonces are random base-64 values generated on each page load that appears in both the CSP policy and in the script tags in the page.</span></span>  <span data-ttu-id="85a91-167">ページが読み込みで動的に生成されると、サーバーは nonce 値を生成し、ページに NonceToken に挿入し、コンテンツ セキュリティ ポリシーの HTTP ヘッダーでも説明します。</span><span class="sxs-lookup"><span data-stu-id="85a91-167">When the page is dynamically generated on load, the server generates a nonce value, inserts it into the NonceToken in the page and also declares it in the Content Security Policy HTTP header.</span></span>  <span data-ttu-id="85a91-168">ハッシュは、CSP ポリシーで `<script>` `<style>` \(または `script-src` directives\) を指定したコンテンツから生き出される統計値 `style-src` です。</span><span class="sxs-lookup"><span data-stu-id="85a91-168">Hashes are static values generated \(via sha256, sha384 or sha512 algorithms\) from the content of a `<script>` or `<style>` element that are then specified \(via `script-src` or `style-src` directives\) in the CSP policy.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="85a91-169">CSP のバリオのレポート</span><span class="sxs-lookup"><span data-stu-id="85a91-169">CSP violation reporting</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="85a91-170">新しいイベントは CSP の休文 `SecurityPolicyViolationEvent` に送信されました。</span><span class="sxs-lookup"><span data-stu-id="85a91-170">A new event, `SecurityPolicyViolationEvent` is now fired upon CSP violations.</span></span>  <span data-ttu-id="85a91-171">CSP レポートの以前のメカニスムは引き `report-uri` 続きサポートされます。</span><span class="sxs-lookup"><span data-stu-id="85a91-171">The earlier mechanism for CSP reporting, `report-uri`, continues to be supported.</span></span>  <span data-ttu-id="85a91-172">いくつかの新しいフィールドが `effectiveDirective` 、\(違う/ポリシーが違う `statusCode` )、\(HTTP 応答コード\)、\(オフロンド リソースの URL の URL) など、両方に共通する休末報告書に `sourceFile` `lineNumber` いくつかの新しいフィールドが追加されています `columnNumber` 。</span><span class="sxs-lookup"><span data-stu-id="85a91-172">Several new fields have been added to the violation reports common to both, including `effectiveDirective` \(the policy that was violated\), `statusCode` \(the HTTP response code\), `sourceFile` \(the URL of the offending resource\), `lineNumber`, and `columnNumber`.</span></span>  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="85a91-173">Web 認証</span><span class="sxs-lookup"><span data-stu-id="85a91-173">Web Authentication</span></span>  

<span data-ttu-id="85a91-174">[Windows Hello](https://www.microsoft.com/windows/comprehensive-security)の生き出[しを使用した EPI](../device/web-authentication.md)のサポートが、次の変更に加えました。</span><span class="sxs-lookup"><span data-stu-id="85a91-174">Microsoft Edge support for the emerging [Web Authentication API](../device/web-authentication.md) using [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) biometrics has been updated with the following changes:</span></span>  

*   <span data-ttu-id="85a91-175">[EdgeHTML 14](https://blogs.windows.com/msedgedev/2016/08/04)での実用 Web 認証 API の初期実装は、MS-- プレフィックス付き API [\(MSCredentials](/previous-versions//mt697639(v=vs.85))インターフェイス\) によって展開されています。</span><span class="sxs-lookup"><span data-stu-id="85a91-175">The initial implementation of the experimental Web Authentication API introduced in [EdgeHTML 14](https://blogs.windows.com/msedgedev/2016/08/04) \(Windows 10 Anniversary Update, build 10240, 7/2016\) was exposed through MS- prefixed APIs \(the [MSCredentials](/previous-versions//mt697639(v=vs.85)) interface\).</span></span>  <span data-ttu-id="85a91-176">これらの API は Microsoft EdgeHTML 15 でも引き続き使用できますが、定義の最近のスナップショットで定義されている非定義の標準 API と動作の基本で廃止され、標準[recent snapshot](https://w3.org/TR/2016/WD-webauthn-20160928)化に向けて速度の高さが向上するため、そのように継続的に変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="85a91-176">While these APIs are still available in EdgeHTML 15, they are now deprecated in favor of the non-prefixed, standards-based APIs and behaviors defined in a more [recent snapshot](https://w3.org/TR/2016/WD-webauthn-20160928) of the specification, and are likely to continue changing as the spec matures toward standardization.</span></span>  

*   <span data-ttu-id="85a91-177">既定では、Microsoft Edge の実装は既定では無効になっており、フラグ \の後で出荷されます (この機能を `about:flags` 有効にするにはアドレス バーに入力してください)。</span><span class="sxs-lookup"><span data-stu-id="85a91-177">The latest Microsoft Edge implementation is turned off by default and ships behind a flag \(type `about:flags` in your address bar to turn on the feature\).</span></span>  

*   <span data-ttu-id="85a91-178">Microsoft Edge では、USB キーやデバイスなどの外部資ーデ資BluetoothはまだBluetoothいません。</span><span class="sxs-lookup"><span data-stu-id="85a91-178">Microsoft Edge does not yet support external credentials like USB keys or Bluetooth devices.</span></span>  <span data-ttu-id="85a91-179">現在の API は TPM に保存されている埋め込み資ーデンシャルに限定されます。</span><span class="sxs-lookup"><span data-stu-id="85a91-179">The current API is limited to embedded credentials stored in the TPM.</span></span>  <span data-ttu-id="85a91-180">デバイスで TPM を利用できない場合、ソフトウェア フォールバックが使用されます。</span><span class="sxs-lookup"><span data-stu-id="85a91-180">A software fallback is used if TPM is not available on the device.</span></span>  

*   <span data-ttu-id="85a91-181">Windows ユーザー アカウントに現在ログインしている場合は、PIN をサポートしており、少なくとも、対面または指紋のバリックスを必要とする必要があります。</span><span class="sxs-lookup"><span data-stu-id="85a91-181">The currently logged in Windows user account must be configured to support at least a PIN, and preferably face or fingerprint biometrics.</span></span>  <span data-ttu-id="85a91-182">これは、Windows が TPM へのアクセスを認証できるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="85a91-182">This is to ensure that Windows can authenticate the access to the TPM.</span></span>  

*   <span data-ttu-id="85a91-183">この時 [点では](https://w3.org/TR/webauthn/#extension-predef) 、Microsoft Edge では [FIDO AppId](https://w3.org/TR/webauthn/#extension-appid) \(\) のみ `webauthn_txAuthSimple` をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="85a91-183">Of the [predefined extensions](https://w3.org/TR/webauthn/#extension-predef) described in the spec, Microsoft Edge only supports the [FIDO AppId](https://w3.org/TR/webauthn/#extension-appid) \(`webauthn_txAuthSimple`\) at this time.</span></span>  

*  <span data-ttu-id="85a91-184">現在 `timeoutSeconds` 、オプションは評価されていません</span><span class="sxs-lookup"><span data-stu-id="85a91-184">The `timeoutSeconds` option is not currently evaluated</span></span>  

### <span data-ttu-id="85a91-185">WebDriver</span><span class="sxs-lookup"><span data-stu-id="85a91-185">WebDriver</span></span>  

<span data-ttu-id="85a91-186">Microsoft EdgeHTML 15 では、サイレント コマンド ライン フラグや新しいコマンド エンドポイントのサポートなど、WebDriver の更新プログラムを一部の WebDriver の更新プログラムで利用できます。</span><span class="sxs-lookup"><span data-stu-id="85a91-186">EdgeHTML 15 brings a handful of WebDriver updates including support for the silent command line flag and new command endpoints:</span></span>  

| <span data-ttu-id="85a91-187">メソッド</span><span class="sxs-lookup"><span data-stu-id="85a91-187">Method</span></span> | <span data-ttu-id="85a91-188">URI テンプレート</span><span class="sxs-lookup"><span data-stu-id="85a91-188">URI Template</span></span> | <span data-ttu-id="85a91-189">コマンド</span><span class="sxs-lookup"><span data-stu-id="85a91-189">Command</span></span> |  
|:--- |:---  |:--- |    
| <span data-ttu-id="85a91-190">POST</span><span class="sxs-lookup"><span data-stu-id="85a91-190">POST</span></span> | <span data-ttu-id="85a91-191">/session/{session id}/alert/accept</span><span class="sxs-lookup"><span data-stu-id="85a91-191">/session/{session id}/alert/accept</span></span> | [<span data-ttu-id="85a91-192">通知を承諾する</span><span class="sxs-lookup"><span data-stu-id="85a91-192">Accept Alert</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-accept-alert) |  
| <span data-ttu-id="85a91-193">POST</span><span class="sxs-lookup"><span data-stu-id="85a91-193">POST</span></span> | <span data-ttu-id="85a91-194">/session/{session id}/alert/dismiss</span><span class="sxs-lookup"><span data-stu-id="85a91-194">/session/{session id}/alert/dismiss</span></span> | [<span data-ttu-id="85a91-195">アラートを削除する</span><span class="sxs-lookup"><span data-stu-id="85a91-195">Dismiss Alert</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-dismiss-alert) |  
| <span data-ttu-id="85a91-196">GET</span><span class="sxs-lookup"><span data-stu-id="85a91-196">GET</span></span> | <span data-ttu-id="85a91-197">/session/{session id}/alert/text</span><span class="sxs-lookup"><span data-stu-id="85a91-197">/session/{session id}/alert/text</span></span> | [<span data-ttu-id="85a91-198">通知テキストを取得する</span><span class="sxs-lookup"><span data-stu-id="85a91-198">Get Alert Text</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-alert-text) |  
| <span data-ttu-id="85a91-199">POST</span><span class="sxs-lookup"><span data-stu-id="85a91-199">POST</span></span> | <span data-ttu-id="85a91-200">/session/{session id}/alert/text</span><span class="sxs-lookup"><span data-stu-id="85a91-200">/session/{session id}/alert/text</span></span> | [<span data-ttu-id="85a91-201">通知テキストを送信する</span><span class="sxs-lookup"><span data-stu-id="85a91-201">Send Alert Text</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-send-alert-text) |  
| <span data-ttu-id="85a91-202">POST</span><span class="sxs-lookup"><span data-stu-id="85a91-202">POST</span></span> | <span data-ttu-id="85a91-203">/session/{session id}/execute/async</span><span class="sxs-lookup"><span data-stu-id="85a91-203">/session/{session id}/execute/async</span></span> | [<span data-ttu-id="85a91-204">非同期スクリプトの実行</span><span class="sxs-lookup"><span data-stu-id="85a91-204">Execute Async Script</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-async-script) |  
| <span data-ttu-id="85a91-205">POST</span><span class="sxs-lookup"><span data-stu-id="85a91-205">POST</span></span> | <span data-ttu-id="85a91-206">/session/{session id}/execute/sync</span><span class="sxs-lookup"><span data-stu-id="85a91-206">/session/{session id}/execute/sync</span></span> | [<span data-ttu-id="85a91-207">スクリプトの実行</span><span class="sxs-lookup"><span data-stu-id="85a91-207">Execute Script</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-script) |  
| <span data-ttu-id="85a91-208">GET</span><span class="sxs-lookup"><span data-stu-id="85a91-208">GET</span></span> | <span data-ttu-id="85a91-209">/session/{session id}/window</span><span class="sxs-lookup"><span data-stu-id="85a91-209">/session/{session id}/window</span></span> | [<span data-ttu-id="85a91-210">ウィンドウ ハンドルを入手する</span><span class="sxs-lookup"><span data-stu-id="85a91-210">Get Window Handle</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#get-window-handle) |  
| <span data-ttu-id="85a91-211">GET</span><span class="sxs-lookup"><span data-stu-id="85a91-211">GET</span></span> | <span data-ttu-id="85a91-212">/session/{session id}/window/handles</span><span class="sxs-lookup"><span data-stu-id="85a91-212">/session/{session id}/window/handles</span></span> | [<span data-ttu-id="85a91-213">ウィンドウ ハンドルを入手する</span><span class="sxs-lookup"><span data-stu-id="85a91-213">Get Window Handles</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-window-handles) |  

<span data-ttu-id="85a91-214">WebDriver のその他の機能の詳細と状態については、WebDriver [を参照してください](../../webdriver.md)。</span><span class="sxs-lookup"><span data-stu-id="85a91-214">For more info and the status of other WebDriver features, check out [WebDriver](../../webdriver.md).</span></span>  

## <span data-ttu-id="85a91-215">EdgeHTML 15 の新しい API</span><span class="sxs-lookup"><span data-stu-id="85a91-215">New APIs in EdgeHTML 15</span></span>  

<span data-ttu-id="85a91-216">EdgeHTML 15 の新しい API の完全な一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="85a91-216">Here's the full list of new APIs in EdgeHTML 15.</span></span>  <span data-ttu-id="85a91-217">これらは形式で表示されます `[interface name].[api name]` 。</span><span class="sxs-lookup"><span data-stu-id="85a91-217">They are listed in the format of `[interface name].[api name]`.</span></span>  

<iframe height='582' scrolling='no' title='<span data-ttu-id="85a91-218">New EdgeHTML15 API</span><span class="sxs-lookup"><span data-stu-id="85a91-218">New EdgeHTML15 APIs</span></span>' src='//codepen.io/MicrosoftEdgeDocumentation/embed/evRjjZ/?height=582&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="85a91-219"><a href='http://codepen.io/MicrosoftEdgeDocumentation/pen/evRjjZ/'> </a> CodePen で、Microsoft Edge Docs (新しい EdgeHTML15 API <a href='http://codepen.io/MicrosoftEdgeDocumentation'> </a> @MicrosoftEdgeDocumentation) <a href='http://codepen.io'> を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="85a91-219">See the Pen <a href='http://codepen.io/MicrosoftEdgeDocumentation/pen/evRjjZ/'>New EdgeHTML15 APIs</a> by Microsoft Edge Docs (<a href='http://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='http://codepen.io'>CodePen</a>.</span></span></iframe>  

## <span data-ttu-id="85a91-220">以前の EdgeHTML リリース</span><span class="sxs-lookup"><span data-stu-id="85a91-220">Previous EdgeHTML releases</span></span>  

[<span data-ttu-id="85a91-221">Microsoft EdgeHTML 12 / Windows ビルド 10240 (7/2015)</span><span class="sxs-lookup"><span data-stu-id="85a91-221">EdgeHTML 12 / Windows build 10240 (7/2015)</span></span>](./edgehtml-12.md)  

[<span data-ttu-id="85a91-222">Microsoft EdgeHTML 13 / Windows ビルド 10586 (2015/11)</span><span class="sxs-lookup"><span data-stu-id="85a91-222">EdgeHTML 13 / Windows build 10586 (11/2015)</span></span>](./edgehtml-13.md)  

[<span data-ttu-id="85a91-223">EdgeHTML 14 / Windows ビルド 14393 (8/2016)</span><span class="sxs-lookup"><span data-stu-id="85a91-223">EdgeHTML 14 / Windows build 14393 (8/2016)</span></span>](./edgehtml-14.md)  
