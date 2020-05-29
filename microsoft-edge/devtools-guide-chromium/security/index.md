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





# <span data-ttu-id="b3ad1-103">Microsoft Edge DevTools のセキュリティに関する問題を理解する</span><span class="sxs-lookup"><span data-stu-id="b3ad1-103">Understand Security Issues With Microsoft Edge DevTools</span></span>   

  

<!--Use the **Security** Panel in [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to make sure HTTPS is properly implemented on a page.  See **Why HTTPS Matters** to learn why every website should be protected with HTTPS, even sites that do not handle sensitive user data.  -->  

<!--todo: add section when why-https is available -->  

## <span data-ttu-id="b3ad1-104">セキュリティパネルを開く</span><span class="sxs-lookup"><span data-stu-id="b3ad1-104">Open the Security panel</span></span>   

<span data-ttu-id="b3ad1-105">**セキュリティ**パネルは、ページのセキュリティを検査するための devtools の主要な場所です。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-105">The **Security** panel is the main place in DevTools for inspecting the security of a page.</span></span>  

1.  <span data-ttu-id="b3ad1-106">[DevTools を開き][DevToolsOpen]ます。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-106">[Open DevTools][DevToolsOpen].</span></span>  

1.  <span data-ttu-id="b3ad1-107">[**セキュリティ**] タブをクリックして、[**セキュリティ**] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-107">Click the **Security** tab to open the **Security** panel.</span></span>  
    
    > ##### <span data-ttu-id="b3ad1-108">図 1</span><span class="sxs-lookup"><span data-stu-id="b3ad1-108">Figure 1</span></span>  
    > <span data-ttu-id="b3ad1-109">セキュリティパネル</span><span class="sxs-lookup"><span data-stu-id="b3ad1-109">The Security panel</span></span>  
    > ![セキュリティパネル][ImageSecurityPanel]  
    
## <span data-ttu-id="b3ad1-111">一般的な問題</span><span class="sxs-lookup"><span data-stu-id="b3ad1-111">Common problems</span></span>   

### <span data-ttu-id="b3ad1-112">セキュリティで保護されていない本文</span><span class="sxs-lookup"><span data-stu-id="b3ad1-112">Non-secure main origins</span></span>   

<span data-ttu-id="b3ad1-113">ページのメインの起点がセキュリティで保護されていない場合、**このページは**セキュリティで保護されていないことを**示してい**ます。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-113">When the main origin of a page is not secure, the **Security Overview** says **This page is not secure**.</span></span>  

> ##### <span data-ttu-id="b3ad1-114">図 2</span><span class="sxs-lookup"><span data-stu-id="b3ad1-114">Figure 2</span></span>  
> <span data-ttu-id="b3ad1-115">セキュリティで保護されていないページ</span><span class="sxs-lookup"><span data-stu-id="b3ad1-115">A non-secure page</span></span>  
> ![セキュリティで保護されていないページ][ImageNonSecurePage]  

<span data-ttu-id="b3ad1-117">この問題は、アクセスした URL が HTTP 経由で要求された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-117">This problem occurs when the URL that you visited was requested over HTTP.</span></span>  <span data-ttu-id="b3ad1-118">セキュリティを確保するには、HTTPS 経由で要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-118">To make it secure you need to request it over HTTPS.</span></span>  <span data-ttu-id="b3ad1-119">たとえば、アドレスバーに表示される URL を見ると、次のように表示されることがあり `http://example.com` ます。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-119">For example, if you look at the URL in your address bar, it probably looks similar to `http://example.com`.</span></span>  <span data-ttu-id="b3ad1-120">URL がセキュリティで保護されるようにし `https://example.com` ます。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-120">To make it secure the URL should be `https://example.com`.</span></span>  

<span data-ttu-id="b3ad1-121">サーバーに HTTPS を既にセットアップしている場合は、この問題を解決するために必要な操作は、すべての HTTP 要求を HTTPS にリダイレクトするようにサーバーを構成することだけです。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-121">If you already set up HTTPS on your server, all you need to do to fix this problem is configure your server to redirect all HTTP requests to HTTPS.</span></span>  

<span data-ttu-id="b3ad1-122">サーバーで HTTPS をセットアップしていない場合は、[暗号化][LetsEncrypt]を使用して、処理を開始するための無料で比較的簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-122">If you have not set up HTTPS on your server, [Let's Encrypt][LetsEncrypt] provides a free and relatively-easy way to start the process.</span></span>  <span data-ttu-id="b3ad1-123">または、サイトを CDN でホストすることを検討することもできます。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-123">Or, you might consider hosting your site on a CDN.</span></span>  <span data-ttu-id="b3ad1-124">既定では、ほとんどの主要な CDNs ホストサイトが HTTPS で提供されます。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-124">Most major CDNs host sites on HTTPS by default now.</span></span>  

> [!TIP]
> <span data-ttu-id="b3ad1-125">[Webhint][Webhint]で[https の使用][WebhintUseHttps]に関するヒントを使用すると、すべての HTTP 要求が HTTPS に転送されることを確認するプロセスを自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-125">The [Use HTTPS][WebhintUseHttps] hint in [webhint][Webhint] may help automate the process of making sure that all HTTP requests are directed to HTTPS.</span></span>  

### <span data-ttu-id="b3ad1-126">混在したコンテンツ</span><span class="sxs-lookup"><span data-stu-id="b3ad1-126">Mixed content</span></span>   

<span data-ttu-id="b3ad1-127">**混在**しているコンテンツとは、ページのメインの起点がセキュリティで保護されているが、ページは安全ではない元のリソースを要求したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-127">**Mixed content** means that the main origin of a page is secure, but the page requested resources from non-secure origins.</span></span>  <span data-ttu-id="b3ad1-128">混在したコンテンツページは、HTTP コンテンツがスニファーでアクセス可能であり、man-in-the-middle 攻撃に対して脆弱であるため、部分的に保護されています。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-128">Mixed content pages are only partially protected because the HTTP content is accessible to sniffers and vulnerable to man-in-the-middle attacks.</span></span>  

> ##### <span data-ttu-id="b3ad1-129">図 3</span><span class="sxs-lookup"><span data-stu-id="b3ad1-129">Figure 3</span></span>  
> <span data-ttu-id="b3ad1-130">混在したコンテンツ</span><span class="sxs-lookup"><span data-stu-id="b3ad1-130">Mixed content</span></span>  
> ![混在したコンテンツ][ImageMixedContent]  

<span data-ttu-id="b3ad1-132">[図 3](#figure-3)では、[**ネットワークパネル] で [1 つの要求を表示**] をクリックして [ネットワーク] パネルを開き、 **Network** `mixed-content:displayed` **ネットワークログ**にセキュリティ以外のリソースしか表示されないようにフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-132">In [Figure 3](#figure-3), click **View 1 request in Network panel** to open the **Network** panel and apply the `mixed-content:displayed` filter so that the **Network Log** only shows non-secure resources.</span></span>  

> ##### <span data-ttu-id="b3ad1-133">図 4</span><span class="sxs-lookup"><span data-stu-id="b3ad1-133">Figure 4</span></span>  
> <span data-ttu-id="b3ad1-134">ネットワークログの混在したリソース</span><span class="sxs-lookup"><span data-stu-id="b3ad1-134">Mixed resources in the Network Log</span></span>  
> ![ネットワークログの混在したリソース][ImageMixedResourcesNetworkLog]  

## <span data-ttu-id="b3ad1-136">詳細の表示</span><span class="sxs-lookup"><span data-stu-id="b3ad1-136">View details</span></span>   

### <span data-ttu-id="b3ad1-137">メインの元の証明書を表示する</span><span class="sxs-lookup"><span data-stu-id="b3ad1-137">View main origin certificate</span></span>   

<span data-ttu-id="b3ad1-138">セキュリティの**概要**で、[**証明書の表示**] をクリックして、メインの元の証明書をすばやく検査します。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-138">From the **Security Overview**, click **View certificate** to quickly inspect the certificate for the main origin.</span></span>  

> ##### <span data-ttu-id="b3ad1-139">図 5</span><span class="sxs-lookup"><span data-stu-id="b3ad1-139">Figure 5</span></span>  
> <span data-ttu-id="b3ad1-140">メインの元の証明書</span><span class="sxs-lookup"><span data-stu-id="b3ad1-140">A main origin certificate</span></span>  
> ![メインの元の証明書][ImageCertificate]  

### <span data-ttu-id="b3ad1-142">オリジンの詳細の表示</span><span class="sxs-lookup"><span data-stu-id="b3ad1-142">View origin details</span></span>   

<span data-ttu-id="b3ad1-143">左側のナビゲーションでいずれかのエントリをクリックして、元の情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-143">Click one of the entries in the left-hand nav to view the details of the origin.</span></span>  <span data-ttu-id="b3ad1-144">[詳細] ページでは、接続と証明書の情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-144">From the details page you are able to view connection and certificate information.</span></span>  <span data-ttu-id="b3ad1-145">証明書の透過性情報は、可能な場合にも表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-145">Certificate transparency information is also shown when available.</span></span>  

> ##### <span data-ttu-id="b3ad1-146">図 6</span><span class="sxs-lookup"><span data-stu-id="b3ad1-146">Figure 6</span></span>  
> <span data-ttu-id="b3ad1-147">主要な原産国の詳細</span><span class="sxs-lookup"><span data-stu-id="b3ad1-147">Main origin details</span></span>  
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
> <span data-ttu-id="b3ad1-160">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-160">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b3ad1-161">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/security/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-161">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/security/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="b3ad1-163">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="b3ad1-163">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
