---
title: Microsoft Edge DevTools を使ってキャッシュデータを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 82356777f209b86f88de1ee53b212947d969ff8a
ms.sourcegitcommit: ad68bfbb355f6cfdaaf6612b77ea3985d4d6a58b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "10612075"
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





# Microsoft Edge DevTools を使ってキャッシュデータを表示する   



このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使って[キャッシュ][MDNCache]データを検査する方法について説明します。  

[HTTP キャッシュ][MDNHTTPCaching]データを検査しようとしている場合、これは目的のガイドではありません。  
**ネットワークログ**の**Size**列で情報を探します。  「[ネットワークアクティビティのログ記録][DevtoolsNetworkLogActivity]」を参照してください。  

## キャッシュデータを表示する   

1.  [**アプリケーション**] タブを選択して、[**アプリケーション**] パネルを開きます。  通常、**マニフェスト**ウィンドウは既定で開かれます。  
    
    > ##### 図 1  
    > マニフェストウィンドウ  
    > ![マニフェストウィンドウ][ImageManifestPane]  

1.  [**キャッシュ記憶域**] セクションを展開して、利用可能なキャッシュを表示します。  
    
    > ##### 図 2  
    > 利用可能なキャッシュ  
    > ![利用可能なキャッシュ][ImageCache]  

1.  コンテンツを表示するキャッシュを選択します。  
    
    > ##### 図 3  
    > キャッシュの内容を表示する  
    > ![キャッシュの内容を表示する][ImageCacheView]  

1.  リソースを選択して、表の下のセクションに HTTP ヘッダーを表示します。  
    
    > ##### 図 4  
    > リソースの HTTP ヘッダーの表示  
    > ![リソースの HTTP ヘッダーの表示][ImageViewCacheResource]  

1.  [**プレビュー** ] を選択して、リソースのコンテンツを表示します。  
    
    > ##### 図 5  
    > リソースの内容を表示する  
    > ![リソースの内容を表示する][ImageCacheContent]  

## リソースを更新する   

1.  [キャッシュのデータを表示](#view-cache-data)する。  
1.  更新するリソースを選びます。  DevTools では、選択されていることを示すように強調表示されます。  
    
    > ##### 図 6  
    > リソースの選択  
    > ![リソースの選択][ImageCacheSelected]  

1.  [**更新の更新]** を選び ![ ][ImageRefreshIcon] ます。  

## リソースをフィルター処理する   

1.  [キャッシュのデータを表示](#view-cache-data)する。  
1.  [**パスを指定してフィルター** ] テキストボックスを使用して、指定したパスと一致しないリソースをフィルター処理します。  
    
    > ##### 図 7  
    > 指定したパスと一致しないリソースをフィルター処理する  
    > ![指定したパスと一致しないリソースをフィルター処理する][ImageCacheFilter]  

## リソースの削除   

1.  [キャッシュのデータを表示](#view-cache-data)する。  
1.  削除するリソースを選びます。  DevTools では、選択されていることを示すように強調表示されます。  
    
    > ##### 図 8  
    > リソースの選択  
    > ![リソースの選択][ImageCacheSelected2]  

1.  [選択した削除の**削除**] を選択し ![ ][ImageDeleteIcon] ます。  

## すべてのキャッシュデータを削除する   

1.  **アプリケーション**  >  の**クリアストレージ**を開きます。  
1.  [**キャッシュストレージ**] チェックボックスがオンになっていることを確認します。  
    
    > ##### 図 9  
    > [**キャッシュストレージ**] チェックボックス  
    > ![[キャッシュストレージ] チェックボックス][ImageCacheCheckbox]  

1.  [**サイトデータのクリア**] を選びます。  
    
    > ##### 図 10  
    > [**サイトデータのクリア**] ボタン  
    > ![[サイトデータのクリア] ボタン][ImageCacheClearSite]  

<!--  -->  



<!-- image links -->  

[ImageDeleteIcon]: /microsoft-edge/devtools-guide-chromium/media/delete-icon.msft.png  
[ImageRefreshIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-icon.msft.png  

[ImageManifestPane]: /microsoft-edge/devtools-guide-chromium/media/storage-application-manifest.msft.png "図 1: [マニフェスト] ウィンドウ"  
[ImageCache]: /microsoft-edge/devtools-guide-chromium/media/storage-application-cache-storage.msft.png "図 2: 使用できるキャッシュ"  
[ImageCacheView]: /microsoft-edge/devtools-guide-chromium/media/storage-application-cache-storage-domain-root-headers.msft.png "図 3: キャッシュの内容を表示する"  
[ImageViewCacheResource]: /microsoft-edge/devtools-guide-chromium/media/storage-application-cache-storage-index-headers.msft.png "図 4: リソースの HTTP ヘッダーの表示"  
[ImageCacheContent]: /microsoft-edge/devtools-guide-chromium/media/storage-application-cache-storage-domain-js-preview.msft.png "図 5: リソースの内容を表示する"  
[ImageCacheSelected]: /microsoft-edge/devtools-guide-chromium/media/storage-application-cache-storage-domain-refresh.msft.png "図 6: リソースの選択"  
[ImageCacheFilter]: /microsoft-edge/devtools-guide-chromium/media/storage-application-cache-storage-filter.msft.png "図 7: 指定したパスと一致しないリソースのフィルター処理"  
[ImageCacheSelected2]: /microsoft-edge/devtools-guide-chromium/media/storage-application-cache-storage-delete-selected.msft.png "図 8: リソースの選択"  
[ImageCacheCheckbox]: /microsoft-edge/devtools-guide-chromium/media/storage-application-clear-storage-cache-storage-checkbox.msft.png "図 9: キャッシュ記憶域のチェックボックス"  
[ImageCacheClearSite]: /microsoft-edge/devtools-guide-chromium/media/storage-application-clear-storage-cache-storage-checkbox-clear-site-data-button.msft.png "図 10: [サイトデータのクリア] ボタン"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  
[DevtoolsNetworkLogActivity]: /microsoft-edge/network/index#log-network-activity  "ネットワークアクティビティをログに記録する"  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "キャッシュ |MDN"  
[MDNHTTPCaching]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP キャッシュMDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/storage/cache)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
