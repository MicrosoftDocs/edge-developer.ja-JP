---
description: このガイドでは、EdgeHTML 15 に含まれている開発者向けの機能と標準の概要について説明します。
title: EdgeHTML 15 の新機能と Api
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/02/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.custom: seodec18
ms.openlocfilehash: 4fd0bbc06d27bace424ea99cfe9941aabc737fee
ms.sourcegitcommit: 204a284e21bf2da5cdc862c5e8b5839245abbbbc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "11094362"
---
# <span data-ttu-id="1afe9-104">EdgeHTML 15 の新機能</span><span class="sxs-lookup"><span data-stu-id="1afe9-104">What's new in EdgeHTML 15</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="1afe9-105">Microsoft Edge プラットフォームの現在のリリースで出荷された変更については、 [Windows 10](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) の作成者による更新 (04/2017、ビルド 15063 \) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1afe9-105">Here are the changes shipped with the current release of the Microsoft Edge platform, as of the [Windows 10 Creators Update](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) \(04/2017, Build 15063\).</span></span>  <span data-ttu-id="1afe9-106">Microsoft Edge ブラウザー全体の変更の概要については、「Windows 10 の作成者による [Microsoft edge の新機能](https://blogs.windows.com/msedgedev/2017/04/11)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1afe9-106">For an overview of changes to the overall Microsoft Edge browser, see [What's new in Microsoft Edge in the Windows 10 Creators Update](https://blogs.windows.com/msedgedev/2017/04/11).</span></span>  

<span data-ttu-id="1afe9-107">以降の Windows Insider Preview ビルドでの変更については、「 [EdgeHTML の新機能](../whats-new.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1afe9-107">For changes in subsequent Windows Insider Preview builds, see [What's New in EdgeHTML](../whats-new.md).</span></span>  

<span data-ttu-id="1afe9-108">次の変更の固定リンクを示し  [https://aka.ms/devguide_edgehtml_15](./edgehtml-15.md) ます。</span><span class="sxs-lookup"><span data-stu-id="1afe9-108">Here's the permalink for the following list of changes:  [https://aka.ms/devguide_edgehtml_15](./edgehtml-15.md).</span></span>  

## <span data-ttu-id="1afe9-109">新機能</span><span class="sxs-lookup"><span data-stu-id="1afe9-109">New features</span></span>  

### <span data-ttu-id="1afe9-110">CSS のカスタムプロパティ</span><span class="sxs-lookup"><span data-stu-id="1afe9-110">CSS Custom Properties</span></span>  

<span data-ttu-id="1afe9-111">Microsoft Edge で [css のカスタムプロパティ](https://drafts.csswg.org/css-variables)がサポートされるようになりました。 css 変数。</span><span class="sxs-lookup"><span data-stu-id="1afe9-111">Microsoft Edge now supports [CSS Custom Properties](https://drafts.csswg.org/css-variables), a.k.a CSS Variables.</span></span>  <span data-ttu-id="1afe9-112">CSS 変数を使用すると、ユーザー設定の CSS プロパティを作成して、繰り返し色などの重複データの量を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="1afe9-112">CSS Variables allow you to create custom CSS properties that can be reused throughout stylesheets to help reduce the amount of duplicate data, like repeated colors.</span></span>  <span data-ttu-id="1afe9-113">CSS 変数の使い方は簡単です。</span><span class="sxs-lookup"><span data-stu-id="1afe9-113">Using CSS Variables is simple:</span></span>  

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

### <span data-ttu-id="1afe9-114">交差するオブザーバー</span><span class="sxs-lookup"><span data-stu-id="1afe9-114">Intersection Observer</span></span>  

<span data-ttu-id="1afe9-115">EdgeHTML 15 では、 [交差するオブザーバー API](https://w3c.github.io/IntersectionObserver) の仕様が導入されています。</span><span class="sxs-lookup"><span data-stu-id="1afe9-115">EdgeHTML 15 introduces the [Intersection Observer API](https://w3c.github.io/IntersectionObserver) specification.</span></span>  <span data-ttu-id="1afe9-116">交差するオブザーバー API では、他の要素またはグローバルビューポートを基準とした DOM 要素の位置と可視性を非同期的に照会することができます。</span><span class="sxs-lookup"><span data-stu-id="1afe9-116">The Intersection Observer API allows you to asynchronously query the position and visibility of DOM elements relative to other elements or the global viewport.</span></span>  <span data-ttu-id="1afe9-117">この API では、ユーザーが表示されているときに要素を効率的に通知するためのメソッドを作成することによって、カスタムのコストコードを不要にしています。</span><span class="sxs-lookup"><span data-stu-id="1afe9-117">This API eliminates the need for custom expensive code by creating a method to efficiently notify elements when they are in view.</span></span>  

### <span data-ttu-id="1afe9-118">JavaScript</span><span class="sxs-lookup"><span data-stu-id="1afe9-118">JavaScript</span></span>  

<span data-ttu-id="1afe9-119">パフォーマンス最適化は、Chakra JavaScript エンジンの EdgeHTML 15 のバージョンで、中央のステージを実行します。</span><span class="sxs-lookup"><span data-stu-id="1afe9-119">Performance optimizations take center stage with the EdgeHTML 15 rev of the Chakra JavaScript engine.</span></span>  <span data-ttu-id="1afe9-120">Windows 10 の作成者が更新されると、Chakra は、関数を再利用してヒープ引数を最適化し、ミニ修正コードのパフォーマンスを向上させることによってメモリを節約します。</span><span class="sxs-lookup"><span data-stu-id="1afe9-120">With the Windows 10 Creators Update, Chakra saves memory by re-deferring functions and optimizing away heap arguments and improves performance for minified code.</span></span>  

<span data-ttu-id="1afe9-121">さらに、EdgeHTML 15 では、次の機能のプレビューが導入されています。</span><span class="sxs-lookup"><span data-stu-id="1afe9-121">Additionally, EdgeHTML 15 introduces the following feature previews:</span></span>  

#### <span data-ttu-id="1afe9-122">実験的な JavaScript 機能</span><span class="sxs-lookup"><span data-stu-id="1afe9-122">Experimental JavaScript features</span></span>  

<span data-ttu-id="1afe9-123">有効</span><span class="sxs-lookup"><span data-stu-id="1afe9-123">Enabled with</span></span> `about:flags`  

*   <span data-ttu-id="1afe9-124">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) 「」 ([デモ](https://webassembly.org/demo))</span><span class="sxs-lookup"><span data-stu-id="1afe9-124">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) \([demo](https://webassembly.org/demo)\)</span></span>  
*   [<span data-ttu-id="1afe9-125">共有メモリと Atomics</span><span class="sxs-lookup"><span data-stu-id="1afe9-125">Shared Memory and Atomics</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

<span data-ttu-id="1afe9-126">詳細については、「JavaScript のパフォーマンスが向上しました」 [および「Microsoft Edge で共有メモリ](https://blogs.windows.com/msedgedev/2017/04/20) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1afe9-126">See [Improved JavaScript performance, WebAssembly, and Shared Memory in Microsoft Edge](https://blogs.windows.com/msedgedev/2017/04/20) for further details.</span></span>  

### <span data-ttu-id="1afe9-127">支払い要求 API</span><span class="sxs-lookup"><span data-stu-id="1afe9-127">Payment Request API</span></span>  

<span data-ttu-id="1afe9-128">[支払い要求 API](https://w3.org/TR/payment-request)がサポートされるようになりました。これにより、Windows 10 の Pc と電話で web での支払いや支払いがより簡単になります。</span><span class="sxs-lookup"><span data-stu-id="1afe9-128">The [Payment Request API](https://w3.org/TR/payment-request) is now supported, enabling simpler checkout and payments on the web on Windows 10 PCs and Phones.</span></span>  <span data-ttu-id="1afe9-129">この API を使用すると、Microsoft Edge は、商人、消費者、お客様がクラウドに保存した支払い方法 (クレジットカードなど) 間の仲介として機能します。</span><span class="sxs-lookup"><span data-stu-id="1afe9-129">This API enables Microsoft Edge to act as an intermediary between merchants, consumers, and the payment methods \(such as credit cards\) that consumers have stored in the cloud.</span></span>  <span data-ttu-id="1afe9-130">支払い要求 API の詳細については、「支払要求 API と[支払い要求 api](/microsoft-edge/dev-guide/device/payment-request-api)開発者ガイドの[紹介](https://blogs.windows.com/msedgedev/2016/12/15)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1afe9-130">For more information on the Payment Request API, check out [Simpler web payments: Introducing the Payment Request API](https://blogs.windows.com/msedgedev/2016/12/15) and the [Payment Request API](/microsoft-edge/dev-guide/device/payment-request-api) developer guide.</span></span>  

### <span data-ttu-id="1afe9-131">TCP Fast Open (TFO)</span><span class="sxs-lookup"><span data-stu-id="1afe9-131">TCP Fast Open (TFO)</span></span>  
<span data-ttu-id="1afe9-132">TCP Fast Open は、TCP 接続を開くために必要なラウンドトリップの数を減らし、ブラウザーネットワークのパフォーマンスを向上させるための機能です。</span><span class="sxs-lookup"><span data-stu-id="1afe9-132">TCP Fast Open is a feature that reduces the number of round trips required to open a TCP connection, improving browser networking performance.</span></span>  <span data-ttu-id="1afe9-133">詳しくは、「高速で [安全な web サイトを作成する](https://blogs.windows.com/msedgedev/2016/06/15)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1afe9-133">For more details, see [Building a faster and more secure web with TCP Fast Open](https://blogs.windows.com/msedgedev/2016/06/15).</span></span>  <span data-ttu-id="1afe9-134">さまざまなネットワークトポロジの相互運用性の違いにより、Microsoft Edge では、この機能は既定で有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="1afe9-134">Due to interoperability differences in various network topologies, this features is not enabled by default in Microsoft Edge.</span></span>  <span data-ttu-id="1afe9-135">有効にするには、 `about:flags` アドレスバーに入力し、[**ネットワーク**] セクションで [ **TCP Fast Open を有効にする**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1afe9-135">To enable it, type `about:flags` in your address bar, and select the checkbox for **Enable TCP Fast Open** under the **Networking** section.</span></span>  

### <span data-ttu-id="1afe9-136">WebRTC と相互運用可能な RTC ビデオコーデックのサポート</span><span class="sxs-lookup"><span data-stu-id="1afe9-136">WebRTC and interoperable RTC video codec support</span></span>  

<span data-ttu-id="1afe9-137">EdgeHTML 15 は、以前のバージョンの W3C WebRTC API circa 2015 で構築されたアプリケーションとの相互運用性を実現するために、WebRTC 1.0 API のサブセットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1afe9-137">EdgeHTML 15 supports a subset of the WebRTC 1.0 API for interoperability with applications built with earlier versions of the W3C WebRTC-PC API circa 2015.</span></span>  <span data-ttu-id="1afe9-138">詳細については、 [WEBRTC API リファレンス](/previous-versions//mt806139(v=vs.85)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1afe9-138">See the [WebRTC API reference](/previous-versions//mt806139(v=vs.85)) for details.</span></span>  

<span data-ttu-id="1afe9-139">ピアツーピアの音声とビデオによる通信で最も高度な機能を利用するには、 [オブジェクトリアルタイム通信 API](https://ortc.org)を使うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1afe9-139">To take advantage of our most advanced features in peer-to-peer audio and video communication, we recommend using the [Object Real-Time Communication) API](https://ortc.org).</span></span>  <span data-ttu-id="1afe9-140">ORTC API は、グループの音声通話とビデオ通話を設定したり、個々のトランスポート、送信者、レシーバーオブジェクトを直接制御したりする場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="1afe9-140">The ORTC API is better suited for situations where you want to set up group audio and video calls, or directly control individual transport, sender, and receiver objects.</span></span>  

<span data-ttu-id="1afe9-141">Microsoft Edge は、ORTC と WebRTC 1.0 を使って、VP8 ビデオとビデオの[両方をサポート](https://tools.ietf.org/html/rfc4585)しており、両方の種類の[コーデックをサポート](https://tools.ietf.org/html/draft-alvestrand-rmcat-remb-03)し[てい](https://tools.ietf.org/html/rfc4588)ます。これは、次の機能をサポート[します。](https://webrtc.org/experiments/rtp-hdrext/abs-send-time)</span><span class="sxs-lookup"><span data-stu-id="1afe9-141">The Microsoft Edge supports both H.264/AVC and VP8 video with ORTC and WebRTC 1.0, and provides the following features in support of both codec types: [abs-send-time](https://webrtc.org/experiments/rtp-hdrext/abs-send-time), [goog-remb](https://tools.ietf.org/html/draft-alvestrand-rmcat-remb-03), [Picture Loss Indication and Generic NACK feedback](https://tools.ietf.org/html/rfc4585), [RTP Retransmission](https://tools.ietf.org/html/rfc4588).</span></span>  

<span data-ttu-id="1afe9-142">詳細については、「 [WebRTC 1.0 と相互運用可能なリアルタイム通信の概要 (Microsoft Edge](https://blogs.windows.com/msedgedev/2017/01/31))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1afe9-142">For more info, see [Introducing WebRTC 1.0 and interoperable real-time communications in Microsoft Edge](https://blogs.windows.com/msedgedev/2017/01/31).</span></span>  

### <span data-ttu-id="1afe9-143">WebVR</span><span class="sxs-lookup"><span data-stu-id="1afe9-143">WebVR</span></span>  

<span data-ttu-id="1afe9-144">Microsoft Edge では、Windows Mixed Reality ヘッドマウントされたディスプレイと Microsoft Edge を接続する実験的 API である [Webvr](https://immersive-web.github.io/webxr)をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1afe9-144">Microsoft Edge now has support for [WebVR](https://immersive-web.github.io/webxr), an experimental API that connects Windows Mixed Reality head mounted displays and Microsoft Edge.</span></span>  <span data-ttu-id="1afe9-145">この接続によって、web サイト内での VR コンテンツの使用が可能になります。また、イマーシブ VR のエクスペリエンスはデスクトップアプリケーションに限定されなくなります。</span><span class="sxs-lookup"><span data-stu-id="1afe9-145">This connection enables VR content to be experienced within a website, meaning immersive VR experiences are no longer limited to desktop applications.</span></span>  

<span data-ttu-id="1afe9-146">Microsoft Edge の仮想現実は、3D と2D のグラフィックスをレンダリングするための JavaScript API である WebGL によって実現されています。</span><span class="sxs-lookup"><span data-stu-id="1afe9-146">Virtual reality in Microsoft Edge is powered by WebGL, a JavaScript API for rendering 3D and 2D graphics.</span></span>  <span data-ttu-id="1afe9-147">BabylonJS などの WebGL ライブラリで構築された WebGL アプリケーションとアプリケーションはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1afe9-147">WebGL applications and applications built with WebGL libraries like BabylonJS are supported.</span></span>  <span data-ttu-id="1afe9-148">接続すると、WebVR はヘッドセットの周りの位置情報とセンサー情報に対応する視覚効果を送信します。</span><span class="sxs-lookup"><span data-stu-id="1afe9-148">Once connected, WebVR sends visuals corresponding to the position and sensor information around the headset.</span></span>  <span data-ttu-id="1afe9-149">WebVR API では、 [ゲームパッド api](../dom/gamepad-api.md)の拡張機能により、空間コントローラーもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1afe9-149">The WebVR API also supports spatial controllers thanks to an extension to the [Gamepad API](../dom/gamepad-api.md).</span></span>  <span data-ttu-id="1afe9-150">この API は既定でオンになっているため、フラグを切り替える必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1afe9-150">This API is on by default, so no need to toggle a flag.</span></span>  

<span data-ttu-id="1afe9-151">詳しくは、 [Webvr api リファレンス](/previous-versions//mt806281(v=vs.85)) と [ゲームパッド api リファレンス](https://developer.mozilla.org/docs/Web/API/Gamepad_API) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1afe9-151">See the [WebVR API reference](/previous-versions//mt806281(v=vs.85)) and [Gamepad API reference](https://developer.mozilla.org/docs/Web/API/Gamepad_API) for details.</span></span>  

 > [!NOTE] 
 > <span data-ttu-id="1afe9-152">WebVR の仕様はまだ開発段階のため、Microsoft Edge の実装は後で変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1afe9-152">Since the WebVR spec is still in development, Microsoft Edge's implementation may change later down the line.</span></span>  

## <span data-ttu-id="1afe9-153">更新された機能</span><span class="sxs-lookup"><span data-stu-id="1afe9-153">Updated features</span></span>  

### <span data-ttu-id="1afe9-154">コンテンツセキュリティポリシー (レベル 2)</span><span class="sxs-lookup"><span data-stu-id="1afe9-154">Content Security Policy (Level 2)</span></span>  

<span data-ttu-id="1afe9-155">CSP 1 を使用しているサイトは、引き続き、CSP 2 の Microsoft Edge のサポートに対応している必要があり `frame-src` ます。ただし、ワーカースクリプトを作成するディレクティブは、新しいディレクティブに切り替えることをお勧めし `child-src` ます。</span><span class="sxs-lookup"><span data-stu-id="1afe9-155">Sites already using CSP 1 should continue to work with Microsoft Edge support for CSP 2, however it's best to switch any `frame-src` directives that load worker scripts to the new `child-src` directive to future-proof your site.</span></span>  <span data-ttu-id="1afe9-156">\ (CSP 3 では、他 `frame-src` のユーザーには適用されなくなります)。 csp 2 には、次の項目も追加されます。</span><span class="sxs-lookup"><span data-stu-id="1afe9-156">\(In CSP 3, `frame-src` will no longer apply to workers.\) CSP 2 also adds the following:</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="1afe9-157">新しいディレクティブ</span><span class="sxs-lookup"><span data-stu-id="1afe9-157">New directives</span></span>  
   :::column-end:::
   :::column span="2":::
      `base-uri`<span data-ttu-id="1afe9-158">、 `child-src` 、 `form-action` 、 `frame-ancestors` および `plugin-types` 。</span><span class="sxs-lookup"><span data-stu-id="1afe9-158">, `child-src`, `form-action`, `frame-ancestors` and `plugin-types`.</span></span>  <span data-ttu-id="1afe9-159">詳細については、 [Microsoft Edge でサポートされている CSP ディレクティブ](../security/content-security-policy.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1afe9-159">See [Microsoft Edge supported CSP directives](../security/content-security-policy.md) for more.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="1afe9-160">Worker のサポート</span><span class="sxs-lookup"><span data-stu-id="1afe9-160">Workers support</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1afe9-161">バックグラウンドワーカースクリプトは、それらを読み込むドキュメントのポリシーとは別のポリシーによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="1afe9-161">Background worker scripts are governed by their own policy, separate from the policy of the document loading them.</span></span>  <span data-ttu-id="1afe9-162">ホストドキュメントの場合と同様に、応答ヘッダーでワーカーの CSP を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="1afe9-162">As with host documents, you can set the CSP for a worker in the response header.</span></span>  <span data-ttu-id="1afe9-163">また、CSP 2 での新方法  `allow-scripts` として、 `allow-same-origin` ディレクティブのフラグと `sandbox` ワーカースレッドの作成に影響が出るようになりました。</span><span class="sxs-lookup"><span data-stu-id="1afe9-163">Also new in CSP 2 is that  `allow-scripts` and `allow-same-origin` flags of the `sandbox` directive now affect worker thread creation.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="1afe9-164">インラインスクリプトとスタイル</span><span class="sxs-lookup"><span data-stu-id="1afe9-164">Inline scripts and styles</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1afe9-165">CSP 2 では、nonces とハッシュを許可リストメカニズムとして提供することで、インラインスクリプトとスタイルブロックの実行を許可しています。</span><span class="sxs-lookup"><span data-stu-id="1afe9-165">CSP 2 allows for the execution of inline scripts and style blocks by providing nonces and hashes as a allow-listing mechanism.</span></span>  <span data-ttu-id="1afe9-166">Nonces は、CSP ポリシーとページ内のスクリプトタグの両方に表示される、各ページ読み込みに対して生成されるランダムなベース64値です。</span><span class="sxs-lookup"><span data-stu-id="1afe9-166">Nonces are random base-64 values generated on each page load that appears in both the CSP policy and in the script tags in the page.</span></span>  <span data-ttu-id="1afe9-167">ページが読み込み時に動的に生成されると、サーバーは nonce 値を生成し、その値をページの NonceToken に挿入し、コンテンツセキュリティポリシーの HTTP ヘッダーでも宣言します。</span><span class="sxs-lookup"><span data-stu-id="1afe9-167">When the page is dynamically generated on load, the server generates a nonce value, inserts it into the NonceToken in the page and also declares it in the Content Security Policy HTTP header.</span></span>  <span data-ttu-id="1afe9-168">ハッシュは、 `<script>` `<style>` `script-src` CSP ポリシーで \ (using またはディレクティブ \) を指定した a または element のコンテンツから (sha256、sha384、または sha512 アルゴリズムを使用して) 生成される静的な値です `style-src` 。</span><span class="sxs-lookup"><span data-stu-id="1afe9-168">Hashes are static values generated \(using sha256, sha384 or sha512 algorithms\) from the content of a `<script>` or `<style>` element that are then specified \(using `script-src` or `style-src` directives\) in the CSP policy.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="1afe9-169">CSP 違反の報告</span><span class="sxs-lookup"><span data-stu-id="1afe9-169">CSP violation reporting</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1afe9-170">新しいイベントは、 `SecurityPolicyViolationEvent` CSP 違反に応じて発生します。</span><span class="sxs-lookup"><span data-stu-id="1afe9-170">A new event, `SecurityPolicyViolationEvent` is now fired upon CSP violations.</span></span>  <span data-ttu-id="1afe9-171">CSP レポートの以前のメカニズムは `report-uri` 引き続きサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1afe9-171">The earlier mechanism for CSP reporting, `report-uri`, continues to be supported.</span></span>  <span data-ttu-id="1afe9-172">他のいくつかの新しいフィールドが、\ (違反し `effectiveDirective` たポリシー)、\ `statusCode` (HTTP 応答コード \)、 `sourceFile` \ (問題のあるリソースの URL)、、、などの両方に共通する違反レポートに追加されてい `lineNumber` `columnNumber` ます。</span><span class="sxs-lookup"><span data-stu-id="1afe9-172">Several new fields have been added to the violation reports common to both, including `effectiveDirective` \(the policy that was violated\), `statusCode` \(the HTTP response code\), `sourceFile` \(the URL of the offending resource\), `lineNumber`, and `columnNumber`.</span></span>  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="1afe9-173">Web 認証</span><span class="sxs-lookup"><span data-stu-id="1afe9-173">Web Authentication</span></span>  

<span data-ttu-id="1afe9-174">[Windows Hello](https://www.microsoft.com/windows/comprehensive-security)生体認証を使用した新しい[Web 認証 API](../device/web-authentication.md)に対する Microsoft Edge のサポートは、次のような変更が加えられました。</span><span class="sxs-lookup"><span data-stu-id="1afe9-174">Microsoft Edge support for the emerging [Web Authentication API](../device/web-authentication.md) using [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) biometrics has been updated with the following changes:</span></span>  

*   <span data-ttu-id="1afe9-175">[EdgeHTML 14](https://blogs.windows.com/msedgedev/2016/08/04) \ (Windows 10 記念日更新プログラム、ビルド10240、7/2016 \) で導入された実験的な WEB 認証 API の最初の実装は、プレフィックス付き api \ ( [MSCredentials](/previous-versions//mt697639(v=vs.85)) interface \) を介して公開されました。</span><span class="sxs-lookup"><span data-stu-id="1afe9-175">The initial implementation of the experimental Web Authentication API introduced in [EdgeHTML 14](https://blogs.windows.com/msedgedev/2016/08/04) \(Windows 10 Anniversary Update, build 10240, 7/2016\) was exposed through MS- prefixed APIs \(the [MSCredentials](/previous-versions//mt697639(v=vs.85)) interface\).</span></span>  <span data-ttu-id="1afe9-176">これらの Api は依然として EdgeHTML 15 で利用できますが、指定されていない、標準ベースの Api、および仕様の [最新のスナップショット](https://w3.org/TR/2016/WD-webauthn-20160928) で定義されている標準ベースの api と動作を優先して使用することは推奨されていません。仕様が標準化されるため、変更は引き続き行われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1afe9-176">While these APIs are still available in EdgeHTML 15, they are now deprecated in favor of the non-prefixed, standards-based APIs and behaviors defined in a more [recent snapshot](https://w3.org/TR/2016/WD-webauthn-20160928) of the specification, and are likely to continue changing as the spec matures toward standardization.</span></span>  

*   <span data-ttu-id="1afe9-177">最新の Microsoft Edge の実装は、既定でオフになっています。また、(アドレスバーに入力して機能を有効にし `about:flags` ます)。</span><span class="sxs-lookup"><span data-stu-id="1afe9-177">The latest Microsoft Edge implementation is turned off by default and ships behind a flag \(type `about:flags` in your address bar to turn on the feature\).</span></span>  

*   <span data-ttu-id="1afe9-178">Microsoft Edge では、USB キーや Bluetooth デバイスなどの外部資格情報はまだサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1afe9-178">Microsoft Edge does not yet support external credentials like USB keys or Bluetooth devices.</span></span>  <span data-ttu-id="1afe9-179">現在の API は、TPM に保存されている埋め込まれた資格情報に制限されています。</span><span class="sxs-lookup"><span data-stu-id="1afe9-179">The current API is limited to embedded credentials stored in the TPM.</span></span>  <span data-ttu-id="1afe9-180">デバイスで TPM が利用できない場合は、ソフトウェアフォールバックが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1afe9-180">A software fallback is used if TPM is not available on the device.</span></span>  

*   <span data-ttu-id="1afe9-181">現在ログインしている Windows のユーザーアカウントは、少なくとも1つの PIN をサポートするように構成されている必要があります。また、推奨されるフェースまたは指紋の生体認証</span><span class="sxs-lookup"><span data-stu-id="1afe9-181">The currently logged in Windows user account must be configured to support at least a PIN, and preferably face or fingerprint biometrics.</span></span>  <span data-ttu-id="1afe9-182">これにより、Windows で TPM へのアクセスが認証されるようになります。</span><span class="sxs-lookup"><span data-stu-id="1afe9-182">This is to ensure that Windows can authenticate the access to the TPM.</span></span>  

*   <span data-ttu-id="1afe9-183">この仕様で説明されている [定義済みの拡張機能](https://w3.org/TR/webauthn/#extension-predef) では、現時点では [FIDO AppId](https://w3.org/TR/webauthn/#extension-appid) \ (\) のみがサポートされて `webauthn_txAuthSimple` います。</span><span class="sxs-lookup"><span data-stu-id="1afe9-183">Of the [predefined extensions](https://w3.org/TR/webauthn/#extension-predef) described in the spec, Microsoft Edge only supports the [FIDO AppId](https://w3.org/TR/webauthn/#extension-appid) \(`webauthn_txAuthSimple`\) at this time.</span></span>  

*  <span data-ttu-id="1afe9-184">この `timeoutSeconds` オプションは現在評価されていません</span><span class="sxs-lookup"><span data-stu-id="1afe9-184">The `timeoutSeconds` option is not currently evaluated</span></span>  

### <span data-ttu-id="1afe9-185">WebDriver</span><span class="sxs-lookup"><span data-stu-id="1afe9-185">WebDriver</span></span>  

<span data-ttu-id="1afe9-186">EdgeHTML 15 では、サイレントコマンドラインフラグと新しいコマンドエンドポイントのサポートなど、いくつかの WebDriver の更新プログラムを提供しています。</span><span class="sxs-lookup"><span data-stu-id="1afe9-186">EdgeHTML 15 brings a handful of WebDriver updates including support for the silent command line flag and new command endpoints:</span></span>  

| <span data-ttu-id="1afe9-187">メソッド</span><span class="sxs-lookup"><span data-stu-id="1afe9-187">Method</span></span> | <span data-ttu-id="1afe9-188">URI テンプレート</span><span class="sxs-lookup"><span data-stu-id="1afe9-188">URI Template</span></span> | <span data-ttu-id="1afe9-189">コマンド</span><span class="sxs-lookup"><span data-stu-id="1afe9-189">Command</span></span> |  
|:--- |:---  |:--- |    
| <span data-ttu-id="1afe9-190">POST</span><span class="sxs-lookup"><span data-stu-id="1afe9-190">POST</span></span> | <span data-ttu-id="1afe9-191">/セッション id/イベント id/alert/accept</span><span class="sxs-lookup"><span data-stu-id="1afe9-191">/session/{session id}/alert/accept</span></span> | [<span data-ttu-id="1afe9-192">通知を受信する</span><span class="sxs-lookup"><span data-stu-id="1afe9-192">Accept Alert</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-accept-alert) |  
| <span data-ttu-id="1afe9-193">POST</span><span class="sxs-lookup"><span data-stu-id="1afe9-193">POST</span></span> | <span data-ttu-id="1afe9-194">/セッション id/イベント id/通知/無視</span><span class="sxs-lookup"><span data-stu-id="1afe9-194">/session/{session id}/alert/dismiss</span></span> | [<span data-ttu-id="1afe9-195">通知を無視する</span><span class="sxs-lookup"><span data-stu-id="1afe9-195">Dismiss Alert</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-dismiss-alert) |  
| <span data-ttu-id="1afe9-196">GET</span><span class="sxs-lookup"><span data-stu-id="1afe9-196">GET</span></span> | <span data-ttu-id="1afe9-197">セッション id/イベント id}/alert/text</span><span class="sxs-lookup"><span data-stu-id="1afe9-197">/session/{session id}/alert/text</span></span> | [<span data-ttu-id="1afe9-198">通知テキストを取得する</span><span class="sxs-lookup"><span data-stu-id="1afe9-198">Get Alert Text</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-alert-text) |  
| <span data-ttu-id="1afe9-199">POST</span><span class="sxs-lookup"><span data-stu-id="1afe9-199">POST</span></span> | <span data-ttu-id="1afe9-200">セッション id/イベント id}/alert/text</span><span class="sxs-lookup"><span data-stu-id="1afe9-200">/session/{session id}/alert/text</span></span> | [<span data-ttu-id="1afe9-201">通知テキストを送信する</span><span class="sxs-lookup"><span data-stu-id="1afe9-201">Send Alert Text</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-send-alert-text) |  
| <span data-ttu-id="1afe9-202">POST</span><span class="sxs-lookup"><span data-stu-id="1afe9-202">POST</span></span> | <span data-ttu-id="1afe9-203">/セッション id/execute/async</span><span class="sxs-lookup"><span data-stu-id="1afe9-203">/session/{session id}/execute/async</span></span> | [<span data-ttu-id="1afe9-204">Async スクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="1afe9-204">Execute Async Script</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-async-script) |  
| <span data-ttu-id="1afe9-205">POST</span><span class="sxs-lookup"><span data-stu-id="1afe9-205">POST</span></span> | <span data-ttu-id="1afe9-206">/セッション id/execute/sync</span><span class="sxs-lookup"><span data-stu-id="1afe9-206">/session/{session id}/execute/sync</span></span> | [<span data-ttu-id="1afe9-207">スクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="1afe9-207">Execute Script</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-script) |  
| <span data-ttu-id="1afe9-208">GET</span><span class="sxs-lookup"><span data-stu-id="1afe9-208">GET</span></span> | <span data-ttu-id="1afe9-209">/セッション id}/window</span><span class="sxs-lookup"><span data-stu-id="1afe9-209">/session/{session id}/window</span></span> | [<span data-ttu-id="1afe9-210">ウィンドウハンドルを取得する</span><span class="sxs-lookup"><span data-stu-id="1afe9-210">Get Window Handle</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#get-window-handle) |  
| <span data-ttu-id="1afe9-211">GET</span><span class="sxs-lookup"><span data-stu-id="1afe9-211">GET</span></span> | <span data-ttu-id="1afe9-212">/セッション id/ウィンドウのウィンドウ/ハンドル</span><span class="sxs-lookup"><span data-stu-id="1afe9-212">/session/{session id}/window/handles</span></span> | [<span data-ttu-id="1afe9-213">ウィンドウハンドルを取得する</span><span class="sxs-lookup"><span data-stu-id="1afe9-213">Get Window Handles</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-window-handles) |  

<span data-ttu-id="1afe9-214">その他の WebDriver 機能の詳細とその他の WebDriver 機能の状態については、「 [webdriver](../../webdriver.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1afe9-214">For more info and the status of other WebDriver features, check out [WebDriver](../../webdriver.md).</span></span>  

## <span data-ttu-id="1afe9-215">EdgeHTML 15 の新しい Api</span><span class="sxs-lookup"><span data-stu-id="1afe9-215">New APIs in EdgeHTML 15</span></span>  

<span data-ttu-id="1afe9-216">EdgeHTML 15 の新しい Api の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1afe9-216">Here's the full list of new APIs in EdgeHTML 15.</span></span>  <span data-ttu-id="1afe9-217">これらのファイルは、の形式で表示され `[interface name].[api name]` ます。</span><span class="sxs-lookup"><span data-stu-id="1afe9-217">They are listed in the format of `[interface name].[api name]`.</span></span>  

<iframe height='582' scrolling='no' title='<span data-ttu-id="1afe9-218">新しい EdgeHTML15 Api</span><span class="sxs-lookup"><span data-stu-id="1afe9-218">New EdgeHTML15 APIs</span></span>' src='//codepen.io/MicrosoftEdgeDocumentation/embed/evRjjZ/?height=582&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="1afe9-219"><a href='http://codepen.io/MicrosoftEdgeDocumentation/pen/evRjjZ/'> </a> CodePen の Microsoft Edge ドキュメント (@MicrosoftEdgeDocumentation) による Pen New EdgeHTML15 api に関する記事を参照してください <a href='http://codepen.io/MicrosoftEdgeDocumentation'> </a> <a href='http://codepen.io'> </a> 。</span><span class="sxs-lookup"><span data-stu-id="1afe9-219">See the Pen <a href='http://codepen.io/MicrosoftEdgeDocumentation/pen/evRjjZ/'>New EdgeHTML15 APIs</a> by Microsoft Edge Docs (<a href='http://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='http://codepen.io'>CodePen</a>.</span></span></iframe>  

## <span data-ttu-id="1afe9-220">以前の EdgeHTML リリース</span><span class="sxs-lookup"><span data-stu-id="1afe9-220">Previous EdgeHTML releases</span></span>  

[<span data-ttu-id="1afe9-221">EdgeHTML 12/Windows ビルド 10240 (7/2015)</span><span class="sxs-lookup"><span data-stu-id="1afe9-221">EdgeHTML 12 / Windows build 10240 (7/2015)</span></span>](./edgehtml-12.md)  

[<span data-ttu-id="1afe9-222">EdgeHTML 13/Windows ビルド 10586 (11/2015)</span><span class="sxs-lookup"><span data-stu-id="1afe9-222">EdgeHTML 13 / Windows build 10586 (11/2015)</span></span>](./edgehtml-13.md)  

[<span data-ttu-id="1afe9-223">EdgeHTML 14/Windows ビルド 14393 (8/2016)</span><span class="sxs-lookup"><span data-stu-id="1afe9-223">EdgeHTML 14 / Windows build 14393 (8/2016)</span></span>](./edgehtml-14.md)  
