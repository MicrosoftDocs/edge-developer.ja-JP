---
description: Microsoft Edge 拡張機能を作成する方法について説明します
title: 拡張機能の作成
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 15cb7a4c187210c885b5d75770bda1c590a8c5d1
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235009"
---
# Microsoft Edge 拡張機能の作成  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

このガイドでは、Microsoft Edge の拡張機能を作成する方法について説明します。  この拡張例を使用すると、マニフェスト ファイル [、ユーザー インターフェイス、][MicrosoftDocs] およびバックグラウンド スクリプトとコンテンツ スクリプトの作成を行docs.microsoft.comページの特定の CSS を操作できます。  

:::image type="complex" source="../media/color-changer_header.png" alt-text="Docs.microsoft.comが青に変更されました":::
   Docs.microsoft.comが青に変更されました
:::image-end:::

<!--![Docs.microsoft.com body changed to blue][ImageColorChangerHeader]  -->  

このチュートリアルでは、ブラウザー拡張機能の基本と動作について理解している必要があります。  拡張機能の構成要素の詳細については、「拡張機能の構造」 [を参照してください][MDNAnatomyExtension]。  

GitHub で完全な [サンプルのコードをダウンロードします][GithubMicrosoftEdgeExtensionsDemosColorChanger]。  

## マニフェスト ファイルの作成  

まず、拡張機能のディレクトリを作成し、名前を指定します `color-changer` 。  

フォルダー内 `color-changer` に、次の名前のファイルを作成します `manifest.json` 。  このファイルは、すべての拡張子に必要であり、拡張子名からアクセス許可に至るまで、拡張子に関する重要 `manifest.json` な情報を提供します。  

> [!NOTE] 
> このガイドでは、このガイドで使用する必要があるすべてのマニフェスト キーについて詳しい情報を示しますが、サポートされているマニフェスト キーと推奨されるマニフェスト キーの一覧については、「サポートされているマニフェスト キー」を [参照してください][ExtensionsApisupportManifestKeys]。  

内部 `manifest.json` に、次のコードを追加します。  

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

### マニフェスト キーの定義  

| キー | 詳細 |  
|:--- |:--- |  
| [name][MDNManifestjsonName] | 拡張機能の名前。  |  
| [author][MDNManifestjsonAuthor] | 拡張機能の作成者。  |  
| [version][MDNManifestjsonVersion] | 内線番号のバージョン番号。  |  
| [description][MDNManifestjsonDescription] | Microsoft Edge の拡張機能メニューの [About] セクションに表示される拡張機能の説明。  |  
| [permissions][MDNManifestjsonPermissions] | 拡張情報のアクセス許可を要求する文字列の配列。  拡張機能の場合は、アクセスした Web サイトを表示するためのアクセス許可 ("tabs"\) を要求し、" に一致する URL のコンテンツを更新します `*://docs.microsoft.com/*` 。  |  
| [browser_action][MDNManifestjsonBrowserAction] | アイコンの情報が含まれる。 アイコンは、アドレス バーの右側にある Microsoft Edge ツール バーに配置されます。  |  

#### browser_actionの定義  

| キー | 詳細 |  
|:--- |:--- |  
| `default_icon` | ツール バーで使用されるアイコン。  |  
| `default_title` | ユーザーがツール バーのアイコンの上にマウス ポインターを置くと表示されるテキスト。  |  
| `default_popup` | ポップアップ ウィンドウの HTML ファイルへのパス。  |  

マニフェスト ファイルを作成したら、拡張機能のユーザー インターフェイスが必要です。  

## ポップアップの作成  

拡張機能の場合は、次のようなユーザー インターフェイスのポップアップを作成します。  

:::image type="complex" source="../media/color-changer_popup.png" alt-text="拡張機能のポップアップ インターフェイス":::
   拡張機能のポップアップ インターフェイス
:::image-end:::

<!--![The pop-up interface of the extension][ImageColorChangerPopup]  -->  

フォルダーのルートに `popup.html` 名前を付け、ファイルを作成 `color-changer` します。  次のコードを貼り付けます `popup.html` 。  

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

In, `popup.html` you create a title, a paragraph, and three buttons \(Aliceblue, Alicesilk, and Reset\).  

次に、フォルダーを作成し `css` 、その中に名前を付けるという名前のファイルを作成します `styles.css` 。  以下のスタイルを追加します。  

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

この CSS は、拡張機能にいくつかの基本的なスタイルを提供します。  拡張機能をカスタマイズするためのスタイルを自由に追加できます。  

次に、ポップアップを操作する JavaScript ファイルを作成する必要があります。  フォルダーと `js` 、その中に名前を付けられたファイルを `popup.js` 作成します。  次 `popup.js` のコードで更新します。  

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

タブ API では、ブラウザーのタブを操作し、スクリプトとスタイルをページ `popup.js` コンテンツに挿入できます。 [][MDNApiTabs]  [tabs.insertCSS()][MDNApiTabsInsertcss]メソッドを使用して、指定した CSS をページに挿入し、指定したボタンがクリックされた場合に[docs.microsoft.com][MicrosoftDocs]のヘッダーを別の色に変更します。  

これで基本的なポップアップ機能が作成されたので、拡張機能にアイコンを追加します。  

## アイコンの追加  

アイコンは、ブラウザーのツール バー、拡張機能メニュー、その他の場所の拡張機能を表す場合に使用されます。  [GitHub で拡張機能のアイコンをダウンロードします][GithubMicrosoftEdgeExtensionsDemosColorChangerImages]。 Microsoft Edge の拡張機能アイコンの詳細については、「デザイン ガイド」を [参照してください][ExtensionsGuidesDesignIcons]。  

拡張機能のアイコンをダウンロードした後、アイコンをフォルダー内 `images` に保存します `color-changer` 。  

ツール バーに表示されるアイコンは、前のセクションで既にマニフェスト ファイルに追加した browser_action キーの内側を使用 `default_icon` して設定されます。 [][MDNManifestjsonBrowserAction]  

キー `icons` は、[拡張機能の設定] メニューで使用するアイコンを定義します。  以下では、さまざまな画面解像度を考慮して、サイズが異なる複数のアイコンを指定しています。  アイコンの名前。アイコンの `25` `48` 高さ (ピクセル単位) です。  

ファイルの [manifest.jsに][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] 、次のトップ レベル キーを含める `icons` 必要があります。  

```json
  "icons": {
    "25": "images/color-changer25.png",
    "48": "images/color-changer48.png"
  }
```  

### マニフェスト キーの定義  

| キー | 詳細 |  
|:--- |:--- |  
| [アイコン][MDNManifestjsonIcons] | 拡張機能のルート ディレクトリに対するイメージ サイズとイメージ パスのキーと値のペアを持つ拡張機能 `px` のアイコン。 |  

> [!NOTE]
> このガイドで後 `inactive##.png` で説明する images フォルダーにある名前のアイコンを使用します。  

## 拡張機能のテスト  

ユーザー インターフェイスを追加し、アイコンを作成したら、拡張機能をテストします。  Microsoft Edge に拡張機能を [追加する手順][ExtensionsGuidesAddingRemovingExtensionsAdding] について説明します。  その後、このガイドに戻ってください。  

拡張機能を追加した後、任意のページに [docs.microsoft.com][MicrosoftDocs] します。  ブラウザーの操作をクリックすると、次のポップアップが表示されます。  本文の色も [docs.microsoft.com][MicrosoftDocs] 変更する必要があります。  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/color-changer_header_aliceblue.png" alt-text="Docs.microsoft.comヘッダーが Aliceblue に変更されました":::
         Docs.microsoft.comヘッダーが Aliceblue に変更されました :::image-end:::
      
      <!--![Docs.microsoft.com header changed to Aliceblue][ImageColorChangerHeaderAliceblue]  -->
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="../media/color-changer_header_cornsilk.png" alt-text="Docs.microsoft.comヘッダーが次の値に変更されました":::
         Docs.microsoft.comヘッダーが次の値に変更されました :::image-end:::
      
      <!--![Docs.microsoft.com header changed to Cornsilk][ImageColorChangerHeaderCornsilk]  -->
   :::column-end:::
:::row-end:::

動作しないエラーや機能が発生した場合は、デバッグ拡張機能のガイド[][ExtensionsGuidesDebuggingExtensions]を参照するか、GitHub で完全なサンプル[をダウンロードしてください][GithubMicrosoftEdgeExtensionsDemosColorChanger]。  

## コンテンツとバックグラウンド スクリプトの追加  

もう 1 つの手順に進み、拡張機能がドメイン外のページで機能することを無効にするロジック [docs.microsoft.com][MicrosoftDocs] します。  

最初にコンテンツ スクリプトを作成 [する必要があります][MDNContentScripts]。  次に、特定の Web ページのコンテキストで実行し、Web ページのコンテンツにアクセスし、バックグラウンド スクリプトと通信できるコンテンツ スクリプトを作成する必要があります。  ディレクトリ内に `js` 、名前を付け、次の `content.js` コードを追加するファイルを作成します。  

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

このスクリプトは、現在のページの URL を取得し、現在のページが現在のドメイン上 `document.location.href` [docs.microsoft.com][MicrosoftDocs] します。  [ページ][MicrosoftDocs]が docs.microsoft.com ドメイン \(\など) 上にない場合、非アクティブなアイコン \(灰色表示されたアイコン\) へのパスは [https://www.bing.com/][|::ref1::|] [runtime.sendMessage()][MDNApiRuntimeSendmessage]を使用してバックグラウンド スクリプトに送信されます。  

次のキーを含 [manifest.jsファイル][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] のファイル名を更新する必要 `content_scripts` があります。  

```json
  "content_scripts": [{
    "matches": [
        "<all_urls>"
    ],
    "js": ["js/content.js"],
    "run_at": "document_end"
}]
```  

### マニフェスト キーの定義  

| キー | 詳細 |  
|:--- |:---- |  
| [content_scripts][MDNManifestjsonContentScripts] | ブラウザーが読み込むコンテンツ スクリプトに関する情報が含まれます。 |  

#### content_scriptsの定義  

| キー | 詳細 |  
|:--- |:---- |  
| `matches` \(required\) | コンテンツ スクリプトを読み込む前に一致する URL パターン。 |  
| `js` | 一致する URL に読み込む必要があるスクリプト。 |  
| `run_at` | キーの JavaScript ファイルが挿入 `js` される場所を指定します。 |  

次に、バックグラウンド スクリプトを [作成する必要があります][MDNAnatomyExtensionBackgroundScripts]。  バックグラウンド スクリプトはブラウザーのバックグラウンドで実行され、Web ページまたはブラウザー ウィンドウの有効期間とは別に実行され、コンテンツ スクリプトと通信できます。  

フォルダー内に `js` 、名前を付け、次の `background.js` コードを追加するファイルを作成します。  

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

[runtime.onMessage メソッドは][MDNApiRuntimeOnmessage]、コンテンツ スクリプト[から runtime.sendMessage()][MDNApiRuntimeSendmessage]をリッスンします。  ページのドメインが指定されていない場合docs.microsoft.com [][MicrosoftDocs] [browserAction.setIcon()][MDNApiBrowseractionSeticon]メソッドは、アイコン パスを非アクティブなイメージに設定します。  

また、このスクリプトはブラウザー アクション \([browserAction.disable][MDApiBrowseractionDisable]\) を無効にし、ユーザーがブラウザーの操作をページの外部でクリック[docs.microsoft.comします。][MicrosoftDocs]  

ファイルに対してバックグラウンド スクリプトをmanifest.js[ する必要][GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson] があります。  マニフェストに次 `background` のキーを追加します。  

```json
"background": {
    "scripts": ["js/background.js"],
    "persistent": true
  }
```  

### マニフェスト キーの定義  

| キー | 詳細|  
|:--- |:--- |  
| [背景][MDNManifestjsonBackground] | バックグラウンド スクリプトが含まれます。 |  

#### バックグラウンド キーの定義  

| キー | 詳細 |  
|:--- |:--- |  
| `scripts` | JavaScript ファイルへのパス。 |  
| `persistent` (必須) | これは、次の値に設定する `true` 必要があります `false` 。  設定すると、 `true` バックグラウンド スクリプトが読み込まれ、閲覧セクション全体で保持されます。  設定されている場合、バックグラウンド スクリプトは遅延と一緒に読み込まれ、閲覧 `false` セッションで保持されます。 |  

拡張機能を再読み込みし、もう一度テストします。  To reload your extension: click the **...** for settings and more in Microsoft Edge, click **Extensions,** click on your extension \(**Color Changer**\), and click **Reload extension**.  

次に、新しいタブを開くか、新しいページではない既存のタブ [docs.microsoft.com][MicrosoftDocs] します。  You should see the inactive icon and not be able to click on the browser action.  

お疲れさまでした。  Microsoft Edge の拡張機能を作成しました。  [GitHub で完全なサンプルを表示します][GithubMicrosoftEdgeExtensionsDemosColorChanger]。  拡張機能の詳細については、続きを参照してください。  

## より複雑な拡張機能の作成  

より複雑な拡張機能を作成する場合  MdN の 2 番目の拡張機能である MdN の 2 番目の拡張機能 [をご覧ください][MDNYourSecondWebextension]。  Microsoft Edge の拡張機能モデルは Firefox の拡張機能モデルとは少し異なります。2[][MDNYourSecondWebextension]番目の拡張機能で作成された 1 つ目の拡張機能は、Microsoft Edge で機能するように適合されました。  GitHub で [確認してください][GithubMicrosoftEdgeExtensionsDemosBeastify]。  

MDN (2 番目の [拡張機能)][MDNYourSecondWebextension]に関する記事を見ながら、次のセクションに注意してください。  

### API  

Microsoft Edge [でサポートされている][ExtensionsAPIsupportApis] 拡張機能 API の一覧については、「サポートされる API」ページを参照してください。  

### アイコンのサイズ  

Microsoft Edge の推奨される拡張アイコンのサイズは `20px` 、次 `25px` `30px` のとおりです `40px` 。  その他のサポートされるサイズは `19px` `35px` 、,, and `38px` です。  アイコンのサイズとベスト プラクティスについて詳しくは、デザイン ガイドをご [覧][ExtensionsGuidesDesign] ください。  

### JavaScript  

Microsoft Edge の拡張機能モデルでは、JavaScript Promise はサポートされていません。  代わりに、コールバックを使用します。  拡張機能でコールバックを使用するその他の例については、クイック印刷デモとテキスト[][GithubMicrosoftEdgeExtensionsDemosQuickPrint]スワップ デモ[をご覧ください][GithubMicrosoftEdgeExtensionsDemosTextSwap]。  

次のビデオ [のクイック印刷][GithubMicrosoftEdgeExtensionsDemosQuickPrint] の例を説明します。  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Adding-a-Background-Script-to-you-Edge-Extension/player]  

### Manifest.jsオン  

*   キー `author` は Microsoft Edge で必要です  
*   キー `activeTab` は Microsoft Edge ではサポートされていません  

ブラウザー拡張機能について詳 [しくは、MDN][MDNBrowserExtensions]の [Web ドキュメントをご覧ください][MDNWebDocs]。  

<!-- image links -->  

<!--[ImageColorChangerHeader]: ../media/color-changer_header.png "Docs.microsoft.com body changed to blue"  -->  
<!--[ImageColorChangerPopup]: ../media/color-changer_popup.png "The pop-up interface of the extension"  -->  
<!--[ImageColorChangerHeaderAliceblue]: ../media/color-changer_header_aliceblue.png "[Docs.microsoft.com header changed to Aliceblue"  -->  
<!--[ImageColorChangerHeaderCornsilk]: ../media/color-changer_header_cornsilk.png "Docs.microsoft.com header changed to Cornsilk"  -->  

<!-- links -->  

[ExtensionsGuidesAddingRemovingExtensionsAdding]: ./adding-and-removing-extensions.md#adding-an-extension "拡張機能の追加 - Microsoft Edge の拡張機能の追加、移動、削除 |Microsoft Docs"  
[ExtensionsGuidesDebuggingExtensions]: ./debugging-extensions.md "拡張機能のデバッグ |Microsoft Docs"  
[ExtensionsGuidesDesign]: ./design.md "Microsoft Edge 拡張機能の設計ガイドライン |Microsoft Docs"  
[ExtensionsGuidesDesignIcons]: ./design.md#icons "アイコン - Microsoft Edge 拡張機能の設計ガイドライン |Microsoft Docs"  
[ExtensionsAPIsupportApis]: ../api-support/supported-apis.md " サポートされている API |Microsoft Docs"  
[ExtensionsApisupportManifestKeys]: ../api-support/supported-manifest-keys.md "サポートされているマニフェスト キー |Microsoft Docs"  

[MicrosoftDocs]: https://docs.microsoft.com "Microsoft Docs"  

[MDNWebDocs]: https://developer.mozilla.org "MDN Web ドキュメント"  
[MDNBrowserExtensions]: https://developer.mozilla.org/Add-ons/WebExtensions "ブラウザーの拡張機能 | MDN"  
[MDNAnatomyExtension]: https://developer.mozilla.org/Add-ons/WebExtensions/Anatomy_of_a_WebExtension "拡張機能の構造 |MDN"  
[MDNAnatomyExtensionBackgroundScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/Anatomy_of_a_WebExtension#Background_scripts "バックグラウンド スクリプト - 拡張機能の構造 |MDN"  
[MDApiBrowseractionDisable]: https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/disable "browserAction.disable() - API |MDN" 
[MDNApiBrowseractionSeticon]: https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/setIcon "browserAction.setIcon() - API |MDN"  
[MDNApiRuntimeOnmessage]: https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/onmessage "runtime.onMessage - API |MDN"  
[MDNApiRuntimeSendmessage]: https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendMessage "runtime.sendMessage() - API |MDN"  
[MDNApiTabs]: https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs "タブ - API |MDN"  
[MDNApiTabsInsertcss]: https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs/insertCSS "tabs.insertCSS() - API |MDN"  
[MDNContentScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/Content_scripts "コンテンツ スクリプト |MDN"  
[MDNManifestjsonAuthor]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/author "author - manifest.json |MDN"  
[MDNManifestjsonBackground]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/background "background - manifest.json |MDN"  
[MDNManifestjsonBrowserAction]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/browser_action "browser_action - manifest.json |MDN"  
[MDNManifestjsonContentScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/content_scripts "content_scripts - manifest.json |MDN"  
[MDNManifestjsonDescription]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/description "description - manifest.json |MDN"  
[MDNManifestjsonIcons]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/icons "アイコン - manifest.jsオン |MDN"  
[MDNManifestjsonName]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/name "name - manifest.json |MDN"  
[MDNManifestjsonPermissions]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/permissions "permissions - manifest.json |MDN"  
[MDNManifestjsonVersion]: https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/version "version - manifest.json |MDN"  
[MDNYourSecondWebextension]: https://developer.mozilla.org/Add-ons/WebExtensions/Your_second_WebExtension "2 番目の拡張機能 |MDN"  

[Bing]: https://www.bing.com "Bing"  

[GithubMicrosoftEdgeExtensionsDemosBeastify]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/beastify_edge "Ify - MicrosoftEdge/MicrosoftEdge-Extensions-Demos |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosColorChanger]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/color_changer "カラー Changer - MicrosoftEdge/MicrosoftEdge-Extensions-Demos |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosColorChangerImages]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/color_changer/images "画像 - カラー Changer - MicrosoftEdge/MicrosoftEdge-Extensions-Demos |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosColorChangerManifestjson]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/color_changer/manifest.json "Manifest.jsオン - カラー Changer - MicrosoftEdge/MicrosoftEdge-Extensions-Demos |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosQuickPrint]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/quick_print "クイック印刷 - MicrosoftEdge/MicrosoftEdge-Extensions-Demos |GitHub"  
[GithubMicrosoftEdgeExtensionsDemosTextSwap]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/text_swap "テキスト スワップ - MicrosoftEdge/MicrosoftEdge-Extensions-Demos |GitHub"  
