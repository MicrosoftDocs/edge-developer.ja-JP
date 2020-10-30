---
description: スニペットは、Microsoft Edge DevTools のソースツールで作成および実行できる小さなスクリプトです。  どの web ページからでも、リソースにアクセスして実行することができます。  スニペットを実行すると、現在開いている web ページのコンテキストから実行されます。
title: Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 3542243f7fa886865ced47d47991cd9b11001e2e
ms.sourcegitcommit: 9dcaf598f3930bcfab9f93ff63463beb98274de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "11145121"
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

# Microsoft Edge DevTools を使用して、任意の web ページで JavaScript のスニペットを実行します。  

[コンソール][DevtoolsConsoleIndex]で同じコードを繰り返し実行する場合は、代わりにスニペットとしてコードを保存することを検討してください。  スニペットは、 [ソース][DevToolsSourcesTool] ツールで作成したスクリプトです。  スニペットは、web ページの JavaScript コンテキストにアクセスできます。また、スニペットはどの web ページでも実行できます。  ほとんどの web ページブロックのセキュリティ設定では、スニペットで他のスクリプトを読み込むことができません。  そのため、すべてのコードを1つのファイルに含める必要があります。  

スニペットは、 [bookmarklets][WikiBookmarklet] の代わりとなるものです。スニペットは、devtools でのみ実行され、URL の許容される長さに制限されないという違いがあります。  

スニペットの使用は、サードパーティの web ページでいくつかの項目を変更する優れた方法です。  スニペットのコードの変更は、現在の web ページに追加され、同じコンテキストで実行されます。  Web ページの既存のコードを変更する方法について詳しくは、[ [上書き][DevtoolsJavascriptOverrides]] に移動してください。  

:::row:::
   :::column span="":::
      たとえば、次の図は、左側の DevTools ホームページと右側にあるスニペットソースコードを示しています。  
      
      :::image type="complex" source="../media/javascript-sources-snippets-split-screen.msft.png" alt-text="スニペットを実行する前に" lightbox="../media/javascript-sources-snippets-split-screen.msft.png":::
         スニペットを実行する前の web ページ  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      スニペットを実行する前の web ページのスニペットソースコード。  
      
      ```javascript
      console.log('Hello, Snippets!');
      document.body.innerHTML = '';
      var p = document.createElement('p');
      p.textContent = 'Hello, Snippets!';
      document.body.appendChild(p);
      ```
   :::column-end:::
:::row-end:::  

次の図は、スニペットを実行した後に web ページが表示されることを示しています。  **本体の引き出し**がポップアップ表示され、スニペットがログに記録され、 `Hello, Snippets!` web ページの内容が完全に変更されます。  

:::image type="complex" source="../media/javascript-sources-snippets-split-screen-after.msft.png" alt-text="スニペットを実行する前に" lightbox="../media/javascript-sources-snippets-split-screen-after.msft.png":::
   スニペットを実行した後の web ページ  
:::image-end:::  

## [スニペット] ウィンドウを開く  

[ **スニペット** ] ウィンドウにスニペットの一覧が表示されます。  スニペットを編集するには、スニペットを [ **スニペット** ] ウィンドウから開く必要があります。  

:::image type="complex" source="../media/javascript-sources-snippets-pane.msft.png" alt-text="スニペットを実行する前に" lightbox="../media/javascript-sources-snippets-pane.msft.png":::
   [ **スニペット** ] ウィンドウ  
:::image-end:::  

### [スニペット] ウィンドウをマウスで開く  

1.  [ **ソース** ] タブを選択して、 **ソース** ツールを開きます。  通常、 **ページ** ウィンドウは既定で開かれます。  
    
    :::image type="complex" source="../media/javascript-sources-page-pane.msft.png" alt-text="スニペットを実行する前に" lightbox="../media/javascript-sources-page-pane.msft.png":::
       左側に**ページ**ウィンドウが表示された**ソース**ツール  
    :::image-end:::  
    
1.  [ **スニペット** ] タブを選択して、[ **スニペット** ] ウィンドウを開きます。  [スニペット] オプションにアクセスするには、[**その他のタブ**] ([ ![ その他のタブ \]) を選択する必要がある場合があり ][ImageMoreTabsIcon] ます。 **Snippets**  
    
### [スニペット] ウィンドウでコマンドメニューを開きます。  

1.  DevTools 内の任意の場所にカーソルを置きます。  
1.  `Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows, Linux \) または `Command` + `Shift` + `P` \ (macOS \) を選択します。  
1.  入力し `Snippets` 、[ **スニペットの表示**] を選択して、コマンドを実行し `Enter` ます。  
    
    :::image type="complex" source="../media/javascript-search-show-snippets.msft.png" alt-text="スニペットを実行する前に" lightbox="../media/javascript-search-show-snippets.msft.png":::
       [ **スニペットの表示** ] コマンド  
    :::image-end:::  
    
## スニペットを作成する  

### ソースパネルを使用してスニペットを作成する  

1.  [ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。  
1.  [ **新しいスニペット**] を選びます。  
1.  スニペットの名前を入力し、[ `Enter` 保存] を選択します。  
    
    :::image type="complex" source="../media/javascript-sources-snippets-naming.msft.png" alt-text="スニペットを実行する前に" lightbox="../media/javascript-sources-snippets-naming.msft.png":::
       スニペットに名前を指定する  
    :::image-end:::  
    
### コマンドメニューを使用してスニペットを作成する  

1.  DevTools 内の任意の場所にカーソルを置きます。  
1.  `Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows, Linux \) または `Command` + `Shift` + `P` \ (macOS \) を選択します。  
1.  「 `Snippet` **新規スニペットの作成**」を選択し、 `Enter` コマンドを実行します。  
    
    :::image type="complex" source="../media/javascript-search-create-new-snippet.msft.png" alt-text="スニペットを実行する前に" lightbox="../media/javascript-search-create-new-snippet.msft.png":::
       新しいスニペットを作成するためのコマンド  
    :::image-end:::  
    
新しいスニペットの名前をカスタム名に変更するには、[スニペット名の [変更](#rename-snippets)] に移動します。  

## スニペットを編集する  

1.  [ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。  
1.  [ **スニペット** ] ウィンドウで、編集するスニペットの名前を選びます。  **コードエディター**で開きます。  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-saved.msft.png" alt-text="スニペットを実行する前に" lightbox="../media/javascript-sources-snippets-editor-saved.msft.png":::
       **コードエディター**  
    :::image-end:::  
    
1.  **コードエディター**を使用して、スニペットに JavaScript を追加します。  
1.  スニペットの名前の横にアスタリスクが表示される場合は、コードが保存されていないことを意味します。  `Control` + `S` 保存するには、\ (Windows、Linux \) または `Command` + `S` \ (macOS \) を選択します。  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-unsaved.msft.png" alt-text="スニペットを実行する前に" lightbox="../media/javascript-sources-snippets-editor-unsaved.msft.png":::
       スニペット名の横にあるアスタリスクは、保存されていないコードを示します。  
    :::image-end:::  
    
## スニペットの実行  

### [ソース] パネルからスニペットを実行する  

1.  [ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。  
1.  実行するスニペットの名前を選びます。  スニペットが **コードエディター**で開きます。  
1.  [ **Run スニペット**\ ( ![ スニペットを実行し ][ImageRunSnippetIcon] ます)] または [\ ( `Control` + `Enter` Windows、Linux \)] または [ `Command` + `Enter` \ (macOS \)] を選びます。  
    
### コマンドメニューを使用してスニペットを実行する  

1.  DevTools 内の任意の場所にカーソルを置きます。  
1.  `Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows, Linux \) または `Command` + `Shift` + `P` \ (macOS \) を選択します。  
1.  文字を削除 `>` して、 `!` 実行するスニペットの名前の後に文字を入力します。  
    
    :::image type="complex" source="../media/javascript-search-run-command.msft.png" alt-text="スニペットを実行する前に" lightbox="../media/javascript-search-run-command.msft.png":::
       **コマンドメニュー**からのスニペットの実行  
    :::image-end:::  
    
1.  `Enter`スニペットを実行する場合に選択します。  

## スニペットの名前変更  

1.  [ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。  
1.  スニペット名の上にカーソルを置いてコンテキストメニューを開き (\ [\] を右クリックし)、[ **名前の変更**] を選択します。  
    
## スニペットを削除する  

1.  [ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。  
1.  スニペット名の上にカーソルを置いて、コンテキストメニューを開き (\ [\] を右クリックし)、[ **削除**] を選択します。  
    
## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageMoreTabsIcon]: ../media/more-tabs-icon.msft.png  
[ImageRunSnippetIcon]: ../media/run-snippet-icon.msft.png  

<!-- links -->  

[DevtoolsConsoleIndex]: ../console/index.md "本体の概要 |Microsoft ドキュメント"  
[DevToolsSourcesTool]: ../sources.md "ソースツールの概要 |Microsoft ドキュメント"  
[DevtoolsJavascriptOverrides]: ./overrides.md "Overrides |Microsoft ドキュメント"  

[MDNScratchpad]: https://developer.mozilla.org/docs/Tools/Scratchpad "書い |MDN"  
[WikiBookmarklet]: https://en.wikipedia.org/wiki/Bookmarklet "Bookmarklet |Wikipedia"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
