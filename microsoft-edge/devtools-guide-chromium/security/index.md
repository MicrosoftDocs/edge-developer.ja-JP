---
description: ページが HTTPS で完全に保護されている場合は、セキュリティ パネルを使用します。
title: DevTools のセキュリティMicrosoft Edge理解する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 71138ad33afb9eb56055fa522eb35edb71974c89
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397777"
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

# <a name="understand-security-issues-with-microsoft-edge-devtools"></a>DevTools のセキュリティMicrosoft Edge理解する  

  

<!--Use the **Security** Panel in [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to make sure HTTPS is properly implemented on a page.  Navigate to **Why HTTPS Matters** to learn why every website should be protected with HTTPS, even sites that do not handle sensitive user data.  -->  

<!--todo: add section when why-https is available -->  

## <a name="open-the-security-panel"></a>[セキュリティ] パネルを開く  

セキュリティ **パネル** は、ページのセキュリティを検査する DevTools の主要な場所です。  

1.  [DevTools を開きます][DevToolsOpen]。  
1.  [セキュリティ **] タブを** 選択して、[セキュリティ] ツール **を開** きます。  
    
    :::image type="complex" source="../media/security-security-overview-secure.msft.png" alt-text="[セキュリティ] パネル" lightbox="../media/security-security-overview-secure.msft.png":::
       [ **セキュリティ]** パネル  
    :::image-end:::  
    
## <a name="common-problems"></a>一般的な問題  

### <a name="non-secure-main-origins"></a>セキュリティで保護されていない主な発生元  

ページの主な作成元がセキュリティで保護されていない場合、セキュリティ **の概要には** 、この **ページはセキュリティで保護されていないと表示されます**。  

:::image type="complex" source="../media/security-security-overview-non-secure.msft.png" alt-text="セキュリティ保護されていないページ" lightbox="../media/security-security-overview-non-secure.msft.png":::
   セキュリティ保護されていないページ  
:::image-end:::  

この問題は、アクセスした URL が HTTP を使用して要求された場合に発生します。  セキュリティで保護するには、HTTPS 経由で要求する必要があります。  たとえば、アドレス バーの URL を確認すると、おそらくに似ています `http://example.com` 。  URL をセキュリティで保護するには、 である必要があります `https://example.com` 。  

サーバーで HTTPS を既にセットアップしている場合は、この問題を解決するために必要なのは、すべての HTTP 要求を HTTPS にリダイレクトするようにサーバーを構成することです。  

サーバーで HTTPS を設定していない場合は [、Let's Encrypt][LetsEncrypt] を使用すると、プロセスを開始するための無料で比較的簡単な方法が提供されます。  または、サイトをサイトにホストする方法を検討CDN。  現在、ほとんどの主要な CDN は HTTPS 上のサイトを既定でホストしています。  

> [!TIP]
> [Webhint で HTTPS][WebhintUseHttps]ヒント[を使用すると][Webhint]、すべての HTTP 要求が HTTPS に送信されるプロセスを自動化できます。  

### <a name="mixed-content"></a>混在コンテンツ  

**混在コンテンツ** とは、ページの主な作成元がセキュリティで保護されているが、ページがセキュリティで保護されていないオリジンからリソースを要求したという意味です。  混在コンテンツ ページは部分的にしか保護されません。HTTP コンテンツはスニッフィングにアクセス可能で、中間者攻撃に対して脆弱です。  

:::image type="complex" source="../media/security-security-overview-mixed-secure.msft.png" alt-text="混在コンテンツ" lightbox="../media/security-security-overview-mixed-secure.msft.png":::
   混在コンテンツ  
:::image-end:::  

前の図で、[ネットワーク] パネルで **[1**要求**** の表示] を選択してネットワーク ツールを開き、フィルターを適用して、ネットワーク ログにセキュリティ保護されていないリソースのみを `mixed-content:displayed` **** 表示します。  

:::image type="complex" source="../media/security-network-filter.msft.png" alt-text="ネットワーク ログ内の混在リソース" lightbox="../media/security-network-filter.msft.png":::
   ネットワーク ログ内の **混在リソース**  
:::image-end:::  

## <a name="view-details"></a>詳細の表示  

### <a name="view-main-origin-certificate"></a>メインオリジン証明書の表示  

[セキュリティの **概要] で**、[証明書の **表示] を** 選択して、メインの発行元の証明書をすばやく検査します。  

:::image type="complex" source="../media/security-security-overview-secure-view-certificate.msft.png" alt-text="主な発行元証明書" lightbox="../media/security-security-overview-secure-view-certificate.msft.png":::
   主な発行元証明書  
:::image-end:::  

### <a name="view-origin-details"></a>原点の詳細を表示する  

左側のナビゲーションでエントリの 1 つを選択して、原点の詳細を表示します。  詳細ページから、接続と証明書の情報を表示できます。  証明書の透明性情報は、利用可能な場合にも表示されます。  

:::image type="complex" source="../media/security-security-overview-mixed-secure-main-origin.msft.png" alt-text="主な発生元の詳細" lightbox="../media/security-security-overview-mixed-secure-main-origin.msft.png":::
   主な発生元の詳細  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft Docs"  
[DevToolsOpen]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  

[LetsEncrypt]: https://letsencrypt.org "Let's Encrypt - 無料の SSL/TLS 証明書"  

[Webhint]: https://webhint.io "webhint"  
[WebhintUseHttps]: https://webhint.io/docs/user-guide/hints/hint-https-only "HTTPS を使用|webhint のドキュメント"  

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
