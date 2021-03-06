---
description: 開発マシン Web サーバーでサイトをホストし、Android デバイスからコンテンツにアクセスします。
title: ローカル サーバーにアクセスする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 16c9927ce4548d71681d35e643aea0a6c44ec75a
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398211"
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

# <a name="access-local-servers"></a><span data-ttu-id="3ee1e-104">ローカル サーバーにアクセスする</span><span class="sxs-lookup"><span data-stu-id="3ee1e-104">Access local servers</span></span>  

<span data-ttu-id="3ee1e-105">開発マシン Web サーバーでサイトをホストし、Android デバイスからコンテンツにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-105">Host a site on a development machine web server, then access the content from an Android device.</span></span>  

<span data-ttu-id="3ee1e-106">USB ケーブルと Microsoft Edge DevTools を使用して、開発マシンからサイトを実行し、Android デバイスでサイトを表示します。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-106">With a USB cable and Microsoft Edge DevTools, run a site from a development machine and then view the site on an Android device.</span></span>  

### <a name="summary"></a><span data-ttu-id="3ee1e-107">要約</span><span class="sxs-lookup"><span data-stu-id="3ee1e-107">Summary</span></span>  

*   <span data-ttu-id="3ee1e-108">ポート転送を使用すると、Android デバイス上の開発マシンで実行されている Web サーバーによってホストされるコンテンツを表示できます。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-108">Port forwarding enables you to view content hosted by the web server running in your development machine on your Android device.</span></span>  
*   <span data-ttu-id="3ee1e-109">Web サーバーがカスタム ドメインを使用している場合は、カスタム ドメイン マッピングを使用してそのドメインのコンテンツにアクセスする Android デバイスをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-109">If your web server is using a custom domain, set up your Android device to access the content at that domain with custom domain mapping.</span></span>  

## <a name="set-up-port-forwarding"></a><span data-ttu-id="3ee1e-110">ポート転送のセットアップ</span><span class="sxs-lookup"><span data-stu-id="3ee1e-110">Set up port forwarding</span></span>  

<span data-ttu-id="3ee1e-111">ポート転送を使用すると、開発マシンで実行されている Web サーバーでホストされているコンテンツに Android デバイスがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-111">Port forwarding enables your Android device to access content that is being hosted on the web server running in your development machine.</span></span>  <span data-ttu-id="3ee1e-112">ポート転送は、開発マシン上の TCP ポートにマップするリッスン TCP ポートを Android デバイスに作成することで動作します。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-112">Port forwarding works by creating a listening TCP port on your Android device that maps to a TCP port on your development machine.</span></span>  <span data-ttu-id="3ee1e-113">ポート間のトラフィックは、Android デバイスと開発マシン間の USB 接続を介して移動します。そのため、接続はネットワーク構成に依存しません。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-113">Traffic between the ports travel through the USB connection between your Android device and development machine, so the connection does not depend on your network configuration.</span></span>  

<span data-ttu-id="3ee1e-114">ポート転送を有効にするには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-114">To enable port forwarding:</span></span>  

1.  <span data-ttu-id="3ee1e-115">開発マシン [と Android デバイス][RemoteDebuggingGettingStarted] の間でリモート デバッグをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-115">Set up [remote debugging][RemoteDebuggingGettingStarted] between your development machine and your Android device.</span></span>  <span data-ttu-id="3ee1e-116">完了したら、[デバイスの検査] ダイアログボックスの左側のメニューと [接続済み\*\*\*\* 状態] インジケーターに Android デバイス**が**表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-116">When you are finished, your Android device should be displayed in the left-hand menu of the **Inspect Devices** dialog and a **Connected** status indicator.</span></span>  
1.  <span data-ttu-id="3ee1e-117">DevTools **の [デバイスの** 検査] ダイアログで、[ポート転送] **を有効にします**。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-117">In the **Inspect Devices** dialog in DevTools, enable **Port forwarding**.</span></span>  
1.  <span data-ttu-id="3ee1e-118">[ルール **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-118">Choose **Add rule**.</span></span>  
    
    :::image type="complex" source="../media/remote-debugging-remote-devices-devices-port-forwarding-add-rule.msft.png" alt-text="ポート転送ルールの追加" lightbox="../media/remote-debugging-remote-devices-devices-port-forwarding-add-rule.msft.png":::
       <span data-ttu-id="3ee1e-120">ポート転送ルールの追加</span><span class="sxs-lookup"><span data-stu-id="3ee1e-120">Adding a port forwarding rule</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3ee1e-121">左側の **[デバイス ポート** ] テキスト ボックスに、Android デバイス上のサイトにアクセスできるポート番号 `localhost` を入力します。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-121">In the **Device port** textbox on the left, enter the `localhost` port number from which you want to be able to access the site on your Android device.</span></span>  <span data-ttu-id="3ee1e-122">たとえば、Enter からサイトにアクセスする場合 `localhost:5000` `5000` です。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-122">For example, if you wanted to access the site from `localhost:5000` enter `5000`.</span></span>  
1.  <span data-ttu-id="3ee1e-123">右側の **[ローカル アドレス** ] テキスト ボックスに、開発マシンで実行されている Web サーバーでサイトがホストされている IP アドレスまたはホスト名を入力し、その後にポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-123">In the **Local address** textbox on the right, enter the IP address or hostname on which your site is hosted on the web server running in your development machine, followed by the port number.</span></span>  <span data-ttu-id="3ee1e-124">たとえば、サイトが Enter で実行されている `localhost:7331` 場合 `localhost:7331` です。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-124">For example, if your site is running on `localhost:7331` enter `localhost:7331`.</span></span>  
1.  <span data-ttu-id="3ee1e-125">**追加** を選びます。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-125">Choose **Add**.</span></span>  
    
<span data-ttu-id="3ee1e-126">ポート転送がセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-126">Port forwarding is now set up.</span></span>  <span data-ttu-id="3ee1e-127">[デバイスの検査] ダイアログボックス内のデバイスのタブで、ポート転送の状態インジケーター **を確認** します。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-127">Review the status indicator for the port forward on the tab on your device within the **Inspect Devices** dialog.</span></span>  

:::image type="complex" source="../media/remote-debugging-remote-devices-devices-port-forwarding-5000-edge-user-agent.msft.png" alt-text="ポート転送の状態" lightbox="../media/remote-debugging-remote-devices-devices-port-forwarding-5000-edge-user-agent.msft.png":::
   <span data-ttu-id="3ee1e-129">ポート転送の状態</span><span class="sxs-lookup"><span data-stu-id="3ee1e-129">Port forwarding status</span></span>  
:::image-end:::  

<span data-ttu-id="3ee1e-130">コンテンツを表示するには、Android デバイスで Microsoft Edge を開き、[デバイス ポート] フィールドで指定したポート `localhost` **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-130">To view the content, open up Microsoft Edge on your Android device and go to the `localhost` port that you specified in the **Device port** field.</span></span>  <span data-ttu-id="3ee1e-131">たとえば、フィールドに入力した `5000` 場合は、 を参照してください `localhost:5000` 。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-131">For example, if you entered `5000` in the field, visit `localhost:5000`.</span></span>  

## <a name="map-to-custom-local-domains"></a><span data-ttu-id="3ee1e-132">カスタム ローカル ドメインへのマップ</span><span class="sxs-lookup"><span data-stu-id="3ee1e-132">Map to custom local domains</span></span>  

<span data-ttu-id="3ee1e-133">カスタム ドメイン マッピングを使用すると、カスタム ドメインを使用している開発マシン上の Web サーバーから Android デバイス上のコンテンツを表示できます。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-133">Custom domain mapping enables you to view content on an Android device from a web server on your development machine that is using a custom domain.</span></span>  

<span data-ttu-id="3ee1e-134">たとえば、サイトがドメインでのみ動作するサードパーティの JavaScript ライブラリを使用するとします `microsoft-edge.devtools` 。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-134">For example, suppose that your site uses a third-party JavaScript library that only works on the domain `microsoft-edge.devtools`.</span></span>  <span data-ttu-id="3ee1e-135">そのため、開発マシン上のファイルにエントリを作成して、このドメインを `hosts` `localhost` \(たとえば\) にマップ `127.0.0.1 microsoft-edge.devtools` します。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-135">So, you create an entry in your `hosts` file on your development machine to map this domain to `localhost` \(for example, `127.0.0.1 microsoft-edge.devtools`\).</span></span>  <span data-ttu-id="3ee1e-136">カスタム ドメイン マッピングとポート転送を設定した後、URL で Android デバイス上のサイトを表示します `microsoft-edge.devtools` 。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-136">After setting up custom domain mapping and port forwarding, view the site on your Android device at the URL `microsoft-edge.devtools`.</span></span>  

### <a name="set-up-port-forwarding-to-proxy-server"></a><span data-ttu-id="3ee1e-137">プロキシ サーバーへのポート転送のセットアップ</span><span class="sxs-lookup"><span data-stu-id="3ee1e-137">Set up port forwarding to proxy server</span></span>  

<span data-ttu-id="3ee1e-138">カスタム ドメインをマップするには、開発マシンでプロキシ サーバーを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-138">To map a custom domain you must run a proxy server on your development machine.</span></span>  <span data-ttu-id="3ee1e-139">プロキシ サーバーの例は[、Charles、Squid、][CharlesWebDebuggingProxy][および Fiddler です][FiddlerWebDebuggingProxy]。 [][SquidOptimisingWebDelivery]</span><span class="sxs-lookup"><span data-stu-id="3ee1e-139">Examples of proxy servers are [Charles][CharlesWebDebuggingProxy], [Squid][SquidOptimisingWebDelivery], and [Fiddler][FiddlerWebDebuggingProxy].</span></span>  

<span data-ttu-id="3ee1e-140">プロキシへのポート転送を設定するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-140">To set up port forwarding to a proxy:</span></span>  

1.  <span data-ttu-id="3ee1e-141">プロキシ サーバーを実行し、使用しているポートを記録します。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-141">Run the proxy server and record the port that it is using.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="3ee1e-142">プロキシ サーバーと Web サーバーは、異なるポートで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-142">The proxy server and your web server must run on different ports.</span></span>  
    
1.  <span data-ttu-id="3ee1e-143">Android デバイス [へのポート転送](#set-up-port-forwarding) を設定します。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-143">Set up [port forwarding](#set-up-port-forwarding) to your Android device.</span></span>  <span data-ttu-id="3ee1e-144">[ローカル **アドレス] フィールド** に、プロキシ サーバーが `localhost:` 実行されているポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-144">For the **local address** field, enter `localhost:` followed by the port that your proxy server is running on.</span></span>  <span data-ttu-id="3ee1e-145">たとえば、ポートで実行されている場合は `8000` 、 に移動します `localhost:8000` 。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-145">For example, if it is running on port `8000`, navigate to `localhost:8000`.</span></span>  <span data-ttu-id="3ee1e-146">[デバイス **ポート]** フィールドに、Android デバイスでリッスンする番号 (など) を入力します `3333` 。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-146">In the **device port** field enter the number that you want your Android device to listen on, such as `3333`.</span></span>  
    
### <a name="configure-proxy-settings-on-your-device"></a><span data-ttu-id="3ee1e-147">デバイスでプロキシ設定を構成する</span><span class="sxs-lookup"><span data-stu-id="3ee1e-147">Configure proxy settings on your device</span></span>  

<span data-ttu-id="3ee1e-148">次に、プロキシ サーバーと通信するために Android デバイスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-148">Next, you need to configure your Android device to communicate with the proxy server.</span></span>  

1.  <span data-ttu-id="3ee1e-149">Android デバイスで、[設定] \*\*\*\*  >  **Wi-Fi に移動します**。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-149">On your Android device, navigate to **Settings** > **Wi-Fi**.</span></span>  
1.  <span data-ttu-id="3ee1e-150">現在接続しているネットワークの名前を長押しします。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-150">Long-press the name of the network to which you are currently connected.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="3ee1e-151">プロキシ設定はネットワークごとに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-151">Proxy settings apply per network.</span></span>  
    
1.  <span data-ttu-id="3ee1e-152">[ネットワーク **の変更] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-152">Choose **Modify network**.</span></span>  
1.  <span data-ttu-id="3ee1e-153">[詳細設定 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-153">Choose **Advanced options**.</span></span>  <span data-ttu-id="3ee1e-154">プロキシ設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-154">The proxy settings display.</span></span>  
1.  <span data-ttu-id="3ee1e-155">[プロキシ] **メニューを選択** し、[手動] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-155">Choose the **Proxy** menu and choose **Manual**.</span></span>  
1.  <span data-ttu-id="3ee1e-156">[プロキシの **ホスト名] フィールド** に「 」 と入力 `localhost` します。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-156">For the **Proxy hostname** field, enter `localhost`.</span></span>  
1.  <span data-ttu-id="3ee1e-157">[プロキシ **ポート] フィールド** に、前のセクションでデバイス ポートに入力した **ポート番号** を入力します。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-157">For the **Proxy port** field, enter the port number that you entered for **device port** in the previous section.</span></span>  
1.  <span data-ttu-id="3ee1e-158">[保存 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-158">Choose **Save**.</span></span>  
    
<span data-ttu-id="3ee1e-159">これらの設定を使用すると、デバイスは、すべての要求を開発マシン上のプロキシに転送します。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-159">With these settings, your device forwards all of its requests to the proxy on your development machine.</span></span>  <span data-ttu-id="3ee1e-160">プロキシはデバイスに代わって要求を行うので、カスタマイズしたローカル ドメインへの要求は適切に解決されます。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-160">The proxy makes requests on behalf of your device, so requests to your customized local domain are properly resolved.</span></span>  

<span data-ttu-id="3ee1e-161">開発マシンと同様に、Android デバイス上のカスタム ドメインにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-161">Now access custom domains on your Android device just like on the development machine.</span></span>  

<span data-ttu-id="3ee1e-162">Web サーバーが標準以外のポートから実行されている場合は、Android デバイスからコンテンツを要求するときにポートを指定してください。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-162">If your web server is running off of a non-standard port, remember to specify the port when requesting the content from your Android device.</span></span>  <span data-ttu-id="3ee1e-163">たとえば、Web サーバーがポートでカスタム ドメインを使用している場合、Android デバイスからサイトを表示するときに `microsoft-edge.devtools` `7331` URL を使用する必要があります `microsoft-edge.devtools:7331` 。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-163">For example, if your web server is using the custom domain `microsoft-edge.devtools` on port `7331`, when you view the site from your Android device you should be using the URL `microsoft-edge.devtools:7331`.</span></span>  

> [!TIP]
> <span data-ttu-id="3ee1e-164">通常の閲覧を再開するには、開発マシンから切断した後、Android デバイスのプロキシ設定を元に戻してください。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-164">To resume normal browsing, remember to revert the proxy settings on your Android device after you disconnect from the development machine.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="3ee1e-165">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="3ee1e-165">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[RemoteDebuggingGettingStarted]: ./index.md "Android デバイスのリモート デバッグの開始|Microsoft Docs"  

[CharlesWebDebuggingProxy]: https://www.charlesproxy.com "Charles Web デバッグ プロキシ"  

[SquidOptimisingWebDelivery]: https://www.squid-cache.org "squid : Web 配信の最適化"  

[FiddlerWebDebuggingProxy]: https://www.telerik.com/fiddler "Fiddler - 無料の Web デバッグ プロキシ"  

> [!NOTE]
> <span data-ttu-id="3ee1e-170">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-170">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="3ee1e-171">元のページはここで[](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/local-server)見つかり[、Kayce バス][KayceBasques]ク人 \(Technical Writer, Chrome DevTools \& ライトハウス\) と[Meggin Kearney][MegginKearney] \(Tech Writer\) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-171">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/local-server) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="3ee1e-173">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="3ee1e-173">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
