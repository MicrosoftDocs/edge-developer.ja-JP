---
title: Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: aa9f7e96c7e379c1fe537ffba730e08990e0c20a
ms.sourcegitcommit: ecdc4287fa25a18cb4ddcaf43fcce3b396c3314c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2020
ms.locfileid: "10581818"
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



同じコードを[コンソール][DevtoolsConsoleIndex]で繰り返し実行していることがわかった場合は、代わりにスニペットとしてコードを保存することを検討してください。  スニペットは、[ [**ソース**] パネル][DevToolsSourcesPanel]で作成したスクリプトです。  このページの JavaScript のコンテキストにアクセスできるので、どのページでも実行できます。  スニペットは、 [bookmarklets][WikiBookmarklet]の代わりとなります。  
Firefox DevTools には、[書い][MDNScratchpad]というスニペットのような機能があります。  

たとえば、[**図 1**](#figure-1)では、左側の devtools ホームページと右側にあるスニペットソースコードを示しています。  

> ##### 図 1  
> スニペットを実行する前のページの外観  
> ![スニペットを実行する前のページの外観][ImageSnippetSplitScreen]  

[**図 1**](#figure-1)のスニペットソースコード:  

```javascript
console.log('Hello, Snippets!');
document.body.innerHTML = '';
var p = document.createElement('p');
p.textContent = 'Hello, Snippets!';
document.body.appendChild(p);
```  

[**図 2**](#figure-2)は、スニペットの実行後にページがどのように見えるかを示しています。  **本体の引き出し**がポップアップ表示され、スニペットのログが記録され、 `Hello, Snippets!` ページの内容が完全に変更されます。  

> ##### 図 2  
> スニペットの実行後のページの外観  
> ![スニペットの実行後のページの外観][ImageSnippetSplitScreenAfter]  

## [スニペット] ウィンドウを開く   

[**スニペット**] ウィンドウにスニペットの一覧が表示されます。  スニペットを編集するには、スニペットを [**スニペット**] ウィンドウから開く必要があります。  

> ##### 図 3  
> [**スニペット**] ウィンドウ  
> ![[スニペット] ウィンドウ][ImageSnippetsPane]  

### [スニペット] ウィンドウをマウスで開く   

1.  [**ソース**] タブをクリックして、[**ソース**] パネルを開きます。  通常、**ページ**ウィンドウは既定で開かれます。  

    > ##### 図 4  
    > 左側に**ページ**ウィンドウが開いている [**ソース**] パネル  
    > ![左側にページウィンドウが開いている [ソース] パネル][ImageSourcesPageEmpty]  

1.  [**スニペット**] タブをクリックして、[**スニペット**] ウィンドウを開きます。  スニペットオプションにアクセスするには、[その他の**タブ**] タブをクリックする必要がある場合があり ![ ][ImageMoreTabsIcon] ます**Snippets** 。  

### [スニペット] ウィンドウでコマンドメニューを開きます。   

1.  DevTools 内の任意の場所にカーソルをフォーカスします。  
1.  `Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押します。  
1.  入力を開始し `Snippets` 、[**スニペットの表示**] を選択します。次に、を押して `Enter` コマンドを実行します。  

    > ##### 図 5  
    > [**スニペットの表示**] コマンド  
    > ![[スニペットの表示] コマンド][ImageShowSnippetsSearch]  

## スニペットを作成する   

### ソースパネルを使用してスニペットを作成する   

1.  [ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。  
1.  [**新しいスニペット**] をクリックします。  
1.  スニペットの名前を入力し、を押して `Enter` 保存します。  

    > ##### 図 6  
    > スニペットに名前を付ける  
    > ![スニペットに名前を付ける][ImageSnippetName]  

### コマンドメニューを使用してスニペットを作成する   

1.  DevTools 内の任意の場所にカーソルをフォーカスします。  
1.  `Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押します。  
1.  入力を開始し `Snippet` て、[**新しいスニペットの作成**] を選択し、を押して `Enter` コマンドを実行します。  

    > ##### 図 7  
    > 新しいスニペットを作成するためのコマンド  
    > ![新しいスニペットを作成するためのコマンド][ImageCreateSnippetSearch]  

新しいスニペットにカスタム名を付ける場合は、「[スニペットの名前変更](#rename-snippets)」を参照してください。  

## スニペットを編集する   

1.  [ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。  
1.  [**スニペット**] ウィンドウで、編集するスニペットの名前をクリックして、**コードエディター**で開きます。  

    > ##### 図 8  
    > コードエディター  
    > ![コードエディター][ImageSnippetEditor]  

1.  **コードエディター**を使用して、スニペットに JavaScript を追加します。  
1.  スニペットの名前の横にアスタリスクが表示される場合は、コードが保存されていないことを意味します。 `Control` + `S` 保存するには、\ (Windows \) または `Command` + `S` \ (macOS \) を押します。  

    > ##### 図 9  
    > まだ保存されていないコードを示すスニペット名の横に表示されるアスタリスク  
    > ![まだ保存されていないコードを示すスニペット名の横に表示されるアスタリスク][ImageUnsavedSnippet]  

## スニペットの実行   

### [ソース] パネルからスニペットを実行する   

1.  [ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。  
1.  実行するスニペットの名前をクリックします。  スニペットが**コードエディター**で開きます。  
1.  [ **Run Snippet**スニペット ![ 実行スニペットの実行] をクリックする ][ImageRunSnippetIcon] か、 `Control` + `Enter` \ (Windows \) または `Command` + `Enter` \ (macOS \) を押します。  

### コマンドメニューを使用してスニペットを実行する   

1.  DevTools 内の任意の場所にカーソルをフォーカスします。  
1.  `Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押します。  
1.  文字を削除 `>` して、 `!` 実行するスニペットの名前の後に文字を入力します。  

    > ##### 図 10  
    > コマンドメニューからのスニペットの実行  
    > ![コマンドメニューからのスニペットの実行][ImageRunSnippetCommand]  

1.  を押して `Enter` スニペットを実行します。  

## スニペットの名前変更   

1.  [ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。  
1.  スニペット名を右クリックし、[**名前の変更**] を選択します。  

## スニペットを削除する   

1.  [ [**スニペット**] ウィンドウを開き](#open-the-snippets-pane)ます。  
1.  スニペット名を右クリックし、[**削除**] を選択します。  

 



<!-- image links -->  

[ImageMoreTabsIcon]: /microsoft-edge/devtools-guide-chromium/media/more-tabs-icon.msft.png  
[ImageRunSnippetIcon]: /microsoft-edge/devtools-guide-chromium/media/run-snippet-icon.msft.png  

[ImageSnippetSplitScreen]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-snippets-split-screen.msft.png "図 1: スニペットを実行する前にページがどのように表示されるか"  
[ImageSnippetSplitScreenAfter]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-snippets-split-screen-after.msft.png "図 2: スニペットの実行後のページの外観"  
[ImageSnippetsPane]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-snippets-pane.msft.png "図 3: [スニペット] ウィンドウ"  
[ImageSourcesPageEmpty]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-page-pane.msft.png "図 4: 左側にページウィンドウが開いている [ソース] パネル"  
[ImageShowSnippetsSearch]: /microsoft-edge/devtools-guide-chromium/media/javascript-search-show-snippets.msft.png "図 5: [スニペットの表示] コマンド"  
[ImageSnippetName]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-snippets-naming.msft.png "図 6: スニペットに名前を付ける"  
[ImageCreateSnippetSearch]: /microsoft-edge/devtools-guide-chromium/media/javascript-search-create-new-snippet.msft.png "図 7: 新しいスニペットを作成するためのコマンド"  
[ImageSnippetEditor]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-snippets-editor-saved.msft.png "図 8: コードエディター"  
[ImageUnsavedSnippet]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-snippets-editor-unsaved.msft.png "図 9: スニペット名の横に表示されるアスタリスク。まだ保存されていないコードを示します。"  
[ImageRunSnippetCommand]: /microsoft-edge/devtools-guide-chromium/media/javascript-search-run-command.msft.png "図 10: コマンドメニューからスニペットを実行する"  

<!-- links -->  

[DevtoolsConsoleIndex]: ../console/index.md "本体の概要"  
[DevToolsSourcesPanel]: ../sources.md "ソースパネルの概要"  

[MDNScratchpad]: https://developer.mozilla.org/docs/Tools/Scratchpad "書い |MDN"  
[WikiBookmarklet]: https://en.wikipedia.org/wiki/Bookmarklet "Bookmarklet-Wikipedia"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
