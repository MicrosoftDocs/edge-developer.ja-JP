---
title: ワークスペースを使用してファイルを編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/20/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 8a31dd9fbfe492cf8eaacc654f7d501925f730f2
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942179"
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
> このチュートリアルの目標は、ワークスペースの設定と使用に関する実用的な演習を提供することで、独自のプロジェクトでワークスペースを使用できるようにすることです。  ワークスペースを有効にした後で、DevTools 内で行ったソース コードに対する変更をローカル コンピューター上で保存できます。  

> [!IMPORTANT]
> **前提条件**: このチュートリアルを開始する前に、次の操作を実行する方法を理解しておく必要があります。  
> 
> *   [Web ページを作成するには、html、CSS、JavaScript を使用する][MDNWebGettingStarted]  
> *   [DevTools を使用して CSS に基本的な変更を加える][DevToolsCssIndex]  
> *   [ローカル HTTP Web サーバーを実行する][MDNSimpleLocalHTTPServer]  

## 概要  

ワークスペースを使用すると、Devtools で行う変更をコンピューター上の同じファイルのローカル コピーに保存できます。  このチュートリアルでは、コンピューターに次の設定が必要です。  

*   サイトのソース コードがデスクトップにあります。  
*   サイトがアクセスできるように、ソース コード ディレクトリからローカルの Web サーバーを実行している `localhost:8080` 場合。  
*   Microsoft Edge で `localhost:8080` 開き、DevTools を使用してサイトの CSS を変更します。  

ワークスペースが有効になっていると、DevTools 内で行った CSS の変更は、デスクトップ上のソース コードに保存されます。  

## 制限事項  

モダン フレームワークを使用している場合、ソース コードはできるだけすばやく実行されるように最適化されている形式からソース コードを変換できることがあります。  

通常、ワークスペースは、最適化されたコードを元のソース コードにマップして元のコードに [マ][TreehouseBlogSourceMaps]ップすることができます。  しかし、各国でのソース マップの使用方法には、フレームワーク間のさまざまなバリエーションがあります。  Devtools は、すべてのバリエーションをサポートするのが簡単です。  

ワークスペースは、次のフレームワークでは動作しないことを知っています。  

*   再度正アクティブ化アプリを作成する  

    <!-- If you run into issues while using Workspaces with your framework of choice, or you get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  
    
## 関連する機能: ローカル オーバーライド  

**ローカル オーバーライド** はワークスペースにおける別の DevTools 機能です。  ページの変更を試してみて、ページの読み込み全体で変更を確認する必要がある場合は、ローカル オーバーライドを使用しますが、ページのソース コードに変更をマッピングすることはごまくわかりません。  

<!--Todo: add section when content is ready  -->  

## 手順 1: セットアップ  

ワークスペースでの操作性を高めているには、次の操作を行います。  

### デモを設定する  

1.  [デモを開きます][GlitchWorkspacesDemo]。  <!--In the top-left of the editor, a randomly-generated project name is displayed.  -->  
    
    :::image type="complex" source="../media/workspaces-glitch-workspaces-demo-source.msft.png" alt-text="グリッチ プロジェクト" lightbox="../media/workspaces-glitch-workspaces-demo-source.msft.png":::
       グリッチ プロジェクト  
    :::image-end:::  
    
    <!--1.  Choose the project name.  -->  
    <!--1.  Select **Advanced Options** > **Download Project**.  
    
    :::image type="complex" source="../media/workspaces-glitch-advanced-options-download-project.msft.png" alt-text="The Download Project button" lightbox="../media/workspaces-glitch-advanced-options-download-project.msft.png":::
       The Download Project button  
    :::image-end:::  

    -->  
    <!--1.  Close the tab.  -->  
    <!--1.  Unzip the source code and move the unzipped `app` directory to your desktop.  For the rest of this tutorial the unzipped directory is referred to as `~/Desktop/app`.  -->  
    
1.  デスクトップに `app` ディレクトリを作成します。  ディレクトリからディレクトリ `workspaces-demo` にファイルのコピーを `app` 保存します。  チュートリアルの残りの場合、ディレクトリは "リテンシック" と評価されます `~/Desktop/app` 。  
1.  ローカル Web サーバーを開始します `~/Desktop/app` 。  以下は、起動時のサンプル コードですが `SimpleHTTPServer` 、どのサーバーを使用するのかを指定することもできます。  
    
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
    
1.  Microsoft Edge でタブを開き、ローカルでホストされているバージョンのサイトに移動します。  URL やその URL を使ってアクセス `localhost:8080` できます `http://0.0.0.0:8080` 。  正しいポート [番号が異][WikiPortURLs] なる場合があります。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo.msft.png" alt-text="デモ" lightbox="../media/workspaces-workspaces-demo.msft.png":::
       デモ  
    :::image-end:::  
    
### DevTools のセットアップ  

1.  `Control` + `Shift` + `J` \(Windows\) または `Command` + `Option` + `J` \(macOS\) を選択して DevTools**の本体**パネルを開きます。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-console.msft.png" alt-text="本体パネル" lightbox="../media/workspaces-workspaces-demo-console.msft.png":::
       本 **体パ** ネル  
    :::image-end:::  
    
1.  [ソース] **タブを選** びます。  
1.  **[Filesystem] タブを選**びます。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem.msft.png" alt-text="[ファイルシステム] タブ" lightbox="../media/workspaces-workspaces-demo-sources-filesystem.msft.png":::
       **[ファイルシステム]** タブ  
    :::image-end:::  
    
1.  [ワ **ークスペースにフォルダーを追加] を選びます**。  
1.  「`~/Desktop/app`」と入力します。  
1.  [Allow to Give to DevTools permission to read and writs to read and write to the directory] **([Allow** to DevTools] を選び、ディレクトリの読み取りと書き込みを許可します。  
    [ **ファイルシステム]** タブには、緑のドットが隣り合 `index.html` わせ表示 `script.js` されます `styles.css` 。  これらの緑のドットは、DevTools がページのネットワーク リソースとその中のファイル間のマッピングを決定したことを意味します `~/Desktop/app` 。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png" alt-text="[ファイル] タブに、ローカル ファイルとネットワーク ネットワークの間のマッピングが表示されるようになりました" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png":::
       [ **ファイル] タブ** に、ローカル ファイルとネットワーク ネットワークの間のマッピングが表示されるようになりました  
    :::image-end:::  
    
## 手順 2: CSS をディスクに変更する  

1.  開 `styles.css` きます。  
    
    > [!NOTE]
    > 要素 `color` のプロパティ `h1` は設定されています `fuchsia` 。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png" alt-text="テキスト エディターでスタイル.css を表示する" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png":::
       テキスト `styles.css` エディターで表示する  
    :::image-end:::  
    
1.  [要素 **] タブを選** びます。  
1.  要素のプロパティ `color` の値を `<h1>` お気に入りの色に変更します。  
    [スタイル] ウィンドウに CSS ルールが適用されている CSS ルールを表示するには `<h1>` **、DOM ツ** リーで要素を **選ぶ必要** があります。  横にある緑色のドットは、行う変更がマップされている `styles.css:1` ことを意味します `~/Desktop/app/styles.css` 。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-css.msft.png" alt-text="ファイルがリンクされている緑のインジケーター" lightbox="../media/workspaces-workspaces-demo-elements-styles-css.msft.png":::
       ファイルがリンクされている緑のインジケーター  
    :::image-end:::  
    
1.  もう `styles.css` 一度テキスト エディターで開きます。  これ `color` で、このプロパティはお気に入りの色に設定されます。  
1.  ページを最新の情報に更新してください。  要素の色は `<h1>` 、引き続きお気に入りの色に設定されます。  変更内容はディスクに保存されたため、更新中も維維します。  そして、ページを更新すると、ローカル サーバーはディスクから変更されたファイルのコピーを開示しました。  
    
## 手順 3: ディスクに HTML 変更を保存する  

### [要素パネル] から HTML を変更する  

要素パネルから HTML を変更できますが、DOM ツリーの変更はディスクに保存されず、現在のブラウザーの操作のみが有効です。  

DOM ツライは html ではサポートされていません。  

<!--### Try changing HTML from the Elements panel  

> [!WARNING]
> The workflow that you are about to try does not work.  You are trying it now so that you do not waste time later trying to figure out why it is not working.  

1.  Choose the **Elements** tab.  
1.  Choose and edit the text content of the `h1` element, which says `Workspaces Demo`, and replace it with `I ❤️  Cake`.  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-change-h1.msft.png" alt-text="Attempt to change html from the DOM Tree of the Elements panel" lightbox="../media/workspaces-workspaces-demo-change-h1.msft.png":::
       Attempt to change html from the DOM Tree of the **Elements** panel  
    :::image-end:::  
    
1.  Open `~/Desktop/app/index.html` in a text editor.  The change that you just made does not appear.  
1.  Refresh the page.  The page reverts to the original title.  
    
#### Optional: Why it is not working  

> [!NOTE]
> This section describes why the workflow from [Try changing html from the Elements panel](#try-changing-html-from-the-elements-panel) does not work.  You should skip this section if you do not care why.  

*   The tree of nodes that you see on the **Elements** panel represents the [DOM][MDNWebAPIsDOM] of the page.  
*   To display a page, a browser fetches html over the network, parses the html, and then converts it into a tree of DOM nodes.  
*   If the page has any JavaScript, that JavaScript may add, delete, or change DOM nodes.  CSS may change the DOM, too, using the [`content`][MDNCSSContent] property.  
*   The browser eventually uses the DOM to determine what content it should present to browser users.  
*   Therefore, the final state of the page that users see may be very different from the html that the browser fetched.  
*   This makes it difficult for DevTools to resolve where a change made in the **Elements** panel should be saved, because the DOM is affected by HTML, JavaScript, and CSS.  

In short, the **DOM Tree** `!==` HTML.  
-->  

### [ソース] パネルから HTML を変更する  

ページの html への変更を保存する場合は、[ソース] パネル **で行** います。  

1.  [ソース] **タブを選** びます。  
1.  [ページ] **タブを選択** します。  
1.  **[(索引) を選びます] を選びます**。  ページの HTML が開きます。  
1.  置換 `<h1>Workspaces Demo</h1>` の文字列 `<h1>I ❤️  Cake</h1>`  次の図を参照してください。  
1.  `Control` + `S` \(Windows\) または `Command` + `S` \(macOS\) を選択して変更を保存します。  
1.  ページを最新の情報に更新してください。  要素 `<h1>` には新しいテキストが引き続き表示されます。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-page-h1.msft.png" alt-text="[ソース] パネルから HTML を変更する" lightbox="../media/workspaces-workspaces-demo-sources-page-h1.msft.png":::
       [ソース] パネル **から HTML を** 変更する  
    :::image-end:::  
    
1.  開 `~/Desktop/app/index.html` きます。  要素 `<h1>` には新しいテキストが含まれている。  
    
## 手順 4: JavaScript の変更をディスクに保存する  

[ **ソース]** パネルは、JavaScript に変更を加える場所です。  ただし、場合によっては、[ **要素** ] パネルや **[本** 体] パネルなど、他のパネルにアクセスしなけやすくなり、サイトに変更を加える必要がある場合もあります。  [ソース] パネル**Sources**を他のパネルと一度に開く方法があります。  

1.  [要素 **] タブを選** びます。  
1.  `Control` + `Shift` + `P` \(Windows\) または `Command` + `Shift` + `P` \(macOS\) を選択します。  コマンド **メニューが** 開きます。  
1.  「クイック `QS` ソースの **表示」を選びます**。  [開発ツール] ウィンドウの下部に 、[クイック ソース] タブ **が表示されています** 。 タブには、[ソース] パネルで最後に編集したファイルである `index.html` **内容が** 表示されます。  [**クイック ソース]** タブには [ソース]**Sources**パネルからエディターが表示されるので、他のパネルを開いている間にファイルを編集できます。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png" alt-text="[コマンド] メニューを使用して [クイック ソース] タブを開く" lightbox="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png":::
       [コマンド] **メニューを使用して [** クイック ソース] **タブを開く**  
    :::image-end:::  
    
1.  `Control` + `P` \(Windows\) または `Command` + `P` \(macOS\) を選択して、[ファイルを**開く] ダイアログを開**きます。  次の図を参照してください。  
1.  「 `script` 入力してアプリ **/またはアプリ/ボタンscript.js。 **  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-script.msft.png" alt-text="[ファイルを開script.js] ダイアログ ボックスを使用して、タブを開く" lightbox="../media/workspaces-workspaces-demo-search-script.msft.png":::
       [ファイル `script.js` を開 **く] ダイアログ ボックスを使って開** く  
    :::image-end:::  
    
    > [!NOTE]
    > デ `Save Changes To Disk With Workspaces` モのリンクは定的に適用されます。  
    
1.  [クイック ソース] タブを使用**して、script.jsの下部に次の****コードを追加**します。  
    
    ```javascript
    console.log('greetings from script.js');
    document.querySelector('a').style = 'font-style:italic';
    ```  
    
1.  `Control` + `S` \(Windows\) または `Command` + `S` \(macOS\) を選択して変更を保存します。  
1.  ページを最新の情報に更新してください。  
    
    > [!NOTE]
    > ページ上のリンクがイタリアル化されます。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png" alt-text="ページ上のリンクがイタリアル化されるようになりました" lightbox="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png":::
       ページ上のリンクがイタリアル化されるようになりました  
    :::image-end:::  
    
## 次のステップ  

このチュートリアルで学習したものを使用して、自分のプロジェクトでワークスペースを設定します。  <!-- If you run into any issues or are able to get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  

<!--  
If you have more feedback on the topics or anything else, please use any of the channels below:  

*   [Mailing List][AlphabetGroupsAlphabetBrowserDevTools]  
*   [Twitter][TwitterAlphabetBrowserDevTools]  
    -->  

<!-- links -->  

[DevToolsCssIndex]: ../css/index.md "CSS の表示と変更を開始する |Microsoft ドキュメント"  

<!--[LocalOverrides]: ../whats-new/2018/01/devtools#overrides -->  

<!--[AlphabetGroupsAlphabetBrowserDevTools]: https://groups.alphabet.com/forum/#!forum/alphabet-browser-developer-tools "Alphabet Browser DevTools - Alphabet Groups"  -->  

[GlitchWorkspacesDemo]: https://glitch.com/edit/#!/microsoft-edge-chromium-devtools?path=workspaces-demo/index.html:1:0 "ワークスペース デモ ファイル |グリトチ"  

[MDNCSSContent]: https://developer.mozilla.org/docs/Web/CSS/content "コンテンツ - CSS:カスケード スタイル シート |MDN"  
[MDNWebGettingStarted]: https://developer.mozilla.org/docs/Learn/Getting_started_with_the_web "Web の使用を開始する |MDN"  
[MDNSimpleLocalHTTPServer]: https://developer.mozilla.org/docs/Learn/Common_questions/set_up_a_local_testing_server#Running_a_simple_local_HTTP_server "簡単なローカル HTTP サーバーを実行する |MDN"  
[MDNWebAPIsDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM - Web API の概要 |MDN"  

<!--[StackOverflowAlphabetBrowserDevTools]: https://stackoverflow.com/questions/ask?tags=alphabet-browser-devtools "Alphabet Browser DevTools - Stack Overflow"  -->

[TreehouseBlogSourceMaps]: https://blog.teamtreehouse.com/introduction-source-maps "ソース マップの概要 |Treehouse ブログ"  

<!-- [TwitterAlphabetBrowserDevTools]: https://twitter.com/alphabetbrowserdevtools "Alphabet Browser DevTools \(@AlphabetBrowserDevTools\) | Twitter"  -->

[WikiPortURLs]: https://en.wikipedia.org/wiki/Port_(computer_networking)#Use_in_URLs "ポート \(コンピューター ネットワーク\) - Wikipedia"  

> [!NOTE]
> このページの一部は [、Google][GoogleSitePolicies] によって作成され共有された作業および共有に基づいて変更され、クリエイティブ コモンス属性 [4.0 国際ライセンス][CCA4IL]で説明されている用語に応じた使用されます。  
> ここには元のページが表示[され](https://developers.google.com/web/tools/chrome-devtools/workspaces/index)[、Kayce Basques][KayceBasques] \(テクニカル ライター, Chrome DevTools \& Lighthouse\) によって作成されます。  

[![クリエイティブ コブル ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
