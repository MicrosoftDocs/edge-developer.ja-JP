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





# <span data-ttu-id="95f85-103">Microsoft Edge DevTools を使用して IndexedDB データを表示および変更する</span><span class="sxs-lookup"><span data-stu-id="95f85-103">View And Change IndexedDB Data With Microsoft Edge DevTools</span></span>   

  

<span data-ttu-id="95f85-104">このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使って[インデックス eddb][MDNIndexedDBAPI]データを表示および変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="95f85-104">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view and change [IndexedDB][MDNIndexedDBAPI] data.</span></span>  <span data-ttu-id="95f85-105">これは、DevTools に精通していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="95f85-105">It assumes you are familiar with DevTools.</span></span>  <span data-ttu-id="95f85-106">また、IndexedDB に精通していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="95f85-106">It also assumes you are familiar with IndexedDB.</span></span>  <span data-ttu-id="95f85-107">表示されない場合は、「 [IndexedDB を使用する][MDNUsingIndexedDB]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95f85-107">If not, see [Using IndexedDB][MDNUsingIndexedDB].</span></span>  

## <span data-ttu-id="95f85-108">IndexedDB データの表示</span><span class="sxs-lookup"><span data-stu-id="95f85-108">View IndexedDB data</span></span>   

1.  <span data-ttu-id="95f85-109">[**アプリケーション**] タブを選択して、[**アプリケーション**] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="95f85-109">Select the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="95f85-110">通常、**マニフェスト**ウィンドウは既定で開かれます。</span><span class="sxs-lookup"><span data-stu-id="95f85-110">The **Manifest** pane usually opens by default.</span></span>  
    
    > ##### <span data-ttu-id="95f85-111">図 1</span><span class="sxs-lookup"><span data-stu-id="95f85-111">Figure 1</span></span>  
    > <span data-ttu-id="95f85-112">マニフェストウィンドウ</span><span class="sxs-lookup"><span data-stu-id="95f85-112">The Manifest pane</span></span>  
    > ![マニフェストウィンドウ][ImageManifest]  

1.  <span data-ttu-id="95f85-114">[ **Indexeddb** ] メニューを展開して、利用可能なデータベースを確認します。</span><span class="sxs-lookup"><span data-stu-id="95f85-114">Expand the **IndexedDB** menu to see which databases are available.</span></span>  
    
    > ##### <span data-ttu-id="95f85-115">図 2</span><span class="sxs-lookup"><span data-stu-id="95f85-115">Figure 2</span></span>  
    > <span data-ttu-id="95f85-116">**Indexeddb**メニュー</span><span class="sxs-lookup"><span data-stu-id="95f85-116">The **IndexedDB** menu</span></span>  
    > ![IndexedDB メニュー][ImageIndexedDBMenu]  
    
    *   ![<span data-ttu-id="95f85-118">データベースアイコンは、データベース ][ImageDatabaseIcon] `notes - https://mdn.github.io` の名前を表し、データベースに `notes` `https://mdn.github.io` アクセスする元の場所です。</span><span class="sxs-lookup"><span data-stu-id="95f85-118">Database icon][ImageDatabaseIcon] `notes - https://mdn.github.io` represents a database, where `notes` is the name of the database and `https://mdn.github.io` is the origin that accesses the database.</span></span>  
    *   ![<span data-ttu-id="95f85-119">オブジェクトストアアイコン ][ImageObjectStoreIcon] `notes` はオブジェクトストアです。</span><span class="sxs-lookup"><span data-stu-id="95f85-119">Object Store icon][ImageObjectStoreIcon] `notes` is an object store.</span></span>  
    *   <span data-ttu-id="95f85-120">**タイトル**と**本文**は[インデックス][MDNUsingIndexedDBUsingIndex]です。</span><span class="sxs-lookup"><span data-stu-id="95f85-120">**title** and **body** are [indexes][MDNUsingIndexedDBUsingIndex].</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="95f85-121">**既知の制限** サードパーティデータベースは表示されません。</span><span class="sxs-lookup"><span data-stu-id="95f85-121">**Known Limitation**  Third-party databases are not visible.</span></span>  <span data-ttu-id="95f85-122">たとえば、 `<iframe>` を使って広告をページに埋め込む場合、広告ネットワークで IndexedDB を使用している場合、広告ネットワークの indexeddb データは表示されません。</span><span class="sxs-lookup"><span data-stu-id="95f85-122">For example, if you use an `<iframe>` to embed an ad on your page, and your ad network uses IndexedDB, the IndexedDB data for your ad network is not be visible.</span></span>  <span data-ttu-id="95f85-123">[#943770 問題][ChromiumIssue943770]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95f85-123">See [issue #943770][ChromiumIssue943770].</span></span>  
    
1.  <span data-ttu-id="95f85-124">起点とバージョン番号を確認するには、データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="95f85-124">Select a database to see the origin and version number.</span></span>  
    
    > ##### <span data-ttu-id="95f85-125">図 3</span><span class="sxs-lookup"><span data-stu-id="95f85-125">Figure 3</span></span>  
    > <span data-ttu-id="95f85-126">**ノーツ**データベース</span><span class="sxs-lookup"><span data-stu-id="95f85-126">The **notes** database</span></span>  
    > ![ノーツデータベース][ImageIndexedDBDatabase]  
    
1.  <span data-ttu-id="95f85-128">キーと値のペアを表示するオブジェクトストアを選択します。</span><span class="sxs-lookup"><span data-stu-id="95f85-128">Select an object store to see the key-value pairs.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="95f85-129">IndexedDB データは、リアルタイムでは更新されません。</span><span class="sxs-lookup"><span data-stu-id="95f85-129">IndexedDB data does not update in real-time.</span></span>  <span data-ttu-id="95f85-130">「 [IndexedDB データを更新](#refresh-indexeddb-data)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="95f85-130">See [Refresh IndexedDB data](#refresh-indexeddb-data).</span></span>  
    
    > ##### <span data-ttu-id="95f85-131">図 4</span><span class="sxs-lookup"><span data-stu-id="95f85-131">Figure 4</span></span>  
    > <span data-ttu-id="95f85-132">**ノーツ**オブジェクトストア</span><span class="sxs-lookup"><span data-stu-id="95f85-132">The **notes** object store</span></span>  
    > ![ノーツオブジェクトストア][ImageIndexedDBObjectStore]  

    *   <span data-ttu-id="95f85-134">**Total entries**は、オブジェクトストアのキーと値のペアの合計数です。</span><span class="sxs-lookup"><span data-stu-id="95f85-134">**Total entries** is the total number of key-value pairs in the object store.</span></span>  
    *   <span data-ttu-id="95f85-135">**キージェネレーターの値**は、次に使用可能なキーです。</span><span class="sxs-lookup"><span data-stu-id="95f85-135">**Key generator value** is the next available key.</span></span>  <span data-ttu-id="95f85-136">このフィールドは、[キージェネレーター][MDNBasicConceptsKeyGenerator]を使用している場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="95f85-136">This field is only shown when using [key generators][MDNBasicConceptsKeyGenerator].</span></span>  

1.  <span data-ttu-id="95f85-137">[**値**] 列のセルを選択して、その値を展開します。</span><span class="sxs-lookup"><span data-stu-id="95f85-137">Select a cell in the **Value** column to expand that value.</span></span>  
    
    > ##### <span data-ttu-id="95f85-138">図 5</span><span class="sxs-lookup"><span data-stu-id="95f85-138">Figure 5</span></span>  
    > <span data-ttu-id="95f85-139">IndexedDB 値の表示</span><span class="sxs-lookup"><span data-stu-id="95f85-139">Viewing an IndexedDB value</span></span>  
    > ![IndexedDB 値の表示][ImageIndexedBDValue]  
    
1.  <span data-ttu-id="95f85-141">[図 6](#figure-6)の [**タイトル**] や [**本文**] などのインデックスを選択し、そのインデックスの値に従ってオブジェクトストアを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="95f85-141">Select an index, such as **title** or **body** in [Figure 6](#figure-6), to sort the object store according to the values of that index.</span></span>  
   
    > ##### <span data-ttu-id="95f85-142">図 6</span><span class="sxs-lookup"><span data-stu-id="95f85-142">Figure 6</span></span>  
    > <span data-ttu-id="95f85-143">**タイトル**キーに従ってアルファベット順に並べ替えられたオブジェクトストア</span><span class="sxs-lookup"><span data-stu-id="95f85-143">An object store that is sorted alphabetically according to the **title** key</span></span>  
    > ![インデックスによるオブジェクトストアの並べ替え][ImageIndexedDBIndex]  

## <span data-ttu-id="95f85-145">IndexedDB データを更新する</span><span class="sxs-lookup"><span data-stu-id="95f85-145">Refresh IndexedDB data</span></span>   

<span data-ttu-id="95f85-146">**アプリケーション**パネルの IndexedDB 値は、リアルタイムでは更新されません。</span><span class="sxs-lookup"><span data-stu-id="95f85-146">IndexedDB values in the **Application** panel do not update in real-time.</span></span>  <span data-ttu-id="95f85-147">**Refresh** ![ オブジェクトストアを表示してデータを ][ImageReloadIcon] 更新するか、データベースを表示し、[**データベースの更新**] をクリックしてすべてのデータを更新するには、[更新更新] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95f85-147">Select **Refresh** ![Refresh][ImageReloadIcon] when viewing an object store to refresh the data, or view a database and click **Refresh database** to refresh all data.</span></span>  

> ##### <span data-ttu-id="95f85-148">図 7</span><span class="sxs-lookup"><span data-stu-id="95f85-148">Figure 7</span></span>  
> <span data-ttu-id="95f85-149">データベースの表示</span><span class="sxs-lookup"><span data-stu-id="95f85-149">Viewing a database</span></span>  
> ![データベースの表示][ImageIndexedDBDatabase2]  

## <span data-ttu-id="95f85-151">IndexedDB データを編集する</span><span class="sxs-lookup"><span data-stu-id="95f85-151">Edit IndexedDB data</span></span>   

<span data-ttu-id="95f85-152">IndexedDB キーと値は、**アプリケーション**パネルから編集できません。</span><span class="sxs-lookup"><span data-stu-id="95f85-152">IndexedDB keys and values are not editable from the **Application** panel.</span></span>  <span data-ttu-id="95f85-153">DevTools にはページのコンテキストへのアクセスがあります。ただし、DevTools 内では、IndexedDB データを編集するための JavaScript コードを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="95f85-153">Since DevTools has access to page context, however, you may run JavaScript code within DevTools to edit IndexedDB data.</span></span>  

### <span data-ttu-id="95f85-154">スニペットを使用して IndexedDB データを編集する</span><span class="sxs-lookup"><span data-stu-id="95f85-154">Edit IndexedDB data with Snippets</span></span>   

<span data-ttu-id="95f85-155">[スニペット][DevtoolsJavascriptSnippets]は、devtools 内に JavaScript コードのブロックを保存して実行するための手段です。</span><span class="sxs-lookup"><span data-stu-id="95f85-155">[Snippets][DevtoolsJavascriptSnippets] are a way to store and run blocks of JavaScript code within DevTools.</span></span>  <span data-ttu-id="95f85-156">スニペットを実行すると、結果が**コンソール**に記録されます。</span><span class="sxs-lookup"><span data-stu-id="95f85-156">When you run a Snippet, the result is logged to the **Console**.</span></span>  <span data-ttu-id="95f85-157">スニペットを使って、IndexedDB データベースを編集する JavaScript コードを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="95f85-157">You may use a Snippet to run JavaScript code to edit an IndexedDB database.</span></span>  

> ##### <span data-ttu-id="95f85-158">図 8</span><span class="sxs-lookup"><span data-stu-id="95f85-158">Figure 8</span></span>  
> <span data-ttu-id="95f85-159">スニペットを使った IndexedDB の操作</span><span class="sxs-lookup"><span data-stu-id="95f85-159">Using a Snippet to interact with IndexedDB</span></span>  
> ![スニペットを使った IndexedDB の操作][ImageIndexedDBSnippet]  

## <span data-ttu-id="95f85-161">IndexedDB データを削除する</span><span class="sxs-lookup"><span data-stu-id="95f85-161">Delete IndexedDB data</span></span>   

### <span data-ttu-id="95f85-162">IndexedDB キーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="95f85-162">Delete an IndexedDB key-value pair</span></span>   

1.  <span data-ttu-id="95f85-163">[IndexedDB オブジェクトストアを表示](#view-indexeddb-data)します。</span><span class="sxs-lookup"><span data-stu-id="95f85-163">[View an IndexedDB object store](#view-indexeddb-data).</span></span>  
1.  <span data-ttu-id="95f85-164">削除するキーと値のペアを選択します。</span><span class="sxs-lookup"><span data-stu-id="95f85-164">Select the key-value pair that you want to delete.</span></span>  <span data-ttu-id="95f85-165">DevTools では、選択されていることを示すように強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="95f85-165">DevTools highlights it to indicate that it is selected.</span></span>  
    
    > ##### <span data-ttu-id="95f85-166">図 9</span><span class="sxs-lookup"><span data-stu-id="95f85-166">Figure 9</span></span>  
    > <span data-ttu-id="95f85-167">キーと値のペアを選択して削除する</span><span class="sxs-lookup"><span data-stu-id="95f85-167">Selecting a key-value pair in order to delete it</span></span>  
    > ![キーと値のペアを選択して削除する][ImageIndexedDBKeyValuePair]  

1.  <span data-ttu-id="95f85-169">キーを押すか、[選択した `Delete` 削除の削除] をクリックし**Delete Selected** ![ ][ImageDeleteIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="95f85-169">Press the `Delete` key or click **Delete Selected** ![Delete Selected][ImageDeleteIcon].</span></span>  
    
    > ##### <span data-ttu-id="95f85-170">図 10</span><span class="sxs-lookup"><span data-stu-id="95f85-170">Figure 10</span></span>  
    > <span data-ttu-id="95f85-171">キーと値のペアが削除された後のオブジェクトストアの外観</span><span class="sxs-lookup"><span data-stu-id="95f85-171">How the object store looks after the key-value pair has been deleted</span></span>  
    > ![キーと値のペアが削除された後のオブジェクトストアの外観][ImageIndexedDBKeyValuePairDeleted]  

### <span data-ttu-id="95f85-173">オブジェクトストア内のすべてのキーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="95f85-173">Delete all key-value pairs in an object store</span></span>   

1.  <span data-ttu-id="95f85-174">[IndexedDB オブジェクトストアを表示](#view-indexeddb-data)します。</span><span class="sxs-lookup"><span data-stu-id="95f85-174">[View an IndexedDB object store](#view-indexeddb-data).</span></span>  
    
    > ##### <span data-ttu-id="95f85-175">図 11</span><span class="sxs-lookup"><span data-stu-id="95f85-175">Figure 11</span></span>  
    > <span data-ttu-id="95f85-176">オブジェクトストアの表示</span><span class="sxs-lookup"><span data-stu-id="95f85-176">Viewing an object store</span></span>  
    > ![オブジェクトストアの表示][ImageIndexedDBObjectStore]  

1.  <span data-ttu-id="95f85-178">[ **Clear object store** clear object store] を選び ![ ][ImageClearIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="95f85-178">Select **Clear object store** ![Clear object store][ImageClearIcon].</span></span>  

### <span data-ttu-id="95f85-179">IndexedDB データベースを削除する</span><span class="sxs-lookup"><span data-stu-id="95f85-179">Delete an IndexedDB database</span></span>   

1.  <span data-ttu-id="95f85-180">削除する[IndexedDB データベースを表示](#view-indexeddb-data)します。</span><span class="sxs-lookup"><span data-stu-id="95f85-180">[View the IndexedDB database](#view-indexeddb-data) that you want to delete.</span></span>  
1.  <span data-ttu-id="95f85-181">[**データベースの削除**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="95f85-181">Select **Delete database**.</span></span>  
    
    > ##### <span data-ttu-id="95f85-182">図 12</span><span class="sxs-lookup"><span data-stu-id="95f85-182">Figure 12</span></span>  
    > <span data-ttu-id="95f85-183">[**データベースの削除**] ボタン</span><span class="sxs-lookup"><span data-stu-id="95f85-183">The **Delete database** button</span></span>  
    > ![[データベースの削除] ボタン][ImageIndexedDBDatabase]  

### <span data-ttu-id="95f85-185">すべての IndexedDB ストレージを削除します</span><span class="sxs-lookup"><span data-stu-id="95f85-185">Delete all IndexedDB storage</span></span>   

1.  <span data-ttu-id="95f85-186">[**記憶域のクリア**] ウィンドウを開く。</span><span class="sxs-lookup"><span data-stu-id="95f85-186">Open the **Clear storage** pane.</span></span>  

1.  <span data-ttu-id="95f85-187">[ **Indexeddb** ] チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="95f85-187">Make sure that the **IndexedDB** checkbox is enabled.</span></span>  

1.  <span data-ttu-id="95f85-188">[**サイトデータのクリア**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="95f85-188">Select **Clear site data**.</span></span>  
    
    > ##### <span data-ttu-id="95f85-189">図 13</span><span class="sxs-lookup"><span data-stu-id="95f85-189">Figure 13</span></span>  
    > <span data-ttu-id="95f85-190">[**記憶域**のクリア] ウィンドウ ![][ImageIndexedDBClearStorage]</span><span class="sxs-lookup"><span data-stu-id="95f85-190">The **Clear storage** pane ![The Clear storage pane][ImageIndexedDBClearStorage]</span></span>  

 



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
> <span data-ttu-id="95f85-211">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="95f85-211">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="95f85-212">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/storage/indexeddb)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="95f85-212">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/indexeddb) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="95f85-214">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="95f85-214">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
