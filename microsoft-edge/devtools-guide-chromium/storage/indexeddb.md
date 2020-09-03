---
description: アプリケーションパネルとスニペットを使って、IndexedDB データを表示および変更する方法について説明します。
title: Microsoft Edge DevTools を使用して IndexedDB データを表示および変更する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 6b1209ddcbfac305535d9d61e001441dbf61b6ec
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993563"
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

  

このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使って [インデックス eddb][MDNIndexedDBAPI] データを表示および変更する方法について説明します。  これは、DevTools に精通していることを前提としています。  また、IndexedDB に精通していることを前提としています。  表示されない場合は、「 [IndexedDB を使用する][MDNUsingIndexedDB]」を参照してください。  

## IndexedDB データの表示   

1.  [ **アプリケーション** ] タブを選択して、[ **アプリケーション** ] パネルを開きます。  通常、 **マニフェスト** ウィンドウは既定で開かれます。  
    
    :::image type="complex" source="../media/storage-application-manifest-empty.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-manifest-empty.msft.png":::
       **マニフェスト**ウィンドウ  
    :::image-end:::  
    
1.  [ **Indexeddb** ] メニューを展開して、利用可能なデータベースを確認します。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb.msft.png" alt-text="IndexedDB メニュー" lightbox="../media/storage-application-storage-indexeddb.msft.png":::
       **Indexeddb**メニュー  
    :::image-end:::  
    
    *   \ ( ![ データベースアイコン \) は、データベースの名前であり、 ][ImageDatabaseIcon] `notes - https://mdn.github.io` `notes` `https://mdn.github.io` データベースにアクセスする元のデータベースを表します。  
    *   \ ( ![ オブジェクトストアアイコン ][ImageObjectStoreIcon] \) `notes` はオブジェクトストアです。  
    *   **タイトル** と **本文** は [インデックス][MDNUsingIndexedDBUsingIndex]です。  
    
    > [!NOTE]
    > **既知の制限**  サードパーティデータベースは表示されません。  たとえば、 `<iframe>` を使って広告をページに埋め込む場合、広告ネットワークで IndexedDB を使用している場合、広告ネットワークの indexeddb データは表示されません。  [#943770 問題][ChromiumIssue943770]を参照してください。  
    
1.  起点とバージョン番号を確認するには、データベースを選択します。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db.msft.png" alt-text="ノーツデータベース" lightbox="../media/storage-application-storage-indexeddb-notes_db.msft.png":::
       **ノーツ**データベース  
    :::image-end:::  
    
1.  キーと値のペアを表示するオブジェクトストアを選択します。  
    
    > [!NOTE]
    > IndexedDB データは、リアルタイムでは更新されません。  「 [IndexedDB データを更新](#refresh-indexeddb-data)する」をご覧ください。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os.msft.png" alt-text="ノーツオブジェクトストア" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os.msft.png":::
       **ノーツ**オブジェクトストア  
    :::image-end:::  
    
    *   **Total entries** は、オブジェクトストアのキーと値のペアの合計数です。  
    *   **キージェネレーターの値** は、次に使用可能なキーです。  このフィールドは、 [キージェネレーター][MDNBasicConceptsKeyGenerator]を使用している場合にのみ表示されます。  
    
1.  [ **値** ] 列のセルを選択して、その値を展開します。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-edge-chromium.msft.png" alt-text="IndexedDB 値の表示" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-edge-chromium.msft.png":::
       **Indexeddb**値の表示  
    :::image-end:::  
    
1.  次の図の [ **タイトル** ] や [ **本文** ] などのインデックスを選択し、そのインデックスの値に従ってオブジェクトストアを並べ替えます。  
   
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-title.msft.png" alt-text="インデックスによるオブジェクトストアの並べ替え" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-title.msft.png":::
       インデックスによるオブジェクトストアの並べ替え  
    :::image-end:::  
    
## IndexedDB データを更新する   

**アプリケーション**パネルの IndexedDB 値は、リアルタイムでは更新されません。  オブジェクト**Refresh**ストアを表示して ![ データを ][ImageReloadIcon] 更新するか、データベースを表示し、[**データベースの更新**] をクリックしてすべてのデータを更新するには、[更新] を選択します。  

:::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-refresh-database.msft.png" alt-text="データベースの表示" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-refresh-database.msft.png":::
   データベースの表示  
:::image-end:::  

## IndexedDB データを編集する   

IndexedDB キーと値は、 **アプリケーション** パネルから編集できません。  DevTools にはページのコンテキストへのアクセスがあります。ただし、DevTools 内では、IndexedDB データを編集するための JavaScript コードを実行することができます。  

### スニペットを使用して IndexedDB データを編集する   

[スニペット][DevtoolsJavascriptSnippets] は、devtools 内に JavaScript コードのブロックを保存して実行するための手段です。  スニペットを実行すると、結果が **コンソール**に記録されます。  スニペットを使って、IndexedDB データベースを編集する JavaScript コードを実行することができます。  

:::image type="complex" source="../media/storage-sources-snippets-indexeddb-output.msft.png" alt-text="スニペットを使って IndexedDB を操作する" lightbox="../media/storage-sources-snippets-indexeddb-output.msft.png":::
   スニペットを使って IndexedDB を操作する  
:::image-end:::  

## IndexedDB データを削除する   

### IndexedDB キーと値のペアを削除する   

1.  [IndexedDB オブジェクトストアを表示](#view-indexeddb-data)します。  
1.  削除するキーと値のペアを選択します。  DevTools では、選択されていることを示すように強調表示されます。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os2.msft.png" alt-text="キーと値のペアを選択して削除する" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os2.msft.png":::
       キーと値のペアを選択して削除する  
    :::image-end:::  
    
1.  キーを押す `Delete` か、[ **選択した** ものを削除] をクリックし ![ ます (選択した \ を削除 ][ImageDeleteIcon] )。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-delete-selected.msft.png" alt-text="キーと値のペアが削除された後のオブジェクトストアの外観" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-delete-selected.msft.png":::
       キーと値のペアが削除された後のオブジェクトストアの外観  
    :::image-end:::  
    
### オブジェクトストア内のすべてのキーと値のペアを削除する   

1.  [IndexedDB オブジェクトストアを表示](#view-indexeddb-data)します。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-clear-object-store.msft.png" alt-text="オブジェクトストアの表示" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-clear-object-store.msft.png":::
       オブジェクトストアの表示  
    :::image-end:::  
    
1.  [ **Clear object store** (オブジェクトストアをクリア)] を選び ![ ][ImageClearIcon] ます。  
    
### IndexedDB データベースを削除する   

1.  削除する[IndexedDB データベースを表示](#view-indexeddb-data)します。  
1.  [ **データベースの削除**] を選びます。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-delete-database.msft.png" alt-text="[データベースの削除] ボタン" lightbox="../media/storage-application-storage-indexeddb-notes_db-delete-database.msft.png":::
       [ **データベースの削除** ] ボタン  
    :::image-end:::  
    
### すべての IndexedDB ストレージを削除します   

1.  [ **記憶域のクリア** ] ウィンドウを開く。  
1.  [ **Indexeddb** ] チェックボックスがオンになっていることを確認します。  
1.  [ **サイトデータのクリア**] を選びます。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-indexeddb-clear-site-data.msft.png" alt-text="[記憶域のクリア] ウィンドウ" lightbox="../media/storage-application-clear-storage-indexeddb-clear-site-data.msft.png":::
       [ **記憶域のクリア** ] ウィンドウ  
    :::image-end:::  
    
<!--  
 


-->  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDatabaseIcon]: ../media/database-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  
[ImageObjectStoreIcon]: ../media/object-store-icon.msft.png  
[ImageReloadIcon]: ../media/reload-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevtoolsJavascriptSnippets]: ../javascript/snippets.md "Microsoft Edge DevTools を使用して、任意のページで JavaScript のスニペットを実行します。Microsoft ドキュメント"  

[ChromiumIssue943770]: https://crbug.com/943770 "943770-DevTools: iframe Indexindexeddb データベースの表示-chromium-Monorail"  

[MDNBasicConceptsKeyGenerator]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Basic_Concepts_Behind_IndexedDB#gloss_keygenerator "キージェネレーター-基本的な概念 |MDN"  
[MDNIndexedDBAPI]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API "IndexedDB API |MDN"  
[MDNUsingIndexedDB]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB "IndexedDB を使用する |MDN"  
[MDNUsingIndexedDBUsingIndex]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Using_an_index "インデックスの使用-IndexedDB を使っています。 |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/indexeddb) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
