---
description: スニペットは、Microsoft Edge DevTools のソースパネル内で作成および実行できる小さなスクリプトです。  どのページからでもアクセスして実行できます。  スニペットを実行すると、現在開いているページのコンテキストから実行されます。
title: Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: e353da76a5c354d834b69708c8a8c9e8dbdf9934
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11124741"
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

# Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。  

同じコードを [コンソール][DevtoolsConsoleIndex] で繰り返し実行していることがわかった場合は、代わりにスニペットとしてコードを保存することを検討してください。  スニペットは、[ [ソース][DevToolsSourcesPanel] ] パネルで作成したスクリプトです。  このページの JavaScript のコンテキストにアクセスできるので、どのページでも実行できます。  スニペットは、 [bookmarklets][WikiBookmarklet]の代わりとなります。  
Firefox DevTools には、 [書い][MDNScratchpad]というスニペットのような機能があります。  

たとえば、次の図は、左側の DevTools ホームページと右側にあるスニペットソースコードを示しています。  

:::image type="complex" source="../media/javascript-sources-snippets-split-screen.msft.png" alt-text="スニペットを実行する前のページの外観" lightbox="../media/javascript-sources-snippets-split-screen.msft.png":::
   スニペットを実行する前のページの外観  
:::image-end:::  

前の図のスニペットソースコード。  

```javascript
console.log('Hello, Snippets!');
document.body.innerHTML = '';
var p = document.createElement('p');
p.textContent = 'Hello, Snippets!';
document.body.appendChild(p);
```  

次の図では、スニペットを実行した後にページが表示されます。  **本体の引き出し**がポップアップ表示され、スニペットのログが記録され、 `Hello, Snippets!` ページの内容が完全に変更されます。  

:::image type="complex" source="../media/javascript-sources-snippets-split-screen-after.msft.png" alt-text="スニペットを実行する前のページの外観" lightbox="../media/javascript-sources-snippets-split-screen-after.msft.png":::
   スニペットの実行後のページの外観  
:::image-end:::  

## [スニペット] ウィンドウを開く  

[ **スニペット** ] ウィンドウにスニペットの一覧が表示されます。  スニペットを編集するには、スニペットを [ **スニペット** ] ウィンドウから開く必要があります。  

:::image type="complex" source="../media/javascript-sources-snippets-pane.msft.png" alt-text="スニペットを実行する前のページの外観" lightbox="../media/javascript-sources-snippets-pane.msft.png":::
   [ **スニペット** ] ウィンドウ  
:::image-end:::  

### [スニペット] ウィンドウをマウスで開く  

1.  [ **ソース** ] タブをクリックして、[ **ソース** ] パネルを開きます。  通常、 **ページ** ウィンドウは既定で開かれます。  
    
    :::image type="complex" source="../media/javascript-sources-page-pane.msft.png" alt-text="スニペットを実行する前のページの外観" lightbox="../media/javascript-sources-page-pane.msft.png":::
       左側に**ページ**ウィンドウが開いている [**ソース**] パネル  
    :::image-end:::  
    
1.  [ **スニペット** ] タブをクリックして、[ **スニペット** ] ウィンドウを開きます。  スニペットオプションにアクセスするには、[**その他のタブ**] ([その他] タブ) を選択する必要がある場合があり ![ ][ImageMoreTabsIcon] ます。 **Snippets**  
    
### [スニペット] ウィンドウでコマンドメニューを開きます。  

1.  DevTools 内の任意の場所にカーソルをフォーカスします。  
1.  `Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows, Linux \) または `Command` + `Shift` + `P` \ (macOS \) を選択します。  
1.  入力を開始し `Snippets` 、[ **スニペットの表示**] を選択して、コマンドを `Enter` 実行します。  
    
    :::image type="complex" source="../media/javascript-search-show-snippets.msft.png" alt-text="スニペットを実行する前のページの外観" lightbox="../media/javascript-search-show-snippets.msft.png":::
       [ **スニペットの表示** ] コマンド  
    :::image-end:::  
    
## スニペットを作成する  

### ソースパネルを使用してスニペットを作成する  

1.  [ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。  
1.  [ **新しいスニペット**] を選びます。  
1.  スニペットの名前を入力し、[ `Enter` 保存] を選択します。  
    
    :::image type="complex" source="../media/javascript-sources-snippets-naming.msft.png" alt-text="スニペットを実行する前のページの外観" lightbox="../media/javascript-sources-snippets-naming.msft.png":::
       スニペットに名前を指定する  
    :::image-end:::  
    
### コマンドメニューを使用してスニペットを作成する  

1.  DevTools 内の任意の場所にカーソルをフォーカスします。  
1.  `Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows, Linux \) または `Command` + `Shift` + `P` \ (macOS \) を選択します。  
1.  入力を開始し `Snippet` 、[ **新しいスニペットの作成**] を選択し `Enter` て、コマンドを実行します。  
    
    :::image type="complex" source="../media/javascript-search-create-new-snippet.msft.png" alt-text="スニペットを実行する前のページの外観" lightbox="../media/javascript-search-create-new-snippet.msft.png":::
       新しいスニペットを作成するためのコマンド  
    :::image-end:::  
    
新しいスニペットにカスタム名を付ける場合は、「 [スニペットの名前変更](#rename-snippets) 」を参照してください。  

## スニペットを編集する  

1.  [ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。  
1.  [ **スニペット** ] ウィンドウで、編集するスニペットの名前をクリックして、 **コードエディター**で開きます。  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-saved.msft.png" alt-text="スニペットを実行する前のページの外観" lightbox="../media/javascript-sources-snippets-editor-saved.msft.png":::
       **コードエディター**  
    :::image-end:::  
    
1.  **コードエディター**を使用して、スニペットに JavaScript を追加します。  
1.  スニペットの名前の横にアスタリスクが表示される場合は、コードが保存されていないことを意味します。 `Control` + `S` 保存するには、\ (Windows、Linux \) または `Command` + `S` \ (macOS \) を選択します。  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-unsaved.msft.png" alt-text="スニペットを実行する前のページの外観" lightbox="../media/javascript-sources-snippets-editor-unsaved.msft.png":::
       まだ保存されていないコードを示すスニペット名の横に表示されるアスタリスク  
    :::image-end:::  
    
## スニペットの実行  

### [ソース] パネルからスニペットを実行する  

1.  [ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。  
1.  実行するスニペットの名前をクリックします。  スニペットが **コードエディター**で開きます。  
1.  [ **Run スニペット**\ ( ![ スニペットを実行し ][ImageRunSnippetIcon] ます)] または [\ ( `Control` + `Enter` Windows、Linux \)] または [ `Command` + `Enter` \ (macOS \)] を選びます。  
    
### コマンドメニューを使用してスニペットを実行する  

1.  DevTools 内の任意の場所にカーソルをフォーカスします。  
1.  `Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows, Linux \) または `Command` + `Shift` + `P` \ (macOS \) を選択します。  
1.  文字を削除 `>` して、 `!` 実行するスニペットの名前の後に文字を入力します。  
    
    :::image type="complex" source="../media/javascript-search-run-command.msft.png" alt-text="スニペットを実行する前のページの外観" lightbox="../media/javascript-search-run-command.msft.png":::
       **コマンドメニュー**からのスニペットの実行  
    :::image-end:::  
    
1.  `Enter`スニペットを実行する場合に選択します。  

## スニペットの名前変更  

1.  [ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。  
1.  スニペット名を右クリックし、[ **名前の変更**] を選択します。  
    
## スニペットを削除する  

1.  [ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。  
1.  スニペット名を右クリックし、[ **削除**] を選択します。  
    
## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageMoreTabsIcon]: ../media/more-tabs-icon.msft.png  
[ImageRunSnippetIcon]: ../media/run-snippet-icon.msft.png  

<!-- links -->  

[DevtoolsConsoleIndex]: ../console/index.md "本体の概要 |Microsoft ドキュメント"  
[DevToolsSourcesPanel]: ../sources.md "ソースパネルの概要 |Microsoft ドキュメント"  

[MDNScratchpad]: https://developer.mozilla.org/docs/Tools/Scratchpad "書い |MDN"  
[WikiBookmarklet]: https://en.wikipedia.org/wiki/Bookmarklet "Bookmarklet-Wikipedia"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
