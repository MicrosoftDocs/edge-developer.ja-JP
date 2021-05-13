---
description: DevTools 内で行われた変更をディスクに保存する方法について学習します。
title: ワークスペースを使用してファイルを編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 640bb80e01f776c763af053cf8354ce90cf52e93
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564666"
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
# <a name="edit-files-with-workspaces"></a>ワークスペースを使用してファイルを編集する  

このチュートリアルでは、Workspace のセットアップと使用に関する実践的な方法を説明します。  ワークスペースにファイルを追加すると、DevTools 内のソース コードで行った変更はローカル コンピューターに保存され、Web ページを更新した後も保持されます。  

> [!IMPORTANT]
> **前提条件**: このチュートリアルを開始する前に、次の操作を実行する方法を知っている必要があります。  
> 
> *   [html、CSS、JavaScript を使用して Web ページを作成する][MDNWebGettingStarted]  
> *   [DevTools を使用して CSS に基本的な変更を加える][DevToolsCssIndex]  
> *   [ローカル HTTP Web サーバーの実行][MDNSimpleLocalHTTPServer]  

## <a name="overview"></a>概要  

ワークスペースを使用すると、Devtools で行った変更を、コンピューター上の同じファイルのローカル コピーに保存できます。  このチュートリアルでは、コンピューターに次の設定が必要です。  

*   デスクトップ上にサイトのソース コードがあります。  
*   ソース コード ディレクトリからローカル Web サーバーを実行して、サイトにアクセスできます `localhost:8080` 。  
*   このページ `localhost:8080` でMicrosoft Edge、DevTools を使用してサイトの CSS を変更しています。  

Workspaces を有効にすると、DevTools 内で行った CSS の変更がデスクトップのソース コードに保存されます。  

## <a name="limitations"></a>制限事項  

モダン フレームワークを使用している場合は、ソース コードを保守しやすい形式から、可能な限り迅速に実行するために最適化された形式に変換される可能性があります。  

ワークスペースは、通常、ソース マップの助けを借りて、最適化されたコードを元のソース コードに [マップすることができます][TreehouseBlogSourceMaps]。  ただし、各フレームワークがソース マップを使用する方法に関して、フレームワーク間には多くのバリエーションがあります。  Devtools は、すべてのバリエーションをサポートしているのではない。  

ワークスペースは、次のフレームワークでは動作しません。  

*   アプリReact作成  

    <!-- If you run into issues while using Workspaces with your framework of choice, or you get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  
    
## <a name="related-feature-local-overrides"></a>関連機能: ローカルオーバーライド  

**ローカル オーバーライドは** 、Workspaces に似た別の DevTools 機能です。  Web ページの変更を試し、Web ページの読み込み間で変更を表示する必要がある場合はローカルオーバーライドを使用しますが、変更を Web ページのソース コードにマッピングする場合は気にしません。  

<!--Todo: add section when content is ready  -->  

## <a name="step-1-set-up"></a>手順 1: セットアップ  

Workspaces で実践的なエクスペリエンスを得るには、次のアクションを実行します。  

### <a name="set-up-the-demo"></a>デモのセットアップ  

1.  [デモを開きます][GlitchWorkspacesDemo]。  <!--In the top-left of the editor, a randomly-generated project name is displayed.  -->  
    
    :::image type="complex" source="../media/workspaces-glitch-workspaces-demo-source.msft.png" alt-text="Glitch プロジェクト" lightbox="../media/workspaces-glitch-workspaces-demo-source.msft.png":::
       Glitch プロジェクト  
    :::image-end:::  
    
    <!--1.  Choose the project name.  -->  
    <!--1.  Choose **Advanced Options** > **Download Project**.  
    
    :::image type="complex" source="../media/workspaces-glitch-advanced-options-download-project.msft.png" alt-text="The Download Project button" lightbox="../media/workspaces-glitch-advanced-options-download-project.msft.png":::
       The Download Project button  
    :::image-end:::  

    -->  
    <!--1.  Close the tab.  -->  
    <!--1.  Unzip the source code and move the unzipped `app` directory to your desktop.  For the rest of this tutorial the unzipped directory is referred to as `~/Desktop/app`.  -->  
    
1.  デスクトップに `app` ディレクトリを作成します。  ディレクトリからディレクトリにファイル `workspaces-demo` のコピーを保存 `app` します。  チュートリアルの残りの部分では、ディレクトリはと呼ばれます `~/Desktop/app` 。  
1.  でローカル Web サーバーを起動します `~/Desktop/app` 。  以下に、起動用のサンプル コードを示しますが、必要な `SimpleHTTPServer` サーバーを使用できます。  
    
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
    
1.  サイトでタブを開Microsoft Edge、ローカルでホストされているバージョンのサイトに移動します。  URL を使用してアクセスできる必要 `localhost:8080` があります `http://0.0.0.0:8080` 。  正確な [ポート番号は][WikiPortURLs] 異なる場合があります。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo.msft.png" alt-text="デモ" lightbox="../media/workspaces-workspaces-demo.msft.png":::
       デモ  
    :::image-end:::  
    
### <a name="set-up-devtools"></a>DevTools のセットアップ  

1.  `Control` + `Shift` + `J` \(Windows Linux\) または `Command` + `Option` + `J` \(macOS\) を選択して、DevTools の**コンソール**パネルを開きます。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-console.msft.png" alt-text="[コンソール] パネル" lightbox="../media/workspaces-workspaces-demo-console.msft.png":::
       [ **コンソール]** パネル  
    :::image-end:::  
    
1.  [ソース] **ツールに移動** します。  
1.  左側の **[ナビゲーター]** ウィンドウで、[ファイルシステム] タブ **を選択** します。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem.msft.png" alt-text="[ファイルシステム] タブ" lightbox="../media/workspaces-workspaces-demo-sources-filesystem.msft.png":::
       [ **ファイルシステム]** タブ  
    :::image-end:::  
    
1.  [ワークスペース **にフォルダーを追加] を選択します**。  
1.  「`~/Desktop/app`」と入力します。  
1.  [ **許可] を** 選択して、ディレクトリへの読み取りおよび書き込みのアクセス許可を DevTools に付与します。  
    [ファイルシステム **] タブ** で、緑のドットが 、 `index.html` 、 と の横 `script.js` に表示されます `styles.css` 。  緑色のドットは、DevTools がページのネットワーク リソースと内のファイルとの間にマッピングを確立したと示します `~/Desktop/app` 。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png" alt-text="[ファイルシステム] タブは、ローカル ファイルとネットワーク ファイル間のマッピングを示します。" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png":::
       [ **ファイルシステム]** タブは、ローカル ファイルとネットワーク ファイル間のマッピングを示します。  
    :::image-end:::  
    
## <a name="step-2-save-a-css-change-to-disk"></a>手順 2: CSS の変更をディスクに保存する  

1.  を `styles.css` 開きます。  
    
    > [!NOTE]
    > 要素 `color` のプロパティ `h1` は に設定されます `fuchsia` 。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png" alt-text="テキスト エディターで styles.css を表示する" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png":::
       テキスト `styles.css` エディターでの表示  
    :::image-end:::  
    
1.  [要素] **ツールを選択** します。  
1.  要素のプロパティの値 `color` を、お気に `<h1>` 入りの色に変更します。  
    スタイル ウィンドウに適用される CSS ルールを表示するには `<h1>` **、DOM ツリー** で要素を選択する **必要** があります。  次の緑の点 `styles.css:1` は、変更がマップされる点を意味します `~/Desktop/app/styles.css` 。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-css.msft.png" alt-text="ファイルがリンクされている緑色のインジケーター" lightbox="../media/workspaces-workspaces-demo-elements-styles-css.msft.png":::
       ファイルがリンクされている緑色のインジケーター  
    :::image-end:::  
    
1.  テキスト `styles.css` エディターで再度開きます。  この `color` プロパティは、お気に入りの色に設定されます。  
1.  ページを最新の情報に更新してください。  要素の色は `<h1>` 、引き続きお気に入りの色に設定されます。  変更を行った場合、DevTools によって変更がディスクに保存されたため、更新後も変更はそのまま残ります。  次に、ページを更新すると、ローカル サーバーがディスクからファイルの変更されたコピーを提供しました。  
    
## <a name="step-3-save-an-html-change-to-disk"></a>手順 3: HTML の変更をディスクに保存する  

### <a name="change-html-from-the-elements-panel"></a>要素パネルから HTML を変更する  

要素パネルから html に変更を加える場合がありますが、DOM ツリーへの変更はディスクに保存されません。現在のブラウザー セッションにのみ影響します。  

DOM ツリーは html ではありません。  

<!--### Try changing HTML from the Elements panel  

> [!WARNING]
> The workflow that you are about to try does not work.  You are trying it now so that you do not waste time later trying to figure out why it is not working.  

1.  Choose the **Elements** tool.  
1.  Choose and edit the text content of the `h1` element, which says `Workspaces Demo`, and replace it with `I ❤️  Cake`.  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-change-h1.msft.png" alt-text="Attempt to change html from the DOM Tree of the Elements panel" lightbox="../media/workspaces-workspaces-demo-change-h1.msft.png":::
       Attempt to change html from the DOM Tree of the **Elements** tool  
    :::image-end:::  
    
1.  Open `~/Desktop/app/index.html` in a text editor.  The change that you just made does not appear.  
1.  Refresh the page.  The page reverts to the original title.  
    
#### Optional: Why it is not working  

> [!NOTE]
> This section describes why the workflow from [Try changing html from the Elements panel](#try-changing-html-from-the-elements-panel) does not work.  You should skip this section if you do not care why.  

*   The tree of nodes that are displayed on the **Elements** tool represents the [DOM][MDNWebAPIsDOM] of the page.  
*   To display a page, a browser fetches html over the network, parses the html, and then converts it into a tree of DOM nodes.  
*   If the page has any JavaScript, that JavaScript may add, delete, or change DOM nodes.  CSS may change the DOM, too, using the [`content`][MDNCSSContent] property.  
*   The browser eventually uses the DOM to determine what content it should present to browser users.  
*   Therefore, the final state of the webpage displayed for users may be very different from the html that the browser fetched.  
*   This makes it difficult for DevTools to resolve where a change made in the **Elements** tool should be saved, because the DOM is affected by HTML, JavaScript, and CSS.  

In short, the **DOM Tree** `!==` HTML.  
-->  

### <a name="change-html-from-the-sources-tool"></a>ソース ツールから HTML を変更する  

Web ページの HTML への変更を保存する場合は、[ソース] ツール **を使用** します。  

1.  [ソース] **ツールに移動** します。  
1.  左側の **[ナビゲーター]** ウィンドウで、[ページ] タブ **を選択** します。  
1.  ( **インデックス) を選択します**。  ページの HTML が開きます。  
1.  に `<h1>Workspaces Demo</h1>` 置き換える `<h1>I ❤️  Cake</h1>` 。  次の図を確認します。  
1.  `Control` + `S` \(Windows Linux\) または `Command` + `S` \(macOS\) を選択して変更を保存します。  
1.  ページを最新の情報に更新してください。  ページ `<h1>` が更新された後も、要素は新しいテキストを表示し続ける。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-page-h1.msft.png" alt-text="ソース ツールから HTML を変更する" lightbox="../media/workspaces-workspaces-demo-sources-page-h1.msft.png":::
       ソース ツールから HTML **を変更** する  
    :::image-end:::  
    
1.  を `~/Desktop/app/index.html` 開きます。  要素 `<h1>` には、新しいテキストが含まれる。  
    
## <a name="step-4-save-a-javascript-change-to-disk"></a>手順 4: JavaScript の変更をディスクに保存する  

DevTools のコード エディターを使用する主な場所は、 **ソース ツール** です。  ただし、ファイルの編集中に、[要素] ツール**** や [コンソール****] パネルなどの他のツールにアクセスする必要がある場合があります。  クイック**ソース ツール**を使用すると、ソース ツールのエディターが提供されます。どのツールも開いている間です。 ****  

DevTools コード エディターを他のツールと共に開くには、次の操作を行います。  

1.  [要素] ツール **に移動** します。  
1.  `Control` + `Shift` + `P` \(Windows Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。  [ **コマンド] メニューが** 開きます。  
1.  を `Quick Source` 入力し、[クイック ソース **の表示] を選択します**。  [DevTools] ウィンドウの下部にクイック**** ソース ツールが表示され、ソース ツールで編集した最後のファイルであるコンテンツ `index.html` **が表示**されます。    
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png" alt-text="コマンド メニューを使用してクイック ソース ツールを開く" lightbox="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png":::
       コマンド メニュー **を使用して** クイック ソース ツール **を開く**  
    :::image-end:::  
    
1.  `Control` + `P` \(Windows Linux\) または \(macOS\) を選択して、[ファイルを開く `Command` + `P` ]**ダイアログを開**きます。  次の図を確認します。  
1.  [入力 `script` ] をクリックし、[**アプリ/script.js] をscript.js。 **  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-script.msft.png" alt-text="[ファイルscript.jsダイアログを使用してファイルを開く" lightbox="../media/workspaces-workspaces-demo-search-script.msft.png":::
       [ファイル `script.js` を開く] **ダイアログを使用して開** く  
    :::image-end:::  
    
    > [!NOTE]
    > デモ `Save Changes To Disk With Workspaces` のリンクは、定期的にスタイル設定されます。  
    
1.  クイック ソース ツールを使用して **、script.jsコード****を下部に追加**します。  
    
    ```javascript
    console.log('greetings from script.js');
    document.querySelector('a').style = 'font-style:italic';
    ```  
    
1.  `Control` + `S` \(Windows Linux\) または `Command` + `S` \(macOS\) を選択して変更を保存します。  
1.  ページを最新の情報に更新してください。  
    
    > [!NOTE]
    > ページ上のリンクが、現在は italicized です。  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png" alt-text="ページ上のリンクが italicized に変更されました" lightbox="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png":::
       ページ上のリンクが italicized に変更されました  
    :::image-end:::  
    
## <a name="next-steps"></a>次の手順  

このチュートリアルで学んだことを使用して、独自のプロジェクトで Workspaces を設定します。  <!-- If you run into any issues or are able to get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  

<!--  
If you have more feedback on the topics or anything else, please use any of the channels below:  

*   [Mailing List][AlphabetGroupsAlphabetBrowserDevTools]  
*   [Twitter][TwitterAlphabetBrowserDevTools]  -->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsCssIndex]: ../css/index.md "CSS ファイルの表示と変更の|Microsoft Docs"  

<!--[LocalOverrides]: ../whats-new/2018/01/devtools#overrides -->  

<!--[AlphabetGroupsAlphabetBrowserDevTools]: https://groups.alphabet.com/forum/#!forum/alphabet-browser-developer-tools "Alphabet Browser DevTools - Alphabet Groups"  -->  

[GlitchWorkspacesDemo]: https://glitch.com/edit/#!/microsoft-edge-chromium-devtools?path=workspaces-demo/index.html:1:0 "Workspaces のデモ ファイル|Glitch"  

[MDNCSSContent]: https://developer.mozilla.org/docs/Web/CSS/content "コンテンツ - CSS: カスケード スタイル シート |MDN"  
[MDNWebGettingStarted]: https://developer.mozilla.org/docs/Learn/Getting_started_with_the_web "Web アプリケーションの|MDN"  
[MDNSimpleLocalHTTPServer]: https://developer.mozilla.org/docs/Learn/Common_questions/set_up_a_local_testing_server#Running_a_simple_local_HTTP_server "単純なローカル HTTP サーバー を実行|MDN"  
[MDNWebAPIsDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM の概要 - Web API |MDN"  

<!--[StackOverflowAlphabetBrowserDevTools]: https://stackoverflow.com/questions/ask?tags=alphabet-browser-devtools "Alphabet Browser DevTools - Stack Overflow"  -->

[TreehouseBlogSourceMaps]: https://blog.teamtreehouse.com/introduction-source-maps "ソース ソースの概要マップ |Treehouse ブログ"  

<!-- [TwitterAlphabetBrowserDevTools]: https://twitter.com/alphabetbrowserdevtools "Alphabet Browser DevTools \(@AlphabetBrowserDevTools\) | Twitter"  -->

[WikiPortURLs]: https://en.wikipedia.org/wiki/Port_(computer_networking)#Use_in_URLs "Port \(computer networking\) - Wikipedia"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/workspaces/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
