---
description: 上書き機能は、Microsoft Edge DevTools のソースツール内の機能で、web ページのリソースをハードドライブにコピーすることができます。  Web ページを更新すると、DevTools でリソースが読み込まれることはありませんが、代わりにローカルコピーで置き換えられます。
title: Microsoft Edge DevTools を使用してローカルコピーで web ページのリソースを上書きする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 579ebe92dc50571837e7e3caf8fb7c1a9989bc59
ms.sourcegitcommit: 9dcaf598f3930bcfab9f93ff63463beb98274de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "11145183"
---
# Microsoft Edge DevTools を使用してローカルコピーで web ページのリソースを上書きする  

アクセス権を持っていない web ページの問題を解決する必要があります。または、修復が複雑で複雑なビルドプロセスが含まれていることがあります。  DevTools では、すべての種類の問題をデバッグして修正することができます。 ただし、この変更は保存されません。  ファイルを更新すると、すべての作業が失われます。  

[ソース][DevToolsSourcesTool]ツールの上書き機能は、この問題を解決するのに役立ちます。  

現在の web ページのリソースを取得して、ローカルに保存することができます。  Web ページを更新しても、ブラウザーによってサーバーからリソースが読み込まれることはありません。  代わりに、ブラウザーによってリソースのローカルコピーで置き換えられます。  

## 上書きを保存するためのローカルフォルダーの設定  

1.  **ソース**ツールで、左側にあるいくつかのセクションを検索します。  [ **上書き** ] オプションが表示されない場合は、 <code>&#x0226B;</code><!--`≫`--> アイコンを選びます。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-overflow-menu.msft.png" alt-text="[上書き] オプションを表示するための十分な領域がないソースツール" lightbox="../media/javascript-overrides-overflow-menu.msft.png":::
             [上書き] オプションを表示するための十分な領域がない**ソース**ツール  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/javascript-overrides-menu.msft.png" alt-text="[上書き] オプションを表示するための十分な領域がないソースツール" lightbox="../media/javascript-overrides-menu.msft.png":::
             [上書き] オプションを選ぶ  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  [ **上書き** ] オプションを選んだら、置換するリソースファイルを保存するローカルコンピューター上のフォルダーを選択する必要があります。  フォルダーを検索するには、[ **上書き用の + 選択] フォルダー** を選択します。  
    
    :::image type="complex" source="../media/javascript-overrides-select-folder.msft.png" alt-text="[上書き] オプションを表示するための十分な領域がないソースツール" lightbox="../media/javascript-overrides-select-folder.msft.png":::
       上書きに使用するフォルダーを選択する  
    :::image-end:::  
    
1.  DevTools は、フォルダーへのフルアクセス権が必要であることを警告し、機密情報を表示しないようにします。  警告バーで、[ **許可** ] を選択してアクセスを許可します。  
    
    :::image type="complex" source="../media/javascript-overrides-give-access-to-folder.msft.png" alt-text="[上書き] オプションを表示するための十分な領域がないソースツール" lightbox="../media/javascript-overrides-give-access-to-folder.msft.png":::
       フォルダーへの DevTools アクセスの許可  
    :::image-end:::  
    
1.  [ **上書き** ] ウィンドウで、[] と [上書き] フォルダーの横に checkbox が表示され `Enable Local Overrides` ます。  横にアイコンが表示され、ローカルの上書き設定を削除することができます。  これで、フォルダーの設定が完了し、ライブリソースをローカルのリソースに置き換える準備が整いました。
    
    :::image type="complex" source="../media/javascript-overrides-folder-setup-complete.msft.png" alt-text="[上書き] オプションを表示するための十分な領域がないソースツール" lightbox="../media/javascript-overrides-folder-setup-complete.msft.png":::
       上書きフォルダーの設定が完了しました  
    :::image-end:::  
    
## 上書きフォルダーにファイルを追加する  
  
上書きフォルダーにファイルを追加するには、 **要素** ツールを開いて、web ページを調べます。  編集するには、 **スタイル** インスペクターで CSS ファイルの名前を選択します。  

:::image type="complex" source="../media/javascript-overrides-select-css-file.msft.png" alt-text="[上書き] オプションを表示するための十分な領域がないソースツール" lightbox="../media/javascript-overrides-select-css-file.msft.png":::
   [ **スタイル** インスペクター] でファイルを選ぶ  
:::image-end:::  

**ソース**エディターで、選択したファイルのファイル名にポインターを置いて、コンテキストメニュー \ (右クリック \) を開き、[**上書き用に保存**] を選びます。  

:::image type="complex" source="../media/javascript-overrides-file-name.msft.png" alt-text="[上書き] オプションを表示するための十分な領域がないソースツール" lightbox="../media/javascript-overrides-file-name.msft.png":::
   **ソース**エディターで、上書きするファイルの名前を追加します。  
:::image-end:::  

:::image type="complex" source="../media/javascript-overrides-save-for-overrides.msft.png" alt-text="[上書き] オプションを表示するための十分な領域がないソースツール" lightbox="../media/javascript-overrides-save-for-overrides.msft.png":::
   コンテキストメニューで、[**上書き用に保存**] を選択します。  
:::image-end:::  

ファイルは [上書き] フォルダーに格納されます。  DevTools で、ディレクトリ構造が適切なファイルの URL を使用して名前が付けられたフォルダーを作成していることを確認します。  ファイルは内部に保存されています。  エディターのファイル名には、ファイルがローカルであり、ライブではないことを示す紫色のドットも表示されるようになりました。  

:::image type="complex" source="../media/javascript-overrides-file-stored.msft.png" alt-text="[上書き] オプションを表示するための十分な領域がないソースツール" lightbox="../media/javascript-overrides-file-stored.msft.png":::
   上書きフォルダーにファイルが正常に保存されました  
:::image-end:::  

:::row:::
   :::column span="":::
      次の例では、web ページのスタイルを変更できるようになりました。  ファイルの周囲に赤い境界線を追加するには、[ **スタイル** エディター] で次のスタイルをコピーして本文要素に追加します。  
      
      ```css
      border: 10px solid firebrick
      ```  
   :::column-end:::
   :::column span="":::
      ファイルはコンピューターに自動的に保存されます。  ファイルを更新すると、枠線が表示され、作業内容が失われることはありません。  
      
      :::image type="complex" source="../media/javascript-overrides-changing-styles.msft.png" alt-text="[上書き] オプションを表示するための十分な領域がないソースツール" lightbox="../media/javascript-overrides-changing-styles.msft.png":::
         上書きフォルダー内のファイルを編集して、web ページのスタイルを永続的に変更する  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

:::row:::
   :::column span="":::
      **ソース**ツールの [**ページ**] セクションで、任意のファイルをポイントし、コンテキストメニュー \ (右クリック \) を開き、[上書き] に追加します。  この場合も、[上書き] フォルダーに既にあるファイルのアイコンに紫色のドットが付いています。  
      
      :::image type="complex" source="../media/javascript-overrides-safe-from-sources.msft.png" alt-text="[上書き] オプションを表示するための十分な領域がないソースツール" lightbox="../media/javascript-overrides-safe-from-sources.msft.png":::
         上書き用の **ソース** ツールからファイルを選ぶ  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      または、 **ネットワーク** ツールで任意のファイルをポイントし、コンテキストメニューを開き (\ を右クリックし)、[上書き] に追加します。  上書きが有効な場合は、実際の web ページではなく、コンピューター上にあるファイル。  上書きが有効な場合は、 **ネットワーク** ツールで、ファイル名の横にある警告アイコンを見つけます。  
      
      :::image type="complex" source="../media/javascript-overrides-network.msft.png" alt-text="[上書き] オプションを表示するための十分な領域がないソースツール" lightbox="../media/javascript-overrides-network.msft.png":::
         上書き用の **ネットワーク** ツールからファイルを選ぶ  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## 上書きの双方向の相互作用  

DevTools の **ソース** ツール、またはファイルを変更するエディターで提供されるエディターを使用します。  変更は、上書きフォルダー内のファイルにアクセスするすべての製品間で同期されます。  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsSourcesTool]: ../sources.md "ソースツールの概要 |Microsoft ドキュメント"  
