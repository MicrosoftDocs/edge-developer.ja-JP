---
description: Microsoft Edge DevTools の [アプリケーション] パネルからアプリケーション キャッシュ データを表示する方法。
title: Microsoft Edge DevTools を使用してアプリケーション キャッシュ データを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: cbe6623aa3132db4d01cd6b440702eb157525eed
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519143"
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

# <a name="view-application-cache-data-with-microsoft-edge-devtools"></a>Microsoft Edge DevTools を使用してアプリケーション キャッシュ データを表示する  

> [!WARNING]
> アプリケーション キャッシュ API が [Web プラットフォームから削除されています][HTMLStandardOfflineWebApplications]。  

このガイドでは [、Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使用してアプリケーション キャッシュ リソース [を検査する方法を示][MDNWebAPIsWindowApplicationCache] します。  

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

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[HTMLStandardOfflineWebApplications]: https://html.spec.whatwg.org/multipage/offline.html#offline "オフライン Web アプリケーション - HTML Standard"  

[MDNHTMLResourcesInAnApplicationCache]: https://developer.mozilla.org/docs/Web/HTML/Using_the_application_cache#Resources_in_an_application_cache "アプリケーション キャッシュ 内のリソース|MDN"  
[MDNWebAPIsWindowApplicationCache]: https://developer.mozilla.org/docs/Web/API/Window/applicationCache "Window.applicationCache - Web API |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/applicationcache) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
