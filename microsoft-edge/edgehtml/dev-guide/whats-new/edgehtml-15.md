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
# EdgeHTML 15 の新機能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

[Windows 10 Creators Update \(04/2017,](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) Build 15063\) の現在のリリースの Microsoft Edge プラットフォームに同梱されている変更点を次に示します。  Microsoft Edge ブラウザー全体の変更点の概要については [、Windows 10 Creators Update](https://blogs.windows.com/msedgedev/2017/04/11)の Microsoft Edge の新機能に関するページをご覧ください。  

それ以降の Windows Insider Preview ビルドの変更については [、「EdgeHTML](../whats-new.md)の新機能」を参照してください。  

次の変更の一覧の permalink を次に示します  [https://aka.ms/devguide_edgehtml_15](./edgehtml-15.md) 。  

## 新機能  

### CSS カスタム プロパティ  

Microsoft Edge では [、CSS カスタム プロパティ (CSS](https://drafts.csswg.org/css-variables)変数) がサポートされます。  CSS 変数を使用すると、スタイルシート全体で再利用できるカスタム CSS プロパティを作成して、重複するデータの量 (色の繰り返しなど) を減らします。  CSS 変数の使用は簡単です。  

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

### 交差オブザーバー  

EdgeHTML 15 では、Intersection [Intersection API の仕様が導入](https://w3c.github.io/IntersectionObserver) されています。  Intersection Intersection API を使用すると、他の要素またはグローバル ビューポートを基準に DOM 要素の位置と表示を非同期に照会できます。  この API では、要素が表示されているときに効率的に通知するメソッドを作成することで、コストの高いカスタム コードが不要になります。  

### JavaScript  

パフォーマンスの最適化は、Chakra JavaScript エンジンの EdgeHTML 15 rev を使用して中心に行います。  Windows 10 Creators Update では、Chakra は関数を再延期し、ヒープ引数を最適化することでメモリを節約し、コードを最適化するパフォーマンスを向上させます。  

さらに、EdgeHTML 15 では、次の機能のプレビューが導入されています。  

#### 試験的な JavaScript 機能  

有効 `about:flags`  

*   [WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) \([demo](https://webassembly.org/demo)\)  
*   [共有メモリとアトミック](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

詳細 [については、Microsoft Edge の JavaScript パフォーマンス、WebAssembly、共有](https://blogs.windows.com/msedgedev/2017/04/20) メモリの改善に関するページを参照してください。  

### 支払い要求 API  

支払 [い要求 API](https://w3.org/TR/payment-request) がサポートされ、Windows 10 PC とスマートフォン上の Web でのチェックアウトと支払いを簡単にできます。  この API を使用すると、Microsoft Edge は、業者、消費者、および消費者がクラウドに保存した支払い方法 \(クレジット カード\など) の仲介者として機能できます。  支払い要求 API の詳細については、「簡単な Web 支払い:支払い要求 [API](https://blogs.windows.com/msedgedev/2016/12/15) と支払い要求 [API](/microsoft-edge/dev-guide/device/payment-request-api) 開発者ガイド」をご覧ください。  

### TCP Fast Open (TFO)  
TCP ファスト オープンは、TCP 接続を開くのに必要なラウンド トリップ数を減らして、ブラウザーのネットワーク パフォーマンスを向上させる機能です。  詳細については [、「TCP Fast Open を使用してより高速で安全な Web を構築する」を参照してください](https://blogs.windows.com/msedgedev/2016/06/15)。  さまざまなネットワーク トポロジの相互運用性の違いにより、この機能は Microsoft Edge では既定で有効になっていません。  有効にするには、アドレス バーに入力し、[ネットワーク] セクションの [TCP ファスト オープンを有効にする] チェック ボックス `about:flags` **をオン**にします。 ****  

### WebRTC と相互運用可能な RTC ビデオ コーデックのサポート  

EdgeHTML 15 は、W3C WebRTC-PC API circa 2015 の以前のバージョンで構築されたアプリケーションとの相互運用性を確保するために、WebRTC 1.0 API のサブセットをサポートしています。  詳細については [、WebRTC API リファレンス](/previous-versions//mt806139(v=vs.85)) を参照してください。  

ピアツーピアの音声およびビデオ通信で最も高度な機能を利用するには [、Object Real-Time Communication) API](https://ortc.org)を使用することをお勧めします。  ORTC API は、グループの音声通話とビデオ通話を設定する場合や、個々のトランスポート オブジェクト、送信者オブジェクト、および受信者オブジェクトを直接制御する場合に適しています。  

Microsoft Edge は、ORTC と WebRTC 1.0 で H.264/AVC と VP8 の両方のビデオをサポートし、両方のコーデックの種類をサポートする次の機能を提供します。abs-send-time、goog-remb、Picture [Loss Indication and Generic NACK feedback](https://tools.ietf.org/html/rfc4585), [](https://webrtc.org/experiments/rtp-hdrext/abs-send-time) [RTP Retransmission](https://tools.ietf.org/html/rfc4588). [](https://tools.ietf.org/html/draft-alvestrand-rmcat-remb-03)  

詳細については、Microsoft Edge での [WebRTC 1.0](https://blogs.windows.com/msedgedev/2017/01/31)と相互運用可能なリアルタイム通信の紹介を参照してください。  

### WebVR  

Microsoft Edge では、Windows Mixed Reality ヘッド マウント ディスプレイと Microsoft Edge を接続する試験的な API である [WebVR](https://immersive-web.github.io/webxr)がサポートされました。  この接続により、VR コンテンツを Web サイト内で体験できます。つまり、イマーシブ VR エクスペリエンスはデスクトップ アプリケーションに限定されなくなりました。  

Microsoft Edge の仮想現実には、3D および 2D グラフィックスをレンダリングする JavaScript API である WebGL が搭載されています。  BabylonJS のような WebGL ライブラリで構築された WebGL アプリケーションとアプリケーションがサポートされています。  接続されると、WebVR はヘッドセットの位置とセンサー情報に対応する視覚効果を送信します。  WebVR API は、ゲームパッド API の拡張機能により空間コントローラー **もサポートします**。  この API は既定で有効なので、フラグを切り替える必要はありません。  

<!--  Virtual reality in Microsoft Edge is powered by WebGL, a JavaScript API for rendering 3D and 2D graphics.  WebGL applications and applications built with WebGL libraries like BabylonJS are supported.  Once connected, WebVR sends visuals corresponding to the position and sensor information around the headset.  The WebVR API also supports spatial controllers thanks to an extension to the [Gamepad API](../dom/gamepad-api.md).  This API is on by default, so no need to toggle a flag.  -->  

詳細については [、WebVR API リファレンス](/previous-versions/mt806281(v=vs.85)) と [ゲームパッド API リファレンス](https://developer.mozilla.org/docs/Web/API/Gamepad_API) を参照してください。  

 > [!NOTE] 
 > WebVR 仕様はまだ開発中です。Microsoft Edge の実装は後で変更される可能性があります。  

## 更新された機能  

### コンテンツ セキュリティ ポリシー (レベル 2)  

CSP 1 を既に使用しているサイトは、CSP 2 に対する Microsoft Edge サポートで引き続き動作する必要があります。ただし、ワーカー スクリプトを読み込むディレクティブを新しいディレクティブに切り替えて、サイトの将来性を高め続けるのが最善です。 `frame-src` `child-src`  \(CSP 3 では、ワーカーには適用されなくなりました。\) CSP 2 では、次の機能 `frame-src` も追加されます。  

:::row:::
   :::column span="1":::
      新しいディレクティブ  
   :::column-end:::
   :::column span="2":::
      `base-uri`,, `child-src` `form-action` , and `frame-ancestors` `plugin-types` .  <!--  See [Microsoft Edge supported CSP directives](../security/content-security-policy.md) for more.  -->  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ワーカーサポート  
   :::column-end:::
   :::column span="2":::
      バックグラウンド ワーカー スクリプトは、読み込むドキュメントのポリシーとは別に、独自のポリシーによって管理されます。  ホスト ドキュメントと同様に、応答ヘッダーでワーカーの CSP を設定できます。  また、CSP 2 の新機能は、ディレクティブのフラグがワーカー スレッドの作成 `allow-scripts` `allow-same-origin` `sandbox` に影響を与える点です。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      インライン スクリプトとスタイル  
   :::column-end:::
   :::column span="2":::
      CSP 2 では、nonce とハッシュを許可一覧メカニズムとして提供することで、インライン スクリプトとスタイル ブロックを実行できます。  Nonce は、CSP ポリシーとページ内のスクリプト タグの両方に表示される各ページ読み込みで生成されるランダムな Base 64 値です。  読み込み時にページが動的に生成されると、サーバーは nonce 値を生成し、その値をページ内の NonceToken に挿入し、コンテンツ セキュリティ ポリシー HTTP ヘッダーでも宣言します。  ハッシュは、CSP ポリシーで \(using または `<script>` `<style>` `script-src` directives\) が指定された 1 つ以上の要素のコンテンツから \(sha256、sha384、sha512 アルゴリズムを使用して `style-src` ) 生成される静的な値です。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      CSP 違反の報告  
   :::column-end:::
   :::column span="2":::
      新しいイベントは `SecurityPolicyViolationEvent` 、CSP 違反時に発生します。  CSP レポートの以前のメカニズム `report-uri` は、引き続きサポートされています。  両方に共通する違反レポートには `effectiveDirective` 、\(違反したポリシー\)、\(HTTP 応答コード\)、\(問題を引き受けるリソース `statusCode` の URL\)、および `sourceFile` `lineNumber` `columnNumber` .  
   :::column-end:::
:::row-end:::  

### Web 認証  

Windows Hello 生体認証を使用する新しい **Web 認証 API** に対する Microsoft [Edge](https://www.microsoft.com/windows/comprehensive-security) のサポートは、次の変更によって更新されました。  

<!--  Microsoft Edge support for the emerging [Web Authentication API](../device/web-authentication.md) using [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) biometrics has been updated with the following changes:  -->  

*   [EdgeHTML 14](https://blogs.windows.com/msedgedev/2016/08/04) \(Windows 10 Anniversary Update ビルド 10240、7/2016\) で導入された試験的な Web 認証 API の初期実装は、MS- プレフィックス付き API [\(MSCredentials](/previous-versions/mt697639(v=vs.85))インターフェイス\) を通じて公開されました。  これらの API は EdgeHTML 15 でも引き続き使用できます。これらの API は、仕様の最新のスナップショットで定義されたプレフィックス付きでない標準ベース[](https://w3.org/TR/2016/WD-webauthn-20160928)の API と動作を推奨して廃止され、仕様が標準化に向けて成熟するに従って変化し続ける可能性があります。  

*   最新の Microsoft Edge 実装は既定でオフにされ、フラグ \(type `about:flags` in your address bar to turn on the feature\) の背後に出荷されます。  

*   Microsoft Edge では、USB キーや外部デバイスなど、外部資格情報Bluetoothされていません。  現在の API は、TPM に格納されている埋め込み資格情報に制限されています。  デバイスで TPM を利用できない場合は、ソフトウェア フォールバックが使用されます。  

*   現在ログインしている Windows ユーザー アカウントは、少なくとも PIN、できれば顔認証または指紋生体認証をサポートするように構成する必要があります。  これは、Windows が TPM へのアクセスを認証するための方法です。  

*   仕様で [説明されている定義済](https://w3.org/TR/webauthn/#extension-predef) みの拡張機能の中で、Microsoft Edge は現時点では [FIDO AppId](https://w3.org/TR/webauthn/#extension-appid) \( `webauthn_txAuthSimple` \) のみをサポートしています。  

*  この `timeoutSeconds` オプションは現在評価されません  

### WebDriver  

EdgeHTML 15 では、サイレント コマンド ライン フラグと新しいコマンド エンドポイントのサポートを含む、一部の WebDriver 更新プログラムが提供されます。  

| メソッド | URI テンプレート | コマンド |  
|:--- |:---  |:--- |    
| POST | /session/{session id}/alert/accept | [通知を受け入れる](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-accept-alert) |  
| POST | /session/{session id}/alert/dismiss | [アラートを閉じる](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-dismiss-alert) |  
| GET | /session/{session id}/alert/text | [アラート テキストを取得する](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-alert-text) |  
| POST | /session/{session id}/alert/text | [通知テキストを送信する](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-send-alert-text) |  
| POST | /session/{session id}/execute/async | [非同期スクリプトの実行](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-async-script) |  
| POST | /session/{session id}/execute/sync | [スクリプトの実行](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-script) |  
| GET | /session/{session id}/window | [ウィンドウ ハンドルを取得する](https://w3c.github.io/webdriver/webdriver-spec.html#get-window-handle) |  
| GET | /session/{session id}/window/handles | [ウィンドウ ハンドルを取得する](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-window-handles) |  

他の WebDriver 機能の詳細と状態については [、WebDriver を参照してください](../../webdriver/index.md)。  

## EdgeHTML 15 の新しい API  

EdgeHTML 15 の新しい API の完全な一覧を次に示します。  これらは次の形式で一覧表示されます `[interface name].[api name]` 。  

<iframe height='582' scrolling='no' title='新しい EdgeHTML15 API' src='//codepen.io/MicrosoftEdgeDocumentation/embed/evRjjZ/?height=582&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>CodePen で Microsoft Edge Docs ( @MicrosoftEdgeDocumentation ) による Pen New <a href='http://codepen.io/MicrosoftEdgeDocumentation/pen/evRjjZ/'> EdgeHTML15 </a> <a href='http://codepen.io/MicrosoftEdgeDocumentation'> API </a> を <a href='http://codepen.io'> 参照してください </a> 。</iframe>  

## 以前の EdgeHTML リリース  

[EdgeHTML 12 / Windows ビルド 10240 (7/2015)](./edgehtml-12.md)  

[EdgeHTML 13 / Windows ビルド 10586 (11/2015)](./edgehtml-13.md)  

[EdgeHTML 14 / Windows ビルド 14393 (8/2016)](./edgehtml-14.md)  
