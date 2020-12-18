---
description: セキュリティ パネルを使用して、ページが HTTPS で完全に保護されている必要があります。
title: Microsoft Edge DevTools のセキュリティの問題を理解する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 5bef22eae8deacc81e31cf6d1c7791e016541346
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230615"
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

# Microsoft Edge DevTools のセキュリティの問題を理解する  

  

<!--Use the **Security** Panel in [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to make sure HTTPS is properly implemented on a page.  Navigate to **Why HTTPS Matters** to learn why every website should be protected with HTTPS, even sites that do not handle sensitive user data.  -->  

<!--todo: add section when why-https is available -->  

## セキュリティ パネルを開く  

セキュリティ **パネル** は、ページのセキュリティを検査する DevTools の主要な場所です。  

1.  [DevTools を開きます][DevToolsOpen]。  
1.  [セキュリティ **] タブを** 選択して、[セキュリティ] パネル **を開** きます。  
    
    :::image type="complex" source="../media/security-security-overview-secure.msft.png" alt-text="[セキュリティ] パネル" lightbox="../media/security-security-overview-secure.msft.png":::
       [ **セキュリティ]** パネル  
    :::image-end:::  
    
## 一般的な問題  

### セキュリティで保護されていないメインの原点  

ページのメインの作成元がセキュリティで保護されていない場合****、セキュリティの概要では、この**ページはセキュリティで保護されていないと表示されます**。  

:::image type="complex" source="../media/security-security-overview-non-secure.msft.png" alt-text="セキュリティで保護されていないページ" lightbox="../media/security-security-overview-non-secure.msft.png":::
   セキュリティで保護されていないページ  
:::image-end:::  

この問題は、アクセスした URL が HTTP で要求された場合に発生します。  セキュリティを確保するには、HTTPS 経由で要求する必要があります。  たとえば、アドレス バーの URL を確認すると、次のようになります `http://example.com` 。  URL をセキュリティで保護するには、次の必要があります `https://example.com` 。  

サーバーで HTTPS を既にセットアップしている場合、この問題を解決するために必要なのは、すべての HTTP 要求を HTTPS にリダイレクトするようにサーバーを構成することです。  

サーバーに HTTPS を設定していない場合は [、Let's Encrypt][LetsEncrypt] を使用すると、無料で比較的簡単にプロセスを開始できます。  または、CDN でのサイトのホストを検討する場合もあります。  ほとんどの主要な CDN は、既定で HTTPS 上のサイトをホストします。  

> [!TIP]
> Webhint [で HTTPS][WebhintUseHttps] ヒント [を使用すると][Webhint] 、すべての HTTP 要求が HTTPS に送信されるプロセスを自動化できる場合があります。  

### 混在コンテンツ  

**コンテンツが** 混在しているということは、ページのメインの作成元は安全ですが、ページはセキュリティ保護されていない元の元のリソースを要求しました。  混在コンテンツ ページは部分的にしか保護されません。これは、HTTP コンテンツはスニファーからアクセス可能であり、man-in-the-middle 攻撃に対して脆弱だからです。  

:::image type="complex" source="../media/security-security-overview-mixed-secure.msft.png" alt-text="混在コンテンツ" lightbox="../media/security-security-overview-mixed-secure.msft.png":::
   混在コンテンツ  
:::image-end:::  

前の図で、[ネットワーク] パネルで **[View 1 request]** を選択してネットワーク パネルを開き、セキュリティで保護されていないリソースのみをネットワーク ログに表示するフィルター**** `mixed-content:displayed` を適用します。 ****  

:::image type="complex" source="../media/security-network-filter.msft.png" alt-text="ネットワーク ログ内の混在リソース" lightbox="../media/security-network-filter.msft.png":::
   ネットワーク ログ内の混在 **リソース**  
:::image-end:::  

## 詳細の表示  

### メインの生成元の証明書を表示する  

[セキュリティ **の概要] で**、[証明書の **表示] を** 選択して、証明書をメインの発行元にすばやく検査します。  

:::image type="complex" source="../media/security-security-overview-secure-view-certificate.msft.png" alt-text="メインの生成元証明書" lightbox="../media/security-security-overview-secure-view-certificate.msft.png":::
   メインの生成元証明書  
:::image-end:::  

### 原点の詳細を表示する  

左側のナビゲーションのエントリの 1 つを選択して、原点の詳細を表示します。  詳細ページから、接続と証明書の情報を表示できます。  証明書の透過性情報は、利用可能な場合にも表示されます。  

:::image type="complex" source="../media/security-security-overview-mixed-secure-main-origin.msft.png" alt-text="メインの原点の詳細" lightbox="../media/security-security-overview-mixed-secure-main-origin.msft.png":::
   メインの原点の詳細  
:::image-end:::  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft Docs"  
[DevToolsOpen]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  

[LetsEncrypt]: https://letsencrypt.org "暗号化 - 無料の SSL/TLS 証明書"  

[Webhint]: https://webhint.io "webhint"  
[WebhintUseHttps]: https://webhint.io/docs/user-guide/hints/hint-https-only "HTTPS を使用する |webhint ドキュメント"  

<!--[mixed]: /web/fundamentals/security/prevent-mixed-content/what-is-mixed-content ""  -->

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/security/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
