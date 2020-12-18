---
description: Microsoft Edge DevTools の [アプリケーション] パネルからキャッシュ データを表示する方法について説明します。
title: Microsoft Edge DevTools を使用してキャッシュ データを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 770001beb9b7eebd4dae76355a1f3e41a8021ecb
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230804"
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

# Microsoft Edge DevTools を使用してキャッシュ データを表示する  

このガイドでは [、Microsoft Edge DevTools を使用して][MicrosoftEdgeDevTools] キャッシュ データを検査する方法 [について説明][MDNCache] します。  

HTTP キャッシュ データを検査 [しようとしている][MDNHTTPCaching] 場合、これは必要なガイドではありません。  ネットワーク ログの [ **サイズ** ] 列の情報を **探します**。  [ネットワーク アクティビティ [のログ] に移動します][DevtoolsNetworkLogActivity]。  

## キャッシュ データを表示する  

1.  [アプリケーション **] タブを** 選択して、[アプリケーション] パネル **を開** きます。  通常 **、マニフェスト** ウィンドウは既定で開きます。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="マニフェスト ウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       マニフェスト**ウィンドウ**  
    :::image-end:::  
    
1.  [キャッシュ ストレージ **] セクションを展開** して、使用可能なキャッシュを表示します。  
    
    :::image type="complex" source="../media/storage-application-cache-storage.msft.png" alt-text="使用可能なキャッシュ" lightbox="../media/storage-application-cache-storage.msft.png":::
       使用可能なキャッシュ  
    :::image-end:::  
    
1.  キャッシュを選択してコンテンツを表示します。  
    
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
    
## リソースを更新する  

1.  [キャッシュのデータを表示します](#view-cache-data)。  
1.  更新するリソースを選択します。  DevTools によって強調表示され、選択された状態が示されます。  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-refresh.msft.png" alt-text="更新するリソースを選択する" lightbox="../media/storage-application-cache-storage-domain-refresh.msft.png":::
       更新するリソースを選択する  
    :::image-end:::  
    
1.  Choose **Refresh** \( ![ Refresh ][ImageRefreshIcon] \).  
    
## リソースをフィルター処理する  

1.  [キャッシュのデータを表示します](#view-cache-data)。  
1.  [パス **でフィルター]** テキスト ボックスを使用して、指定したパスと一致しないリソースをフィルター処理します。  
    
    :::image type="complex" source="../media/storage-application-cache-storage-filter.msft.png" alt-text="指定したパスと一致しないリソースをフィルター処理する" lightbox="../media/storage-application-cache-storage-filter.msft.png":::
       指定したパスと一致しないリソースをフィルター処理する  
    :::image-end:::  
    
## リソースの削除  

1.  [キャッシュのデータを表示します](#view-cache-data)。  
1.  削除するリソースを選択します。  DevTools によって強調表示され、選択された状態が示されます。  
    
    :::image type="complex" source="../media/storage-application-cache-storage-delete-selected.msft.png" alt-text="削除するリソースを選択する" lightbox="../media/storage-application-cache-storage-delete-selected.msft.png":::
       削除するリソースを選択する  
    :::image-end:::  
    
1.  Choose **Delete Selected** \( ![ Delete Selected ][ImageDeleteIcon] \).  
    
## すべてのキャッシュ データを削除する  

1.  アプリケーションクリア**ストレージ**  >  **を開きます**。  
1.  [キャッシュ ストレージ] **チェック ボックスが有効** になっていることを確認します。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-cache-storage-checkbox.msft.png" alt-text="[キャッシュ ストレージ] チェック ボックス" lightbox="../media/storage-application-clear-storage-cache-storage-checkbox.msft.png":::
       [ **キャッシュ ストレージ]** チェック ボックス  
    :::image-end:::  
    
1.  [サイト **データのクリア] を選択します**。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-cache-storage-checkbox-clear-site-data-button.msft.png" alt-text="[サイト データのクリア] ボタン" lightbox="../media/storage-application-clear-storage-cache-storage-checkbox-clear-site-data-button.msft.png":::
       [ **サイト データのクリア]** ボタン  
    :::image-end:::  
    
## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageDeleteIcon]: ../media/delete-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft Docs"  
[DevtoolsNetworkLogActivity]: ../network/index.md#log-network-activity  "ネットワーク アクティビティをログに記録する |Microsoft Docs"  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "Cache |MDN"  
[MDNHTTPCaching]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP キャッシュ | MDN"  

> [!NOTE]
> このページの一部は、 [Google によって][GoogleSitePolicies] 作成および共有され、 [クリエイティブ コモンズ 4.0 インターナショナル ライセンス][CCA4IL]で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/cache) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
