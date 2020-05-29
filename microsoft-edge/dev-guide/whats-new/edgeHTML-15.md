---
description: このガイドでは、EdgeHTML 15 に含まれている開発者向けの機能と標準の概要について説明します。
title: EdgeHTML 15 の新機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.custom: seodec18
ms.openlocfilehash: e750a9272bb8bcdb51662839a31cc303c4064ef9
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568852"
---
# EdgeHTML 15 の新機能
Microsoft Edge プラットフォームの現在のリリースで出荷された変更については、「Windows 10 の作成者[更新プログラム](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97)(04/2017、ビルド 15063)」を参照してください。 Microsoft Edge ブラウザー全体の変更の概要については、「 [Windows 10 の作成者による更新プログラム」の「Microsoft edge の新機能](https://blogs.windows.com/msedgedev/2017/04/11/introducing-edgehtml-15/#DrVEvmPU6TPq3tMK.97)」を参照してください。

以降の Windows Insider Preview ビルドでの変更については、「 [EdgeHTML の新機能](../whats-new.md)」を参照してください。

次の変更の固定リンクを示し **[https://aka.ms/devguide_edgehtml_15](https://aka.ms/devguide_edgehtml_15)** ます。

## 新機能

### CSS のカスタムプロパティ
Microsoft Edge で[css のカスタムプロパティ](https://drafts.csswg.org/css-variables/)がサポートされるようになりました。 css 変数。 CSS 変数を使用すると、ユーザー設定の CSS プロパティを作成して、繰り返し色などの重複データの量を減らすことができます。 CSS 変数の使い方は簡単です。

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

### 交差するオブザーバー
EdgeHTML 15 では、[交差するオブザーバー API](https://w3c.github.io/IntersectionObserver/)の仕様が導入されています。 交差するオブザーバー API では、他の要素またはグローバルビューポートを基準とした DOM 要素の位置と可視性を非同期的に照会することができます。 この API では、ユーザーが表示されているときに要素を効率的に通知するためのメソッドを作成することによって、カスタムのコストコードを不要にしています。

### JavaScript

パフォーマンス最適化は、Chakra JavaScript エンジンの EdgeHTML 15 のバージョンで、中央のステージを実行します。 Windows 10 の作成者が更新されると、Chakra は、関数を再利用してヒープ引数を最適化し、ミニ修正コードのパフォーマンスを向上させることによってメモリを節約します。

さらに、EdgeHTML 15 では、次の機能のプレビューが導入されています。

#### 実験的な JavaScript 機能 ( *about: flags*で有効)

* [WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) [プレゼンテーション (デモ](https://webassembly.org/demo/))
* [共有メモリと Atomics](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)

詳細については、「JavaScript のパフォーマンスが向上しました」[*および「Microsoft Edge で共有メモリ*](https://blogs.windows.com/msedgedev/2017/04/20/improved-javascript-performance-webassembly-shared-memory/#t4gwUKjjtdmstMbs.97)」を参照してください。

### 支払い要求 API
[支払い要求 API](https://w3.org/TR/payment-request/)がサポートされるようになりました。これにより、Windows 10 の Pc と電話で web での支払いや支払いがより簡単になります。 この API により、Microsoft Edge は、ユーザーがクラウドに保存された支払い方法 (クレジットカードなど) との仲介として機能します。 支払い要求 API の詳細については、「支払要求 API と[支払い要求 api](/microsoft-edge/dev-guide/device/payment-request-api)開発者ガイドの[紹介](https://blogs.windows.com/msedgedev/2016/12/15/payment-request-api-edge/)」をご覧ください。

### TCP Fast Open (TFO)
TCP Fast Open は、TCP 接続を開くために必要なラウンドトリップの数を減らし、ブラウザーネットワークのパフォーマンスを向上させるための機能です。 詳しくは、「高速で[安全な web サイトを作成する](https://blogs.windows.com/msedgedev/2016/06/15/building-a-faster-and-more-secure-web-with-tcp-fast-open-tls-false-start-and-tls-1-3/#eQMauReErmIRXYqh.97)」をご覧ください。 さまざまなネットワークトポロジの相互運用性の違いにより、Microsoft Edge では、この機能は既定で有効になっていません。 有効にするには、 `about:flags` アドレスバーに入力し、[*ネットワーク*] セクションで [ **TCP Fast Open を有効にする**] チェックボックスをオンにします。 

### WebRTC と相互運用可能な RTC ビデオコーデックのサポート

EdgeHTML 15 は、以前のバージョンの W3C WebRTC API circa 2015 で構築されたアプリケーションとの相互運用性を実現するために、WebRTC 1.0 API のサブセットをサポートしています。 詳細については、 [WEBRTC API リファレンス](https://msdn.microsoft.com/library/mt806139(v=vs.85).aspx)を参照してください。

ピアツーピアの音声とビデオによる通信で最も高度な機能を利用するには、[オブジェクトリアルタイム通信 API](../realtime-communication/object-rtc-api.md)を使うことをお勧めします。 ORTC API は、グループの音声通話とビデオ通話を設定したり、個々のトランスポート、送信者、レシーバーオブジェクトを直接制御したりする場合に適しています。

Microsoft Edge は、ORTC と WebRTC 1.0 を使って、VP8 ビデオとビデオの[両方をサポート](https://tools.ietf.org/html/rfc4585)しており、両方の種類の[コーデックをサポート](https://tools.ietf.org/html/draft-alvestrand-rmcat-remb-03)し[てい](https://tools.ietf.org/html/rfc4588)ます。これは、次の機能をサポート[します。](https://webrtc.org/experiments/rtp-hdrext/abs-send-time/)

詳細については、「 [WebRTC 1.0 と相互運用可能なリアルタイム通信の概要 (Microsoft Edge](https://blogs.windows.com/msedgedev/2017/01/31/introducing-webrtc-microsoft-edge/#k8XMeWKyZDQDPYR4.97))」を参照してください。

### WebVR

Microsoft Edge では、Windows Mixed Reality ヘッドマウントされたディスプレイと Microsoft Edge を接続する実験的 API である[Webvr](https://immersive-web.github.io/webxr/)をサポートしています。 この接続によって、web サイト内での VR コンテンツの使用が可能になります。また、イマーシブ VR のエクスペリエンスはデスクトップアプリケーションに限定されなくなります。  

Microsoft Edge の仮想現実は、3D と2D のグラフィックスをレンダリングするための JavaScript API である WebGL によって実現されています。 BabylonJS などの WebGL ライブラリで構築された WebGL アプリケーションとアプリケーションはサポートされています。 接続すると、WebVR はヘッドセットの周りの位置情報とセンサー情報に対応する視覚効果を送信します。 WebVR API では、[ゲームパッド api](../dom/gamepad-api.md)の拡張機能により、空間コントローラーもサポートされています。 この API は既定でオンになっているため、フラグを切り替える必要はありません。

詳しくは、 [Webvr api リファレンス](https://msdn.microsoft.com/library/mt806281(v=vs.85).aspx)と[ゲームパッド api リファレンス](https://msdn.microsoft.com/library/dn743630(v=vs.85).aspx)をご覧ください。

 > [!NOTE] 
 > WebVR の仕様はまだ開発段階のため、Microsoft Edge の実装は後で変更される可能性があります。



## 更新された機能

### コンテンツセキュリティポリシー (レベル 2)
CSP 1 を使用しているサイトは、引き続き、CSP 2 の Microsoft Edge のサポートに対応している必要があり `frame-src` ます。ただし、ワーカースクリプトを作成するディレクティブは、新しいディレクティブに切り替えることをお勧めし `child-src` ます。 (CSP 3 で `frame-src` は、ワーカーには適用されなくなります)。CSP 2 は、次の項目も追加します。

1. 新しいディレクティブ: `base-uri` 、、、 `child-src` `form-action` `frame-ancestors` および `plugin-types` 。 詳細については、 [Microsoft Edge でサポートされている CSP ディレクティブ](../security/content-security-policy.md)を参照してください。

2. Worker のサポート: バックグラウンドワーカースクリプトは、それらを読み込むドキュメントのポリシーとは別のポリシーによって制御されます。 ホストドキュメントの場合と同様に、応答ヘッダーでワーカーの CSP を設定することができます。 また、CSP 2 での新方法 `allow-scripts` として、 `allow-same-origin` ディレクティブのフラグと `sandbox` ワーカースレッドの作成に影響が出るようになりました。

3. インラインスクリプトとスタイル: CSP 2 では、nonces とハッシュを空白文字のメカニズムとして提供することで、インラインスクリプトとスタイルブロックの実行を許可します。 Nonces は、CSP ポリシーとページ内のスクリプトタグの両方に表示される、各ページ読み込みに対して生成されるランダムなベース64値です。 ページが読み込み時に動的に生成されると、サーバーは nonce 値を生成し、その値をページの NonceToken に挿入し、コンテンツセキュリティポリシーの HTTP ヘッダーでも宣言します。 ハッシュは、 *sha256* *sha384* *sha512* `<script>` `<style>` `script-src` `style-src` CSP ポリシーで指定された a または element のコンテンツから (sha256、sha384、または sha512 アルゴリズム経由で) 生成される静的な値です。

4. CSP 違反の報告: 新しいイベントとして、SecurityPolicyViolationEvent が CSP 違反に対して発生しました。 CSP レポートの以前のメカニズムは `report-uri` 引き続きサポートされます。 いくつかの新しいフィールドが、(違反し `effectiveDirective` たポリシー)、( `statusCode` HTTP 応答コード)、 `sourceFile` (問題のあるリソースの URL)、、などの両方に共通する違反レポートに追加されてい `lineNumber` `columnNumber` ます。

### Web 認証
[Windows Hello](https://go.microsoft.com/fwlink/p/?LinkID=624961)生体認証を使用した新しい[Web 認証 API](../device/web-authentication.md)に対する Microsoft Edge のサポートは、次のような変更が加えられました。
- [EdgeHTML 14](https://blogs.windows.com/msedgedev/2016/08/04/introducing-edgehtml-14/#TVSCzKDkG4jCI5mt.97) (Windows 10 記念日更新プログラム、ビルド10240、7/2016) で導入された実験的な WEB 認証 API の最初の実装は、プレフィックス付き Api ( [MSCredentials](https://msdn.microsoft.com/library/mt697639)インターフェイス) を介して公開されました。 これらの Api は依然として EdgeHTML 15 で利用できますが、指定されていない、標準ベースの Api、および仕様の[最新のスナップショット](https://w3.org/TR/2016/WD-webauthn-20160928)で定義されている標準ベースの api と動作を優先して使用することは推奨されていません。仕様が標準化されるため、変更は引き続き行われる可能性があります。

- 最新の Microsoft Edge の実装は、既定でオフになっています。フラグを付けます (この `about:flags` 機能を有効にするには、アドレスバーに入力します)。

- Microsoft Edge では、USB キーや Bluetooth デバイスなどの外部資格情報はまだサポートしていません。 現在の API は、TPM に保存されている埋め込まれた資格情報に制限されています。 デバイスで TPM が利用できない場合は、ソフトウェアフォールバックが使用されます。

- 現在ログインしている Windows のユーザーアカウントは、少なくとも1つの PIN をサポートするように構成されている必要があります。また、推奨されるフェースまたは指紋の生体認証 これにより、Windows で TPM へのアクセスが認証されるようになります。

- この仕様で説明されている[定義済みの拡張機能](https://w3.org/TR/webauthn/#extension-predef)のうち、Microsoft Edge では、現時点では[FIDO AppId](https://w3.org/TR/webauthn/#extension-appid) () のみがサポートされて `webauthn_txAuthSimple` います。

- この `timeoutSeconds` オプションは現在評価されていません

### WebDriver

EdgeHTML 15 では、サイレントコマンドラインフラグと新しいコマンドエンドポイントのサポートなど、いくつかの WebDriver の更新プログラムを提供しています。

メソッド | URI テンプレート | コマンド
:----- | :----------  | :--------
POST | /セッション id/イベント id/alert/accept | [通知を受信する](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-accept-alert)
POST | /セッション id/イベント id/通知/無視 | [通知を無視する](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-dismiss-alert)
GET | セッション id/イベント id}/alert/text | [通知テキストを取得する](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-alert-text)
POST | セッション id/イベント id}/alert/text | [通知テキストを送信する](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-send-alert-text)
POST | /セッション id/execute/async | [Async スクリプトを実行する](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-async-script)
POST | /セッション id/execute/sync | [スクリプトを実行する](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-script)
GET | /セッション id}/window | [ウィンドウハンドルを取得する](https://w3c.github.io/webdriver/webdriver-spec.html#get-window-handle)
GET | /セッション id/ウィンドウのウィンドウ/ハンドル | [ウィンドウハンドルを取得する](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-window-handles)

その他の WebDriver 機能の詳細とその他の WebDriver 機能の状態については、「 [webdriver](../../webdriver.md)」をご覧ください。

## EdgeHTML 15 の新しい Api

EdgeHTML 15 の新しい Api の一覧を次に示します。 [Interface name] の形式で一覧表示され**ます。 [api 名]**。

<iframe height='582' scrolling='no' title='新しい EdgeHTML15 Api' src='//codepen.io/MicrosoftEdgeDocumentation/embed/evRjjZ/?height=582&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><a href='http://codepen.io/MicrosoftEdgeDocumentation/pen/evRjjZ/'> </a> CodePen の Microsoft Edge ドキュメント (@MicrosoftEdgeDocumentation) による Pen New EdgeHTML15 api に関する記事を参照してください <a href='http://codepen.io/MicrosoftEdgeDocumentation'> </a> <a href='http://codepen.io'> </a> 。</iframe>  

## 以前の EdgeHTML リリース
[EdgeHTML 12/Windows ビルド 10240 (7/2015)](https://aka.ms/devguide_edgehtml_12)

[EdgeHTML 13/Windows ビルド 10586 (11/2015)](https://aka.ms/devguide_edgehtml_13)

[EdgeHTML 14/Windows ビルド 14393 (8/2016)](https://aka.ms/devguide_edgehtml_14)
