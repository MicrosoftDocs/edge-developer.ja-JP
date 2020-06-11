---
title: Android デバイスのリモートデバッグの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c77633c4844f0e576b7dff6574000a78c8c083da
ms.sourcegitcommit: f010f43604bd4363af6827f79dbc071b9afcb667
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2020
ms.locfileid: "10708537"
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

# <span data-ttu-id="c7cb1-103">Android デバイスのリモートデバッグの概要</span><span class="sxs-lookup"><span data-stu-id="c7cb1-103">Get started with remote debugging Android devices</span></span>  

<span data-ttu-id="c7cb1-104">Windows または macOS コンピューターから Android デバイス上のリモートデバッグライブコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-104">Remote debug live content on an Android device from your Windows or macOS computer.</span></span>  <span data-ttu-id="c7cb1-105">次のチュートリアルページでは、次の操作を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-105">The following tutorial page teaches you how to complete the following actions.</span></span>  

*   <span data-ttu-id="c7cb1-106">リモートデバッグ用に Android デバイスをセットアップし、開発用コンピューターから検出します。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-106">Set up your Android device for remote debugging, and discover it from your development machine.</span></span>  
*   <span data-ttu-id="c7cb1-107">開発用コンピューターから Android デバイスのライブコンテンツを検査およびデバッグします。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-107">Inspect and debug live content on your Android device from your development machine.</span></span>  
*   <span data-ttu-id="c7cb1-108">Android デバイスのコンテンツを開発用コンピューターの DevTools インスタンスに Screencast します。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-108">Screencast content from your Android device onto a DevTools instance on your development machine.</span></span>  

<!--  
:::image type="complex" source="../media/remote-debugging--remote-debugging.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging--remote-debugging.msft.png":::
   old Figure 1.  Remote Debugging lets you inspect a page running on an Android device from your development machine  
:::image-end:::  
-->  

> [!NOTE]
> <span data-ttu-id="c7cb1-109">IOS デバイスでの Microsoft Edge アプリのリモートデバッグは、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-109">Remote debugging the Microsoft Edge app on iOS devices is not currently supported.</span></span>  <span data-ttu-id="c7cb1-110">次のガイドでは、特に Android デバイスでの Microsoft Edge のリモートデバッグに重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-110">The following guide is specifically focused on remote debugging Microsoft Edge on Android devices.</span></span>
> <span data-ttu-id="c7cb1-111">MacOS デバイスをお使いの場合は、 [Brightcove のデバッグガイド][BrightcoveSupportDebuggingMobileDevices]に従って、Safari を使用して iOS デバイスで Microsoft Edge をリモートでデバッグしてください。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-111">If you have a macOS device, follow the [Brightcove Debugging guide][BrightcoveSupportDebuggingMobileDevices] to remotely debug Microsoft Edge on an iOS device using Safari.</span></span>  <span data-ttu-id="c7cb1-112">Safari の Web 検査ツールの詳細については、「 [Safari Web 開発ツール][AppleDeveloperSafariTools]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-112">For more information about the Web Inspector tool in Safari, see [Safari Web Development Tools][AppleDeveloperSafariTools].</span></span>  

## <span data-ttu-id="c7cb1-113">手順 1: Android デバイスを見つける</span><span class="sxs-lookup"><span data-stu-id="c7cb1-113">Step 1: Discover your Android device</span></span>  

<span data-ttu-id="c7cb1-114">以下のワークフローは、ほとんどのユーザーに適しています。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-114">The workflow below works for most users.</span></span>  <span data-ttu-id="c7cb1-115">詳細については、「開発[ツールで Android デバイスが検出されていない場合のトラブルシューティング](#troubleshooting-devtools-is-not-detecting-the-android-device)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-115">For more help, see the [Troubleshooting: DevTools is not detecting the Android device](#troubleshooting-devtools-is-not-detecting-the-android-device) section.</span></span>  

1.  <span data-ttu-id="c7cb1-116">Android で [**開発者向けオプション**] 画面を開きます。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-116">Open the **Developer Options** screen on your Android.</span></span>  <span data-ttu-id="c7cb1-117">詳細については、「[デバイスの開発者向けオプションを構成する][AndroidDeveloperStudioDevOptions]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-117">For more information, see [Configure On-Device Developer Options][AndroidDeveloperStudioDevOptions].</span></span>  
1.  <span data-ttu-id="c7cb1-118">[ **USB デバッグを有効にする**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-118">Select **Enable USB Debugging**.</span></span>  
1.  <span data-ttu-id="c7cb1-119">開発用コンピューターで、Microsoft Edge を開きます。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-119">On your development machine, open Microsoft Edge.</span></span>  
1.  <span data-ttu-id="c7cb1-120">`edge://inspect`Microsoft Edge でページに移動します。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-120">Navigate to the `edge://inspect` page in Microsoft Edge.</span></span>  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-no-targets.msft.png" alt-text="Microsoft Edge の [edge://inspect] ページ" lightbox="../media/remote-debugging-edge-inspect-no-targets.msft.png":::
       <span data-ttu-id="c7cb1-122">図 1. </span><span class="sxs-lookup"><span data-stu-id="c7cb1-122">Figure 1.</span></span>  <span data-ttu-id="c7cb1-123">`edge://inspect`Microsoft Edge のページ</span><span class="sxs-lookup"><span data-stu-id="c7cb1-123">The `edge://inspect` page in Microsoft Edge</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c7cb1-124">USB ケーブルを使って、Android デバイスを開発用コンピューターに直接接続します。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-124">Connect your Android device directly to your development machine using a USB cable.</span></span>  <span data-ttu-id="c7cb1-125">初めて接続しようとしたときに、一般的に、不明なデバイスを検出するための DevTools のプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-125">The first time you try to connect, you usually see prompt about DevTools detecting an unknown device.</span></span>  <span data-ttu-id="c7cb1-126">Android デバイスで [ **USB のデバッグを許可**] プロンプトを承諾します。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-126">Accept the **Allow USB Debugging** permission prompt on your Android device.</span></span>  
    
    :::image type="complex" source="../media/remote-debugging-android-permissions-prompt.msft.png" alt-text="Android デバイスでの USB デバッグの許可プロンプト" lightbox="../media/remote-debugging-android-permissions-prompt.msft.png":::
       <span data-ttu-id="c7cb1-128">図 2. </span><span class="sxs-lookup"><span data-stu-id="c7cb1-128">Figure 2.</span></span>  <span data-ttu-id="c7cb1-129">Android デバイスでの**USB デバッグ**の許可プロンプト</span><span class="sxs-lookup"><span data-stu-id="c7cb1-129">The **Allow USB Debugging** permission prompt on an Android device</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c7cb1-130">Android デバイスのモデル名が表示される場合は、Microsoft Edge でデバイスへの接続が正常に確立されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-130">If you see the model name of your Android device, then Microsoft Edge has successfully established the connection to your device.</span></span>  <span data-ttu-id="c7cb1-131">[手順 2](#step-2-debug-content-on-your-android-device-from-your-development-machine)のセクションに進みます。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-131">Continue to the [Step 2](#step-2-debug-content-on-your-android-device-from-your-development-machine) section.</span></span>  
    
    <!--  
    :::image type="complex" source="../media/remote-debugging--unknown-device.msft.png" alt-text="The Remote Devices tab has successfully detected an unknown device that is pending authorization" lightbox="../media/remote-debugging--unknown-device.msft.png":::
       old Figure 4.  The **Remote Devices** tab has successfully detected an unknown device that is pending authorization  
    :::image-end:::
    -->  
    
### <span data-ttu-id="c7cb1-132">トラブルシューティング: DevTools で Android デバイスが検出されない</span><span class="sxs-lookup"><span data-stu-id="c7cb1-132">Troubleshooting: DevTools is not detecting the Android device</span></span>  

<span data-ttu-id="c7cb1-133">以下のヒントは、お使いのハードウェアの適切な設定のトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-133">Use the following tips to help you troubleshoot the correct settings for your hardware.</span></span>  

*   <span data-ttu-id="c7cb1-134">USB ハブを使っている場合は、Android デバイスを開発用コンピューターに直接接続してみてください。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-134">If you are using a USB hub, try connecting your Android device directly to your development machine.</span></span>  
*   <span data-ttu-id="c7cb1-135">Android デバイスと開発マシンの間で USB ケーブルを外して、USB ケーブルを再接続してみてください。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-135">Try unplugging the USB cable between your Android device and development machine, and then re-plugging your USB cable.</span></span>  <span data-ttu-id="c7cb1-136">Android および開発マシンの画面のロックが解除されている状態で、タスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-136">Complete the task while your Android and development machine screens are unlocked.</span></span>  
*   <span data-ttu-id="c7cb1-137">USB ケーブルが動作していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-137">Make sure that your USB cable works.</span></span>  <span data-ttu-id="c7cb1-138">開発用コンピューターから Android デバイスのファイルを検査できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-138">You should be able to inspect files on your Android device from your development machine.</span></span>  

<span data-ttu-id="c7cb1-139">ソフトウェアが正しく設定されているかどうかを確認するには、次のヒントを参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-139">Use the following tips to help you verify that your software is set up correctly.</span></span>  

*   <span data-ttu-id="c7cb1-140">開発用コンピューターで Windows を実行している場合は、Android デバイスの USB ドライバーを手動でインストールしてみてください。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-140">If your development machine is running Windows, try manually installing the USB drivers for your Android device.</span></span>  <span data-ttu-id="c7cb1-141">詳細については、「 [OEM USB ドライバーをインストール][AndroidDeveloperToolsOemUsb]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-141">For more information, see [Install OEM USB Drivers][AndroidDeveloperToolsOemUsb].</span></span>  
*   <span data-ttu-id="c7cb1-142">Windows と Android デバイスの組み合わせ (特に Samsung \) には、追加の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-142">Some combinations of Windows and Android devices \(especially Samsung\) require additional settings.</span></span>  <span data-ttu-id="c7cb1-143">詳細については、「[デバイスに接続してもデバイスが検出されない][Stackoverflow21925992]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-143">For more information, see [DevTools Devices does not detect device when plugged in][Stackoverflow21925992].</span></span>  

<span data-ttu-id="c7cb1-144">Android デバイスで**USB デバッグを許可**するかどうかを確認するには、次のヒントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-144">Use the following tips to help you troubleshoot not seeing the **Allow USB Debugging** prompt on your Android device.</span></span>  

*   <span data-ttu-id="c7cb1-145">DevTools が開発用コンピューターに集中していて、Android のホーム画面が表示されているときに、USB ケーブルを切断してから接続し直す。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-145">Disconnecting and then re-connecting the USB cable while DevTools is in focus on your development machine and your Android homescreen is showing.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="c7cb1-146">Android または開発用コンピューターの画面がロックされている場合、このプロンプトが表示されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-146">You may not see the prompt if your Android or development machine screens are locked.</span></span>  

*   <span data-ttu-id="c7cb1-147">Android デバイスと開発用コンピューターの表示設定を更新して、それぞれがスリープ状態にならないようにします。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-147">Updating the display settings for your Android device and development machine so that each never goes to sleep.</span></span>  
*   <span data-ttu-id="c7cb1-148">Android の USB モードを PTP に設定します。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-148">Setting the USB mode for Android to PTP.</span></span>  <span data-ttu-id="c7cb1-149">詳細については、「 [Galaxy S4 で [USB デバッグの承認] ダイアログボックスが表示されない][StackexchangeAndroid101933]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-149">For more information, see [Galaxy S4 does not show Authorize USB debugging dialog box][StackexchangeAndroid101933].</span></span>  
*   <span data-ttu-id="c7cb1-150">Android デバイスの [**開発者オプション**] 画面で [ **USB デバッグ承認の取り消し**] を選択して、新しい状態にリセットします。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-150">Select **Revoke USB Debugging Authorizations** from the **Developer Options** screen on your Android device to reset it to a fresh state.</span></span>  

<span data-ttu-id="c7cb1-151">このページに記載されていない解決策を見つけた場合や、Devtools デバイスでスタックオーバーフローに接続しても[デバイスが検出][Stackoverflow21925992]されない場合は、スタックオーバーフローの質問にソリューションを追加してください。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-151">If you find a solution that is not mentioned on this page or in [DevTools Devices does not detect device when plugged in][Stackoverflow21925992] on Stack Overflow, please add your solution to the Stack Overflow question</span></span><!--, or [open an issue in the webfundamentals repository][GitHubWebFundamentalsNewIssue]--><span data-ttu-id="c7cb1-152">!</span><span class="sxs-lookup"><span data-stu-id="c7cb1-152">!</span></span>  

## <span data-ttu-id="c7cb1-153">手順 2: 開発用コンピューターから Android デバイスのコンテンツをデバッグする</span><span class="sxs-lookup"><span data-stu-id="c7cb1-153">Step 2: Debug content on your Android device from your development machine</span></span>  

1.  <span data-ttu-id="c7cb1-154">Android デバイスで Microsoft Edge を開きます。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-154">Open Microsoft Edge on your Android device.</span></span>  
1.  <span data-ttu-id="c7cb1-155">ページから `edge://inspect` 、Android デバイスのモデル名の後にデバイスのシリアル番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-155">From the `edge://inspect` page, you see the model name of your Android device, followed by the device serial number.</span></span>  <span data-ttu-id="c7cb1-156">その下で、デバイス上で実行されている Microsoft Edge のバージョン番号がかっこで囲まれていることが確認できます。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-156">Below that, you should see the version of Microsoft Edge running on the device, with the version number in parentheses.</span></span>  <span data-ttu-id="c7cb1-157">各開いている Microsoft Edge タブには、一意のセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-157">Each open Microsoft Edge tab gets a unique section.</span></span>  <span data-ttu-id="c7cb1-158">セクションからそのタブを操作できます。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-158">You may interact with that tab from a section.</span></span>  <!--If there are any apps using WebView, you see a section for each of those apps, too.  --><!--In [**Figure 5**](#figure-5) there are no tabs or WebViews open.  -->  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets.msft.png" alt-text="接続されているリモートデバイス" lightbox="../media/remote-debugging-edge-inspect-with-targets.msft.png":::
       <span data-ttu-id="c7cb1-160">図 3. </span><span class="sxs-lookup"><span data-stu-id="c7cb1-160">Figure 3.</span></span>  <span data-ttu-id="c7cb1-161">接続されているリモートデバイス</span><span class="sxs-lookup"><span data-stu-id="c7cb1-161">A connected remote device</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c7cb1-162">[**開く] タブ**の [url] テキストボックスに url を入力し、[**開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-162">In the **Open tab with url** text box, enter a URL and then select **Open**.</span></span>  <span data-ttu-id="c7cb1-163">Android デバイスの新しいタブにページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-163">The page opens in a new tab on your Android device.</span></span>  
1.  <span data-ttu-id="c7cb1-164">直前に開いた URL の横にある [**検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-164">Select **inspect** next to the URL that you just opened.</span></span>  <span data-ttu-id="c7cb1-165">新しい DevTools インスタンスが開きます。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-165">A new DevTools instance opens.</span></span>  

<!-- The version of Microsoft Edge running on your Android device determines the version of DevTools that opens on your development machine.  
    So, if your Android device is running a very old version of Microsoft Edge, the DevTools instance may look very different than what you are used to.   -->

### <span data-ttu-id="c7cb1-166">その他のアクション: タブにフォーカス、再読み込み、または閉じる</span><span class="sxs-lookup"><span data-stu-id="c7cb1-166">More actions: focus, reload, or close a tab</span></span>  

<span data-ttu-id="c7cb1-167">フォーカスタブ、再読み込み、または閉じるタブの横にある [**フォーカス] タブ**、[**再読み込み**]、または [**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-167">Select **focus tab**, **reload**, or **close** next to the tab that you want to focus, reload, or close.</span></span>  

:::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png" alt-text="タブをフォーカス、再読み込み、または閉じるためのボタン" lightbox="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png":::
   <span data-ttu-id="c7cb1-169">図 4: </span><span class="sxs-lookup"><span data-stu-id="c7cb1-169">Figure 4.</span></span>  <span data-ttu-id="c7cb1-170">タブをフォーカス、再読み込み、または閉じるためのボタン</span><span class="sxs-lookup"><span data-stu-id="c7cb1-170">The buttons for focusing, reloading, or closing a tab</span></span>  
:::image-end:::  

### <span data-ttu-id="c7cb1-171">要素を検査する</span><span class="sxs-lookup"><span data-stu-id="c7cb1-171">Inspect elements</span></span>  

<span data-ttu-id="c7cb1-172">DevTools インスタンスの**要素**パネルに移動し、要素の上にマウスポインターを置いて、Android デバイスのビューポートでその要素を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-172">Go to the **Elements** panel of your DevTools instance, and hover over an element to highlight it in the viewport of your Android device.</span></span>  

<span data-ttu-id="c7cb1-173">Android デバイスの画面で要素を選択して、[**要素**] パネルで選ぶこともできます。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-173">You may also select an element on your Android device screen to select it in the **Elements** panel.</span></span>  <span data-ttu-id="c7cb1-174">DevTools インスタンスで [**要素**の選択] アイコンを選択し、 ![ ][ImageSelectElementIcon] Android デバイス画面で要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-174">Select **Select Element** ![Select Element][ImageSelectElementIcon] icon on your DevTools instance, and then select the element on your Android device screen.</span></span>  

> [!NOTE]
> <span data-ttu-id="c7cb1-175">最初の選択の後に **[要素の選択]** が無効になっているため、この機能を使うたびに有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-175">**Select Element** is disabled after the first selection, so you must re-enable it every time you want to use the feature.</span></span>  

### <span data-ttu-id="c7cb1-176">Android の画面を開発用コンピューターに Screencast</span><span class="sxs-lookup"><span data-stu-id="c7cb1-176">Screencast your Android screen to your development machine</span></span>  

<span data-ttu-id="c7cb1-177">[ **Screencast** ![ トグル Screencast] を選択し ][ImageToggleScreencastIcon] て、Devtools インスタンスで Android デバイスのコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-177">Select **Toggle Screencast** ![Toggle Screencast][ImageToggleScreencastIcon] icon to view the content of your Android device in your DevTools instance.</span></span>  

<span data-ttu-id="c7cb1-178">Screencast は次の方法で操作できます。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-178">You are able to interact with the screencast in the following ways.</span></span>  

*   <span data-ttu-id="c7cb1-179">クリックは、デバイスで適切なタッチイベントを発生させるために、タップに変換されます。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-179">Clicks are translated into taps, firing proper touch events on the device.</span></span>  
*   <span data-ttu-id="c7cb1-180">コンピューターのキーボード操作がデバイスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-180">Keystrokes on your computer are sent to the device.</span></span>  
*   <span data-ttu-id="c7cb1-181">ピンチジェスチャをシミュレートするには、 `Shift` ドラッグ中にホールドします。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-181">To simulate a pinch gesture, hold `Shift` while dragging.</span></span>  
*   <span data-ttu-id="c7cb1-182">スクロールするには、トラックパッドまたはマウスホイール、またはマウスポインターでフリックを使用します。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-182">To scroll, use your trackpad or mouse wheel, or fling with your mouse pointer.</span></span>

> [!NOTE]
> <span data-ttu-id="c7cb1-183">次のヒントを使用して、screencast を支援してください。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-183">Use the following tips to help you screencast.</span></span>  
> 
> *   <span data-ttu-id="c7cb1-184">スクリーンキャストは、ページコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-184">Screencasts only display page content.</span></span>  <span data-ttu-id="c7cb1-185">Screencast の透明部分は、Microsoft Edge のアドレスバー、Android ステータスバー、Android キーボードなどのデバイスインターフェイスを表します。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-185">Transparent portions of the screencast represent device interfaces, such as the Microsoft Edge address bar, the Android status bar, or the Android keyboard.</span></span>  
> *   <span data-ttu-id="c7cb1-186">スクリーンキャストはフレームレートに悪影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-186">Screencasts negatively affect frame rates.</span></span>  <span data-ttu-id="c7cb1-187">スクロールまたはアニメーションの計測中に screencasting を無効にすると、ページのパフォーマンスがより正確に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-187">Disable screencasting while measuring scrolls or animations to get a more accurate picture of the performance of your page.</span></span>  
> *   <span data-ttu-id="c7cb1-188">Android デバイスの画面がロックされている場合、screencast のコンテンツは表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-188">If your Android device screen locks, the content of your screencast disappears.</span></span>  <span data-ttu-id="c7cb1-189">Android デバイスの画面のロックを解除して、screencast を自動的に再開します。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-189">Unlock your Android device screen to automatically resume the screencast.</span></span>  

<!-- image links -->  

[ImageSelectElementIcon]: /microsoft-edge/devtools-guide-chromium/media/select-element-icon.msft.png  
[ImageToggleScreencastIcon]: /microsoft-edge/devtools-guide-chromium/media/toggle-screencast-icon.msft.png  

<!-- links -->  

[AndroidDeveloperStudioDevOptions]: https://developer.android.com/studio/debug/dev-options "デバイス開発者向けオプションを構成する |Android 開発者"  
[AndroidDeveloperToolsOemUsb]: https://developer.android.com/tools/extras/oem-usb.html "OEM USB ドライバーをインストールする |Android 開発者"  

[AppleDeveloperSafariTools]: https://developer.apple.com/safari/tools "Safari Web 開発ツール |Apple 開発者"  

[BrightcoveSupportDebuggingMobileDevices]: https://support.brightcove.com/debugging-mobile-devices "モバイルデバイスでのデバッグ |Brightcove サポート"  

<!-- [GitHubWebFundamentalsNewIssue]: https://github.com/Alphabet/webfundamentals/issues/new?title=[Remote%20Debugging] "GitHub - Web Fundamentals - New Issue"  -->  

[StackexchangeAndroid101933]: https://android.stackexchange.com/questions/101933 "adb-Android ファンスタック交換"  

[Stackoverflow21925992]: https://stackoverflow.com/questions/21925992 "デバイスが電源に接続されているときにデバイスが検出されない"  

> [!NOTE]
> <span data-ttu-id="c7cb1-196">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-196">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c7cb1-197">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-197">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="c7cb1-199">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="c7cb1-199">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
