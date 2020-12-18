---
description: このガイドでは、EdgeHTML 15 に含まれる開発者向けの機能と標準の概要について説明します。
title: EdgeHTML 15 の新機能と API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 126fbc5f2a077052654063237c669089a3376ab0
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235007"
---
# <span data-ttu-id="4cc56-104">EdgeHTML 15 の新機能</span><span class="sxs-lookup"><span data-stu-id="4cc56-104">What's new in EdgeHTML 15</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="4cc56-105">[Windows 10 Creators Update \(04/2017,](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) Build 15063\) の現在のリリースの Microsoft Edge プラットフォームに同梱されている変更点を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4cc56-105">Here are the changes shipped with the current release of the Microsoft Edge platform, as of the [Windows 10 Creators Update](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) \(04/2017, Build 15063\).</span></span>  <span data-ttu-id="4cc56-106">Microsoft Edge ブラウザー全体の変更点の概要については [、Windows 10 Creators Update](https://blogs.windows.com/msedgedev/2017/04/11)の Microsoft Edge の新機能に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4cc56-106">For an overview of changes to the overall Microsoft Edge browser, see [What's new in Microsoft Edge in the Windows 10 Creators Update](https://blogs.windows.com/msedgedev/2017/04/11).</span></span>  

<span data-ttu-id="4cc56-107">それ以降の Windows Insider Preview ビルドの変更については [、「EdgeHTML](../whats-new.md)の新機能」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc56-107">For changes in subsequent Windows Insider Preview builds, see [What's New in EdgeHTML](../whats-new.md).</span></span>  

<span data-ttu-id="4cc56-108">次の変更の一覧の permalink を次に示します  [https://aka.ms/devguide_edgehtml_15](./edgehtml-15.md) 。</span><span class="sxs-lookup"><span data-stu-id="4cc56-108">Here's the permalink for the following list of changes:  [https://aka.ms/devguide_edgehtml_15](./edgehtml-15.md).</span></span>  

## <span data-ttu-id="4cc56-109">新機能</span><span class="sxs-lookup"><span data-stu-id="4cc56-109">New features</span></span>  

### <span data-ttu-id="4cc56-110">CSS カスタム プロパティ</span><span class="sxs-lookup"><span data-stu-id="4cc56-110">CSS Custom Properties</span></span>  

<span data-ttu-id="4cc56-111">Microsoft Edge では [、CSS カスタム プロパティ (CSS](https://drafts.csswg.org/css-variables)変数) がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="4cc56-111">Microsoft Edge now supports [CSS Custom Properties](https://drafts.csswg.org/css-variables), a.k.a CSS Variables.</span></span>  <span data-ttu-id="4cc56-112">CSS 変数を使用すると、スタイルシート全体で再利用できるカスタム CSS プロパティを作成して、重複するデータの量 (色の繰り返しなど) を減らします。</span><span class="sxs-lookup"><span data-stu-id="4cc56-112">CSS Variables allow you to create custom CSS properties that can be reused throughout stylesheets to help reduce the amount of duplicate data, like repeated colors.</span></span>  <span data-ttu-id="4cc56-113">CSS 変数の使用は簡単です。</span><span class="sxs-lookup"><span data-stu-id="4cc56-113">Using CSS Variables is simple:</span></span>  

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

### <span data-ttu-id="4cc56-114">交差オブザーバー</span><span class="sxs-lookup"><span data-stu-id="4cc56-114">Intersection Observer</span></span>  

<span data-ttu-id="4cc56-115">EdgeHTML 15 では、Intersection [Intersection API の仕様が導入](https://w3c.github.io/IntersectionObserver) されています。</span><span class="sxs-lookup"><span data-stu-id="4cc56-115">EdgeHTML 15 introduces the [Intersection Observer API](https://w3c.github.io/IntersectionObserver) specification.</span></span>  <span data-ttu-id="4cc56-116">Intersection Intersection API を使用すると、他の要素またはグローバル ビューポートを基準に DOM 要素の位置と表示を非同期に照会できます。</span><span class="sxs-lookup"><span data-stu-id="4cc56-116">The Intersection Observer API allows you to asynchronously query the position and visibility of DOM elements relative to other elements or the global viewport.</span></span>  <span data-ttu-id="4cc56-117">この API では、要素が表示されているときに効率的に通知するメソッドを作成することで、コストの高いカスタム コードが不要になります。</span><span class="sxs-lookup"><span data-stu-id="4cc56-117">This API eliminates the need for custom expensive code by creating a method to efficiently notify elements when they are in view.</span></span>  

### <span data-ttu-id="4cc56-118">JavaScript</span><span class="sxs-lookup"><span data-stu-id="4cc56-118">JavaScript</span></span>  

<span data-ttu-id="4cc56-119">パフォーマンスの最適化は、Chakra JavaScript エンジンの EdgeHTML 15 rev を使用して中心に行います。</span><span class="sxs-lookup"><span data-stu-id="4cc56-119">Performance optimizations take center stage with the EdgeHTML 15 rev of the Chakra JavaScript engine.</span></span>  <span data-ttu-id="4cc56-120">Windows 10 Creators Update では、Chakra は関数を再延期し、ヒープ引数を最適化することでメモリを節約し、コードを最適化するパフォーマンスを向上させます。</span><span class="sxs-lookup"><span data-stu-id="4cc56-120">With the Windows 10 Creators Update, Chakra saves memory by re-deferring functions and optimizing away heap arguments and improves performance for minified code.</span></span>  

<span data-ttu-id="4cc56-121">さらに、EdgeHTML 15 では、次の機能のプレビューが導入されています。</span><span class="sxs-lookup"><span data-stu-id="4cc56-121">Additionally, EdgeHTML 15 introduces the following feature previews:</span></span>  

#### <span data-ttu-id="4cc56-122">試験的な JavaScript 機能</span><span class="sxs-lookup"><span data-stu-id="4cc56-122">Experimental JavaScript features</span></span>  

<span data-ttu-id="4cc56-123">有効</span><span class="sxs-lookup"><span data-stu-id="4cc56-123">Enabled with</span></span> `about:flags`  

*   <span data-ttu-id="4cc56-124">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) \([demo](https://webassembly.org/demo)\)</span><span class="sxs-lookup"><span data-stu-id="4cc56-124">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) \([demo](https://webassembly.org/demo)\)</span></span>  
*   [<span data-ttu-id="4cc56-125">共有メモリとアトミック</span><span class="sxs-lookup"><span data-stu-id="4cc56-125">Shared Memory and Atomics</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

<span data-ttu-id="4cc56-126">詳細 [については、Microsoft Edge の JavaScript パフォーマンス、WebAssembly、共有](https://blogs.windows.com/msedgedev/2017/04/20) メモリの改善に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc56-126">See [Improved JavaScript performance, WebAssembly, and Shared Memory in Microsoft Edge](https://blogs.windows.com/msedgedev/2017/04/20) for further details.</span></span>  

### <span data-ttu-id="4cc56-127">支払い要求 API</span><span class="sxs-lookup"><span data-stu-id="4cc56-127">Payment Request API</span></span>  

<span data-ttu-id="4cc56-128">支払 [い要求 API](https://w3.org/TR/payment-request) がサポートされ、Windows 10 PC とスマートフォン上の Web でのチェックアウトと支払いを簡単にできます。</span><span class="sxs-lookup"><span data-stu-id="4cc56-128">The [Payment Request API](https://w3.org/TR/payment-request) is now supported, enabling simpler checkout and payments on the web on Windows 10 PCs and Phones.</span></span>  <span data-ttu-id="4cc56-129">この API を使用すると、Microsoft Edge は、業者、消費者、および消費者がクラウドに保存した支払い方法 \(クレジット カード\など) の仲介者として機能できます。</span><span class="sxs-lookup"><span data-stu-id="4cc56-129">This API enables Microsoft Edge to act as an intermediary between merchants, consumers, and the payment methods \(such as credit cards\) that consumers have stored in the cloud.</span></span>  <span data-ttu-id="4cc56-130">支払い要求 API の詳細については、「簡単な Web 支払い:支払い要求 [API](https://blogs.windows.com/msedgedev/2016/12/15) と支払い要求 [API](/microsoft-edge/dev-guide/device/payment-request-api) 開発者ガイド」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4cc56-130">For more information on the Payment Request API, check out [Simpler web payments: Introducing the Payment Request API](https://blogs.windows.com/msedgedev/2016/12/15) and the [Payment Request API](/microsoft-edge/dev-guide/device/payment-request-api) developer guide.</span></span>  

### <span data-ttu-id="4cc56-131">TCP Fast Open (TFO)</span><span class="sxs-lookup"><span data-stu-id="4cc56-131">TCP Fast Open (TFO)</span></span>  
<span data-ttu-id="4cc56-132">TCP ファスト オープンは、TCP 接続を開くのに必要なラウンド トリップ数を減らして、ブラウザーのネットワーク パフォーマンスを向上させる機能です。</span><span class="sxs-lookup"><span data-stu-id="4cc56-132">TCP Fast Open is a feature that reduces the number of round trips required to open a TCP connection, improving browser networking performance.</span></span>  <span data-ttu-id="4cc56-133">詳細については [、「TCP Fast Open を使用してより高速で安全な Web を構築する」を参照してください](https://blogs.windows.com/msedgedev/2016/06/15)。</span><span class="sxs-lookup"><span data-stu-id="4cc56-133">For more details, see [Building a faster and more secure web with TCP Fast Open](https://blogs.windows.com/msedgedev/2016/06/15).</span></span>  <span data-ttu-id="4cc56-134">さまざまなネットワーク トポロジの相互運用性の違いにより、この機能は Microsoft Edge では既定で有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="4cc56-134">Due to interoperability differences in various network topologies, this features is not enabled by default in Microsoft Edge.</span></span>  <span data-ttu-id="4cc56-135">有効にするには、アドレス バーに入力し、[ネットワーク] セクションの [TCP ファスト オープンを有効にする] チェック ボックス `about:flags` **をオン**にします。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4cc56-135">To enable it, type `about:flags` in your address bar, and select the checkbox for **Enable TCP Fast Open** under the **Networking** section.</span></span>  

### <span data-ttu-id="4cc56-136">WebRTC と相互運用可能な RTC ビデオ コーデックのサポート</span><span class="sxs-lookup"><span data-stu-id="4cc56-136">WebRTC and interoperable RTC video codec support</span></span>  

<span data-ttu-id="4cc56-137">EdgeHTML 15 は、W3C WebRTC-PC API circa 2015 の以前のバージョンで構築されたアプリケーションとの相互運用性を確保するために、WebRTC 1.0 API のサブセットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4cc56-137">EdgeHTML 15 supports a subset of the WebRTC 1.0 API for interoperability with applications built with earlier versions of the W3C WebRTC-PC API circa 2015.</span></span>  <span data-ttu-id="4cc56-138">詳細については [、WebRTC API リファレンス](/previous-versions//mt806139(v=vs.85)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc56-138">See the [WebRTC API reference](/previous-versions//mt806139(v=vs.85)) for details.</span></span>  

<span data-ttu-id="4cc56-139">ピアツーピアの音声およびビデオ通信で最も高度な機能を利用するには [、Object Real-Time Communication) API](https://ortc.org)を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4cc56-139">To take advantage of our most advanced features in peer-to-peer audio and video communication, we recommend using the [Object Real-Time Communication) API](https://ortc.org).</span></span>  <span data-ttu-id="4cc56-140">ORTC API は、グループの音声通話とビデオ通話を設定する場合や、個々のトランスポート オブジェクト、送信者オブジェクト、および受信者オブジェクトを直接制御する場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="4cc56-140">The ORTC API is better suited for situations where you want to set up group audio and video calls, or directly control individual transport, sender, and receiver objects.</span></span>  

<span data-ttu-id="4cc56-141">Microsoft Edge は、ORTC と WebRTC 1.0 で H.264/AVC と VP8 の両方のビデオをサポートし、両方のコーデックの種類をサポートする次の機能を提供します。abs-send-time、goog-remb、Picture [Loss Indication and Generic NACK feedback](https://tools.ietf.org/html/rfc4585), [](https://webrtc.org/experiments/rtp-hdrext/abs-send-time) [RTP Retransmission](https://tools.ietf.org/html/rfc4588). [](https://tools.ietf.org/html/draft-alvestrand-rmcat-remb-03)</span><span class="sxs-lookup"><span data-stu-id="4cc56-141">The Microsoft Edge supports both H.264/AVC and VP8 video with ORTC and WebRTC 1.0, and provides the following features in support of both codec types: [abs-send-time](https://webrtc.org/experiments/rtp-hdrext/abs-send-time), [goog-remb](https://tools.ietf.org/html/draft-alvestrand-rmcat-remb-03), [Picture Loss Indication and Generic NACK feedback](https://tools.ietf.org/html/rfc4585), [RTP Retransmission](https://tools.ietf.org/html/rfc4588).</span></span>  

<span data-ttu-id="4cc56-142">詳細については、Microsoft Edge での [WebRTC 1.0](https://blogs.windows.com/msedgedev/2017/01/31)と相互運用可能なリアルタイム通信の紹介を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc56-142">For more info, see [Introducing WebRTC 1.0 and interoperable real-time communications in Microsoft Edge](https://blogs.windows.com/msedgedev/2017/01/31).</span></span>  

### <span data-ttu-id="4cc56-143">WebVR</span><span class="sxs-lookup"><span data-stu-id="4cc56-143">WebVR</span></span>  

<span data-ttu-id="4cc56-144">Microsoft Edge では、Windows Mixed Reality ヘッド マウント ディスプレイと Microsoft Edge を接続する試験的な API である [WebVR](https://immersive-web.github.io/webxr)がサポートされました。</span><span class="sxs-lookup"><span data-stu-id="4cc56-144">Microsoft Edge now has support for [WebVR](https://immersive-web.github.io/webxr), an experimental API that connects Windows Mixed Reality head mounted displays and Microsoft Edge.</span></span>  <span data-ttu-id="4cc56-145">この接続により、VR コンテンツを Web サイト内で体験できます。つまり、イマーシブ VR エクスペリエンスはデスクトップ アプリケーションに限定されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="4cc56-145">This connection enables VR content to be experienced within a website, meaning immersive VR experiences are no longer limited to desktop applications.</span></span>  

<span data-ttu-id="4cc56-146">Microsoft Edge の仮想現実には、3D および 2D グラフィックスをレンダリングする JavaScript API である WebGL が搭載されています。</span><span class="sxs-lookup"><span data-stu-id="4cc56-146">Virtual reality in Microsoft Edge is powered by WebGL, a JavaScript API for rendering 3D and 2D graphics.</span></span>  <span data-ttu-id="4cc56-147">BabylonJS のような WebGL ライブラリで構築された WebGL アプリケーションとアプリケーションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4cc56-147">WebGL applications and applications built with WebGL libraries like BabylonJS are supported.</span></span>  <span data-ttu-id="4cc56-148">接続されると、WebVR はヘッドセットの位置とセンサー情報に対応する視覚効果を送信します。</span><span class="sxs-lookup"><span data-stu-id="4cc56-148">Once connected, WebVR sends visuals corresponding to the position and sensor information around the headset.</span></span>  <span data-ttu-id="4cc56-149">WebVR API は、ゲームパッド API の拡張機能により空間コントローラー **もサポートします**。</span><span class="sxs-lookup"><span data-stu-id="4cc56-149">The WebVR API also supports spatial controllers thanks to an extension to the **Gamepad API**.</span></span>  <span data-ttu-id="4cc56-150">この API は既定で有効なので、フラグを切り替える必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4cc56-150">This API is on by default, so no need to toggle a flag.</span></span>  

<!--  Virtual reality in Microsoft Edge is powered by WebGL, a JavaScript API for rendering 3D and 2D graphics.  WebGL applications and applications built with WebGL libraries like BabylonJS are supported.  Once connected, WebVR sends visuals corresponding to the position and sensor information around the headset.  The WebVR API also supports spatial controllers thanks to an extension to the [Gamepad API](../dom/gamepad-api.md).  This API is on by default, so no need to toggle a flag.  -->  

<span data-ttu-id="4cc56-151">詳細については [、WebVR API リファレンス](/previous-versions/mt806281(v=vs.85)) と [ゲームパッド API リファレンス](https://developer.mozilla.org/docs/Web/API/Gamepad_API) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cc56-151">See the [WebVR API reference](/previous-versions/mt806281(v=vs.85)) and [Gamepad API reference](https://developer.mozilla.org/docs/Web/API/Gamepad_API) for details.</span></span>  

 > [!NOTE] 
 > <span data-ttu-id="4cc56-152">WebVR 仕様はまだ開発中です。Microsoft Edge の実装は後で変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4cc56-152">Since the WebVR spec is still in development, Microsoft Edge's implementation may change later down the line.</span></span>  

## <span data-ttu-id="4cc56-153">更新された機能</span><span class="sxs-lookup"><span data-stu-id="4cc56-153">Updated features</span></span>  

### <span data-ttu-id="4cc56-154">コンテンツ セキュリティ ポリシー (レベル 2)</span><span class="sxs-lookup"><span data-stu-id="4cc56-154">Content Security Policy (Level 2)</span></span>  

<span data-ttu-id="4cc56-155">CSP 1 を既に使用しているサイトは、CSP 2 に対する Microsoft Edge サポートで引き続き動作する必要があります。ただし、ワーカー スクリプトを読み込むディレクティブを新しいディレクティブに切り替えて、サイトの将来性を高め続けるのが最善です。 `frame-src` `child-src`</span><span class="sxs-lookup"><span data-stu-id="4cc56-155">Sites already using CSP 1 should continue to work with Microsoft Edge support for CSP 2, however it's best to switch any `frame-src` directives that load worker scripts to the new `child-src` directive to future-proof your site.</span></span>  <span data-ttu-id="4cc56-156">\(CSP 3 では、ワーカーには適用されなくなりました。\) CSP 2 では、次の機能 `frame-src` も追加されます。</span><span class="sxs-lookup"><span data-stu-id="4cc56-156">\(In CSP 3, `frame-src` will no longer apply to workers.\) CSP 2 also adds the following:</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="4cc56-157">新しいディレクティブ</span><span class="sxs-lookup"><span data-stu-id="4cc56-157">New directives</span></span>  
   :::column-end:::
   :::column span="2":::
      `base-uri`<span data-ttu-id="4cc56-158">,, `child-src` `form-action` , and `frame-ancestors` `plugin-types` .</span><span class="sxs-lookup"><span data-stu-id="4cc56-158">, `child-src`, `form-action`, `frame-ancestors` and `plugin-types`.</span></span>  <!--  See [Microsoft Edge supported CSP directives](../security/content-security-policy.md) for more.  -->  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="4cc56-159">ワーカーサポート</span><span class="sxs-lookup"><span data-stu-id="4cc56-159">Workers support</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4cc56-160">バックグラウンド ワーカー スクリプトは、読み込むドキュメントのポリシーとは別に、独自のポリシーによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="4cc56-160">Background worker scripts are governed by their own policy, separate from the policy of the document loading them.</span></span>  <span data-ttu-id="4cc56-161">ホスト ドキュメントと同様に、応答ヘッダーでワーカーの CSP を設定できます。</span><span class="sxs-lookup"><span data-stu-id="4cc56-161">As with host documents, you can set the CSP for a worker in the response header.</span></span>  <span data-ttu-id="4cc56-162">また、CSP 2 の新機能は、ディレクティブのフラグがワーカー スレッドの作成 `allow-scripts` `allow-same-origin` `sandbox` に影響を与える点です。</span><span class="sxs-lookup"><span data-stu-id="4cc56-162">Also new in CSP 2 is that `allow-scripts` and `allow-same-origin` flags of the `sandbox` directive now affect worker thread creation.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="4cc56-163">インライン スクリプトとスタイル</span><span class="sxs-lookup"><span data-stu-id="4cc56-163">Inline scripts and styles</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4cc56-164">CSP 2 では、nonce とハッシュを許可一覧メカニズムとして提供することで、インライン スクリプトとスタイル ブロックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="4cc56-164">CSP 2 allows for the execution of inline scripts and style blocks by providing nonces and hashes as a allow-listing mechanism.</span></span>  <span data-ttu-id="4cc56-165">Nonce は、CSP ポリシーとページ内のスクリプト タグの両方に表示される各ページ読み込みで生成されるランダムな Base 64 値です。</span><span class="sxs-lookup"><span data-stu-id="4cc56-165">Nonces are random base-64 values generated on each page load that appears in both the CSP policy and in the script tags in the page.</span></span>  <span data-ttu-id="4cc56-166">読み込み時にページが動的に生成されると、サーバーは nonce 値を生成し、その値をページ内の NonceToken に挿入し、コンテンツ セキュリティ ポリシー HTTP ヘッダーでも宣言します。</span><span class="sxs-lookup"><span data-stu-id="4cc56-166">When the page is dynamically generated on load, the server generates a nonce value, inserts it into the NonceToken in the page and also declares it in the Content Security Policy HTTP header.</span></span>  <span data-ttu-id="4cc56-167">ハッシュは、CSP ポリシーで \(using または `<script>` `<style>` `script-src` directives\) が指定された 1 つ以上の要素のコンテンツから \(sha256、sha384、sha512 アルゴリズムを使用して `style-src` ) 生成される静的な値です。</span><span class="sxs-lookup"><span data-stu-id="4cc56-167">Hashes are static values generated \(using sha256, sha384 or sha512 algorithms\) from the content of a `<script>` or `<style>` element that are then specified \(using `script-src` or `style-src` directives\) in the CSP policy.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="4cc56-168">CSP 違反の報告</span><span class="sxs-lookup"><span data-stu-id="4cc56-168">CSP violation reporting</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4cc56-169">新しいイベントは `SecurityPolicyViolationEvent` 、CSP 違反時に発生します。</span><span class="sxs-lookup"><span data-stu-id="4cc56-169">A new event, `SecurityPolicyViolationEvent` is now fired upon CSP violations.</span></span>  <span data-ttu-id="4cc56-170">CSP レポートの以前のメカニズム `report-uri` は、引き続きサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4cc56-170">The earlier mechanism for CSP reporting, `report-uri`, continues to be supported.</span></span>  <span data-ttu-id="4cc56-171">両方に共通する違反レポートには `effectiveDirective` 、\(違反したポリシー\)、\(HTTP 応答コード\)、\(問題を引き受けるリソース `statusCode` の URL\)、および `sourceFile` `lineNumber` `columnNumber` .</span><span class="sxs-lookup"><span data-stu-id="4cc56-171">Several new fields have been added to the violation reports common to both, including `effectiveDirective` \(the policy that was violated\), `statusCode` \(the HTTP response code\), `sourceFile` \(the URL of the offending resource\), `lineNumber`, and `columnNumber`.</span></span>  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="4cc56-172">Web 認証</span><span class="sxs-lookup"><span data-stu-id="4cc56-172">Web Authentication</span></span>  

<span data-ttu-id="4cc56-173">Windows Hello 生体認証を使用する新しい **Web 認証 API** に対する Microsoft [Edge](https://www.microsoft.com/windows/comprehensive-security) のサポートは、次の変更によって更新されました。</span><span class="sxs-lookup"><span data-stu-id="4cc56-173">Microsoft Edge support for the emerging **Web Authentication API** using [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) biometrics has been updated with the following changes:</span></span>  

<!--  Microsoft Edge support for the emerging [Web Authentication API](../device/web-authentication.md) using [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) biometrics has been updated with the following changes:  -->  

*   <span data-ttu-id="4cc56-174">[EdgeHTML 14](https://blogs.windows.com/msedgedev/2016/08/04) \(Windows 10 Anniversary Update ビルド 10240、7/2016\) で導入された試験的な Web 認証 API の初期実装は、MS- プレフィックス付き API [\(MSCredentials](/previous-versions/mt697639(v=vs.85))インターフェイス\) を通じて公開されました。</span><span class="sxs-lookup"><span data-stu-id="4cc56-174">The initial implementation of the experimental Web Authentication API introduced in [EdgeHTML 14](https://blogs.windows.com/msedgedev/2016/08/04) \(Windows 10 Anniversary Update, build 10240, 7/2016\) was exposed through MS- prefixed APIs \(the [MSCredentials](/previous-versions/mt697639(v=vs.85)) interface\).</span></span>  <span data-ttu-id="4cc56-175">これらの API は EdgeHTML 15 でも引き続き使用できます。これらの API は、仕様の最新のスナップショットで定義されたプレフィックス付きでない標準ベース[](https://w3.org/TR/2016/WD-webauthn-20160928)の API と動作を推奨して廃止され、仕様が標準化に向けて成熟するに従って変化し続ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4cc56-175">While these APIs are still available in EdgeHTML 15, they are now deprecated in favor of the non-prefixed, standards-based APIs and behaviors defined in a more [recent snapshot](https://w3.org/TR/2016/WD-webauthn-20160928) of the specification, and are likely to continue changing as the spec matures toward standardization.</span></span>  

*   <span data-ttu-id="4cc56-176">最新の Microsoft Edge 実装は既定でオフにされ、フラグ \(type `about:flags` in your address bar to turn on the feature\) の背後に出荷されます。</span><span class="sxs-lookup"><span data-stu-id="4cc56-176">The latest Microsoft Edge implementation is turned off by default and ships behind a flag \(type `about:flags` in your address bar to turn on the feature\).</span></span>  

*   <span data-ttu-id="4cc56-177">Microsoft Edge では、USB キーや外部デバイスなど、外部資格情報Bluetoothされていません。</span><span class="sxs-lookup"><span data-stu-id="4cc56-177">Microsoft Edge does not yet support external credentials like USB keys or Bluetooth devices.</span></span>  <span data-ttu-id="4cc56-178">現在の API は、TPM に格納されている埋め込み資格情報に制限されています。</span><span class="sxs-lookup"><span data-stu-id="4cc56-178">The current API is limited to embedded credentials stored in the TPM.</span></span>  <span data-ttu-id="4cc56-179">デバイスで TPM を利用できない場合は、ソフトウェア フォールバックが使用されます。</span><span class="sxs-lookup"><span data-stu-id="4cc56-179">A software fallback is used if TPM is not available on the device.</span></span>  

*   <span data-ttu-id="4cc56-180">現在ログインしている Windows ユーザー アカウントは、少なくとも PIN、できれば顔認証または指紋生体認証をサポートするように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc56-180">The currently logged in Windows user account must be configured to support at least a PIN, and preferably face or fingerprint biometrics.</span></span>  <span data-ttu-id="4cc56-181">これは、Windows が TPM へのアクセスを認証するための方法です。</span><span class="sxs-lookup"><span data-stu-id="4cc56-181">This is to ensure that Windows can authenticate the access to the TPM.</span></span>  

*   <span data-ttu-id="4cc56-182">仕様で [説明されている定義済](https://w3.org/TR/webauthn/#extension-predef) みの拡張機能の中で、Microsoft Edge は現時点では [FIDO AppId](https://w3.org/TR/webauthn/#extension-appid) \( `webauthn_txAuthSimple` \) のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4cc56-182">Of the [predefined extensions](https://w3.org/TR/webauthn/#extension-predef) described in the spec, Microsoft Edge only supports the [FIDO AppId](https://w3.org/TR/webauthn/#extension-appid) \(`webauthn_txAuthSimple`\) at this time.</span></span>  

*  <span data-ttu-id="4cc56-183">この `timeoutSeconds` オプションは現在評価されません</span><span class="sxs-lookup"><span data-stu-id="4cc56-183">The `timeoutSeconds` option is not currently evaluated</span></span>  

### <span data-ttu-id="4cc56-184">WebDriver</span><span class="sxs-lookup"><span data-stu-id="4cc56-184">WebDriver</span></span>  

<span data-ttu-id="4cc56-185">EdgeHTML 15 では、サイレント コマンド ライン フラグと新しいコマンド エンドポイントのサポートを含む、一部の WebDriver 更新プログラムが提供されます。</span><span class="sxs-lookup"><span data-stu-id="4cc56-185">EdgeHTML 15 brings a handful of WebDriver updates including support for the silent command line flag and new command endpoints:</span></span>  

| <span data-ttu-id="4cc56-186">メソッド</span><span class="sxs-lookup"><span data-stu-id="4cc56-186">Method</span></span> | <span data-ttu-id="4cc56-187">URI テンプレート</span><span class="sxs-lookup"><span data-stu-id="4cc56-187">URI Template</span></span> | <span data-ttu-id="4cc56-188">コマンド</span><span class="sxs-lookup"><span data-stu-id="4cc56-188">Command</span></span> |  
|:--- |:---  |:--- |    
| <span data-ttu-id="4cc56-189">POST</span><span class="sxs-lookup"><span data-stu-id="4cc56-189">POST</span></span> | <span data-ttu-id="4cc56-190">/session/{session id}/alert/accept</span><span class="sxs-lookup"><span data-stu-id="4cc56-190">/session/{session id}/alert/accept</span></span> | [<span data-ttu-id="4cc56-191">通知を受け入れる</span><span class="sxs-lookup"><span data-stu-id="4cc56-191">Accept Alert</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-accept-alert) |  
| <span data-ttu-id="4cc56-192">POST</span><span class="sxs-lookup"><span data-stu-id="4cc56-192">POST</span></span> | <span data-ttu-id="4cc56-193">/session/{session id}/alert/dismiss</span><span class="sxs-lookup"><span data-stu-id="4cc56-193">/session/{session id}/alert/dismiss</span></span> | [<span data-ttu-id="4cc56-194">アラートを閉じる</span><span class="sxs-lookup"><span data-stu-id="4cc56-194">Dismiss Alert</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-dismiss-alert) |  
| <span data-ttu-id="4cc56-195">GET</span><span class="sxs-lookup"><span data-stu-id="4cc56-195">GET</span></span> | <span data-ttu-id="4cc56-196">/session/{session id}/alert/text</span><span class="sxs-lookup"><span data-stu-id="4cc56-196">/session/{session id}/alert/text</span></span> | [<span data-ttu-id="4cc56-197">アラート テキストを取得する</span><span class="sxs-lookup"><span data-stu-id="4cc56-197">Get Alert Text</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-alert-text) |  
| <span data-ttu-id="4cc56-198">POST</span><span class="sxs-lookup"><span data-stu-id="4cc56-198">POST</span></span> | <span data-ttu-id="4cc56-199">/session/{session id}/alert/text</span><span class="sxs-lookup"><span data-stu-id="4cc56-199">/session/{session id}/alert/text</span></span> | [<span data-ttu-id="4cc56-200">通知テキストを送信する</span><span class="sxs-lookup"><span data-stu-id="4cc56-200">Send Alert Text</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-send-alert-text) |  
| <span data-ttu-id="4cc56-201">POST</span><span class="sxs-lookup"><span data-stu-id="4cc56-201">POST</span></span> | <span data-ttu-id="4cc56-202">/session/{session id}/execute/async</span><span class="sxs-lookup"><span data-stu-id="4cc56-202">/session/{session id}/execute/async</span></span> | [<span data-ttu-id="4cc56-203">非同期スクリプトの実行</span><span class="sxs-lookup"><span data-stu-id="4cc56-203">Execute Async Script</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-async-script) |  
| <span data-ttu-id="4cc56-204">POST</span><span class="sxs-lookup"><span data-stu-id="4cc56-204">POST</span></span> | <span data-ttu-id="4cc56-205">/session/{session id}/execute/sync</span><span class="sxs-lookup"><span data-stu-id="4cc56-205">/session/{session id}/execute/sync</span></span> | [<span data-ttu-id="4cc56-206">スクリプトの実行</span><span class="sxs-lookup"><span data-stu-id="4cc56-206">Execute Script</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-script) |  
| <span data-ttu-id="4cc56-207">GET</span><span class="sxs-lookup"><span data-stu-id="4cc56-207">GET</span></span> | <span data-ttu-id="4cc56-208">/session/{session id}/window</span><span class="sxs-lookup"><span data-stu-id="4cc56-208">/session/{session id}/window</span></span> | [<span data-ttu-id="4cc56-209">ウィンドウ ハンドルを取得する</span><span class="sxs-lookup"><span data-stu-id="4cc56-209">Get Window Handle</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#get-window-handle) |  
| <span data-ttu-id="4cc56-210">GET</span><span class="sxs-lookup"><span data-stu-id="4cc56-210">GET</span></span> | <span data-ttu-id="4cc56-211">/session/{session id}/window/handles</span><span class="sxs-lookup"><span data-stu-id="4cc56-211">/session/{session id}/window/handles</span></span> | [<span data-ttu-id="4cc56-212">ウィンドウ ハンドルを取得する</span><span class="sxs-lookup"><span data-stu-id="4cc56-212">Get Window Handles</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-window-handles) |  

<span data-ttu-id="4cc56-213">他の WebDriver 機能の詳細と状態については [、WebDriver を参照してください](../../webdriver/index.md)。</span><span class="sxs-lookup"><span data-stu-id="4cc56-213">For more info and the status of other WebDriver features, check out [WebDriver](../../webdriver/index.md).</span></span>  

## <span data-ttu-id="4cc56-214">EdgeHTML 15 の新しい API</span><span class="sxs-lookup"><span data-stu-id="4cc56-214">New APIs in EdgeHTML 15</span></span>  

<span data-ttu-id="4cc56-215">EdgeHTML 15 の新しい API の完全な一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4cc56-215">Here's the full list of new APIs in EdgeHTML 15.</span></span>  <span data-ttu-id="4cc56-216">これらは次の形式で一覧表示されます `[interface name].[api name]` 。</span><span class="sxs-lookup"><span data-stu-id="4cc56-216">They are listed in the format of `[interface name].[api name]`.</span></span>  

<iframe height='582' scrolling='no' title='<span data-ttu-id="4cc56-217">新しい EdgeHTML15 API</span><span class="sxs-lookup"><span data-stu-id="4cc56-217">New EdgeHTML15 APIs</span></span>' src='//codepen.io/MicrosoftEdgeDocumentation/embed/evRjjZ/?height=582&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="4cc56-218">CodePen で Microsoft Edge Docs ( @MicrosoftEdgeDocumentation ) による Pen New <a href='http://codepen.io/MicrosoftEdgeDocumentation/pen/evRjjZ/'> EdgeHTML15 </a> <a href='http://codepen.io/MicrosoftEdgeDocumentation'> API </a> を <a href='http://codepen.io'> 参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="4cc56-218">See the Pen <a href='http://codepen.io/MicrosoftEdgeDocumentation/pen/evRjjZ/'>New EdgeHTML15 APIs</a> by Microsoft Edge Docs (<a href='http://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='http://codepen.io'>CodePen</a>.</span></span></iframe>  

## <span data-ttu-id="4cc56-219">以前の EdgeHTML リリース</span><span class="sxs-lookup"><span data-stu-id="4cc56-219">Previous EdgeHTML releases</span></span>  

[<span data-ttu-id="4cc56-220">EdgeHTML 12 / Windows ビルド 10240 (7/2015)</span><span class="sxs-lookup"><span data-stu-id="4cc56-220">EdgeHTML 12 / Windows build 10240 (7/2015)</span></span>](./edgehtml-12.md)  

[<span data-ttu-id="4cc56-221">EdgeHTML 13 / Windows ビルド 10586 (11/2015)</span><span class="sxs-lookup"><span data-stu-id="4cc56-221">EdgeHTML 13 / Windows build 10586 (11/2015)</span></span>](./edgehtml-13.md)  

[<span data-ttu-id="4cc56-222">EdgeHTML 14 / Windows ビルド 14393 (8/2016)</span><span class="sxs-lookup"><span data-stu-id="4cc56-222">EdgeHTML 14 / Windows build 14393 (8/2016)</span></span>](./edgehtml-14.md)  
