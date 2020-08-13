---
title: ワークスペースを使用してファイルを編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/31/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 7cafa2b186d151a478fa532cdac49ae46f2120c3
ms.sourcegitcommit: 4bc904c5d54347185f275bd76441975be471c320
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2020
ms.locfileid: "10926554"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  

# ワークスペースを使用してファイルを編集する  

> [!NOTE]
> このチュートリアルの目標は、ワークスペースのセットアップと使用に関する実践的な練習を行い、独自のプロジェクトでワークスペースを使用できるようにすることです。  ワークスペースを有効にした後、DevTools で作成したソースコードの変更をローカルコンピューターに保存することができます。  

> [!CAUTION]
> **前提条件**: このチュートリアルを始める前に、次の方法を理解しておく必要があります。  
> *   [HTML、CSS、JavaScript を使って web ページを作成する][MDNWebGettingStarted]  
> *   [DevTools を使って CSS の基本的な変更を行う][DevToolsCssIndex]  
> *   [ローカル HTTP web サーバーを実行する][MDNSimpleLocalHTTPServer]  

## 概要  

ワークスペースを使用すると、Devtools で行った変更を、コンピューター上の同じファイルのローカルコピーに保存することができます。  たとえば、次のようにします。  

*   自分のサイトのソースコードはデスクトップにあります。  
*   ソースコードディレクトリからローカル web サーバーを実行しているため、サイトにアクセスできるように `localhost:8080` なります。  
*   `localhost:8080`Microsoft Edge で開かれており、DevTools を使ってサイトの CSS を変更しています。  

ワークスペースを有効にすると、DevTools で行った CSS の変更が、デスクトップのソースコードに保存されます。  

## 制限事項  

モダンフレームワークを使用している場合は、可能な限り早く実行するために最適化された形式に簡単に保持できる形式からソースコードを変換する可能性があります。  
通常、ワークスペースでは、最適化されたコードを[ソースマップ][TreehouseBlogSourceMaps]のヘルプを使用して元のソースコードに戻すことができます。  ただし、フレームワーク間のソースマップの使い方については、さまざまなバリエーションがあります。  Devtools は、すべてのバリエーションをサポートしているわけではありません。  

ワークスペースは、次のフレームワークでは動作しないことがわかっています。  

*   反応するアプリを作成する  
    
    <!-- If you run into issues while using Workspaces with your framework of choice, or you get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  
    
## 関連する機能: ローカルの上書き  

**ローカルオーバーライド**は、ワークスペースに似た別の devtools 機能です。  ページに対する変更を試す必要があり、ページの読み込み全体でそれらの変更を確認する必要がある場合は、ローカルの上書きを使用しますが、ページのソースコードへの変更のマッピングについては注意してください。  

<!--Todo: add section when content is ready  -->  

## 手順 1: セットアップ  

このチュートリアルを実行して、ワークスペースの実践的なエクスペリエンスを実現します。  

### デモを設定する  

1.  [デモを開き][GlitchWorkspacesDemo]ます。  <!--In the top-left of the editor, a randomly-generated project name is displayed.  -->  
    
    :::image type="complex" source="../media/workspaces-glitch-workspaces-demo-source.msft.png" alt-text="エラープロジェクト" lightbox="../media/workspaces-glitch-workspaces-demo-source.msft.png":::
       エラープロジェクト  
    :::image-end:::  
    
    <!--1.  Choose the project name.  -->
    <!--1.  Select **Advanced Options** > **Download Project**.  
    
    :::image type="complex" source="../media/workspaces-glitch-advanced-options-download-project.msft.png" alt-text="The Download Project button" lightbox="../media/workspaces-glitch-advanced-options-download-project.msft.png":::
       The Download Project button  
    :::image-end:::  
    -->
    <!--1.  Close the tab.  -->
    <!--1.  Unzip the source code and move the unzipped `app` directory to your desktop.  For the rest of this tutorial this directory is referred to as `~/Desktop/app`.  -->  
    
1.  `app`デスクトップにディレクトリを作成します。  ディレクトリ内のファイルのコピーを保存 `workspaces-demo` します。  このチュートリアルの残りの部分では、というディレクトリがと呼ばれて `~/Desktop/app` います。  
1.  でローカル web サーバーを起動 `~/Desktop/app` します。  以下は、起動のためのサンプルコードです `SimpleHTTPServer` が、好きなサーバーを使用することもできます。  
    
    :::row:::
       :::column span="":::
          ```bash
          cd ~/Desktop/app
          python -m SimpleHTTPServer # Python 2
          ```  
       :::column-end:::
       :::column span="":::
          ```bash
          cd ~/Desktop/app
          python -m http.server # Python 3
          ```  
       :::column-end:::
    :::row-end:::  
    
1.  Microsoft Edge でタブを開き、ローカルでホストされているバージョンのサイトに移動します。  またはのような URL を使用してアクセスできる必要があり `localhost:8080` `http://0.0.0.0:8080` ます。  正確な[ポート番号][WikiPortURLs]は異なる場合があります。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo.msft.png" alt-text="デモ" lightbox="../media/workspaces-workspaces-demo.msft.png":::
       デモ  
    :::image-end:::  
    
### DevTools のセットアップ  

1.  [ `Control` + `Shift` + `J` \ (Windows \)] または [ `Command` + `Option` + `J` \ (macOS \)] を選択して、devtools の**コンソール**パネルを開きます。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-console.msft.png" alt-text="コンソールパネル" lightbox="../media/workspaces-workspaces-demo-console.msft.png":::
       **コンソール**パネル  
    :::image-end:::  
    
1.  [**ソース**] タブを選択します。  
1.  [ **Filesystem** ] タブを選びます。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem.msft.png" alt-text="[Filesystem] タブ" lightbox="../media/workspaces-workspaces-demo-sources-filesystem.msft.png":::
       [ **Filesystem** ] タブ  
    :::image-end:::  
    
1.  [**ワークスペースにフォルダーを追加**] を選びます。  
1.  Enter キーを押す `~/Desktop/app` 。  
1.  ディレクトリの読み取りと書き込みを行うための DevTools アクセス許可を与えるには、[**許可**] を選びます。  
    [ **Filesystem** ] タブで、、、およびの横に緑の点が表示され `index.html` `script.js` `styles.css` ます。  これらの緑の点は、DevTools がページのネットワークリソースとの間のマッピングを確立したことを意味 `~/Desktop/app` します。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png" alt-text="[Filesystem] タブに、ローカルファイルとネットワーク間のマッピングが表示されるようになりました" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png":::
       [ **Filesystem** ] タブに、ローカルファイルとネットワーク間のマッピングが表示されるようになりました  
    :::image-end:::  
    
## 手順 2: CSS の変更をディスクに保存する  

1.  [開く] `styles.css` を選びます。  
    
    > [!NOTE]
    > `color`要素のプロパティ `h1` はに設定され `fuchsia` ます。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png" alt-text="テキストエディターでスタイルの css を表示する" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png":::
       `styles.css`テキストエディターでの表示  
    :::image-end:::  
    
1.  [**要素**] タブを選択します。  
1.  `color`要素のプロパティの値 `<h1>` を、お気に入りの色に変更します。  
    [ `<h1>` **スタイル**] ウィンドウで CSS ルールが適用されていることを確認するために、 **DOM ツリー**で要素を選ぶ必要があることに注意してください。  [] の横にある緑の点は、 `styles.css:1` 加えた変更がマップされていることを意味 `~/Desktop/app/styles.css` します。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-css.msft.png" alt-text="ファイルがリンクされていることを示す緑色のインジケーター" lightbox="../media/workspaces-workspaces-demo-elements-styles-css.msft.png":::
       ファイルがリンクされていることを示す緑色のインジケーター  
    :::image-end:::  
    
1.  `styles.css`もう一度テキストエディターで開きます。  `color`これで、プロパティが [お気に入りの色」に設定されました。  
1.  ページを再読み込みします。  要素の色 `<h1>` は、引き続き好みの色に設定されます。  これは、変更を加えたときに、DevTools によってディスクへの変更が保存されたためです。  次に、ページを再ロードすると、ローカルサーバーは、ファイルの変更されたコピーをディスクから提供します。  
    
## 手順 3: HTML の変更をディスクに保存する  

### [要素] パネルで HTML を変更する  

HTML は、要素パネルから変更できますが、DOM ツリーへの変更はディスクに保存されず、現在のブラウザーセッションのみに影響します。  
DOM ツリーは HTML ではありません。  

<!--### Try changing HTML from the Elements panel  

> [!WARNING]
> The workflow that you are about to try does not work.  You are trying it now so that you do not waste time later trying to figure out why it is not working.  

1.  Choose the **Elements** tab.  
1.  Double-click the text content of the `h1` element, which says `Workspaces Demo`, and replace it with `I ❤️  Cake`.  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-change-h1.msft.png" alt-text="Attempting to change HTML from the DOM Tree of the Elements panel" lightbox="../media/workspaces-workspaces-demo-change-h1.msft.png":::
       Attempting to change HTML from the **DOM Tree** of the **Elements** panel  
    :::image-end:::  
    
1.  Open `~/Desktop/app/index.html` in a text editor.  The change that you just made does not appear.  
1.  Reload the page.  The page reverts to its original title.  
    
#### Optional: Why it is not working  

> [!NOTE]
> This section describes why the workflow from [Try changing HTML from the Elements panel](#try-changing-html-from-the-elements-panel) does not work.  You should skip this section if you do not care why.  

*   The tree of nodes that you see on the **Elements** panel represents the [DOM][MDNWebAPIsDOM] of the page.  
*   To display a page, a browser fetches HTML over the network, parses the HTML, and then converts it into a tree of DOM nodes.  
*   If the page has any JavaScript, that JavaScript may add, delete, or change DOM nodes.  CSS may change the DOM, too, using the [`content`][MDNCSSContent] property.  
*   The browser eventually uses the DOM to determine what content it should present to browser users.  
*   Therefore, the final state of the page that users see may be very different from the HTML that the browser fetched.  
*   This makes it difficult for DevTools to resolve where a change made in the **Elements** panel should be saved, because the DOM is affected by HTML, JavaScript, and CSS.  

In short, the **DOM Tree** `!==` HTML.  
-->  

### [ソース] パネルで HTML を変更する  

ページの HTML への変更を保存する場合は、[**ソース**] パネルを使用します。  

1.  [**ソース**] タブを選択します。  
1.  [**ページ**] タブを選択します。  
1.  [ **(インデックス)**] を選びます。  ページの HTML が開きます。  
1.  置換後 `<h1>Workspaces Demo</h1>` の文字列 `<h1>I ❤️  Cake</h1>`  次の図を参照してください。  
1.  `Control` + `S` 変更を保存するには、\ (Windows \) または `Command` + `S` \ (macOS \) を選択します。  
1.  ページを再読み込みします。  `<h1>`要素に新しいテキストが引き続き表示されています。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-page-h1.msft.png" alt-text="[ソース] パネルでの HTML の変更" lightbox="../media/workspaces-workspaces-demo-sources-page-h1.msft.png":::
       行12はに設定されています `I ❤️  Cake`  
    :::image-end:::  
    
1.  [開く] `~/Desktop/app/index.html` を選びます。  `<h1>`要素に新しいテキストが含まれています。  
    
## 手順 4: JavaScript の変更をディスクに保存する  

[**ソース**] パネルも JavaScript を変更する場所です。  ただし、サイトを変更するときに、[**要素**] パネルや**コンソール**パネルなどの他のパネルにアクセスする必要がある場合もあります。  他のパネルと共に**ソース**パネルを開く方法があります。  

1.  [**要素**] タブを選択します。  
1.  [ `Control` + `Shift` + `P` \ (Windows \)] または [ `Command` + `Shift` + `P` \ (macOS \)] を選びます。  **コマンドメニュー**が開きます。  
1.  入力して `QS` 、[**クイックソースの表示**] を選択します。  [DevTools] ウィンドウの下部に、[**クイックソース**] タブが表示されています。 タブには `index.html` 、[**ソース**] パネルで最後に編集したファイルの内容が表示されます。  [**クイックソース**] タブでは、[**ソース**] パネルからエディターが表示されるため、他のパネルを開いたままファイルを編集できます。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png" alt-text="[コマンド] メニューを使用して [クイックソース] タブを開く" lightbox="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png":::
       **コマンドメニュー**を使用して [**クイックソース**] タブを開く  
    :::image-end:::  
    
1.  [ `Control` + `P` \ (Windows \)] または [ `Command` + `P` \ (macOS \)] を選択して、[**ファイルを開く**] ダイアログボックスを開きます。  次の図を参照してください。  
1.  入力して `script` 、[**アプリ/script.js**] を選びます。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-script.msft.png" alt-text="[ファイルを開く] ダイアログボックスを使用して script.js を開く" lightbox="../media/workspaces-workspaces-demo-search-script.msft.png":::
       [ `script.js` ファイルを**開く**] ダイアログボックスを開く  
    :::image-end:::  
    
    > [!NOTE]
    > `Save Changes To Disk With Workspaces`デモのリンクは、定期的にスタイル設定されています。  
    
1.  [**クイックソース**] タブを使用して、 **script.js**の下部に次のコードを追加します。  
    
    ```javascript
    console.log('greetings from script.js');
    document.querySelector('a').style = 'font-style:italic';
    ```  
    
1.  `Control` + `S` 変更を保存するには、\ (Windows \) または `Command` + `S` \ (macOS \) を選択します。  
1.  ページを再読み込みします。  
    
    > [!NOTE]
    > ページ上のリンクが斜体になりました。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png" alt-text="ページ上のリンクが斜体になりました" lightbox="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png":::
       ページ上のリンクが斜体になりました  
    :::image-end:::  
    
## 次のステップ  

このチュートリアルで学んだことを使用して、自分のプロジェクトでワークスペースをセットアップします。  <!-- If you run into any issues or are able to get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  

<!--  
If you have more feedback on these topics or anything else, please use any of the channels below:  

*   [Mailing List][AlphabetGroupsAlphabetBrowserDevTools]  
*   [Twitter][TwitterAlphabetBrowserDevTools]  
-->  

<!-- links -->  

[DevToolsCssIndex]: ../css/index.md# "CSS の表示と変更の概要 |Microsoft ドキュメント"  

<!--[LocalOverrides]: ../whats-new/2018/01/devtools#overrides -->  

<!--[AlphabetGroupsAlphabetBrowserDevTools]: https://groups.alphabet.com/forum/#!forum/alphabet-browser-developer-tools "Alphabet Browser DevTools - Alphabet Groups"  -->  

[GlitchWorkspacesDemo]: https://glitch.com/edit/#!/microsoft-edge-chromium-devtools?path=workspaces-demo/index.html:1:0 "ワークスペースデモファイル |故障"  

[MDNCSSContent]: https://developer.mozilla.org/docs/Web/CSS/content "コンテンツ-CSS: カスケードスタイルシート |MDN"  
[MDNWebGettingStarted]: https://developer.mozilla.org/docs/Learn/Getting_started_with_the_web "Web の概要 |MDN"  
[MDNSimpleLocalHTTPServer]: https://developer.mozilla.org/docs/Learn/Common_questions/set_up_a_local_testing_server#Running_a_simple_local_HTTP_server "簡単なローカル HTTP サーバーを実行する |MDN"  
[MDNWebAPIsDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM の概要-Web Api |MDN"  

<!--[StackOverflowAlphabetBrowserDevTools]: https://stackoverflow.com/questions/ask?tags=alphabet-browser-devtools "Alphabet Browser DevTools - Stack Overflow"  -->

[TreehouseBlogSourceMaps]: https://blog.teamtreehouse.com/introduction-source-maps "ソースマップの概要 |Treehouse ブログ"  

<!-- [TwitterAlphabetBrowserDevTools]: https://twitter.com/alphabetbrowserdevtools "Alphabet Browser DevTools \(@AlphabetBrowserDevTools\) | Twitter"  -->

[WikiPortURLs]: https://en.wikipedia.org/wiki/Port_(computer_networking)#Use_in_URLs "ポート \ (コンピューターネットワーク \)-Wikipedia"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/workspaces/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
