---
description: このページでは、EdgeHTML 12 の新機能の概要を示します。
title: EdgeHTML 12 の新機能と API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/27/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、Web 開発、html、cs、javascript、開発者
ms.openlocfilehash: 51c5c89b8ae4ea0e02de68f6b413c162336661f6
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941954"
---
# Microsoft EdgeHTML 12 の新機能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Microsoft Edge には、Microsoft Edge には、最新で最高の Windows Web プラットフォームを入手できるように、コアで設計された新しい "living" エンジンである EdgeHTML が用語です。  Microsoft Edge では、ActiveX コントロール、ブラウザー ヘルプァー オブジェクト \(BHOs\) をサポートするのに必要なレガシ コードから、クリーンな切り取りを発表します。  また、Microsoft Edge ではネイティブ PDF サポートも提供しています。  IE11 の場合、従事のドキュメント モードは廃まれており、Microsoft Edge を使用してサポートするブラウザー インフラストラクチャは存在しません。  [詳細については、IEBlog](/archive/blogs/ie/living-on-the-edge-our-next-step-in-interoperability)を参照してください。  

Windows 10 \(07/2015、ビルド [10240\)](https://blogs.windows.com/windowsexperience/2015/07/28/windows-10-free-upgrade-available-in-190-countries) の最初のリリースで、EdgeHTML 12 に出荷された変更は次のとおりです。  Microsoft Edge ブラウザー全体の変更の概要については、過ぎ [た過](https://blogs.windows.com/msedgedev/2015/02/26) ぎた Microsoft の新しい Web レンダリング エンジンの誕生日 [と過ぎた A の改行 (パート 2: ActiveX、VBScript、attachEvent など](https://blogs.windows.com/msedgedev/2015/05/06)) を参照してください。  

次の一覧を行うと、この機能が利用できます  [https://aka.ms/devguide_edgehtml_12](./edgehtml-12.md) 。  

## 新機能  

### コンテンツ セキュリティ ポリシー 1.0  

Microsoft Edge でコンテンツ セキュリティ ポリシー \(CSP\) 1.0 が実装されました。  CSP セキュリティ標準により、Web デベロッパーはリソース \(スクリプト、CSS、 特定のページをフラグイン、画像など、特定のページにフェッチまたは実行できるプラグインや画像などを、クロスサイト スクリプト機能の防止、クリック、およびその他のコードに取り込むことは、信頼された Web ページのコンテキストで不適切なコンテンツを実行することを目指しています。  Microsoft Edge [の CSP について](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/Content_Security_Policy) 詳しくは、コンテンツ セキュリティ ポリシーを参照してください。  

### フィルター効果  

Microsoft Edge を使用すると、要素に視覚効果を簡単に追加できます。  プロパティを使用すると、ブルークを追加したり、明るさを調整したり、ドロップ シャドウを追加したり、読みやすさを `filter` 変更したりできます。  また、このような場合は、1 つの要素に複数のフィルター効果を適用して、フィルターにアニメーションを設定できます。  詳細については、フィルター効果 [を参照してください](https://developer.mozilla.org/docs/Web/CSS/filter)。  

### JavaScript  

JavaScript サポートは、最後のバージョンの Internet Explorer \(IE11\) と Microsoft Edge の間で少し異なります。  Edge の新機能は次のとおりです。  

:::row:::
   :::column span="1":::
      **明細**  
   :::column-end:::
   :::column span="2":::
      [class](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/class) \(experimental\) [が](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/for...of)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **オブジェクト**  
   :::column-end:::
   :::column span="2":::
      [Promise](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Promise)Promise、Proxy、Symbol、WeakSet [Proxy](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Proxy) [Symbol](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Symbol) [WeakSet](/scripting/javascript/reference/weakset-object-javascript)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **関数**  
   :::column-end:::
   :::column span="2":::
      [acosh,](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/acosh) [codePointAt,](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/codepointat) [fromCodePoint,](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/fromcodepoint) [hypot](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/hypot), [imul,](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/imul) [isInteger, isInteger,](/scripting/javascript/reference/number-isinteger-function-number-javascript) [isNaN,](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number/isnan) [raw](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/raw)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **メソッド**  
   :::column-end:::
   :::column span="2":::
      [includes,](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/includes) [keys](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/keys) \(Array\), [repeat](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/repeat) \(String\), [values](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/values) \(Array\)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **その他の機能**  
   :::column-end:::
   :::column span="2":::
      [関数](https://developer.mozilla.org/docs/Learn/JavaScript/Building_blocks/Functions)\(実数\)、[ジェテナ](https://developer.mozilla.org/docs/Web/JavaScript/Guide/Iterators_and_generators)ーター,[イ](https://developer.mozilla.org/docs/Web/JavaScript/Guide/Iterators_and_generators)ターセレクター,[正数表現 `y` フラグ](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/RegExp)\(実数\)、[テンプレート文字列](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Template_literals)[,Unicode コード ポイント エスケープ文字](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Lexical_grammar#String_literals)  
   :::column-end:::
:::row-end:::  

Internet Explorer、Microsoft Edge、Microsoft Store アプリでの JavaScript サポートの比較については [、JavaScript バージョン情報を参照してください](./javascript-version-information.md)。  

### メディア キャプチャとストリーム  

Microsoft Edge では [、W3C メ](https://w3c.github.io/mediacapture-main/getusermedia.html) ディア キャプチャと Streams の指定に基づいてメディア キャプチャと Streams API のサポートが追加されました。  これらの JavaScript API を使用すると、Web ページに Web カメラやマイクなどのメディア キャプチャ デバイスにユーザーからのアクセス許可が与えられます。  メディア キャプチャとストリーミング API を使用すると、Web カメラを使用して写真をキャプチャしたり、マイクから音声メッセージをキャプチャしたりするシナリオを作成できます。  Microsoft Edge デベロッパー ブログの Microsoft Edge でメディア キャプチャ [の詳細を参照してください](https://blogs.windows.com/msedgedev/2015/05/13)。  

### 新しい HTML 要素と属性  

*   `meter` 要素  
*   `picture` 要素  
*   `template` 要素  
*   `image` 要素: `srcset` 属 `sizes` 性 \(Microsoft Edge Developer [ブログ投稿](https://blogs.windows.com/msedgedev/2015/06/08)\)  
*   `selectionDirection` attribute  
*   `input type=time` および `input type=datetime-local`  

### オブジェクト RTC API  

Object Real-Time Communications \(ORTC\) を使用すると、Web ブラウザー、モバイル デバイス、およびネイティブ JavaScript API を使用するサーバー間でリアルタイムでメディア \(オーディオと/ビデオ\) をストリーミング化することができます。  Microsoft Edge の [ORTC API](https://ortc.org) の詳細については、デベロッパー ガイドトピックを参照してください。  

### 閲覧表示  

Microsoft Edge では、ページ上の関連しないコンテンツや他の第 2 のコンテンツに気がついていることなく、より効率的で、より効率的に Web ページの閲覧表示機能が用意されています。  閲覧表示は、アドレス バーの閲覧表示の \(書籍アイコン\) ボタンまたは使用してオンまたはオフに切り替えることができます `Ctrl` + `Shift` + `R` 。  詳細については、 [閲覧表示](../browser-features/reading-view.md) にアクセスしてください。  

### 検索プロバイダーの検出  

高度な検索統合は、検索候補、Web からの結果、閲覧履歴、お気に入りなど、Microsoft Edge アドレス バーに組み込まれています。  Microsoft Edge は [、web OpenSearch 1.1 の指定](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) に従って Web 検索プロバイダーを見つけ、使用します。  検索プロバイダーの場合、Microsoft Edge[read more](../browser-features/search-provider-discovery.md)がサービスをサポートしているかどうかを確認する方法をご覧ください。  

### WebKit API のサポート  

互換性を強化するため、Microsoft Edge は、さまざまなプレフィックスされた `-webkit-` API をサポートしています。  サポートされている API の完全な `-webkit-` リストについては [、API カタログを使用します](https://developer.microsoft.com/microsoft-edge/platform/catalog/?page=1&q=webkit)。  

### Web オーディオ  

Microsoft Edge では [、W3C Web Audio API の指定のサポートが追加](https://webaudio.github.io/web-audio-api) されました。  Web Audio は、Web アプリケーションのオーディオを処理して合理化して、高度な音声と音楽の操作環境を提供するための、Web アプリケーションでオーディオを処理および合理化するためのハイレベルの JavaScript API です。  HTML5 要素を使用すると、基本ストリーミング オーディオ `audio` 再生が可能ですが、Web Audio API は、Tighronization を使用して複数のサウンドを再生し、ミックスされたオーディオに対してゲイン、フェード、切り替え、基本的な効果を適用できる API を提供します。  [Web オーディオ](...Dev ガイドおよび [Microsoft Edge Developer](https://blogs.windows.com/msedgedev/2015/05/19)ブログの /multimedia/web-audio.md。  

### Web Driver  

[W3C WebDriver API は](https://w3.org/TR/webdriver)プラットフォームと言語ニュートラル インターフェイスで、プログラムまたはスクリプトによって Web ブラウザーの動作を制御できます。  WebDriver を使用すると、デベロッパーはユーザーの操作をシミュレートする自動テストを作成できます。  WebDriver には、ブラウザーで実行されている JavaScript が動作しない機能や情報にアクセスできるため、ユーザー イベントや OS レベルのイベントを正確にシミュレートできるためです。  WebDriver は、1 回のテスト 操作で複数のウィンドウ、タブ、Web ページ間でテストを管理することもできます。  WebDriver for Microsoft Edge の使用を開始する方法の詳細については [、WebDriver をご覧ください](../../webdriver.md)。  

## EdgeHTML 12 の新しい API  

EdgeHTML 12 の新しい API の完全な一覧を次に示します。  これらは形式で表示されます `[interface name].[api name]` 。  

 > [!NOTE] 
 > これらの API の多くは IE11 で利用できるようになりました。  Microsoft EdgeHTML 12 の以下のデータは、初バージョンの EdgeHTML を新しいバージョンに比較する基準として用いられます。  

<iframe height='580' scrolling='no' title='EdgeHTML 12 の新しい API' src='//codepen.io/MicrosoftEdgeDocumentation/embed/pPOwby/?height=580&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/pPOwby/'>CodePen で Microsoft Edge </a> DOcs (新しい API) <a href='https://codepen.io/MicrosoftEdgeDocumentation'> @MicrosoftEdgeDocumentation </a> を <a href='https://codepen.io'> 参照してください </a> 。</iframe>  
