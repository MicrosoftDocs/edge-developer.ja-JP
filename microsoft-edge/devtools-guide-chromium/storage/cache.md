---
description: DevTools の [アプリケーション] パネルからキャッシュ データMicrosoft Edgeする方法。
title: DevTools でキャッシュ データMicrosoft Edge表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 1f66419014682a316fa565c5ef2ab704f652637f
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564687"
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
# <a name="view-cache-data-with-microsoft-edge-devtools"></a>DevTools でキャッシュ データMicrosoft Edge表示する  

このガイドでは、DevTools でキャッシュ[データMicrosoft Edgeを][MicrosoftEdgeDevTools]調Microsoft Edge方法[を示][MDNCache]します。  

[HTTP][MDNHTTPCaching]キャッシュ データを検査しようとしている場合、これは必要なガイドではありません。  ネットワーク ログの [ **サイズ** ] 列の情報を **探します**。  [ネットワーク アクティビティ [のログ記録] に移動します][DevtoolsNetworkLogActivity]。  

## <a name="view-cache-data"></a>キャッシュ データの表示  

1.  [アプリケーション] **タブを** 選択して、[アプリケーション] パネル **を開** きます。  通常 **、マニフェスト ウィンドウ** は既定で開きます。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="[マニフェスト] ウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       [ **マニフェスト]** ウィンドウ  
    :::image-end:::  
    
1.  [キャッシュ]**セクションStorage**を展開して、使用可能なキャッシュを表示します。  
    
    :::image type="complex" source="../media/storage-application-cache-storage.msft.png" alt-text="使用可能なキャッシュ" lightbox="../media/storage-application-cache-storage.msft.png":::
       使用可能なキャッシュ  
    :::image-end:::  
    
1.  コンテンツを表示するキャッシュを選択します。  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-root-headers.msft.png" alt-text="キャッシュの内容を表示する" lightbox="../media/storage-application-cache-storage-domain-root-headers.msft.png":::
       キャッシュの内容を表示する  
    :::image-end:::  
    
1.  表の下のセクションで HTTP ヘッダーを表示するリソースを選択します。  
    
    :::image type="complex" source="../media/storage-application-cache-storage-index-headers.msft.png" alt-text="リソースの HTTP ヘッダーを表示する" lightbox="../media/storage-application-cache-storage-index-headers.msft.png":::
       リソースの HTTP ヘッダーを表示する  
    :::image-end:::  
    
1.  [ **プレビュー] を** 選択して、リソースのコンテンツを表示します。  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-js-preview.msft.png" alt-text="リソースのコンテンツを表示する" lightbox="../media/storage-application-cache-storage-domain-js-preview.msft.png":::
       リソースのコンテンツを表示する  
    :::image-end:::  
    
## <a name="refresh-a-resource"></a>リソースの更新  

1.  [キャッシュのデータを表示します](#view-cache-data)。  
1.  更新するリソースを選択します。  DevTools では強調表示され、選択されているかどうかを示します。  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-refresh.msft.png" alt-text="更新するリソースを選択する" lightbox="../media/storage-application-cache-storage-domain-refresh.msft.png":::
       更新するリソースを選択する  
    :::image-end:::  
    
1.  [ **更新** \( ![ Refresh ](../media/refresh-icon.msft.png) \] を選択します)。  
    
## <a name="filter-resources"></a>リソースをフィルター処理する  

1.  [キャッシュのデータを表示します](#view-cache-data)。  
1.  [パス **でフィルター] テキスト** ボックスを使用して、指定したパスに一致しないリソースをフィルター処理します。  
    
    :::image type="complex" source="../media/storage-application-cache-storage-filter.msft.png" alt-text="指定したパスに一致しないリソースをフィルター処理する" lightbox="../media/storage-application-cache-storage-filter.msft.png":::
       指定したパスに一致しないリソースをフィルター処理する  
    :::image-end:::  
    
## <a name="delete-a-resource"></a>リソースの削除  

1.  [キャッシュのデータを表示します](#view-cache-data)。  
1.  削除するリソースを選択します。  DevTools では強調表示され、選択されているかどうかを示します。  
    
    :::image type="complex" source="../media/storage-application-cache-storage-delete-selected.msft.png" alt-text="削除するリソースを選択する" lightbox="../media/storage-application-cache-storage-delete-selected.msft.png":::
       削除するリソースを選択する  
    :::image-end:::  
    
1.  [ **選択済み \(** Delete ![ Selected ](../media/delete-icon.msft.png) \) を削除する] を選択します。  
    
## <a name="delete-all-cache-data"></a>すべてのキャッシュ データを削除する  

1.  [**アプリケーションの**  >  **クリア] Storage を開きます**。  
1.  [キャッシュ の設定]**チェック Storage**が有効になっていることを確認します。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-cache-storage-checkbox.msft.png" alt-text="[キャッシュのStorage] チェック ボックス" lightbox="../media/storage-application-clear-storage-cache-storage-checkbox.msft.png":::
       [**キャッシュのStorage]** チェック ボックス  
    :::image-end:::  
    
1.  [サイト **データのクリア] を選択します**。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-cache-storage-checkbox-clear-site-data-button.msft.png" alt-text="[サイト データのクリア] ボタン" lightbox="../media/storage-application-clear-storage-cache-storage-checkbox-clear-site-data-button.msft.png":::
       [ **サイト データのクリア]** ボタン  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft Docs"  
[DevtoolsNetworkLogActivity]: ../network/index.md#log-network-activity  "ネットワーク アクティビティのログ |Microsoft Docs"  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "キャッシュ |MDN"  
[MDNHTTPCaching]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP キャッシュ | MDN"  

> [!NOTE]
> このページの一部は、 [Google によって][GoogleSitePolicies] 作成および共有され、 [クリエイティブ コモンズ 4.0 インターナショナル ライセンス][CCA4IL]で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/cache) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
