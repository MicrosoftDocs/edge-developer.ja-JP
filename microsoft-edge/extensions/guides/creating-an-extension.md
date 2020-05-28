---
description: Microsoft Edge 拡張機能を作成する方法について説明します。
title: 内線番号を作成する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.custom: seodec18
ms.openlocfilehash: a08fc6bd604ce810895e7103f7f6384dbedc9f78
ms.sourcegitcommit: 0bc1312a1e6a0ac37cf385201db4361fc05184fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2020
ms.locfileid: "10683652"
---
# Microsoft Edge 拡張機能の作成  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

このガイドでは、Microsoft Edge 用の拡張機能を作成する方法について説明します。  この例の拡張機能を使用すると、マニフェストファイル、ユーザーインターフェイス、バックグラウンドおよびコンテンツスクリプトの作成を[docs.microsoft.com][MicrosoftDocs]するなど、特定の CSS を操作することができます。  

:::image type="complex" source="../media/color-changer_header.png" alt-text="Docs.microsoft.com 本文が青に変更されました":::
   Docs.microsoft.com 本文が青に変更されました
:::image-end:::

<!--![Docs.microsoft.com body changed to blue][ImageColorChangerHeader]  -->  

このチュートリアルでは、ブラウザーの拡張機能の概要とそのしくみについて、基本的に理解していることを前提としています。  拡張機能の構築要素について詳しくは、「[拡張機能の構造][MDNAnatomyExtension]」をご覧ください。  

[GitHub の完全なサンプル][GithubMicrosoftEdgeExtensionsDemosColorChanger]コードをダウンロードしてください。  

## マニフェストファイルを作成する  

開始するには、拡張機能用のディレクトリを作成し、名前を付ける必要が `color-changer` あります。  

フォルダー内 `color-changer` で、という名前のファイルを作成し `manifest.json` ます。  `manifest.json`ファイルはすべての拡張機能に必要であり、拡張機能の名前からアクセス許可までの重要な情報を提供します。  

> [!NOTE] 
> このガイドでは、このガイドで使用する必要があるすべてのマニフェストキーについて説明しますが、サポートされているすべてのマニフェストキーと推奨マニフェストキーの一覧については、「[サポートされているマニフェストキー][ExtensionsApisupportManifestKeys]」をご覧ください。  

内部 `manifest.json` に次のコードを追加します。  

```json
{
  "name": "Color Changer",
  "author": "Microsoft Edge Extension Developer",
  "version": "1.0",
  "description": "Change the color of the body on docs.microsoft.com",
  "permissions": [
    "*://docs.microsoft.com/*",
    "tabs"
  ], 
  "browser_action": {
    "default_icon": {
      "20": "images/color-changer20.png",
      "40": "images/color-changer40.png"
    },
    "default_title": "Color Changer",
    "default_popup": "popup.html"
  }
}
```  

### マニフェストキーの定義  

| Key | 詳細 |  
|:--- |:--- |  
| [name][MDNManifestjsonName] | 拡張機能の名前。  |  
| [著作者][MDNManifestjsonAuthor] | 内線番号の作成者。  |  
| [version][MDNManifestjsonVersion] | 拡張機能のバージョン番号。  |  
| [description][MDNManifestjsonDescription] | Microsoft Edge の [拡張] メニューの [バージョン情報] セクションに表示される拡張機能の説明です。  |  
| [権限][MDNManifestjsonPermissions] | 拡張子のアクセス許可を要求する文字列の配列です。  お客様の内線番号については、アクセス許可を要求している web サイトが表示され `*://docs.microsoft.com/*` ます。  |  
| [browser_action][MDNManifestjsonBrowserAction] | アイコンの情報が含まれています。 アイコンは、Microsoft Edge ツールバーのアドレスバーの右側に配置されます。  |  

#### browser_action キーの定義  

| Key | 詳細 |  
|:--- |:--- |  
| `default_icon` | ツールバーで使用されるアイコン。  |  
| `default_title` | ユーザーがツールバーのアイコンの上にマウスポインターを置いたときに表示されるテキスト。  |  
| `default_popup` | ポップアップウィンドウの HTML ファイルのパス。  |  

マニフェストファイルを作成したので、拡張機能のユーザーインターフェイスが必要です。  

## ポップアップの作成  

拡張機能については、次のように、ユーザーインターフェイス用のポップアップを作成します。  

:::image type="complex" source="../media/color-changer_popup.png" alt-text="拡張機能のポップアップインターフェイス":::
   拡張機能のポップアップインターフェイス
:::image-end:::

<!--![The pop-up interface of the extension][ImageColorChangerPopup]  -->  

フォルダーのルートに、という名前のファイルを作成 `popup.html` `color-changer` します。  次のコードを貼り付け `popup.html` ます。  

```html
<!DOCTYPE html>
<html>
    <head>
        <link rel="stylesheet" type="text/css" href="css/styles.css" />
    </head>
    <body>
        <h1>Creating a Microsoft Edge Extension</h1>
        <p>Color Changer</p>
        <input id="aliceblue" type="button" value="Aliceblue" />
        <input id="cornsilk" type="button" value="Cornsilk" />
        <input id="reset" type="button" value="Reset" />
        <script src="js/popup.js"></script>
    </body>
</html>
```  

では、 `popup.html` タイトル、段落、3つのボタン \ (Aliceblue、Cornsilk、および Reset \) を作成します。  

次に、という名前のフォルダーを作成して、という名前 `css` のファイルを作成し `styles.css` ます。  以下のスタイルを追加します。  

```css
/* main styles */
* {
    font-family: 'Segoe UI';
}

h1 {
    font-weight: 600;
    font-size: .9em;
}

p {
    font-weight: 500;
    font-size: .8em;
    margin-bottom: 10px;  
}
```  

この CSS には、拡張機能がいくつかの基本的なスタイルで用意されています。  さらにスタイルを追加して、拡張機能をカスタマイズしてください。  

次に、ポップアップと連携する JavaScript ファイルを作成する必要があります。  フォルダーと、in と `js` いう名前のファイルを作成 `popup.js` します。  `popup.js`次のコードを使用して更新します。  

```JavaScript
// get the buttons by id
let aliceblue = document.getElementById('aliceblue');
let cornsilk = document.getElementById('cornsilk');
let reset = document.getElementById('reset');

// use tabs.insertCSS to change header color on button click

// aliceblue
aliceblue.onclick = () => {
  browser.tabs.insertCSS({code: "body { background: aliceblue !important; }"});
};

// cornsilk
cornsilk.onclick = () => {
  browser.tabs.insertCSS({code: "body { background: cornsilk !important; }"});
};

// back to original
reset.onclick = () => {
  browser.tabs.insertCSS({code: "body { background: none !important; }"});
};
```  

の `popup.js` [タブ][MDNApiTabs]API では、ブラウザーのタブを操作したり、スクリプトとスタイルをページコンテンツに挿入したりできます。  [Tabs css ()][MDNApiTabsInsertcss]メソッドを使用して、指定した css をページに挿入して、指定したボタンをクリックしたときに[docs.microsoft.com][MicrosoftDocs]のヘッダーを別の色に変更します。  

基本的なポップアップ機能を使用したので、拡張機能にアイコンを追加します。  

## アイコンの追加  

アイコンは、ブラウザーのツールバー、[拡張機能] メニュー、その他の場所で拡張機能を表すために使用されます。  GitHub の[拡張機能のアイコン][GithubMicrosoftEdgeExtensionsDemosColorChangerImages]をダウンロードします。 Microsoft Edge の拡張機能アイコンの詳細については、「[デザインガイド][ExtensionsGuidesDesignIcons]」を参照してください。  

拡張機能のアイコンをダウンロードしたら、その中のフォルダーにアイコンを保存し `images` `color-changer` ます。  

ツールバーに表示されるアイコンは、 `default_icon` 前のセクションで既にマニフェストファイルに追加した[browser_action][MDNManifestjsonBrowserAction]キーの内部で設定されています。  

この `icons` キーは、[拡張設定] メニューで使用するアイコンを定義します。  次に、異なるサイズの複数のアイコンを指定して、さまざまな画面解像度を考慮します。  アイコンの名前 `25` `48` 。アイコンの高さ (ピクセル単位) です。  

[Manifest.xml][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson]ファイルで、の最上位レベルのキーを含め `icons` ます。  

```json
  "icons": {
    "25": "images/color-changer25.png",
    "48": "images/color-changer48.png"
  }
```  

### マニフェストキーの定義  

| Key | 詳細 |  
|:--- |:--- |  
| [アイコン][MDNManifestjsonIcons] | 拡張子の `px` ルートディレクトリを基準とした、イメージのサイズとイメージのパスのキーと値のペアのアイコン。 |  

> [!NOTE]
> `inactive##.png`このガイドで後述する images フォルダーの下にあるアイコンを使用します。  

## 拡張機能のテスト  

これで、ユーザーインターフェイスと作成したアイコンが追加されました。拡張機能をテストします。  Microsoft Edge に[拡張機能を追加][ExtensionsGuidesAddingRemovingExtensionsAdding]するための手順について説明します。  その後、このガイドに戻ります。  

拡張機能を追加した後で、任意の[docs.microsoft.com][MicrosoftDocs]ページに移動します。  ブラウザーの操作をクリックすると、次のポップアップが表示されます。  [Docs.microsoft.com][MicrosoftDocs]本文の色も色を変更する必要があります。  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/color-changer_header_aliceblue.png" alt-text="Docs.microsoft.com ヘッダーが Aliceblue に変更されました":::
         Docs.microsoft.com ヘッダーが Aliceblue に変更されました :::image-end:::
      
      <!--![Docs.microsoft.com header changed to Aliceblue][ImageColorChangerHeaderAliceblue]  -->
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/color-changer_header_cornsilk.png" alt-text="Docs.microsoft.com ヘッダーが Cornsilk に変更されました":::
         Docs.microsoft.com ヘッダーが Cornsilk に変更されました :::image-end:::
      
      <!--![Docs.microsoft.com header changed to Cornsilk][ImageColorChangerHeaderCornsilk]  -->
   :::column-end:::
:::row-end:::

機能しないエラーや機能が発生した場合は、「[デバッグ拡張機能][ExtensionsGuidesDebuggingExtensions]ガイド」または「 [GitHub の完全なサンプル][GithubMicrosoftEdgeExtensionsDemosColorChanger]をダウンロードする」を参照してください。  

## コンテンツとバックグラウンドスクリプトの追加  

さらに一歩進んで、 [docs.microsoft.com][MicrosoftDocs]ドメイン以外のページで機能しないようにするためのロジックを追加します。  

まず、[コンテンツスクリプト][MDNContentScripts]を作成する必要があります。  次に、特定の web ページのコンテキストで実行されるコンテンツスクリプトを作成して、web ページのコンテンツにアクセスできるようにし、バックグラウンドスクリプトと通信できるようにする必要があります。  `js`ディレクトリ内で、という名前のファイルを作成 `content.js` し、次のコードを追加します。  

```javascript
// get the URL of the page
var url = document.location.href;

// if not on a docs.microsoft.com domain
if (url.indexOf("//docs.microsoft.com") === -1) {
    // send inactive icons
    browser.runtime.sendMessage({
        "iconPath20": "images/inactive20.png",
        "iconPath40": "images/inactive40.png"
    });
}
```  

このスクリプトは、現在のページの URL を取得 `document.location.href` し、現在のページが[docs.microsoft.com][MicrosoftDocs]ドメインにあるかどうかを確認します。  ページが[docs.microsoft.com][MicrosoftDocs]ドメインにない場合 ( [https://www.bing.com/][|::ref1::|] \ など)、非アクティブアイコン (灰色のアイコン) へのパスは、 [sendMessage ()][MDNApiRuntimeSendmessage]を使ってバックグラウンドスクリプトに送信されます。  

次のキーを含めるには、 [manifest.xml][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson]ファイルを更新する必要があります。 `content_scripts`  

```json
  "content_scripts": [{
    "matches": [
        "<all_urls>"
    ],
    "js": ["js/content.js"],
    "run_at": "document_end"
}]
```  

### マニフェストキーの定義  

| Key | 詳細 |  
|:--- |:---- |  
| [content_scripts][MDNManifestjsonContentScripts] | ブラウザーが読み込むコンテンツスクリプトに関する情報が含まれています。 |  

#### content_scripts キーの定義  

| Key | 詳細 |  
|:--- |:---- |  
| `matches` \ (必須 \) | コンテンツスクリプトを読み込む前に照合する URL パターン。 |  
| `js` | 一致する Url に読み込む必要があるスクリプト。 |  
| `run_at` | キーからの JavaScript ファイルを挿入する場所を指定し `js` ます。 |  

次に、[バックグラウンドスクリプト][MDNAnatomyExtensionBackgroundScripts]を作成する必要があります。  バックグラウンドスクリプトは、ブラウザーのバックグラウンドで実行され、web ページまたはブラウザーウィンドウの有効期間とは無関係に動作し、コンテンツスクリプトと通信できます。  

`js`フォルダー内で、という名前のファイルを作成 `background.js` し、次のコードを追加します。  

```javascript
// listen for sendMessage() from content script
browser.runtime.onMessage.addListener(
    function (request, sender, sendResponse) {
        // set the icon for the browser action from sendMessage() in content script
        browser.browserAction.setIcon({
            path: {
                "20": request.iconPath20,
                "40": request.iconPath40
            },
            tabId: sender.tab.id
        });
        // disable browser action for the current tab
        browser.browserAction.disable(sender.tab.id);
    });
```  

[OnMessage][MDNApiRuntimeOnmessage]メソッドは、コンテンツスクリプトから[実行時の sendMessage ()][MDNApiRuntimeSendmessage]をリッスンします。  ページのドメインが[docs.microsoft.com][MicrosoftDocs]ではない場合、 [setIcon ()][MDNApiBrowseractionSeticon]メソッドは、非アクティブな画像へのアイコンパスを設定します。  

このスクリプトでは、ブラウザーのアクション \ ([Browseraction][MDApiBrowseractionDisable]) を無効にして、ユーザーが[docs.microsoft.com][MicrosoftDocs]ページ以外でブラウザーの操作をクリックできないようにします。  

[マニフェスト][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson]ファイルにバックグラウンドスクリプトを追加する必要があります。  `background`マニフェストに次のキーを追加します。  

```json
"background": {
    "scripts": ["js/background.js"],
    "persistent": true
  }
```  

### マニフェストキーの定義  

| Key | 詳細|  
|:--- |:--- |  
| [背景][MDNManifestjsonBackground] | バックグラウンドスクリプトが含まれています。 |  

#### バックグラウンドキーの定義  

| Key | 詳細 |  
|:--- |:--- |  
| `scripts` | JavaScript ファイルのパス。 |  
| `persistent` (必須) | これは、またはに設定する必要があり `true` `false` ます。  をに設定する `true` と、バックグラウンドスクリプトが読み込まれ、閲覧セクション全体に対して保持されます。  がに設定 `false` されている場合は、バックグラウンドスクリプトに遅延が含まれており、閲覧セッションのために存続します。 |  

延長をリロードして、もう一度テストしてください。  拡張機能を再ロードするには: [設定] の [詳細] をクリックします。 Microsoft Edge の場合**は、[** **拡張機能**] をクリックし、拡張機能 \ (**カラーチェンジャー**\) をクリックし、[**拡張機能の再読み込み**] をクリックします。  

次に、新しいタブを開くか、 [docs.microsoft.com][MicrosoftDocs]ページではない既存のタブを更新します。  [非アクティブ] アイコンが表示され、ブラウザーのアクションをクリックできません。  

お疲れさまでした。  Microsoft Edge 用の拡張機能を作成しました。  [GitHub の完全なサンプル][GithubMicrosoftEdgeExtensionsDemosColorChanger]を表示します。  拡張機能の詳細については、こちらを参照してください。  

## より複雑な拡張機能の作成  

より複雑な拡張子を作成したい場合  [2 つ目の拡張機能][MDNYourSecondWebextension]である、記事の MDN の Beastify extension を見てみてください。  Microsoft Edge の拡張モデルは Firefox の拡張モデルとは少し異なります。[第2の拡張機能][MDNYourSecondWebextension]で作成された Beastify extension は、microsoft edge で機能するように調整されています。  [GitHub][GithubMicrosoftEdgeExtensionsDemosBeastify]で確認してください。  

MDN の記事をウォークしながら、 [2 つ目の拡張機能][MDNYourSecondWebextension]については、次のセクションを念頭に置いてください。  

### API  

Microsoft Edge でサポートされている拡張機能 Api の一覧については、「[サポートされている api][ExtensionsAPIsupportApis] 」ページを参照してください。  

### アイコンのサイズ  

Microsoft Edge の優先拡張機能アイコンのサイズは、、、、 `20px` `25px` `30px` `40px` です。  サポートされているその他のサイズは、、、 `19px` `35px` `38px` です。  アイコンのサイズとベストプラクティスの詳細については、[設計][ExtensionsGuidesDesign]ガイドを参照してください。  

### JavaScript  

Microsoft Edge の拡張モデルでは、JavaScript の約束はサポートされていません。  代わりに、コールバックを使います。  拡張機能でコールバックを使う方法の例については、「[クイック印刷][GithubMicrosoftEdgeExtensionsDemosQuickPrint]と[テキスト交換][GithubMicrosoftEdgeExtensionsDemosTextSwap]のデモ」をご覧ください。  

[クイック印刷][GithubMicrosoftEdgeExtensionsDemosQuickPrint]の例については、次のビデオを参照してください。  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Adding-a-Background-Script-to-you-Edge-Extension/player]  

### Manifest.xml  

*   `author`Microsoft Edge ではキーが必要です  
*   `activeTab`Microsoft Edge では、キーはサポートされていません  

[ブラウザーの拡張機能][MDNBrowserExtensions]の詳細については、「 [MDN web ドキュメント][MDNWebDocs]」を参照してください。  

<!-- image links -->  

<!--[ImageColorChangerHeader]: ../media/color-changer_header.png "Docs.microsoft.com body changed to blue"  -->  
<!--[ImageColorChangerPopup]: ../media/color-changer_popup.png "The pop-up interface of the extension"  -->  
<!--[ImageColorChangerHeaderAliceblue]: ../media/color-changer_header_aliceblue.png "[Docs.microsoft.com header changed to Aliceblue"  -->  
<!--[ImageColorChangerHeaderCornsilk]: ../media/color-changer_header_cornsilk.png "Docs.microsoft.com header changed to Cornsilk"  -->  

<!-- links -->  

[ExtensionsGuidesAddingRemovingExtensionsAdding]: ./adding-and-removing-extensions.md#adding-an-extension "拡張機能の追加-Microsoft Edge の拡張機能の追加、移動、削除 |Microsoft ドキュメント"  
[ExtensionsGuidesDebuggingExtensions]: ./debugging-extensions.md "拡張機能のデバッグ |Microsoft ドキュメント"  
[ExtensionsGuidesDesign]: ./design.md "Microsoft Edge Extensions の設計ガイドライン |Microsoft ドキュメント"  
[ExtensionsGuidesDesignIcons]: ./design.md#icons "アイコン-Microsoft Edge Extensions のデザインガイドライン |Microsoft ドキュメント"  
[ExtensionsAPIsupportApis]: ../api-support/supported-apis.md "サポートされている Api |Microsoft ドキュメント"  
[ExtensionsApisupportManifestKeys]: ../api-support/supported-manifest-keys.md "サポートされているマニフェストキー |Microsoft ドキュメント"  

[MicrosoftDocs]: https://docs.microsoft.com "Microsoft ドキュメント"  

[MDNWebDocs]: https://developer.mozilla.org "MDN Web ドキュメント"  
[MDNBrowserExtensions]: https://developer.mozilla.org/Add-ons/WebExtensions "ブラウザーの拡張機能 |MDN"  
[MDNAnatomyExtension]: https://developer.mozilla.org/Add-ons/WebExtensions/Anatomy_of_a_WebExtension "拡張機能の構造 |MDN"  
[MDNAnatomyExtensionBackgroundScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/Anatomy_of_a_WebExtension#Background_scripts "バックグラウンドスクリプト-拡張機能の構造 |MDN"  
[MDApiBrowseractionDisable]: https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/disable "browserAction. disable ()-API |MDN" 
[MDNApiBrowseractionSeticon]: https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/setIcon "browserAction ()-API |MDN"  
[MDNApiRuntimeOnmessage]: https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/onmessage "onMessage-API |MDN"  
[MDNApiRuntimeSendmessage]: https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendMessage "runtime ()-API |MDN"  
[MDNApiTabs]: https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs "タブ-API |MDN"  
[MDNApiTabsInsertcss]: https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs/insertCSS "tabs Css ()-API |MDN"  
[MDNContentScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/Content_scripts "コンテンツスクリプト |MDN"  
[MDNManifestjsonAuthor]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/author "作成-マニフェスト |MDN"  
[MDNManifestjsonBackground]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/background "バックグラウンド-マニフェスト |MDN"  
[MDNManifestjsonBrowserAction]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/browser_action "browser_action-manifest |MDN"  
[MDNManifestjsonContentScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/content_scripts "content_scripts-manifest |MDN"  
[MDNManifestjsonDescription]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/description "説明-manifest.xml |MDN"  
[MDNManifestjsonIcons]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/icons "アイコン-manifest |MDN"  
[MDNManifestjsonName]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/name "name-manifest |MDN"  
[MDNManifestjsonPermissions]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/permissions "権限-manifest |MDN"  
[MDNManifestjsonVersion]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/version "バージョン-manifest |MDN"  
[MDNYourSecondWebextension]: https://developer.mozilla.org/Add-ons/WebExtensions/Your_second_WebExtension "2つ目の内線番号 |MDN"  

[Bing]: https://www.bing.com "Bing"  

[GithubMicrosoftEdgeExtensionsDemosBeastify]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/beastify_edge "Beastify-MicrosoftEdge/MicrosoftEdge-デモ |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosColorChanger]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/color_changer "カラーチェンジャー-MicrosoftEdge/MicrosoftEdge-デモ機能-デモ |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosColorChangerImages]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/color_changer/images "画像-カラーチェンジャー-MicrosoftEdge/MicrosoftEdge-デモ |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/color_changer/manifest.json "Manifest.xml-カラーチェンジャー-MicrosoftEdge/MicrosoftEdge-デモ |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosQuickPrint]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/quick_print "クイック印刷-MicrosoftEdge/MicrosoftEdge-デモ機能GitHub"  
[GithubMicrosoftEdgeExtensionsDemosTextSwap]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/text_swap "テキストの MicrosoftEdge/MicrosoftEdge-デモ機能-デモ |GitHub"  
