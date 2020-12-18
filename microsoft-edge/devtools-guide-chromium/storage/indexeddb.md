---
description: アプリケーション パネルとスニペットを使用して IndexedDB データを表示および変更する方法について説明します。
title: Microsoft Edge DevTools を使用して IndexedDB データを表示および変更する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 03e6d04050677a0ba153c6adc06dd795cc42115d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231203"
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

# Microsoft Edge DevTools を使用して IndexedDB データを表示および変更する  

このガイドでは [、Microsoft Edge DevTools を使用して][MicrosoftEdgeDevTools] [IndexedDB][MDNIndexedDBAPI] データを表示および変更する方法について説明します。  DevTools に精通している必要があります。  また、IndexedDB に精通している必要があります。  If not, navigate to [Using IndexedDB][MDNUsingIndexedDB].  

## IndexedDB データの表示  

1.  [アプリケーション **] タブ** を選択して、アプリケーション ツール **を開** きます。  通常 **、マニフェスト** ウィンドウは既定で開きます。  
    
    :::image type="complex" source="../media/storage-application-manifest-empty.msft.png" alt-text="マニフェスト ウィンドウ" lightbox="../media/storage-application-manifest-empty.msft.png":::
       マニフェスト**ウィンドウ**  
    :::image-end:::  
    
1.  **[IndexedDB] メニューを展開**して、使用可能なデータベースを確認します。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb.msft.png" alt-text="IndexedDB メニュー" lightbox="../media/storage-application-storage-indexeddb.msft.png":::
       **IndexedDB**メニュー  
    :::image-end:::  
    
    *   \( ![ Database icon ][ImageDatabaseIcon] \) `notes - https://mdn.github.io` represents a database, where `notes` is the name of the database and is the origin that `https://mdn.github.io` accesses the database.  
    *   \( ![ Object Store icon ][ImageObjectStoreIcon] \) is an object `notes` store.  
    *   **title** and **body** are [indexes][MDNUsingIndexedDBUsingIndex].  
    
    > [!NOTE]
    > **既知の制限**  サード パーティ製のデータベースは表示されません。  たとえば、ページに広告を埋め込むのに使用し、広告ネットワークが IndexedDB を使用している場合、広告ネットワークの `<iframe>` IndexedDB データは表示されません。  問題の解決[方法に#943770。][ChromiumIssue943770]  
    
1.  データベースを選択して、原点とバージョン番号を確認します。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db.msft.png" alt-text="メモ データベース" lightbox="../media/storage-application-storage-indexeddb-notes_db.msft.png":::
       メモ**** データベース  
    :::image-end:::  
    
1.  オブジェクト ストアを選択してキーと値のペアを確認します。  
    
    > [!NOTE]
    > IndexedDB データはリアルタイムで更新されません。  [[IndexedDB データの更新] に移動します](#refresh-indexeddb-data)。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os.msft.png" alt-text="ノート オブジェクト ストア" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os.msft.png":::
       ノート **オブジェクト** ストア  
    :::image-end:::  
    
    *   **エントリの総数は** 、オブジェクト ストア内のキーと値のペアの総数です。  
    *   **キー ジェネレーターの値は** 、次に使用可能なキーです。  フィールドは、キー ジェネレーターを使用 [する場合にのみ表示されます][MDNBasicConceptsKeyGenerator]。  
    
1.  [値] 列のセル **を選択** して、値を展開します。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-edge-chromium.msft.png" alt-text="IndexedDB 値を表示する" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-edge-chromium.msft.png":::
       **IndexedDB 値を表示**する  
    :::image-end:::  
    
1.  次の図のタイトルや**** 本文などの**** インデックスを選択して、そのインデックスの値に従ってオブジェクト ストアを並べ替える。  
   
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-title.msft.png" alt-text="インデックスでオブジェクト ストアを並べ替える" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-title.msft.png":::
       インデックスでオブジェクト ストアを並べ替える  
    :::image-end:::  
    
## IndexedDB データを更新する  

アプリケーション ツールの IndexedDB **値** はリアルタイムで更新されません。  オブジェクト**ストアを表示**してデータを更新する場合は [更新 \( Refresh \) ] を選択し、データベースを表示して [データベースの更新] を選択してすべてのデータ ![ ][ImageReloadIcon] を更新します。 ****  

:::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-refresh-database.msft.png" alt-text="データベースを表示する" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-refresh-database.msft.png":::
   データベースを表示する  
:::image-end:::  

## IndexedDB データの編集  

IndexedDB キーと値は、アプリケーション ツールでは **編集** できません。  ただし、DevTools はページ コンテキストにアクセスできます。ただし、DevTools 内で JavaScript コードを実行して IndexedDB データを編集できます。  

### スニペットを使用して IndexedDB データを編集する  

[スニペットは][DevtoolsJavascriptSnippets] 、DevTools 内に JavaScript コードのブロックを格納して実行する方法です。  スニペットを実行すると、結果がコンソールに記録 **されます**。  スニペットを使用して JavaScript コードを実行し、IndexedDB データベースを編集できます。  

:::image type="complex" source="../media/storage-sources-snippets-indexeddb-output.msft.png" alt-text="スニペットを使用して IndexedDB を操作する" lightbox="../media/storage-sources-snippets-indexeddb-output.msft.png":::
   スニペットを使用して IndexedDB を操作する  
:::image-end:::  

## IndexedDB データを削除する  

### IndexedDB キーと値のペアを削除する  

1.  [IndexedDB オブジェクト ストアを表示します](#view-indexeddb-data)。  
1.  削除するキーと値のペアを選択します。  DevTools によって強調表示され、選択された状態が示されます。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os2.msft.png" alt-text="キーと値のペアを選択して削除する" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os2.msft.png":::
       キーと値のペアを選択して削除する  
    :::image-end:::  
    
1.  キーを押 `Delete` す、または **[Delete Selected** \( ![ Delete Selected \) ] を ][ImageDeleteIcon] 選択します。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-delete-selected.msft.png" alt-text="キーと値のペアが削除された後のオブジェクト ストアの外観" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-delete-selected.msft.png":::
       キーと値のペアが削除された後のオブジェクト ストアの外観  
    :::image-end:::  
    
### オブジェクト ストア内のすべてのキーと値のペアを削除する  

1.  [IndexedDB オブジェクト ストアを表示します](#view-indexeddb-data)。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-clear-object-store.msft.png" alt-text="オブジェクト ストアを表示する" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-clear-object-store.msft.png":::
       オブジェクト ストアを表示する  
    :::image-end:::  
    
1.  Choose **Clear object store** \( Clear object store ![ ][ImageClearIcon] \).  
    
### IndexedDB データベースを削除する  

1.  [削除する IndexedDB](#view-indexeddb-data) データベースを表示します。  
1.  Choose **Delete database**.  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-delete-database.msft.png" alt-text="[データベースの削除] ボタン" lightbox="../media/storage-application-storage-indexeddb-notes_db-delete-database.msft.png":::
       [ **データベースの削除]** ボタン  
    :::image-end:::  
    
### すべての IndexedDB ストレージを削除する  

1.  [記憶域の **クリア] ウィンドウを開** きます。  
1.  **[IndexedDB] チェック ボックスが有効**になっていることを確認します。  
1.  [サイト **データのクリア] を選択します**。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-indexeddb-clear-site-data.msft.png" alt-text="[記憶域のクリア] ウィンドウ" lightbox="../media/storage-application-clear-storage-indexeddb-clear-site-data.msft.png":::
       [ **記憶域のクリア]** ウィンドウ  
    :::image-end:::  
    
## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDatabaseIcon]: ../media/database-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  
[ImageObjectStoreIcon]: ../media/object-store-icon.msft.png  
[ImageReloadIcon]: ../media/reload-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft Docs"  
[DevtoolsJavascriptSnippets]: ../javascript/snippets.md "Microsoft Edge DevTools を使用して任意のページで JavaScript のスニペットを実行する |Microsoft Docs"  

[ChromiumIssue943770]: https://crbug.com/943770 "943770 - DevTools: iframe IndexedDB データベースの表示 - chromium - Monorail"  

[MDNBasicConceptsKeyGenerator]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Basic_Concepts_Behind_IndexedDB#gloss_keygenerator "キー ジェネレーター - 基本的な概念 |MDN"  
[MDNIndexedDBAPI]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API "IndexedDB API |MDN"  
[MDNUsingIndexedDB]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB "IndexedDB の使用 |MDN"  
[MDNUsingIndexedDBUsingIndex]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Using_an_index "インデックスを使用する - IndexedDB を使用する |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/indexeddb) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
