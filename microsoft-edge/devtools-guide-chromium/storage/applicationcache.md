---
description: DevTools の [アプリケーション] パネルからアプリケーション キャッシュ データMicrosoft Edgeする方法。
title: DevTools を使用してアプリケーション キャッシュ データMicrosoft Edge表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 71e71555940d74f2071178be2e6daf0ec2f49dfd
ms.sourcegitcommit: d0a6959c5338cf1927093b4a9ed29a0bc0390b43
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "11615422"
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
# <a name="view-application-cache-data-with-microsoft-edge-devtools"></a>DevTools を使用してアプリケーション キャッシュ データMicrosoft Edge表示する  

> [!WARNING]
> アプリケーション キャッシュは非推奨であり、使用を避ける必要があります。  アプリケーション キャッシュ API が Web プラットフォームから削除されています。  詳細については [、「Preparing for AppCache の削除」に移動します][WebDevAppcacheRemoval]。

このガイドでは、アプリケーション キャッシュ リソースを調[Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使用[する方法を示][MDNWebAPIsWindowApplicationCache]します。  

## <a name="view-application-cache-data"></a>アプリケーション キャッシュ データの表示  

1.  DevTools の上部で、[アプリケーション] ツール **を選択** します。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="[マニフェスト] ウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       [ **マニフェスト]** ウィンドウ  
    :::image-end:::  

1.  [アプリケーション キャッシュ **] セクションを展開** し、キャッシュを選択してリソースを表示します。  
    
    :::image type="complex" source="../media/storage-cache-pane-cache-storage-resources.msft.png" alt-text="[アプリケーション キャッシュ] ウィンドウ" lightbox="../media/storage-cache-pane-cache-storage-resources.msft.png":::
       [ **アプリケーション キャッシュ]** ウィンドウ  
    :::image-end:::  

テーブルの各行は、キャッシュされたリソースを表します。  

[ **種類]** 列は、リソース [のカテゴリを表します][MDNHTMLResourcesInAnApplicationCache]。  

| カテゴリ | 詳細 |  
|:--- |:--- |  
| `Explicit` | このリソースはマニフェストに明示的に一覧表示されました。 |  
| `Fallback` | URL は別のリソースのフォールバックです。  他のリソースの URL は DevTools に表示されません。 |  
| `Master` | リソース `manifest` の属性は、キャッシュがリソースの親を示します。 |  
| `Network` | リソースがネットワークから取得する必要があるというマニフェストが指定されています。 |  

<!--todo:  replace "Master" phrasing if possible.  -->  

表の下部には、ネットワーク接続とアプリケーション キャッシュの状態を示す状態アイコン **があります**。  アプリケーション **キャッシュの状態** は次のとおりです。  

| 状態 | 詳細 |  
|:--- |:--- |  
| `CHECKING` | マニフェストがフェッチされ、更新プログラムがチェックされています。 |  
| `DOWNLOADING` | リソースがキャッシュに追加されています。 |  
| `IDLE` | キャッシュに新しい変更はありません。 |  
| `OBSOLETE` | キャッシュが削除中です。 |  
| `UPDATEREADY` |  新しいバージョンのキャッシュを使用できます。 |  

<!-- links -->  
[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
<!-- external links: -->
[MDNHTMLResourcesInAnApplicationCache]: https://developer.mozilla.org/docs/Web/HTML/Using_the_application_cache#Resources_in_an_application_cache "アプリケーション キャッシュ 内のリソース|MDN"  
[MDNWebAPIsWindowApplicationCache]: https://developer.mozilla.org/docs/Web/API/Window/applicationCache "Window.applicationCache - Web API |MDN"  

[WebDevAppcacheRemoval]: https://web.dev/appcache-removal "AppCache の削除の準備|web.dev"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
