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





# <span data-ttu-id="3679e-104">Microsoft Edge DevTools を使用して IndexedDB データを表示および変更する</span><span class="sxs-lookup"><span data-stu-id="3679e-104">View and change IndexedDB data with Microsoft Edge DevTools</span></span>   

  

<span data-ttu-id="3679e-105">このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使って [インデックス eddb][MDNIndexedDBAPI] データを表示および変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3679e-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view and change [IndexedDB][MDNIndexedDBAPI] data.</span></span>  <span data-ttu-id="3679e-106">これは、DevTools に精通していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="3679e-106">It assumes you are familiar with DevTools.</span></span>  <span data-ttu-id="3679e-107">また、IndexedDB に精通していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="3679e-107">It also assumes you are familiar with IndexedDB.</span></span>  <span data-ttu-id="3679e-108">表示されない場合は、「 [IndexedDB を使用する][MDNUsingIndexedDB]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3679e-108">If not, see [Using IndexedDB][MDNUsingIndexedDB].</span></span>  

## <span data-ttu-id="3679e-109">IndexedDB データの表示</span><span class="sxs-lookup"><span data-stu-id="3679e-109">View IndexedDB data</span></span>   

1.  <span data-ttu-id="3679e-110">[ **アプリケーション** ] タブを選択して、[ **アプリケーション** ] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3679e-110">Select the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="3679e-111">通常、 **マニフェスト** ウィンドウは既定で開かれます。</span><span class="sxs-lookup"><span data-stu-id="3679e-111">The **Manifest** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest-empty.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-manifest-empty.msft.png":::
       <span data-ttu-id="3679e-113">**マニフェスト**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="3679e-113">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3679e-114">[ **Indexeddb** ] メニューを展開して、利用可能なデータベースを確認します。</span><span class="sxs-lookup"><span data-stu-id="3679e-114">Expand the **IndexedDB** menu to see which databases are available.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb.msft.png" alt-text="IndexedDB メニュー" lightbox="../media/storage-application-storage-indexeddb.msft.png":::
       <span data-ttu-id="3679e-116">**Indexeddb**メニュー</span><span class="sxs-lookup"><span data-stu-id="3679e-116">The **IndexedDB** menu</span></span>  
    :::image-end:::  
    
    *   <span data-ttu-id="3679e-117">\ ( ![ データベースアイコン \) は、データベースの名前であり、 ][ImageDatabaseIcon] `notes - https://mdn.github.io` `notes` `https://mdn.github.io` データベースにアクセスする元のデータベースを表します。</span><span class="sxs-lookup"><span data-stu-id="3679e-117">\(![Database icon][ImageDatabaseIcon]\) `notes - https://mdn.github.io` represents a database, where `notes` is the name of the database and `https://mdn.github.io` is the origin that accesses the database.</span></span>  
    *   <span data-ttu-id="3679e-118">\ ( ![ オブジェクトストアアイコン ][ImageObjectStoreIcon] \) `notes` はオブジェクトストアです。</span><span class="sxs-lookup"><span data-stu-id="3679e-118">\(![Object Store icon][ImageObjectStoreIcon]\) `notes` is an object store.</span></span>  
    *   <span data-ttu-id="3679e-119">**タイトル** と **本文** は [インデックス][MDNUsingIndexedDBUsingIndex]です。</span><span class="sxs-lookup"><span data-stu-id="3679e-119">**title** and **body** are [indexes][MDNUsingIndexedDBUsingIndex].</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="3679e-120">**既知の制限**  サードパーティデータベースは表示されません。</span><span class="sxs-lookup"><span data-stu-id="3679e-120">**Known Limitation**  Third-party databases are not visible.</span></span>  <span data-ttu-id="3679e-121">たとえば、 `<iframe>` を使って広告をページに埋め込む場合、広告ネットワークで IndexedDB を使用している場合、広告ネットワークの indexeddb データは表示されません。</span><span class="sxs-lookup"><span data-stu-id="3679e-121">For example, if you use an `<iframe>` to embed an ad on your page, and your ad network uses IndexedDB, the IndexedDB data for your ad network is not be visible.</span></span>  <span data-ttu-id="3679e-122">[#943770 問題][ChromiumIssue943770]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3679e-122">See [issue #943770][ChromiumIssue943770].</span></span>  
    
1.  <span data-ttu-id="3679e-123">起点とバージョン番号を確認するには、データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="3679e-123">Select a database to see the origin and version number.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db.msft.png" alt-text="ノーツデータベース" lightbox="../media/storage-application-storage-indexeddb-notes_db.msft.png":::
       <span data-ttu-id="3679e-125">**ノーツ**データベース</span><span class="sxs-lookup"><span data-stu-id="3679e-125">The **notes** database</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3679e-126">キーと値のペアを表示するオブジェクトストアを選択します。</span><span class="sxs-lookup"><span data-stu-id="3679e-126">Select an object store to see the key-value pairs.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="3679e-127">IndexedDB データは、リアルタイムでは更新されません。</span><span class="sxs-lookup"><span data-stu-id="3679e-127">IndexedDB data does not update in real-time.</span></span>  <span data-ttu-id="3679e-128">「 [IndexedDB データを更新](#refresh-indexeddb-data)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3679e-128">See [Refresh IndexedDB data](#refresh-indexeddb-data).</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os.msft.png" alt-text="ノーツオブジェクトストア" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os.msft.png":::
       <span data-ttu-id="3679e-130">**ノーツ**オブジェクトストア</span><span class="sxs-lookup"><span data-stu-id="3679e-130">The **notes** object store</span></span>  
    :::image-end:::  
    
    *   <span data-ttu-id="3679e-131">**Total entries** は、オブジェクトストアのキーと値のペアの合計数です。</span><span class="sxs-lookup"><span data-stu-id="3679e-131">**Total entries** is the total number of key-value pairs in the object store.</span></span>  
    *   <span data-ttu-id="3679e-132">**キージェネレーターの値** は、次に使用可能なキーです。</span><span class="sxs-lookup"><span data-stu-id="3679e-132">**Key generator value** is the next available key.</span></span>  <span data-ttu-id="3679e-133">このフィールドは、 [キージェネレーター][MDNBasicConceptsKeyGenerator]を使用している場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="3679e-133">This field is only shown when using [key generators][MDNBasicConceptsKeyGenerator].</span></span>  
    
1.  <span data-ttu-id="3679e-134">[ **値** ] 列のセルを選択して、その値を展開します。</span><span class="sxs-lookup"><span data-stu-id="3679e-134">Select a cell in the **Value** column to expand that value.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-edge-chromium.msft.png" alt-text="IndexedDB 値の表示" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-edge-chromium.msft.png":::
       <span data-ttu-id="3679e-136">**Indexeddb**値の表示</span><span class="sxs-lookup"><span data-stu-id="3679e-136">View an **IndexedDB** value</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3679e-137">次の図の [ **タイトル** ] や [ **本文** ] などのインデックスを選択し、そのインデックスの値に従ってオブジェクトストアを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="3679e-137">Select an index, such as **title** or **body** in the following figure, to sort the object store according to the values of that index.</span></span>  
   
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-title.msft.png" alt-text="インデックスによるオブジェクトストアの並べ替え" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-title.msft.png":::
       <span data-ttu-id="3679e-139">インデックスによるオブジェクトストアの並べ替え</span><span class="sxs-lookup"><span data-stu-id="3679e-139">Sort an object store by an index</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="3679e-140">IndexedDB データを更新する</span><span class="sxs-lookup"><span data-stu-id="3679e-140">Refresh IndexedDB data</span></span>   

<span data-ttu-id="3679e-141">**アプリケーション**パネルの IndexedDB 値は、リアルタイムでは更新されません。</span><span class="sxs-lookup"><span data-stu-id="3679e-141">IndexedDB values in the **Application** panel do not update in real-time.</span></span>  <span data-ttu-id="3679e-142">オブジェクト**Refresh**ストアを表示して ![ データを ][ImageReloadIcon] 更新するか、データベースを表示し、[**データベースの更新**] をクリックしてすべてのデータを更新するには、[更新] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3679e-142">Select **Refresh** \(![Refresh][ImageReloadIcon]\) when viewing an object store to refresh the data, or view a database and click **Refresh database** to refresh all data.</span></span>  

:::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-refresh-database.msft.png" alt-text="データベースの表示" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-refresh-database.msft.png":::
   <span data-ttu-id="3679e-144">データベースの表示</span><span class="sxs-lookup"><span data-stu-id="3679e-144">View a database</span></span>  
:::image-end:::  

## <span data-ttu-id="3679e-145">IndexedDB データを編集する</span><span class="sxs-lookup"><span data-stu-id="3679e-145">Edit IndexedDB data</span></span>   

<span data-ttu-id="3679e-146">IndexedDB キーと値は、 **アプリケーション** パネルから編集できません。</span><span class="sxs-lookup"><span data-stu-id="3679e-146">IndexedDB keys and values are not editable from the **Application** panel.</span></span>  <span data-ttu-id="3679e-147">DevTools にはページのコンテキストへのアクセスがあります。ただし、DevTools 内では、IndexedDB データを編集するための JavaScript コードを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="3679e-147">Since DevTools has access to page context, however, you may run JavaScript code within DevTools to edit IndexedDB data.</span></span>  

### <span data-ttu-id="3679e-148">スニペットを使用して IndexedDB データを編集する</span><span class="sxs-lookup"><span data-stu-id="3679e-148">Edit IndexedDB data with Snippets</span></span>   

<span data-ttu-id="3679e-149">[スニペット][DevtoolsJavascriptSnippets] は、devtools 内に JavaScript コードのブロックを保存して実行するための手段です。</span><span class="sxs-lookup"><span data-stu-id="3679e-149">[Snippets][DevtoolsJavascriptSnippets] are a way to store and run blocks of JavaScript code within DevTools.</span></span>  <span data-ttu-id="3679e-150">スニペットを実行すると、結果が **コンソール**に記録されます。</span><span class="sxs-lookup"><span data-stu-id="3679e-150">When you run a Snippet, the result is logged to the **Console**.</span></span>  <span data-ttu-id="3679e-151">スニペットを使って、IndexedDB データベースを編集する JavaScript コードを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="3679e-151">You may use a Snippet to run JavaScript code to edit an IndexedDB database.</span></span>  

:::image type="complex" source="../media/storage-sources-snippets-indexeddb-output.msft.png" alt-text="スニペットを使って IndexedDB を操作する" lightbox="../media/storage-sources-snippets-indexeddb-output.msft.png":::
   <span data-ttu-id="3679e-153">スニペットを使って IndexedDB を操作する</span><span class="sxs-lookup"><span data-stu-id="3679e-153">Use a Snippet to interact with IndexedDB</span></span>  
:::image-end:::  

## <span data-ttu-id="3679e-154">IndexedDB データを削除する</span><span class="sxs-lookup"><span data-stu-id="3679e-154">Delete IndexedDB data</span></span>   

### <span data-ttu-id="3679e-155">IndexedDB キーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="3679e-155">Delete an IndexedDB key-value pair</span></span>   

1.  <span data-ttu-id="3679e-156">[IndexedDB オブジェクトストアを表示](#view-indexeddb-data)します。</span><span class="sxs-lookup"><span data-stu-id="3679e-156">[View an IndexedDB object store](#view-indexeddb-data).</span></span>  
1.  <span data-ttu-id="3679e-157">削除するキーと値のペアを選択します。</span><span class="sxs-lookup"><span data-stu-id="3679e-157">Select the key-value pair that you want to delete.</span></span>  <span data-ttu-id="3679e-158">DevTools では、選択されていることを示すように強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="3679e-158">DevTools highlights it to indicate that it is selected.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os2.msft.png" alt-text="キーと値のペアを選択して削除する" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os2.msft.png":::
       <span data-ttu-id="3679e-160">キーと値のペアを選択して削除する</span><span class="sxs-lookup"><span data-stu-id="3679e-160">Select a key-value pair in order to delete it</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3679e-161">キーを押す `Delete` か、[ **選択した** ものを削除] をクリックし ![ ます (選択した \ を削除 ][ImageDeleteIcon] )。</span><span class="sxs-lookup"><span data-stu-id="3679e-161">Press the `Delete` key or click **Delete Selected** \(![Delete Selected][ImageDeleteIcon]\).</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-delete-selected.msft.png" alt-text="キーと値のペアが削除された後のオブジェクトストアの外観" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-delete-selected.msft.png":::
       <span data-ttu-id="3679e-163">キーと値のペアが削除された後のオブジェクトストアの外観</span><span class="sxs-lookup"><span data-stu-id="3679e-163">How the object store looks after the key-value pair has been deleted</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="3679e-164">オブジェクトストア内のすべてのキーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="3679e-164">Delete all key-value pairs in an object store</span></span>   

1.  <span data-ttu-id="3679e-165">[IndexedDB オブジェクトストアを表示](#view-indexeddb-data)します。</span><span class="sxs-lookup"><span data-stu-id="3679e-165">[View an IndexedDB object store](#view-indexeddb-data).</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-clear-object-store.msft.png" alt-text="オブジェクトストアの表示" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-clear-object-store.msft.png":::
       <span data-ttu-id="3679e-167">オブジェクトストアの表示</span><span class="sxs-lookup"><span data-stu-id="3679e-167">View an object store</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3679e-168">[ **Clear object store** (オブジェクトストアをクリア)] を選び ![ ][ImageClearIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="3679e-168">Select **Clear object store** \(![Clear object store][ImageClearIcon]\).</span></span>  
    
### <span data-ttu-id="3679e-169">IndexedDB データベースを削除する</span><span class="sxs-lookup"><span data-stu-id="3679e-169">Delete an IndexedDB database</span></span>   

1.  <span data-ttu-id="3679e-170">削除する[IndexedDB データベースを表示](#view-indexeddb-data)します。</span><span class="sxs-lookup"><span data-stu-id="3679e-170">[View the IndexedDB database](#view-indexeddb-data) that you want to delete.</span></span>  
1.  <span data-ttu-id="3679e-171">[ **データベースの削除**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3679e-171">Select **Delete database**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-delete-database.msft.png" alt-text="[データベースの削除] ボタン" lightbox="../media/storage-application-storage-indexeddb-notes_db-delete-database.msft.png":::
       <span data-ttu-id="3679e-173">[ **データベースの削除** ] ボタン</span><span class="sxs-lookup"><span data-stu-id="3679e-173">The **Delete database** button</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="3679e-174">すべての IndexedDB ストレージを削除します</span><span class="sxs-lookup"><span data-stu-id="3679e-174">Delete all IndexedDB storage</span></span>   

1.  <span data-ttu-id="3679e-175">[ **記憶域のクリア** ] ウィンドウを開く。</span><span class="sxs-lookup"><span data-stu-id="3679e-175">Open the **Clear storage** pane.</span></span>  
1.  <span data-ttu-id="3679e-176">[ **Indexeddb** ] チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3679e-176">Make sure that the **IndexedDB** checkbox is enabled.</span></span>  
1.  <span data-ttu-id="3679e-177">[ **サイトデータのクリア**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3679e-177">Select **Clear site data**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-indexeddb-clear-site-data.msft.png" alt-text="[記憶域のクリア] ウィンドウ" lightbox="../media/storage-application-clear-storage-indexeddb-clear-site-data.msft.png":::
       <span data-ttu-id="3679e-179">[ **記憶域のクリア** ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="3679e-179">The **Clear storage** pane</span></span>  
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
> <span data-ttu-id="3679e-187">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="3679e-187">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="3679e-188">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/indexeddb) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="3679e-188">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/indexeddb) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="3679e-190">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="3679e-190">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
