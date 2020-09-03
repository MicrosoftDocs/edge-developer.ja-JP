---
description: Microsoft Edge DevTools のアプリケーションパネルから Web SQL データを表示する方法について説明します。
title: Microsoft Edge DevTools で Web SQL データを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: cc2f726c80fbf0c943b43ff6c131e9479db75b78
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993535"
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





# Microsoft Edge DevTools で Web SQL データを表示する   



> [!WARNING]
> Web SQL 仕様は [管理されていません][W3CWebSQLStatus]。  

このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使って Web SQL データを検査する方法について説明します。  

## Web SQL データの表示   

1.  [ **ソース** ] タブを選択して、[ **ソース** ] パネルを開きます。  通常、 **マニフェスト** ウィンドウは既定で開かれます。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       **マニフェスト**ウィンドウ  
    :::image-end:::  
    
1.  [ **WEB SQL** ] セクションを展開して、データベースとテーブルを表示します。  次の図では、 **html5meetup** はデータベースの下にあり、 **会議室** は表です。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql.msft.png" alt-text="Web SQL ウィンドウ" lightbox="../media/storage-application-storage-web-sql.msft.png":::
       **WEB SQL**ウィンドウ  
    :::image-end:::  
    
1.  テーブルを選択して、そのテーブルのデータを表示します。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png" alt-text="Web SQL テーブルのデータを表示する" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png":::
       Web SQL テーブルのデータを表示する  
    :::image-end:::  
    
## Web SQL データを編集する   

上記の **図 3** のように、web sql テーブルを表示するときに、web sql データを編集することはできません。  ただし、テーブルを編集または削除する Web SQL 本体のステートメントを実行することができます。  「 [Web クエリを実行](#run-web-sql-queries)する」を参照してください。  

## Web SQL クエリを実行する   

1.  データベースを選択して、そのデータベースのコンソールを開きます。  
1.  Web SQL ステートメントを入力し、を押して `Enter` 実行します。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png" alt-text="Web SQL コンソールを使用してテーブルから行を削除する" lightbox="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png":::
       Web SQL コンソールを使用してテーブルから行を削除する  
    :::image-end:::  
    
## Web SQL テーブルを更新する   

DevTools では、表がリアルタイムで更新されることはありません。  表のデータを更新するには、次の操作を行います。  

1.  [WEB SQL テーブルのデータを表示](#view-web-sql-data)する。  
1.  [ **Refresh** (更新)] を選び ![ ][ImageRefreshIcon] ます。  
    
## Web SQL テーブルの列をフィルター処理する   

1.  [WEB SQL テーブルのデータを表示](#view-web-sql-data)する。  
1.  [ **表示列** ] ボックスを使用して、表示する列を指定します。  列名を CSV リストとして指定します。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png" alt-text="表示される列の数を減らすには、[可視列] ボックスを使用します。" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png":::
       表示される列の数を減らすには、[ **可視列** ] ボックスを使用します。  
    :::image-end:::  
    
## すべての Web SQL データを削除する   

1.  [ **記憶域のクリア** ] ウィンドウを開く。  
1.  [ **WEB SQL** ] チェックボックスがオンになっていることを確認します。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-web-sql.msft.png" alt-text="Web SQL チェックボックス" lightbox="../media/storage-application-clear-storage-web-sql.msft.png":::
       **WEB SQL**チェックボックス  
    :::image-end:::  
    
1.  [ **サイトデータのクリア**] を選びます。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-clear-site-data-button.msft.png" alt-text="[サイトデータのクリア] ボタン" lightbox="../media/storage-application-clear-storage-clear-site-data-button.msft.png":::
       [ **サイトデータのクリア** ] ボタン  
    :::image-end:::  
    
<!--  
 


-->  

<!-- image links -->  

[ImageRefreshIcon]: ../media/refresh-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[W3CWebSQLStatus]: https://w3.org/TR/webdatabase/#status-of-this-document "Web SQL データベース |勧告"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/websql) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
