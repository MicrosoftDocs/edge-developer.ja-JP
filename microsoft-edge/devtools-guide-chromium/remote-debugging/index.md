---
title: Android デバイスのリモートデバッグの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: a9002ca82e6e0dcaf7f174b336e5c640929a561b
ms.sourcegitcommit: 33663cd7838dddee86228dde469a5e9551bddb02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611820"
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




<!--
<style>
.devtools-inline {
  max-height: 1em;
  vertical-align: middle;
}
</style>
-->  
# <span data-ttu-id="cff08-103">Android デバイスのリモートデバッグの概要</span><span class="sxs-lookup"><span data-stu-id="cff08-103">Get Started with Remote Debugging Android Devices</span></span>   



<span data-ttu-id="cff08-104">Windows または macOS コンピューターから Android デバイス上のリモートデバッグライブコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="cff08-104">Remote debug live content on an Android device from your Windows or macOS computer.</span></span>  <span data-ttu-id="cff08-105">このチュートリアルでは、次の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cff08-105">This tutorial teaches you how to:</span></span>  

*   <span data-ttu-id="cff08-106">リモートデバッグ用に Android デバイスをセットアップし、開発用コンピューターから検出します。</span><span class="sxs-lookup"><span data-stu-id="cff08-106">Set up your Android device for remote debugging, and discover it from your development machine.</span></span>  
*   <span data-ttu-id="cff08-107">開発用コンピューターから Android デバイスのライブコンテンツを検査およびデバッグします。</span><span class="sxs-lookup"><span data-stu-id="cff08-107">Inspect and debug live content on your Android device from your development machine.</span></span>  
*   <span data-ttu-id="cff08-108">Android デバイスのコンテンツを開発用コンピューターの DevTools インスタンスに Screencast します。</span><span class="sxs-lookup"><span data-stu-id="cff08-108">Screencast content from your Android device onto a DevTools instance on your development machine.</span></span>  

<!--
> ##### Figure 1  
> Remote Debugging lets you inspect a page running on an Android device from your development machine  
> ![Remote Debugging lets you inspect a page running on an Android device from your development machine][ImageRemoteDebugging]  -->

## <span data-ttu-id="cff08-109">手順 1: Android デバイスを見つける</span><span class="sxs-lookup"><span data-stu-id="cff08-109">Step 1: Discover your Android device</span></span>   

<span data-ttu-id="cff08-110">以下のワークフローは、ほとんどのユーザーに適しています。</span><span class="sxs-lookup"><span data-stu-id="cff08-110">The workflow below works for most users.</span></span>  <span data-ttu-id="cff08-111">詳細について[は、「開発ツールで Android デバイスが検出されない](#troubleshooting-devtools-is-not-detecting-the-android-device)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cff08-111">See [Troubleshooting: DevTools is not detecting the Android device](#troubleshooting-devtools-is-not-detecting-the-android-device) for more help.</span></span>  

1.  <span data-ttu-id="cff08-112">Android で [**開発者向けオプション**] 画面を開きます。</span><span class="sxs-lookup"><span data-stu-id="cff08-112">Open the **Developer Options** screen on your Android.</span></span>  <span data-ttu-id="cff08-113">「[デバイス開発者向けオプションを構成する」を](https://developer.android.com/studio/debug/dev-options.html)参照してください。</span><span class="sxs-lookup"><span data-stu-id="cff08-113">See [Configure On-Device Developer Options](https://developer.android.com/studio/debug/dev-options.html).</span></span>  
1.  <span data-ttu-id="cff08-114">[ **USB デバッグを有効にする**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cff08-114">Select **Enable USB Debugging**.</span></span>  
1.  <span data-ttu-id="cff08-115">開発用コンピューターで、Microsoft Edge を開きます。</span><span class="sxs-lookup"><span data-stu-id="cff08-115">On your development machine, open Microsoft Edge.</span></span>  
1.  <span data-ttu-id="cff08-116">[DevTools を開き][DevToolsOpen]ます。</span><span class="sxs-lookup"><span data-stu-id="cff08-116">[Open DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="cff08-117">Devtools で、**メインメニュー**を選択して、 `...` 「**その他のツール**」「  >  **リモートデバイス**」を選択します。</span><span class="sxs-lookup"><span data-stu-id="cff08-117">In DevTools, select the **Main Menu** `...` then select **More tools** > **Remote devices**.</span></span>  
    
    > ##### <span data-ttu-id="cff08-118">図 1</span><span class="sxs-lookup"><span data-stu-id="cff08-118">Figure 1</span></span>  
    > <span data-ttu-id="cff08-119">**メインメニュー**から [**リモートデバイス**] タブを開く</span><span class="sxs-lookup"><span data-stu-id="cff08-119">Opening the **Remote Devices** tab via the **Main Menu**</span></span>  
    > <span data-ttu-id="cff08-120">![リモートデバイス] タブを開くには、メインメニューから[ImageOpenRemoteDevices]</span><span class="sxs-lookup"><span data-stu-id="cff08-120">![Opening the Remote Devices tab via the Main Menu][ImageOpenRemoteDevices]</span></span>  

1.  <span data-ttu-id="cff08-121">DevTools で、[**設定**] タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="cff08-121">In DevTools, open the **Settings** tab.</span></span>  

1.  <span data-ttu-id="cff08-122">[ **USB デバイスの検出**] チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cff08-122">Make sure that the **Discover USB devices** checkbox is enabled.</span></span>  
    
    > ##### <span data-ttu-id="cff08-123">図 2</span><span class="sxs-lookup"><span data-stu-id="cff08-123">Figure 2</span></span>  
    > <span data-ttu-id="cff08-124">[ **USB デバイスの検出**] チェックボックスがオンになっている</span><span class="sxs-lookup"><span data-stu-id="cff08-124">The **Discover USB Devices** checkbox is enabled</span></span>  
    > <span data-ttu-id="cff08-125">![USB デバイスの検出] チェックボックスがオンになっている[ImageDiscoverUSBDevices]</span><span class="sxs-lookup"><span data-stu-id="cff08-125">![The Discover USB Devices checkbox is enabled][ImageDiscoverUSBDevices]</span></span>  

1.  <span data-ttu-id="cff08-126">USB ケーブルを使って、Android デバイスを開発用コンピューターに直接接続します。</span><span class="sxs-lookup"><span data-stu-id="cff08-126">Connect your Android device directly to your development machine using a USB cable.</span></span>  <span data-ttu-id="cff08-127">この操作を初めて行うときは、DevTools で不明なデバイスが検出されたことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cff08-127">The first time you do this, you usually see that DevTools has detected an unknown device.</span></span>  <span data-ttu-id="cff08-128">Android デバイスのモデル名の下に緑色のドットとテキストが**接続さ**れている場合は、devtools でデバイスへの接続が正常に確立されています。</span><span class="sxs-lookup"><span data-stu-id="cff08-128">If you see a green dot and the text **Connected** below the model name of your Android device, then DevTools has successfully established the connection to your device.</span></span>  <span data-ttu-id="cff08-129">[手順 2](#step-2-debug-content-on-your-android-device-from-your-development-machine)に進みます。</span><span class="sxs-lookup"><span data-stu-id="cff08-129">Continue to [Step 2](#step-2-debug-content-on-your-android-device-from-your-development-machine).</span></span>  
    <!--
    > ##### Figure 4  
    > The **Remote Devices** tab has successfully detected an unknown device that is pending authorization  
    > ![The Remote Devices tab has successfully detected an unknown device that is pending authorization][ImageUnknownDevice]  -->

1.  <span data-ttu-id="cff08-130">デバイスが**不明**と表示されている場合は、Android デバイスで [ **USB デバッグの許可**] プロンプトを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="cff08-130">If your device is showing up as **Unknown**, accept the **Allow USB Debugging** permission prompt on your Android device.</span></span>  

### <span data-ttu-id="cff08-131">トラブルシューティング: DevTools で Android デバイスが検出されない</span><span class="sxs-lookup"><span data-stu-id="cff08-131">Troubleshooting: DevTools is not detecting the Android device</span></span>   

<span data-ttu-id="cff08-132">ハードウェアが正しく設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cff08-132">Make sure that your hardware is set up correctly:</span></span>  

*   <span data-ttu-id="cff08-133">USB ハブを使っている場合は、代わりに Android デバイスを開発用コンピューターに直接接続してみてください。</span><span class="sxs-lookup"><span data-stu-id="cff08-133">If you are using a USB hub, try connecting your Android device directly to your development machine instead.</span></span>  
*   <span data-ttu-id="cff08-134">Android デバイスと開発マシンの間で USB ケーブルを外してから、もう一度接続してみてください。</span><span class="sxs-lookup"><span data-stu-id="cff08-134">Try unplugging the USB cable between your Android device and development machine, and then plugging it back in.</span></span>  <span data-ttu-id="cff08-135">Android および開発マシンの画面のロックが解除されている間に、この操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cff08-135">Do it while your Android and development machine screens are unlocked.</span></span>  
*   <span data-ttu-id="cff08-136">USB ケーブルが動作していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cff08-136">Make sure that your USB cable works.</span></span>  <span data-ttu-id="cff08-137">開発用コンピューターから Android デバイスのファイルを検査できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="cff08-137">You should be able to inspect files on your Android device from your development machine.</span></span>  

<span data-ttu-id="cff08-138">ソフトウェアが正しく設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cff08-138">Make sure that your software is set up correctly:</span></span>  

*   <span data-ttu-id="cff08-139">開発用コンピューターで Windows を実行している場合は、Android デバイスの USB ドライバーを手動でインストールしてみてください。</span><span class="sxs-lookup"><span data-stu-id="cff08-139">If your development machine is running Windows, try manually installing the USB drivers for your Android device.</span></span>  <span data-ttu-id="cff08-140">「 [OEM USB ドライバーをインストール][AndroidUSBDrivers]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cff08-140">See [Install OEM USB Drivers][AndroidUSBDrivers].</span></span>  
    
*   <span data-ttu-id="cff08-141">Windows と Android デバイス (特に Samsung) の一部の組み合わせでは、追加の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="cff08-141">Some combinations of Windows and Android devices (especially Samsung) require extra set up.</span></span>  <span data-ttu-id="cff08-142">「[StackOverflowDevicesNotDetected] に接続してもデバイスが検出されない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cff08-142">See [DevTools Devices does not detect device when plugged in][StackOverflowDevicesNotDetected].</span></span>  
    
<span data-ttu-id="cff08-143">Android デバイスで**USB のデバッグを許可**するかどうかを確認するメッセージが表示されない場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cff08-143">If you do not see the **Allow USB Debugging** prompt on your Android device try:</span></span>  

*   <span data-ttu-id="cff08-144">DevTools が開発用コンピューターに集中していて、Android のホーム画面が表示されているときに、USB ケーブルを切断してから接続し直す。</span><span class="sxs-lookup"><span data-stu-id="cff08-144">Disconnecting and then re-connecting the USB cable while DevTools is in focus on your development machine and your Android homescreen is showing.</span></span>  <span data-ttu-id="cff08-145">つまり、Android または開発機の画面がロックされているときに、プロンプトが表示されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="cff08-145">In other words, sometimes the prompt does not show up when your Android or development machine screens are locked.</span></span>
*   <span data-ttu-id="cff08-146">Android デバイスと開発用コンピューターの表示設定を更新して、スリープ状態に移動しないようにします。</span><span class="sxs-lookup"><span data-stu-id="cff08-146">Updating the display settings for your Android device and development machine so that they never go to sleep.</span></span>  
*   <span data-ttu-id="cff08-147">Android の USB モードを PTP に設定します。</span><span class="sxs-lookup"><span data-stu-id="cff08-147">Setting the USB mode for Android to PTP.</span></span>  <span data-ttu-id="cff08-148">「 [Galaxy S4 で [USB デバッグの承認] ダイアログボックスが表示されない」を][StackExchangeGalaxyS4DoesNotShowDialogBox]参照してください。</span><span class="sxs-lookup"><span data-stu-id="cff08-148">See [Galaxy S4 does not show Authorize USB debugging dialog box][StackExchangeGalaxyS4DoesNotShowDialogBox].</span></span>  
*   <span data-ttu-id="cff08-149">Android デバイスの [**開発者オプション**] 画面で [ **USB デバッグ承認の取り消し**] を選択して、新しい状態にリセットします。</span><span class="sxs-lookup"><span data-stu-id="cff08-149">Select **Revoke USB Debugging Authorizations** from the **Developer Options** screen on your Android device to reset it to a fresh state.</span></span>  

<span data-ttu-id="cff08-150">このセクションで説明されていない解決策、または [StackOverflowDevicesNotDetected] に接続しているときに、デバイスがデバイスを検出しない場合、またはそのスタックオーバーフローの質問に回答を追加してください。</span><span class="sxs-lookup"><span data-stu-id="cff08-150">If you find a solution that is not mentioned in this section or in [DevTools Devices does not detect device when plugged in][StackOverflowDevicesNotDetected] or please add an answer to that Stack Overflow question</span></span><!--, or [open an issue in the webfundamentals repository][GitHubWebFundamentalsNewIssue]--><span data-ttu-id="cff08-151">!</span><span class="sxs-lookup"><span data-stu-id="cff08-151">!</span></span>  

## <span data-ttu-id="cff08-152">手順 2: 開発用コンピューターから Android デバイスのコンテンツをデバッグする</span><span class="sxs-lookup"><span data-stu-id="cff08-152">Step 2: Debug content on your Android device from your development machine</span></span>   

1.  <span data-ttu-id="cff08-153">Android デバイスで Microsoft Edge を開きます。</span><span class="sxs-lookup"><span data-stu-id="cff08-153">Open Microsoft Edge on your Android device.</span></span>  

1.  <span data-ttu-id="cff08-154">[**リモートデバイス**] タブで、Android デバイスモデル名に一致するタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="cff08-154">In the **Remote Devices** tab, select the tab that matches your Android device model name.</span></span>  
    <span data-ttu-id="cff08-155">このページの上部には、Android デバイスのモデル名に続いて、そのシリアル番号が表示されています。</span><span class="sxs-lookup"><span data-stu-id="cff08-155">At the top of this page, you see the model name of your Android device, followed by its serial number.</span></span>  <span data-ttu-id="cff08-156">その下で、デバイス上で実行されている Microsoft Edge のバージョン番号がかっこで囲まれていることが確認できます。</span><span class="sxs-lookup"><span data-stu-id="cff08-156">Below that, you should see the version of Microsoft Edge running on the device, with the version number in parentheses.</span></span>  <span data-ttu-id="cff08-157">開かれている Microsoft Edge タブごとに、独自のセクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cff08-157">Each open Microsoft Edge tab gets its own section.</span></span>  <span data-ttu-id="cff08-158">このセクションでは、このタブを操作できます。</span><span class="sxs-lookup"><span data-stu-id="cff08-158">You may interact with that tab from this section.</span></span>  <!--If there are any apps using WebView, you see a section for each of those apps, too.  --><!--In [**Figure 5**](#figure-5) there are no tabs or WebViews open.  -->
    <!--
    > ##### Figure 5  
    > A connected remote device  
    > ![A connected remote device][ImageConnectedRemoteDevice]  -->

1.  <span data-ttu-id="cff08-159">[**新しいタブ**テキスト] ボックスに URL を入力し、[**開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cff08-159">In the **New tab** text box, enter a URL and then select **Open**.</span></span>  <span data-ttu-id="cff08-160">Android デバイスの新しいタブにページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cff08-160">The page opens in a new tab on your Android device.</span></span>  

1.  <span data-ttu-id="cff08-161">直前に開いた URL の横にある [**検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cff08-161">Select **Inspect** next to the URL that you just opened.</span></span>  <span data-ttu-id="cff08-162">新しい DevTools インスタンスが開きます。</span><span class="sxs-lookup"><span data-stu-id="cff08-162">A new DevTools instance opens.</span></span>  <span data-ttu-id="cff08-163">Android デバイス上で実行されている Microsoft Edge のバージョンによって、開発用コンピューターで開く DevTools のバージョンが決まります。</span><span class="sxs-lookup"><span data-stu-id="cff08-163">The version of Microsoft Edge running on your Android device determines the version of DevTools that opens on your development machine.</span></span>  
    <span data-ttu-id="cff08-164">Android デバイスで古いバージョンの Microsoft Edge が実行されている場合、DevTools インスタンスは、使用しているものとは大幅に異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cff08-164">So, if your Android device is running a very old version of Microsoft Edge, the DevTools instance may look very different than what you are used to.</span></span>  

### <span data-ttu-id="cff08-165">その他のアクション: タブを再読み込み、フォーカス、または閉じる</span><span class="sxs-lookup"><span data-stu-id="cff08-165">More actions: reload, focus, or close a tab</span></span>   

<span data-ttu-id="cff08-166">**More Options** `...` 再読み込み、フォーカス、または閉じるタブの隣にある [その他のオプション] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cff08-166">Select **More Options** `...` next to the tab that you want to reload, focus, or close.</span></span>  
<!--
> ##### Figure 6  
> The menu for reloading, focusing, or closing a tab  
> ![The menu for reloading, focusing, or closing a tab][ImageReload]  -->

### <span data-ttu-id="cff08-167">要素を検査する</span><span class="sxs-lookup"><span data-stu-id="cff08-167">Inspect elements</span></span>   

<span data-ttu-id="cff08-168">DevTools インスタンスの**要素**パネルに移動し、要素の上にマウスポインターを置いて、Android デバイスのビューポートでその要素を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="cff08-168">Go to the **Elements** panel of your DevTools instance, and hover over an element to highlight it in the viewport of your Android device.</span></span>  

<span data-ttu-id="cff08-169">Android デバイスの画面で要素を選択して、[**要素**] パネルで選ぶこともできます。</span><span class="sxs-lookup"><span data-stu-id="cff08-169">You may also select an element on your Android device screen to select it in the **Elements** panel.</span></span>  <span data-ttu-id="cff08-170">DevTools インスタンスで [**要素**の選択] を選択し ![ ][ImageSelectElementIcon] 、Android デバイス画面で要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="cff08-170">Select **Select Element** ![Select Element][ImageSelectElementIcon] on your DevTools instance, and then select the element on your Android device screen.</span></span>  

> [!NOTE]
> <span data-ttu-id="cff08-171">最初の選択の後に **[要素の選択]** が無効になっているため、この機能を使うたびに有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cff08-171">**Select Element** is disabled after the first selection, so you must re-enable it every time you want to use this feature.</span></span>  

### <span data-ttu-id="cff08-172">Android の画面を開発用コンピューターに Screencast</span><span class="sxs-lookup"><span data-stu-id="cff08-172">Screencast your Android screen to your development machine</span></span>   

<span data-ttu-id="cff08-173">[**トグル Screencast**トグル Screencast] を選択して、 ![ ][ImageToggleScreencastIcon] Devtools インスタンスで Android デバイスのコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="cff08-173">Select **Toggle Screencast** ![Toggle Screencast][ImageToggleScreencastIcon] to view the content of your Android device in your DevTools instance.</span></span>  

<span data-ttu-id="cff08-174">Screencast はさまざまな方法で操作できます。</span><span class="sxs-lookup"><span data-stu-id="cff08-174">You are able to interact with the screencast in multiple ways:</span></span>  

*   <span data-ttu-id="cff08-175">クリックは、デバイスで適切なタッチイベントを発生させるために、タップに変換されます。</span><span class="sxs-lookup"><span data-stu-id="cff08-175">Clicks are translated into taps, firing proper touch events on the device.</span></span>  
*   <span data-ttu-id="cff08-176">コンピューターのキーボード操作がデバイスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="cff08-176">Keystrokes on your computer are sent to the device.</span></span>  
*   <span data-ttu-id="cff08-177">ピンチジェスチャをシミュレートするには、 `Shift` ドラッグ中にホールドします。</span><span class="sxs-lookup"><span data-stu-id="cff08-177">To simulate a pinch gesture, hold `Shift` while dragging.</span></span>  
*   <span data-ttu-id="cff08-178">スクロールするには、トラックパッドまたはマウスホイール、またはマウスポインターでフリックを使用します。</span><span class="sxs-lookup"><span data-stu-id="cff08-178">To scroll, use your trackpad or mouse wheel, or fling with your mouse pointer.</span></span>

<span data-ttu-id="cff08-179">スクリーンキャストに関する注意事項:</span><span class="sxs-lookup"><span data-stu-id="cff08-179">Some notes on screencasts:</span></span>  

*   <span data-ttu-id="cff08-180">スクリーンキャストは、ページコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="cff08-180">Screencasts only display page content.</span></span>  <span data-ttu-id="cff08-181">Screencast の透明部分は、Microsoft Edge のアドレスバー、Android ステータスバー、Android キーボードなどのデバイスインターフェイスを表します。</span><span class="sxs-lookup"><span data-stu-id="cff08-181">Transparent portions of the screencast represent device interfaces, such as the Microsoft Edge address bar, the Android status bar, or the Android keyboard.</span></span>  
*   <span data-ttu-id="cff08-182">スクリーンキャストはフレームレートに悪影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="cff08-182">Screencasts negatively affect frame rates.</span></span>  <span data-ttu-id="cff08-183">スクロールまたはアニメーションの計測中に screencasting を無効にすると、ページのパフォーマンスがより正確に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cff08-183">Disable screencasting while measuring scrolls or animations to get a more accurate picture of the performance of your page.</span></span>  
*   <span data-ttu-id="cff08-184">Android デバイスの画面がロックされている場合、screencast のコンテンツは表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="cff08-184">If your Android device screen locks, the content of your screencast disappears.</span></span>  <span data-ttu-id="cff08-185">Android デバイスの画面のロックを解除して、screencast を自動的に再開します。</span><span class="sxs-lookup"><span data-stu-id="cff08-185">Unlock your Android device screen to automatically resume the screencast.</span></span>  





<!-- image links -->  

[ImageSelectElementIcon]: /microsoft-edge/devtools-guide-chromium/media/select-element-icon.msft.png  
[ImageToggleScreencastIcon]: /microsoft-edge/devtools-guide-chromium/media/toggle-screencast-icon.msft.png  

<!--[ImageRemoteDebugging]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging--remote-debugging.msft.png "old Figure 1:  Remote Debugging lets you inspect a page running on an Android device from your development machine"  -->  
[ImageOpenRemoteDevices]:/microsoft-edge/devtools-guide-chromium/media/remote-debugging-more-tools-remote-devices.msft.png "図 1: メインメニューから [リモートデバイス] タブを開く"  
[ImageDiscoverUSBDevices]:/microsoft-edge/devtools-guide-chromium/media/remote-debugging-remote-devices-tab.msft.png "図 2: [USB デバイスの検出] チェックボックスがオンになっている  
<!--[ImageUnknownDevice]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging--unknown-device.msft.png "old Figure 4:  The Remote Devices tab has successfully detected an unknown device that is pending authorization"  -->  
<!--[ImageConnectedRemoteDevice]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging--connected-remote-device.msft.png "old Figure 5:  A connected remote device"  -->
<!--[ImageReload]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging--reload.msft.png "old Figure 6: The menu for reloading, focusing, or closing a tab"  -->

<!-- links -->  

[DevToolsOpen]: /microsoft-edge/devtools-guide-chromium/open "Microsoft Edge DevTools を開く"  

[AndroidUSBDrivers]: https://developer.android.com/tools/extras/oem-usb.html "OEM USB ドライバーをインストールする |Android 開発者"  

<!-- [GitHubWebFundamentalsNewIssue]: https://github.com/Alphabet/webfundamentals/issues/new?title=[Remote%20Debugging] "GitHub - Web Fundamentals - New Issue"  -->  
[StackOverflowDevicesNotDetected]: https://stackoverflow.com/questions/21925992 "devtools デバイスで、電源に接続されているときにデバイスが検出されません"-スタックオーバーフロー "  

[StackExchangeGalaxyS4DoesNotShowDialogBox]: https://android.stackexchange.com/questions/101933 "adb-Android ファンスタック交換"  

> [!NOTE]
> <span data-ttu-id="cff08-192">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="cff08-192">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="cff08-193">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="cff08-193">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="cff08-195">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="cff08-195">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
