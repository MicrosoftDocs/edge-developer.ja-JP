---
description: スニペットは、Microsoft Edge DevTools の Sources ツール内で作成して実行できる小さなスクリプトです。  任意の Web ページからリソースにアクセスして実行できます。  スニペットを実行すると、現在開いている Web ページのコンテキストから実行されます。
title: Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 89b028177016a9194a67bbbe44d08572e5755f95
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230958"
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

# Microsoft Edge DevTools を使用して任意の Web ページで JavaScript のスニペットを実行する  

コンソールで同じコードを繰り返 [し実行][DevtoolsConsoleIndex] している場合は、コードをスニペットとして保存してください。  スニペットは、ソース ツールで作成 [するスクリプト][DevToolsSourcesTool] です。  スニペットは Web ページの JavaScript コンテキストにアクセスできます。スニペットは任意の Web ページで実行できます。  ほとんどの Web ページのセキュリティ設定では、スニペット内の他のスクリプトの読み込みがブロックされます。  このため、すべてのコードを 1 つのファイルに含める必要があります。  

スニペットは、スニペットが[][WikiBookmarklet]DevTools でのみ実行される点が異なるブックマークレットに代わる方法であり、URL の許容される長さに限定されません。  

スニペットの使用は、サード パーティの Web ページでいくつかの変更を行う優れた方法です。  スニペットのコード変更は現在の Web ページに追加され、同じコンテキストで実行されます。  Web ページの既存のコードを変更する方法の詳細については、[上書き] に [移動します][DevtoolsJavascriptOverrides]。  

:::row:::
   :::column span="":::
      たとえば、次の図では、左側の DevTools ホームページと、いくつかのスニペット ソース コードを右側に示しています。  
      
      :::image type="complex" source="../media/javascript-sources-snippets-split-screen.msft.png" alt-text="スニペットを実行する前" lightbox="../media/javascript-sources-snippets-split-screen.msft.png":::
         スニペットを実行する前の Web ページ  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      スニペットを実行する前の Web ページのスニペット ソース コード。  
      
      ```javascript
      console.log('Hello, Snippets!');
      document.body.innerHTML = '';
      var p = document.createElement('p');
      p.textContent = 'Hello, Snippets!';
      document.body.appendChild(p);
      ```
   :::column-end:::
:::row-end:::  

次の図では、スニペットの実行後に Web ページが表示されます。  コンソール **ドロワー** が表示され、スニペットによってログに記録されるメッセージが表示され、Web ページの内容が `Hello, Snippets!` 完全に変更されます。  

:::image type="complex" source="../media/javascript-sources-snippets-split-screen-after.msft.png" alt-text="スニペットの実行後の Web ページ" lightbox="../media/javascript-sources-snippets-split-screen-after.msft.png":::
   スニペットの実行後の Web ページ  
:::image-end:::  

## [スニペット] ウィンドウを開く  

[ **スニペット] ウィンドウ** には、スニペットが一覧表示されます。  スニペットを編集する場合は、[スニペット] ウィンドウからスニペットを **開く必要** があります。  

:::image type="complex" source="../media/javascript-sources-snippets-pane.msft.png" alt-text="[スニペット] ウィンドウ" lightbox="../media/javascript-sources-snippets-pane.msft.png":::
   [ **スニペット]** ウィンドウ  
:::image-end:::  

### マウスを使用して [スニペット] ウィンドウを開く  

1.  [ソース **] タブを** 選択して、ソース **ツールを開** きます。  通常 **、ページ** ウィンドウは既定で開きます。  
    
    :::image type="complex" source="../media/javascript-sources-page-pane.msft.png" alt-text="左側に [ページ] ウィンドウが開いているソース ツール" lightbox="../media/javascript-sources-page-pane.msft.png":::
       左側 **にページ** ウィンドウ **が開いている** ソース ツール  
    :::image-end:::  
    
1.  [スニペット **] タブを** 選択して 、[スニペット] ウィンドウ **を開** きます。  スニペット オプションにアクセスするには、 **その他の** タブ \( その他のタブ ![ ][ImageMoreTabsIcon] \) を選択 **する必要があります** 。  
    
### コマンド メニューで [スニペット] ウィンドウを開く  

1.  DevTools のどこかにカーソルを移動します。  
1.  `Control` + `Shift` + `P` \(Windows, Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択してコマンド メニューを開きます。  
1.  「入力 `Snippets` 」と入力し **、[スニペットの表示**] を選択し、コマンドの `Enter` 実行を選択します。  
    
    :::image type="complex" source="../media/javascript-search-show-snippets.msft.png" alt-text="[スニペットの表示] コマンド" lightbox="../media/javascript-search-show-snippets.msft.png":::
       [ **スニペットの表示]** コマンド  
    :::image-end:::  
    
## スニペットを作成する  

### [ソース] パネルを使用してスニペットを作成する  

1.  [[スニペット **] ウィンドウを開** きます](#open-the-snippets-pane)。  
1.  [新 **しいスニペット] を選択します**。  
1.  スニペットの名前を入力し、保存を `Enter` 選択します。  
    
    :::image type="complex" source="../media/javascript-sources-snippets-naming.msft.png" alt-text="スニペットに名前を付け" lightbox="../media/javascript-sources-snippets-naming.msft.png":::
       スニペットに名前を付け  
    :::image-end:::  
    
### コマンド メニューを使用してスニペットを作成する  

1.  DevTools のどこかにカーソルを移動します。  
1.  `Control` + `Shift` + `P` \(Windows, Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択してコマンド メニューを開きます。  
1.  「入力 `Snippet` 」と入力し **、[新しいスニペットの作成]** を選択し、コマンド `Enter` の実行を選択します。  
    
    :::image type="complex" source="../media/javascript-search-create-new-snippet.msft.png" alt-text="新しいスニペットを作成するためのコマンド" lightbox="../media/javascript-search-create-new-snippet.msft.png":::
       新しいスニペットを作成するためのコマンド  
    :::image-end:::  
    
新しいスニペットの名前をカスタム名で変更するには、[スニペットの名前の変更 [] に移動します](#rename-snippets)。  

## スニペットの編集  

1.  [[スニペット **] ウィンドウを開** きます](#open-the-snippets-pane)。  
1.  [ **スニペット] ウィンドウ** で、編集するスニペットの名前を選択します。  コード エディターで **開きます**。  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-saved.msft.png" alt-text="コード エディター" lightbox="../media/javascript-sources-snippets-editor-saved.msft.png":::
       コード **エディター**  
    :::image-end:::  
    
1.  コード エディター **を使用して** 、スニペットに JavaScript を追加します。  
1.  スニペットの名前の横にアスタリスクが表示されている場合は、コードが保存されていないことを意味します。  `Control` + `S` \(Windows, Linux\) または `Command` + `S` \(macOS\) を選択して保存します。  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-unsaved.msft.png" alt-text="スニペット名の横にあるアスタリスクは、保存されていないコードを示します" lightbox="../media/javascript-sources-snippets-editor-unsaved.msft.png":::
       スニペット名の横にあるアスタリスクは、保存されていないコードを示します  
    :::image-end:::  
    
## スニペットを実行する  

### [ソース] パネルからスニペットを実行する  

1.  [[スニペット **] ウィンドウを開** きます](#open-the-snippets-pane)。  
1.  実行するスニペットの名前を選択します。  スニペットがコード エディターで **開きます**。  
1.  [**スニペットの実行**\ ( ![ スニペットの実行 \ ) を ][ImageRunSnippetIcon] 選択するか `Control` + `Enter` 、\(Windows, Linux\) `Command` + `Enter` または \(macOS\) を選択します。  
    
### コマンド メニューを使用してスニペットを実行する  

1.  DevTools のどこかにカーソルを移動します。  
1.  `Control` + `Shift` + `P` \(Windows, Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択してコマンド メニューを開きます。  
1.  文字を `>` 削除し、その `!` 文字の後に実行するスニペットの名前を入力します。  
    
    :::image type="complex" source="../media/javascript-search-run-command.msft.png" alt-text="コマンド メニューからのスニペットの実行" lightbox="../media/javascript-search-run-command.msft.png":::
       コマンド メニューからのスニペット **の実行**  
    :::image-end:::  
    
1.  スニペット `Enter` を実行する場合に選択します。  

## スニペットの名前を変更する  

1.  [[スニペット **] ウィンドウを開** きます](#open-the-snippets-pane)。  
1.  スニペット名をポイントし、コンテキスト メニュー \(右クリック\) を開き、[名前の変更] を選択 **します**。  
    
## スニペットを削除する  

1.  [[スニペット **] ウィンドウを開** きます](#open-the-snippets-pane)。  
1.  スニペット名をポイントし、コンテキスト メニュー \(右クリック\) を開き、[削除] を選択 **します**。  
    
## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageMoreTabsIcon]: ../media/more-tabs-icon.msft.png  
[ImageRunSnippetIcon]: ../media/run-snippet-icon.msft.png  

<!-- links -->  

[DevtoolsConsoleIndex]: ../console/index.md "コンソールの概要 |Microsoft Docs"  
[DevToolsSourcesTool]: ../sources/index.md "ソース ツールの概要 |Microsoft Docs"  
[DevtoolsJavascriptOverrides]: ./overrides.md "Overrides |Microsoft Docs"  

[MDNScratchpad]: https://developer.mozilla.org/docs/Tools/Scratchpad "スクラッチパッド |MDN"  
[WikiBookmarklet]: https://en.wikipedia.org/wiki/Bookmarklet "Bookmarklet |Wikipedia"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
