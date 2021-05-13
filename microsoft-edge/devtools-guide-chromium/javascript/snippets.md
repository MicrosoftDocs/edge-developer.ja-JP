---
description: スニペットは、DevTools の Sources ツール内で作成および実行できる小Microsoft Edgeです。  Web ページからリソースにアクセスして実行できます。  スニペットを実行すると、現在開いている Web ページのコンテキストから実行されます。
title: DevTools を使用して任意の Web ページで JavaScript のスニペットMicrosoft Edge実行する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 4a84e959f652320f40a501a26e9ba763c7348b33
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564113"
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
# <a name="run-snippets-of-javascript-on-any-webpage-with-microsoft-edge-devtools"></a>DevTools を使用して任意の Web ページで JavaScript のスニペットMicrosoft Edge実行する  

コンソールで同じコードを繰り返[][DevtoolsConsoleIndex]し実行している場合は、コードをスニペットとして保存してください。  スニペットは、ソース ツールで作成する [スクリプト][DevToolsSourcesTool] です。  スニペットは Web ページの JavaScript コンテキストにアクセスし、任意の Web ページでスニペットを実行できます。  ほとんどの Web ページのセキュリティ設定は、スニペットに他のスクリプトを読み込むのをブロックします。  このため、すべてのコードを 1 つのファイルに含める必要があります。  

スニペットは、スニペットが[][WikiBookmarklet]DevTools でのみ実行されるという違いを持つブックマークレットの代わりであり、URL の許可される長さに限定されません。  

スニペットの使用は、サードパーティの Web ページでいくつかの変更を行う優れた方法です。  スニペットのコードの変更は、現在の Web ページに追加され、同じコンテキストで実行されます。  Web ページの既存のコードを変更する方法の詳細については [、「Overrides」に移動します][DevtoolsJavascriptOverrides]。  

:::row:::
   :::column span="":::
      たとえば、次の図に、左側の DevTools ホームページと、右側のスニペット ソース コードを示します。  
      
      :::image type="complex" source="../media/javascript-sources-snippets-split-screen.msft.png" alt-text="スニペットを実行する前に" lightbox="../media/javascript-sources-snippets-split-screen.msft.png":::
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

次の図では、スニペットの実行後に Web ページが表示されます。  コンソール **ドロワー** がポップアップ表示され、スニペットによってログに記録されるメッセージが表示され、Web ページの内容 `Hello, Snippets!` が完全に変更されます。  

:::image type="complex" source="../media/javascript-sources-snippets-split-screen-after.msft.png" alt-text="スニペットの実行後の Web ページ" lightbox="../media/javascript-sources-snippets-split-screen-after.msft.png":::
   スニペットの実行後の Web ページ  
:::image-end:::  

## <a name="open-the-snippets-tab"></a>[スニペット] タブを開く  

左側 **の [** ナビゲーター] ウィンドウの [ **スニペット** ] タブに、スニペットの一覧が表示されます。  スニペットを編集する場合は、[スニペット] タブから **スニペットを開く必要** があります。  

:::image type="complex" source="../media/javascript-sources-snippets-pane.msft.png" alt-text="[スニペット] タブ" lightbox="../media/javascript-sources-snippets-pane.msft.png":::
   [ **スニペット]** タブ  
:::image-end:::  

### <a name="open-the-snippets-tab-with-a-mouse"></a>マウスで [スニペット] タブを開く  

1.  [ソース] **タブを選択** します。 [ **ソース] ツール** が表示されます。  
    
    :::image type="complex" source="../media/javascript-sources-page-pane.msft.png" alt-text="左側の [ページ] タブを開いた [ソース] ツール" lightbox="../media/javascript-sources-page-pane.msft.png":::
       左側 **の [** ページ] タブ **を開** いた [ソース] ツール  
    :::image-end:::  
    
1.  左側の **[ナビゲーター]** ウィンドウで、[スニペット] **タブを選択** します。 スニペット オプションに **アクセスするには** 、[その他のタブ] \( More **tabs** \) を選択 ![ する必要 ](../media/more-tabs-icon.msft.png) があります。  
    
### <a name="open-the-snippets-tab-with-the-command-menu"></a>コマンド メニューで [スニペット] タブを開く  

1.  DevTools で何かを選択して、DevTools にフォーカスを設定します。  
1.  `Control` + `Shift` + `P` コマンド メニューを開Windows \(Windows Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。  
1.  [ `Snippets` スニペットの **表示] を選択**し、コマンドを `Enter` 実行する場合に選択します。  
    
    :::image type="complex" source="../media/javascript-search-show-snippets.msft.png" alt-text="[スニペットの表示] コマンド" lightbox="../media/javascript-search-show-snippets.msft.png":::
       [ **スニペットの表示]** コマンド  
    :::image-end:::  
    
## <a name="create-snippets"></a>スニペットの作成  

### <a name="create-a-snippet-through-the-sources-tool"></a>ソース ツールを使用してスニペットを作成する  

1.  [[スニペット] タブを開きます](#open-the-snippets-tab)。  
1.  [新 **しいスニペット] を選択します**。  
1.  スニペットの名前を入力し、[. `Enter`  
    
    :::image type="complex" source="../media/javascript-sources-snippets-naming.msft.png" alt-text="スニペットに名前を付け" lightbox="../media/javascript-sources-snippets-naming.msft.png":::
       スニペットに名前を付け  
    :::image-end:::  
    
### <a name="create-a-snippet-through-the-command-menu"></a>コマンド メニューからスニペットを作成する  

1.  DevTools のどこかにカーソルを移動します。  
1.  `Control` + `Shift` + `P` コマンド メニューを開Windows \(Windows Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。  
1.  [ `Snippet` 新しいスニペットの **作成] を**選択し、コマンド `Enter` を実行する場合に選択します。  
    
    :::image type="complex" source="../media/javascript-search-create-new-snippet.msft.png" alt-text="新しいスニペットを作成するためのコマンド" lightbox="../media/javascript-search-create-new-snippet.msft.png":::
       新しいスニペットを作成するためのコマンド  
    :::image-end:::  
    
カスタム名を使用して新しいスニペットの名前を変更するには、[スニペットの名前の変更 [] に移動します](#rename-snippets)。  

## <a name="edit-snippets"></a>スニペットの編集  

1.  [[スニペット] タブを開きます](#open-the-snippets-tab)。  
1.  [スニペット **] タブ** で、編集するスニペットの名前を選択します。  コード エディターで **開きます**。  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-saved.msft.png" alt-text="コード エディター" lightbox="../media/javascript-sources-snippets-editor-saved.msft.png":::
       コード **エディター**  
    :::image-end:::  
    
1.  コード エディター **を使用して** 、スニペットに JavaScript を追加します。  
1.  スニペットの名前の横にアスタリスクが表示される場合は、コードが保存されていないことを意味します。  `Control` + `S` \(Windows Linux\) または `Command` + `S` \(macOS\) を選択して保存します。  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-unsaved.msft.png" alt-text="スニペット名の横にあるアスタリスクは、保存されていないコードを示します" lightbox="../media/javascript-sources-snippets-editor-unsaved.msft.png":::
       スニペット名の横にあるアスタリスクは、保存されていないコードを示します  
    :::image-end:::  
    
## <a name="run-snippets"></a>スニペットの実行  

### <a name="run-a-snippet-from-the-sources-tool"></a>ソース ツールからスニペットを実行する  

1.  [[スニペット] タブを開きます](#open-the-snippets-tab)。  
1.  実行するスニペットの名前を選択します。  コード エディターでスニペット **が開きます**。  
1.  [ **スニペットの実行** \( ![ Run Snippet ](../media/run-snippet-icon.msft.png) \) を選択します。
    
### <a name="run-a-snippet-with-the-command-menu"></a>コマンド メニューを使用してスニペットを実行する  

1.  DevTools のどこかにカーソルを移動します。  
1.  `Control` + `Shift` + `P` コマンド メニューを開Windows \(Windows Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。  
1.  文字を削除し、実行するスニペットの名前の後に文字 `>` `!` を入力します。  
    
    :::image type="complex" source="../media/javascript-search-run-command.msft.png" alt-text="コマンド メニューからスニペットを実行する" lightbox="../media/javascript-search-run-command.msft.png":::
       コマンド メニューからスニペット **を実行する**  
    :::image-end:::  
    
1.  スニペット `Enter` を実行する場合に選択します。  

## <a name="rename-snippets"></a>スニペットの名前を変更する  

1.  [[スニペット] タブを開きます](#open-the-snippets-tab)。  
1.  スニペット名をポイントし、コンテキスト メニュー \(右クリック\) を開き、[名前の変更] を **選択します**。  
    
## <a name="delete-snippets"></a>スニペットの削除  

1.  [[スニペット] タブを開きます](#open-the-snippets-tab)。  
1.  スニペット名をポイントし、コンテキスト メニュー \(右クリック\) を開き、[削除] を **選択します**。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleIndex]: ../console/index.md "コンソールの概要|Microsoft Docs"  
[DevToolsSourcesTool]: ../sources/index.md "ソース ツールの概要|Microsoft Docs"  
[DevtoolsJavascriptOverrides]: ./overrides.md "オーバーライド|Microsoft Docs"  

[MDNScratchpad]: https://developer.mozilla.org/docs/Tools/Scratchpad "Scratchpad |MDN"  
[WikiBookmarklet]: https://en.wikipedia.org/wiki/Bookmarklet "Bookmarklet |Wikipedia"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
