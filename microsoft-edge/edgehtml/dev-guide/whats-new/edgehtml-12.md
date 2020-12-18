---
description: このページでは、EdgeHTML 12 の新機能の概要について説明します。
title: EdgeHTML 12 の新機能と API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 8a96d75ff7decf2c6efdfee3be94736707fea5a6
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234695"
---
# EdgeHTML 12 の新機能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Microsoft Edge では、常に最新の最大の Windows Web プラットフォームを確実に取得するために、相互運用性をコアとして設計された新しい "生きている" エンジンである EdgeHTML が導入されています。  Microsoft Edge は、ActiveX コントロール、ブラウザー ヘルパー オブジェクト \(BHOs\)、その他の過去の Web 開発プラクティスをサポートするために必要な従来のコードから解放され、過去からのクリーンなブレークを提供します。  さらに、Microsoft Edge はネイティブ PDF サポートを提供します。  IE11 では、従来のドキュメント モードは廃止され、Microsoft Edge では、それらをサポートするブラウザー インフラストラクチャは存在しません。  詳しくは [、IEBlog](/archive/blogs/ie/living-on-the-edge-our-next-step-in-interoperability) をご覧ください。  

[Windows 10](https://blogs.windows.com/windowsexperience/2015/07/28/windows-10-free-upgrade-available-in-190-countries) \(07/2015, Build 10240\) の最初のリリースで EdgeHTML 12 に同梱されている変更点を次に示します。  Microsoft Edge ブラウザー全体に対する変更の概要については、過去からの休憩を参照してください [。Microsoft](https://blogs.windows.com/msedgedev/2015/02/26) の新しい Web レンダリング エンジンの生まれと過去からの休憩、パート [2: ActiveX、VBScript、attachEvent...](https://blogs.windows.com/msedgedev/2015/05/06)にさよならを言う。  

次の変更の一覧の permalink を次に示します  [https://aka.ms/devguide_edgehtml_12](./edgehtml-12.md) 。  

## 新機能  

### コンテンツ セキュリティ ポリシー 1.0  

Microsoft Edge では、コンテンツ セキュリティ ポリシー \(CSP\) 1.0 が実装されています。  CSP セキュリティ標準を使用すると、Web 開発者は、クロスサイト スクリプト \(XSS\)、クリックジャック、および信頼された Web ページのコンテキストで悪意のあるコンテンツを実行する他のコードインジェクション攻撃を防止するために、特定のページがフェッチまたは実行できるリソース \(スクリプト、CSS、プラグイン、画像など) を制御できます。  Microsoft Edge [の CSP について詳](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/Content_Security_Policy) しくは、コンテンツ セキュリティ ポリシーをご覧ください。  

### フィルター効果  

Microsoft Edge は、要素に視覚効果を追加する簡単な方法を提供します。  プロパティを使って、ぼかしの追加、明るさの調整、ドロップ シャドウの追加、不透明度の変更など、要素への変更を `filter` 行えます。  純粋な CSS を使用すると、1 つの要素に複数のフィルター効果を適用し、フィルターをアニメーション化できます。  詳細については、「フィルター効果 [」を参照してください](https://developer.mozilla.org/docs/Web/CSS/filter)。  

### JavaScript  

JavaScript のサポートは、最終バージョンの Internet Explorer \(IE11\) と Microsoft Edge によって若干異なります。  Edge の新機能は次のとおりです。  

:::row:::
   :::column span="1":::
      **明細**  
   :::column-end:::
   :::column span="2":::
      [クラス](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/class) \(experimental\), [for...of](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/for...of)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **オブジェクト**  
   :::column-end:::
   :::column span="2":::
      [](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Promise) [Promise、Proxy、Symbol](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Proxy) [](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Symbol) [、WeakSet](/scripting/javascript/reference/weakset-object-javascript)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **関数**  
   :::column-end:::
   :::column span="2":::
      [acosh](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/acosh), [codePointAt](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/codepointat), [fromCodePoint](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/fromcodepoint), [hypot](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/hypot), [imul](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/imul), [isInteger](/scripting/javascript/reference/number-isinteger-function-number-javascript), [isNaN](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number/isnan), [raw](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/raw)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **メソッド**  
   :::column-end:::
   :::column span="2":::
      [includes](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/includes)、 [keys](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/keys) \(Array\), [repeat](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/repeat) \(String\), [values](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/values) \(Array\)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **その他の機能**  
   :::column-end:::
   :::column span="2":::
      [Functions](https://developer.mozilla.org/docs/Learn/JavaScript/Building_blocks/Functions) \(experimental\), [Generators](https://developer.mozilla.org/docs/Web/JavaScript/Guide/Iterators_and_generators),  [Iterators](https://developer.mozilla.org/docs/Web/JavaScript/Guide/Iterators_and_generators), [Regular Expression `y` flag](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/RegExp) \(experimental\), [Template strings](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Template_literals), Unicode code point [escape characters](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Lexical_grammar#String_literals)  
   :::column-end:::
:::row-end:::  

Internet Explorer、Microsoft Edge、Microsoft Store アプリ間での JavaScript サポートの比較については、「JavaScript のバージョン情報」 [を参照してください](./javascript-version-information.md)。  

### メディア キャプチャとストリーム  

Microsoft Edge では [、W3C](https://w3c.github.io/mediacapture-main/getusermedia.html) Media Capture and Streams 仕様に基づくメディア キャプチャおよびストリーム API のサポートが導入されています。  これらの JavaScript API を使用すると、Web ページは、ユーザーの許可を得て、Web カメラやマイクなど、メディア キャプチャ デバイスにアクセスできます。  メディア キャプチャとストリーム API を使用すると、Web カメラを使用して写真をキャプチャしたり、マイクから音声メッセージをキャプチャするシナリオを作成できます。  Microsoft Edge でのメディア キャプチャの詳細については、Microsoft Edge [開発者ブログを参照してください](https://blogs.windows.com/msedgedev/2015/05/13)。  

### 新しい HTML 要素と属性  

*   `meter` 要素  
*   `picture` 要素  
*   `template` 要素  
*   `image` element: `srcset` and `sizes` attributes \(Microsoft Edge 開発者 [ブログ投稿](https://blogs.windows.com/msedgedev/2015/06/08)\)  
*   `selectionDirection` attribute  
*   `input type=time` および `input type=datetime-local`  

### オブジェクト RTC API  

Object Real-Time Communications \(ORTC\) を使用すると、ネイティブ JavaScript API を介して、Web ブラウザー、モバイル デバイス、サーバー間でリアルタイムでメディア \(オーディオやビデオ\) を直接ストリーミングできます。  Microsoft Edge の ORTC の詳細については、開発者ガイドの [トピック「Object RTC API」](https://ortc.org) を参照してください。  

### 閲覧ビュー  

Microsoft Edge は、ページ上の無関係なコンテンツや他のセカンダリ コンテンツを気を散らさずに、Web ページの読み書きのような読み上がりを効率化する閲覧ビューを提供します。  閲覧ビューは、アドレス バーの閲覧ビュー \(ブック アイコン\) ボタンからオンまたはオフに切り替え、または次の操作を行えます `Ctrl` + `Shift` + `R` 。  詳細 [については、閲覧ビュー](../browser-features/reading-view.md) にアクセスしてください。  

### 検索プロバイダーの検出  

リッチ検索の統合は、Microsoft Edge アドレス バーに組み込み、検索候補、Web からの結果、閲覧履歴、お気に入りを含む。  Microsoft Edge は、OpenSearch [1.1 仕様](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) に従って、Web 検索プロバイダーを検出して使用します。  検索プロバイダーの場合は、Microsoft Edge が [サービスをサポート](../browser-features/search-provider-discovery.md) する方法の詳細をご覧ください。  

### WebKit API のサポート  

互換性を向上するために、Microsoft Edge はさまざまなプレフィックス付き `-webkit-` API をサポートしています。  サポートされている API の完全な一覧については `-webkit-` 、API カタログを [使用してください](https://developer.microsoft.com/microsoft-edge/platform/catalog/?page=1&q=webkit)。  

### Web オーディオ  

Microsoft Edge では [、W3C Web オーディオ API 仕様のサポートが導入](https://webaudio.github.io/web-audio-api) されています。  Web オーディオは、豊富なオーディオと音楽のエクスペリエンスを提供するために、Web アプリケーションでオーディオを処理および合成する高レベルの JavaScript API です。  HTML5 要素では基本的なストリーミング オーディオ再生が可能ですが、Web オーディオ API には、狭い同期で複数のサウンドを再生し、混合オーディオにゲイン、フェード、切り替え、基本効果を適用できるさまざまな API が備まれています。 `audio`  詳細については、「Web オーディオ」を参照してください。/multimedia/web-audio.md in the Dev guide and on the [Microsoft Edge Developer blog](https://blogs.windows.com/msedgedev/2015/05/19).  

### Web ドライバー  

[W3C WebDriver API](https://w3.org/TR/webdriver)はプラットフォームと言語に依存しないインターフェイスであり、プログラムやスクリプトで Web ブラウザーの動作を制御できるワイヤー プロトコルです。  WebDriver を使用すると、開発者はユーザーの操作をシミュレートする自動テストを作成できます。  これは JavaScript 単体テストとは異なります。WebDriver は、ブラウザーで実行されている JavaScript では実行できない機能や情報にアクセスできます。また、ユーザー イベントや OS レベルのイベントをより正確にシミュレートできます。  WebDriver では、1 つのテスト セッションで複数のウィンドウ、タブ、Web ページのテストを管理することもできます。  Microsoft Edge 用 WebDriver の使用を開始する方法の詳細については [、WebDriver を参照してください](../../webdriver/index.md)。  

## EdgeHTML 12 の新しい API  

EdgeHTML 12 の新しい API の完全な一覧を次に示します。  これらは次の形式で一覧表示されます `[interface name].[api name]` 。  

 > [!NOTE] 
 > これらの API の多くは IE11 で利用できます。  EdgeHTML 12 に関する以下のデータは、EdgeHTML の初期バージョンと以降のバージョンを比較するベースラインとして提供されています。  

<iframe height='580' scrolling='no' title='EdgeHTML 12 の新しい API' src='//codepen.io/MicrosoftEdgeDocumentation/embed/pPOwby/?height=580&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>CodePen の Microsoft Edge Docs ( @MicrosoftEdgeDocumentation ) による EdgeHTML 12 の Pen <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/pPOwby/'> </a> の新しい API <a href='https://codepen.io/MicrosoftEdgeDocumentation'> </a> <a href='https://codepen.io'> をご覧ください </a> 。</iframe>  
