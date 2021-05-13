---
description: DevTools の [ネットワーク] パネルでネットワークの問題を検出するMicrosoft Edge説明します。
title: ネットワーク問題ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c99f43872abe04800880c63ee4126bfcdd633edb
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564981"
---
<!-- Copyright Kayce Basques and Jonathan Garbee

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->
# <a name="network-issues-guide"></a><span data-ttu-id="33e90-104">ネットワーク問題ガイド</span><span class="sxs-lookup"><span data-stu-id="33e90-104">Network issues guide</span></span>  

<span data-ttu-id="33e90-105">このガイドでは、DevTools の [ネットワーク] パネルでネットワークの問題や最適化の機会Microsoft Edge示します。</span><span class="sxs-lookup"><span data-stu-id="33e90-105">This guide shows you how to detect network issues or optimization opportunities in the Network panel of Microsoft Edge DevTools.</span></span>  

<span data-ttu-id="33e90-106">ネットワーク ツールの基本**を確認するには**、[ネットワーク] ツールに移動[はじめに。][NetworkPerformance]</span><span class="sxs-lookup"><span data-stu-id="33e90-106">To learn the basics of the **Network** tool, navigate to [Get Started][NetworkPerformance].</span></span>  

## <a name="queued-or-stalled-requests"></a><span data-ttu-id="33e90-107">キューに入れまたは停止している要求</span><span class="sxs-lookup"><span data-stu-id="33e90-107">Queued or stalled requests</span></span>  

**<span data-ttu-id="33e90-108">現象</span><span class="sxs-lookup"><span data-stu-id="33e90-108">Symptoms</span></span>**  

<span data-ttu-id="33e90-109">6 つの要求が同時にダウンロードされています。</span><span class="sxs-lookup"><span data-stu-id="33e90-109">Six requests are downloading simultaneously.</span></span>  <span data-ttu-id="33e90-110">その後、一連の要求がキューに入れられます。または停止します。</span><span class="sxs-lookup"><span data-stu-id="33e90-110">After that, a series of requests are queued or stalled.</span></span>  <span data-ttu-id="33e90-111">最初の 6 つの要求の 1 つが終了すると、キュー内の要求の 1 つが開始されます。</span><span class="sxs-lookup"><span data-stu-id="33e90-111">Once one of the first six requests finishes, one of the requests in the queue starts.</span></span>  

<span data-ttu-id="33e90-112">次の **図のウォーター** フォールでは、アセットの最初の 6 つの要求が `edge-iconx1024.msft.png` 同時に開始されます。</span><span class="sxs-lookup"><span data-stu-id="33e90-112">In the **Waterfall** in the following figure, the first six requests for the `edge-iconx1024.msft.png` asset start simultaneously.</span></span>  <span data-ttu-id="33e90-113">以降の要求は、元の 6 つの要求の 1 つが終了するまで停止します。</span><span class="sxs-lookup"><span data-stu-id="33e90-113">The subsequent requests are stalled until one of the original six finishes.</span></span>  

:::image type="complex" source="../media/network-network-disabled-cache-resources-queue.msft.png" alt-text="ネットワーク パネルのキューに入れまたは停止している系列の例" lightbox="../media/network-network-disabled-cache-resources-queue.msft.png":::
   <span data-ttu-id="33e90-115">ネットワーク ツールのキューに入れまたは停止している系列**の例**</span><span class="sxs-lookup"><span data-stu-id="33e90-115">An example of a queued or stalled series in the **Network** tool</span></span>  
:::image-end:::  

**<span data-ttu-id="33e90-116">原因</span><span class="sxs-lookup"><span data-stu-id="33e90-116">Causes</span></span>**  

<span data-ttu-id="33e90-117">1 つのドメインで要求が多すぎます。</span><span class="sxs-lookup"><span data-stu-id="33e90-117">Too many requests are being made on a single domain.</span></span>  <span data-ttu-id="33e90-118">HTTP/1.0 または HTTP/1.1 接続では、Microsoft Edgeホストごとに最大 6 つの同時 TCP 接続を許可します。</span><span class="sxs-lookup"><span data-stu-id="33e90-118">On HTTP/1.0 or HTTP/1.1 connections, Microsoft Edge allows a maximum of six simultaneous TCP connections per host.</span></span>  

**<span data-ttu-id="33e90-119">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="33e90-119">Fixes</span></span>**  

*   <span data-ttu-id="33e90-120">HTTP/1.0 または HTTP/1.1 を使用する必要がある場合は、ドメイン シャーディングを実装します。</span><span class="sxs-lookup"><span data-stu-id="33e90-120">Implement domain sharding if you must use HTTP/1.0 or HTTP/1.1.</span></span>  
*   <span data-ttu-id="33e90-121">HTTP/2 を使用します。</span><span class="sxs-lookup"><span data-stu-id="33e90-121">Use HTTP/2.</span></span>  <span data-ttu-id="33e90-122">HTTP/2 でドメイン シャーディングを使用しない。</span><span class="sxs-lookup"><span data-stu-id="33e90-122">Do not use domain sharding with HTTP/2.</span></span>  
*   <span data-ttu-id="33e90-123">重要な要求が以前にダウンロードされるので、不要な要求を削除または延期します。</span><span class="sxs-lookup"><span data-stu-id="33e90-123">Remove or defer unnecessary requests so that critical requests download earlier.</span></span>  
    
## <a name="slow-time-to-first-byte-ttfb"></a><span data-ttu-id="33e90-124">最初のバイトへの低速時間 (TTFB)</span><span class="sxs-lookup"><span data-stu-id="33e90-124">Slow Time To First Byte (TTFB)</span></span>  

**<span data-ttu-id="33e90-125">現象</span><span class="sxs-lookup"><span data-stu-id="33e90-125">Symptoms</span></span>**  

<span data-ttu-id="33e90-126">要求は、サーバーから最初のバイトを受け取るのを待つのに長い時間を費やします。</span><span class="sxs-lookup"><span data-stu-id="33e90-126">A request spends a long time waiting to receive the first byte from the server.</span></span>  

<span data-ttu-id="33e90-127">次の図では、ウォーターフォールの長い緑色のバー **は** 、要求が長い時間待っていたかどうかを示しています。</span><span class="sxs-lookup"><span data-stu-id="33e90-127">In the following figure, the long, green bar in the **Waterfall** indicates that the request was waiting a long time.</span></span>  <span data-ttu-id="33e90-128">これは、プロファイルを使用してネットワーク速度を制限し、遅延を追加するためにシミュレートされました。</span><span class="sxs-lookup"><span data-stu-id="33e90-128">This was simulated using a profile to restrict network speed and add a delay.</span></span>  

:::image type="complex" source="../media/network-network-resources-using-dial-up-profile.msft.png" alt-text="時間が遅い最初のバイトの要求の例" lightbox="../media/network-network-resources-using-dial-up-profile.msft.png":::
   <span data-ttu-id="33e90-130">時間が遅い最初のバイトの要求の例</span><span class="sxs-lookup"><span data-stu-id="33e90-130">An example of a request with a slow Time To First Byte</span></span>  
:::image-end:::  

**<span data-ttu-id="33e90-131">原因</span><span class="sxs-lookup"><span data-stu-id="33e90-131">Causes</span></span>**  

*   <span data-ttu-id="33e90-132">クライアントとサーバー間の接続が遅い。</span><span class="sxs-lookup"><span data-stu-id="33e90-132">The connection between the client and server is slow.</span></span>  
*   <span data-ttu-id="33e90-133">サーバーの応答が遅い。</span><span class="sxs-lookup"><span data-stu-id="33e90-133">The server is slow to respond.</span></span>  <span data-ttu-id="33e90-134">サーバーをローカルでホストして、低速の接続またはサーバーかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="33e90-134">Host the server locally to determine if it is the connection or server that is slow.</span></span>  <span data-ttu-id="33e90-135">ローカル サーバーにアクセスするときに最初のバイト \(TTFB\) への時間が遅い場合は、サーバーの速度が低下します。</span><span class="sxs-lookup"><span data-stu-id="33e90-135">If you still get a slow Time To First Byte \(TTFB\) when accessing a local server, then the server is slow.</span></span>  
    
**<span data-ttu-id="33e90-136">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="33e90-136">Fixes</span></span>**  

*   <span data-ttu-id="33e90-137">接続が遅い場合は、コンテンツをホストする方法やホスティング プロバイダー CDN変更する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="33e90-137">If the connection is slow, consider hosting your content on a CDN or changing hosting providers.</span></span>  
*   <span data-ttu-id="33e90-138">サーバーの速度が遅い場合は、データベース クエリの最適化、キャッシュの実装、またはサーバー構成の変更を検討してください。</span><span class="sxs-lookup"><span data-stu-id="33e90-138">If the server is slow, consider optimizing database queries, implementing a cache, or modifying your server configuration.</span></span>  
    
## <a name="slow-content-download"></a><span data-ttu-id="33e90-139">コンテンツのダウンロードが遅い</span><span class="sxs-lookup"><span data-stu-id="33e90-139">Slow content download</span></span>  

**<span data-ttu-id="33e90-140">現象</span><span class="sxs-lookup"><span data-stu-id="33e90-140">Symptoms</span></span>**  

<span data-ttu-id="33e90-141">要求のダウンロードには長い時間が必要です。</span><span class="sxs-lookup"><span data-stu-id="33e90-141">A request takes a long time to download.</span></span>  

<span data-ttu-id="33e90-142">次の図では、png の横にあるウォーターフォール\*\*\*\* の長い青いバーは、ダウンロードに長い時間がかかったという意味です。</span><span class="sxs-lookup"><span data-stu-id="33e90-142">In the following figure, the long, blue bar in the **Waterfall** next to the png means it took a long time to download.</span></span>  

:::image type="complex" source="../media/network-network-resources-edge-devtools.msft.png" alt-text="ダウンロードに長い時間がかかる要求の例" lightbox="../media/network-network-resources-edge-devtools.msft.png":::
   <span data-ttu-id="33e90-144">ダウンロードに長い時間がかかる要求の例</span><span class="sxs-lookup"><span data-stu-id="33e90-144">An example of a request that takes a long time to download</span></span>  
:::image-end:::  

**<span data-ttu-id="33e90-145">原因</span><span class="sxs-lookup"><span data-stu-id="33e90-145">Causes</span></span>**  

*   <span data-ttu-id="33e90-146">クライアントとサーバー間の接続が遅い。</span><span class="sxs-lookup"><span data-stu-id="33e90-146">The connection between the client and server is slow.</span></span>  
*   <span data-ttu-id="33e90-147">多くのコンテンツがダウンロードされています。</span><span class="sxs-lookup"><span data-stu-id="33e90-147">A lot of content is being downloaded.</span></span>  
    
**<span data-ttu-id="33e90-148">修正プログラム</span><span class="sxs-lookup"><span data-stu-id="33e90-148">Fixes</span></span>**  

*   <span data-ttu-id="33e90-149">コンテンツをホストする場合は、CDNホスティング プロバイダーを変更する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="33e90-149">Consider hosting your content on a CDN or changing hosting providers.</span></span>  
*   <span data-ttu-id="33e90-150">要求を最適化して送信するバイト数を少なくします。</span><span class="sxs-lookup"><span data-stu-id="33e90-150">Send fewer bytes by optimizing your requests.</span></span>  
    
<!--   ## Contribute knowledge  

Do you have a network issue that should be added to this guide?  

*   Send a tweet to [@EdgeDevTools][MicrosoftEdgeTweet].  
*   Choose **Send Feedback** \(![Send Feedback](../media/smile-icon.msft.png)\) in the DevTools or select `Alt`+`Shift`+`I` \(Windows, Linux\) or `Option`+`Shift`+`I` \(macOS\) to provide feedback or feature requests.  
*   [Open an issue][WebFundamentalsIssue] on the docs repo.  -->  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="33e90-151">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="33e90-151">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[NetworkPerformance]: ./index.md "DevTools サーバーでネットワークMicrosoft Edgeを調|Microsoft Docs"  

[MicrosoftEdgeTweet]: https://twitter.com/intent/tweet?text=@EdgeDevTools%20[Network%20Issues%20Guide%20Suggestion]  

[WebFundamentalsIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Network%20Issues%20Guide%20Suggestion%5D "新しい問題 - Microsoft Docs/Edge Developer"  

> [!NOTE]
> <span data-ttu-id="33e90-154">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="33e90-154">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="33e90-155">元のページはここで[](https://developers.google.com/web/tools/chrome-devtools/network/issues)見つかり[、Kayce バス][KayceBasques]ク人 \(Technical Writer, Chrome DevTools \& ライトハウス\) と[Jonathan Garbee][JonathanGarbee] \(Google Developer Expert for Web Technology\) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="33e90-155">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/issues) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Jonathan Garbee][JonathanGarbee] \(Google Developer Expert for Web Technology\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="33e90-157">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="33e90-157">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[JonathanGarbee]: https://developers.google.com/web/resources/contributors#jonathan-garbee
