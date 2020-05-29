---
ms.assetid: ef705c70-73f8-445b-84ed-4f83679f1980
description: オブジェクトリアルタイム通信 (ORTC) を使って、web ブラウザー、モバイルデバイス、またはサーバー間でメディアをリアルタイムで直接ストリーミングできるようにする方法について説明します。
title: 開発ガイド-オブジェクト RTC API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: ac033ea26fa7c1eb435b0164e5dbd2a3a5428474
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568826"
---
# <span data-ttu-id="aab53-104">オブジェクト RTC API</span><span class="sxs-lookup"><span data-stu-id="aab53-104">Object RTC API</span></span>

<span data-ttu-id="aab53-105">オブジェクトリアルタイム通信 (ORTC) を使うと、web ブラウザー、モバイルデバイス、およびネイティブ Javascript Api を介して、メディア (音声やビデオ) をリアルタイムで直接ストリーミング (送受信) できます。</span><span class="sxs-lookup"><span data-stu-id="aab53-105">Object Real-Time Communications (ORTC) enables media (audio and/or video) to be streamed (sent and received) in real-time directly between web browsers, mobile devices, and servers via native Javascript APIs.</span></span>

> [!NOTE]
> <span data-ttu-id="aab53-106">Microsoft Edge では、Windows 10 デバイスに対して ORTC が実装されています。</span><span class="sxs-lookup"><span data-stu-id="aab53-106">Microsoft Edge now implements ORTC for Windows 10 devices.</span></span> <span data-ttu-id="aab53-107">ただし、この実装は、最新バージョンの[ORTC API](https://go.microsoft.com/fwlink/p/?LinkID=690096)とは異なります。</span><span class="sxs-lookup"><span data-stu-id="aab53-107">However, this implementation differs from the most recent version of the [ORTC API](https://go.microsoft.com/fwlink/p/?LinkID=690096).</span></span> <span data-ttu-id="aab53-108">ORTC は、Microsoft Edge の開発とリリースの後で進化し続けています。ブラウザーは、ORTC API 内のすべてのオブジェクトやメソッドを実装するわけではなく、現時点で定義に組み込まれていない拡張機能も含まれています。</span><span class="sxs-lookup"><span data-stu-id="aab53-108">ORTC has continued to evolve since the development and release of Microsoft Edge -- the browser does not implement every object or method within the ORTC API, and includes extensions not currently incorporated within the specification.</span></span> <span data-ttu-id="aab53-109">さらに開発には引き続き、世界中の開発者が、Skype ユーザーやその他の WebRTC 対応のコミュニケーションサービスに通話を発信する機能を備えたエクスペリエンスを構築できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="aab53-109">Further development will continue with the goal to enable developers around the world to build experiences that include the ability to talk to Skype users and other WebRTC compatible communication services.</span></span>



<span data-ttu-id="aab53-110">ORTC の実践的な体験を得るには、次のデモをテストドライブで試してください。</span><span class="sxs-lookup"><span data-stu-id="aab53-110">To get a hands-on experience with ORTC, try out these demos on Test Drive:</span></span>
-  [<span data-ttu-id="aab53-111">SimpleWebRTC</span><span class="sxs-lookup"><span data-stu-id="aab53-111">SimpleWebRTC</span></span>](https://developer.microsoft.com/microsoft-edge/testdrive/demos/simplewebrtc/)
-  [<span data-ttu-id="aab53-112">ORTC 通話</span><span class="sxs-lookup"><span data-stu-id="aab53-112">ORTC phone call</span></span>](https://developer.microsoft.com/microsoft-edge/testdrive/demos/twilioortc/)
-  [<span data-ttu-id="aab53-113">ORTC デモ</span><span class="sxs-lookup"><span data-stu-id="aab53-113">ORTC demo</span></span>](https://developer.microsoft.com/microsoft-edge/testdrive/demos/ortcdemo/)


<span data-ttu-id="aab53-114">ORTC の詳細については、Microsoft edge dev ブログの[Microsoft edge で、「ORTC API を使用できるようになりました](https://go.microsoft.com/fwlink/p/?LinkID=627564)。」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="aab53-114">For more information about ORTC, check out [ORTC API is now available in Microsoft Edge](https://go.microsoft.com/fwlink/p/?LinkID=627564) on the Microsoft Edge dev blog.</span></span>


## <span data-ttu-id="aab53-115">概要図</span><span class="sxs-lookup"><span data-stu-id="aab53-115">Overview Diagram</span></span>


<span data-ttu-id="aab53-116">次の図は、ORTC オブジェクト間の関係を説明する概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="aab53-116">The diagram below provides a summary describing relationships between ORTC objects.</span></span> <span data-ttu-id="aab53-117">水平方向または斜め方向の矢印は、メディアまたはデータの流れを示し、縦方向矢印はメソッドとイベントでの相互作用を表します。</span><span class="sxs-lookup"><span data-stu-id="aab53-117">Horizontal or slanted arrows denote the flow of media or data, whereas vertical arrows denote interactions via methods and events.</span></span>

<span data-ttu-id="aab53-118">ORTC は、"*送信者*"、"*受信者*"、"*トランスポート*" の各オブジェクトを使用します。これには、実行できる操作について説明されている "*機能*" と "*パラメーター*" が含まれています。</span><span class="sxs-lookup"><span data-stu-id="aab53-118">ORTC uses "*sender*", "*receiver*" and "*transport*" objects, which have "*capabilities*" describing what they are capable of doing, as well as "*parameters*" which define what they are configured to do.</span></span> <span data-ttu-id="aab53-119">"*追跡*" は、送信者によるメディアストリームのキャプチャとエンコード、トランスポート上の移動、ビデオ/オーディオタグにメディアストリームトラックをレンダリングするレシーバーによるデコードなどを行います。</span><span class="sxs-lookup"><span data-stu-id="aab53-119">"*Tracks*" capture and encode media streams by senders, traveling over transports, then decoded by receivers that render the media stream tracks to video/audio tags.</span></span>

![<span data-ttu-id="aab53-120">Microsoft Edge の、 ](./../media/ortc_diagram.png) 上の図の図で [`RTCRtpSender`](https://msdn.microsoft.com/library/Mt502516) は、a または a に転送される、入力として提供されるトラックをエンコードしてい [`RTCDtlsTransport`](https://msdn.microsoft.com/library/Mt502495) [`RTCSrtpSdesTransport`](https://msdn.microsoft.com/library/Mt502527) ます。</span><span class="sxs-lookup"><span data-stu-id="aab53-120">Microsoft Edge ORTC Flow Diagram](./../media/ortc_diagram.png) In the figure above, the [`RTCRtpSender`](https://msdn.microsoft.com/library/Mt502516) encodes the track provided as input, which is transported over a [`RTCDtlsTransport`](https://msdn.microsoft.com/library/Mt502495) or an [`RTCSrtpSdesTransport`](https://msdn.microsoft.com/library/Mt502527).</span></span> <span data-ttu-id="aab53-121">デュアルトーンマルチ周波数 (DTMF) トーンの送信は、でサポートされてい [`RTCDtmfSender`](https://msdn.microsoft.com/library/Mt502496) ます。</span><span class="sxs-lookup"><span data-stu-id="aab53-121">Sending of Dual Tone Multi Frequency (DTMF) tones is supported via the [`RTCDtmfSender`](https://msdn.microsoft.com/library/Mt502496).</span></span>

<span data-ttu-id="aab53-122">を [`RTCDtlsTransport`](https://msdn.microsoft.com/library/Mt502495) 使用して、 [`RTCSrtpSdesTransport`](https://msdn.microsoft.com/library/Mt502527) [`RTCIceTransport`](https://msdn.microsoft.com/library/Mt433112) 受信側のピアに到達するための通信パスを選択し `RTCIceTransport` ます。これは、メディアに関連付けられている、またはによって `RTCDtlsTransport` 、と `RTCSrtpSdesTransport` の重複を解除し [`RTCRtpReceiver`](https://msdn.microsoft.com/library/Mt502508) ます。</span><span class="sxs-lookup"><span data-stu-id="aab53-122">The [`RTCDtlsTransport`](https://msdn.microsoft.com/library/Mt502495) and [`RTCSrtpSdesTransport`](https://msdn.microsoft.com/library/Mt502527) utilize an [`RTCIceTransport`](https://msdn.microsoft.com/library/Mt433112) to select a communication path to reach the receiving peer's `RTCIceTransport`, which is in turn associated with an `RTCDtlsTransport` or `RTCSrtpSdesTransport` which de-multiplexes media to the [`RTCRtpReceiver`](https://msdn.microsoft.com/library/Mt502508).</span></span> <span data-ttu-id="aab53-123">次に、 `RTCRtpReceiver` メディアをデコードし、オーディオタグまたはビデオタグでレンダリングされたトラックを生成します。</span><span class="sxs-lookup"><span data-stu-id="aab53-123">The `RTCRtpReceiver` then decodes media, producing a track which is rendered by an audio or video tag.</span></span>

<span data-ttu-id="aab53-124">他のいくつかのオブジェクトも役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="aab53-124">Several other objects also play a role.</span></span> <span data-ttu-id="aab53-125">[`RTCIceGatherer`](https://msdn.microsoft.com/library/Mt433107)1 つのオブジェクトによって使用されるローカル ICE 候補を収集 [`RTCIceTransport`](https://msdn.microsoft.com/library/Mt433112) します。</span><span class="sxs-lookup"><span data-stu-id="aab53-125">The [`RTCIceGatherer`](https://msdn.microsoft.com/library/Mt433107) gathers local ICE candidates for use by a single [`RTCIceTransport`](https://msdn.microsoft.com/library/Mt433112) object.</span></span> <span data-ttu-id="aab53-126">API の残りの部分では、RTP の*機能*と*パラメーター*、*操作の統計情報*、 [WebRTC 1.0 API](https://go.microsoft.com/fwlink/p/?LinkID=627573)との互換性に関する詳細について説明しています。</span><span class="sxs-lookup"><span data-stu-id="aab53-126">Remaining sections of the API fill in details relating to RTP *capabilities* and *parameters*, *operational statistics* and compatibility with the [WebRTC 1.0 API](https://go.microsoft.com/fwlink/p/?LinkID=627573).</span></span>

> [!NOTE]
> <span data-ttu-id="aab53-127">Microsoft Edge ではデータチャネルが実装されていないため、 `RTCDataChannel` と `RTCSctpTransport` オブジェクトはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="aab53-127">Since Microsoft Edge does not implement the data channel, the `RTCDataChannel` and `RTCSctpTransport` objects are not supported.</span></span>




## <span data-ttu-id="aab53-128">Microsoft Edge の初期実装でサポートされているコンポーネント</span><span class="sxs-lookup"><span data-stu-id="aab53-128">Components supported in the initial Microsoft Edge implementation</span></span>


* **<span data-ttu-id="aab53-129">ORTC API のサポート。</span><span class="sxs-lookup"><span data-stu-id="aab53-129">ORTC API support.</span></span>** <span data-ttu-id="aab53-130">音声/ビデオ通信は主要なフォーカスであり、次のオブジェクト、、、、、 [`RTCIceGatherer`](https://msdn.microsoft.com/library/Mt433107) [`RTCIceTransport`](https://msdn.microsoft.com/library/Mt433112) [`RTCDtlsTransport`](https://msdn.microsoft.com/library/Mt502495) [`RTCRtpSender`](https://msdn.microsoft.com/library/Mt502516) [`RTCRtpReceiver`](https://msdn.microsoft.com/library/Mt502508) および [`RTCStats`](https://msdn.microsoft.com/library/Mt589726) 図に直接表示されていないインタフェースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="aab53-130">Audio/video communications is the primary focus, including the following objects: [`RTCIceGatherer`](https://msdn.microsoft.com/library/Mt433107), [`RTCIceTransport`](https://msdn.microsoft.com/library/Mt433112), [`RTCDtlsTransport`](https://msdn.microsoft.com/library/Mt502495), [`RTCRtpSender`](https://msdn.microsoft.com/library/Mt502516), [`RTCRtpReceiver`](https://msdn.microsoft.com/library/Mt502508), as well as the [`RTCStats`](https://msdn.microsoft.com/library/Mt589726) interfaces that are not shown directly in the diagram.</span></span>
* **<span data-ttu-id="aab53-131">RTP/RTCP マルチプレクシングのサポート。</span><span class="sxs-lookup"><span data-stu-id="aab53-131">RTP/RTCP multiplexing support.</span></span>** <span data-ttu-id="aab53-132">[`RTP/RTCP multiplexing`](https://msdn.microsoft.com/library/Mt502503)は、と共に使用する必要が [`DtlsTransport`](https://msdn.microsoft.com/library/Mt502495) あります。</span><span class="sxs-lookup"><span data-stu-id="aab53-132">[`RTP/RTCP multiplexing`](https://msdn.microsoft.com/library/Mt502503) is required for use with the [`DtlsTransport`](https://msdn.microsoft.com/library/Mt502495).</span></span> <span data-ttu-id="aab53-133">また、A/V マルチプレクシングもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="aab53-133">A/V multiplexing is also supported.</span></span>
* **<span data-ttu-id="aab53-134">STUN/TURN/ICE サポート。</span><span class="sxs-lookup"><span data-stu-id="aab53-134">STUN/TURN/ICE support.</span></span>** <span data-ttu-id="aab53-135">STUN [(rfc 5389)](https://go.microsoft.com/fwlink/p/?LinkID=627619)、TURN [(rfc 5766)](https://go.microsoft.com/fwlink/p/?LinkID=627620) 、および ICE [(rfc 5245)](https://go.microsoft.com/fwlink/p/?LinkID=627621)がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="aab53-135">STUN [(RFC 5389)](https://go.microsoft.com/fwlink/p/?LinkID=627619), TURN [(RFC 5766)](https://go.microsoft.com/fwlink/p/?LinkID=627620) as well as ICE [(RFC 5245)](https://go.microsoft.com/fwlink/p/?LinkID=627621), are supported.</span></span> <span data-ttu-id="aab53-136">ICE では、標準の参加がサポートされ、(受け手として) 積極的な推薦が部分的にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="aab53-136">Within ICE, regular nomination is supported, with aggressive nomination partially supported (as a receiver).</span></span> <span data-ttu-id="aab53-137">DTLS-SRTP [(RFC 5764)](https://go.microsoft.com/fwlink/p/?LinkID=627622)は、DTLS 1.0 [(RFC4347)](https://go.microsoft.com/fwlink/p/?LinkID=627629)に基づいてサポートされています。</span><span class="sxs-lookup"><span data-stu-id="aab53-137">DTLS-SRTP [(RFC 5764)](https://go.microsoft.com/fwlink/p/?LinkID=627622) is supported, based on DTLS 1.0 [(RFC4347)](https://go.microsoft.com/fwlink/p/?LinkID=627629).</span></span>
* **<span data-ttu-id="aab53-138">コーデックのサポート。</span><span class="sxs-lookup"><span data-stu-id="aab53-138">Codec support.</span></span>** <span data-ttu-id="aab53-139">[オーディオコーデック](https://msdn.microsoft.com/library/Mt599587)については、722、OPUS、SILK をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="aab53-139">For [audio codecs](https://msdn.microsoft.com/library/Mt599587), we support G.711, G.722, Opus and SILK.</span></span> <span data-ttu-id="aab53-140">また、RTCWEB audio の要件に従って、お客様には快適な雑音 (CN) と DTMF もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="aab53-140">We also support Comfort Noise (CN) and DTMF according to the RTCWEB audio requirements.</span></span> <span data-ttu-id="aab53-141">ビデオについては、現在 [`H.264UC`](https://msdn.microsoft.com/library/Mt589706) Skype サービスで使用されているコーデックがサポートされています。 simulcast、スケーラブルなビデオコーディング、転送エラー訂正などの高度な機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="aab53-141">For video we currently support the [`H.264UC`](https://msdn.microsoft.com/library/Mt589706) codec used by Skype services, supporting advanced features such as simulcast, scalable video coding and forward error correction.</span></span> <span data-ttu-id="aab53-142">ここでは、相互運用可能なビデオを H. 264 で有効にするために取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="aab53-142">We're working toward to enabling interoperable video with H.264.</span></span>

> [!NOTE]
> <span data-ttu-id="aab53-143">WebRTC 1.0 の実装に精通していて、WebRTC 1.0 と ORTC 内のオブジェクトサポートの進化に関心がある場合は、2014 IIT RTC 会議: "[ORTC API Update](http://www.rtc-conference.com/2016/wp-content/uploads/gravity_forms/2-2f7a537445fa703985ab4d2372ac42ca/2014/10/ORTC_API_Update.pdf)" から、Google、Microsoft、および Hookflash によって次のプレゼンテーションを行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="aab53-143">If you are familiar with WebRTC 1.0 implementations, and are interested in the evolution of object support within WebRTC 1.0 and ORTC, we recommend the following presentation by Google, Microsoft, and Hookflash from the 2014 IIT RTC Conference: "[ORTC API Update](http://www.rtc-conference.com/2016/wp-content/uploads/gravity_forms/2-2f7a537445fa703985ab4d2372ac42ca/2014/10/ORTC_API_Update.pdf)."</span></span>




## <span data-ttu-id="aab53-144">1:1 通信用のアプリレベルのコードフロー</span><span class="sxs-lookup"><span data-stu-id="aab53-144">App level code flow for 1:1 communications</span></span>


<span data-ttu-id="aab53-145">このシナリオでは、2つの Windows 10 マシンが、web サーバとの間で通信を確立するために、ピア間で情報を交換するために、2つのピアを2つのピアとして処理します。</span><span class="sxs-lookup"><span data-stu-id="aab53-145">For this scenario, two Windows 10 machines will act as two peers with a webserver as the signaling channel to exchange information between the peers so that a connection may be established between them.</span></span>

<span data-ttu-id="aab53-146">次の手順は、1つのピアによって実行される操作を対象としています。</span><span class="sxs-lookup"><span data-stu-id="aab53-146">The steps below are scoped to operations taken by one peer.</span></span> <span data-ttu-id="aab53-147">どちらのピアも、1:1 通信をセットアップするために、同様の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aab53-147">Both peers must go through similar steps in order to set up the 1:1 communications.</span></span> <span data-ttu-id="aab53-148">以下のコードスニペットをさらに詳しく理解するには、 [Microsoft Edge テストドライブデモ](https://go.microsoft.com/fwlink/p/?LinkID=627635)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aab53-148">To make better sense out of the code snippets below, refer to the [Microsoft Edge Test Drive Demo](https://go.microsoft.com/fwlink/p/?LinkID=627635).</span></span>

<span data-ttu-id="aab53-149">この例では、オーディオビデオと RTP/RTCP 多重化を使用しています。これにより、1つの ICE と DTLS transport のみが表示され、オーディオとビデオの両方に対して RTP と RTCP のパケットが伝送されます。</span><span class="sxs-lookup"><span data-stu-id="aab53-149">This example uses audio-video and RTP/RTCP multiplexing, so you will see only a single ICE and DTLS transport, used to transport RTP and RTCP packets for both audio and video.</span></span>

`Step #1.` <span data-ttu-id="aab53-150">[`MediaStream`](https://msdn.microsoft.com/library/Mt131875)1 つのオーディオトラックと1つのビデオトラックを含むオブジェクト ([メディアキャプチャとストリーム API](./../multimedia/media-Capture-and-Streams.md)) を作成します。</span><span class="sxs-lookup"><span data-stu-id="aab53-150">Create [`MediaStream`](https://msdn.microsoft.com/library/Mt131875) object (i.e. [Media Capture and Streams API](./../multimedia/media-Capture-and-Streams.md)) with one audio track and one video track.</span></span>

```js
navigator.MediaDevices.getUserMedia ({
    "audio": true,
    "video": {
        width: 640,
        height: 360,
        facingMode: "user"
    }
}).then(
    gotStream
).catch(
    gotMediaError
);

function gotStream(stream) {
    var mediaStreamLocal = stream;
    …
}
```

`Step #2.` <span data-ttu-id="aab53-151">を作成 [`ICE gatherer`](https://msdn.microsoft.com/library/mt433107(v=vs.85).aspx) し、ローカル [`ICE candidates`](https://msdn.microsoft.com/library/Mt502499) がリモートピアに通知されるようにします。</span><span class="sxs-lookup"><span data-stu-id="aab53-151">Create the [`ICE gatherer`](https://msdn.microsoft.com/library/mt433107(v=vs.85).aspx), and enable local [`ICE candidates`](https://msdn.microsoft.com/library/Mt502499) to be signaled to remote peer.</span></span>

```js
var iceOptions = new RTCIceGatherOptions;
iceOptions.gatherPolicy = "all";
iceOptions.iceservers = ... ;
var iceGathr = new RTCIceGatherer(iceOptions);
iceGathr.onlocalcandidate = function(evt) {
    mySignaller.signalMessage({
        "candidate": evt.candidate
    });
};
```

<span data-ttu-id="aab53-152">ユーザーのプライバシーを保護するために、Microsoft Edge には、ユーザーがローカルホストの IP アドレスをオブジェクトによって公開できるかどうかを制御できるオプションが導入さ [`IceGatherer`](https://msdn.microsoft.com/library/Mt433107) れています。</span><span class="sxs-lookup"><span data-stu-id="aab53-152">To help protect user privacy, Microsoft Edge introduces an option that allows a user to control whether local host IP addresses can be exposed by the [`IceGatherer`](https://msdn.microsoft.com/library/Mt433107) objects.</span></span> <span data-ttu-id="aab53-153">この設定を切り替えるためのインターフェイスオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="aab53-153">An interface option will be provided to toggle this setting.</span></span>

<span data-ttu-id="aab53-154">[Microsoft Edge テストドライブデモ](https://go.microsoft.com/fwlink/p/?LinkID=627635)では、TURN server がセットアップされています。</span><span class="sxs-lookup"><span data-stu-id="aab53-154">In the [Microsoft Edge Test Drive Demo](https://go.microsoft.com/fwlink/p/?LinkID=627635), a TURN server has been set up.</span></span> <span data-ttu-id="aab53-155">この TURN server はスループットが非常に限定されているため、デモページの使用のみに限定されています。</span><span class="sxs-lookup"><span data-stu-id="aab53-155">This TURN server has a very limited throughput, so is limited to only demo page use.</span></span>

`Step #3.` <span data-ttu-id="aab53-156">[`ICE transport`](https://msdn.microsoft.com/library/Mt433112)オーディオとビデオのためのを作成し、ICE トランスポート上のリモートでの処理を準備し [`ICE candidates`](https://msdn.microsoft.com/library/Mt502499) ます。</span><span class="sxs-lookup"><span data-stu-id="aab53-156">Create the [`ICE transport`](https://msdn.microsoft.com/library/Mt433112) for audio and video, and prepare to handle remote [`ICE candidates`](https://msdn.microsoft.com/library/Mt502499) on the ICE transport.</span></span>

```js
var iceTr = new RTCIceTransport();
mySignaller.onRemoteCandidate = function(remote) {
    iceTr.addRemoteCandidate(remote.candidate);
}
```

<span data-ttu-id="aab53-157">ここでは、すべてのリモート ICE 候補を配列に蓄積し `remoteCandidates` て、 `iceTr.setRemoteCandidates(remoteCandidates)` すべてのリモート候補をまとめて追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aab53-157">Another option here is to accumulate all the remote ICE candidates into an array `remoteCandidates` and call `iceTr.setRemoteCandidates(remoteCandidates)` to add all the remote candidates together.</span></span>

`Step #4.` <span data-ttu-id="aab53-158">DTLS トランスポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="aab53-158">Create the DTLS transport.</span></span>

```js
var dtlsTr = new RTCDtlsTransport(iceTr);
```

`Step #5.` <span data-ttu-id="aab53-159">送信者と受信者のオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="aab53-159">Create the sender and receiver objects.</span></span>

```js
var audioTrack = mediaStreamLocal.getAudioTracks()[0];
var videoTrack = mediaStreamLocal.getVideoTracks()[0];
var audioSender = new RtpSender(audioTrack, dtlsTr);
var videoSender = new RtpSender(videoTrack, dtlsTr);
var audioReceiver = new RtpReceiver(dtlsTr, "audio");
var videoReceiver = new RtpReceiver(dtlsTr, "video");
```

<span data-ttu-id="aab53-160">手順 #6</span><span class="sxs-lookup"><span data-stu-id="aab53-160">Step #6.</span></span> <span data-ttu-id="aab53-161">受信者と送信者の機能を取得します。</span><span class="sxs-lookup"><span data-stu-id="aab53-161">Retrieve the receiver and sender capabilities.</span></span>

```js
var recvAudioCaps = RTCRtpReceiver.getCapabilities("audio");
var recvVideoCaps = RTCRtpReceiver.getCapabilities("video");
var sendAudioCaps = RTCRtpSender.getCapabilities("audio");
var sendVideoCaps = RTCRtpSender.getCapabilities("video");
```

`Step #7.` <span data-ttu-id="aab53-162">ICE/DTLS パラメーターと送受信機能を交換できます。</span><span class="sxs-lookup"><span data-stu-id="aab53-162">ICE/DTLS parameters and Send/Receive capabilities can be exchanged.</span></span>

```js
mySignaller.signalMessage({
    "ice": iceGathr.getLocalParameters(),
    "dtls": dtlsTr.getLocalParameters(),
    "recvAudioCaps": recvAudioCaps,
    "recvVideoCaps": recvVideoCaps,
    "sendAudioCaps": sendAudioCaps,
    "sendVideoCaps": sendVideoCaps
};
```

`Step #8.` <span data-ttu-id="aab53-163">リモートのパラメーターを取得して、 [`ICE`](https://msdn.microsoft.com/library/Mt433112) およびトランスポートを開始し、 [`DTLS`](https://msdn.microsoft.com/library/Mt502495) オーディオとビデオの送受信パラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="aab53-163">Get remote params, start the [`ICE`](https://msdn.microsoft.com/library/Mt433112) and [`DTLS`](https://msdn.microsoft.com/library/Mt502495) transports, and set the audio and video send and receive parameters.</span></span>

```js
mySignaller.onRemoteParams = function(params) {
    // The responder answers with its preferences, parameters and capabilities
    // Derive the send and receive parameters.
    var audioSendParams = myCapsToSendParams(sendAudioCaps, params.recvAudioCaps);
    var videoSendParams = myCapsToSendParams(sendVideoCaps, params.recvVideoCaps);
    var audioRecvParams = myCapsToRecvParams(recvAudioCaps, params.sendAudioCaps);
    var videoRecvParams = myCapsToRecvParams(recvVideoCaps, params.sendVideoCaps);
    iceTr.start(iceGathr, params.ice, RTCIceRole.controlling);
    dtlsTr.start(params.dtls);
    audioSender.send(audioSendParams);
    videoSender.send(videoSendParams);
    audioReceiver.receive(audioRecvParams);
    videoReceiver.receive(videoRecvParams);
};
```

<span data-ttu-id="aab53-164">次に示すのは、ヘルパー関数のスケルトンです。</span><span class="sxs-lookup"><span data-stu-id="aab53-164">Below is a skeleton of the helper functions.</span></span> <span data-ttu-id="aab53-165">詳細については、 [Microsoft Edge テストドライブのデモ](https://go.microsoft.com/fwlink/p/?LinkID=627635)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aab53-165">Find more details in the [Microsoft Edge Test Drive Demo](https://go.microsoft.com/fwlink/p/?LinkID=627635).</span></span>

```js
RTCRtpParameters function myCapsToSendParams (RTCRtpCapabilities sendCaps, RTCRtpCapabilities remoteRecvCaps) {
    // Function returning the sender RTCRtpParameters, based on intersection of the local sender and remote receiver capabilities.
    // Steps to be followed:
    // 1. Determine the RTP features that the receiver and sender have in common.
    // 2. Determine the codecs that the sender and receiver have in common.
    // 3. Within each common codec, determine the common formats and rtcpFeedback mechanisms.
    // 4. Determine the payloadType to be used, based on the receiver preferredPayloadType.
    // 5. Set RTCRtcpParameters such as mux to their default values.  
}

RTCRtpParameters function myCapsToRecvParams(RTCRtpCapabilities recvCaps, RTCRtpCapabilities remoteSendCaps) {
    return myCapsToSendParams(remoteSendCaps, recvCaps);
}
```

`Step #9.` <span data-ttu-id="aab53-166">ビデオタグを介してリモートメディアストリームトラックをレンダリングし、再生します。</span><span class="sxs-lookup"><span data-stu-id="aab53-166">Render and play the remote media stream tracks through a video tag.</span></span>

```js
var videoRenderer = document.getElementById("myRtcVideoTag");
var mediaStreamRemote = new MediaStream();
mediaStreamRemote.addTrack(audioReceiver.track);
mediaStreamRemote.addTrack(videoReceiver.track);
videoRenderer.srcObject = mediaStreamRemote;
videoRenderer.play();
```

<span data-ttu-id="aab53-167">1:1 通話の設定に慣れたら、同じ原則に従って、メッシュトポロジを使って小規模グループの通話を設定します。各ピアには、グループの残りの部分と1:1 の接続があります。</span><span class="sxs-lookup"><span data-stu-id="aab53-167">Once familiar with setting up 1:1 calls, apply the same principles to set up small group calls using a mesh topology, where each peer will have a 1:1 connection with the rest of the group.</span></span> <span data-ttu-id="aab53-168">並列フォークは Microsoft Edge プラットフォームではサポートされていないため、これは1:1 のシグナルで処理されるため、 [`IceGatherer`](https://msdn.microsoft.com/library/Mt433107) [`DtlsTransport`](https://msdn.microsoft.com/library/Mt502495) 個々の接続に対して独立型とオブジェクトが使われます。</span><span class="sxs-lookup"><span data-stu-id="aab53-168">Since parallel forking is not supported on the Microsoft Edge platform, this should be handled via 1:1 signaling, so that independent [`IceGatherer`](https://msdn.microsoft.com/library/Mt433107) and [`DtlsTransport`](https://msdn.microsoft.com/library/Mt502495) objects will be used for each connection.</span></span>

## <span data-ttu-id="aab53-169">Microsoft Edge の実装の詳細</span><span class="sxs-lookup"><span data-stu-id="aab53-169">Implementation details in Microsoft Edge</span></span>


<span data-ttu-id="aab53-170">Ortc spec は、"実装のための呼び出し" を発行したものであり、JavaScript API レベルでの重大な課題が想定されていないため、比較的安定しています。</span><span class="sxs-lookup"><span data-stu-id="aab53-170">The ORTC spec has been relatively stable since the ORTC Community Group issued the "Call for Implementations," and significant challenges at the JavaScript API level are not expected.</span></span> <span data-ttu-id="aab53-171">これに基づいて、Microsoft Edge の実装は、プロトコルレベルでのクロスブラウザーの相互運用テストに対してリリースされました。</span><span class="sxs-lookup"><span data-stu-id="aab53-171">Based on this, Microsoft Edge implementation has been released for cross-browser interoperability testing at the protocol level.</span></span>

<span data-ttu-id="aab53-172">Microsoft Edge の実装では、いくつかの制限事項に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aab53-172">A few limitations in the Microsoft Edge implementation should be noted:</span></span>

* `RTCIceTransportController` <span data-ttu-id="aab53-173">はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="aab53-173">is not supported.</span></span> <span data-ttu-id="aab53-174">Microsoft Edge の実装では、各トランスポートベースでの氷の固定/解除を処理するため、すべてを注文する `IceTransports` 必要はありません。</span><span class="sxs-lookup"><span data-stu-id="aab53-174">Microsoft Edge implementation handles ICE freezing/unfreezing on a per-transport basis, so that ordering all the `IceTransports` is not necessary.</span></span> <span data-ttu-id="aab53-175">この方法は、既存の実装と相互運用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aab53-175">This approach should interoperate with existing implementations.</span></span>
* `RtpListener` <span data-ttu-id="aab53-176">はまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="aab53-176">is not yet supported.</span></span> <span data-ttu-id="aab53-177">これは、で SSRCs (ストリームと同期ソース) を事前に指定する必要があることを意味し [`RtpReceiver`](https://msdn.microsoft.com/library/Mt502508) ます。</span><span class="sxs-lookup"><span data-stu-id="aab53-177">This means that SSRCs (stream and synchronization sources) need to be specified in advance within the [`RtpReceiver`](https://msdn.microsoft.com/library/Mt502508).</span></span>
* <span data-ttu-id="aab53-178">Fork は `IceTransport` 、、 `IceGatherer` 、またはのどちらでもまだサポートされていません `DtlsTransport` 。</span><span class="sxs-lookup"><span data-stu-id="aab53-178">Forking is not yet supported in either `IceTransport`, `IceGatherer`, or `DtlsTransport`.</span></span> <span data-ttu-id="aab53-179">フォークの解 `DtlsTransport` は、"ORTC コミュニティ" の [ディスカッション] の下に残っています。</span><span class="sxs-lookup"><span data-stu-id="aab53-179">The solution to `DtlsTransport` forking is still under discussion in the ORTC Community Group.</span></span>
* <span data-ttu-id="aab53-180">RTP/RTCP ノン mux `DtlsTransport` はまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="aab53-180">RTP/RTCP non-mux with `DtlsTransport` is not yet supported.</span></span> <span data-ttu-id="aab53-181">アプリケーションを使う場合 `DtlsTransport` は、RTP/RTCP マルチプレクサーをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aab53-181">When using `DtlsTransport` your application will need to support RTP/RTCP mux.</span></span>
* <span data-ttu-id="aab53-182">[`RTCRtpEncodingParameters Dictionary`](https://msdn.microsoft.com/library/mt502505(v=vs.85).aspx)Microsoft Edge では、現在、エンコード品質コントロールのほとんどが無視されますが、"active" 属性と ' ssrc ' 属性の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="aab53-182">In [`RTCRtpEncodingParameters Dictionary`](https://msdn.microsoft.com/library/mt502505(v=vs.85).aspx), Microsoft Edge currently ignores most of the encoding quality controls, but does require setting the 'active' and 'ssrc' attributes.</span></span>
* <span data-ttu-id="aab53-183">`icecandidatepairchanged`イベントはまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="aab53-183">The `icecandidatepairchanged` event is not yet supported.</span></span> <span data-ttu-id="aab53-184">このメソッドを通じて候補のペアの情報を抽出でき [`getNominatedCandidatePair`](https://msdn.microsoft.com/library/Mt433087) ます。</span><span class="sxs-lookup"><span data-stu-id="aab53-184">You can extract the candidate pair information through the [`getNominatedCandidatePair`](https://msdn.microsoft.com/library/Mt433087) method.</span></span>
* <span data-ttu-id="aab53-185">Microsoft Edge では、現在、 `DataChannel` ORTC spec で定義されている機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="aab53-185">Microsoft Edge currently does not support any of the `DataChannel` functionality currently defined in the ORTC spec.</span></span>

#### <span data-ttu-id="aab53-186">今後の予定</span><span class="sxs-lookup"><span data-stu-id="aab53-186">Looking forward</span></span>

<span data-ttu-id="aab53-187">Microsoft Edge の実装はまだ早い時点であり、今後数か月の間も機能が拡張されることを期待しています。</span><span class="sxs-lookup"><span data-stu-id="aab53-187">Microsoft Edge implementation is still early, expect the feature set to continue to grow in the coming months.</span></span> <span data-ttu-id="aab53-188">Microsoft Edge の実装の目標は、今日の web 全体での相互運用性であり、長期的なリアルタイム通信産業にも対応しています。</span><span class="sxs-lookup"><span data-stu-id="aab53-188">The goal for Microsoft Edge implementation is interoperability across the web today as well as with the real-time communications industry in the long term.</span></span>



## <span data-ttu-id="aab53-189">API リファレンス</span><span class="sxs-lookup"><span data-stu-id="aab53-189">API reference</span></span>

[<span data-ttu-id="aab53-190">ORTC (オブジェクトリアルタイム通信)</span><span class="sxs-lookup"><span data-stu-id="aab53-190">ORTC (Object Real-Time Communications)</span></span>](https://msdn.microsoft.com/library/Mt433097)

## <span data-ttu-id="aab53-191">デモ</span><span class="sxs-lookup"><span data-stu-id="aab53-191">Demos</span></span>

[<span data-ttu-id="aab53-192">SimpleWebRTC</span><span class="sxs-lookup"><span data-stu-id="aab53-192">SimpleWebRTC</span></span>](https://developer.microsoft.com/microsoft-edge/testdrive/demos/simplewebrtc/)

[<span data-ttu-id="aab53-193">ORTC 通話</span><span class="sxs-lookup"><span data-stu-id="aab53-193">ORTC phone call</span></span>](https://developer.microsoft.com/microsoft-edge/testdrive/demos/twilioortc/)

[<span data-ttu-id="aab53-194">ORTC デモ</span><span class="sxs-lookup"><span data-stu-id="aab53-194">ORTC demo</span></span>](https://developer.microsoft.com/microsoft-edge/testdrive/demos/ortcdemo/)

## <span data-ttu-id="aab53-195">関連トピック</span><span class="sxs-lookup"><span data-stu-id="aab53-195">Related topics</span></span>

[<span data-ttu-id="aab53-196">ORTC API を Microsoft Edge で利用できるようになりました</span><span class="sxs-lookup"><span data-stu-id="aab53-196">ORTC API is now available in Microsoft Edge</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=627564)

[<span data-ttu-id="aab53-197">SimpleWebRTC: Microsoft Edge の ORTC API と Chrome および Firefox の WebRTC Api を使って、ブラウザー間の会議通話を行います。</span><span class="sxs-lookup"><span data-stu-id="aab53-197">SimpleWebRTC: Use Microsoft Edge's ORTC API and the WebRTC APIs in Chrome and Firefox to make cross-browser conference calls.</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=629636)

[<span data-ttu-id="aab53-198">Skype、Skype for Business、Microsoft Edge で、Web 向けのシームレスな通信エクスペリエンスを実現します。</span><span class="sxs-lookup"><span data-stu-id="aab53-198">Enabling Seamless Communication Experiences for the Web with Skype, Skype for Business, and Microsoft Edge.</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=671722)

[<span data-ttu-id="aab53-199">ORTC (オブジェクトリアルタイム通信) コミュニティグループ</span><span class="sxs-lookup"><span data-stu-id="aab53-199">ORTC (OBJECT REAL-TIME COMMUNICATIONS) COMMUNITY GROUP</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=671724)

## <span data-ttu-id="aab53-200">キャスト</span><span class="sxs-lookup"><span data-stu-id="aab53-200">Specification</span></span>

[<span data-ttu-id="aab53-201">W3C Object RTC (ORTC) API for WebRTC</span><span class="sxs-lookup"><span data-stu-id="aab53-201">W3C Object RTC (ORTC) API for WebRTC</span></span>](http://draft.ortc.org/)  
