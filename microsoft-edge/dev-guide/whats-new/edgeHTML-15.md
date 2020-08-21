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
# Microsoft EdgeHTML 15 の新機能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

[Windows 10 Creators Update](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) \(04/2017, ビルド 15063\) に含めた変更は次のとおりです。  Microsoft Edge ブラウザー全体の変更の概要については [、Windows 10 Creators Update の Microsoft Edge の新機能をご覧ください](https://blogs.windows.com/msedgedev/2017/04/11)。  

以降の Windows Insider Preview ビルドの変更については [、EdgeHTML の新機能を参照してください](../whats-new.md)。  

次の一覧を行うと、この機能が利用できます  [https://aka.ms/devguide_edgehtml_15](./edgehtml-15.md) 。  

## 新機能  

### CSS カスタム プロパティ  

Microsoft Edge では [、CSS](https://drafts.csswg.org/css-variables)のカスタム プロパティ (A.k.a CSS 変数) がサポートされるようになりました。  CSS 変数を使用すると、スタイルシート全体で再利用できるカスタム CSS プロパティを作成して、繰り返しカラーなど、重複データの量を減らすことができます。  CSS 変数は簡単に使用できます。  

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

### Intersection Observer  

EdgeHTML 15 では [、Intersection Observer API](https://w3c.github.io/IntersectionObserver) の指定が追加されました。  Intersection Observer API を使用すると、他の要素またはグローバル ビューポートとの間で DOM 要素の位置と表示を非同期で実行できます。  この API では、ユーザーがビューにいるときに要素を効果的に知らすための方法を作成することで、カスタムの経用コードが必要なくなります。  

### JavaScript  

Chakra JavaScript エンジンの EdgeHTML 15 Reva によってパフォーマンス最適化が行われます。  Windows 10 Creators Update では、Chakra は関数を再度段階的に定義し、ヒープ引数を最適化することでメモリを保存し、ミニされたコードのパフォーマンスを改善します。  

さらに、Microsoft EdgeHTML 15 では、次の機能プレビューが追加されました。  

#### 実用 JavaScript 機能  

有効 `about:flags`  

*   [WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) \([デモ](https://webassembly.org/demo)ル \)  
*   [共有メモリとアトミックス](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

[詳細については、Microsoft Edge で JavaScript のパフォーマンス、WebAssembly、共有メモ](https://blogs.windows.com/msedgedev/2017/04/20)リを改善して詳細を確認します。  

### 支払い要求 API  

[Payment Request API](https://w3.org/TR/payment-request)がサポートされるようになりました。Windows 10 PC およびスマートフォンで Web 上で簡単なチェックアウトと支払いを有効にできるようになりました。  この API により、Microsoft Edge は、クラウドに保存されている一部のコンシューマー、コンシューマー、支払方法 \(クレジット カード\) 間の中間として機能します。  支払い要求 API の詳細については、シンプルな Web ペイリングを [確認してください。支払要求 API と](https://blogs.windows.com/msedgedev/2016/12/15) [Payment Request API 開発者ガイドの](/microsoft-edge/dev-guide/device/payment-request-api) 説明を追加してください。  

### TCP ファースト オープン (TFO)  
TCP ファースト オープンは、ブラウザー ネットワークのパフォーマンスを向上させるために必要なラウンド トリップの数を減らす機能です。  [詳細については、TCP ファ](https://blogs.windows.com/msedgedev/2016/06/15)ースト オープンを使用して、高速でより高度な Web を構築してください。  ネットワーク トポロジの不整合のため、Microsoft Edge では、この機能は既定では無効になっています。  これを有効にするには、アドレス バーに入力し、[ `about:flags` **ネットワーク] セクションの下にある [TCP ファーストオーストを有効** にする] チェック ボックスを **オンに** します。  

### WebRTC と操作可能な RTC ビデオ コーデック サポート  

Microsoft EDGEHTML 15 は、以前のバージョンの W3C WebRTC-PC API 円で作成されたアプリケーションとの互換性を保つために、WebRTC 1.0 API のサブセットをサポートしています。  [詳細については、WebRTC API リ](/previous-versions//mt806139(v=vs.85))ファレンスを参照してください。  

ピア間の音声とビデオ通信で最も高度な機能を活用するには [、Object Real-Time Communication) API を使用することをお勧めします](https://ortc.org)。  ORTC API は、グループの音声通話やビデオ通話をセットアップする場合や、個々のトランスポート、送信者、受信者オブジェクトを直接制御する必要がある場合に適しています。  

Microsoft Edge は、ORTC と WebRTC 1.0 が付いた H.264/AVC と VP8 のビデオの両方をサポートしており、両方のコーデックの種類 ([送信](https://webrtc.org/experiments/rtp-hdrext/abs-send-time)時、[良](https://tools.ietf.org/html/draft-alvestrand-rmcat-remb-03)いリマブ、画像損失インジケーションと[汎用 NACK フィードバック](https://tools.ietf.org/html/rfc4585)[、RTP リミュ](https://tools.ietf.org/html/rfc4588)ーション) のサポートに対応しています。  

詳細については、Microsoft Edge で [WebRTC 1.0 の概要と、WebRTC の](https://blogs.windows.com/msedgedev/2017/01/31)知識ややすいリアルタイム通信を参照してください。  

### WebVR  

Microsoft Edge では [、Windows](https://immersive-web.github.io/webxr)Mixed Reality Headed ディスプレイと Microsoft Edge を接続する実用的 API をサポートできるようになりました。  この接続により、VR コンテンツは Web サイト内での経験ができるため、VR エクスペリエンスが高いデスクトップ アプリケーションに制限がないことを意味します。  

Microsoft Edge の仮想リアルティは WebGL を利用しています。これは WebGL を利用することで、3D グラフィックと 2D グラフィックをレンダリングするための JavaScript API。  WebGL ライブラリ (BabylonJS など) ライブラリで作成された WebGL アプリケーションとアプリケーションがサポートされます。  接続すると、WebVR はヘッドセットの位置と上下に表示される位置と情報を視覚的に送信します。  WebVR API は、ゲームパッド API の拡張機能にかかって、バティカル コントローラ [ーもサポートしています](../dom/gamepad-api.md)。  この API は既定でオンになっているため、フラグを切り替えなくてもかなりません。  

詳細 [については、WebVR API](/previous-versions//mt806281(v=vs.85)) リファレ [ンスとゲームパッド API リファレン](https://developer.mozilla.org/docs/Web/API/Gamepad_API) スを参照してください。  

 > [!NOTE] 
 > WebVR の速度は開発中であるため、Microsoft Edge の実装は後で行直す場合があります。  

## 更新された機能  

### コンテンツ セキュリティ ポリシー (レベル 2)  

既に CSP 1 を使用しているサイトは、CSP 2 の Microsoft Edge サポートに連絡する必要がありますが、ワーカー スクリプトを読み込むディレクティブを、現在のサイトの正しい正常性に向けて新しいディレクティブ `frame-src` `child-src` に切り替えることをおすすめします。  \(CSP 3 では `frame-src` 、workers.\) CSP 2 にも次の情報が追加されます。  

:::row:::
   :::column span="1":::
      新しいダイレクト  
   :::column-end:::
   :::column span="2":::
      `base-uri`、 `child-src` `form-action` および `frame-ancestors` `plugin-types` .  [詳細については、Microsoft Edge で CSP ディレクティブをサポート](../security/content-security-policy.md)している Microsoft Edge を参照してください。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      作業者のサポート  
   :::column-end:::
   :::column span="2":::
      バックグラウンド ワーカー スクリプトは、ドキュメントの読み込みポリシーとは別に、それぞれのポリシーによって管理されます。  ホスト ドキュメントと同じように、応答ヘッダーに作業者の CSP を設定できます。  また、CSP 2 の新機能は、ワーカー スレッドの作成に影響を与える  `allow-scripts` `allow-same-origin` `sandbox` ことです。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      インライン スクリプトとスタイル  
   :::column-end:::
   :::column span="2":::
      CSP 2 では、ニーズとハッシュをホワイトリスト メカニズムとして指定することで、インライン スクリプトとスタイルのブロックの実行を行えます。  Nonce は、各ページ読み込みに対して生成されるランダム 64 値であり、ページ内のスクリプト タグの両方に表示されます。  ページが読み込みで動的に生成されると、サーバーは nonce 値を生成し、ページに NonceToken に挿入し、コンテンツ セキュリティ ポリシーの HTTP ヘッダーでも説明します。  ハッシュは、CSP ポリシーで `<script>` `<style>` \(または `script-src` directives\) を指定したコンテンツから生き出される統計値 `style-src` です。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      CSP のバリオのレポート  
   :::column-end:::
   :::column span="2":::
      新しいイベントは CSP の休文 `SecurityPolicyViolationEvent` に送信されました。  CSP レポートの以前のメカニスムは引き `report-uri` 続きサポートされます。  いくつかの新しいフィールドが `effectiveDirective` 、\(違う/ポリシーが違う `statusCode` )、\(HTTP 応答コード\)、\(オフロンド リソースの URL の URL) など、両方に共通する休末報告書に `sourceFile` `lineNumber` いくつかの新しいフィールドが追加されています `columnNumber` 。  
   :::column-end:::
:::row-end:::  

### Web 認証  

[Windows Hello](https://www.microsoft.com/windows/comprehensive-security)の生き出[しを使用した EPI](../device/web-authentication.md)のサポートが、次の変更に加えました。  

*   [EdgeHTML 14](https://blogs.windows.com/msedgedev/2016/08/04)での実用 Web 認証 API の初期実装は、MS-- プレフィックス付き API [\(MSCredentials](/previous-versions//mt697639(v=vs.85))インターフェイス\) によって展開されています。  これらの API は Microsoft EdgeHTML 15 でも引き続き使用できますが、定義の最近のスナップショットで定義されている非定義の標準 API と動作の基本で廃止され、標準[recent snapshot](https://w3.org/TR/2016/WD-webauthn-20160928)化に向けて速度の高さが向上するため、そのように継続的に変更される場合があります。  

*   既定では、Microsoft Edge の実装は既定では無効になっており、フラグ \の後で出荷されます (この機能を `about:flags` 有効にするにはアドレス バーに入力してください)。  

*   Microsoft Edge では、USB キーやデバイスなどの外部資ーデ資BluetoothはまだBluetoothいません。  現在の API は TPM に保存されている埋め込み資ーデンシャルに限定されます。  デバイスで TPM を利用できない場合、ソフトウェア フォールバックが使用されます。  

*   Windows ユーザー アカウントに現在ログインしている場合は、PIN をサポートしており、少なくとも、対面または指紋のバリックスを必要とする必要があります。  これは、Windows が TPM へのアクセスを認証できるようにするためです。  

*   この時 [点では](https://w3.org/TR/webauthn/#extension-predef) 、Microsoft Edge では [FIDO AppId](https://w3.org/TR/webauthn/#extension-appid) \(\) のみ `webauthn_txAuthSimple` をサポートしています。  

*  現在 `timeoutSeconds` 、オプションは評価されていません  

### WebDriver  

Microsoft EdgeHTML 15 では、サイレント コマンド ライン フラグや新しいコマンド エンドポイントのサポートなど、WebDriver の更新プログラムを一部の WebDriver の更新プログラムで利用できます。  

| メソッド | URI テンプレート | コマンド |  
|:--- |:---  |:--- |    
| POST | /session/{session id}/alert/accept | [通知を承諾する](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-accept-alert) |  
| POST | /session/{session id}/alert/dismiss | [アラートを削除する](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-dismiss-alert) |  
| GET | /session/{session id}/alert/text | [通知テキストを取得する](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-alert-text) |  
| POST | /session/{session id}/alert/text | [通知テキストを送信する](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-send-alert-text) |  
| POST | /session/{session id}/execute/async | [非同期スクリプトの実行](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-async-script) |  
| POST | /session/{session id}/execute/sync | [スクリプトの実行](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-script) |  
| GET | /session/{session id}/window | [ウィンドウ ハンドルを入手する](https://w3c.github.io/webdriver/webdriver-spec.html#get-window-handle) |  
| GET | /session/{session id}/window/handles | [ウィンドウ ハンドルを入手する](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-window-handles) |  

WebDriver のその他の機能の詳細と状態については、WebDriver [を参照してください](../../webdriver.md)。  

## EdgeHTML 15 の新しい API  

EdgeHTML 15 の新しい API の完全な一覧を次に示します。  これらは形式で表示されます `[interface name].[api name]` 。  

<iframe height='582' scrolling='no' title='New EdgeHTML15 API' src='//codepen.io/MicrosoftEdgeDocumentation/embed/evRjjZ/?height=582&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><a href='http://codepen.io/MicrosoftEdgeDocumentation/pen/evRjjZ/'> </a> CodePen で、Microsoft Edge Docs (新しい EdgeHTML15 API <a href='http://codepen.io/MicrosoftEdgeDocumentation'> </a> @MicrosoftEdgeDocumentation) <a href='http://codepen.io'> を参照してください </a> 。</iframe>  

## 以前の EdgeHTML リリース  

[Microsoft EdgeHTML 12 / Windows ビルド 10240 (7/2015)](./edgehtml-12.md)  

[Microsoft EdgeHTML 13 / Windows ビルド 10586 (2015/11)](./edgehtml-13.md)  

[EdgeHTML 14 / Windows ビルド 14393 (8/2016)](./edgehtml-14.md)  
