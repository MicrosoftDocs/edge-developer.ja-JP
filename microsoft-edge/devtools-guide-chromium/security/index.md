---
description: ページが HTTPS で完全に保護されている場合は、セキュリティ パネルを使用します。
title: Microsoft Edge DevTools のセキュリティの問題を理解する
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

# <a name="understand-security-issues-with-microsoft-edge-devtools"></a><span data-ttu-id="1ad02-104">Microsoft Edge DevTools のセキュリティの問題を理解する</span><span class="sxs-lookup"><span data-stu-id="1ad02-104">Understand security issues with Microsoft Edge DevTools</span></span>  

  

<!--Use the **Security** Panel in [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to make sure HTTPS is properly implemented on a page.  Navigate to **Why HTTPS Matters** to learn why every website should be protected with HTTPS, even sites that do not handle sensitive user data.  -->  

<!--todo: add section when why-https is available -->  

## <a name="open-the-security-panel"></a><span data-ttu-id="1ad02-105">[セキュリティ] パネルを開く</span><span class="sxs-lookup"><span data-stu-id="1ad02-105">Open the Security panel</span></span>  

<span data-ttu-id="1ad02-106">セキュリティ **パネル** は、ページのセキュリティを検査する DevTools の主要な場所です。</span><span class="sxs-lookup"><span data-stu-id="1ad02-106">The **Security** panel is the main place in DevTools for inspecting the security of a page.</span></span>  

1.  <span data-ttu-id="1ad02-107">[DevTools を開きます][DevToolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="1ad02-107">[Open DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="1ad02-108">[セキュリティ **] タブを** 選択して、[セキュリティ] ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="1ad02-108">Choose the **Security** tab to open the **Security** tool.</span></span>  
    
    :::image type="complex" source="../media/security-security-overview-secure.msft.png" alt-text="[セキュリティ] パネル" lightbox="../media/security-security-overview-secure.msft.png":::
       <span data-ttu-id="1ad02-110">[ **セキュリティ]** パネル</span><span class="sxs-lookup"><span data-stu-id="1ad02-110">The **Security** panel</span></span>  
    :::image-end:::  
    
## <a name="common-problems"></a><span data-ttu-id="1ad02-111">一般的な問題</span><span class="sxs-lookup"><span data-stu-id="1ad02-111">Common problems</span></span>  

### <a name="non-secure-main-origins"></a><span data-ttu-id="1ad02-112">セキュリティで保護されていない主な発生元</span><span class="sxs-lookup"><span data-stu-id="1ad02-112">Non-secure main origins</span></span>  

<span data-ttu-id="1ad02-113">ページの主な作成元がセキュリティで保護されていない場合、セキュリティ **の概要には** 、この **ページはセキュリティで保護されていないと表示されます**。</span><span class="sxs-lookup"><span data-stu-id="1ad02-113">When the main origin of a page is not secure, the **Security Overview** says **This page is not secure**.</span></span>  

:::image type="complex" source="../media/security-security-overview-non-secure.msft.png" alt-text="セキュリティ保護されていないページ" lightbox="../media/security-security-overview-non-secure.msft.png":::
   <span data-ttu-id="1ad02-115">セキュリティ保護されていないページ</span><span class="sxs-lookup"><span data-stu-id="1ad02-115">A non-secure page</span></span>  
:::image-end:::  

<span data-ttu-id="1ad02-116">この問題は、アクセスした URL が HTTP を使用して要求された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="1ad02-116">This problem occurs when the URL that you visited was requested over HTTP.</span></span>  <span data-ttu-id="1ad02-117">セキュリティで保護するには、HTTPS 経由で要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ad02-117">To make it secure you need to request it over HTTPS.</span></span>  <span data-ttu-id="1ad02-118">たとえば、アドレス バーの URL を確認すると、おそらくに似ています `http://example.com` 。</span><span class="sxs-lookup"><span data-stu-id="1ad02-118">For example, if you look at the URL in your address bar, it probably looks similar to `http://example.com`.</span></span>  <span data-ttu-id="1ad02-119">URL をセキュリティで保護するには、 である必要があります `https://example.com` 。</span><span class="sxs-lookup"><span data-stu-id="1ad02-119">To make it secure the URL should be `https://example.com`.</span></span>  

<span data-ttu-id="1ad02-120">サーバーで HTTPS を既にセットアップしている場合は、この問題を解決するために必要なのは、すべての HTTP 要求を HTTPS にリダイレクトするようにサーバーを構成することです。</span><span class="sxs-lookup"><span data-stu-id="1ad02-120">If you already set up HTTPS on your server, all you need to do to fix this problem is configure your server to redirect all HTTP requests to HTTPS.</span></span>  

<span data-ttu-id="1ad02-121">サーバーで HTTPS を設定していない場合は [、Let's Encrypt][LetsEncrypt] を使用すると、プロセスを開始するための無料で比較的簡単な方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="1ad02-121">If you have not set up HTTPS on your server, [Let's Encrypt][LetsEncrypt] provides a free and relatively-easy way to start the process.</span></span>  <span data-ttu-id="1ad02-122">または、CDN でのサイトのホストを検討する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="1ad02-122">Or, you may consider hosting your site on a CDN.</span></span>  <span data-ttu-id="1ad02-123">現在、ほとんどの主要な CDN は HTTPS 上のサイトを既定でホストしています。</span><span class="sxs-lookup"><span data-stu-id="1ad02-123">Most major CDNs host sites on HTTPS by default now.</span></span>  

> [!TIP]
> <span data-ttu-id="1ad02-124">[Webhint で HTTPS][WebhintUseHttps]ヒント[を使用すると][Webhint]、すべての HTTP 要求が HTTPS に送信されるプロセスを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="1ad02-124">The [Use HTTPS][WebhintUseHttps] hint in [webhint][Webhint] may help automate the process of making sure that all HTTP requests are directed to HTTPS.</span></span>  

### <a name="mixed-content"></a><span data-ttu-id="1ad02-125">混在コンテンツ</span><span class="sxs-lookup"><span data-stu-id="1ad02-125">Mixed content</span></span>  

<span data-ttu-id="1ad02-126">**混在コンテンツ** とは、ページの主な作成元がセキュリティで保護されているが、ページがセキュリティで保護されていないオリジンからリソースを要求したという意味です。</span><span class="sxs-lookup"><span data-stu-id="1ad02-126">**Mixed content** means that the main origin of a page is secure, but the page requested resources from non-secure origins.</span></span>  <span data-ttu-id="1ad02-127">混在コンテンツ ページは部分的にしか保護されません。HTTP コンテンツはスニッフィングにアクセス可能で、中間者攻撃に対して脆弱です。</span><span class="sxs-lookup"><span data-stu-id="1ad02-127">Mixed content pages are only partially protected because the HTTP content is accessible to sniffers and vulnerable to man-in-the-middle attacks.</span></span>  

:::image type="complex" source="../media/security-security-overview-mixed-secure.msft.png" alt-text="混在コンテンツ" lightbox="../media/security-security-overview-mixed-secure.msft.png":::
   <span data-ttu-id="1ad02-129">混在コンテンツ</span><span class="sxs-lookup"><span data-stu-id="1ad02-129">Mixed content</span></span>  
:::image-end:::  

<span data-ttu-id="1ad02-130">前の図で、[ネットワーク] パネルで **[1**要求\*\*\*\* の表示] を選択してネットワーク ツールを開き、フィルターを適用して、ネットワーク ログにセキュリティ保護されていないリソースのみを `mixed-content:displayed` \*\*\*\* 表示します。</span><span class="sxs-lookup"><span data-stu-id="1ad02-130">In the previous figure, choose **View 1 request in Network panel** to open the **Network** tool and apply the `mixed-content:displayed` filter so that the **Network Log** only shows non-secure resources.</span></span>  

:::image type="complex" source="../media/security-network-filter.msft.png" alt-text="ネットワーク ログ内の混在リソース" lightbox="../media/security-network-filter.msft.png":::
   <span data-ttu-id="1ad02-132">ネットワーク ログ内の **混在リソース**</span><span class="sxs-lookup"><span data-stu-id="1ad02-132">Mixed resources in the **Network Log**</span></span>  
:::image-end:::  

## <a name="view-details"></a><span data-ttu-id="1ad02-133">詳細の表示</span><span class="sxs-lookup"><span data-stu-id="1ad02-133">View details</span></span>  

### <a name="view-main-origin-certificate"></a><span data-ttu-id="1ad02-134">メインオリジン証明書の表示</span><span class="sxs-lookup"><span data-stu-id="1ad02-134">View main origin certificate</span></span>  

<span data-ttu-id="1ad02-135">[セキュリティの **概要] で**、[証明書の **表示] を** 選択して、メインの発行元の証明書をすばやく検査します。</span><span class="sxs-lookup"><span data-stu-id="1ad02-135">From the **Security Overview**, choose **View certificate** to quickly inspect the certificate for the main origin.</span></span>  

:::image type="complex" source="../media/security-security-overview-secure-view-certificate.msft.png" alt-text="主な発行元証明書" lightbox="../media/security-security-overview-secure-view-certificate.msft.png":::
   <span data-ttu-id="1ad02-137">主な発行元証明書</span><span class="sxs-lookup"><span data-stu-id="1ad02-137">A main origin certificate</span></span>  
:::image-end:::  

### <a name="view-origin-details"></a><span data-ttu-id="1ad02-138">原点の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="1ad02-138">View origin details</span></span>  

<span data-ttu-id="1ad02-139">左側のナビゲーションでエントリの 1 つを選択して、原点の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="1ad02-139">Choose one of the entries in the left-hand nav to view the details of the origin.</span></span>  <span data-ttu-id="1ad02-140">詳細ページから、接続と証明書の情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="1ad02-140">From the details page you are able to view connection and certificate information.</span></span>  <span data-ttu-id="1ad02-141">証明書の透明性情報は、利用可能な場合にも表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ad02-141">Certificate transparency information is also shown when available.</span></span>  

:::image type="complex" source="../media/security-security-overview-mixed-secure-main-origin.msft.png" alt-text="主な発生元の詳細" lightbox="../media/security-security-overview-mixed-secure-main-origin.msft.png":::
   <span data-ttu-id="1ad02-143">主な発生元の詳細</span><span class="sxs-lookup"><span data-stu-id="1ad02-143">Main origin details</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="1ad02-144">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="1ad02-144">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (クロム) 開発者向け|Microsoft Docs"  
[DevToolsOpen]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  

[LetsEncrypt]: https://letsencrypt.org "Let's Encrypt - 無料の SSL/TLS 証明書"  

[Webhint]: https://webhint.io "webhint"  
[WebhintUseHttps]: https://webhint.io/docs/user-guide/hints/hint-https-only "HTTPS を使用|webhint のドキュメント"  

<!--[mixed]: /web/fundamentals/security/prevent-mixed-content/what-is-mixed-content ""  -->

> [!NOTE]
> <span data-ttu-id="1ad02-150">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="1ad02-150">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="1ad02-151">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/security/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="1ad02-151">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/security/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="1ad02-153">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="1ad02-153">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
