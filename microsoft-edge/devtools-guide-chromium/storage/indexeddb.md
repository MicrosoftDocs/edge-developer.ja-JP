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

# <span data-ttu-id="a052c-104">Microsoft Edge DevTools を使用して IndexedDB データを表示および変更する</span><span class="sxs-lookup"><span data-stu-id="a052c-104">View and change IndexedDB data with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="a052c-105">このガイドでは [、Microsoft Edge DevTools を使用して][MicrosoftEdgeDevTools] [IndexedDB][MDNIndexedDBAPI] データを表示および変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a052c-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view and change [IndexedDB][MDNIndexedDBAPI] data.</span></span>  <span data-ttu-id="a052c-106">DevTools に精通している必要があります。</span><span class="sxs-lookup"><span data-stu-id="a052c-106">It assumes you are familiar with DevTools.</span></span>  <span data-ttu-id="a052c-107">また、IndexedDB に精通している必要があります。</span><span class="sxs-lookup"><span data-stu-id="a052c-107">It also assumes you are familiar with IndexedDB.</span></span>  <span data-ttu-id="a052c-108">If not, navigate to [Using IndexedDB][MDNUsingIndexedDB].</span><span class="sxs-lookup"><span data-stu-id="a052c-108">If not, navigate to [Using IndexedDB][MDNUsingIndexedDB].</span></span>  

## <span data-ttu-id="a052c-109">IndexedDB データの表示</span><span class="sxs-lookup"><span data-stu-id="a052c-109">View IndexedDB data</span></span>  

1.  <span data-ttu-id="a052c-110">[アプリケーション **] タブ** を選択して、アプリケーション ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="a052c-110">Choose the **Application** tab to open the **Application** tool.</span></span>  <span data-ttu-id="a052c-111">通常 **、マニフェスト** ウィンドウは既定で開きます。</span><span class="sxs-lookup"><span data-stu-id="a052c-111">The **Manifest** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest-empty.msft.png" alt-text="マニフェスト ウィンドウ" lightbox="../media/storage-application-manifest-empty.msft.png":::
       <span data-ttu-id="a052c-113">マニフェスト**ウィンドウ**</span><span class="sxs-lookup"><span data-stu-id="a052c-113">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a052c-114">**[IndexedDB] メニューを展開**して、使用可能なデータベースを確認します。</span><span class="sxs-lookup"><span data-stu-id="a052c-114">Expand the **IndexedDB** menu to review which databases are available.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb.msft.png" alt-text="IndexedDB メニュー" lightbox="../media/storage-application-storage-indexeddb.msft.png":::
       <span data-ttu-id="a052c-116">**IndexedDB**メニュー</span><span class="sxs-lookup"><span data-stu-id="a052c-116">The **IndexedDB** menu</span></span>  
    :::image-end:::  
    
    *   <span data-ttu-id="a052c-117">\( ![ Database icon ][ImageDatabaseIcon] \) `notes - https://mdn.github.io` represents a database, where `notes` is the name of the database and is the origin that `https://mdn.github.io` accesses the database.</span><span class="sxs-lookup"><span data-stu-id="a052c-117">\(![Database icon][ImageDatabaseIcon]\) `notes - https://mdn.github.io` represents a database, where `notes` is the name of the database and `https://mdn.github.io` is the origin that accesses the database.</span></span>  
    *   <span data-ttu-id="a052c-118">\( ![ Object Store icon ][ImageObjectStoreIcon] \) is an object `notes` store.</span><span class="sxs-lookup"><span data-stu-id="a052c-118">\(![Object Store icon][ImageObjectStoreIcon]\) `notes` is an object store.</span></span>  
    *   <span data-ttu-id="a052c-119">**title** and **body** are [indexes][MDNUsingIndexedDBUsingIndex].</span><span class="sxs-lookup"><span data-stu-id="a052c-119">**title** and **body** are [indexes][MDNUsingIndexedDBUsingIndex].</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="a052c-120">**既知の制限**  サード パーティ製のデータベースは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a052c-120">**Known Limitation**  Third-party databases are not visible.</span></span>  <span data-ttu-id="a052c-121">たとえば、ページに広告を埋め込むのに使用し、広告ネットワークが IndexedDB を使用している場合、広告ネットワークの `<iframe>` IndexedDB データは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a052c-121">For example, if you use an `<iframe>` to embed an ad on your page, and your ad network uses IndexedDB, the IndexedDB data for your ad network is not be visible.</span></span>  <span data-ttu-id="a052c-122">問題の解決[方法に#943770。][ChromiumIssue943770]</span><span class="sxs-lookup"><span data-stu-id="a052c-122">Navigate to [issue #943770][ChromiumIssue943770].</span></span>  
    
1.  <span data-ttu-id="a052c-123">データベースを選択して、原点とバージョン番号を確認します。</span><span class="sxs-lookup"><span data-stu-id="a052c-123">Choose a database to review the origin and version number.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db.msft.png" alt-text="メモ データベース" lightbox="../media/storage-application-storage-indexeddb-notes_db.msft.png":::
       <span data-ttu-id="a052c-125">メモ\*\*\*\* データベース</span><span class="sxs-lookup"><span data-stu-id="a052c-125">The **notes** database</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a052c-126">オブジェクト ストアを選択してキーと値のペアを確認します。</span><span class="sxs-lookup"><span data-stu-id="a052c-126">Choose an object store to review the key-value pairs.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="a052c-127">IndexedDB データはリアルタイムで更新されません。</span><span class="sxs-lookup"><span data-stu-id="a052c-127">IndexedDB data does not update in real-time.</span></span>  <span data-ttu-id="a052c-128">[[IndexedDB データの更新] に移動します](#refresh-indexeddb-data)。</span><span class="sxs-lookup"><span data-stu-id="a052c-128">Navigate to [Refresh IndexedDB data](#refresh-indexeddb-data).</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os.msft.png" alt-text="ノート オブジェクト ストア" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os.msft.png":::
       <span data-ttu-id="a052c-130">ノート **オブジェクト** ストア</span><span class="sxs-lookup"><span data-stu-id="a052c-130">The **notes** object store</span></span>  
    :::image-end:::  
    
    *   <span data-ttu-id="a052c-131">**エントリの総数は** 、オブジェクト ストア内のキーと値のペアの総数です。</span><span class="sxs-lookup"><span data-stu-id="a052c-131">**Total entries** is the total number of key-value pairs in the object store.</span></span>  
    *   <span data-ttu-id="a052c-132">**キー ジェネレーターの値は** 、次に使用可能なキーです。</span><span class="sxs-lookup"><span data-stu-id="a052c-132">**Key generator value** is the next available key.</span></span>  <span data-ttu-id="a052c-133">フィールドは、キー ジェネレーターを使用 [する場合にのみ表示されます][MDNBasicConceptsKeyGenerator]。</span><span class="sxs-lookup"><span data-stu-id="a052c-133">The field is only shown when using [key generators][MDNBasicConceptsKeyGenerator].</span></span>  
    
1.  <span data-ttu-id="a052c-134">[値] 列のセル **を選択** して、値を展開します。</span><span class="sxs-lookup"><span data-stu-id="a052c-134">Choose a cell in the **Value** column to expand the value.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-edge-chromium.msft.png" alt-text="IndexedDB 値を表示する" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-edge-chromium.msft.png":::
       <span data-ttu-id="a052c-136">**IndexedDB 値を表示**する</span><span class="sxs-lookup"><span data-stu-id="a052c-136">View an **IndexedDB** value</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a052c-137">次の図のタイトルや\*\*\*\* 本文などの\*\*\*\* インデックスを選択して、そのインデックスの値に従ってオブジェクト ストアを並べ替える。</span><span class="sxs-lookup"><span data-stu-id="a052c-137">Choose an index, such as **title** or **body** in the following figure, to sort the object store according to the values of that index.</span></span>  
   
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-title.msft.png" alt-text="インデックスでオブジェクト ストアを並べ替える" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-title.msft.png":::
       <span data-ttu-id="a052c-139">インデックスでオブジェクト ストアを並べ替える</span><span class="sxs-lookup"><span data-stu-id="a052c-139">Sort an object store by an index</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="a052c-140">IndexedDB データを更新する</span><span class="sxs-lookup"><span data-stu-id="a052c-140">Refresh IndexedDB data</span></span>  

<span data-ttu-id="a052c-141">アプリケーション ツールの IndexedDB **値** はリアルタイムで更新されません。</span><span class="sxs-lookup"><span data-stu-id="a052c-141">IndexedDB values in the **Application** tool do not update in real-time.</span></span>  <span data-ttu-id="a052c-142">オブジェクト**ストアを表示**してデータを更新する場合は [更新 \( Refresh \) ] を選択し、データベースを表示して [データベースの更新] を選択してすべてのデータ ![ ][ImageReloadIcon] を更新します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a052c-142">Choose **Refresh** \(![Refresh][ImageReloadIcon]\) when viewing an object store to refresh the data, or view a database and choose **Refresh database** to refresh all data.</span></span>  

:::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-refresh-database.msft.png" alt-text="データベースを表示する" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-refresh-database.msft.png":::
   <span data-ttu-id="a052c-144">データベースを表示する</span><span class="sxs-lookup"><span data-stu-id="a052c-144">View a database</span></span>  
:::image-end:::  

## <span data-ttu-id="a052c-145">IndexedDB データの編集</span><span class="sxs-lookup"><span data-stu-id="a052c-145">Edit IndexedDB data</span></span>  

<span data-ttu-id="a052c-146">IndexedDB キーと値は、アプリケーション ツールでは **編集** できません。</span><span class="sxs-lookup"><span data-stu-id="a052c-146">IndexedDB keys and values are not editable from the **Application** tool.</span></span>  <span data-ttu-id="a052c-147">ただし、DevTools はページ コンテキストにアクセスできます。ただし、DevTools 内で JavaScript コードを実行して IndexedDB データを編集できます。</span><span class="sxs-lookup"><span data-stu-id="a052c-147">Since DevTools has access to page context, however, you may run JavaScript code within DevTools to edit IndexedDB data.</span></span>  

### <span data-ttu-id="a052c-148">スニペットを使用して IndexedDB データを編集する</span><span class="sxs-lookup"><span data-stu-id="a052c-148">Edit IndexedDB data with Snippets</span></span>  

<span data-ttu-id="a052c-149">[スニペットは][DevtoolsJavascriptSnippets] 、DevTools 内に JavaScript コードのブロックを格納して実行する方法です。</span><span class="sxs-lookup"><span data-stu-id="a052c-149">[Snippets][DevtoolsJavascriptSnippets] are a way to store and run blocks of JavaScript code within DevTools.</span></span>  <span data-ttu-id="a052c-150">スニペットを実行すると、結果がコンソールに記録 **されます**。</span><span class="sxs-lookup"><span data-stu-id="a052c-150">When you run a Snippet, the result is logged to the **Console**.</span></span>  <span data-ttu-id="a052c-151">スニペットを使用して JavaScript コードを実行し、IndexedDB データベースを編集できます。</span><span class="sxs-lookup"><span data-stu-id="a052c-151">You may use a Snippet to run JavaScript code to edit an IndexedDB database.</span></span>  

:::image type="complex" source="../media/storage-sources-snippets-indexeddb-output.msft.png" alt-text="スニペットを使用して IndexedDB を操作する" lightbox="../media/storage-sources-snippets-indexeddb-output.msft.png":::
   <span data-ttu-id="a052c-153">スニペットを使用して IndexedDB を操作する</span><span class="sxs-lookup"><span data-stu-id="a052c-153">Use a Snippet to interact with IndexedDB</span></span>  
:::image-end:::  

## <span data-ttu-id="a052c-154">IndexedDB データを削除する</span><span class="sxs-lookup"><span data-stu-id="a052c-154">Delete IndexedDB data</span></span>  

### <span data-ttu-id="a052c-155">IndexedDB キーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="a052c-155">Delete an IndexedDB key-value pair</span></span>  

1.  <span data-ttu-id="a052c-156">[IndexedDB オブジェクト ストアを表示します](#view-indexeddb-data)。</span><span class="sxs-lookup"><span data-stu-id="a052c-156">[View an IndexedDB object store](#view-indexeddb-data).</span></span>  
1.  <span data-ttu-id="a052c-157">削除するキーと値のペアを選択します。</span><span class="sxs-lookup"><span data-stu-id="a052c-157">Select the key-value pair that you want to delete.</span></span>  <span data-ttu-id="a052c-158">DevTools によって強調表示され、選択された状態が示されます。</span><span class="sxs-lookup"><span data-stu-id="a052c-158">DevTools highlights it to indicate that it is selected.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os2.msft.png" alt-text="キーと値のペアを選択して削除する" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os2.msft.png":::
       <span data-ttu-id="a052c-160">キーと値のペアを選択して削除する</span><span class="sxs-lookup"><span data-stu-id="a052c-160">Select a key-value pair in order to delete it</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a052c-161">キーを押 `Delete` す、または **[Delete Selected** \( ![ Delete Selected \) ] を ][ImageDeleteIcon] 選択します。</span><span class="sxs-lookup"><span data-stu-id="a052c-161">Press the `Delete` key or choose **Delete Selected** \(![Delete Selected][ImageDeleteIcon]\).</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-delete-selected.msft.png" alt-text="キーと値のペアが削除された後のオブジェクト ストアの外観" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-delete-selected.msft.png":::
       <span data-ttu-id="a052c-163">キーと値のペアが削除された後のオブジェクト ストアの外観</span><span class="sxs-lookup"><span data-stu-id="a052c-163">How the object store looks after the key-value pair has been deleted</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="a052c-164">オブジェクト ストア内のすべてのキーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="a052c-164">Delete all key-value pairs in an object store</span></span>  

1.  <span data-ttu-id="a052c-165">[IndexedDB オブジェクト ストアを表示します](#view-indexeddb-data)。</span><span class="sxs-lookup"><span data-stu-id="a052c-165">[View an IndexedDB object store](#view-indexeddb-data).</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-clear-object-store.msft.png" alt-text="オブジェクト ストアを表示する" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-clear-object-store.msft.png":::
       <span data-ttu-id="a052c-167">オブジェクト ストアを表示する</span><span class="sxs-lookup"><span data-stu-id="a052c-167">View an object store</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a052c-168">Choose **Clear object store** \( Clear object store ![ ][ImageClearIcon] \).</span><span class="sxs-lookup"><span data-stu-id="a052c-168">Choose **Clear object store** \(![Clear object store][ImageClearIcon]\).</span></span>  
    
### <span data-ttu-id="a052c-169">IndexedDB データベースを削除する</span><span class="sxs-lookup"><span data-stu-id="a052c-169">Delete an IndexedDB database</span></span>  

1.  <span data-ttu-id="a052c-170">[削除する IndexedDB](#view-indexeddb-data) データベースを表示します。</span><span class="sxs-lookup"><span data-stu-id="a052c-170">[View the IndexedDB database](#view-indexeddb-data) that you want to delete.</span></span>  
1.  <span data-ttu-id="a052c-171">Choose **Delete database**.</span><span class="sxs-lookup"><span data-stu-id="a052c-171">Choose **Delete database**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-delete-database.msft.png" alt-text="[データベースの削除] ボタン" lightbox="../media/storage-application-storage-indexeddb-notes_db-delete-database.msft.png":::
       <span data-ttu-id="a052c-173">[ **データベースの削除]** ボタン</span><span class="sxs-lookup"><span data-stu-id="a052c-173">The **Delete database** button</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="a052c-174">すべての IndexedDB ストレージを削除する</span><span class="sxs-lookup"><span data-stu-id="a052c-174">Delete all IndexedDB storage</span></span>  

1.  <span data-ttu-id="a052c-175">[記憶域の **クリア] ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="a052c-175">Open the **Clear storage** pane.</span></span>  
1.  <span data-ttu-id="a052c-176">**[IndexedDB] チェック ボックスが有効**になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a052c-176">Make sure that the **IndexedDB** checkbox is enabled.</span></span>  
1.  <span data-ttu-id="a052c-177">[サイト **データのクリア] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a052c-177">Choose **Clear site data**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-indexeddb-clear-site-data.msft.png" alt-text="[記憶域のクリア] ウィンドウ" lightbox="../media/storage-application-clear-storage-indexeddb-clear-site-data.msft.png":::
       <span data-ttu-id="a052c-179">[ **記憶域のクリア]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="a052c-179">The **Clear storage** pane</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="a052c-180">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="a052c-180">Getting in touch with the Microsoft Edge DevTools team</span></span>  

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
> <span data-ttu-id="a052c-188">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="a052c-188">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="a052c-189">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/indexeddb) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="a052c-189">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/indexeddb) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="a052c-191">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="a052c-191">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
