---
description: アプリケーション パネルとスニペットを使用して IndexedDB データを表示および変更する方法。
title: DevTools を使用して IndexedDB データを表示Microsoft Edge変更する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: b0927ab436d1278f50b0dee099ba3526e5506762
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564806"
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
# <a name="view-and-change-indexeddb-data-with-microsoft-edge-devtools"></a>DevTools を使用して IndexedDB データを表示Microsoft Edge変更する  

このガイドでは、DevTools を使用して[IndexedDB Microsoft Edgeを][MicrosoftEdgeDevTools]表示および変更する方法[を示][MDNIndexedDBAPI]します。  DevTools に精通している必要があります。  また、IndexedDB に精通している必要があります。  使用しない場合は [、[IndexedDB の使用] に移動します][MDNUsingIndexedDB]。  

## <a name="view-indexeddb-data"></a>IndexedDB データの表示  

1.  [アプリケーション] **タブを** 選択して、[アプリケーション] ツール **を開** きます。  通常 **、マニフェスト ウィンドウ** は既定で開きます。  
    
    :::image type="complex" source="../media/storage-application-manifest-empty.msft.png" alt-text="[マニフェスト] ウィンドウ" lightbox="../media/storage-application-manifest-empty.msft.png":::
       [ **マニフェスト]** ウィンドウ  
    :::image-end:::  
    
1.  **[IndexedDB] メニューを展開**して、使用可能なデータベースを確認します。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb.msft.png" alt-text="IndexedDB メニュー" lightbox="../media/storage-application-storage-indexeddb.msft.png":::
       **IndexedDB**メニュー  
    :::image-end:::  
    
    *   \( Database icon \) は、データベースの名前であり、データベースにアクセスする元であるデータベース ![ ](../media/database-icon.msft.png) `notes - https://mdn.github.io` `notes` `https://mdn.github.io` を表します。  
    *   \( ![ Object Store icon ](../media/object-store-icon.msft.png) \) `notes` はオブジェクト ストアです。  
    *   **title**と**body は**[インデックス です][MDNUsingIndexedDBUsingIndex]。  
    
    > [!NOTE]
    > **既知の制限**  サード パーティ製のデータベースは表示されません。  たとえば、a を使用してページに広告を埋め込み、広告ネットワークが IndexedDB を使用している場合、広告ネットワークの `<iframe>` IndexedDB データは表示されません。  [問題] に [移動#943770][ChromiumIssue943770]します。  
    
1.  データベースを選択して、元の番号とバージョン番号を確認します。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db.msft.png" alt-text="メモ データベース" lightbox="../media/storage-application-storage-indexeddb-notes_db.msft.png":::
       メモ**データベース**  
    :::image-end:::  
    
1.  キーと値のペアを確認するには、オブジェクト ストアを選択します。  
    
    > [!NOTE]
    > IndexedDB データはリアルタイムで更新されません。  [インデックス付 [きDB データの更新] に移動します](#refresh-indexeddb-data)。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os.msft.png" alt-text="notes オブジェクト ストア" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os.msft.png":::
       notes **オブジェクト** ストア  
    :::image-end:::  
    
    *   **合計エントリは** 、オブジェクト ストア内のキーと値のペアの総数です。  
    *   **キー ジェネレーターの値は** 、次に使用可能なキーです。  このフィールドは、キー ジェネレーターを使用 [する場合にのみ表示されます][MDNBasicConceptsKeyGenerator]。  
    
1.  [値] 列の **セルを選択** して、値を展開します。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-edge-chromium.msft.png" alt-text="IndexedDB 値の表示" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-edge-chromium.msft.png":::
       **IndexedDB 値の**表示  
    :::image-end:::  
    
1.  次の図のタイトルや**** 本文などの**** インデックスを選択して、そのインデックスの値に従ってオブジェクト ストアを並べ替える。  
   
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-title.msft.png" alt-text="インデックスでオブジェクト ストアを並べ替える" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-title.msft.png":::
       インデックスでオブジェクト ストアを並べ替える  
    :::image-end:::  
    
## <a name="refresh-indexeddb-data"></a>IndexedDB データの更新  

アプリケーション ツールの IndexedDB **値** はリアルタイムで更新されません。  オブジェクト**ストアを表示**してデータを更新する場合は [Refresh \( Refresh \)] を選択するか、データベースを表示して [データベースの更新] を選択してすべてのデータ ![ ](../media/reload-icon.msft.png) を更新します。 ****  

:::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-refresh-database.msft.png" alt-text="データベースの表示" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-refresh-database.msft.png":::
   データベースの表示  
:::image-end:::  

## <a name="edit-indexeddb-data"></a>IndexedDB データの編集  

IndexedDB キーと値は、アプリケーション ツールでは **編集** できません。  ただし、DevTools はページ コンテキストにアクセスできますので、DevTools 内で JavaScript コードを実行して IndexedDB データを編集できます。  

### <a name="edit-indexeddb-data-with-snippets"></a>スニペットを使用して IndexedDB データを編集する  

[スニペットは][DevtoolsJavascriptSnippets] 、DevTools 内で JavaScript コードのブロックを格納および実行する方法です。  スニペットを実行すると、結果はコンソールに記録 **されます**。  スニペットを使用して JavaScript コードを実行して IndexedDB データベースを編集できます。  

:::image type="complex" source="../media/storage-sources-snippets-indexeddb-output.msft.png" alt-text="スニペットを使用して IndexedDB を操作する" lightbox="../media/storage-sources-snippets-indexeddb-output.msft.png":::
   スニペットを使用して IndexedDB を操作する  
:::image-end:::  

## <a name="delete-indexeddb-data"></a>IndexedDB データの削除  

### <a name="delete-an-indexeddb-key-value-pair"></a>IndexedDB キーと値のペアを削除する  

1.  [IndexedDB オブジェクト ストアを表示します](#view-indexeddb-data)。  
1.  削除するキーと値のペアを選択します。  DevTools では強調表示され、選択されているかどうかを示します。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os2.msft.png" alt-text="キーと値のペアを選択して削除する" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os2.msft.png":::
       キーと値のペアを選択して削除する  
    :::image-end:::  
    
1.  キーを `Delete` 選択するか、[ **選択した \(** Delete ![ Selected \) を削除する] ](../media/delete-icon.msft.png) を選択します。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-delete-selected.msft.png" alt-text="キーと値のペアが削除された後のオブジェクト ストアの外観" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-delete-selected.msft.png":::
       キーと値のペアが削除された後のオブジェクト ストアの外観  
    :::image-end:::  
    
### <a name="delete-all-key-value-pairs-in-an-object-store"></a>オブジェクト ストア内のすべてのキーと値のペアを削除する  

1.  [IndexedDB オブジェクト ストアを表示します](#view-indexeddb-data)。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-clear-object-store.msft.png" alt-text="オブジェクト ストアの表示" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-clear-object-store.msft.png":::
       オブジェクト ストアの表示  
    :::image-end:::  
    
1.  [ **オブジェクト ストアのクリア** ] \( ![ Clear object store ](../media/clear-icon.msft.png) \) を選択します。  
    
### <a name="delete-an-indexeddb-database"></a>IndexedDB データベースの削除  

1.  [削除する IndexedDB](#view-indexeddb-data) データベースを表示します。  
1.  [データベース **の削除] を選択します**。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-delete-database.msft.png" alt-text="[データベースの削除] ボタン" lightbox="../media/storage-application-storage-indexeddb-notes_db-delete-database.msft.png":::
       [ **データベースの削除]** ボタン  
    :::image-end:::  
    
### <a name="delete-all-indexeddb-storage"></a>すべての IndexedDB ストレージを削除する  

1.  [ストレージの **クリア] ウィンドウを開** きます。  
1.  **[IndexedDB] チェック ボックスが有効**になっていることを確認します。  
1.  [サイト **データのクリア] を選択します**。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-indexeddb-clear-site-data.msft.png" alt-text="[ストレージのクリア] ウィンドウ" lightbox="../media/storage-application-clear-storage-indexeddb-clear-site-data.msft.png":::
       [ **ストレージのクリア]** ウィンドウ  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft Docs"  
[DevtoolsJavascriptSnippets]: ../javascript/snippets.md "DevTools を使用して任意のページで JavaScript のスニペットMicrosoft Edge実行|Microsoft Docs"  

[ChromiumIssue943770]: https://crbug.com/943770 "943770 - DevTools: show iframe IndexedDB データベース - クロム - Monorail"  

[MDNBasicConceptsKeyGenerator]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Basic_Concepts_Behind_IndexedDB#gloss_keygenerator "キー ジェネレーター - 基本概念|MDN"  
[MDNIndexedDBAPI]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API "IndexedDB API |MDN"  
[MDNUsingIndexedDB]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB "IndexedDB の使用|MDN"  
[MDNUsingIndexedDBUsingIndex]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Using_an_index "インデックスの使用 - IndexedDB を使用|MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/indexeddb) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
