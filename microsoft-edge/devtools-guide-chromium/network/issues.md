---
title: ネットワークの問題に関するガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 018a6ef89242d55cefaa974641be456f4501c557
ms.sourcegitcommit: 33663cd7838dddee86228dde469a5e9551bddb02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611806"
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





# <span data-ttu-id="f2904-103">ネットワークの問題に関するガイド</span><span class="sxs-lookup"><span data-stu-id="f2904-103">Network Issues Guide</span></span>   




<span data-ttu-id="f2904-104">このガイドでは、Microsoft Edge DevTools のネットワークパネルでネットワークの問題や最適化の機会を検出する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f2904-104">This guide shows you how to detect network issues or optimization opportunities in the Network panel of Microsoft Edge DevTools.</span></span>  

<span data-ttu-id="f2904-105">詳しく[は、「ネットワーク][NetworkPerformance]パネルの基本」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2904-105">See [Get Started][NetworkPerformance] to learn the basics of the Network panel.</span></span>  

## <span data-ttu-id="f2904-106">キューに入っているまたは停止している要求</span><span class="sxs-lookup"><span data-stu-id="f2904-106">Queued or stalled requests</span></span>   

### <span data-ttu-id="f2904-107">現象</span><span class="sxs-lookup"><span data-stu-id="f2904-107">Symptoms</span></span>  

<span data-ttu-id="f2904-108">6つの要求が同時にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="f2904-108">Six requests are downloading simultaneously.</span></span>  <span data-ttu-id="f2904-109">その後、一連の要求はキューまたは停止されます。</span><span class="sxs-lookup"><span data-stu-id="f2904-109">After that, a series of requests are queued or stalled.</span></span>  <span data-ttu-id="f2904-110">最初の6つの要求のいずれかが完了したら、キュー内のいずれかの要求が開始されます。</span><span class="sxs-lookup"><span data-stu-id="f2904-110">Once one of the first six requests finishes, one of the requests in the queue starts.</span></span>  

<span data-ttu-id="f2904-111">[図 1](#figure-1)の**ウォーターフォール**では、資産の最初の6つの要求が同時に開始され `edge-iconx1024.msft.png` ます。</span><span class="sxs-lookup"><span data-stu-id="f2904-111">In the **Waterfall** in [Figure 1](#figure-1), the first six requests for the `edge-iconx1024.msft.png` asset start simultaneously.</span></span>  <span data-ttu-id="f2904-112">それ以降の要求は、元の6つの処理が完了するまで停止します。</span><span class="sxs-lookup"><span data-stu-id="f2904-112">The subsequent requests are stalled until one of the original six finishes.</span></span>  

> ##### <span data-ttu-id="f2904-113">図 1</span><span class="sxs-lookup"><span data-stu-id="f2904-113">Figure 1</span></span>  
> <span data-ttu-id="f2904-114">[ネットワーク] パネルのキューに入っている、または停止しているシリーズの例</span><span class="sxs-lookup"><span data-stu-id="f2904-114">An example of a queued or stalled series in the Network panel</span></span>  
> ![[ネットワーク] パネルのキューに入っている、または停止しているシリーズの例][ImageStalled]  

### <span data-ttu-id="f2904-116">原因</span><span class="sxs-lookup"><span data-stu-id="f2904-116">Causes</span></span>  

<span data-ttu-id="f2904-117">1つのドメインで実行されている要求が多すぎます。</span><span class="sxs-lookup"><span data-stu-id="f2904-117">Too many requests are being made on a single domain.</span></span>  <span data-ttu-id="f2904-118">HTTP/1.0 または HTTP/1.1 接続の場合、Microsoft Edge では、ホストあたり最大6つの同時 TCP 接続を許可します。</span><span class="sxs-lookup"><span data-stu-id="f2904-118">On HTTP/1.0 or HTTP/1.1 connections, Microsoft Edge allows a maximum of six simultaneous TCP connections per host.</span></span>  

### <span data-ttu-id="f2904-119">修正</span><span class="sxs-lookup"><span data-stu-id="f2904-119">Fixes</span></span>  

*   <span data-ttu-id="f2904-120">HTTP/1.0 または HTTP/1.1 を使用する必要がある場合は、ドメイン sharding を実装します。</span><span class="sxs-lookup"><span data-stu-id="f2904-120">Implement domain sharding if you must use HTTP/1.0 or HTTP/1.1.</span></span>  
*   <span data-ttu-id="f2904-121">HTTP/2 を使用します。</span><span class="sxs-lookup"><span data-stu-id="f2904-121">Use HTTP/2.</span></span>  <span data-ttu-id="f2904-122">HTTP/2 では domain sharding を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="f2904-122">Do not use domain sharding with HTTP/2.</span></span>  
*   <span data-ttu-id="f2904-123">重要な要求が事前にダウンロードされるように、不要な要求を削除または保留します。</span><span class="sxs-lookup"><span data-stu-id="f2904-123">Remove or defer unnecessary requests so that critical requests download earlier.</span></span>  

## <span data-ttu-id="f2904-124">最初のバイトまでの時間が遅い (TTFB)</span><span class="sxs-lookup"><span data-stu-id="f2904-124">Slow Time To First Byte (TTFB)</span></span>   

### <span data-ttu-id="f2904-125">現象</span><span class="sxs-lookup"><span data-stu-id="f2904-125">Symptoms</span></span>  

<span data-ttu-id="f2904-126">要求は、サーバーから最初のバイトを受信するまでに長い時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="f2904-126">A request spends a long time waiting to receive the first byte from the server.</span></span>  

<span data-ttu-id="f2904-127">[図 2](#figure-2)の**ウォーターフォール**の長い緑色のバーは、要求が長時間待機していたことを示します。</span><span class="sxs-lookup"><span data-stu-id="f2904-127">In [Figure 2](#figure-2), the long, green bar in the **Waterfall** indicates that the request was waiting a long time.</span></span>  <span data-ttu-id="f2904-128">これは、ネットワークの速度を制限し、遅延を追加するためにプロファイルを使用してシミュレートされました。</span><span class="sxs-lookup"><span data-stu-id="f2904-128">This was simulated using a profile to restrict network speed and add a delay.</span></span>  

> ##### <span data-ttu-id="f2904-129">図 2</span><span class="sxs-lookup"><span data-stu-id="f2904-129">Figure 2</span></span>  
> <span data-ttu-id="f2904-130">最初のバイトまでの時間が遅い要求の例</span><span class="sxs-lookup"><span data-stu-id="f2904-130">An example of a request with a slow Time To First Byte</span></span>  
> ![最初のバイトまでの時間が遅い要求の例][ImageSlowTimeToFirstByte]  

### <span data-ttu-id="f2904-132">原因</span><span class="sxs-lookup"><span data-stu-id="f2904-132">Causes</span></span>  

*   <span data-ttu-id="f2904-133">クライアントとサーバー間の接続速度が遅い。</span><span class="sxs-lookup"><span data-stu-id="f2904-133">The connection between the client and server is slow.</span></span>  
*   <span data-ttu-id="f2904-134">サーバーの応答が遅くなります。</span><span class="sxs-lookup"><span data-stu-id="f2904-134">The server is slow to respond.</span></span>  <span data-ttu-id="f2904-135">サーバーをローカルにホストして、接続またはサーバーが低速であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f2904-135">Host the server locally to determine if it is the connection or server that is slow.</span></span>  <span data-ttu-id="f2904-136">ローカルサーバーにアクセスしようとしても、最初のバイト \ (TTFB \) に時間がかかる場合は、サーバーの速度が遅くなります。</span><span class="sxs-lookup"><span data-stu-id="f2904-136">If you still get a slow Time To First Byte \(TTFB\) when accessing a local server, then the server is slow.</span></span>  

### <span data-ttu-id="f2904-137">修正</span><span class="sxs-lookup"><span data-stu-id="f2904-137">Fixes</span></span>  

*   <span data-ttu-id="f2904-138">接続速度が遅い場合は、CDN でコンテンツをホストするか、ホスティングプロバイダーを変更することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="f2904-138">If the connection is slow, consider hosting your content on a CDN or changing hosting providers.</span></span>  
*   <span data-ttu-id="f2904-139">サーバーの速度が遅い場合は、データベースクエリの最適化、キャッシュの実装、またはサーバー構成の変更を検討してください。</span><span class="sxs-lookup"><span data-stu-id="f2904-139">If the server is slow, consider optimizing database queries, implementing a cache, or modifying your server configuration.</span></span>  

## <span data-ttu-id="f2904-140">コンテンツのダウンロードが遅い</span><span class="sxs-lookup"><span data-stu-id="f2904-140">Slow content download</span></span>   

### <span data-ttu-id="f2904-141">現象</span><span class="sxs-lookup"><span data-stu-id="f2904-141">Symptoms</span></span>  

<span data-ttu-id="f2904-142">リクエストのダウンロードには時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="f2904-142">A request takes a long time to download.</span></span>  

<span data-ttu-id="f2904-143">[図 3](#figure-3)の png の隣にある**ウォーターフォール**の長い青色のバーは、ダウンロードに時間がかかることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f2904-143">In [Figure 3](#figure-3), the long, blue bar in the **Waterfall** next to the png means it took a long time to download.</span></span>  

> ##### <span data-ttu-id="f2904-144">図 3</span><span class="sxs-lookup"><span data-stu-id="f2904-144">Figure 3</span></span>  
> <span data-ttu-id="f2904-145">ダウンロードに時間がかかる要求の例</span><span class="sxs-lookup"><span data-stu-id="f2904-145">An example of a request that takes a long time to download</span></span>  
> ![ダウンロードに時間がかかる要求の例][ImageSlowContentDownload]  

### <span data-ttu-id="f2904-147">原因</span><span class="sxs-lookup"><span data-stu-id="f2904-147">Causes</span></span>  

*   <span data-ttu-id="f2904-148">クライアントとサーバー間の接続速度が遅い。</span><span class="sxs-lookup"><span data-stu-id="f2904-148">The connection between the client and server is slow.</span></span>  
*   <span data-ttu-id="f2904-149">多くのコンテンツがダウンロードされています。</span><span class="sxs-lookup"><span data-stu-id="f2904-149">A lot of content is being downloaded.</span></span>  

### <span data-ttu-id="f2904-150">修正</span><span class="sxs-lookup"><span data-stu-id="f2904-150">Fixes</span></span>  

*   <span data-ttu-id="f2904-151">コンテンツを CDN でホストするか、ホスティングプロバイダーを変更することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="f2904-151">Consider hosting your content on a CDN or changing hosting providers.</span></span>  
*   <span data-ttu-id="f2904-152">要求を最適化して、送信するバイト数を減らします。</span><span class="sxs-lookup"><span data-stu-id="f2904-152">Send fewer bytes by optimizing your requests.</span></span>  

## <span data-ttu-id="f2904-153">知識の投稿</span><span class="sxs-lookup"><span data-stu-id="f2904-153">Contribute knowledge</span></span>  

<span data-ttu-id="f2904-154">このガイドに追加する必要があるネットワークの問題はありますか?</span><span class="sxs-lookup"><span data-stu-id="f2904-154">Do you have a network issue that should be added to this guide?</span></span>  

*   <span data-ttu-id="f2904-155">[@EdgeDevTools][MicrosoftEdgeTweet]にツイートを送信します。</span><span class="sxs-lookup"><span data-stu-id="f2904-155">Send a tweet to [@EdgeDevTools][MicrosoftEdgeTweet].</span></span>  
*   <span data-ttu-id="f2904-156">**Send Feedback** ![ ご意見・ご ][ImageSendFeedbackIcon] 感想や機能のリクエストについては、devtools で「フィードバックを送信」を選択するか、\ ( `Alt` + `Shift` + `I` Windows \) または `Option` + `Shift` + `I` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="f2904-156">Select **Send Feedback** ![Send Feedback][ImageSendFeedbackIcon] in the DevTools or press `Alt`+`Shift`+`I` \(Windows\) or `Option`+`Shift`+`I` \(macOS\) to provide feedback or feature requests.</span></span>  
*   <span data-ttu-id="f2904-157">Docs リポジトリで[問題を開き][WebFundamentalsIssue]ます。</span><span class="sxs-lookup"><span data-stu-id="f2904-157">[Open an issue][WebFundamentalsIssue] on the docs repo.</span></span>  

<!--   -->  



<!-- image links -->  

[ImageSendFeedbackIcon]: /microsoft-edge/devtools-guide-chromium/media/smile-icon.msft.png  

[ImageStalled]: /microsoft-edge/devtools-guide-chromium/media/network-network-disabled-cache-resources-queue.msft.png "図 1: [ネットワーク] パネルのキューにある、または停止しているシリーズの例"  
[ImageSlowTimeToFirstByte]: /microsoft-edge/devtools-guide-chromium/media/network-network-resources-using-dial-up-profile.msft.png "図 2: 最初のバイトに時間がかかる要求の例"  
[ImageSlowContentDownload]: /microsoft-edge/devtools-guide-chromium/media/network-network-resources-edge-devtools.msft.png "図 3: ダウンロードに時間がかかる要求の例"  

<!-- links -->  

[NetworkPerformance]: /microsoft-edge/devtools-guide-chromium/network/index "Microsoft Edge DevTools でネットワークアクティビティを検査する"  

[MicrosoftEdgeTweet]: https://twitter.com/intent/tweet?text=@EdgeDevTools%20[Network%20Issues%20Guide%20Suggestion]  

[WebFundamentalsIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Network%20Issues%20Guide%20Suggestion%5D "新しい問題-Microsoft のドキュメント/エッジ-開発者"  

> [!NOTE]
> <span data-ttu-id="f2904-163">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="f2904-163">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f2904-164">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/network/issues)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) および[Jonathan Garbee][JonathanGarbee] \ (Google Developer Expert for Web テクノロジ \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="f2904-164">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/issues) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Jonathan Garbee][JonathanGarbee] \(Google Developer Expert for Web Technology\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="f2904-166">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="f2904-166">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[JonathanGarbee]: https://developers.google.com/web/resources/contributors/jonathangarbee
