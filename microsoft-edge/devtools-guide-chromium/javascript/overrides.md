---
description: オーバーライド機能は、Microsoft Edge DevTools の Sources ツール内の機能で、Web ページ リソースをハード ドライブにコピーできます。  Web ページを更新すると、DevTools はリソースを読み込むのではなく、ローカル コピーに置き換える必要があります。
title: Microsoft Edge DevTools を使用して Web ページ リソースをローカル コピーで上書きする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 7f273f89708e0948e68cd2c7ba79cefb6d7e167c
ms.sourcegitcommit: 2ddfd98d1e871be9c61380a8ca57da398d38bd54
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "11230965"
---
# <a name="override-webpage-resources-with-local-copies-using-microsoft-edge-devtools"></a>Microsoft Edge DevTools を使用して Web ページ リソースをローカル コピーで上書きする  

アクセスできない Web ページや修正プログラムで問題を修正する必要がある場合は、ビルド プロセスが遅く複雑な場合があります。  DevTools のすべての種類の問題をデバッグして修正できます。 しかし、問題は変更が持続しない点です。  ファイルを更新すると、すべての作業が完了します。  

ソース ツールのオーバーライド機能 [を使用すると][DevToolsSourcesTool] 、この問題を解決できます。  

現在の Web ページのリソースを取得し、ローカルに保存できます。  Web ページを更新しても、ブラウザーはサーバーからリソースを読み込む必要があります。  代わりに、ブラウザーは、リソースのローカル コピーに置き換える。  

## <a name="setting-up-your-local-folder-to-store-overrides"></a>上書きを保存するローカル フォルダーを設定する  

1.  [ソース **] ツール** で、左側に複数のセクションを検索します。  [ **上書き] オプション** が表示されない場合は、 <code>&#x0226B;</code><!--`≫`--> アイコンをクリックしてそこにアクセスします。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-overflow-menu.msft.png" alt-text="オーバーライド オプションを表示するのに十分な領域を持つソース ツール" lightbox="../media/javascript-overrides-overflow-menu.msft.png":::
             **オーバーライド オプション** を表示するのに十分な領域を持つソース ツール  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-menu.msft.png" alt-text="上書きオプションを選択する" lightbox="../media/javascript-overrides-menu.msft.png":::
             上書きオプションを選択する  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  [上書き] オプション **を** 選択した後、ローカル コンピューター上のフォルダーを選択して、置き換えるリソース ファイルを保存する必要があります。  フォルダーを **検索するには、上書きする +** 選択フォルダーを選択します。  
    
    :::image type="complex" source="../media/javascript-overrides-select-folder.msft.png" alt-text="上書きに使用するフォルダーを選択する" lightbox="../media/javascript-overrides-select-folder.msft.png":::
       上書きに使用するフォルダーを選択する  
    :::image-end:::  
    
1.  DevTools は、フォルダーへのフル アクセス権が必要であり、機密情報を明らかにしなける必要があるという警告を表示します。  警告バーで、[許可] を **選択してアクセス** を許可します。  
    
    :::image type="complex" source="../media/javascript-overrides-give-access-to-folder.msft.png" alt-text="DevTools にフォルダーへのアクセス権を付与する" lightbox="../media/javascript-overrides-give-access-to-folder.msft.png":::
       DevTools にフォルダーへのアクセス権を付与する  
    :::image-end:::  
    
1.  [上書 **き]** ウィンドウの横にチェック ボックスが表示され、 `Enable Local Overrides` 上書きフォルダーが表示されます。  アイコンが横に表示され、ローカルの上書き設定を削除できます。  これで、フォルダーのセットアップが完了し、ライブ リソースをローカル リソースに置き換える準備ができました。
    
    :::image type="complex" source="../media/javascript-overrides-folder-setup-complete.msft.png" alt-text="上書きフォルダーの正常なセットアップ" lightbox="../media/javascript-overrides-folder-setup-complete.msft.png":::
       上書きフォルダーの正常なセットアップ  
    :::image-end:::  
    
## <a name="adding-files-to-your-overrides-folder"></a>Overrides フォルダーへのファイルの追加  
  
上書きフォルダーにファイルを追加するには、[要素] ツール **を開** き、Web ページを調べる。  編集するには、[スタイル] インスペクタで CSS ファイルの名前 **を選択** します。  

:::image type="complex" source="../media/javascript-overrides-select-css-file.msft.png" alt-text="[スタイル] インスペクタでファイルを選択する" lightbox="../media/javascript-overrides-select-css-file.msft.png":::
   [スタイル] インスペクタでファイル **を選択** する  
:::image-end:::  

[ソース **] エディターで** 、選択したファイルのファイル名にマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[上書き用に保存] を **選択します**。  

:::image type="complex" source="../media/javascript-overrides-file-name.msft.png" alt-text="[ソース] エディターで、上書きするファイルの名前を追加します。" lightbox="../media/javascript-overrides-file-name.msft.png":::
   [ソース **] エディターで** 、上書きするファイルの名前を追加します。  
:::image-end:::  

:::image type="complex" source="../media/javascript-overrides-save-for-overrides.msft.png" alt-text="コンテキスト メニューで、[上書き用に保存] を選択します。" lightbox="../media/javascript-overrides-save-for-overrides.msft.png":::
   コンテキスト メニューで、[上書き用 **に保存] を選択します。**  
:::image-end:::  

ファイルは上書きフォルダーに保存されます。  DevTools が、正しいディレクトリ構造を持つファイルの URL を使用して名前が付けられたフォルダーを作成していることを確認します。  ファイルは内部に格納されます。  エディターのファイル名には、ファイルがローカルであり、ライブではないかどうかを示す紫色のドットも表示されます。  

:::image type="complex" source="../media/javascript-overrides-file-stored.msft.png" alt-text="ファイルをオーバーライド フォルダーに正常に保存しました" lightbox="../media/javascript-overrides-file-stored.msft.png":::
   ファイルをオーバーライド フォルダーに正常に保存しました  
:::image-end:::  

:::row:::
   :::column span="":::
      次の例では、Web ページのスタイルを変更できます。  ファイルの周囲に赤い枠線を追加するには****、[スタイル] エディターで次のスタイルをコピーし、body 要素に追加します。  
      
      ```css
      border: 10px solid firebrick
      ```  
   :::column-end:::
   :::column span="":::
      ファイルはコンピューターに自動的に保存されます。  ファイルを更新すると、罫線が表示され、作業のどれも失われます。  
      
      :::image type="complex" source="../media/javascript-overrides-changing-styles.msft.png" alt-text="オーバーライド フォルダー内のファイルを編集して、Web ページのスタイルを永続的に変更する" lightbox="../media/javascript-overrides-changing-styles.msft.png":::
         オーバーライド フォルダー内のファイルを編集して、Web ページのスタイルを永続的に変更する  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

:::row:::
   :::column span="":::
      [ソース **] ツールの** [ **ページ** ] セクションで、任意のファイルにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、上書きに追加します。  繰り返しますが、上書きフォルダーに既に存在するファイルには、アイコンに紫色のドットが表示されます。  
      
      :::image type="complex" source="../media/javascript-overrides-safe-from-sources.msft.png" alt-text="上書きのために Sources ツールからファイルを選択する" lightbox="../media/javascript-overrides-safe-from-sources.msft.png":::
         上書きのために **Sources ツールから** ファイルを選択する  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      または、ネットワーク ツール**** で任意のファイルにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、上書きに追加します。  上書きが有効な場合、ライブ Web ページではなく、コンピューター上にあるファイル。  上書きが有効な場合は、 **ネットワーク** ツールで、ファイル名の横にある警告アイコンを探します。  
      
      :::image type="complex" source="../media/javascript-overrides-network.msft.png" alt-text="ネットワーク ツールから上書き用のファイルを選択する" lightbox="../media/javascript-overrides-network.msft.png":::
         ネットワーク ツールから上書き **用の** ファイルを選択する  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="two-way-interaction-of-overrides"></a>オーバーライドの相互対話  

DevTools の **Sources** ツールまたはファイルを変更する任意のエディターで提供されるエディターを使用します。  変更は、オーバーライド フォルダー内のファイルにアクセスするすべての製品間で同期されます。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsSourcesTool]: ../sources/index.md "ソース ツールの概要|Microsoft Docs"  
