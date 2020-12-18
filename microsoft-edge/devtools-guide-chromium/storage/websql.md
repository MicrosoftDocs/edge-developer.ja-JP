---
description: Microsoft Edge DevTools SQLアプリケーション パネルから Web アプリケーション データを表示する方法について説明します。
title: Microsoft Edge DevTools SQL Web アプリケーション データを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 802f21cb4cadfa3ee08ddd8feeea8b8132551740
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231175"
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

# Microsoft Edge DevTools SQL Web アプリ データを表示する  

> [!WARNING]
> Web SQL仕様 [は維持されません][W3CWebSQLStatus]。  

このガイドでは [、Microsoft Edge DevTools を使用して][MicrosoftEdgeDevTools] Web アプリケーションデータを検査SQLします。  

## Web アプリケーション データSQLする  

1.  [ソース **] タブを** 選択して、ソース **ツールを開** きます。  通常 **、マニフェスト** ウィンドウは既定で開きます。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="マニフェスト ウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       マニフェスト**ウィンドウ**  
    :::image-end:::  
    
1.  [Web データベース **] セクションSQL、** データベースとテーブルを表示します。  次の図では、 **以下の html5meetup は** データベースであり、 **ルームは** テーブルです。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql.msft.png" alt-text="[Web SQL] ウィンドウ" lightbox="../media/storage-application-storage-web-sql.msft.png":::
       [Web **SQL]** ウィンドウ  
    :::image-end:::  
    
1.  テーブルを選択して、そのテーブルのデータを表示します。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png" alt-text="Web アプリケーション テーブルのデータSQLする" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-1.msft.png":::
       Web アプリケーション テーブルのデータSQLする  
    :::image-end:::  
    
## Web アプリケーション データSQL編集  

前の例のように、Web SQLテーブルを表示SQL Web データを編集できない。  ただし、テーブルを編集または削除するステートメントを Web SQLコンソールから実行できます。  「Web [クエリの実行SQL参照してください](#run-web-sql-queries)。  

## Web クエリをSQLする  

1.  データベースを選択して、そのデータベースのコンソールを開きます。  
1.  Web アプリケーション ステートメントをSQLし、実行 `Enter` を選択します。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png" alt-text="Web SQLコンソールを使用してテーブルから行を削除する" lightbox="../media/storage-application-storage-web-sql-html5meetup-commands.msft.png":::
       Web SQL コンソールを使用してテーブルから行を削除する  
    :::image-end:::  
    
## Web テーブルをSQLする  

DevTools では、テーブルはリアルタイムで更新されません。  テーブル内のデータを更新するには、次のアクションを実行します。  

1.  [Web テーブル内のデータSQLします](#view-web-sql-data)。  
1.  Choose **Refresh** \( ![ Refresh ][ImageRefreshIcon] \).  
    
## Web テーブル内の列をSQLする  

1.  [Web テーブル内のデータSQLします](#view-web-sql-data)。  
1.  [表示 **可能な列]** テキスト ボックスを使用して、表示する列を指定します。  列名を CSV リストとして指定します。  
    
    :::image type="complex" source="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png" alt-text="表示される列の数を減らすには、[表示される列] テキスト ボックスを使用します。" lightbox="../media/storage-application-storage-web-sql-html5meetup-rooms-2.msft.png":::
       表示される **列の数** を減らすには、[表示される列] テキスト ボックスを使用します。  
    :::image-end:::  
    
## すべての Web アプリケーション データSQL削除する  

1.  [ストレージの **クリア] ウィンドウを開** きます。  
1.  [Web アプリケーション] **チェック SQL** オンになっていることを確認します。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-web-sql.msft.png" alt-text="[Web SQL] チェック ボックス" lightbox="../media/storage-application-clear-storage-web-sql.msft.png":::
       **[Web SQL]** チェック ボックス  
    :::image-end:::  
    
1.  [サイト **データのクリア] を選択します**。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-clear-site-data-button.msft.png" alt-text="[サイト データのクリア] ボタン" lightbox="../media/storage-application-clear-storage-clear-site-data-button.msft.png":::
       [ **サイト データのクリア]** ボタン  
    :::image-end:::  
    
## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageRefreshIcon]: ../media/refresh-icon.msft.png  

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
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
