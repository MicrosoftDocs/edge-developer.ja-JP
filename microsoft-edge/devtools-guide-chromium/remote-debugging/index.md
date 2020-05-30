---
title: Android デバイスのリモートデバッグの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: fc7450ba2b088eee8f4005216374980096cbb067
ms.sourcegitcommit: ba9f0ed77e84174b03262b17e62c6a7e26cfeb3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2020
ms.locfileid: "10688160"
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

# <span data-ttu-id="d217c-103">Android デバイスのリモートデバッグの概要</span><span class="sxs-lookup"><span data-stu-id="d217c-103">Get started with remote debugging Android devices</span></span>  

<span data-ttu-id="d217c-104">Windows または macOS コンピューターから Android デバイス上のリモートデバッグライブコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="d217c-104">Remote debug live content on an Android device from your Windows or macOS computer.</span></span>  <span data-ttu-id="d217c-105">このチュートリアルページでは、次の操作を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d217c-105">This tutorial page teaches you how to complete the following actions.</span></span>  

*   <span data-ttu-id="d217c-106">リモートデバッグ用に Android デバイスをセットアップし、開発用コンピューターから検出します。</span><span class="sxs-lookup"><span data-stu-id="d217c-106">Set up your Android device for remote debugging, and discover it from your development machine.</span></span>  
*   <span data-ttu-id="d217c-107">開発用コンピューターから Android デバイスのライブコンテンツを検査およびデバッグします。</span><span class="sxs-lookup"><span data-stu-id="d217c-107">Inspect and debug live content on your Android device from your development machine.</span></span>  
*   <span data-ttu-id="d217c-108">Android デバイスのコンテンツを開発用コンピューターの DevTools インスタンスに Screencast します。</span><span class="sxs-lookup"><span data-stu-id="d217c-108">Screencast content from your Android device onto a DevTools instance on your development machine.</span></span>  

<!--  
:::image type="complex" source="../media/remote-debugging--remote-debugging.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging--remote-debugging.msft.png":::
   old Figure 1.  Remote Debugging lets you inspect a page running on an Android device from your development machine  
:::image-end:::  
-->  

## <span data-ttu-id="d217c-109">手順 1: Android デバイスを見つける</span><span class="sxs-lookup"><span data-stu-id="d217c-109">Step 1: Discover your Android device</span></span>  

<span data-ttu-id="d217c-110">以下のワークフローは、ほとんどのユーザーに適しています。</span><span class="sxs-lookup"><span data-stu-id="d217c-110">The workflow below works for most users.</span></span>  <span data-ttu-id="d217c-111">詳細について[は、「開発ツールで Android デバイスが検出されない](#troubleshooting-devtools-is-not-detecting-the-android-device)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d217c-111">See [Troubleshooting: DevTools is not detecting the Android device](#troubleshooting-devtools-is-not-detecting-the-android-device) for more help.</span></span>  

1.  <span data-ttu-id="d217c-112">Android で [**開発者向けオプション**] 画面を開きます。</span><span class="sxs-lookup"><span data-stu-id="d217c-112">Open the **Developer Options** screen on your Android.</span></span>  <span data-ttu-id="d217c-113">詳細については、「[デバイスの開発者向けオプションを構成する](https://developer.android.com/studio/debug/dev-options.html)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d217c-113">For more information, see [Configure On-Device Developer Options](https://developer.android.com/studio/debug/dev-options.html).</span></span>  
1.  <span data-ttu-id="d217c-114">[ **USB デバッグを有効にする**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d217c-114">Select **Enable USB Debugging**.</span></span>  
1.  <span data-ttu-id="d217c-115">開発用コンピューターで、Microsoft Edge を開きます。</span><span class="sxs-lookup"><span data-stu-id="d217c-115">On your development machine, open Microsoft Edge.</span></span>  
1.  <span data-ttu-id="d217c-116">`edge://inspect`Microsoft Edge でページに移動します。</span><span class="sxs-lookup"><span data-stu-id="d217c-116">Navigate to the `edge://inspect` page in Microsoft Edge.</span></span>  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-no-targets.msft.png" alt-text="Microsoft Edge の [edge://inspect] ページ" lightbox="../media/remote-debugging-edge-inspect-no-targets.msft.png":::
       <span data-ttu-id="d217c-118">図 1. </span><span class="sxs-lookup"><span data-stu-id="d217c-118">Figure 1.</span></span>  <span data-ttu-id="d217c-119">`edge://inspect`Microsoft Edge のページ</span><span class="sxs-lookup"><span data-stu-id="d217c-119">The `edge://inspect` page in Microsoft Edge</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d217c-120">USB ケーブルを使って、Android デバイスを開発用コンピューターに直接接続します。</span><span class="sxs-lookup"><span data-stu-id="d217c-120">Connect your Android device directly to your development machine using a USB cable.</span></span>  <span data-ttu-id="d217c-121">初めて接続しようとしたときに、一般的に、不明なデバイスを検出するための DevTools のプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d217c-121">The first time you try to connect, you usually see prompt about DevTools detecting an unknown device.</span></span>  <span data-ttu-id="d217c-122">Android デバイスで [ **USB のデバッグを許可**] プロンプトを承諾します。</span><span class="sxs-lookup"><span data-stu-id="d217c-122">Accept the **Allow USB Debugging** permission prompt on your Android device.</span></span>  
    
    :::image type="complex" source="../media/remote-debugging-android-permissions-prompt.msft.png" alt-text="Android デバイスでの USB デバッグの許可プロンプト" lightbox="../media/remote-debugging-android-permissions-prompt.msft.png":::
       <span data-ttu-id="d217c-124">図 2. </span><span class="sxs-lookup"><span data-stu-id="d217c-124">Figure 2.</span></span>  <span data-ttu-id="d217c-125">Android デバイスでの**USB デバッグ**の許可プロンプト</span><span class="sxs-lookup"><span data-stu-id="d217c-125">The **Allow USB Debugging** permission prompt on an Android device</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d217c-126">Android デバイスのモデル名が表示される場合は、Microsoft Edge でデバイスへの接続が正常に確立されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d217c-126">If you see the model name of your Android device, then Microsoft Edge has successfully established the connection to your device.</span></span>  <span data-ttu-id="d217c-127">[手順 2](#step-2-debug-content-on-your-android-device-from-your-development-machine)に進みます。</span><span class="sxs-lookup"><span data-stu-id="d217c-127">Continue to [Step 2](#step-2-debug-content-on-your-android-device-from-your-development-machine).</span></span>  
    
    <!--  
    :::image type="complex" source="../media/remote-debugging--unknown-device.msft.png" alt-text="The Remote Devices tab has successfully detected an unknown device that is pending authorization" lightbox="../media/remote-debugging--unknown-device.msft.png":::
       old Figure 4.  The **Remote Devices** tab has successfully detected an unknown device that is pending authorization  
    :::image-end:::
    -->  
    
### <span data-ttu-id="d217c-128">トラブルシューティング: DevTools で Android デバイスが検出されない</span><span class="sxs-lookup"><span data-stu-id="d217c-128">Troubleshooting: DevTools is not detecting the Android device</span></span>  

<span data-ttu-id="d217c-129">以下のヒントは、お使いのハードウェアの適切な設定のトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d217c-129">Use the following tips to help you troubleshoot the correct settings for your hardware.</span></span>  

*   <span data-ttu-id="d217c-130">USB ハブを使っている場合は、Android デバイスを開発用コンピューターに直接接続してみてください。</span><span class="sxs-lookup"><span data-stu-id="d217c-130">If you are using a USB hub, try connecting your Android device directly to your development machine.</span></span>  
*   <span data-ttu-id="d217c-131">Android デバイスと開発マシンの間で USB ケーブルを外して、USB ケーブルを再接続してみてください。</span><span class="sxs-lookup"><span data-stu-id="d217c-131">Try unplugging the USB cable between your Android device and development machine, and then re-plugging your USB cable.</span></span>  <span data-ttu-id="d217c-132">Android および開発マシンの画面のロックが解除されている状態で、タスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="d217c-132">Complete the task while your Android and development machine screens are unlocked.</span></span>  
*   <span data-ttu-id="d217c-133">USB ケーブルが動作していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d217c-133">Make sure that your USB cable works.</span></span>  <span data-ttu-id="d217c-134">開発用コンピューターから Android デバイスのファイルを検査できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d217c-134">You should be able to inspect files on your Android device from your development machine.</span></span>  

<span data-ttu-id="d217c-135">ソフトウェアが正しく設定されているかどうかを確認するには、次のヒントを参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="d217c-135">Use the following tips to help you verify that your software is set up correctly.</span></span>  

*   <span data-ttu-id="d217c-136">開発用コンピューターで Windows を実行している場合は、Android デバイスの USB ドライバーを手動でインストールしてみてください。</span><span class="sxs-lookup"><span data-stu-id="d217c-136">If your development machine is running Windows, try manually installing the USB drivers for your Android device.</span></span>  <span data-ttu-id="d217c-137">詳細については、「 [OEM USB ドライバーをインストール][AndroidUSBDrivers]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d217c-137">For more information, see [Install OEM USB Drivers][AndroidUSBDrivers].</span></span>  
*   <span data-ttu-id="d217c-138">Windows と Android デバイスの組み合わせ (特に Samsung \) には、追加の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="d217c-138">Some combinations of Windows and Android devices \(especially Samsung\) require additional settings.</span></span>  <span data-ttu-id="d217c-139">詳細については、「[デバイスが接続されるときにデバイスが検出されない] [StackOverflowDevicesNotDetected]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d217c-139">For more information, see [DevTools Devices does not detect device when plugged in][StackOverflowDevicesNotDetected].</span></span>  

<span data-ttu-id="d217c-140">Android デバイスで**USB デバッグを許可**するかどうかを確認するには、次のヒントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d217c-140">Use the following tips to help you troubleshoot not seeing the **Allow USB Debugging** prompt on your Android device.</span></span>  

*   <span data-ttu-id="d217c-141">DevTools が開発用コンピューターに集中していて、Android のホーム画面が表示されているときに、USB ケーブルを切断してから接続し直す。</span><span class="sxs-lookup"><span data-stu-id="d217c-141">Disconnecting and then re-connecting the USB cable while DevTools is in focus on your development machine and your Android homescreen is showing.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="d217c-142">Android または開発用コンピューターの画面がロックされている場合、このプロンプトが表示されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="d217c-142">You may not see the prompt if your Android or development machine screens are locked.</span></span>  

*   <span data-ttu-id="d217c-143">Android デバイスと開発用コンピューターの表示設定を更新して、それぞれがスリープ状態にならないようにします。</span><span class="sxs-lookup"><span data-stu-id="d217c-143">Updating the display settings for your Android device and development machine so that each never goes to sleep.</span></span>  
*   <span data-ttu-id="d217c-144">Android の USB モードを PTP に設定します。</span><span class="sxs-lookup"><span data-stu-id="d217c-144">Setting the USB mode for Android to PTP.</span></span>  <span data-ttu-id="d217c-145">詳細については、「 [Galaxy S4 で [USB デバッグの承認] ダイアログボックスが表示されない][StackExchangeGalaxyS4DoesNotShowDialogBox]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d217c-145">For more information, see [Galaxy S4 does not show Authorize USB debugging dialog box][StackExchangeGalaxyS4DoesNotShowDialogBox].</span></span>  
*   <span data-ttu-id="d217c-146">Android デバイスの [**開発者オプション**] 画面で [ **USB デバッグ承認の取り消し**] を選択して、新しい状態にリセットします。</span><span class="sxs-lookup"><span data-stu-id="d217c-146">Select **Revoke USB Debugging Authorizations** from the **Developer Options** screen on your Android device to reset it to a fresh state.</span></span>  

<span data-ttu-id="d217c-147">このページに記載されていない解決策を見つけた場合、または [DevTools デバイスで、スタックオーバーフロー時にデバイスが接続されています] [StackOverflowDevicesNotDetected] が検出されない場合は、スタックオーバーフローの質問にソリューションを追加してください。</span><span class="sxs-lookup"><span data-stu-id="d217c-147">If you find a solution that is not mentioned on this page or in [DevTools Devices does not detect device when plugged in][StackOverflowDevicesNotDetected] on Stack Overflow, please add your solution to the Stack Overflow question</span></span><!--, or [open an issue in the webfundamentals repository][GitHubWebFundamentalsNewIssue]--><span data-ttu-id="d217c-148">!</span><span class="sxs-lookup"><span data-stu-id="d217c-148">!</span></span>  

## <span data-ttu-id="d217c-149">手順 2: 開発用コンピューターから Android デバイスのコンテンツをデバッグする</span><span class="sxs-lookup"><span data-stu-id="d217c-149">Step 2: Debug content on your Android device from your development machine</span></span>  

1.  <span data-ttu-id="d217c-150">Android デバイスで Microsoft Edge を開きます。</span><span class="sxs-lookup"><span data-stu-id="d217c-150">Open Microsoft Edge on your Android device.</span></span>  
1.  <span data-ttu-id="d217c-151">ページから `edge://inspect` 、Android デバイスのモデル名の後にデバイスのシリアル番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d217c-151">From the `edge://inspect` page, you see the model name of your Android device, followed by the device serial number.</span></span>  <span data-ttu-id="d217c-152">その下で、デバイス上で実行されている Microsoft Edge のバージョン番号がかっこで囲まれていることが確認できます。</span><span class="sxs-lookup"><span data-stu-id="d217c-152">Below that, you should see the version of Microsoft Edge running on the device, with the version number in parentheses.</span></span>  <span data-ttu-id="d217c-153">各開いている Microsoft Edge タブには、一意のセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="d217c-153">Each open Microsoft Edge tab gets a unique section.</span></span>  <span data-ttu-id="d217c-154">セクションからそのタブを操作できます。</span><span class="sxs-lookup"><span data-stu-id="d217c-154">You may interact with that tab from a section.</span></span>  <!--If there are any apps using WebView, you see a section for each of those apps, too.  --><!--In [**Figure 5**](#figure-5) there are no tabs or WebViews open.  -->  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets.msft.png" alt-text="接続されているリモートデバイス" lightbox="../media/remote-debugging-edge-inspect-with-targets.msft.png":::
       <span data-ttu-id="d217c-156">図 3. </span><span class="sxs-lookup"><span data-stu-id="d217c-156">Figure 3.</span></span>  <span data-ttu-id="d217c-157">接続されているリモートデバイス</span><span class="sxs-lookup"><span data-stu-id="d217c-157">A connected remote device</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d217c-158">[**開く] タブ**の [url] テキストボックスに url を入力し、[**開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d217c-158">In the **Open tab with url** text box, enter a URL and then select **Open**.</span></span>  <span data-ttu-id="d217c-159">Android デバイスの新しいタブにページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d217c-159">The page opens in a new tab on your Android device.</span></span>  
1.  <span data-ttu-id="d217c-160">直前に開いた URL の横にある [**検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d217c-160">Select **inspect** next to the URL that you just opened.</span></span>  <span data-ttu-id="d217c-161">新しい DevTools インスタンスが開きます。</span><span class="sxs-lookup"><span data-stu-id="d217c-161">A new DevTools instance opens.</span></span>  

<!-- The version of Microsoft Edge running on your Android device determines the version of DevTools that opens on your development machine.  
    So, if your Android device is running a very old version of Microsoft Edge, the DevTools instance may look very different than what you are used to.   -->

### <span data-ttu-id="d217c-162">その他のアクション: タブにフォーカス、再読み込み、または閉じる</span><span class="sxs-lookup"><span data-stu-id="d217c-162">More actions: focus, reload, or close a tab</span></span>  

<span data-ttu-id="d217c-163">フォーカスタブ、再読み込み、または閉じるタブの横にある [**フォーカス] タブ**、[**再読み込み**]、または [**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d217c-163">Select **focus tab**, **reload**, or **close** next to the tab that you want to focus, reload, or close.</span></span>  

:::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png" alt-text="タブをフォーカス、再読み込み、または閉じるためのボタン" lightbox="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png":::
   <span data-ttu-id="d217c-165">図 4: </span><span class="sxs-lookup"><span data-stu-id="d217c-165">Figure 4.</span></span>  <span data-ttu-id="d217c-166">タブをフォーカス、再読み込み、または閉じるためのボタン</span><span class="sxs-lookup"><span data-stu-id="d217c-166">The buttons for focusing, reloading, or closing a tab</span></span>  
:::image-end:::  

### <span data-ttu-id="d217c-167">要素を検査する</span><span class="sxs-lookup"><span data-stu-id="d217c-167">Inspect elements</span></span>  

<span data-ttu-id="d217c-168">DevTools インスタンスの**要素**パネルに移動し、要素の上にマウスポインターを置いて、Android デバイスのビューポートでその要素を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="d217c-168">Go to the **Elements** panel of your DevTools instance, and hover over an element to highlight it in the viewport of your Android device.</span></span>  

<span data-ttu-id="d217c-169">Android デバイスの画面で要素を選択して、[**要素**] パネルで選ぶこともできます。</span><span class="sxs-lookup"><span data-stu-id="d217c-169">You may also select an element on your Android device screen to select it in the **Elements** panel.</span></span>  <span data-ttu-id="d217c-170">DevTools インスタンスで [**要素**の選択] アイコンを選択し、 ![ ][ImageSelectElementIcon] Android デバイス画面で要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="d217c-170">Select **Select Element** ![Select Element][ImageSelectElementIcon] icon on your DevTools instance, and then select the element on your Android device screen.</span></span>  

> [!NOTE]
> <span data-ttu-id="d217c-171">最初の選択の後に **[要素の選択]** が無効になっているため、この機能を使うたびに有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d217c-171">**Select Element** is disabled after the first selection, so you must re-enable it every time you want to use the feature.</span></span>  

### <span data-ttu-id="d217c-172">Android の画面を開発用コンピューターに Screencast</span><span class="sxs-lookup"><span data-stu-id="d217c-172">Screencast your Android screen to your development machine</span></span>  

<span data-ttu-id="d217c-173">[ **Screencast** ![ トグル Screencast] を選択し ][ImageToggleScreencastIcon] て、Devtools インスタンスで Android デバイスのコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="d217c-173">Select **Toggle Screencast** ![Toggle Screencast][ImageToggleScreencastIcon] icon to view the content of your Android device in your DevTools instance.</span></span>  

<span data-ttu-id="d217c-174">Screencast は次の方法で操作できます。</span><span class="sxs-lookup"><span data-stu-id="d217c-174">You are able to interact with the screencast in the following ways.</span></span>  

*   <span data-ttu-id="d217c-175">クリックは、デバイスで適切なタッチイベントを発生させるために、タップに変換されます。</span><span class="sxs-lookup"><span data-stu-id="d217c-175">Clicks are translated into taps, firing proper touch events on the device.</span></span>  
*   <span data-ttu-id="d217c-176">コンピューターのキーボード操作がデバイスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="d217c-176">Keystrokes on your computer are sent to the device.</span></span>  
*   <span data-ttu-id="d217c-177">ピンチジェスチャをシミュレートするには、 `Shift` ドラッグ中にホールドします。</span><span class="sxs-lookup"><span data-stu-id="d217c-177">To simulate a pinch gesture, hold `Shift` while dragging.</span></span>  
*   <span data-ttu-id="d217c-178">スクロールするには、トラックパッドまたはマウスホイール、またはマウスポインターでフリックを使用します。</span><span class="sxs-lookup"><span data-stu-id="d217c-178">To scroll, use your trackpad or mouse wheel, or fling with your mouse pointer.</span></span>

> [!NOTE]
> <span data-ttu-id="d217c-179">次のヒントを使用して、screencast を支援してください。</span><span class="sxs-lookup"><span data-stu-id="d217c-179">Use the following tips to help you screencast.</span></span>  
> 
> *   <span data-ttu-id="d217c-180">スクリーンキャストは、ページコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="d217c-180">Screencasts only display page content.</span></span>  <span data-ttu-id="d217c-181">Screencast の透明部分は、Microsoft Edge のアドレスバー、Android ステータスバー、Android キーボードなどのデバイスインターフェイスを表します。</span><span class="sxs-lookup"><span data-stu-id="d217c-181">Transparent portions of the screencast represent device interfaces, such as the Microsoft Edge address bar, the Android status bar, or the Android keyboard.</span></span>  
> *   <span data-ttu-id="d217c-182">スクリーンキャストはフレームレートに悪影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="d217c-182">Screencasts negatively affect frame rates.</span></span>  <span data-ttu-id="d217c-183">スクロールまたはアニメーションの計測中に screencasting を無効にすると、ページのパフォーマンスがより正確に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d217c-183">Disable screencasting while measuring scrolls or animations to get a more accurate picture of the performance of your page.</span></span>  
> *   <span data-ttu-id="d217c-184">Android デバイスの画面がロックされている場合、screencast のコンテンツは表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="d217c-184">If your Android device screen locks, the content of your screencast disappears.</span></span>  <span data-ttu-id="d217c-185">Android デバイスの画面のロックを解除して、screencast を自動的に再開します。</span><span class="sxs-lookup"><span data-stu-id="d217c-185">Unlock your Android device screen to automatically resume the screencast.</span></span>  

<!-- image links -->  

[ImageSelectElementIcon]: /microsoft-edge/devtools-guide-chromium/media/select-element-icon.msft.png  
[ImageToggleScreencastIcon]: /microsoft-edge/devtools-guide-chromium/media/toggle-screencast-icon.msft.png  

<!--[ImageRemoteDebugging]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging--remote-debugging.msft.png "old Figure 1:  Remote Debugging lets you inspect a page running on an Android device from your development machine"  -->  
<!--[ImageEdgeInspect]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-edge-inspect-no-targets.msft.png "Figure 1: The edge://inspect page in Microsoft Edge"  -->  
<!--[ImageAndroidPermissionPrompt]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-android-permissions-prompt.msft.png "Figure 2: The Allow USB Debugging permission prompt on an Android device"  -->  
<!--[ImageConnectedRemoteDevice]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-edge-inspect-with-targets.msft.png "Figure 3: A connected remote device"  -->  
<!-- [ImageReload]:  /microsoft-edge/devtools-guide-chromium/media/remote-debugging-edge-inspect-with-targets-buttons.msft.png "Figure 4: The buttons for focusing, reloading, or closing a tab"  -->  
<!--[ImageUnknownDevice]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging--unknown-device.msft.png "old Figure 4:  The Remote Devices tab has successfully detected an unknown device that is pending authorization"  -->  

<!-- links -->  

[AndroidUSBDrivers]: https://developer.android.com/tools/extras/oem-usb.html "OEM USB ドライバーをインストールする |Android 開発者"  

<!-- [GitHubWebFundamentalsNewIssue]: https://github.com/Alphabet/webfundamentals/issues/new?title=[Remote%20Debugging] "GitHub - Web Fundamentals - New Issue"  -->  
[StackOverflowDevicesNotDetected]: https://stackoverflow.com/questions/21925992 "devtools デバイスで、電源に接続されているときにデバイスが検出されません"-スタックオーバーフロー "  

[StackExchangeGalaxyS4DoesNotShowDialogBox]: https://android.stackexchange.com/questions/101933 "adb-Android ファンスタック交換"  

> [!NOTE]
> <span data-ttu-id="d217c-189">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="d217c-189">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="d217c-190">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="d217c-190">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="d217c-192">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="d217c-192">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
