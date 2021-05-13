---
description: DevTools の [アプリケーション] SQLから Web データを表示するMicrosoft Edge方法。
title: DevTools で web SQLデータをMicrosoft Edgeする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: bc25f7422be19bec99bde1cd7764f08aad8e6668
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564701"
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
# <a name="view-web-sql-data-with-microsoft-edge-devtools"></a>DevTools で web SQLデータをMicrosoft Edgeする  

> [!WARNING]
> Web SQL仕様[は維持されません][W3CWebSQLStatus]。  

このガイドでは、DevTools を使用して[Web Microsoft Edgeデータ][MicrosoftEdgeDevTools]を調SQLします。  

## <a name="view-web-sql-data"></a>Web SQLデータの表示  

1.  [ソース **] ツールを** 選択して [ソース] **ツールを開** きます。  通常 **、マニフェスト ウィンドウ** は既定で開きます。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="[マニフェスト] ウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       [ **マニフェスト]** ウィンドウ  
    :::image-end:::  
    
1.  [Web ファイル **] セクションSQL**データベースとテーブルを表示します。  次の図では、 **以下の html5meetup は** データベースであり、 **会議室は** 表です。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql.msft.png" alt-text="[Web SQL] ウィンドウ" lightbox="../media/storage-application-storage-web-sql.msft.png":::
       [Web **SQL]** ウィンドウ  
    :::image-end:::  
    
1.  テーブルを選択して、そのテーブルのデータを表示します。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png" alt-text="Web テーブルのデータをSQLする" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png":::
       Web テーブルのデータをSQLする  
    :::image-end:::  
    
## <a name="edit-web-sql-data"></a>Web データのSQL編集  

前の例のように、Web SQLテーブルを表示SQL Web データを編集できない。  ただし、テーブルを編集または削除する web SQLコンソールからステートメントを実行できます。  [Web クエリの[実行] SQL移動します](#run-web-sql-queries)。  

## <a name="run-web-sql-queries"></a>Web クエリのSQL実行  

1.  データベースを選択して、そのデータベースのコンソールを開きます。  
1.  [Web ファイル] SQLを入力し、実行 `Enter` を選択します。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png" alt-text="Web コンソールをSQLテーブルから行を削除する" lightbox="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png":::
       Web コンソールをSQLテーブルから行を削除する  
    :::image-end:::  
    
## <a name="refresh-a-web-sql-table"></a>Web テーブルをSQLする  

DevTools はリアルタイムでテーブルを更新しない。  テーブル内のデータを更新するには、次のアクションを実行します。  

1.  [Web テーブルでデータを表示SQLします](#view-web-sql-data)。  
1.  [ **更新** \( ![ Refresh ](../media/refresh-icon.msft.png) \] を選択します)。  
    
## <a name="filter-out-columns-in-a-web-sql-table"></a>Web テーブル内の列をフィルター SQLする  

1.  [Web テーブルでデータを表示SQLします](#view-web-sql-data)。  
1.  表示する **列を** 指定するには、[表示列] テキスト ボックスを使用します。  列名を CSV リストとして指定します。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png" alt-text="[表示列] テキスト ボックスを使用して、表示される列の数を減らす" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png":::
       [表示 **列] テキスト** ボックスを使用して、表示される列の数を減らす  
    :::image-end:::  
    
## <a name="delete-all-web-sql-data"></a>すべての Web データをSQLする  

1.  [クリア]**ウィンドウStorage**開きます。  
1.  [Web] チェック**ボックスSQL**オンになっていることを確認します。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-web-sql.msft.png" alt-text="[Web SQL] チェック ボックス" lightbox="../media/storage-application-clear-storage-web-sql.msft.png":::
       **[Web SQL]** チェック ボックス  
    :::image-end:::  
    
1.  [サイト **データのクリア] を選択します**。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-clear-site-data-button.msft.png" alt-text="[サイト データのクリア] ボタン" lightbox="../media/storage-application-clear-storage-clear-site-data-button.msft.png":::
       [ **サイト データのクリア]** ボタン  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[W3CWebSQLStatus]: https://w3.org/TR/webdatabase/#status-of-this-document "Web SQL データベース |W3C"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/websql) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
