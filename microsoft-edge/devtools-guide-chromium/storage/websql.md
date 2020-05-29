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





# Microsoft Edge DevTools で Web SQL データを表示する   



> [!WARNING]
> Web SQL 仕様は[管理されていません][W3CWebSQLStatus]。  

このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使って Web SQL データを検査する方法について説明します。  

## Web SQL データの表示   

1.  [**ソース**] タブを選択して、[**ソース**] パネルを開きます。  通常、**マニフェスト**ウィンドウは既定で開かれます。  
    
    > ##### 図 1  
    > マニフェストウィンドウ  
    > ![マニフェストウィンドウ][ImageManifestPane]  
    
1.  [ **WEB SQL** ] セクションを展開して、データベースとテーブルを表示します。  **Html5meetup**の下の[図 2](#figure-2)にはデータベースがあり、**会議室**は表です。  
    
    > ##### 図 2  
    > Web SQL ウィンドウ  
    > ![Web SQL ウィンドウ][ImageWebSQLPane]  

1.  テーブルを選択して、そのテーブルのデータを表示します。  
    
    > ##### 図 3  
    > **会議室**Web SQL テーブルのデータの表示  
    > ![Web SQL テーブルのデータを表示する][ImageWebSQLTable]  

## Web SQL データを編集する   

上記の**図 3**のように、web sql テーブルを表示するときに、web sql データを編集することはできません。  ただし、テーブルを編集または削除する Web SQL 本体のステートメントを実行することができます。  「 [Web クエリを実行](#run-web-sql-queries)する」を参照してください。  

## Web SQL クエリを実行する   

1.  データベースを選択して、そのデータベースのコンソールを開きます。  

1.  Web SQL ステートメントを入力し、を押して `Enter` 実行します。  
    
    > ##### 図 4  
    > Web SQL コンソールを使用して、**会議室**テーブルから行を削除する  
    > ![Web SQL 本体を使用してテーブルから行を削除する][ImageWebSQLEdit]  

## Web SQL テーブルを更新する   

DevTools では、表がリアルタイムで更新されることはありません。  表のデータを更新するには、次の操作を行います。  

1.  [WEB SQL テーブルのデータを表示](#view-web-sql-data)する。  
1.  [**更新の更新]** を選び ![ ][ImageRefreshIcon] ます。  

## Web SQL テーブルの列をフィルター処理する   

1.  [WEB SQL テーブルのデータを表示](#view-web-sql-data)する。  
1.  [**表示列**] ボックスを使用して、表示する列を指定します。  列名を CSV リストとして指定します。  
    
    > ##### 図 5  
    > [**可視列**] ボックスを使用して、 `room_name` および列のみを表示する `last_updated`  
    > ![表示される列の数を減らすには、[表示列] ボックスを使用します。][ImageWebSQLFilter]  

## すべての Web SQL データを削除する   

1.  [**記憶域のクリア**] ウィンドウを開く。  
1.  [ **WEB SQL** ] チェックボックスがオンになっていることを確認します。  
    
    > ##### 図 6  
    > **WEB SQL**チェックボックス  
    > ![Web SQL チェックボックス][ImageWebSQLCheckbox]  

1.  [**サイトデータのクリア**] を選びます。  
    
    > ##### 図 7  
    > [**サイトデータのクリア**] ボタン  
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
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/storage/websql)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
