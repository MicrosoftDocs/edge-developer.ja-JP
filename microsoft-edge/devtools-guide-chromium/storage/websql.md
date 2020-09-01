---
title: Microsoft Edge DevTools で Web SQL データを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 8b2e6d1a117e401f9e579cb28f81da9676eea979
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10983467"
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





# <span data-ttu-id="79ead-103">Microsoft Edge DevTools で Web SQL データを表示する</span><span class="sxs-lookup"><span data-stu-id="79ead-103">View Web SQL data with Microsoft Edge DevTools</span></span>   



> [!WARNING]
> <span data-ttu-id="79ead-104">Web SQL 仕様は [管理されていません][W3CWebSQLStatus]。</span><span class="sxs-lookup"><span data-stu-id="79ead-104">The Web SQL specification is [not being maintained][W3CWebSQLStatus].</span></span>  

<span data-ttu-id="79ead-105">このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使って Web SQL データを検査する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="79ead-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to inspect Web SQL data.</span></span>  

## <span data-ttu-id="79ead-106">Web SQL データの表示</span><span class="sxs-lookup"><span data-stu-id="79ead-106">View Web SQL Data</span></span>   

1.  <span data-ttu-id="79ead-107">[ **ソース** ] タブを選択して、[ **ソース** ] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="79ead-107">Select the **Sources** tab to open the **Sources** panel.</span></span>  <span data-ttu-id="79ead-108">通常、 **マニフェスト** ウィンドウは既定で開かれます。</span><span class="sxs-lookup"><span data-stu-id="79ead-108">The **Manifest** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       <span data-ttu-id="79ead-110">**マニフェスト**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="79ead-110">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="79ead-111">[ **WEB SQL** ] セクションを展開して、データベースとテーブルを表示します。</span><span class="sxs-lookup"><span data-stu-id="79ead-111">Expand the **Web SQL** section to view databases and tables.</span></span>  <span data-ttu-id="79ead-112">次の図では、 **html5meetup** はデータベースの下にあり、 **会議室** は表です。</span><span class="sxs-lookup"><span data-stu-id="79ead-112">In the following figure, below **html5meetup** is a database and **rooms** is a table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql.msft.png" alt-text="Web SQL ウィンドウ" lightbox="../media/storage-application-storage-web-sql.msft.png":::
       <span data-ttu-id="79ead-114">**WEB SQL**ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="79ead-114">The **Web SQL** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="79ead-115">テーブルを選択して、そのテーブルのデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="79ead-115">Select a table to view the data for that table.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png" alt-text="Web SQL テーブルのデータを表示する" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png":::
       <span data-ttu-id="79ead-117">Web SQL テーブルのデータを表示する</span><span class="sxs-lookup"><span data-stu-id="79ead-117">View the data of a Web SQL table</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="79ead-118">Web SQL データを編集する</span><span class="sxs-lookup"><span data-stu-id="79ead-118">Edit Web SQL data</span></span>   

<span data-ttu-id="79ead-119">上記の **図 3** のように、web sql テーブルを表示するときに、web sql データを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="79ead-119">You are not able to edit Web SQL data when viewing a Web SQL table, such as in **Figure 3** above.</span></span>  <span data-ttu-id="79ead-120">ただし、テーブルを編集または削除する Web SQL 本体のステートメントを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="79ead-120">But you may run statements from the Web SQL Console that edit or delete tables.</span></span>  <span data-ttu-id="79ead-121">「 [Web クエリを実行](#run-web-sql-queries)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79ead-121">See [Run Web SQL queries](#run-web-sql-queries).</span></span>  

## <span data-ttu-id="79ead-122">Web SQL クエリを実行する</span><span class="sxs-lookup"><span data-stu-id="79ead-122">Run Web SQL queries</span></span>   

1.  <span data-ttu-id="79ead-123">データベースを選択して、そのデータベースのコンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="79ead-123">Select a database to open a console for that database.</span></span>  
1.  <span data-ttu-id="79ead-124">Web SQL ステートメントを入力し、を押して `Enter` 実行します。</span><span class="sxs-lookup"><span data-stu-id="79ead-124">Type a Web SQL statement, then press `Enter` to run it.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png" alt-text="Web SQL コンソールを使用してテーブルから行を削除する" lightbox="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png":::
       <span data-ttu-id="79ead-126">Web SQL コンソールを使用してテーブルから行を削除する</span><span class="sxs-lookup"><span data-stu-id="79ead-126">Use the Web SQL Console to delete a row from a table</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="79ead-127">Web SQL テーブルを更新する</span><span class="sxs-lookup"><span data-stu-id="79ead-127">Refresh a Web SQL table</span></span>   

<span data-ttu-id="79ead-128">DevTools では、表がリアルタイムで更新されることはありません。</span><span class="sxs-lookup"><span data-stu-id="79ead-128">DevTools does not update tables in real-time.</span></span>  <span data-ttu-id="79ead-129">表のデータを更新するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="79ead-129">To update the data in a table:</span></span>  

1.  <span data-ttu-id="79ead-130">[WEB SQL テーブルのデータを表示](#view-web-sql-data)する。</span><span class="sxs-lookup"><span data-stu-id="79ead-130">[View the data in a Web SQL table](#view-web-sql-data).</span></span>  
1.  <span data-ttu-id="79ead-131">[ **Refresh** (更新)] を選び ![ ][ImageRefreshIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="79ead-131">Select **Refresh** \(![Refresh][ImageRefreshIcon]\).</span></span>  
    
## <span data-ttu-id="79ead-132">Web SQL テーブルの列をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="79ead-132">Filter out columns in a Web SQL table</span></span>   

1.  <span data-ttu-id="79ead-133">[WEB SQL テーブルのデータを表示](#view-web-sql-data)する。</span><span class="sxs-lookup"><span data-stu-id="79ead-133">[View the data in a Web SQL table](#view-web-sql-data).</span></span>  
1.  <span data-ttu-id="79ead-134">[ **表示列** ] ボックスを使用して、表示する列を指定します。</span><span class="sxs-lookup"><span data-stu-id="79ead-134">Use the **Visible columns** text box to specify what columns you want to show.</span></span>  <span data-ttu-id="79ead-135">列名を CSV リストとして指定します。</span><span class="sxs-lookup"><span data-stu-id="79ead-135">Provide the column names as a CSV list.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png" alt-text="表示される列の数を減らすには、[可視列] ボックスを使用します。" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png":::
       <span data-ttu-id="79ead-137">表示される列の数を減らすには、[ **可視列** ] ボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="79ead-137">Use the **Visible Columns** text box to reduce the number of columns shown</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="79ead-138">すべての Web SQL データを削除する</span><span class="sxs-lookup"><span data-stu-id="79ead-138">Delete all Web SQL data</span></span>   

1.  <span data-ttu-id="79ead-139">[ **記憶域のクリア** ] ウィンドウを開く。</span><span class="sxs-lookup"><span data-stu-id="79ead-139">Open the **Clear Storage** pane.</span></span>  
1.  <span data-ttu-id="79ead-140">[ **WEB SQL** ] チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="79ead-140">Make sure that the **Web SQL** checkbox is enabled.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-web-sql.msft.png" alt-text="Web SQL チェックボックス" lightbox="../media/storage-application-clear-storage-web-sql.msft.png":::
       <span data-ttu-id="79ead-142">**WEB SQL**チェックボックス</span><span class="sxs-lookup"><span data-stu-id="79ead-142">The **Web SQL** checkbox</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="79ead-143">[ **サイトデータのクリア**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="79ead-143">Select **Clear site data**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-clear-site-data-button.msft.png" alt-text="[サイトデータのクリア] ボタン" lightbox="../media/storage-application-clear-storage-clear-site-data-button.msft.png":::
       <span data-ttu-id="79ead-145">[ **サイトデータのクリア** ] ボタン</span><span class="sxs-lookup"><span data-stu-id="79ead-145">The **Clear Site Data** button</span></span>  
    :::image-end:::  
    
<!--  
 


-->  

<!-- image links -->  

[ImageRefreshIcon]: ../media/refresh-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[W3CWebSQLStatus]: https://w3.org/TR/webdatabase/#status-of-this-document "Web SQL データベース |勧告"  

> [!NOTE]
> <span data-ttu-id="79ead-148">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="79ead-148">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="79ead-149">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/websql) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="79ead-149">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/websql) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="79ead-151">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="79ead-151">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
