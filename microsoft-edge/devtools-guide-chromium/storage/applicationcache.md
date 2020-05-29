---
title: Microsoft Edge DevTools を使ってアプリケーションキャッシュデータを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 6ce3087e9c719efbcf4d9ebceb860edd0ed0c3b6
ms.sourcegitcommit: ad68bfbb355f6cfdaaf6612b77ea3985d4d6a58b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "10612096"
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
> アプリケーションキャッシュ API が[web プラットフォームから削除されて][HTMLStandardOfflineWebApplications]います。  

このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使って[アプリケーションキャッシュ][MDNWebAPIsWindowApplicationCache]のリソースを検査する方法について説明します。  

## アプリケーションキャッシュデータの表示   

1.  [**ソース**] タブを選択して、[**ソース**] パネルを開きます。  通常、**マニフェスト**ウィンドウは既定で開かれます。  
    
    > ##### 図 1  
    > マニフェストウィンドウ  
    > ![マニフェストウィンドウ][ImageManifestPane]  

1.  [**アプリケーションキャッシュ**] セクションを展開して、リソースを表示するキャッシュをクリックします。  
    
    > ##### 図 2  
    > [アプリケーションキャッシュ] ウィンドウ  
    > ![[アプリケーションキャッシュ] ウィンドウ][ImageApplicationCachePane]  

表の各行は、キャッシュされたリソースを表します。  

[**種類**] 列は[リソースのカテゴリ][MDNHTMLResourcesInAnApplicationCache]を表します。  

| カテゴリ | 詳細 |  
|:--- |:--- |  
| `Explicit` | このリソースはマニフェストに明示的に含まれていました。 |  
| `Fallback` | URL は、別のリソースのフォールバックです。  その他のリソースの URL は、DevTools には記載されていません。 |  
| `Master` | リソースの属性によっ `manifest` て、このキャッシュがリソースの親であることが示されました。 |  
| `Network` | このリソースがネットワークから取得する必要があることを指定するマニフェスト。 |  

表の下部には、ネットワーク接続とアプリケーションキャッシュの状態を示す状態アイコンがあります。  アプリケーションキャッシュには、次のような状態があります。  

| 状態 | 詳細 |  
|:--- |:--- |  
| `CHECKING` | マニフェストが取得され、更新プログラムがチェックされます。 |  
| `DOWNLOADING` | キャッシュにリソースが追加されています。 |  
| `IDLE` | キャッシュには新しい変更はありません。 |  
| `OBSOLETE` | キャッシュを削除しています。 |  
| `UPDATEREADY` |  キャッシュの新しいバージョンが使用可能になります。 |  

<!--   -->  



<!-- image links -->  

[ImageManifestPane]: /microsoft-edge/devtools-guide-chromium/media/storage-application-manifest.msft.png "図 1: [マニフェスト] ウィンドウ"  
[ImageApplicationCachePane]: /microsoft-edge/devtools-guide-chromium/media/storage-cache-pane-cache-storage-resources.msft.png "図 2: アプリケーションキャッシュのウィンドウ"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  

[HTMLStandardOfflineWebApplications]: https://html.spec.whatwg.org/multipage/offline.html#offline "オフライン Web アプリケーション-HTML 標準"  

[MDNHTMLResourcesInAnApplicationCache]: https://developer.mozilla.org/docs/Web/HTML/Using_the_application_cache#Resources_in_an_application_cache "アプリケーションキャッシュのリソース |MDN"  
[MDNWebAPIsWindowApplicationCache]: https://developer.mozilla.org/docs/Web/API/Window/applicationCache "Window. applicationCache-Web Api |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
