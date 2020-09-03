---
description: セキュリティパネルを使用して、ページが HTTPS によって完全に保護されていることを確認します。
title: Microsoft Edge DevTools のセキュリティに関する問題を理解する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 2538f80b08c8162d27f075775075a8b81c5f7725
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993577"
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





# <span data-ttu-id="276ff-104">Microsoft Edge DevTools のセキュリティに関する問題を理解する</span><span class="sxs-lookup"><span data-stu-id="276ff-104">Understand security issues with Microsoft Edge DevTools</span></span>   

  

<!--Use the **Security** Panel in [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to make sure HTTPS is properly implemented on a page.  See **Why HTTPS Matters** to learn why every website should be protected with HTTPS, even sites that do not handle sensitive user data.  -->  

<!--todo: add section when why-https is available -->  

## <span data-ttu-id="276ff-105">セキュリティパネルを開く</span><span class="sxs-lookup"><span data-stu-id="276ff-105">Open the Security panel</span></span>   

<span data-ttu-id="276ff-106">**セキュリティ**パネルは、ページのセキュリティを検査するための devtools の主要な場所です。</span><span class="sxs-lookup"><span data-stu-id="276ff-106">The **Security** panel is the main place in DevTools for inspecting the security of a page.</span></span>  

1.  <span data-ttu-id="276ff-107">[DevTools を開き][DevToolsOpen]ます。</span><span class="sxs-lookup"><span data-stu-id="276ff-107">[Open DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="276ff-108">[ **セキュリティ** ] タブをクリックして、[ **セキュリティ** ] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="276ff-108">Click the **Security** tab to open the **Security** panel.</span></span>  
    
    :::image type="complex" source="../media/security-security-overview-secure.msft.png" alt-text="セキュリティパネル" lightbox="../media/security-security-overview-secure.msft.png":::
       <span data-ttu-id="276ff-110">**セキュリティ**パネル</span><span class="sxs-lookup"><span data-stu-id="276ff-110">The **Security** panel</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="276ff-111">一般的な問題</span><span class="sxs-lookup"><span data-stu-id="276ff-111">Common problems</span></span>   

### <span data-ttu-id="276ff-112">セキュリティで保護されていない本文</span><span class="sxs-lookup"><span data-stu-id="276ff-112">Non-secure main origins</span></span>   

<span data-ttu-id="276ff-113">ページのメインの起点がセキュリティで保護されていない場合、**このページは**セキュリティで保護されていないことを**示してい**ます。</span><span class="sxs-lookup"><span data-stu-id="276ff-113">When the main origin of a page is not secure, the **Security Overview** says **This page is not secure**.</span></span>  

:::image type="complex" source="../media/security-security-overview-non-secure.msft.png" alt-text="セキュリティで保護されていないページ" lightbox="../media/security-security-overview-non-secure.msft.png":::
   <span data-ttu-id="276ff-115">セキュリティで保護されていないページ</span><span class="sxs-lookup"><span data-stu-id="276ff-115">A non-secure page</span></span>  
:::image-end:::  

<span data-ttu-id="276ff-116">この問題は、アクセスした URL が HTTP 経由で要求された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="276ff-116">This problem occurs when the URL that you visited was requested over HTTP.</span></span>  <span data-ttu-id="276ff-117">セキュリティを確保するには、HTTPS 経由で要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="276ff-117">To make it secure you need to request it over HTTPS.</span></span>  <span data-ttu-id="276ff-118">たとえば、アドレスバーに表示される URL を見ると、次のように表示されることがあり `http://example.com` ます。</span><span class="sxs-lookup"><span data-stu-id="276ff-118">For example, if you look at the URL in your address bar, it probably looks similar to `http://example.com`.</span></span>  <span data-ttu-id="276ff-119">URL がセキュリティで保護されるようにし `https://example.com` ます。</span><span class="sxs-lookup"><span data-stu-id="276ff-119">To make it secure the URL should be `https://example.com`.</span></span>  

<span data-ttu-id="276ff-120">サーバーに HTTPS を既にセットアップしている場合は、この問題を解決するために必要な操作は、すべての HTTP 要求を HTTPS にリダイレクトするようにサーバーを構成することだけです。</span><span class="sxs-lookup"><span data-stu-id="276ff-120">If you already set up HTTPS on your server, all you need to do to fix this problem is configure your server to redirect all HTTP requests to HTTPS.</span></span>  

<span data-ttu-id="276ff-121">サーバーで HTTPS をセットアップしていない場合は、 [暗号化][LetsEncrypt] を使用して、処理を開始するための無料で比較的簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="276ff-121">If you have not set up HTTPS on your server, [Let's Encrypt][LetsEncrypt] provides a free and relatively-easy way to start the process.</span></span>  <span data-ttu-id="276ff-122">または、サイトを CDN でホストすることを検討することもできます。</span><span class="sxs-lookup"><span data-stu-id="276ff-122">Or, you might consider hosting your site on a CDN.</span></span>  <span data-ttu-id="276ff-123">既定では、ほとんどの主要な CDNs ホストサイトが HTTPS で提供されます。</span><span class="sxs-lookup"><span data-stu-id="276ff-123">Most major CDNs host sites on HTTPS by default now.</span></span>  

> [!TIP]
> <span data-ttu-id="276ff-124">[Webhint][Webhint]で[https の使用][WebhintUseHttps]に関するヒントを使用すると、すべての HTTP 要求が HTTPS に転送されることを確認するプロセスを自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="276ff-124">The [Use HTTPS][WebhintUseHttps] hint in [webhint][Webhint] may help automate the process of making sure that all HTTP requests are directed to HTTPS.</span></span>  

### <span data-ttu-id="276ff-125">混在したコンテンツ</span><span class="sxs-lookup"><span data-stu-id="276ff-125">Mixed content</span></span>   

<span data-ttu-id="276ff-126">**混在** しているコンテンツとは、ページのメインの起点がセキュリティで保護されているが、ページは安全ではない元のリソースを要求したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="276ff-126">**Mixed content** means that the main origin of a page is secure, but the page requested resources from non-secure origins.</span></span>  <span data-ttu-id="276ff-127">混在したコンテンツページは、HTTP コンテンツがスニファーでアクセス可能であり、man-in-the-middle 攻撃に対して脆弱であるため、部分的に保護されています。</span><span class="sxs-lookup"><span data-stu-id="276ff-127">Mixed content pages are only partially protected because the HTTP content is accessible to sniffers and vulnerable to man-in-the-middle attacks.</span></span>  

:::image type="complex" source="../media/security-security-overview-mixed-secure.msft.png" alt-text="混在したコンテンツ" lightbox="../media/security-security-overview-mixed-secure.msft.png":::
   <span data-ttu-id="276ff-129">混在したコンテンツ</span><span class="sxs-lookup"><span data-stu-id="276ff-129">Mixed content</span></span>  
:::image-end:::  

<span data-ttu-id="276ff-130">上の図では、[**ネットワークパネル] で [1 つの要求を表示**] をクリックして [ネットワーク] パネルを開き、 **Network** `mixed-content:displayed` **ネットワークログ**にセキュリティ以外のリソースしか表示されないようにフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="276ff-130">In the previous figure, click **View 1 request in Network panel** to open the **Network** panel and apply the `mixed-content:displayed` filter so that the **Network Log** only shows non-secure resources.</span></span>  

:::image type="complex" source="../media/security-network-filter.msft.png" alt-text="ネットワークログの混在したリソース" lightbox="../media/security-network-filter.msft.png":::
   <span data-ttu-id="276ff-132">**ネットワークログ**の混在したリソース</span><span class="sxs-lookup"><span data-stu-id="276ff-132">Mixed resources in the **Network Log**</span></span>  
:::image-end:::  

## <span data-ttu-id="276ff-133">詳細の表示</span><span class="sxs-lookup"><span data-stu-id="276ff-133">View details</span></span>   

### <span data-ttu-id="276ff-134">メインの元の証明書を表示する</span><span class="sxs-lookup"><span data-stu-id="276ff-134">View main origin certificate</span></span>   

<span data-ttu-id="276ff-135">セキュリティの **概要**で、[ **証明書の表示** ] をクリックして、メインの元の証明書をすばやく検査します。</span><span class="sxs-lookup"><span data-stu-id="276ff-135">From the **Security Overview**, click **View certificate** to quickly inspect the certificate for the main origin.</span></span>  

:::image type="complex" source="../media/security-security-overview-secure-view-certificate.msft.png" alt-text="メインの元の証明書" lightbox="../media/security-security-overview-secure-view-certificate.msft.png":::
   <span data-ttu-id="276ff-137">メインの元の証明書</span><span class="sxs-lookup"><span data-stu-id="276ff-137">A main origin certificate</span></span>  
:::image-end:::  

### <span data-ttu-id="276ff-138">オリジンの詳細の表示</span><span class="sxs-lookup"><span data-stu-id="276ff-138">View origin details</span></span>   

<span data-ttu-id="276ff-139">左側のナビゲーションでいずれかのエントリをクリックして、元の情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="276ff-139">Click one of the entries in the left-hand nav to view the details of the origin.</span></span>  <span data-ttu-id="276ff-140">[詳細] ページでは、接続と証明書の情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="276ff-140">From the details page you are able to view connection and certificate information.</span></span>  <span data-ttu-id="276ff-141">証明書の透過性情報は、可能な場合にも表示されます。</span><span class="sxs-lookup"><span data-stu-id="276ff-141">Certificate transparency information is also shown when available.</span></span>  

:::image type="complex" source="../media/security-security-overview-mixed-secure-main-origin.msft.png" alt-text="主要な原産国の詳細" lightbox="../media/security-security-overview-mixed-secure-main-origin.msft.png":::
   <span data-ttu-id="276ff-143">主要な原産国の詳細</span><span class="sxs-lookup"><span data-stu-id="276ff-143">Main origin details</span></span>  
:::image-end:::  

<!--  
 


-->  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevToolsOpen]: ../open.md "Microsoft Edge DevTools を開く |Microsoft ドキュメント"  


[LetsEncrypt]: https://letsencrypt.org "暗号化されていない SSL/TLS 証明書を使用する"  

[Webhint]: https://webhint.io "web ヒント"  
[WebhintUseHttps]: https://webhint.io/docs/user-guide/hints/hint-https-only "HTTPS を使用 |webhint に関するドキュメント"  

<!--[mixed]: /web/fundamentals/security/prevent-mixed-content/what-is-mixed-content ""  -->

> [!NOTE]
> <span data-ttu-id="276ff-149">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="276ff-149">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="276ff-150">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/security/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="276ff-150">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/security/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="276ff-152">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="276ff-152">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
