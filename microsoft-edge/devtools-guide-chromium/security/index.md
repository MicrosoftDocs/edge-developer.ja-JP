---
title: Microsoft Edge DevTools のセキュリティに関する問題を理解する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 05112d5270f41ce83daa935b8137c4a773ad25a0
ms.sourcegitcommit: 4c24edbd1c591914cb4109511534851570a614cb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611911"
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





# Microsoft Edge DevTools のセキュリティに関する問題を理解する   

  

<!--Use the **Security** Panel in [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to make sure HTTPS is properly implemented on a page.  See **Why HTTPS Matters** to learn why every website should be protected with HTTPS, even sites that do not handle sensitive user data.  -->  

<!--todo: add section when why-https is available -->  

## セキュリティパネルを開く   

**セキュリティ**パネルは、ページのセキュリティを検査するための devtools の主要な場所です。  

1.  [DevTools を開き][DevToolsOpen]ます。  

1.  [**セキュリティ**] タブをクリックして、[**セキュリティ**] パネルを開きます。  
    
    > ##### 図 1  
    > セキュリティパネル  
    > ![セキュリティパネル][ImageSecurityPanel]  
    
## 一般的な問題   

### セキュリティで保護されていない本文   

ページのメインの起点がセキュリティで保護されていない場合、**このページは**セキュリティで保護されていないことを**示してい**ます。  

> ##### 図 2  
> セキュリティで保護されていないページ  
> ![セキュリティで保護されていないページ][ImageNonSecurePage]  

この問題は、アクセスした URL が HTTP 経由で要求された場合に発生します。  セキュリティを確保するには、HTTPS 経由で要求する必要があります。  たとえば、アドレスバーに表示される URL を見ると、次のように表示されることがあり `http://example.com` ます。  URL がセキュリティで保護されるようにし `https://example.com` ます。  

サーバーに HTTPS を既にセットアップしている場合は、この問題を解決するために必要な操作は、すべての HTTP 要求を HTTPS にリダイレクトするようにサーバーを構成することだけです。  

サーバーで HTTPS をセットアップしていない場合は、[暗号化][LetsEncrypt]を使用して、処理を開始するための無料で比較的簡単な方法を提供します。  または、サイトを CDN でホストすることを検討することもできます。  既定では、ほとんどの主要な CDNs ホストサイトが HTTPS で提供されます。  

> [!TIP]
> [Webhint][Webhint]で[https の使用][WebhintUseHttps]に関するヒントを使用すると、すべての HTTP 要求が HTTPS に転送されることを確認するプロセスを自動化することができます。  

### 混在したコンテンツ   

**混在**しているコンテンツとは、ページのメインの起点がセキュリティで保護されているが、ページは安全ではない元のリソースを要求したことを意味します。  混在したコンテンツページは、HTTP コンテンツがスニファーでアクセス可能であり、man-in-the-middle 攻撃に対して脆弱であるため、部分的に保護されています。  

> ##### 図 3  
> 混在したコンテンツ  
> ![混在したコンテンツ][ImageMixedContent]  

[図 3](#figure-3)では、[**ネットワークパネル] で [1 つの要求を表示**] をクリックして [ネットワーク] パネルを開き、 **Network** `mixed-content:displayed` **ネットワークログ**にセキュリティ以外のリソースしか表示されないようにフィルターを適用します。  

> ##### 図 4  
> ネットワークログの混在したリソース  
> ![ネットワークログの混在したリソース][ImageMixedResourcesNetworkLog]  

## 詳細の表示   

### メインの元の証明書を表示する   

セキュリティの**概要**で、[**証明書の表示**] をクリックして、メインの元の証明書をすばやく検査します。  

> ##### 図 5  
> メインの元の証明書  
> ![メインの元の証明書][ImageCertificate]  

### オリジンの詳細の表示   

左側のナビゲーションでいずれかのエントリをクリックして、元の情報を表示します。  [詳細] ページでは、接続と証明書の情報を表示できます。  証明書の透過性情報は、可能な場合にも表示されます。  

> ##### 図 6  
> 主要な原産国の詳細  
> ![主要な原産国の詳細][ImageOriginDetails]  

 



<!-- image links -->  

[ImageSecurityPanel]: /microsoft-edge/devtools-guide-chromium/media/security-security-overview-secure.msft.png "図 1: セキュリティパネル"  
[ImageNonSecurePage]: /microsoft-edge/devtools-guide-chromium/media/security-security-overview-non-secure.msft.png "図 2: セキュリティで保護されていないページ"  
[ImageMixedContent]: /microsoft-edge/devtools-guide-chromium/media/security-security-overview-mixed-secure.msft.png "図 3: 混在したコンテンツ"  
[ImageMixedResourcesNetworkLog]: /microsoft-edge/devtools-guide-chromium/media/security-network-filter.msft.png "図 4: ネットワークログの混在したリソース"  
[ImageCertificate]: /microsoft-edge/devtools-guide-chromium/media/security-security-overview-secure-view-certificate.msft.png "図 5: メインの元の証明書"  
[ImageOriginDetails]: /microsoft-edge/devtools-guide-chromium/media/security-security-overview-mixed-secure-main-origin.msft.png "図 6: 主要な送信元の詳細"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  
[DevToolsOpen]: /microsoft-edge/devtools-guide-chromium/open "Microsoft Edge DevTools を開く"  


[LetsEncrypt]: https://letsencrypt.org "暗号化されていない SSL/TLS 証明書を使用する"  

[Webhint]: https://webhint.io "web ヒント"  
[WebhintUseHttps]: https://webhint.io/docs/user-guide/hints/hint-https-only "HTTPS を使用 |webhint に関するドキュメント"  

<!--[mixed]: /web/fundamentals/security/prevent-mixed-content/what-is-mixed-content ""  -->

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/security/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
