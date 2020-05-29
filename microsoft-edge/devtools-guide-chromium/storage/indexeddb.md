---
title: Microsoft Edge DevTools を使用して IndexedDB データを表示および変更する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 4eca78dcd92048d75f8488fddc7b210da68690df
ms.sourcegitcommit: ad68bfbb355f6cfdaaf6612b77ea3985d4d6a58b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "10612089"
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

  

このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使って[インデックス eddb][MDNIndexedDBAPI]データを表示および変更する方法について説明します。  これは、DevTools に精通していることを前提としています。  また、IndexedDB に精通していることを前提としています。  表示されない場合は、「 [IndexedDB を使用する][MDNUsingIndexedDB]」を参照してください。  

## IndexedDB データの表示   

1.  [**アプリケーション**] タブを選択して、[**アプリケーション**] パネルを開きます。  通常、**マニフェスト**ウィンドウは既定で開かれます。  
    
    > ##### 図 1  
    > マニフェストウィンドウ  
    > ![マニフェストウィンドウ][ImageManifest]  

1.  [ **Indexeddb** ] メニューを展開して、利用可能なデータベースを確認します。  
    
    > ##### 図 2  
    > **Indexeddb**メニュー  
    > ![IndexedDB メニュー][ImageIndexedDBMenu]  
    
    *   ![データベースアイコンは、データベース ][ImageDatabaseIcon] `notes - https://mdn.github.io` の名前を表し、データベースに `notes` `https://mdn.github.io` アクセスする元の場所です。  
    *   ![オブジェクトストアアイコン ][ImageObjectStoreIcon] `notes` はオブジェクトストアです。  
    *   **タイトル**と**本文**は[インデックス][MDNUsingIndexedDBUsingIndex]です。  
    
    > [!NOTE]
    > **既知の制限** サードパーティデータベースは表示されません。  たとえば、 `<iframe>` を使って広告をページに埋め込む場合、広告ネットワークで IndexedDB を使用している場合、広告ネットワークの indexeddb データは表示されません。  [#943770 問題][ChromiumIssue943770]を参照してください。  
    
1.  起点とバージョン番号を確認するには、データベースを選択します。  
    
    > ##### 図 3  
    > **ノーツ**データベース  
    > ![ノーツデータベース][ImageIndexedDBDatabase]  
    
1.  キーと値のペアを表示するオブジェクトストアを選択します。  
    
    > [!NOTE]
    > IndexedDB データは、リアルタイムでは更新されません。  「 [IndexedDB データを更新](#refresh-indexeddb-data)する」をご覧ください。  
    
    > ##### 図 4  
    > **ノーツ**オブジェクトストア  
    > ![ノーツオブジェクトストア][ImageIndexedDBObjectStore]  

    *   **Total entries**は、オブジェクトストアのキーと値のペアの合計数です。  
    *   **キージェネレーターの値**は、次に使用可能なキーです。  このフィールドは、[キージェネレーター][MDNBasicConceptsKeyGenerator]を使用している場合にのみ表示されます。  

1.  [**値**] 列のセルを選択して、その値を展開します。  
    
    > ##### 図 5  
    > IndexedDB 値の表示  
    > ![IndexedDB 値の表示][ImageIndexedBDValue]  
    
1.  [図 6](#figure-6)の [**タイトル**] や [**本文**] などのインデックスを選択し、そのインデックスの値に従ってオブジェクトストアを並べ替えます。  
   
    > ##### 図 6  
    > **タイトル**キーに従ってアルファベット順に並べ替えられたオブジェクトストア  
    > ![インデックスによるオブジェクトストアの並べ替え][ImageIndexedDBIndex]  

## IndexedDB データを更新する   

**アプリケーション**パネルの IndexedDB 値は、リアルタイムでは更新されません。  **Refresh** ![ オブジェクトストアを表示してデータを ][ImageReloadIcon] 更新するか、データベースを表示し、[**データベースの更新**] をクリックしてすべてのデータを更新するには、[更新更新] を選択します。  

> ##### 図 7  
> データベースの表示  
> ![データベースの表示][ImageIndexedDBDatabase2]  

## IndexedDB データを編集する   

IndexedDB キーと値は、**アプリケーション**パネルから編集できません。  DevTools にはページのコンテキストへのアクセスがあります。ただし、DevTools 内では、IndexedDB データを編集するための JavaScript コードを実行することができます。  

### スニペットを使用して IndexedDB データを編集する   

[スニペット][DevtoolsJavascriptSnippets]は、devtools 内に JavaScript コードのブロックを保存して実行するための手段です。  スニペットを実行すると、結果が**コンソール**に記録されます。  スニペットを使って、IndexedDB データベースを編集する JavaScript コードを実行することができます。  

> ##### 図 8  
> スニペットを使った IndexedDB の操作  
> ![スニペットを使った IndexedDB の操作][ImageIndexedDBSnippet]  

## IndexedDB データを削除する   

### IndexedDB キーと値のペアを削除する   

1.  [IndexedDB オブジェクトストアを表示](#view-indexeddb-data)します。  
1.  削除するキーと値のペアを選択します。  DevTools では、選択されていることを示すように強調表示されます。  
    
    > ##### 図 9  
    > キーと値のペアを選択して削除する  
    > ![キーと値のペアを選択して削除する][ImageIndexedDBKeyValuePair]  

1.  キーを押すか、[選択した `Delete` 削除の削除] をクリックし**Delete Selected** ![ ][ImageDeleteIcon] ます。  
    
    > ##### 図 10  
    > キーと値のペアが削除された後のオブジェクトストアの外観  
    > ![キーと値のペアが削除された後のオブジェクトストアの外観][ImageIndexedDBKeyValuePairDeleted]  

### オブジェクトストア内のすべてのキーと値のペアを削除する   

1.  [IndexedDB オブジェクトストアを表示](#view-indexeddb-data)します。  
    
    > ##### 図 11  
    > オブジェクトストアの表示  
    > ![オブジェクトストアの表示][ImageIndexedDBObjectStore]  

1.  [ **Clear object store** clear object store] を選び ![ ][ImageClearIcon] ます。  

### IndexedDB データベースを削除する   

1.  削除する[IndexedDB データベースを表示](#view-indexeddb-data)します。  
1.  [**データベースの削除**] を選びます。  
    
    > ##### 図 12  
    > [**データベースの削除**] ボタン  
    > ![[データベースの削除] ボタン][ImageIndexedDBDatabase]  

### すべての IndexedDB ストレージを削除します   

1.  [**記憶域のクリア**] ウィンドウを開く。  

1.  [ **Indexeddb** ] チェックボックスがオンになっていることを確認します。  

1.  [**サイトデータのクリア**] を選びます。  
    
    > ##### 図 13  
    > [**記憶域**のクリア] ウィンドウ ![][ImageIndexedDBClearStorage]  

 



<!-- image links -->  

[ImageClearIcon]: /microsoft-edge/devtools-guide-chromium/media/clear-icon.msft.png  
[ImageDatabaseIcon]: /microsoft-edge/devtools-guide-chromium/media/database-icon.msft.png  
[ImageDeleteIcon]: /microsoft-edge/devtools-guide-chromium/media/delete-icon.msft.png  
[ImageObjectStoreIcon]: /microsoft-edge/devtools-guide-chromium/media/object-store-icon.msft.png  
[ImageReloadIcon]: /microsoft-edge/devtools-guide-chromium/media/reload-icon.msft.png  

[ImageManifest]: /microsoft-edge/devtools-guide-chromium/media/storage-application-manifest-empty.msft.png "図 1: [マニフェスト] ウィンドウ"  
[ImageIndexedDBMenu]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-indexeddb.msft.png "図 2: IndexedDB メニュー"  
[ImageIndexedDBDatabase]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-indexeddb-notes_db.msft.png "図 3: notes_db データベース"  
[ImageIndexedDBObjectStore]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-indexeddb-notes_db-notes_os.msft.png "図 4: notes_os オブジェクトストア"  
[ImageIndexedBDValue]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-indexeddb-notes_db-notes_os-edge-chromium.msft.png "図 5: IndexedDB 値の表示"  
[ImageIndexedDBIndex]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-indexeddb-notes_db-notes_os-title.msft.png "図 6: インデックスによるオブジェクトストアの並べ替え"  
[ImageIndexedDBDatabase2]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-indexeddb-notes_db-notes_os-refresh-database.msft.png "図 7: データベースの表示"  
[ImageIndexedDBSnippet]: /microsoft-edge/devtools-guide-chromium/media/storage-sources-snippets-indexeddb-output.msft.png "図 8: スニペットを使った IndexedDB の操作"  
[ImageIndexedDBKeyValuePair]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-indexeddb-notes_db-notes_os2.msft.png "図 9: キーと値のペアを選択して削除する"  
[ImageIndexedDBKeyValuePairDeleted]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-indexeddb-notes_db-notes_os-delete-selected.msft.png "図 10: キーと値のペアが削除された後のオブジェクトストアの外観"  
[ImageIndexedDBObjectStore]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-indexeddb-notes_db-notes_os-clear-object-store.msft.png "図 11: オブジェクトストアの表示"  
[ImageIndexedDBDatabase]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-indexeddb-notes_db-delete-database.msft.png "図 12: [データベースの削除] ボタン"  
[ImageIndexedDBClearStorage]: /microsoft-edge/devtools-guide-chromium/media/storage-application-clear-storage-indexeddb-clear-site-data.msft.png "図 13: [記憶域のクリア] ウィンドウ"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  
[DevtoolsJavascriptSnippets]: /microsoft-edge/devtools-guide-chromium/javascript/snippets "Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。"  

[ChromiumIssue943770]: https://crbug.com/943770 "943770-DevTools: iframe Indexindexeddb データベースの表示-chromium-Monorail"  

[MDNBasicConceptsKeyGenerator]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Basic_Concepts_Behind_IndexedDB#gloss_keygenerator "キージェネレーター-基本的な概念 |MDN"  
[MDNIndexedDBAPI]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API "IndexedDB API |MDN"  
[MDNUsingIndexedDB]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB "IndexedDB を使用する |MDN"  
[MDNUsingIndexedDBUsingIndex]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Using_an_index "インデックスの使用-IndexedDB を使っています。 |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/storage/indexeddb)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
