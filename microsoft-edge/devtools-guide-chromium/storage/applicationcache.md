---
description: Microsoft Edge DevTools のアプリケーションパネルからアプリケーションキャッシュデータを表示する方法について説明します。
title: Microsoft Edge DevTools を使ってアプリケーションキャッシュデータを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: ed742f24900786c3c5b31ec2a026ddbf9d16ccb6
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993325"
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

# Microsoft Edge DevTools を使ってアプリケーションキャッシュデータを表示する  

> [!WARNING]
> アプリケーションキャッシュ API が [web プラットフォームから削除されて][HTMLStandardOfflineWebApplications]います。  

このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使って [アプリケーションキャッシュ][MDNWebAPIsWindowApplicationCache] のリソースを検査する方法について説明します。  

## アプリケーションキャッシュデータの表示  

1.  [ **ソース** ] タブを選択して、[ **ソース** ] パネルを開きます。  通常、 **マニフェスト** ウィンドウは既定で開かれます。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       **マニフェスト**ウィンドウ  
    :::image-end:::  

1.  [ **アプリケーションキャッシュ** ] セクションを展開し、リソースを表示するキャッシュを選択します。  
    
    :::image type="complex" source="../media/storage-cache-pane-cache-storage-resources.msft.png" alt-text="[アプリケーションキャッシュ] ウィンドウ" lightbox="../media/storage-cache-pane-cache-storage-resources.msft.png":::
       [ **アプリケーションキャッシュ** ] ウィンドウ  
    :::image-end:::  

表の各行は、キャッシュされたリソースを表します。  

[ **種類** ] 列は [リソースのカテゴリ][MDNHTMLResourcesInAnApplicationCache]を表します。  

| カテゴリ | 詳細 |  
|:--- |:--- |  
| `Explicit` | このリソースはマニフェストに明示的に含まれていました。 |  
| `Fallback` | URL は、別のリソースのフォールバックです。  その他のリソースの URL は、DevTools には記載されていません。 |  
| `Master` | `manifest`リソースの属性は、キャッシュがリソースの親であることを示します。 |  
| `Network` | リソースがネットワークから取得される必要があることを示すマニフェスト。 |  

<!--todo:  replace "Master" phrasing if possible.  -->  

表の下部には、ネットワーク接続と **アプリケーションキャッシュ**の状態を示す状態アイコンがあります。  **アプリケーションキャッシュ**には、次のような状態があります。  

| 状態 | 詳細 |  
|:--- |:--- |  
| `CHECKING` | マニフェストが取得され、更新プログラムがチェックされます。 |  
| `DOWNLOADING` | キャッシュにリソースが追加されています。 |  
| `IDLE` | キャッシュには新しい変更はありません。 |  
| `OBSOLETE` | キャッシュを削除しています。 |  
| `UPDATEREADY` |  キャッシュの新しいバージョンが使用可能になります。 |  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[HTMLStandardOfflineWebApplications]: https://html.spec.whatwg.org/multipage/offline.html#offline "オフライン Web アプリケーション-HTML 標準"  

[MDNHTMLResourcesInAnApplicationCache]: https://developer.mozilla.org/docs/Web/HTML/Using_the_application_cache#Resources_in_an_application_cache "アプリケーションキャッシュのリソース |MDN"  
[MDNWebAPIsWindowApplicationCache]: https://developer.mozilla.org/docs/Web/API/Window/applicationCache "Window. applicationCache-Web Api |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
