---
description: Microsoft Edge DevTools SQLアプリケーション パネルから Web データを表示する方法。
title: Microsoft Edge DevTools SQL Web データを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 326fe492a3436a40d81c8e31db99a26da4ea054f
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397553"
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

# <a name="view-web-sql-data-with-microsoft-edge-devtools"></a><span data-ttu-id="0087b-104">Microsoft Edge DevTools SQL Web データを表示する</span><span class="sxs-lookup"><span data-stu-id="0087b-104">View Web SQL data with Microsoft Edge DevTools</span></span>  

> [!WARNING]
> <span data-ttu-id="0087b-105">Web SQL仕様 [は維持されません][W3CWebSQLStatus]。</span><span class="sxs-lookup"><span data-stu-id="0087b-105">The Web SQL specification is [not being maintained][W3CWebSQLStatus].</span></span>  

<span data-ttu-id="0087b-106">このガイドでは [、Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使用して Web データを調SQLします。</span><span class="sxs-lookup"><span data-stu-id="0087b-106">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect Web SQL data.</span></span>  

## <a name="view-web-sql-data"></a><span data-ttu-id="0087b-107">Web データの表示SQLする</span><span class="sxs-lookup"><span data-stu-id="0087b-107">View Web SQL Data</span></span>  

1.  <span data-ttu-id="0087b-108">[ソース **] ツールを** 選択して [ソース] **ツールを開** きます。</span><span class="sxs-lookup"><span data-stu-id="0087b-108">Choose the **Sources** tool to open the **Sources** tool.</span></span>  <span data-ttu-id="0087b-109">通常 **、マニフェスト ウィンドウ** は既定で開きます。</span><span class="sxs-lookup"><span data-stu-id="0087b-109">The **Manifest** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="[マニフェスト] ウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="0087b-111">[ **マニフェスト]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="0087b-111">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0087b-112">[Web ページ **] セクションSQL** データベースとテーブルを表示します。</span><span class="sxs-lookup"><span data-stu-id="0087b-112">Expand the **Web SQL** section to view databases and tables.</span></span>  <span data-ttu-id="0087b-113">次の図では、 **以下の html5meetup は** データベースであり、 **会議室は** 表です。</span><span class="sxs-lookup"><span data-stu-id="0087b-113">In the following figure, below **html5meetup** is a database and **rooms** is a table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql.msft.png" alt-text="[Web SQL] ウィンドウ" lightbox="../media/storage-application-storage-web-sql.msft.png":::
       <span data-ttu-id="0087b-115">[Web **SQL]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="0087b-115">The **Web SQL** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0087b-116">テーブルを選択して、そのテーブルのデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="0087b-116">Choose a table to view the data for that table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png" alt-text="Web テーブルのデータをSQLする" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png":::
       <span data-ttu-id="0087b-118">Web テーブルのデータをSQLする</span><span class="sxs-lookup"><span data-stu-id="0087b-118">View the data of a Web SQL table</span></span>  
    :::image-end:::  
    
## <a name="edit-web-sql-data"></a><span data-ttu-id="0087b-119">Web データのSQL編集</span><span class="sxs-lookup"><span data-stu-id="0087b-119">Edit Web SQL data</span></span>  

<span data-ttu-id="0087b-120">前の例のように、Web SQLテーブルを表示SQL Web データを編集できない。</span><span class="sxs-lookup"><span data-stu-id="0087b-120">You are not able to edit Web SQL data when viewing a Web SQL table, such as in previous above.</span></span>  <span data-ttu-id="0087b-121">ただし、テーブルを編集または削除する web SQLコンソールからステートメントを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0087b-121">But you may run statements from the Web SQL Console that edit or delete tables.</span></span>  <span data-ttu-id="0087b-122">[Web クエリの [実行] SQL移動します](#run-web-sql-queries)。</span><span class="sxs-lookup"><span data-stu-id="0087b-122">Navigate to [Run Web SQL queries](#run-web-sql-queries).</span></span>  

## <a name="run-web-sql-queries"></a><span data-ttu-id="0087b-123">Web クエリSQL実行する</span><span class="sxs-lookup"><span data-stu-id="0087b-123">Run Web SQL queries</span></span>  

1.  <span data-ttu-id="0087b-124">データベースを選択して、そのデータベースのコンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="0087b-124">Choose a database to open a console for that database.</span></span>  
1.  <span data-ttu-id="0087b-125">[Web ファイル] SQLを入力し、実行 `Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="0087b-125">Type a Web SQL statement, then select `Enter` to run it.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png" alt-text="Web コンソールをSQLテーブルから行を削除する" lightbox="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png":::
       <span data-ttu-id="0087b-127">Web コンソールをSQLテーブルから行を削除する</span><span class="sxs-lookup"><span data-stu-id="0087b-127">Use the Web SQL Console to delete a row from a table</span></span>  
    :::image-end:::  
    
## <a name="refresh-a-web-sql-table"></a><span data-ttu-id="0087b-128">Web テーブルをSQLする</span><span class="sxs-lookup"><span data-stu-id="0087b-128">Refresh a Web SQL table</span></span>  

<span data-ttu-id="0087b-129">DevTools はリアルタイムでテーブルを更新しない。</span><span class="sxs-lookup"><span data-stu-id="0087b-129">DevTools does not update tables in real-time.</span></span>  <span data-ttu-id="0087b-130">テーブル内のデータを更新するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="0087b-130">To update the data in a table, complete the following actions.</span></span>  

1.  <span data-ttu-id="0087b-131">[Web テーブルでデータを表示SQLします](#view-web-sql-data)。</span><span class="sxs-lookup"><span data-stu-id="0087b-131">[View the data in a Web SQL table](#view-web-sql-data).</span></span>  
1.  <span data-ttu-id="0087b-132">[ **更新** \( ![ Refresh ][ImageRefreshIcon] \] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="0087b-132">Choose **Refresh** \(![Refresh][ImageRefreshIcon]\).</span></span>  
    
## <a name="filter-out-columns-in-a-web-sql-table"></a><span data-ttu-id="0087b-133">Web テーブル内の列をSQLする</span><span class="sxs-lookup"><span data-stu-id="0087b-133">Filter out columns in a Web SQL table</span></span>  

1.  <span data-ttu-id="0087b-134">[Web テーブルでデータを表示SQLします](#view-web-sql-data)。</span><span class="sxs-lookup"><span data-stu-id="0087b-134">[View the data in a Web SQL table](#view-web-sql-data).</span></span>  
1.  <span data-ttu-id="0087b-135">表示する **列を** 指定するには、[表示列] テキスト ボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="0087b-135">Use the **Visible columns** text box to specify what columns you want to show.</span></span>  <span data-ttu-id="0087b-136">列名を CSV リストとして指定します。</span><span class="sxs-lookup"><span data-stu-id="0087b-136">Provide the column names as a CSV list.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png" alt-text="[表示列] テキスト ボックスを使用して、表示される列の数を減らす" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png":::
       <span data-ttu-id="0087b-138">[表示 **列] テキスト** ボックスを使用して、表示される列の数を減らす</span><span class="sxs-lookup"><span data-stu-id="0087b-138">Use the **Visible Columns** text box to reduce the number of columns shown</span></span>  
    :::image-end:::  
    
## <a name="delete-all-web-sql-data"></a><span data-ttu-id="0087b-139">すべての Web データをSQLする</span><span class="sxs-lookup"><span data-stu-id="0087b-139">Delete all Web SQL data</span></span>  

1.  <span data-ttu-id="0087b-140">[ストレージの **クリア] ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="0087b-140">Open the **Clear Storage** pane.</span></span>  
1.  <span data-ttu-id="0087b-141">[Web ファイル] チェック **ボックスSQL** オンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0087b-141">Make sure that the **Web SQL** checkbox is turned on.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-web-sql.msft.png" alt-text="[Web SQL] チェック ボックス" lightbox="../media/storage-application-clear-storage-web-sql.msft.png":::
       <span data-ttu-id="0087b-143">**[Web SQL]** チェック ボックス</span><span class="sxs-lookup"><span data-stu-id="0087b-143">The **Web SQL** checkbox</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0087b-144">[サイト **データのクリア] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0087b-144">Choose **Clear site data**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-clear-site-data-button.msft.png" alt-text="[サイト データのクリア] ボタン" lightbox="../media/storage-application-clear-storage-clear-site-data-button.msft.png":::
       <span data-ttu-id="0087b-146">[ **サイト データのクリア]** ボタン</span><span class="sxs-lookup"><span data-stu-id="0087b-146">The **Clear Site Data** button</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="0087b-147">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="0087b-147">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageRefreshIcon]: ../media/refresh-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[W3CWebSQLStatus]: https://w3.org/TR/webdatabase/#status-of-this-document "Web SQL データベース |W3C"  

> [!NOTE]
> <span data-ttu-id="0087b-150">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="0087b-150">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0087b-151">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/websql) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="0087b-151">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/websql) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="0087b-153">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="0087b-153">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
