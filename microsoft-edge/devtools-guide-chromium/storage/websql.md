---
description: Microsoft Edge DevTools のアプリケーションパネルから Web SQL データを表示する方法について説明します。
title: Microsoft Edge DevTools で Web SQL データを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0396a00ec354fdd707bc4d484242d4cf844db5f9
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125469"
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

# <span data-ttu-id="0a2ec-104">Microsoft Edge DevTools で Web SQL データを表示する</span><span class="sxs-lookup"><span data-stu-id="0a2ec-104">View Web SQL data with Microsoft Edge DevTools</span></span>  

> [!WARNING]
> <span data-ttu-id="0a2ec-105">Web SQL 仕様は [管理されていません][W3CWebSQLStatus]。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-105">The Web SQL specification is [not being maintained][W3CWebSQLStatus].</span></span>  

<span data-ttu-id="0a2ec-106">このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使って Web SQL データを検査する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-106">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect Web SQL data.</span></span>  

## <span data-ttu-id="0a2ec-107">Web SQL データの表示</span><span class="sxs-lookup"><span data-stu-id="0a2ec-107">View Web SQL Data</span></span>  

1.  <span data-ttu-id="0a2ec-108">[ **ソース** ] タブを選択して、[ **ソース** ] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-108">Select the **Sources** tab to open the **Sources** panel.</span></span>  <span data-ttu-id="0a2ec-109">通常、 **マニフェスト** ウィンドウは既定で開かれます。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-109">The **Manifest** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="0a2ec-111">**マニフェスト**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="0a2ec-111">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0a2ec-112">[ **WEB SQL** ] セクションを展開して、データベースとテーブルを表示します。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-112">Expand the **Web SQL** section to view databases and tables.</span></span>  <span data-ttu-id="0a2ec-113">次の図では、 **html5meetup** はデータベースの下にあり、 **会議室** は表です。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-113">In the following figure, below **html5meetup** is a database and **rooms** is a table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-storage-web-sql.msft.png":::
       <span data-ttu-id="0a2ec-115">**WEB SQL**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="0a2ec-115">The **Web SQL** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0a2ec-116">テーブルを選択して、そのテーブルのデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-116">Select a table to view the data for that table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png":::
       <span data-ttu-id="0a2ec-118">Web SQL テーブルのデータを表示する</span><span class="sxs-lookup"><span data-stu-id="0a2ec-118">View the data of a Web SQL table</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="0a2ec-119">Web SQL データを編集する</span><span class="sxs-lookup"><span data-stu-id="0a2ec-119">Edit Web SQL data</span></span>  

<span data-ttu-id="0a2ec-120">上記の **図 3** のように、web sql テーブルを表示するときに、web sql データを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-120">You are not able to edit Web SQL data when viewing a Web SQL table, such as in **Figure 3** above.</span></span>  <span data-ttu-id="0a2ec-121">ただし、テーブルを編集または削除する Web SQL 本体のステートメントを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-121">But you may run statements from the Web SQL Console that edit or delete tables.</span></span>  <span data-ttu-id="0a2ec-122">「 [Web クエリを実行](#run-web-sql-queries)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-122">See [Run Web SQL queries](#run-web-sql-queries).</span></span>  

## <span data-ttu-id="0a2ec-123">Web SQL クエリを実行する</span><span class="sxs-lookup"><span data-stu-id="0a2ec-123">Run Web SQL queries</span></span>  

1.  <span data-ttu-id="0a2ec-124">データベースを選択して、そのデータベースのコンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-124">Select a database to open a console for that database.</span></span>  
1.  <span data-ttu-id="0a2ec-125">Web SQL ステートメントを入力して、[実行] を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-125">Type a Web SQL statement, then select `Enter` to run it.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png":::
       <span data-ttu-id="0a2ec-127">Web SQL コンソールを使用してテーブルから行を削除する</span><span class="sxs-lookup"><span data-stu-id="0a2ec-127">Use the Web SQL Console to delete a row from a table</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="0a2ec-128">Web SQL テーブルを更新する</span><span class="sxs-lookup"><span data-stu-id="0a2ec-128">Refresh a Web SQL table</span></span>  

<span data-ttu-id="0a2ec-129">DevTools では、表がリアルタイムで更新されることはありません。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-129">DevTools does not update tables in real-time.</span></span>  <span data-ttu-id="0a2ec-130">表のデータを更新するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-130">To update the data in a table:</span></span>  

1.  <span data-ttu-id="0a2ec-131">[WEB SQL テーブルのデータを表示](#view-web-sql-data)する。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-131">[View the data in a Web SQL table](#view-web-sql-data).</span></span>  
1.  <span data-ttu-id="0a2ec-132">[ **Refresh** ] ( ![ 更新 ][ImageRefreshIcon] \) を選びます。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-132">Choose **Refresh** \(![Refresh][ImageRefreshIcon]\).</span></span>  
    
## <span data-ttu-id="0a2ec-133">Web SQL テーブルの列をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="0a2ec-133">Filter out columns in a Web SQL table</span></span>  

1.  <span data-ttu-id="0a2ec-134">[WEB SQL テーブルのデータを表示](#view-web-sql-data)する。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-134">[View the data in a Web SQL table](#view-web-sql-data).</span></span>  
1.  <span data-ttu-id="0a2ec-135">[ **表示列** ] ボックスを使用して、表示する列を指定します。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-135">Use the **Visible columns** text box to specify what columns you want to show.</span></span>  <span data-ttu-id="0a2ec-136">列名を CSV リストとして指定します。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-136">Provide the column names as a CSV list.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png":::
       <span data-ttu-id="0a2ec-138">表示される列の数を減らすには、[ **可視列** ] ボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-138">Use the **Visible Columns** text box to reduce the number of columns shown</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="0a2ec-139">すべての Web SQL データを削除する</span><span class="sxs-lookup"><span data-stu-id="0a2ec-139">Delete all Web SQL data</span></span>  

1.  <span data-ttu-id="0a2ec-140">[ **記憶域のクリア** ] ウィンドウを開く。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-140">Open the **Clear Storage** pane.</span></span>  
1.  <span data-ttu-id="0a2ec-141">[ **WEB SQL** ] チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-141">Make sure that the **Web SQL** checkbox is enabled.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-web-sql.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-clear-storage-web-sql.msft.png":::
       <span data-ttu-id="0a2ec-143">**WEB SQL**チェックボックス</span><span class="sxs-lookup"><span data-stu-id="0a2ec-143">The **Web SQL** checkbox</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0a2ec-144">[ **サイトデータのクリア**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-144">Choose **Clear site data**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-clear-site-data-button.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-clear-storage-clear-site-data-button.msft.png":::
       <span data-ttu-id="0a2ec-146">[ **サイトデータのクリア** ] ボタン</span><span class="sxs-lookup"><span data-stu-id="0a2ec-146">The **Clear Site Data** button</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="0a2ec-147">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="0a2ec-147">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageRefreshIcon]: ../media/refresh-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[W3CWebSQLStatus]: https://w3.org/TR/webdatabase/#status-of-this-document "Web SQL データベース |勧告"  

> [!NOTE]
> <span data-ttu-id="0a2ec-150">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-150">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0a2ec-151">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/websql) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-151">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/websql) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="0a2ec-153">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="0a2ec-153">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
