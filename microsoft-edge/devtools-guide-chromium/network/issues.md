---
title: ネットワーク問題ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: a9a3234f3516bef16328102858363ffcb06251ec
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10985389"
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





# <span data-ttu-id="fd37a-103">ネットワークの問題に関するガイド</span><span class="sxs-lookup"><span data-stu-id="fd37a-103">Network issues guide</span></span>   




<span data-ttu-id="fd37a-104">このガイドでは、Microsoft Edge DevTools のネットワークパネルでネットワークの問題や最適化の機会を検出する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fd37a-104">This guide shows you how to detect network issues or optimization opportunities in the Network panel of Microsoft Edge DevTools.</span></span>  

<span data-ttu-id="fd37a-105">詳しく [は、「][NetworkPerformance] **ネットワーク** パネルの基本」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fd37a-105">See [Get Started][NetworkPerformance] to learn the basics of the **Network** panel.</span></span>  

## <span data-ttu-id="fd37a-106">キューに入っているまたは停止している要求</span><span class="sxs-lookup"><span data-stu-id="fd37a-106">Queued or stalled requests</span></span>   

**<span data-ttu-id="fd37a-107">現象</span><span class="sxs-lookup"><span data-stu-id="fd37a-107">Symptoms</span></span>**  

<span data-ttu-id="fd37a-108">6つの要求が同時にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="fd37a-108">Six requests are downloading simultaneously.</span></span>  <span data-ttu-id="fd37a-109">その後、一連の要求はキューまたは停止されます。</span><span class="sxs-lookup"><span data-stu-id="fd37a-109">After that, a series of requests are queued or stalled.</span></span>  <span data-ttu-id="fd37a-110">最初の6つの要求のいずれかが完了したら、キュー内のいずれかの要求が開始されます。</span><span class="sxs-lookup"><span data-stu-id="fd37a-110">Once one of the first six requests finishes, one of the requests in the queue starts.</span></span>  

<span data-ttu-id="fd37a-111">次の図の **ウォーターフォール** では、資産の最初の6つの要求が同時に開始され `edge-iconx1024.msft.png` ます。</span><span class="sxs-lookup"><span data-stu-id="fd37a-111">In the **Waterfall** in the following figure, the first six requests for the `edge-iconx1024.msft.png` asset start simultaneously.</span></span>  <span data-ttu-id="fd37a-112">それ以降の要求は、元の6つの処理が完了するまで停止します。</span><span class="sxs-lookup"><span data-stu-id="fd37a-112">The subsequent requests are stalled until one of the original six finishes.</span></span>  

:::image type="complex" source="../media/network-network-disabled-cache-resources-queue.msft.png" alt-text="[ネットワーク] パネルのキューに入っている、または停止しているシリーズの例" lightbox="../media/network-network-disabled-cache-resources-queue.msft.png":::
   <span data-ttu-id="fd37a-114">[ **ネットワーク** ] パネルのキューに入っている、または停止しているシリーズの例</span><span class="sxs-lookup"><span data-stu-id="fd37a-114">An example of a queued or stalled series in the **Network** panel</span></span>  
:::image-end:::  

**<span data-ttu-id="fd37a-115">原因</span><span class="sxs-lookup"><span data-stu-id="fd37a-115">Causes</span></span>**  

<span data-ttu-id="fd37a-116">1つのドメインで実行されている要求が多すぎます。</span><span class="sxs-lookup"><span data-stu-id="fd37a-116">Too many requests are being made on a single domain.</span></span>  <span data-ttu-id="fd37a-117">HTTP/1.0 または HTTP/1.1 接続の場合、Microsoft Edge では、ホストあたり最大6つの同時 TCP 接続を許可します。</span><span class="sxs-lookup"><span data-stu-id="fd37a-117">On HTTP/1.0 or HTTP/1.1 connections, Microsoft Edge allows a maximum of six simultaneous TCP connections per host.</span></span>  

**<span data-ttu-id="fd37a-118">修正</span><span class="sxs-lookup"><span data-stu-id="fd37a-118">Fixes</span></span>**  

*   <span data-ttu-id="fd37a-119">HTTP/1.0 または HTTP/1.1 を使用する必要がある場合は、ドメイン sharding を実装します。</span><span class="sxs-lookup"><span data-stu-id="fd37a-119">Implement domain sharding if you must use HTTP/1.0 or HTTP/1.1.</span></span>  
*   <span data-ttu-id="fd37a-120">HTTP/2 を使用します。</span><span class="sxs-lookup"><span data-stu-id="fd37a-120">Use HTTP/2.</span></span>  <span data-ttu-id="fd37a-121">HTTP/2 では domain sharding を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="fd37a-121">Do not use domain sharding with HTTP/2.</span></span>  
*   <span data-ttu-id="fd37a-122">重要な要求が事前にダウンロードされるように、不要な要求を削除または保留します。</span><span class="sxs-lookup"><span data-stu-id="fd37a-122">Remove or defer unnecessary requests so that critical requests download earlier.</span></span>  
    
## <span data-ttu-id="fd37a-123">最初のバイトまでの時間が遅い (TTFB)</span><span class="sxs-lookup"><span data-stu-id="fd37a-123">Slow Time To First Byte (TTFB)</span></span>   

**<span data-ttu-id="fd37a-124">現象</span><span class="sxs-lookup"><span data-stu-id="fd37a-124">Symptoms</span></span>**  

<span data-ttu-id="fd37a-125">要求は、サーバーから最初のバイトを受信するまでに長い時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="fd37a-125">A request spends a long time waiting to receive the first byte from the server.</span></span>  

<span data-ttu-id="fd37a-126">次の図では、 **ウォーターフォール** の長い緑色のバーは、要求が長い時間待機していたことを示します。</span><span class="sxs-lookup"><span data-stu-id="fd37a-126">In the following figure, the long, green bar in the **Waterfall** indicates that the request was waiting a long time.</span></span>  <span data-ttu-id="fd37a-127">これは、ネットワークの速度を制限し、遅延を追加するためにプロファイルを使用してシミュレートされました。</span><span class="sxs-lookup"><span data-stu-id="fd37a-127">This was simulated using a profile to restrict network speed and add a delay.</span></span>  

:::image type="complex" source="../media/network-network-resources-using-dial-up-profile.msft.png" alt-text="最初のバイトまでの時間が遅い要求の例" lightbox="../media/network-network-resources-using-dial-up-profile.msft.png":::
   <span data-ttu-id="fd37a-129">最初のバイトまでの時間が遅い要求の例</span><span class="sxs-lookup"><span data-stu-id="fd37a-129">An example of a request with a slow Time To First Byte</span></span>  
:::image-end:::  

**<span data-ttu-id="fd37a-130">原因</span><span class="sxs-lookup"><span data-stu-id="fd37a-130">Causes</span></span>**  

*   <span data-ttu-id="fd37a-131">クライアントとサーバー間の接続速度が遅い。</span><span class="sxs-lookup"><span data-stu-id="fd37a-131">The connection between the client and server is slow.</span></span>  
*   <span data-ttu-id="fd37a-132">サーバーの応答が遅くなります。</span><span class="sxs-lookup"><span data-stu-id="fd37a-132">The server is slow to respond.</span></span>  <span data-ttu-id="fd37a-133">サーバーをローカルにホストして、接続またはサーバーが低速であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="fd37a-133">Host the server locally to determine if it is the connection or server that is slow.</span></span>  <span data-ttu-id="fd37a-134">ローカルサーバーにアクセスしようとしても、最初のバイト \ (TTFB \) に時間がかかる場合は、サーバーの速度が遅くなります。</span><span class="sxs-lookup"><span data-stu-id="fd37a-134">If you still get a slow Time To First Byte \(TTFB\) when accessing a local server, then the server is slow.</span></span>  
    
**<span data-ttu-id="fd37a-135">修正</span><span class="sxs-lookup"><span data-stu-id="fd37a-135">Fixes</span></span>**  

*   <span data-ttu-id="fd37a-136">接続速度が遅い場合は、CDN でコンテンツをホストするか、ホスティングプロバイダーを変更することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="fd37a-136">If the connection is slow, consider hosting your content on a CDN or changing hosting providers.</span></span>  
*   <span data-ttu-id="fd37a-137">サーバーの速度が遅い場合は、データベースクエリの最適化、キャッシュの実装、またはサーバー構成の変更を検討してください。</span><span class="sxs-lookup"><span data-stu-id="fd37a-137">If the server is slow, consider optimizing database queries, implementing a cache, or modifying your server configuration.</span></span>  
    
## <span data-ttu-id="fd37a-138">コンテンツのダウンロードが遅い</span><span class="sxs-lookup"><span data-stu-id="fd37a-138">Slow content download</span></span>   

**<span data-ttu-id="fd37a-139">現象</span><span class="sxs-lookup"><span data-stu-id="fd37a-139">Symptoms</span></span>**  

<span data-ttu-id="fd37a-140">リクエストのダウンロードには時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="fd37a-140">A request takes a long time to download.</span></span>  

<span data-ttu-id="fd37a-141">次の図では、png の隣にある **ウォーターフォール** の長い青色のバーは、ダウンロードに時間がかかることを意味します。</span><span class="sxs-lookup"><span data-stu-id="fd37a-141">In the following figure, the long, blue bar in the **Waterfall** next to the png means it took a long time to download.</span></span>  

:::image type="complex" source="../media/network-network-resources-edge-devtools.msft.png" alt-text="ダウンロードに時間がかかる要求の例" lightbox="../media/network-network-resources-edge-devtools.msft.png":::
   <span data-ttu-id="fd37a-143">ダウンロードに時間がかかる要求の例</span><span class="sxs-lookup"><span data-stu-id="fd37a-143">An example of a request that takes a long time to download</span></span>  
:::image-end:::  

**<span data-ttu-id="fd37a-144">原因</span><span class="sxs-lookup"><span data-stu-id="fd37a-144">Causes</span></span>**  

*   <span data-ttu-id="fd37a-145">クライアントとサーバー間の接続速度が遅い。</span><span class="sxs-lookup"><span data-stu-id="fd37a-145">The connection between the client and server is slow.</span></span>  
*   <span data-ttu-id="fd37a-146">多くのコンテンツがダウンロードされています。</span><span class="sxs-lookup"><span data-stu-id="fd37a-146">A lot of content is being downloaded.</span></span>  
    
**<span data-ttu-id="fd37a-147">修正</span><span class="sxs-lookup"><span data-stu-id="fd37a-147">Fixes</span></span>**  

*   <span data-ttu-id="fd37a-148">コンテンツを CDN でホストするか、ホスティングプロバイダーを変更することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="fd37a-148">Consider hosting your content on a CDN or changing hosting providers.</span></span>  
*   <span data-ttu-id="fd37a-149">要求を最適化して、送信するバイト数を減らします。</span><span class="sxs-lookup"><span data-stu-id="fd37a-149">Send fewer bytes by optimizing your requests.</span></span>  
    
## <span data-ttu-id="fd37a-150">知識の投稿</span><span class="sxs-lookup"><span data-stu-id="fd37a-150">Contribute knowledge</span></span>  

<span data-ttu-id="fd37a-151">このガイドに追加する必要があるネットワークの問題はありますか?</span><span class="sxs-lookup"><span data-stu-id="fd37a-151">Do you have a network issue that should be added to this guide?</span></span>  

*   <span data-ttu-id="fd37a-152">[@EdgeDevTools][MicrosoftEdgeTweet]にツイートを送信します。</span><span class="sxs-lookup"><span data-stu-id="fd37a-152">Send a tweet to [@EdgeDevTools][MicrosoftEdgeTweet].</span></span>  
*   <span data-ttu-id="fd37a-153">**Send Feedback** ![ ][ImageSendFeedbackIcon] フィードバックや機能のリクエストについては、devtools で [フィードバックの送信 \ (フィードバックを送信 \)] または [\ (Windows \)] または [ `Alt` + `Shift` + `I` `Option` + `Shift` + `I` \ (macOS \)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd37a-153">Select **Send Feedback** \(![Send Feedback][ImageSendFeedbackIcon]\) in the DevTools or press `Alt`+`Shift`+`I` \(Windows\) or `Option`+`Shift`+`I` \(macOS\) to provide feedback or feature requests.</span></span>  
*   <span data-ttu-id="fd37a-154">Docs リポジトリで[問題を開き][WebFundamentalsIssue]ます。</span><span class="sxs-lookup"><span data-stu-id="fd37a-154">[Open an issue][WebFundamentalsIssue] on the docs repo.</span></span>  
    
<!--  
  


-->  

<!-- image links -->  

[ImageSendFeedbackIcon]: ../media/smile-icon.msft.png  

<!-- links -->  

[NetworkPerformance]: ./index.md "Microsoft Edge DevTools でネットワークアクティビティを検査する |Microsoft ドキュメント"  

[MicrosoftEdgeTweet]: https://twitter.com/intent/tweet?text=@EdgeDevTools%20[Network%20Issues%20Guide%20Suggestion]  

[WebFundamentalsIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Network%20Issues%20Guide%20Suggestion%5D "新しい問題-Microsoft のドキュメント/エッジ-開発者"  

> [!NOTE]
> <span data-ttu-id="fd37a-157">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="fd37a-157">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="fd37a-158">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/network/issues) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) および [Jonathan Garbee][JonathanGarbee] \ (Google Developer Expert for Web テクノロジ \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="fd37a-158">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/issues) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Jonathan Garbee][JonathanGarbee] \(Google Developer Expert for Web Technology\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="fd37a-160">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="fd37a-160">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[JonathanGarbee]: https://developers.google.com/web/resources/contributors/jonathangarbee
