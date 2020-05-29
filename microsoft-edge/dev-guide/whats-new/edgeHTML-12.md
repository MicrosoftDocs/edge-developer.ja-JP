---
description: このページでは、EdgeHTML 12 の新機能の概要を説明します。
title: EdgeHTML 12 の新機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: f16db0551d4bea3d29b974c2a35fff2adf476c75
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568822"
---
# EdgeHTML 12 の新機能

Microsoft Edge では、最新の優れた Windows web プラットフォームを常に入手できるように、コアの相互運用性によって設計された新しい "生きた" エンジン EdgeHTML が導入されています。 Microsoft Edge では、従来のコード (ActiveX コントロール、ブラウザーヘルパーオブジェクト (BHOs)、その他のさまざまな web 開発慣行をサポートするために必要な従来のコードから無料の中断が提供されます。 さらに、Microsoft Edge には、ネイティブの PDF サポートが用意されています。 IE11 の場合、従来のドキュメントモードは廃止され、Microsoft Edge では、サポートするブラウザーインフラストラクチャが存在しません。 詳しい情報については、「 [Ieblog](https://go.microsoft.com/fwlink/p/?LinkID=519011) 」をご覧ください。

ここでは、 [Windows 10](https://blogs.windows.com/windowsexperience/2015/07/28/windows-10-free-upgrade-available-in-190-countries)の最初のリリース (07/2015、ビルド 10240) の EdgeHTML 12 に同梱されている変更について説明します。 Microsoft Edge ブラウザー全体の変更の概要については、「過去の予定」 ( [microsoft の新しい web レンダリングエンジン](https://blogs.windows.com/msedgedev/2015/02/26/a-break-from-the-past-the-birth-of-microsofts-new-web-rendering-engine/)と、過去の[中断、「パート 2: ActiveX、VBScript、attachevent](https://blogs.windows.com/msedgedev/2015/05/06/a-break-from-the-past-part-2-saying-goodbye-to-activex-vbscript-attachevent/)の終了」) を参照してください。

次の変更の固定リンクを示し [https://aka.ms/devguide_edgehtml_12](https://aka.ms/devguide_edgehtml_12) ます。


## 新機能

### コンテンツセキュリティポリシー1.0
Microsoft Edge で、コンテンツセキュリティポリシー (CSP) 1.0 が実装されるようになりました。 CSP セキュリティ標準では、web 開発者が、クロスサイトスクリプティング (XSS)、clickjacking、その他のコードインジェクション攻撃を回避することを目的として、特定のページを取得または実行して、信頼できる web ページのコンテキストで悪意のあるコンテンツを実行できるようにすることができます。 Microsoft Edge の CSP について詳しくは、「[コンテンツセキュリティポリシー](https://docs.microsoft.com/microsoft-edge/dev-guide/security/content-security-policy) 」をご覧ください。 

### フィルター効果
Microsoft Edge では、要素に視覚的効果を追加する簡単な方法を提供しています。 プロパティを使うと `filter` 、ブラーの追加、明るさの調整、ドロップシャドウの追加、不透明度の変更などを、要素に対して行うことができます。 純粋な CSS を使うと、1つの要素に複数のフィルター効果を適用して、フィルターをアニメーション化することができます。 詳細については、「[フィルター効果](https://docs.microsoft.com/microsoft-edge/dev-guide/css/filter-effects)」を参照してください。

### JavaScript
JavaScript のサポートは、Internet Explorer (IE11) と Microsoft Edge の最終バージョンで若干異なります。 Edge の新機能は次のとおりです。

| | |
|--|--|
|**明細**| [class](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/class) (実験的) [。の](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/for...of) |
|**対象**| [約束](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Promise)、[プロキシ](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Proxy)、[記号](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Symbol)、[設定](/scripting/javascript/reference/weakset-object-javascript) |
|**関数** | [acosh](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/acosh)、 [codepointat](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/codepointat)、 [fromcodepoint ポイント](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/fromcodepoint)、 [hypot](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/hypot)、 [imul](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/imul)、 [isinteger](/scripting/javascript/reference/number-isinteger-function-number-javascript)、 [isinteger](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number/isnan)、 [raw](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/raw) |
|**メソッド**| [含む](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/includes)[キー](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/keys) (配列)、[繰り返し](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/repeat)(文字列)、 [values](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/values) (配列) |
|**その他の機能**| [関数](https://developer.mozilla.org/docs/Learn/JavaScript/Building_blocks/Functions)(実験的)、[ジェネレーター](https://developer.mozilla.org/docs/Web/JavaScript/Guide/Iterators_and_generators)、[反復子](https://developer.mozilla.org/docs/Web/JavaScript/Guide/Iterators_and_generators)、[正規表現 `y` フラグ](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/RegExp)(実験的)、[テンプレート文字列](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Template_literals)、 [Unicode コードポイントエスケープ文字](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Lexical_grammar#String_literals) |

Internet Explorer、Microsoft Edge、Microsoft ストアアプリ全体での JavaScript のサポートの比較については、「 [*Javascript バージョン情報*](./javascript-version-information.md)」をご覧ください。

### メディアのキャプチャとストリーム
Microsoft Edge では、 [W3C メディアキャプチャとストリーム](https://go.microsoft.com/fwlink/p/?LinkID=534096)の仕様に基づいたメディアキャプチャとストリーム api のサポートが導入されています。 これらの JavaScript Api により、web ページは、web カメラやマイクなどのメディアキャプチャデバイスにアクセスすることができます。 メディアキャプチャとストリーム Api を使うことで、web カメラを使って写真をキャプチャしたり、マイクから音声メッセージをキャプチャしたりするなど、シナリオを作成することができます。 Microsoft edge でのメディアキャプチャについて詳しくは、 [Microsoft Edge 開発者ブログ](https://blogs.windows.com/msedgedev/2015/05/13/announcing-media-capture-functionality-in-microsoft-edge/)をご覧ください。 

### 新しい HTML 要素と属性
* `meter` 要素
* `picture` 要素
* `template` 要素
* `image` 要素: `srcset` と `sizes` 属性 (Microsoft Edge Developer[ブログの投稿](https://blogs.windows.com/msedgedev/2015/06/08/introducing-srcset-responsive-images-in-microsoft-edge/))
* `selectionDirection` attribute
* `input type=time` および `input type=datetime-local`

### オブジェクト RTC API 
オブジェクトリアルタイム通信 (ORTC) を使うと、web ブラウザー、モバイルデバイス、およびネイティブ JavaScript Api を介して、メディア (音声やビデオ) をリアルタイムで直接ストリーミング (送受信) できます。 Microsoft Edge での ORTC について詳しくは、「開発ガイドのトピック[オブジェクト RTC API](https://docs.microsoft.com/microsoft-edge/dev-guide/realtime-communication/object-rtc-api) 」をご覧ください。 

### 閲覧表示
Microsoft Edge には、ページ上の関連性のない、または他の二次的なコンテンツを気にせずに、web ページをより効率的に使用できるようにするための閲覧表示が用意されています。 閲覧表示は、アドレスバー (または Ctrl + Shift + R) の [閲覧表示] ([ブック] アイコン) ボタンでオンまたはオフに切り替えることができます。 詳細については、「[閲覧表示](https://docs.microsoft.com/microsoft-edge/dev-guide/browser/reading-view)」を参照してください。 

### 検索プロバイダーの検出
Microsoft Edge のアドレスバーには、検索候補、web の結果、閲覧履歴、お気に入りなど、リッチ検索の統合機能が組み込まれています。 Microsoft Edge は、 [OpenSearch 1.1](https://go.microsoft.com/fwlink/p/?LinkID=208582)仕様に従って、web 検索プロバイダーを検出して使用します。 検索プロバイダーの場合は、Microsoft Edge でサービスがサポートされていることを確認する方法についての[詳細を参照](https://docs.microsoft.com/microsoft-edge/dev-guide/browser/search-provider-discovery)してください。 

### WebKit Api のサポート
互換性を向上させるため、Microsoft Edge では、さまざまな "-webkit-" というプレフィックスの Api がサポートされています。 サポートされている "-webkit-" Api の完全な一覧については、 [Api カタログ](https://developer.microsoft.com/microsoft-edge/platform/catalog/?page=1&q=webkit)を使用してください。

### Web オーディオ
Microsoft Edge では、 [W3C Web AUDIO API](https://go.microsoft.com/fwlink/p/?LinkID=512167)仕様のサポートが導入されています。 Web オーディオは、web アプリケーションのオーディオを処理および synthesizing し、オーディオと音楽の豊富なエクスペリエンスを実現するための高レベルの JavaScript API です。 HTML5 要素は `audio` 基本的なストリーミングオーディオの再生に対応していますが、Web AUDIO API にはさまざまな api が用意されています。これによって、大量の同期を使用して複数のサウンドを再生したり、混合オーディオでゲイン、フェード、画面切り替え、基本的な効果を適用したりすることができます。 詳細については、開発ガイドおよび[Microsoft Edge 開発者ブログ](https://blogs.windows.com/msedgedev/2015/05/19/bringing-web-audio-to-microsoft-edge-for-interoperable-gaming-and-enthusiast-media/)の[「Web オーディオ](https://docs.microsoft.com/microsoft-edge/dev-guide/multimedia/web-audio)」を参照してください。 

### Web ドライバー 
[W3C WebDriver API](https://w3.org/TR/webdriver/)は、プラットフォームと言語に依存しないインターフェイスとワイヤプロトコルで、プログラムまたはスクリプトが web ブラウザーの動作を制御できるようにします。 WebDriver を使うと、開発者は、ユーザーの操作をシミュレートする自動テストを作成できます。 WebDriver はブラウザーで実行されている JavaScript の機能と情報にアクセスできないため、これは JavaScript 単体テストとは異なり、ユーザーイベントや OS レベルのイベントをより正確にシミュレートすることができます。 WebDriver は、1回のテストセッションで複数のウィンドウ、タブ、web ページ間でテストを管理することもできます。  Microsoft Edge 用 WebDriver の使用を開始する方法について詳しくは、「 [webdriver](https://docs.microsoft.com/microsoft-edge/dev-guide/tools/webdriver)」をご覧ください。 


## EdgeHTML 12 の新しい Api

EdgeHTML 12 の新しい Api の一覧を次に示します。  [Interface name] の形式で一覧表示され**ます。 [api 名]**。

 > [!NOTE] 
 > これらの Api の多くは、IE11 で提供されています。 以下の EdgeHTML 12 のデータは、EdgeHTML の初期バージョンと以降のバージョンを比較するためのベースラインとして提供されています。

<iframe height='580' scrolling='no' title='EdgeHTML 12 の新しい Api' src='//codepen.io/MicrosoftEdgeDocumentation/embed/pPOwby/?height=580&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/pPOwby/'> </a> CodePen の Microsoft Edge ドキュメント (@MicrosoftEdgeDocumentation) での EdgeHTML 12 の Pen 新しい api を参照してください <a href='https://codepen.io/MicrosoftEdgeDocumentation'> </a> <a href='https://codepen.io'> </a> 。</iframe>
