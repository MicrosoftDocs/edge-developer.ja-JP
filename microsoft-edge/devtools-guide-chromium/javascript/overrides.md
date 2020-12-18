---
description: オーバーライド機能は、Microsoft Edge DevTools の Sources ツール内の機能で、Web ページのリソースをハード ドライブにコピーできます。  Web ページを更新すると、DevTools はリソースを読み込むのではなく、ローカル コピーに置き換える必要があります。
title: Microsoft Edge DevTools を使用して Web ページ リソースをローカル コピーで上書きする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 7f273f89708e0948e68cd2c7ba79cefb6d7e167c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230965"
---
# Microsoft Edge DevTools を使用して Web ページ リソースをローカル コピーで上書きする  

アクセスできない Web ページや修正プログラムの問題を修正する必要がある場合は、ビルド プロセスが遅く複雑になります。  DevTools では、すべての種類の問題をデバッグして修正できます。 ただし、問題は変更が保持されない点です。  ファイルを更新すると、すべての作業が完了します。  

ソース ツールの上書き機能 [は、この][DevToolsSourcesTool] 問題の解決に役立ちます。  

現在の Web ページのリソースを取得し、ローカルに保存できます。  Web ページを更新しても、ブラウザーはサーバーからリソースを読み込みしません。  代わりに、ブラウザーがリソースのローカル コピーに置き換わる。  

## 上書きを保存するローカル フォルダーの設定  

1.  ソース ツール **で** 、左側に複数のセクションがあります。  [ **上書き] オプション** が表示されない場合は、 <code>&#x0226B;</code><!--`≫`--> アイコンをクリックします。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-overflow-menu.msft.png" alt-text="上書きオプションを表示するのに十分な領域を持たなかったソース ツール" lightbox="../media/javascript-overrides-overflow-menu.msft.png":::
             **上書き** オプションを表示するのに十分な領域を持たなかったソース ツール  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-menu.msft.png" alt-text="上書きオプションを選択する" lightbox="../media/javascript-overrides-menu.msft.png":::
             上書きオプションを選択する  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  上書きオプションを **選択** した後、ローカル コンピューター上のフォルダーを選択して、置換するリソース ファイルを格納する必要があります。  Choose the **+ Select folder for overrides** to search for a folder.  
    
    :::image type="complex" source="../media/javascript-overrides-select-folder.msft.png" alt-text="上書きに使用するフォルダーを選択する" lightbox="../media/javascript-overrides-select-folder.msft.png":::
       上書きに使用するフォルダーを選択する  
    :::image-end:::  
    
1.  DevTools は、フォルダーへのフル アクセスが必要であり、機密情報を公開しなけなければならないという警告を表示します。  警告バーで、[アクセスを許可 **する]** を選択します。  
    
    :::image type="complex" source="../media/javascript-overrides-give-access-to-folder.msft.png" alt-text="DevTools にフォルダーへのアクセス権を付与する" lightbox="../media/javascript-overrides-give-access-to-folder.msft.png":::
       DevTools にフォルダーへのアクセス権を付与する  
    :::image-end:::  
    
1.  [上書 **き] ウィンドウ** で、チェック ボックスが横に表示され、上書 `Enable Local Overrides` きフォルダーが表示されます。  アイコンが横に表示され、ローカルの上書き設定を削除できます。  これで、フォルダーのセットアップが完了し、ライブ リソースをローカル リソースに置き換える準備が整いました。
    
    :::image type="complex" source="../media/javascript-overrides-folder-setup-complete.msft.png" alt-text="オーバーライド フォルダーの正常なセットアップ" lightbox="../media/javascript-overrides-folder-setup-complete.msft.png":::
       オーバーライド フォルダーの正常なセットアップ  
    :::image-end:::  
    
## Overrides フォルダーへのファイルの追加  
  
オーバーライド フォルダーにファイルを追加するには **、Elements** ツールを開き、Web ページを検査します。  編集するには、[スタイル] インスペクターで CSS ファイルの名前 **を選択** します。  

:::image type="complex" source="../media/javascript-overrides-select-css-file.msft.png" alt-text="スタイルインスペクターでファイルを選択する" lightbox="../media/javascript-overrides-select-css-file.msft.png":::
   スタイルインスペクターでファイル **を選択** する  
:::image-end:::  

ソース エディター **で、** 選択したファイルのファイル名をポイントし、コンテキスト メニュー \(右クリック\) を開き、[上書きのために保存] を **選択します**。  

:::image type="complex" source="../media/javascript-overrides-file-name.msft.png" alt-text="Sources エディターで、上書きするファイルの名前を追加します。" lightbox="../media/javascript-overrides-file-name.msft.png":::
   Sources **エディターで** 、上書きするファイルの名前を追加します。  
:::image-end:::  

:::image type="complex" source="../media/javascript-overrides-save-for-overrides.msft.png" alt-text="コンテキスト メニューで、[上書き用に保存] を選択します。" lightbox="../media/javascript-overrides-save-for-overrides.msft.png":::
   コンテキスト メニューで、[上書き用に **保存] を選択します。**  
:::image-end:::  

ファイルは上書きフォルダーに格納されます。  DevTools が、正しいディレクトリ構造を持つファイルの URL を使用して名前が付けられたフォルダーを作成していることを確認します。  ファイルは内部に格納されます。  エディターのファイル名にも紫色のドットが表示され、ファイルがローカルであり、ライブファイルできなっています。  

:::image type="complex" source="../media/javascript-overrides-file-stored.msft.png" alt-text="上書きフォルダーにファイルが正常に保存されました" lightbox="../media/javascript-overrides-file-stored.msft.png":::
   上書きフォルダーにファイルが正常に保存されました  
:::image-end:::  

:::row:::
   :::column span="":::
      次の例では、Web ページのスタイルを変更できます。  ファイルの周囲に赤い罫線を追加するには、 **スタイル** エディターで次のスタイルをコピーし、body 要素に追加します。  
      
      ```css
      border: 10px solid firebrick
      ```  
   :::column-end:::
   :::column span="":::
      ファイルはコンピューターに自動的に保存されます。  ファイルを更新すると、境界線が表示され、作業は失われます。  
      
      :::image type="complex" source="../media/javascript-overrides-changing-styles.msft.png" alt-text="上書きフォルダー内のファイルを編集して、Web ページのスタイルを永続的に変更する" lightbox="../media/javascript-overrides-changing-styles.msft.png":::
         上書きフォルダー内のファイルを編集して、Web ページのスタイルを永続的に変更する  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

:::row:::
   :::column span="":::
      ソース ツール **の** [ **ページ** ] セクションで、任意のファイルをポイントし、コンテキスト メニュー \(右クリック\) を開き、上書きに追加します。  繰り返しますが、上書きフォルダーに既に存在するファイルのアイコンには紫色のドットが付きます。  
      
      :::image type="complex" source="../media/javascript-overrides-safe-from-sources.msft.png" alt-text="上書きのためにソース ツールからファイルを選択する" lightbox="../media/javascript-overrides-safe-from-sources.msft.png":::
         上書きのためにソース ツール **からファイル** を選択する  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      または、ネットワーク ツール**** で任意のファイルをポイントし、コンテキスト メニュー \(右クリック\) を開き、上書きに追加します。  上書きが有効な場合、実際の Web ページではなくコンピューター上にあるファイル。  上書きが有効な場合は、 **ネットワーク** ツールでファイル名の横にある警告アイコンを探します。  
      
      :::image type="complex" source="../media/javascript-overrides-network.msft.png" alt-text="ネットワーク ツールから上書き用のファイルを選択する" lightbox="../media/javascript-overrides-network.msft.png":::
         ネットワーク ツールから上書き **用の** ファイルを選択する  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## オーバーライドの 2 つのやり取り  

DevTools の **Sources** ツールに用意されているエディター、またはファイルを変更する任意のエディターを使用します。  変更は、overrides フォルダー内のファイルにアクセスする製品すべてで同期されます。  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsSourcesTool]: ../sources/index.md "ソース ツールの概要 |Microsoft Docs"  
