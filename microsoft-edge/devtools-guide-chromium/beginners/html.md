---
description: はじめに DOM の使用
title: '初級者向け DevTools: HTML と DOM の使用を開始する'
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools
ms.openlocfilehash: 6ca27b720a17928545712666e43495c4da2fb880
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397931"
---
<!-- Copyright Katherine Jackson 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# <a name="devtools-for-beginners-get-started-with-html-and-the-dom"></a>初級者向け DevTools: HTML と DOM の使用を開始する  

これは、Web 開発の基本を教える一連のチュートリアルの最初の例です。  生産性を向上させる可能性がある、DevTools という名前Microsoft Edge一連の Web 開発者ツールについて説明します。  

この特定のチュートリアルでは、HTML と DOM について学習します。  HTML は、Web 開発のコア テクノロジの 1 つです。  Web ページの構造とコンテンツを制御する言語です。  DOM は Web ページの構造とコンテンツにも関連しています。詳細については、後で説明します。  

## <a name="goals"></a>目標  

実際に独自の Web サイトを構築して Web 開発を学ぶつもりです。  **DevTools for Beginners**シリーズのすべてのチュートリアルを完了すると、完成したサイトは次の図のようになります。  

:::image type="complex" source="../media/beginners-html-finished.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-finished.msft.png":::
   完成したサイト  
:::image-end:::  

このチュートリアルの最後には、次のトピックを理解する必要があります。  

*   HTML と DOM が Web ページに表示されるコンテンツを作成する方法。  
*   DevTools Microsoft Edge HTML と DOM の変更を試す方法。  
*   HTML と DOM の違い。  

また、実際の Web サイトがあります。  サイトを使用して履歴書やブログをホストできます。  

## <a name="prerequisites"></a>前提条件  

このチュートリアルを試す前に、次の前提条件を満たしてください。  

*   HTML に慣れていない場合は、「HTML の使用を [開始する」を参照してください][MDNGettingStartedHtml]。  
*   Web ブラウザー [Microsoft Edge][MicrosoftEdgeInsider]ダウンロードします。  このチュートリアルでは、開発ツールに組み込Microsoft Edge DevTools と呼ばれる一連の web 開発Microsoft Edge。  

## <a name="set-up-your-code"></a>コードを設定する  

Glitch というオンライン コード エディターでサイトを構築します。  

1.  ソース コード [を開きます][GlitchAlluringShockIndex]。  このタブは、このチュートリアル全体 **で [エディター] タブ** と呼ばれる。  
    
    :::image type="complex" source="../media/beginners-html-setup1.msft.png" alt-text="[エディター] タブ" lightbox="../media/beginners-html-setup1.msft.png":::
       [エディター] タブ  
    :::image-end:::  
    
1.  **Alluring-shock を選択します**。  [Projectオプション] メニューが左上隅に表示されます。  
    
    :::image type="complex" source="../media/beginners-html-setup2.msft.png" alt-text="[Project オプション] メニュー" lightbox="../media/beginners-html-setup2.msft.png":::
       [Project オプション] メニュー  
    :::image-end:::  
    
1.  **[Remix Project] を選択します**。  Glitch は、編集できるプロジェクトのコピーを作成し、プロジェクトの新しい名前をランダムに生成します。  コンテンツは以前と同じです。  
    
    :::image type="complex" source="../media/beginners-html-setup3.msft.png" alt-text="リミックスされたプロジェクト" lightbox="../media/beginners-html-setup3.msft.png":::
       リミックスされたプロジェクト  
    :::image-end:::  
    
1.  このシリーズの次のチュートリアルを完了する予定の場合は、[**** サインイン] を選択し、自分のアカウントまたは Facebook アカウントで Glitch GitHubサインインします。  アカウントにサインインしない場合は、編集タブを閉じてからプロジェクトを編集できません。  
1.  [表示 **] を** 選択し、[ **新しいウィンドウ] を選択します**。  新しいタブが開き、ライブ ページが表示されます。  このタブは、このチュートリアル全体で **ライブ タブ** と呼ばれる。  
    
    :::image type="complex" source="../media/beginners-html-setup4.msft.png" alt-text="[ライブ] タブ" lightbox="../media/beginners-html-setup4.msft.png":::
       [ライブ] タブ  
    :::image-end:::  
    
## <a name="add-content"></a>コンテンツの追加  

サイトがかなり空です。  以下の手順に従って、コンテンツを追加します。  

1.  [エディター **] タブで、** に置き `<!-- You're "About Me" will go here.  -->` 換えます `<h1>About Me</h1>` 。  
    
    :::row:::
       :::column span="":::
          ```html
          ...
              ...
              <body>
                  <p> Your site!</p>
                  <main>
                      <h1>About Me</h1>
                  </main>
                  ...
              ...
          ...
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-add1.msft.png" alt-text="新しいコードが [エディター] タブで強調表示されます。" lightbox="../media/beginners-html-add1.msft.png":::
             新しいコードが [エディター] タブで強調表示されます。  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  [ライブ] タブで変更 **を表示します**。 テキストは `About Me` ページに表示されます。  要素はセクション見出しを表すので、周囲のテキストよりも `<h1>` 大きいテキスト。  Web ブラウザーは、大きなフォント サイズで見出しのスタイルを自動的に設定します。  
    
    :::image type="complex" source="../media/beginners-html-add2.msft.png" alt-text="新しい見出しがライブ タブに表示される" lightbox="../media/beginners-html-add2.msft.png":::
       新しい見出しがライブ タブに表示される  
    :::image-end:::  
    
1.  [エディター] タブ **に戻り**、下の行に `<p>I am learning HTML.  Recent accomplishments:</p>` 挿入します `<h1>About Me</h1>` 。  
    
    :::row:::
       :::column span="":::
          ```html
          ...
              ...
              <body>
                  <p> Your site!</p>
                  <main>
                      <h1>About Me</h1>
                      <p>I am learning web development.  Recent accomplishments:</p>
                  </main>
                  ...
              ...
          ...
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-add3.msft.png" alt-text="更新されたコードが [エディター] タブで強調表示されます。" lightbox="../media/beginners-html-add3.msft.png":::
             更新されたコードが [エディター] タブで強調表示されます。  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  [ライブ] タブで変更 **を表示します**。  
1.  [エディター] タブ **に戻り**、業績の一覧を追加します。  
    
    :::row:::
       :::column span="":::
          ```html
          ...
              ...
                  ...
                  <p>I am learning web development.  Recent accomplishments:</p>
                  <ul>
                      <li>Learned how to set up my code in Glitch.</li>
                      <li>Added content to my HTML.</li>
                      <li>TODO: Learn how to use Microsoft Edge DevTools to experiment with content changes.</li>
                      <li>TODO: Learn the difference between HTML and the DOM.</li>
                  </ul>
                  ...
              ...
          ...
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-add4.msft.png" alt-text="更新されたコードは、エディター タブでも強調表示されます。" lightbox="../media/beginners-html-add4.msft.png":::
             更新されたコードは、エディター タブでも強調表示されます。  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  再度、ライブ タブに **戻** り、新しいコンテンツが正しく表示されていることを確認します。  
    
    :::image type="complex" source="../media/beginners-html-add5.msft.png" alt-text="新しいリストがライブ タブに表示される" lightbox="../media/beginners-html-add5.msft.png":::
       新しいリストがライブ タブに表示される  
    :::image-end:::  
    
## <a name="experiment-with-content-changes-in-microsoft-edge-devtools"></a>DevTools でコンテンツの変更Microsoft Edgeする  

多くの HTML を含む大きなページを開発している場合は、変更を表示するために、エディター タブとライブ タブの間を何百回も行き来する必要があります。特に、ページに正確に何を置く必要があるのか分からない場合は、何百回も行き来する必要があります。  Microsoft EdgeDevTools は、ライブ タブを離れることなくコンテンツの変更を**試すのに役立ちます**。  

### <a name="learn-the-difference-between-html-and-the-dom"></a>HTML と DOM の違いを学ぶ  

DevTools からコンテンツの編集をMicrosoft Edge前に、HTML と DOM の違いを理解する必要があります。  最適な学習方法は、次の例です。  

1.  [ライブ] タブ **に移動します**。 ページの下部にテキストが `A new element!?!` 表示されます。  
    
    :::image type="complex" source="../media/beginners-html-dom1.msft.png" alt-text="ページの下部にあるテキスト A 新しい要素!?! が表示されます" lightbox="../media/beginners-html-dom1.msft.png":::
       ページの下部にテキストが `A new element!?!` 表示されます  
    :::image-end:::  
    
1.  [エディター] タブに **戻り、** テキストを探します `index.html` 。  テキストがそこには表示されない。  
    
    :::image type="complex" source="../media/beginners-html-dom2.msft.png" alt-text="謎のテキスト 新しい要素!?! は l のどこにもindex.htmはありません。" lightbox="../media/beginners-html-dom2.msft.png":::
       謎のテキスト `A new element!?!` はどこにも見つかりません `index.html`  
    :::image-end:::  
    
1.  ライブ タブに **戻り**、マウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き `A new element!?!` 、[検査] を選択 **します**。  
    
    :::image type="complex" source="../media/beginners-html-dom3.msft.png" alt-text="テキストの検査" lightbox="../media/beginners-html-dom3.msft.png":::
       テキストの検査  
    :::image-end:::  
    
    DevTools がページと一緒に開きます。  `<div>A new element!?!</div>` は青色で強調表示されます。  DevTools のこの構造は HTML のように見えますが、実際には **DOM ツリーです**。  
    
    :::image type="complex" source="../media/beginners-html-dom4.msft.png" alt-text="DevTools がページと一緒に開いている" lightbox="../media/beginners-html-dom4.msft.png":::
       DevTools がページと一緒に開いている  
    :::image-end:::  
    
ページが読み込まれると、ブラウザーは HTML を使用してページ *の初期コンテンツ* を作成します。  DOM はページの現在 *の* コンテンツを表します。時間の流中に変化する可能性があります。  HTML の下部にあるタグのために、ページに不思議なコンテンツ `<div>A new element!?!</div>` `<script src="new.js"></script>` が追加されます。  このタグを使用すると、一部の JavaScript コードが実行されます。  JavaScript の詳細については、後のチュートリアルで説明しますが、今のところは、ページの内容を変更するプログラミング言語と考えておきます。  この特定のケースでは、JavaScript コードがページ `<div>A new element!?!</div>` に追加されます。  この謎のテキストはライブ ページに表示されますが、HTML には表示されません。  

### <a name="edit-the-dom"></a>DOM の編集  

ライブ タブを離れることなくコンテンツの変更をすばやく試す場合は、DevTools を試してみてください。  

1.  DevTools で、マウス ポインターを置き、コンテキスト メニュー `Your site!` \(右クリック\) を開き **、[HTML として編集] を選択します**。  
    
    :::image type="complex" source="../media/beginners-html-edit1.msft.png" alt-text="HTML としてノードを編集する" lightbox="../media/beginners-html-edit1.msft.png":::
       HTML としてノードを編集する  
    :::image-end:::  
    
1.  以下 `<p>Your site!</p>` のコードに置き換えます。  
    
    :::row:::
       :::column span="":::
          ```html
          ...
              ...
                  ...
                  <header>
                      <p><b>Welcome to my site!</b></p>
                      <button>Download my resume</button>
                  </header>
                  ...
              ...
          ...
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-edit2.msft.png" alt-text="HTML としてノードを更新する" lightbox="../media/beginners-html-edit2.msft.png":::
             HTML としてノードを更新する  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  `Control` + `Enter` \(Windows、Linux\) または `Command` + \(macOS\) を選択して変更を保存するか、ボックスの外側 `Enter` を選択します。  変更がページのライブ ビューに自動的に表示されます。  テキストが `Your site!` 新しいコンテンツに置き換えられた。  
    
    :::image type="complex" source="../media/beginners-html-edit3.msft.png" alt-text="新しいコンテンツがページにすぐに表示される" lightbox="../media/beginners-html-edit3.msft.png":::
       新しいコンテンツがページにすぐに表示される  
    :::image-end:::  
    
このワークフローは、コンテンツの変更を試す場合にのみ使用できます。  ページを更新するか、タブを閉じると、変更は永遠に消えてしまいます。  このワークフローを使用して変更を保存する場合は、それらの変更を手動で HTML にコピーする必要があります。  次のセクションでは、DOM ツリーからコンテンツを変更する方法について説明します。  

## <a name="reorder-nodes"></a>ノードの並べ替え  

DOM ノードの順序を変更することもできます。  たとえば、Web ページでは、ナビゲーション メニューが下部の近くに表示されます。  上部に移動するには、次の方法を実行します。  

1.  `<nav>`DevTools の**DOM ツリーで**ノードを検索します。  
    
    :::image type="complex" source="../media/beginners-html-reorder1.msft.png" alt-text="ナビゲーション ノードが DevTools で青色で強調表示されている" lightbox="../media/beginners-html-reorder1.msft.png":::
       ナビゲーション ノードが DevTools で青色で強調表示されている  
    :::image-end:::  
    
1.  ノードを `<nav>` 上にドラッグして、ノードがノードの最初の子 `<body>` になります。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-reorder2.msft.png" alt-text="ナビゲーション ノードを上にドラッグする" lightbox="../media/beginners-html-reorder2.msft.png":::
             ナビゲーション ノードを上にドラッグする  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          これで `<nav>` 、ページの上部にノードが表示されます。  
          
          :::image type="complex" source="../media/beginners-html-reorder3.msft.png" alt-text="ナビゲーション ノードがページの上部にある" lightbox="../media/beginners-html-reorder3.msft.png":::
             ナビゲーション ノードがページの上部にある  
          :::image-end:::  
       :::column-end:::
   :::row-end:::  
    
### <a name="delete-a-node"></a>ノードの削除  

DOM ツリーからノードを削除することもできます。  

1.  DOM ツリー **で、** を選択します `<div>A new element!?!</div>` 。  DevTools はノードを青色で強調表示します。  
    
    :::image type="complex" source="../media/beginners-html-delete1.msft.png" alt-text="削除するノードを選択する" lightbox="../media/beginners-html-delete1.msft.png":::
       削除するノードを選択する  
    :::image-end:::  
    
1.  キーボードの `Delete` キーを選択します。  ノード `<div>A new element!?!</div>` は DOM ツリーから削除されます。  
    
    :::image type="complex" source="../media/beginners-html-delete2.msft.png" alt-text="ノードが削除されました" lightbox="../media/beginners-html-delete2.msft.png":::
       ノードが削除されました  
    :::image-end:::  
    
## <a name="copy-your-changes"></a>変更をコピーする  

もう少しで完了です。  DevTools でページにいくつかの変更を加えたが、まだソース コードに保存されていない。  

1.  ライブ タブ **を更新します**。 DOM ツリーで行った変更は消えます。  特に、テキスト `Your site!` はページの上部に戻り、テキストは `A new element!?!` 下部に戻ります。  
    
    :::image type="complex" source="../media/beginners-html-copy1.msft.png" alt-text="行った変更は消えました" lightbox="../media/beginners-html-copy1.msft.png":::
       行った変更は消えました  
    :::image-end:::  
    
1.  以下のコードをコピーします。  
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="utf-8">
            <meta http-equiv="X-UA-Compatible" content="IE=edge">
            <meta name="viewport" content="width=device-width, initial-scale=1">
        </head>
        <body>
            <header>
                <p>Welcome to my site!</p>
            </header>
            <nav>
                <ul>
                    <li><a href="/">Home</a></li>
                    <li><a href="/contact.html">Contact</a></li>
                </ul>
            </nav>
            <main>
                <h1>About Me</h1>
                <p>I am learning web development.  Recent accomplishments:</p>
                <ul>
                    <li>Learned how to set up my code in Glitch.</li>
                    <li>Added content to my HTML.</li>
                    <li>Learned how to use Microsoft Edge DevTools to experiment with content changes.</li>
                    <li>Learned the difference between HTML and the DOM.</li>
                </ul>
            </main>
        </body>
    </html>
    ```  
    
1.  [エディター] タブ **に戻り** 、ファイルの内容をコピーしたコード `index.html` に置き換えます。  
    
    :::image type="complex" source="../media/beginners-html-copy2.msft.png" alt-text="l ファイルindex.htmの外観" lightbox="../media/beginners-html-copy2.msft.png":::
       ファイルの `index.html` 外観  
    :::image-end:::  
    
## <a name="next-steps"></a>次の手順  

*   このシリーズの次のチュートリアルはじめに[CSS][DevToolsBeginnersCss]を使用して、ページのスタイルを設定し、DevTools でスタイルの変更を試Microsoft Edgeします。  
*   DOM [の詳細については、「DOM の][MDNIntroductionDom] 概要」を参照してください。  
*   Web 開発の概要 [のようなコースをチェック][CourseraIntroductionToWebDevelopment] して、より実践的な Web 開発エクスペリエンスを得る。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!--- links --->  

[DevToolsBeginnersCss]: ./css.md "初級者向け DevTools: CSS はじめにを使用|Microsoft Docs"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge Insider"  

[CourseraIntroductionToWebDevelopment]: https://www.coursera.org/learn/web-development "Web 開発の概要|Coursera"  

[GlitchAlluringShockIndex]: https://glitch.com/edit/#!/alluring-shock?path=index.html "index.html - アリング ショック |Glitch"  

[MDNGettingStartedHtml]: https://developer.mozilla.org/docs/Learn/HTML/Introduction_to_HTML/Getting_started "HTML ファイルの使用を開始|MDN"  
[MDNIntroductionDom]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM の概要|MDN"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページ [はここで見](https://developers.google.com/web/tools/chrome-devtools/beginners/html) つかり、キャ [サ][KatherineJackson] リン・ジャクソン \(Technical Writer Intern, Chrome DevTools\) によって作成されています。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
