---
description: 開発用コンピューターの web サーバーでサイトをホストし、Android デバイスからコンテンツにアクセスします。
title: ローカル サーバーにアクセスする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: f994092460f090743119d7304bfe12aa28556b19
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125413"
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

# <span data-ttu-id="3d578-104">ローカル サーバーにアクセスする</span><span class="sxs-lookup"><span data-stu-id="3d578-104">Access local servers</span></span>  

<span data-ttu-id="3d578-105">開発用コンピューターの web サーバーでサイトをホストし、Android デバイスからコンテンツにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3d578-105">Host a site on a development machine web server, then access the content from an Android device.</span></span>  

<span data-ttu-id="3d578-106">USB ケーブルと Microsoft Edge DevTools を使用して、開発用コンピューターからサイトを実行し、Android デバイスでサイトを表示します。</span><span class="sxs-lookup"><span data-stu-id="3d578-106">With a USB cable and Microsoft Edge DevTools, run a site from a development machine and then view the site on an Android device.</span></span>  

### <span data-ttu-id="3d578-107">まとめ</span><span class="sxs-lookup"><span data-stu-id="3d578-107">Summary</span></span>  

*   <span data-ttu-id="3d578-108">ポート転送を使用すると、開発用コンピューターで実行されている web サーバーによってホストされているコンテンツを Android デバイスで表示することができます。</span><span class="sxs-lookup"><span data-stu-id="3d578-108">Port forwarding enables you to view content hosted by the web server running in your development machine on your Android device.</span></span>  
*   <span data-ttu-id="3d578-109">Web サーバーでカスタムドメインを使用している場合は、カスタムドメインマッピングを使って、そのドメインのコンテンツにアクセスできるように Android デバイスをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="3d578-109">If your web server is using a custom domain, set up your Android device to access the content at that domain with custom domain mapping.</span></span>  

## <span data-ttu-id="3d578-110">ポート転送を設定する</span><span class="sxs-lookup"><span data-stu-id="3d578-110">Set up port forwarding</span></span>  

<span data-ttu-id="3d578-111">ポート転送を使用すると、Android デバイスは、開発用コンピューターで実行されている web サーバーでホストされているコンテンツにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3d578-111">Port forwarding enables your Android device to access content that is being hosted on the web server running in your development machine.</span></span>  <span data-ttu-id="3d578-112">ポート転送は、開発用コンピューターの TCP ポートにマップされている、Android デバイスでリスニング TCP ポートを作成することによって機能します。</span><span class="sxs-lookup"><span data-stu-id="3d578-112">Port forwarding works by creating a listening TCP port on your Android device that maps to a TCP port on your development machine.</span></span>  <span data-ttu-id="3d578-113">ポート間のトラフィックは、Android デバイスと開発マシン間の USB 接続を通じて移動するため、接続はネットワーク構成に依存しません。</span><span class="sxs-lookup"><span data-stu-id="3d578-113">Traffic between the ports travel through the USB connection between your Android device and development machine, so the connection does not depend on your network configuration.</span></span>  

<span data-ttu-id="3d578-114">ポート転送を有効にするには:</span><span class="sxs-lookup"><span data-stu-id="3d578-114">To enable port forwarding:</span></span>  

1.  <span data-ttu-id="3d578-115">開発用コンピューターと Android デバイスの間で [リモートデバッグ][RemoteDebuggingGettingStarted] をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="3d578-115">Set up [remote debugging][RemoteDebuggingGettingStarted] between your development machine and your Android device.</span></span>  <span data-ttu-id="3d578-116">完了すると、[ **デバイスの検査** ] ダイアログボックスと [ **接続** 状態] インジケーターの左側のメニューに Android デバイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d578-116">When you are finished, you should see your Android device in the left-hand menu of the **Inspect Devices** dialog and a **Connected** status indicator.</span></span>  
1.  <span data-ttu-id="3d578-117">DevTools の [ **デバイスの検査** ] ダイアログで、 **ポート転送**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3d578-117">In the **Inspect Devices** dialog in DevTools, enable **Port forwarding**.</span></span>  
1.  <span data-ttu-id="3d578-118">[ **ルールの追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3d578-118">Choose **Add rule**.</span></span>  
    
    :::image type="complex" source="../media/remote-debugging-remote-devices-devices-port-forwarding-add-rule.msft.png" alt-text="ポート転送ルールを追加する" lightbox="../media/remote-debugging-remote-devices-devices-port-forwarding-add-rule.msft.png":::
       <span data-ttu-id="3d578-120">ポート転送ルールを追加する</span><span class="sxs-lookup"><span data-stu-id="3d578-120">Adding a port forwarding rule</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3d578-121">左側の [ **デバイスポート** ] ボックスに、 `localhost` Android デバイスでサイトにアクセスできるようにするポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="3d578-121">In the **Device port** textbox on the left, enter the `localhost` port number from which you want to be able to access the site on your Android device.</span></span>  <span data-ttu-id="3d578-122">たとえば、enter からサイトにアクセスする必要があるとし `localhost:5000` `5000` ます。</span><span class="sxs-lookup"><span data-stu-id="3d578-122">For example, if you wanted to access the site from `localhost:5000` enter `5000`.</span></span>  
1.  <span data-ttu-id="3d578-123">右側の [ **ローカルアドレス** ] ボックスに、開発用コンピューターで実行されている web サーバーでサイトがホストされる IP アドレスまたはホスト名を入力し、その後にポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="3d578-123">In the **Local address** textbox on the right, enter the IP address or hostname on which your site is hosted on the web server running in your development machine, followed by the port number.</span></span>  <span data-ttu-id="3d578-124">たとえば、サイトが enter で実行されている場合です `localhost:7331` `localhost:7331` 。</span><span class="sxs-lookup"><span data-stu-id="3d578-124">For example, if your site is running on `localhost:7331` enter `localhost:7331`.</span></span>  
1.  <span data-ttu-id="3d578-125">[ **追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3d578-125">Choose **Add**.</span></span>  
    
<span data-ttu-id="3d578-126">ポート転送が設定されました。</span><span class="sxs-lookup"><span data-stu-id="3d578-126">Port forwarding is now set up.</span></span>  <span data-ttu-id="3d578-127">[ **デバイスの検査** ] ダイアログボックスで、デバイスのタブの [ポートフォワード] のステータスインジケーターを確認します。</span><span class="sxs-lookup"><span data-stu-id="3d578-127">See the status indicator for the port forward on the tab on your device within the **Inspect Devices** dialog.</span></span>  

:::image type="complex" source="../media/remote-debugging-remote-devices-devices-port-forwarding-5000-edge-user-agent.msft.png" alt-text="ポート転送ルールを追加する" lightbox="../media/remote-debugging-remote-devices-devices-port-forwarding-5000-edge-user-agent.msft.png":::
   <span data-ttu-id="3d578-129">ポート転送の状態</span><span class="sxs-lookup"><span data-stu-id="3d578-129">Port forwarding status</span></span>  
:::image-end:::  

<span data-ttu-id="3d578-130">コンテンツを表示するには、Android デバイスで Microsoft Edge を開き、[ `localhost` **デバイスポート** ] フィールドに指定したポートに移動します。</span><span class="sxs-lookup"><span data-stu-id="3d578-130">To view the content, open up Microsoft Edge on your Android device and go to the `localhost` port that you specified in the **Device port** field.</span></span>  <span data-ttu-id="3d578-131">たとえば、フィールドに入力した場合は、に `5000` アクセス `localhost:5000` します。</span><span class="sxs-lookup"><span data-stu-id="3d578-131">For example, if you entered `5000` in the field, visit `localhost:5000`.</span></span>  

## <span data-ttu-id="3d578-132">カスタムのローカルドメインにマップする</span><span class="sxs-lookup"><span data-stu-id="3d578-132">Map to custom local domains</span></span>  

<span data-ttu-id="3d578-133">カスタムドメインマッピングを使用すると、カスタムドメインを使用している開発用コンピューター上の web サーバーから Android デバイスのコンテンツを表示できます。</span><span class="sxs-lookup"><span data-stu-id="3d578-133">Custom domain mapping enables you to view content on an Android device from a web server on your development machine that is using a custom domain.</span></span>  

<span data-ttu-id="3d578-134">たとえば、ドメインでのみ動作するサードパーティの JavaScript ライブラリをサイトで使用しているとし `microsoft-edge.devtools` ます。</span><span class="sxs-lookup"><span data-stu-id="3d578-134">For example, suppose that your site uses a third-party JavaScript library that only works on the domain `microsoft-edge.devtools`.</span></span>  <span data-ttu-id="3d578-135">このため、 `hosts` 開発用コンピューター上のファイルに、このドメインをマッピングするためのエントリを作成し `localhost` ます (例 `127.0.0.1 microsoft-edge.devtools` \)。</span><span class="sxs-lookup"><span data-stu-id="3d578-135">So, you create an entry in your `hosts` file on your development machine to map this domain to `localhost` \(for example, `127.0.0.1 microsoft-edge.devtools`\).</span></span>  <span data-ttu-id="3d578-136">カスタムドメインマッピングとポート転送を設定した後、URL で Android デバイスのサイトを表示し `microsoft-edge.devtools` ます。</span><span class="sxs-lookup"><span data-stu-id="3d578-136">After setting up custom domain mapping and port forwarding, view the site on your Android device at the URL `microsoft-edge.devtools`.</span></span>  

### <span data-ttu-id="3d578-137">プロキシサーバーへのポート転送を設定する</span><span class="sxs-lookup"><span data-stu-id="3d578-137">Set up port forwarding to proxy server</span></span>  

<span data-ttu-id="3d578-138">カスタムドメインを対応付けるには、開発用コンピューターでプロキシサーバーを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d578-138">To map a custom domain you must run a proxy server on your development machine.</span></span>  <span data-ttu-id="3d578-139">プロキシサーバーの例としては、 [チャールズ][CharlesWebDebuggingProxy]、 [Squid][SquidOptimisingWebDelivery]、 [Fiddler][FiddlerWebDebuggingProxy]があります。</span><span class="sxs-lookup"><span data-stu-id="3d578-139">Examples of proxy servers are [Charles][CharlesWebDebuggingProxy], [Squid][SquidOptimisingWebDelivery], and [Fiddler][FiddlerWebDebuggingProxy].</span></span>  

<span data-ttu-id="3d578-140">プロキシへのポート転送を設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3d578-140">To set up port forwarding to a proxy:</span></span>  

1.  <span data-ttu-id="3d578-141">プロキシサーバーを実行して、使用しているポートを記録します。</span><span class="sxs-lookup"><span data-stu-id="3d578-141">Run the proxy server and record the port that it is using.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="3d578-142">プロキシサーバーと web サーバーは、異なるポートで実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d578-142">The proxy server and your web server must run on different ports.</span></span>  
    
1.  <span data-ttu-id="3d578-143">Android デバイスへの [ポート転送](#set-up-port-forwarding) を設定します。</span><span class="sxs-lookup"><span data-stu-id="3d578-143">Set up [port forwarding](#set-up-port-forwarding) to your Android device.</span></span>  <span data-ttu-id="3d578-144">[ **ローカルアドレス** ] フィールドに「」と入力し、 `localhost:` その後にプロキシサーバーが実行されているポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="3d578-144">For the **local address** field, enter `localhost:` followed by the port that your proxy server is running on.</span></span>  <span data-ttu-id="3d578-145">たとえば、ポートで実行されている場合は、 `8000` に移動 `localhost:8000` します。</span><span class="sxs-lookup"><span data-stu-id="3d578-145">For example, if it is running on port `8000`, navigate to `localhost:8000`.</span></span>  <span data-ttu-id="3d578-146">[ **デバイスポート** ] フィールドに、Android デバイスでリッスンする番号 (など) を入力し `3333` ます。</span><span class="sxs-lookup"><span data-stu-id="3d578-146">In the **device port** field enter the number that you want your Android device to listen on, such as `3333`.</span></span>  
    
### <span data-ttu-id="3d578-147">デバイスのプロキシ設定を構成する</span><span class="sxs-lookup"><span data-stu-id="3d578-147">Configure proxy settings on your device</span></span>  

<span data-ttu-id="3d578-148">次に、プロキシサーバーと通信するために Android デバイスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d578-148">Next, you need to configure your Android device to communicate with the proxy server.</span></span>  

1.  <span data-ttu-id="3d578-149">Android デバイスの場合は、[**設定**] に移動  >  **Wi-Fi**します。</span><span class="sxs-lookup"><span data-stu-id="3d578-149">On your Android device go to **Settings** > **Wi-Fi**.</span></span>  
1.  <span data-ttu-id="3d578-150">Long-現在接続しているネットワークの名前を押します。</span><span class="sxs-lookup"><span data-stu-id="3d578-150">Long-press the name of the network to which you are currently connected.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="3d578-151">プロキシ設定はネットワークごとに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3d578-151">Proxy settings apply per network.</span></span>  
    
1.  <span data-ttu-id="3d578-152">[ **ネットワークの変更**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3d578-152">Choose **Modify network**.</span></span>  
1.  <span data-ttu-id="3d578-153">[ **詳細オプション**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3d578-153">Choose **Advanced options**.</span></span>  <span data-ttu-id="3d578-154">プロキシ設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d578-154">The proxy settings display.</span></span>  
1.  <span data-ttu-id="3d578-155">[ **プロキシ** ] メニューを選択し、[ **手動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d578-155">Select the **Proxy** menu and choose **Manual**.</span></span>  
1.  <span data-ttu-id="3d578-156">[ **Proxy hostname** ] フィールドに、「」と入力し `localhost` ます。</span><span class="sxs-lookup"><span data-stu-id="3d578-156">For the **Proxy hostname** field, enter `localhost`.</span></span>  
1.  <span data-ttu-id="3d578-157">[ **プロキシポート** ] フィールドに、前のセクションの「 **デバイスポート** 」に入力したポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="3d578-157">For the **Proxy port** field, enter the port number that you entered for **device port** in the previous section.</span></span>  
1.  <span data-ttu-id="3d578-158">[ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3d578-158">Choose **Save**.</span></span>  
    
<span data-ttu-id="3d578-159">これらの設定を使用すると、デバイスは、開発用コンピューター上のプロキシにすべての要求を転送します。</span><span class="sxs-lookup"><span data-stu-id="3d578-159">With these settings, your device forwards all of its requests to the proxy on your development machine.</span></span>  <span data-ttu-id="3d578-160">プロキシによってデバイスの代わりに要求が行われるため、カスタマイズしたローカルドメインへの要求が適切に解決されます。</span><span class="sxs-lookup"><span data-stu-id="3d578-160">The proxy makes requests on behalf of your device, so requests to your customized local domain are properly resolved.</span></span>  

<span data-ttu-id="3d578-161">開発用コンピューターの場合と同様に、Android デバイスでカスタムドメインにアクセスできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3d578-161">Now access custom domains on your Android device just like on the development machine.</span></span>  

<span data-ttu-id="3d578-162">Web サーバーが標準以外のポートを使用している場合は、Android デバイスからコンテンツを要求するときに必ずポートを指定してください。</span><span class="sxs-lookup"><span data-stu-id="3d578-162">If your web server is running off of a non-standard port, remember to specify the port when requesting the content from your Android device.</span></span>  <span data-ttu-id="3d578-163">たとえば、web サーバーがポートでカスタムドメインを使用している場合 `microsoft-edge.devtools` `7331` 、Android デバイスからサイトを表示すると、その URL を使用する必要があり `microsoft-edge.devtools:7331` ます。</span><span class="sxs-lookup"><span data-stu-id="3d578-163">For example, if your web server is using the custom domain `microsoft-edge.devtools` on port `7331`, when you view the site from your Android device you should be using the URL `microsoft-edge.devtools:7331`.</span></span>  

> [!TIP]
> <span data-ttu-id="3d578-164">通常の閲覧を再開するには、開発用コンピューターから切断した後で、Android デバイスのプロキシ設定を元に戻してください。</span><span class="sxs-lookup"><span data-stu-id="3d578-164">To resume normal browsing, remember to revert the proxy settings on your Android device after you disconnect from the development machine.</span></span>  

## <span data-ttu-id="3d578-165">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="3d578-165">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[RemoteDebuggingGettingStarted]: ./index.md "Android デバイスのリモートデバッグの概要 |Microsoft ドキュメント"  

[CharlesWebDebuggingProxy]: https://www.charlesproxy.com "チャールズ Web デバッグプロキシ"  

[SquidOptimisingWebDelivery]: https://www.squid-cache.org "squid: Optimising Web 配信"  

[FiddlerWebDebuggingProxy]: https://www.telerik.com/fiddler "Fiddler Free Web デバッギングプロキシ"  

> [!NOTE]
> <span data-ttu-id="3d578-170">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="3d578-170">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="3d578-171">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/local-server) にあり、 [Kayce basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) および [Meggin Kearney][MegginKearney] \ (Tech writer \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="3d578-171">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/local-server) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="3d578-173">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="3d578-173">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
