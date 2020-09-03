---
description: HTML と DOM を使ってみる
title: '初心者向けの DevTools: HTML と DOM の使用を開始する'
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 182885cb97dbd1672d33b257569b0d841466985b
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993283"
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

# 初心者向けの DevTools: HTML と DOM の使用を開始する   

これは、web 開発の基礎について説明する一連のチュートリアルの最初のものです。  また、生産性を向上させるための、Microsoft Edge DevTools という web 開発者ツールのセットについても説明します。  

この特定のチュートリアルでは、HTML と DOM について説明します。  HTML は、web 開発の中核となるテクノロジの1つです。  これは、web ページの構造とコンテンツを制御するための言語です。  DOM は web ページの構造とコンテンツにも関連していますが、詳細については後で説明します。  

## 目標   

独自の web サイトを実際に構築することで、web 開発について学習します。  *初心者向けの Devtools*ですべてのチュートリアルを完了すると、次の図のように完成したサイトが表示されます。  

:::image type="complex" source="../media/beginners-html-finished.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-finished.msft.png":::
   完成したサイト  
:::image-end:::  

このチュートリアルを終了すると、次のことがわかります。  

*   HTML と DOM は、web ページに表示されるコンテンツを作成する方法について説明します。  
*   Microsoft Edge の DevTools を使って、HTML と DOM の変更を試す方法について説明します。  
*   HTML と DOM の違い。  

実際の web サイトも用意されています。  このサイトを使って、履歴書やブログを主催することができます。  

## 前提条件   

このチュートリアルを実行する前に、次の前提条件を完了してください。  

*   HTML に慣れていない場合は、「 [html の概要][MDNGettingStartedHtml]」を参照してください。  
*   [Microsoft Edge][MicrosoftEdgeInsider] web ブラウザーをダウンロードします。  このチュートリアルでは、microsoft edge DevTools と呼ばれる web 開発ツールのセットを使用して、Microsoft Edge に組み込まれています。  

## コードを設定する   

サイトは、"エラー" と呼ばれるオンラインコードエディターで作成します。  

1.  [ソースコード][GlitchAlluringShockIndex]を開きます。  このタブは、このチュートリアル全体で [ **エディター] タブ** と呼ばれます。  
    
    :::image type="complex" source="../media/beginners-html-setup1.msft.png" alt-text="[エディター] タブ" lightbox="../media/beginners-html-setup1.msft.png":::
       [エディター] タブ  
    :::image-end:::  
    
1.  [ **Alluring-ショック] を**クリックします。  [プロジェクトのオプション] メニューが、左上隅に表示されます。  
    
    :::image type="complex" source="../media/beginners-html-setup2.msft.png" alt-text="[プロジェクトのオプション] メニュー" lightbox="../media/beginners-html-setup2.msft.png":::
       [プロジェクトのオプション] メニュー  
    :::image-end:::  
    
1.  [ **Remix Project**] をクリックします。  エラー編集可能なプロジェクトのコピーを作成して、プロジェクトの新しい名前をランダムに生成します。  コンテンツは以前と同じです。  
    
    :::image type="complex" source="../media/beginners-html-setup3.msft.png" alt-text="Remixed プロジェクト" lightbox="../media/beginners-html-setup3.msft.png":::
       Remixed プロジェクト  
    :::image-end:::  
    
1.  このシリーズの次のチュートリアルを実行する場合は、[ **サインイン** ] をクリックして、GitHub または Facebook アカウントでエラーにサインインします。  サインインしない場合は、[編集] タブを閉じると、このプロジェクトを編集できなくなります。  
1.  [ **表示** ] をクリックして、 **新しいウィンドウで**を選択します。  新しいタブが開き、実際のページが表示されます。  このタブは、このチュートリアル全体で「 **ライブ」タブ** と呼ばれます。  
    
    :::image type="complex" source="../media/beginners-html-setup4.msft.png" alt-text="[ライブ] タブ" lightbox="../media/beginners-html-setup4.msft.png":::
       [ライブ] タブ  
    :::image-end:::  
    
## コンテンツを追加する   

サイトは非常に空です。  コンテンツを追加するには、次の手順を実行します。  

1.  [ **エディター] タブ**で、を `<!-- You're "About Me" will go here.  -->` に置き換え `<h1>About Me</h1>` ます。  
    
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
          :::image type="complex" source="../media/beginners-html-add1.msft.png" alt-text="[エディター] タブの新しいコードが強調表示されている" lightbox="../media/beginners-html-add1.msft.png":::
             [エディター] タブの新しいコードが強調表示されている  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  [ **ライブ] タブ**で変更内容を表示します。 テキスト `About Me` がページに表示されます。  要素はセクションの見出しを表すため、テキストの残りの部分よりも大きくなり `<h1>` ます。  Web ブラウザーでは、大きなフォントサイズで見出しが自動的にスタイル設定されます。  
    
    :::image type="complex" source="../media/beginners-html-add2.msft.png" alt-text="新しい見出しが [ライブ] タブに表示される" lightbox="../media/beginners-html-add2.msft.png":::
       新しい見出しが [ライブ] タブに表示される  
    :::image-end:::  
    
1.  [ **エディター] タブ**に戻り、 `<p>I am learning HTML.  Recent accomplishments:</p>` 配置した位置の下の行に挿入 `<h1>About Me</h1>` します。  
    
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
          :::image type="complex" source="../media/beginners-html-add3.msft.png" alt-text="[エディター] タブの新しいコードが強調表示されている" lightbox="../media/beginners-html-add3.msft.png":::
             [エディター] タブの新しいコードが強調表示されている  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  [ **ライブ] タブ**で自分の変更内容を確認します。  
1.  [ **エディター] タブ**に戻り、実績のリストを追加します。  
    
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
          :::image type="complex" source="../media/beginners-html-add4.msft.png" alt-text="[エディター] タブの新しいコードが強調表示されている" lightbox="../media/beginners-html-add4.msft.png":::
             [エディター] タブの新しいコードが強調表示されている  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  この場合も、[ **ライブ] タブ** に戻り、新しいコンテンツが正しく表示されていることを確認してください。  
    
    :::image type="complex" source="../media/beginners-html-add5.msft.png" alt-text="[ライブ] タブに新しいリストが表示される" lightbox="../media/beginners-html-add5.msft.png":::
       [ライブ] タブに新しいリストが表示される  
    :::image-end:::  
    
## Microsoft Edge DevTools でのコンテンツの変更を試す   

大量の HTML を含む大きなページを開発している場合は、変更を確認するために、[エディター] タブと [ライブ] タブの間を前後に移動することが必要になることがあります。特に、ページに何を入力したかがわからない場合は、どうすればよいですか。  Microsoft Edge の DevTools を使うと、ライブタブを残したまま、コンテンツの変更を試すことができます。  

### HTML と DOM の違いについて   

Microsoft Edge DevTools からコンテンツの編集を開始する前に、HTML と DOM の違いについて理解しておくと役立ちます。  次のような方法で学ぶことができます。  

1.  [ **ライブ] タブ**に移動します。 ページの下部にテキストが表示され `A new element!?!` ます。  
    
    :::image type="complex" source="../media/beginners-html-dom1.msft.png" alt-text="ページの下部に新しい要素としてテキストを入力!?! 表示可能" lightbox="../media/beginners-html-dom1.msft.png":::
       ページの下部に新しい要素としてテキストを入力!?! 表示可能  
    :::image-end:::  
    
1.  [ **エディター] タブ** に戻り、のテキストを検索し `index.html` ます。  そうではありません。  
    
    :::image type="complex" source="../media/beginners-html-dom2.msft.png" alt-text="新しい要素の謎のテキスト!?! index.html で見つからない" lightbox="../media/beginners-html-dom2.msft.png":::
       謎のテキスト `A new element!?!` が見つからない `index.html`  
    :::image-end:::  
    
1.  [ **ライブ] タブ**に戻り、右クリックし `A new element!?!` て [ **検査**] を選択します。  
    
    :::image type="complex" source="../media/beginners-html-dom3.msft.png" alt-text="一部のテキストを検査する" lightbox="../media/beginners-html-dom3.msft.png":::
       一部のテキストを検査する  
    :::image-end:::  
    
    DevTools はページの横に表示されます。  `<div>A new element!?!</div>` が青色で強調表示されています。  DevTools のこの構造は HTML と同じような外観ですが、実際には **DOM ツリー**です。  
    
    :::image type="complex" source="../media/beginners-html-dom4.msft.png" alt-text="ページの横に DevTools が開かれている" lightbox="../media/beginners-html-dom4.msft.png":::
       ページの横に DevTools が開かれている  
    :::image-end:::  
    
ページが読み込まれると、ブラウザーは HTML を使ってページの *最初* のコンテンツを作成します。  DOM は、時間の経過と共に変化する可能性があるページの *現在* のコンテンツを表します。  `<div>A new element!?!</div>`HTML の下部にタグがあるため、謎のコンテンツがページに追加され `<script src="new.js"></script>` ます。  このタグを使うと、JavaScript コードが実行されます。  JavaScript の詳細については、後のチュートリアルで説明しますが、ここでは、ページのコンテンツを変更できるプログラミング言語と考えることができます。  この例では、JavaScript コードが `<div>A new element!?!</div>` ページに追加されています。  そのため、この謎のテキストは、実際のページには表示されますが、HTML では表示されません。  

### DOM を編集する   

ライブタブを閉じずに、コンテンツの変更をすばやく試す場合は、DevTools をお試しください。  

1.  DevTools で右クリックし、 `Your site!` [ **HTML として編集**] を選択します。  
    
    :::image type="complex" source="../media/beginners-html-edit1.msft.png" alt-text="HTML としてのノードの編集" lightbox="../media/beginners-html-edit1.msft.png":::
       HTML としてのノードの編集  
    :::image-end:::  
    
1.  `<p>Your site!</p>`以下のコードで置き換えます。  
    
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
          :::image type="complex" source="../media/beginners-html-edit2.msft.png" alt-text="HTML としてのノードの編集" lightbox="../media/beginners-html-edit2.msft.png":::
             HTML としてのノードの編集  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  `Control` + `Enter` \ (Windows \) または `Command` + `Enter` \ (macOS \) を押して変更内容を保存するか、ボックスの外側をクリックします。  変更は、ページのライブビューに自動的に表示されます。  テキスト `Your site!` が新しいコンテンツに置き換えられました。  
    
    :::image type="complex" source="../media/beginners-html-edit3.msft.png" alt-text="ページ上の新しいコンテンツがすぐに表示される" lightbox="../media/beginners-html-edit3.msft.png":::
       ページ上の新しいコンテンツがすぐに表示される  
    :::image-end:::  
    
このワークフローは、コンテンツの変更を試す場合にのみ適しています。  ページを再度読み込むか、タブを閉じると、変更内容は永久に失われます。  このワークフローを使用していて、変更を保存する場合は、それらの変更を手動で HTML にコピーする必要があります。  次のいくつかのセクションでは、DOM ツリーからコンテンツを変更するその他の方法について説明します。  

## ノードの順序を変更する   

DOM ノードの順序を変更することもできます。  たとえば、web ページでは、ナビゲーションメニューは一番下に近い場所にあります。  一番上に移動するには:  

1.  `<nav>`DevTools の**DOM ツリー**でノードを見つけます。  
    
    :::image type="complex" source="../media/beginners-html-reorder1.msft.png" alt-text="DevTools でナビゲーションノードが青色で強調表示されている" lightbox="../media/beginners-html-reorder1.msft.png":::
       DevTools でナビゲーションノードが青色で強調表示されている  
    :::image-end:::  
    
1.  ノードを `<nav>` 一番上にドラッグして、ノードの下にある最初の子にし `<body>` ます。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-reorder2.msft.png" alt-text="ナビゲーションノードを一番上にドラッグする" lightbox="../media/beginners-html-reorder2.msft.png":::
             ナビゲーションノードを一番上にドラッグする  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          `<nav>`これで、ノードがページの上部に表示されるようになりました。  
          
          :::image type="complex" source="../media/beginners-html-reorder3.msft.png" alt-text="ナビゲーションノードはページの一番上にあります" lightbox="../media/beginners-html-reorder3.msft.png":::
             ナビゲーションノードはページの一番上にあります  
          :::image-end:::  
       :::column-end:::
   :::row-end:::  
    
### ノードを削除する   

DOM ツリーからノードを削除することもできます。  

1.  **DOM ツリー**でをクリックし `<div>A new element!?!</div>` ます。  DevTools は、ノード青色を強調表示します。  
    
    :::image type="complex" source="../media/beginners-html-delete1.msft.png" alt-text="削除するノードの選択" lightbox="../media/beginners-html-delete1.msft.png":::
       削除するノードの選択  
    :::image-end:::  
    
1.  キーボードの `Delete` キーを押します。  `<div>A new element!?!</div>`ノードが DOM ツリーから削除されます。  
    
    :::image type="complex" source="../media/beginners-html-delete2.msft.png" alt-text="ノードが削除されました" lightbox="../media/beginners-html-delete2.msft.png":::
       ノードが削除されました  
    :::image-end:::  
    
## 変更内容をコピーする   

まもなく完了です。  DevTools でページにいくつか変更を加えましたが、ソースコードにはまだ保存されていません。  

1.  **[ライブ] タブ**を更新します。 DOM ツリーで行った変更が非表示になります。  特に、テキストは `Your site!` ページの一番上に表示され、テキストは `A new element!?!` 下に戻ります。  
    
    :::image type="complex" source="../media/beginners-html-copy1.msft.png" alt-text="行った変更内容が失われる" lightbox="../media/beginners-html-copy1.msft.png":::
       行った変更内容が失われる  
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
    
1.  [ **エディター] タブ** に戻り、ファイルの内容を `index.html` コピーしたコードに置き換えます。  
    
    :::image type="complex" source="../media/beginners-html-copy2.msft.png" alt-text="index.html ファイルの外観" lightbox="../media/beginners-html-copy2.msft.png":::
       ファイルの `index.html` 外観  
    :::image-end:::  
    
## 次のステップ   

*   このシリーズの次のチュートリアルでは、「 [CSS の使用を開始][DevToolsBeginnersCss]する」を参照して、ページのスタイルを作成する方法と、Microsoft Edge devtools でスタイルの変更を試す方法について説明します。  
*   DOM の詳細について [は、「dom の概要][MDNIntroductionDom] 」を参照してください。  
*   Web [開発の概要][CourseraIntroductionToWebDevelopment] など、実践的な web 開発環境を実現するコースをご覧ください。  

<!--- links --->  

[DevToolsBeginnersCss]: ./css.md "初心者向けの DevTools: CSS の使用を開始する |Microsoft ドキュメント"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge Insider"  

[CourseraIntroductionToWebDevelopment]: https://www.coursera.org/learn/web-development "Web 開発の概要 |Coursera"  

[GlitchAlluringShockIndex]: https://glitch.com/edit/#!/alluring-shock?path=index.html "index.html-alluring-ショック |故障"  

[MDNGettingStartedHtml]: https://developer.mozilla.org/docs/Learn/HTML/Introduction_to_HTML/Getting_started "HTML の概要 |MDN"  
[MDNIntroductionDom]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM の概要 |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/beginners/html) にあり、 [Katherine Jackson][KatherineJackson] \ (テクニカルライターインターン、Chrome devtools) によって作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
