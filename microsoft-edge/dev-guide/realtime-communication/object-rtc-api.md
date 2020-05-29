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
# オブジェクト RTC API

オブジェクトリアルタイム通信 (ORTC) を使うと、web ブラウザー、モバイルデバイス、およびネイティブ Javascript Api を介して、メディア (音声やビデオ) をリアルタイムで直接ストリーミング (送受信) できます。

> [!NOTE]
> Microsoft Edge では、Windows 10 デバイスに対して ORTC が実装されています。 ただし、この実装は、最新バージョンの[ORTC API](https://go.microsoft.com/fwlink/p/?LinkID=690096)とは異なります。 ORTC は、Microsoft Edge の開発とリリースの後で進化し続けています。ブラウザーは、ORTC API 内のすべてのオブジェクトやメソッドを実装するわけではなく、現時点で定義に組み込まれていない拡張機能も含まれています。 さらに開発には引き続き、世界中の開発者が、Skype ユーザーやその他の WebRTC 対応のコミュニケーションサービスに通話を発信する機能を備えたエクスペリエンスを構築できるようにしています。



ORTC の実践的な体験を得るには、次のデモをテストドライブで試してください。
-  [SimpleWebRTC](https://developer.microsoft.com/microsoft-edge/testdrive/demos/simplewebrtc/)
-  [ORTC 通話](https://developer.microsoft.com/microsoft-edge/testdrive/demos/twilioortc/)
-  [ORTC デモ](https://developer.microsoft.com/microsoft-edge/testdrive/demos/ortcdemo/)


ORTC の詳細については、Microsoft edge dev ブログの[Microsoft edge で、「ORTC API を使用できるようになりました](https://go.microsoft.com/fwlink/p/?LinkID=627564)。」をご覧ください。


## 概要図


次の図は、ORTC オブジェクト間の関係を説明する概要を示しています。 水平方向または斜め方向の矢印は、メディアまたはデータの流れを示し、縦方向矢印はメソッドとイベントでの相互作用を表します。

ORTC は、"*送信者*"、"*受信者*"、"*トランスポート*" の各オブジェクトを使用します。これには、実行できる操作について説明されている "*機能*" と "*パラメーター*" が含まれています。 "*追跡*" は、送信者によるメディアストリームのキャプチャとエンコード、トランスポート上の移動、ビデオ/オーディオタグにメディアストリームトラックをレンダリングするレシーバーによるデコードなどを行います。

![Microsoft Edge の、 ](./../media/ortc_diagram.png) 上の図の図で [`RTCRtpSender`](https://msdn.microsoft.com/library/Mt502516) は、a または a に転送される、入力として提供されるトラックをエンコードしてい [`RTCDtlsTransport`](https://msdn.microsoft.com/library/Mt502495) [`RTCSrtpSdesTransport`](https://msdn.microsoft.com/library/Mt502527) ます。 デュアルトーンマルチ周波数 (DTMF) トーンの送信は、でサポートされてい [`RTCDtmfSender`](https://msdn.microsoft.com/library/Mt502496) ます。

を [`RTCDtlsTransport`](https://msdn.microsoft.com/library/Mt502495) 使用して、 [`RTCSrtpSdesTransport`](https://msdn.microsoft.com/library/Mt502527) [`RTCIceTransport`](https://msdn.microsoft.com/library/Mt433112) 受信側のピアに到達するための通信パスを選択し `RTCIceTransport` ます。これは、メディアに関連付けられている、またはによって `RTCDtlsTransport` 、と `RTCSrtpSdesTransport` の重複を解除し [`RTCRtpReceiver`](https://msdn.microsoft.com/library/Mt502508) ます。 次に、 `RTCRtpReceiver` メディアをデコードし、オーディオタグまたはビデオタグでレンダリングされたトラックを生成します。

他のいくつかのオブジェクトも役割を果たします。 [`RTCIceGatherer`](https://msdn.microsoft.com/library/Mt433107)1 つのオブジェクトによって使用されるローカル ICE 候補を収集 [`RTCIceTransport`](https://msdn.microsoft.com/library/Mt433112) します。 API の残りの部分では、RTP の*機能*と*パラメーター*、*操作の統計情報*、 [WebRTC 1.0 API](https://go.microsoft.com/fwlink/p/?LinkID=627573)との互換性に関する詳細について説明しています。

> [!NOTE]
> Microsoft Edge ではデータチャネルが実装されていないため、 `RTCDataChannel` と `RTCSctpTransport` オブジェクトはサポートされません。




## Microsoft Edge の初期実装でサポートされているコンポーネント


* **ORTC API のサポート。** 音声/ビデオ通信は主要なフォーカスであり、次のオブジェクト、、、、、 [`RTCIceGatherer`](https://msdn.microsoft.com/library/Mt433107) [`RTCIceTransport`](https://msdn.microsoft.com/library/Mt433112) [`RTCDtlsTransport`](https://msdn.microsoft.com/library/Mt502495) [`RTCRtpSender`](https://msdn.microsoft.com/library/Mt502516) [`RTCRtpReceiver`](https://msdn.microsoft.com/library/Mt502508) および [`RTCStats`](https://msdn.microsoft.com/library/Mt589726) 図に直接表示されていないインタフェースが含まれます。
* **RTP/RTCP マルチプレクシングのサポート。** [`RTP/RTCP multiplexing`](https://msdn.microsoft.com/library/Mt502503)は、と共に使用する必要が [`DtlsTransport`](https://msdn.microsoft.com/library/Mt502495) あります。 また、A/V マルチプレクシングもサポートされています。
* **STUN/TURN/ICE サポート。** STUN [(rfc 5389)](https://go.microsoft.com/fwlink/p/?LinkID=627619)、TURN [(rfc 5766)](https://go.microsoft.com/fwlink/p/?LinkID=627620) 、および ICE [(rfc 5245)](https://go.microsoft.com/fwlink/p/?LinkID=627621)がサポートされています。 ICE では、標準の参加がサポートされ、(受け手として) 積極的な推薦が部分的にサポートされます。 DTLS-SRTP [(RFC 5764)](https://go.microsoft.com/fwlink/p/?LinkID=627622)は、DTLS 1.0 [(RFC4347)](https://go.microsoft.com/fwlink/p/?LinkID=627629)に基づいてサポートされています。
* **コーデックのサポート。** [オーディオコーデック](https://msdn.microsoft.com/library/Mt599587)については、722、OPUS、SILK をサポートしています。 また、RTCWEB audio の要件に従って、お客様には快適な雑音 (CN) と DTMF もサポートしています。 ビデオについては、現在 [`H.264UC`](https://msdn.microsoft.com/library/Mt589706) Skype サービスで使用されているコーデックがサポートされています。 simulcast、スケーラブルなビデオコーディング、転送エラー訂正などの高度な機能をサポートしています。 ここでは、相互運用可能なビデオを H. 264 で有効にするために取り組んでいます。

> [!NOTE]
> WebRTC 1.0 の実装に精通していて、WebRTC 1.0 と ORTC 内のオブジェクトサポートの進化に関心がある場合は、2014 IIT RTC 会議: "[ORTC API Update](http://www.rtc-conference.com/2016/wp-content/uploads/gravity_forms/2-2f7a537445fa703985ab4d2372ac42ca/2014/10/ORTC_API_Update.pdf)" から、Google、Microsoft、および Hookflash によって次のプレゼンテーションを行うことをお勧めします。




## 1:1 通信用のアプリレベルのコードフロー


このシナリオでは、2つの Windows 10 マシンが、web サーバとの間で通信を確立するために、ピア間で情報を交換するために、2つのピアを2つのピアとして処理します。

次の手順は、1つのピアによって実行される操作を対象としています。 どちらのピアも、1:1 通信をセットアップするために、同様の手順を実行する必要があります。 以下のコードスニペットをさらに詳しく理解するには、 [Microsoft Edge テストドライブデモ](https://go.microsoft.com/fwlink/p/?LinkID=627635)を参照してください。

この例では、オーディオビデオと RTP/RTCP 多重化を使用しています。これにより、1つの ICE と DTLS transport のみが表示され、オーディオとビデオの両方に対して RTP と RTCP のパケットが伝送されます。

`Step #1.` [`MediaStream`](https://msdn.microsoft.com/library/Mt131875)1 つのオーディオトラックと1つのビデオトラックを含むオブジェクト ([メディアキャプチャとストリーム API](./../multimedia/media-Capture-and-Streams.md)) を作成します。

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

`Step #2.` を作成 [`ICE gatherer`](https://msdn.microsoft.com/library/mt433107(v=vs.85).aspx) し、ローカル [`ICE candidates`](https://msdn.microsoft.com/library/Mt502499) がリモートピアに通知されるようにします。

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

ユーザーのプライバシーを保護するために、Microsoft Edge には、ユーザーがローカルホストの IP アドレスをオブジェクトによって公開できるかどうかを制御できるオプションが導入さ [`IceGatherer`](https://msdn.microsoft.com/library/Mt433107) れています。 この設定を切り替えるためのインターフェイスオプションが用意されています。

[Microsoft Edge テストドライブデモ](https://go.microsoft.com/fwlink/p/?LinkID=627635)では、TURN server がセットアップされています。 この TURN server はスループットが非常に限定されているため、デモページの使用のみに限定されています。

`Step #3.` [`ICE transport`](https://msdn.microsoft.com/library/Mt433112)オーディオとビデオのためのを作成し、ICE トランスポート上のリモートでの処理を準備し [`ICE candidates`](https://msdn.microsoft.com/library/Mt502499) ます。

```js
var iceTr = new RTCIceTransport();
mySignaller.onRemoteCandidate = function(remote) {
    iceTr.addRemoteCandidate(remote.candidate);
}
```

ここでは、すべてのリモート ICE 候補を配列に蓄積し `remoteCandidates` て、 `iceTr.setRemoteCandidates(remoteCandidates)` すべてのリモート候補をまとめて追加する方法について説明します。

`Step #4.` DTLS トランスポートを作成します。

```js
var dtlsTr = new RTCDtlsTransport(iceTr);
```

`Step #5.` 送信者と受信者のオブジェクトを作成します。

```js
var audioTrack = mediaStreamLocal.getAudioTracks()[0];
var videoTrack = mediaStreamLocal.getVideoTracks()[0];
var audioSender = new RtpSender(audioTrack, dtlsTr);
var videoSender = new RtpSender(videoTrack, dtlsTr);
var audioReceiver = new RtpReceiver(dtlsTr, "audio");
var videoReceiver = new RtpReceiver(dtlsTr, "video");
```

手順 #6 受信者と送信者の機能を取得します。

```js
var recvAudioCaps = RTCRtpReceiver.getCapabilities("audio");
var recvVideoCaps = RTCRtpReceiver.getCapabilities("video");
var sendAudioCaps = RTCRtpSender.getCapabilities("audio");
var sendVideoCaps = RTCRtpSender.getCapabilities("video");
```

`Step #7.` ICE/DTLS パラメーターと送受信機能を交換できます。

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

`Step #8.` リモートのパラメーターを取得して、 [`ICE`](https://msdn.microsoft.com/library/Mt433112) およびトランスポートを開始し、 [`DTLS`](https://msdn.microsoft.com/library/Mt502495) オーディオとビデオの送受信パラメーターを設定します。

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

次に示すのは、ヘルパー関数のスケルトンです。 詳細については、 [Microsoft Edge テストドライブのデモ](https://go.microsoft.com/fwlink/p/?LinkID=627635)を参照してください。

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

`Step #9.` ビデオタグを介してリモートメディアストリームトラックをレンダリングし、再生します。

```js
var videoRenderer = document.getElementById("myRtcVideoTag");
var mediaStreamRemote = new MediaStream();
mediaStreamRemote.addTrack(audioReceiver.track);
mediaStreamRemote.addTrack(videoReceiver.track);
videoRenderer.srcObject = mediaStreamRemote;
videoRenderer.play();
```

1:1 通話の設定に慣れたら、同じ原則に従って、メッシュトポロジを使って小規模グループの通話を設定します。各ピアには、グループの残りの部分と1:1 の接続があります。 並列フォークは Microsoft Edge プラットフォームではサポートされていないため、これは1:1 のシグナルで処理されるため、 [`IceGatherer`](https://msdn.microsoft.com/library/Mt433107) [`DtlsTransport`](https://msdn.microsoft.com/library/Mt502495) 個々の接続に対して独立型とオブジェクトが使われます。

## Microsoft Edge の実装の詳細


Ortc spec は、"実装のための呼び出し" を発行したものであり、JavaScript API レベルでの重大な課題が想定されていないため、比較的安定しています。 これに基づいて、Microsoft Edge の実装は、プロトコルレベルでのクロスブラウザーの相互運用テストに対してリリースされました。

Microsoft Edge の実装では、いくつかの制限事項に注意する必要があります。

* `RTCIceTransportController` はサポートされていません。 Microsoft Edge の実装では、各トランスポートベースでの氷の固定/解除を処理するため、すべてを注文する `IceTransports` 必要はありません。 この方法は、既存の実装と相互運用する必要があります。
* `RtpListener` はまだサポートされていません。 これは、で SSRCs (ストリームと同期ソース) を事前に指定する必要があることを意味し [`RtpReceiver`](https://msdn.microsoft.com/library/Mt502508) ます。
* Fork は `IceTransport` 、、 `IceGatherer` 、またはのどちらでもまだサポートされていません `DtlsTransport` 。 フォークの解 `DtlsTransport` は、"ORTC コミュニティ" の [ディスカッション] の下に残っています。
* RTP/RTCP ノン mux `DtlsTransport` はまだサポートされていません。 アプリケーションを使う場合 `DtlsTransport` は、RTP/RTCP マルチプレクサーをサポートする必要があります。
* [`RTCRtpEncodingParameters Dictionary`](https://msdn.microsoft.com/library/mt502505(v=vs.85).aspx)Microsoft Edge では、現在、エンコード品質コントロールのほとんどが無視されますが、"active" 属性と ' ssrc ' 属性の設定が必要です。
* `icecandidatepairchanged`イベントはまだサポートされていません。 このメソッドを通じて候補のペアの情報を抽出でき [`getNominatedCandidatePair`](https://msdn.microsoft.com/library/Mt433087) ます。
* Microsoft Edge では、現在、 `DataChannel` ORTC spec で定義されている機能をサポートしていません。

#### 今後の予定

Microsoft Edge の実装はまだ早い時点であり、今後数か月の間も機能が拡張されることを期待しています。 Microsoft Edge の実装の目標は、今日の web 全体での相互運用性であり、長期的なリアルタイム通信産業にも対応しています。



## API リファレンス

[ORTC (オブジェクトリアルタイム通信)](https://msdn.microsoft.com/library/Mt433097)

## デモ

[SimpleWebRTC](https://developer.microsoft.com/microsoft-edge/testdrive/demos/simplewebrtc/)

[ORTC 通話](https://developer.microsoft.com/microsoft-edge/testdrive/demos/twilioortc/)

[ORTC デモ](https://developer.microsoft.com/microsoft-edge/testdrive/demos/ortcdemo/)

## 関連トピック

[ORTC API を Microsoft Edge で利用できるようになりました](https://go.microsoft.com/fwlink/p/?LinkID=627564)

[SimpleWebRTC: Microsoft Edge の ORTC API と Chrome および Firefox の WebRTC Api を使って、ブラウザー間の会議通話を行います。](https://go.microsoft.com/fwlink/p/?LinkID=629636)

[Skype、Skype for Business、Microsoft Edge で、Web 向けのシームレスな通信エクスペリエンスを実現します。](https://go.microsoft.com/fwlink/p/?LinkID=671722)

[ORTC (オブジェクトリアルタイム通信) コミュニティグループ](https://go.microsoft.com/fwlink/p/?LinkID=671724)

## キャスト

[W3C Object RTC (ORTC) API for WebRTC](http://draft.ortc.org/)  
