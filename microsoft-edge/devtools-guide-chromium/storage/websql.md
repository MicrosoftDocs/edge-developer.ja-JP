---
title: Microsoft Edge DevTools で Web SQL データを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 7a1e3e47f6761cfdb23488683107ed0df6a8f4e2
ms.sourcegitcommit: ad68bfbb355f6cfdaaf6612b77ea3985d4d6a58b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "10612061"
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





# <span data-ttu-id="5e530-103">Microsoft Edge DevTools で Web SQL データを表示する</span><span class="sxs-lookup"><span data-stu-id="5e530-103">View Web SQL Data With Microsoft Edge DevTools</span></span>   



> [!WARNING]
> <span data-ttu-id="5e530-104">Web SQL 仕様は[管理されていません][W3CWebSQLStatus]。</span><span class="sxs-lookup"><span data-stu-id="5e530-104">The Web SQL specification is [not being maintained][W3CWebSQLStatus].</span></span>  

<span data-ttu-id="5e530-105">このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使って Web SQL データを検査する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5e530-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect Web SQL data.</span></span>  

## <span data-ttu-id="5e530-106">Web SQL データの表示</span><span class="sxs-lookup"><span data-stu-id="5e530-106">View Web SQL Data</span></span>   

1.  <span data-ttu-id="5e530-107">[**ソース**] タブを選択して、[**ソース**] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5e530-107">Select the **Sources** tab to open the **Sources** panel.</span></span>  <span data-ttu-id="5e530-108">通常、**マニフェスト**ウィンドウは既定で開かれます。</span><span class="sxs-lookup"><span data-stu-id="5e530-108">The **Manifest** pane usually opens by default.</span></span>  
    
    > ##### <span data-ttu-id="5e530-109">図 1</span><span class="sxs-lookup"><span data-stu-id="5e530-109">Figure 1</span></span>  
    > <span data-ttu-id="5e530-110">マニフェストウィンドウ</span><span class="sxs-lookup"><span data-stu-id="5e530-110">The Manifest pane</span></span>  
    > ![マニフェストウィンドウ][ImageManifestPane]  
    
1.  <span data-ttu-id="5e530-112">[ **WEB SQL** ] セクションを展開して、データベースとテーブルを表示します。</span><span class="sxs-lookup"><span data-stu-id="5e530-112">Expand the **Web SQL** section to view databases and tables.</span></span>  <span data-ttu-id="5e530-113">**Html5meetup**の下の[図 2](#figure-2)にはデータベースがあり、**会議室**は表です。</span><span class="sxs-lookup"><span data-stu-id="5e530-113">In [Figure 2](#figure-2) below **html5meetup** is a database and **rooms** is a table.</span></span>  
    
    > ##### <span data-ttu-id="5e530-114">図 2</span><span class="sxs-lookup"><span data-stu-id="5e530-114">Figure 2</span></span>  
    > <span data-ttu-id="5e530-115">Web SQL ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="5e530-115">The Web SQL pane</span></span>  
    > ![Web SQL ウィンドウ][ImageWebSQLPane]  

1.  <span data-ttu-id="5e530-117">テーブルを選択して、そのテーブルのデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="5e530-117">Select a table to view the data for that table.</span></span>  
    
    > ##### <span data-ttu-id="5e530-118">図 3</span><span class="sxs-lookup"><span data-stu-id="5e530-118">Figure 3</span></span>  
    > <span data-ttu-id="5e530-119">**会議室**Web SQL テーブルのデータの表示</span><span class="sxs-lookup"><span data-stu-id="5e530-119">Viewing the data of the **rooms** Web SQL table</span></span>  
    > ![Web SQL テーブルのデータを表示する][ImageWebSQLTable]  

## <span data-ttu-id="5e530-121">Web SQL データを編集する</span><span class="sxs-lookup"><span data-stu-id="5e530-121">Edit Web SQL data</span></span>   

<span data-ttu-id="5e530-122">上記の**図 3**のように、web sql テーブルを表示するときに、web sql データを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="5e530-122">You are not able to edit Web SQL data when viewing a Web SQL table, such as in **Figure 3** above.</span></span>  <span data-ttu-id="5e530-123">ただし、テーブルを編集または削除する Web SQL 本体のステートメントを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="5e530-123">But you may run statements from the Web SQL Console that edit or delete tables.</span></span>  <span data-ttu-id="5e530-124">「 [Web クエリを実行](#run-web-sql-queries)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e530-124">See [Run Web SQL queries](#run-web-sql-queries).</span></span>  

## <span data-ttu-id="5e530-125">Web SQL クエリを実行する</span><span class="sxs-lookup"><span data-stu-id="5e530-125">Run Web SQL queries</span></span>   

1.  <span data-ttu-id="5e530-126">データベースを選択して、そのデータベースのコンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="5e530-126">Select a database to open a console for that database.</span></span>  

1.  <span data-ttu-id="5e530-127">Web SQL ステートメントを入力し、を押して `Enter` 実行します。</span><span class="sxs-lookup"><span data-stu-id="5e530-127">Type a Web SQL statement, then press `Enter` to run it.</span></span>  
    
    > ##### <span data-ttu-id="5e530-128">図 4</span><span class="sxs-lookup"><span data-stu-id="5e530-128">Figure 4</span></span>  
    > <span data-ttu-id="5e530-129">Web SQL コンソールを使用して、**会議室**テーブルから行を削除する</span><span class="sxs-lookup"><span data-stu-id="5e530-129">Using the Web SQL Console to delete a row from the **rooms** table</span></span>  
    > ![Web SQL 本体を使用してテーブルから行を削除する][ImageWebSQLEdit]  

## <span data-ttu-id="5e530-131">Web SQL テーブルを更新する</span><span class="sxs-lookup"><span data-stu-id="5e530-131">Refresh a Web SQL table</span></span>   

<span data-ttu-id="5e530-132">DevTools では、表がリアルタイムで更新されることはありません。</span><span class="sxs-lookup"><span data-stu-id="5e530-132">DevTools does not update tables in real-time.</span></span>  <span data-ttu-id="5e530-133">表のデータを更新するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5e530-133">To update the data in a table:</span></span>  

1.  <span data-ttu-id="5e530-134">[WEB SQL テーブルのデータを表示](#view-web-sql-data)する。</span><span class="sxs-lookup"><span data-stu-id="5e530-134">[View the data in a Web SQL table](#view-web-sql-data).</span></span>  
1.  <span data-ttu-id="5e530-135">[**更新の更新]** を選び ![ ][ImageRefreshIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="5e530-135">Select **Refresh** ![Refresh][ImageRefreshIcon].</span></span>  

## <span data-ttu-id="5e530-136">Web SQL テーブルの列をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="5e530-136">Filter out columns in a Web SQL table</span></span>   

1.  <span data-ttu-id="5e530-137">[WEB SQL テーブルのデータを表示](#view-web-sql-data)する。</span><span class="sxs-lookup"><span data-stu-id="5e530-137">[View the data in a Web SQL table](#view-web-sql-data).</span></span>  
1.  <span data-ttu-id="5e530-138">[**表示列**] ボックスを使用して、表示する列を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e530-138">Use the **Visible columns** text box to specify what columns you want to show.</span></span>  <span data-ttu-id="5e530-139">列名を CSV リストとして指定します。</span><span class="sxs-lookup"><span data-stu-id="5e530-139">Provide the column names as a CSV list.</span></span>  
    
    > ##### <span data-ttu-id="5e530-140">図 5</span><span class="sxs-lookup"><span data-stu-id="5e530-140">Figure 5</span></span>  
    > <span data-ttu-id="5e530-141">[**可視列**] ボックスを使用して、 `room_name` および列のみを表示する `last_updated`</span><span class="sxs-lookup"><span data-stu-id="5e530-141">Using the **Visible Columns** text box to only show the `room_name` and `last_updated` columns</span></span>  
    > ![表示される列の数を減らすには、[表示列] ボックスを使用します。][ImageWebSQLFilter]  

## <span data-ttu-id="5e530-143">すべての Web SQL データを削除する</span><span class="sxs-lookup"><span data-stu-id="5e530-143">Delete all Web SQL data</span></span>   

1.  <span data-ttu-id="5e530-144">[**記憶域のクリア**] ウィンドウを開く。</span><span class="sxs-lookup"><span data-stu-id="5e530-144">Open the **Clear Storage** pane.</span></span>  
1.  <span data-ttu-id="5e530-145">[ **WEB SQL** ] チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e530-145">Make sure that the **Web SQL** checkbox is enabled.</span></span>  
    
    > ##### <span data-ttu-id="5e530-146">図 6</span><span class="sxs-lookup"><span data-stu-id="5e530-146">Figure 6</span></span>  
    > <span data-ttu-id="5e530-147">**WEB SQL**チェックボックス</span><span class="sxs-lookup"><span data-stu-id="5e530-147">The **Web SQL** checkbox</span></span>  
    > ![Web SQL チェックボックス][ImageWebSQLCheckbox]  

1.  <span data-ttu-id="5e530-149">[**サイトデータのクリア**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5e530-149">Select **Clear site data**.</span></span>  
    
    > ##### <span data-ttu-id="5e530-150">図 7</span><span class="sxs-lookup"><span data-stu-id="5e530-150">Figure 7</span></span>  
    > <span data-ttu-id="5e530-151">[**サイトデータのクリア**] ボタン</span><span class="sxs-lookup"><span data-stu-id="5e530-151">The **Clear Site Data** button</span></span>  
    > ![[サイトデータのクリア] ボタン][ImageClearWebSQL]  

 



<!-- image links -->  

[ImageRefreshIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-icon.msft.png  

[ImageManifestPane]: /microsoft-edge/devtools-guide-chromium/media/storage-application-manifest.msft.png "図 1: [マニフェスト] ウィンドウ"  
[ImageWebSQLPane]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-web-sql.msft.png "図 2: [Web SQL] ウィンドウ"  
[ImageWebSQLTable]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png "図 3: Web SQL テーブルのデータの表示"  
[ImageWebSQLEdit]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-web-sql-html5meetup-commands.msft.png "図 4: Web SQL 本体を使ってテーブルから行を削除する"  
[ImageWebSQLFilter]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png "図 5: 表示される列の数を減らすために [表示列] テキストボックスを使用する"  
[ImageWebSQLCheckbox]: /microsoft-edge/devtools-guide-chromium/media/storage-application-clear-storage-web-sql.msft.png "図 6: [Web SQL] チェックボックス"  
[ImageClearWebSQL]: /microsoft-edge/devtools-guide-chromium/media/storage-application-clear-storage-clear-site-data-button.msft.png "図 7: [サイトデータのクリア] ボタン"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  

[W3CWebSQLStatus]: https://w3.org/TR/webdatabase/#status-of-this-document "Web SQL データベース |勧告"  

> [!NOTE]
> <span data-ttu-id="5e530-162">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="5e530-162">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="5e530-163">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/storage/websql)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="5e530-163">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/websql) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="5e530-165">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="5e530-165">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
