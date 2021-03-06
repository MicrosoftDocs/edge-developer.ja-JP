---
description: アプリケーション パネルとスニペットを使用して IndexedDB データを表示および変更する方法。
title: Microsoft Edge DevTools を使用して IndexedDB データを表示および変更する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 6062cb6b574b2295441bc98616f600cbf00cee8e
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398981"
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

# <a name="view-and-change-indexeddb-data-with-microsoft-edge-devtools"></a><span data-ttu-id="154ec-104">Microsoft Edge DevTools を使用して IndexedDB データを表示および変更する</span><span class="sxs-lookup"><span data-stu-id="154ec-104">View and change IndexedDB data with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="154ec-105">このガイドでは [、Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使用して IndexedDB データを表示および変更 [する方法を示][MDNIndexedDBAPI] します。</span><span class="sxs-lookup"><span data-stu-id="154ec-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view and change [IndexedDB][MDNIndexedDBAPI] data.</span></span>  <span data-ttu-id="154ec-106">DevTools に精通している必要があります。</span><span class="sxs-lookup"><span data-stu-id="154ec-106">It assumes you are familiar with DevTools.</span></span>  <span data-ttu-id="154ec-107">また、IndexedDB に精通している必要があります。</span><span class="sxs-lookup"><span data-stu-id="154ec-107">It also assumes you are familiar with IndexedDB.</span></span>  <span data-ttu-id="154ec-108">使用しない場合は [、[IndexedDB の使用] に移動します][MDNUsingIndexedDB]。</span><span class="sxs-lookup"><span data-stu-id="154ec-108">If not, navigate to [Using IndexedDB][MDNUsingIndexedDB].</span></span>  

## <a name="view-indexeddb-data"></a><span data-ttu-id="154ec-109">IndexedDB データの表示</span><span class="sxs-lookup"><span data-stu-id="154ec-109">View IndexedDB data</span></span>  

1.  <span data-ttu-id="154ec-110">[アプリケーション] **タブを** 選択して、[アプリケーション] ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="154ec-110">Choose the **Application** tab to open the **Application** tool.</span></span>  <span data-ttu-id="154ec-111">通常 **、マニフェスト ウィンドウ** は既定で開きます。</span><span class="sxs-lookup"><span data-stu-id="154ec-111">The **Manifest** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest-empty.msft.png" alt-text="[マニフェスト] ウィンドウ" lightbox="../media/storage-application-manifest-empty.msft.png":::
       <span data-ttu-id="154ec-113">[ **マニフェスト]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="154ec-113">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="154ec-114">**[IndexedDB] メニューを展開**して、使用可能なデータベースを確認します。</span><span class="sxs-lookup"><span data-stu-id="154ec-114">Expand the **IndexedDB** menu to review which databases are available.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb.msft.png" alt-text="IndexedDB メニュー" lightbox="../media/storage-application-storage-indexeddb.msft.png":::
       <span data-ttu-id="154ec-116">**IndexedDB**メニュー</span><span class="sxs-lookup"><span data-stu-id="154ec-116">The **IndexedDB** menu</span></span>  
    :::image-end:::  
    
    *   <span data-ttu-id="154ec-117">\( Database icon \) は、データベースの名前であり、データベースにアクセスする元であるデータベース ![ ][ImageDatabaseIcon] `notes - https://mdn.github.io` `notes` `https://mdn.github.io` を表します。</span><span class="sxs-lookup"><span data-stu-id="154ec-117">\(![Database icon][ImageDatabaseIcon]\) `notes - https://mdn.github.io` represents a database, where `notes` is the name of the database and `https://mdn.github.io` is the origin that accesses the database.</span></span>  
    *   <span data-ttu-id="154ec-118">\( ![ Object Store icon ][ImageObjectStoreIcon] \) `notes` はオブジェクト ストアです。</span><span class="sxs-lookup"><span data-stu-id="154ec-118">\(![Object Store icon][ImageObjectStoreIcon]\) `notes` is an object store.</span></span>  
    *   <span data-ttu-id="154ec-119">**title**と**body は**[インデックス です][MDNUsingIndexedDBUsingIndex]。</span><span class="sxs-lookup"><span data-stu-id="154ec-119">**title** and **body** are [indexes][MDNUsingIndexedDBUsingIndex].</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="154ec-120">**既知の制限**  サード パーティ製のデータベースは表示されません。</span><span class="sxs-lookup"><span data-stu-id="154ec-120">**Known Limitation**  Third-party databases are not visible.</span></span>  <span data-ttu-id="154ec-121">たとえば、a を使用してページに広告を埋め込み、広告ネットワークが IndexedDB を使用している場合、広告ネットワークの `<iframe>` IndexedDB データは表示されません。</span><span class="sxs-lookup"><span data-stu-id="154ec-121">For example, if you use an `<iframe>` to embed an ad on your page, and your ad network uses IndexedDB, the IndexedDB data for your ad network is not be visible.</span></span>  <span data-ttu-id="154ec-122">[問題] に [移動#943770][ChromiumIssue943770]します。</span><span class="sxs-lookup"><span data-stu-id="154ec-122">Navigate to [issue #943770][ChromiumIssue943770].</span></span>  
    
1.  <span data-ttu-id="154ec-123">データベースを選択して、元の番号とバージョン番号を確認します。</span><span class="sxs-lookup"><span data-stu-id="154ec-123">Choose a database to review the origin and version number.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db.msft.png" alt-text="メモ データベース" lightbox="../media/storage-application-storage-indexeddb-notes_db.msft.png":::
       <span data-ttu-id="154ec-125">メモ**データベース**</span><span class="sxs-lookup"><span data-stu-id="154ec-125">The **notes** database</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="154ec-126">キーと値のペアを確認するには、オブジェクト ストアを選択します。</span><span class="sxs-lookup"><span data-stu-id="154ec-126">Choose an object store to review the key-value pairs.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="154ec-127">IndexedDB データはリアルタイムで更新されません。</span><span class="sxs-lookup"><span data-stu-id="154ec-127">IndexedDB data does not update in real-time.</span></span>  <span data-ttu-id="154ec-128">[インデックス付 [きDB データの更新] に移動します](#refresh-indexeddb-data)。</span><span class="sxs-lookup"><span data-stu-id="154ec-128">Navigate to [Refresh IndexedDB data](#refresh-indexeddb-data).</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os.msft.png" alt-text="notes オブジェクト ストア" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os.msft.png":::
       <span data-ttu-id="154ec-130">notes **オブジェクト** ストア</span><span class="sxs-lookup"><span data-stu-id="154ec-130">The **notes** object store</span></span>  
    :::image-end:::  
    
    *   <span data-ttu-id="154ec-131">**合計エントリは** 、オブジェクト ストア内のキーと値のペアの総数です。</span><span class="sxs-lookup"><span data-stu-id="154ec-131">**Total entries** is the total number of key-value pairs in the object store.</span></span>  
    *   <span data-ttu-id="154ec-132">**キー ジェネレーターの値は** 、次に使用可能なキーです。</span><span class="sxs-lookup"><span data-stu-id="154ec-132">**Key generator value** is the next available key.</span></span>  <span data-ttu-id="154ec-133">このフィールドは、キー ジェネレーターを使用 [する場合にのみ表示されます][MDNBasicConceptsKeyGenerator]。</span><span class="sxs-lookup"><span data-stu-id="154ec-133">The field is only shown when using [key generators][MDNBasicConceptsKeyGenerator].</span></span>  
    
1.  <span data-ttu-id="154ec-134">[値] 列の **セルを選択** して、値を展開します。</span><span class="sxs-lookup"><span data-stu-id="154ec-134">Choose a cell in the **Value** column to expand the value.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-edge-chromium.msft.png" alt-text="IndexedDB 値の表示" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-edge-chromium.msft.png":::
       <span data-ttu-id="154ec-136">**IndexedDB 値の**表示</span><span class="sxs-lookup"><span data-stu-id="154ec-136">View an **IndexedDB** value</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="154ec-137">次の図のタイトルや\*\*\*\* 本文などの\*\*\*\* インデックスを選択して、そのインデックスの値に従ってオブジェクト ストアを並べ替える。</span><span class="sxs-lookup"><span data-stu-id="154ec-137">Choose an index, such as **title** or **body** in the following figure, to sort the object store according to the values of that index.</span></span>  
   
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-title.msft.png" alt-text="インデックスでオブジェクト ストアを並べ替える" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-title.msft.png":::
       <span data-ttu-id="154ec-139">インデックスでオブジェクト ストアを並べ替える</span><span class="sxs-lookup"><span data-stu-id="154ec-139">Sort an object store by an index</span></span>  
    :::image-end:::  
    
## <a name="refresh-indexeddb-data"></a><span data-ttu-id="154ec-140">IndexedDB データの更新</span><span class="sxs-lookup"><span data-stu-id="154ec-140">Refresh IndexedDB data</span></span>  

<span data-ttu-id="154ec-141">アプリケーション ツールの IndexedDB **値** はリアルタイムで更新されません。</span><span class="sxs-lookup"><span data-stu-id="154ec-141">IndexedDB values in the **Application** tool do not update in real-time.</span></span>  <span data-ttu-id="154ec-142">オブジェクト**ストアを表示**してデータを更新する場合は [Refresh \( Refresh \)] を選択するか、データベースを表示して [データベースの更新] を選択してすべてのデータ ![ ][ImageRefreshIcon] を更新します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="154ec-142">Choose **Refresh** \(![Refresh][ImageRefreshIcon]\) when viewing an object store to refresh the data, or view a database and choose **Refresh database** to refresh all data.</span></span>  

:::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-refresh-database.msft.png" alt-text="データベースの表示" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-refresh-database.msft.png":::
   <span data-ttu-id="154ec-144">データベースの表示</span><span class="sxs-lookup"><span data-stu-id="154ec-144">View a database</span></span>  
:::image-end:::  

## <a name="edit-indexeddb-data"></a><span data-ttu-id="154ec-145">IndexedDB データの編集</span><span class="sxs-lookup"><span data-stu-id="154ec-145">Edit IndexedDB data</span></span>  

<span data-ttu-id="154ec-146">IndexedDB キーと値は、アプリケーション ツールでは **編集** できません。</span><span class="sxs-lookup"><span data-stu-id="154ec-146">IndexedDB keys and values are not editable from the **Application** tool.</span></span>  <span data-ttu-id="154ec-147">ただし、DevTools はページ コンテキストにアクセスできますので、DevTools 内で JavaScript コードを実行して IndexedDB データを編集できます。</span><span class="sxs-lookup"><span data-stu-id="154ec-147">Since DevTools has access to page context, however, you may run JavaScript code within DevTools to edit IndexedDB data.</span></span>  

### <a name="edit-indexeddb-data-with-snippets"></a><span data-ttu-id="154ec-148">スニペットを使用して IndexedDB データを編集する</span><span class="sxs-lookup"><span data-stu-id="154ec-148">Edit IndexedDB data with Snippets</span></span>  

<span data-ttu-id="154ec-149">[スニペットは][DevtoolsJavascriptSnippets] 、DevTools 内で JavaScript コードのブロックを格納および実行する方法です。</span><span class="sxs-lookup"><span data-stu-id="154ec-149">[Snippets][DevtoolsJavascriptSnippets] are a way to store and run blocks of JavaScript code within DevTools.</span></span>  <span data-ttu-id="154ec-150">スニペットを実行すると、結果はコンソールに記録 **されます**。</span><span class="sxs-lookup"><span data-stu-id="154ec-150">When you run a Snippet, the result is logged to the **Console**.</span></span>  <span data-ttu-id="154ec-151">スニペットを使用して JavaScript コードを実行して IndexedDB データベースを編集できます。</span><span class="sxs-lookup"><span data-stu-id="154ec-151">You may use a Snippet to run JavaScript code to edit an IndexedDB database.</span></span>  

:::image type="complex" source="../media/storage-sources-snippets-indexeddb-output.msft.png" alt-text="スニペットを使用して IndexedDB を操作する" lightbox="../media/storage-sources-snippets-indexeddb-output.msft.png":::
   <span data-ttu-id="154ec-153">スニペットを使用して IndexedDB を操作する</span><span class="sxs-lookup"><span data-stu-id="154ec-153">Use a Snippet to interact with IndexedDB</span></span>  
:::image-end:::  

## <a name="delete-indexeddb-data"></a><span data-ttu-id="154ec-154">IndexedDB データの削除</span><span class="sxs-lookup"><span data-stu-id="154ec-154">Delete IndexedDB data</span></span>  

### <a name="delete-an-indexeddb-key-value-pair"></a><span data-ttu-id="154ec-155">IndexedDB キーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="154ec-155">Delete an IndexedDB key-value pair</span></span>  

1.  <span data-ttu-id="154ec-156">[IndexedDB オブジェクト ストアを表示します](#view-indexeddb-data)。</span><span class="sxs-lookup"><span data-stu-id="154ec-156">[View an IndexedDB object store](#view-indexeddb-data).</span></span>  
1.  <span data-ttu-id="154ec-157">削除するキーと値のペアを選択します。</span><span class="sxs-lookup"><span data-stu-id="154ec-157">Choose the key-value pair that you want to delete.</span></span>  <span data-ttu-id="154ec-158">DevTools では強調表示され、選択されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="154ec-158">DevTools highlights it to indicate that it is selected.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os2.msft.png" alt-text="キーと値のペアを選択して削除する" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os2.msft.png":::
       <span data-ttu-id="154ec-160">キーと値のペアを選択して削除する</span><span class="sxs-lookup"><span data-stu-id="154ec-160">Choose a key-value pair in order to delete it</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="154ec-161">キーを `Delete` 選択するか、[ **選択した \(** Delete ![ Selected \) を削除する] ][ImageDeleteIcon] を選択します。</span><span class="sxs-lookup"><span data-stu-id="154ec-161">Select the `Delete` key or choose **Delete Selected** \(![Delete Selected][ImageDeleteIcon]\).</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-delete-selected.msft.png" alt-text="キーと値のペアが削除された後のオブジェクト ストアの外観" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-delete-selected.msft.png":::
       <span data-ttu-id="154ec-163">キーと値のペアが削除された後のオブジェクト ストアの外観</span><span class="sxs-lookup"><span data-stu-id="154ec-163">How the object store looks after the key-value pair has been deleted</span></span>  
    :::image-end:::  
    
### <a name="delete-all-key-value-pairs-in-an-object-store"></a><span data-ttu-id="154ec-164">オブジェクト ストア内のすべてのキーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="154ec-164">Delete all key-value pairs in an object store</span></span>  

1.  <span data-ttu-id="154ec-165">[IndexedDB オブジェクト ストアを表示します](#view-indexeddb-data)。</span><span class="sxs-lookup"><span data-stu-id="154ec-165">[View an IndexedDB object store](#view-indexeddb-data).</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-clear-object-store.msft.png" alt-text="オブジェクト ストアの表示" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-clear-object-store.msft.png":::
       <span data-ttu-id="154ec-167">オブジェクト ストアの表示</span><span class="sxs-lookup"><span data-stu-id="154ec-167">View an object store</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="154ec-168">[ **オブジェクト ストアのクリア** ] \( ![ Clear object store ][ImageClearIcon] \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="154ec-168">Choose **Clear object store** \(![Clear object store][ImageClearIcon]\).</span></span>  
    
### <a name="delete-an-indexeddb-database"></a><span data-ttu-id="154ec-169">IndexedDB データベースの削除</span><span class="sxs-lookup"><span data-stu-id="154ec-169">Delete an IndexedDB database</span></span>  

1.  <span data-ttu-id="154ec-170">[削除する IndexedDB](#view-indexeddb-data) データベースを表示します。</span><span class="sxs-lookup"><span data-stu-id="154ec-170">[View the IndexedDB database](#view-indexeddb-data) that you want to delete.</span></span>  
1.  <span data-ttu-id="154ec-171">[データベース **の削除] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="154ec-171">Choose **Delete database**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-delete-database.msft.png" alt-text="[データベースの削除] ボタン" lightbox="../media/storage-application-storage-indexeddb-notes_db-delete-database.msft.png":::
       <span data-ttu-id="154ec-173">[ **データベースの削除]** ボタン</span><span class="sxs-lookup"><span data-stu-id="154ec-173">The **Delete database** button</span></span>  
    :::image-end:::  
    
### <a name="delete-all-indexeddb-storage"></a><span data-ttu-id="154ec-174">すべての IndexedDB ストレージを削除する</span><span class="sxs-lookup"><span data-stu-id="154ec-174">Delete all IndexedDB storage</span></span>  

1.  <span data-ttu-id="154ec-175">[ストレージの **クリア] ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="154ec-175">Open the **Clear storage** pane.</span></span>  
1.  <span data-ttu-id="154ec-176">**[IndexedDB] チェック ボックスが有効**になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="154ec-176">Make sure that the **IndexedDB** checkbox is enabled.</span></span>  
1.  <span data-ttu-id="154ec-177">[サイト **データのクリア] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="154ec-177">Choose **Clear site data**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-indexeddb-clear-site-data.msft.png" alt-text="[ストレージのクリア] ウィンドウ" lightbox="../media/storage-application-clear-storage-indexeddb-clear-site-data.msft.png":::
       <span data-ttu-id="154ec-179">[ **ストレージのクリア]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="154ec-179">The **Clear storage** pane</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="154ec-180">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="154ec-180">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDatabaseIcon]: ../media/database-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  
[ImageObjectStoreIcon]: ../media/object-store-icon.msft.png  
[ImageRefreshIcon]: ../media/reload-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (クロム) 開発者向け|Microsoft Docs"  
[DevtoolsJavascriptSnippets]: ../javascript/snippets.md "Microsoft Edge DevTools を使用して任意のページで JavaScript のスニペットを実行|Microsoft Docs"  

[ChromiumIssue943770]: https://crbug.com/943770 "943770 - DevTools: show iframe IndexedDB データベース - クロム - Monorail"  

[MDNBasicConceptsKeyGenerator]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Basic_Concepts_Behind_IndexedDB#gloss_keygenerator "キー ジェネレーター - 基本概念|MDN"  
[MDNIndexedDBAPI]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API "IndexedDB API |MDN"  
[MDNUsingIndexedDB]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB "IndexedDB の使用|MDN"  
[MDNUsingIndexedDBUsingIndex]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Using_an_index "インデックスの使用 - IndexedDB を使用|MDN"  

> [!NOTE]
> <span data-ttu-id="154ec-188">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="154ec-188">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="154ec-189">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/indexeddb) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="154ec-189">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/indexeddb) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="154ec-191">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="154ec-191">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
