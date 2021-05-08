---
description: Android デバイス上のリモート デバッグライブ コンテンツは、Windows macOS コンピューターから行います。
title: Android デバイスのリモート デバッグを開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/25/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: d69fd4832991826c76f47daea399bdd89e981bb4
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461214"
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
# <a name="get-started-with-remote-debugging-android-devices"></a><span data-ttu-id="1f34f-104">Android デバイスのリモート デバッグを開始する</span><span class="sxs-lookup"><span data-stu-id="1f34f-104">Get started with remote debugging Android devices</span></span>  

<span data-ttu-id="1f34f-105">Android デバイス上のリモート デバッグライブ コンテンツは、Windows macOS コンピューターから行います。</span><span class="sxs-lookup"><span data-stu-id="1f34f-105">Remote debug live content on an Android device from your Windows or macOS computer.</span></span>  <span data-ttu-id="1f34f-106">次のチュートリアル ページでは、次のアクションを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-106">The following tutorial page teaches you how to complete the following actions.</span></span>  

*   <span data-ttu-id="1f34f-107">リモート デバッグ用に Android デバイスをセットアップし、開発マシンから検出します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-107">Set up your Android device for remote debugging, and discover it from your development machine.</span></span>  
*   <span data-ttu-id="1f34f-108">開発マシンから Android デバイス上のライブ コンテンツを検査およびデバッグします。</span><span class="sxs-lookup"><span data-stu-id="1f34f-108">Inspect and debug live content on your Android device from your development machine.</span></span>  
*   <span data-ttu-id="1f34f-109">Android デバイスから開発マシンの DevTools インスタンスにスクリーンキャストされたコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="1f34f-109">Screencast content from your Android device onto a DevTools instance on your development machine.</span></span>  

<!--  
:::image type="complex" source="../media/remote-debugging--remote-debugging.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging--remote-debugging.msft.png":::
   old Figure 1.  Remote Debugging lets you inspect a page running on an Android device from your development machine  
:::image-end:::  
-->  

> [!NOTE]
> <span data-ttu-id="1f34f-110">iOS デバイスMicrosoft Edgeアプリのリモート デバッグは現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1f34f-110">Remote debugging the Microsoft Edge app on iOS devices is not currently supported.</span></span>  <span data-ttu-id="1f34f-111">次のガイドでは、Android デバイスでのリモート デバッグMicrosoft Edge特に重点を置きます。</span><span class="sxs-lookup"><span data-stu-id="1f34f-111">The following guide is specifically focused on remote debugging Microsoft Edge on Android devices.</span></span>
> <span data-ttu-id="1f34f-112">macOS デバイスをお持ちの場合は[、Brightcove Debuging][BrightcoveSupportDebuggingMobileDevices]ガイドに従って、Safari を使用して iOS デバイスMicrosoft Edgeリモート デバッグを行います。</span><span class="sxs-lookup"><span data-stu-id="1f34f-112">If you have a macOS device, follow the [Brightcove Debugging guide][BrightcoveSupportDebuggingMobileDevices] to remotely debug Microsoft Edge on an iOS device using Safari.</span></span>  <span data-ttu-id="1f34f-113">Safari の Web インスペクター ツールの詳細については [、「Safari Web 開発ツール」に移動します][AppleDeveloperSafariTools]。</span><span class="sxs-lookup"><span data-stu-id="1f34f-113">For more information about the Web Inspector tool in Safari, navigate to [Safari Web Development Tools][AppleDeveloperSafariTools].</span></span>  

## <a name="step-1-discover-your-android-device"></a><span data-ttu-id="1f34f-114">手順 1: Android デバイスを検出する</span><span class="sxs-lookup"><span data-stu-id="1f34f-114">Step 1: Discover your Android device</span></span>  

<span data-ttu-id="1f34f-115">以下のワークフローは、ほとんどのユーザーに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-115">The workflow below works for most users.</span></span>  <span data-ttu-id="1f34f-116">詳細については、「トラブルシューティング: [DevTools](#troubleshooting-devtools-is-not-detecting-the-android-device) で Android デバイスが検出されない」セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-116">For more help, navigate to [Troubleshooting: DevTools is not detecting the Android device](#troubleshooting-devtools-is-not-detecting-the-android-device) section.</span></span>  

1.  <span data-ttu-id="1f34f-117">Android の **[開発者オプション]** 画面を開きます。</span><span class="sxs-lookup"><span data-stu-id="1f34f-117">Open the **Developer Options** screen on your Android.</span></span>  <span data-ttu-id="1f34f-118">詳細については、「Configure [On-Device Developer Options」に移動します][AndroidDeveloperStudioDevOptions]。</span><span class="sxs-lookup"><span data-stu-id="1f34f-118">For more information, navigate to [Configure On-Device Developer Options][AndroidDeveloperStudioDevOptions].</span></span>  
1.  <span data-ttu-id="1f34f-119">[USB **デバッグを有効にする] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1f34f-119">Choose **Enable USB Debugging**.</span></span>  
1.  <span data-ttu-id="1f34f-120">開発マシンで、コンピューターを開Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="1f34f-120">On your development machine, open Microsoft Edge.</span></span>  
1.  <span data-ttu-id="1f34f-121">ページ内の `edge://inspect` ページに移動Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="1f34f-121">Navigate to the `edge://inspect` page in Microsoft Edge.</span></span>  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-no-targets.msft.png" alt-text="[edge://inspect] ページMicrosoft Edge" lightbox="../media/remote-debugging-edge-inspect-no-targets.msft.png":::
       <span data-ttu-id="1f34f-123">図 1.</span><span class="sxs-lookup"><span data-stu-id="1f34f-123">Figure 1.</span></span>  <span data-ttu-id="1f34f-124">[ `edge://inspect` ページ] のMicrosoft Edge</span><span class="sxs-lookup"><span data-stu-id="1f34f-124">The `edge://inspect` page in Microsoft Edge</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1f34f-125">Connect USB ケーブルを使用して、Android デバイスを開発マシンに直接接続します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-125">Connect your Android device directly to your development machine using a USB cable.</span></span>  <span data-ttu-id="1f34f-126">初めて接続を試みた場合は、不明なデバイスを検出する DevTools に関するプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f34f-126">The first time you try to connect, a prompt should be displayed about DevTools detecting an unknown device.</span></span>  <span data-ttu-id="1f34f-127">Android デバイスで **[USB デバッグを許可する** ] アクセス許可のプロンプトに同意します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-127">Accept the **Allow USB Debugging** permission prompt on your Android device.</span></span>  
    
    :::image type="complex" source="../media/remote-debugging-android-permissions-prompt.msft.png" alt-text="Android デバイスで [USB デバッグを許可する] アクセス許可のプロンプト" lightbox="../media/remote-debugging-android-permissions-prompt.msft.png":::
       <span data-ttu-id="1f34f-129">図 2.</span><span class="sxs-lookup"><span data-stu-id="1f34f-129">Figure 2.</span></span>  <span data-ttu-id="1f34f-130">Android **デバイスで [USB デバッグを** 許可する] アクセス許可のプロンプト</span><span class="sxs-lookup"><span data-stu-id="1f34f-130">The **Allow USB Debugging** permission prompt on an Android device</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1f34f-131">Android デバイスのモデル名が表示されている場合はMicrosoft Edgeデバイスへの接続が正常に確立されています。</span><span class="sxs-lookup"><span data-stu-id="1f34f-131">If the model name of your Android device is displayed, then Microsoft Edge has successfully established the connection to your device.</span></span>  <span data-ttu-id="1f34f-132">[手順 [2] セクションに進](#step-2-debug-content-on-your-android-device-from-your-development-machine) みます。</span><span class="sxs-lookup"><span data-stu-id="1f34f-132">Continue to the [Step 2](#step-2-debug-content-on-your-android-device-from-your-development-machine) section.</span></span>  
    
    <!--  
    :::image type="complex" source="../media/remote-debugging--unknown-device.msft.png" alt-text="The Remote Devices tab has successfully detected an unknown device that is pending authorization" lightbox="../media/remote-debugging--unknown-device.msft.png":::
       old Figure 4.  The **Remote Devices** tab has successfully detected an unknown device that is pending authorization  
    :::image-end:::
    -->  
    
### <a name="troubleshooting-devtools-is-not-detecting-the-android-device"></a><span data-ttu-id="1f34f-133">トラブルシューティング: DevTools が Android デバイスを検出していない</span><span class="sxs-lookup"><span data-stu-id="1f34f-133">Troubleshooting: DevTools is not detecting the Android device</span></span>  

<span data-ttu-id="1f34f-134">ハードウェアの正しい設定のトラブルシューティングに役立つヒントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-134">Use the following tips to help you troubleshoot the correct settings for your hardware.</span></span>  

*   <span data-ttu-id="1f34f-135">USB ハブを使用している場合は、Android デバイスを開発マシンに直接接続してみてください。</span><span class="sxs-lookup"><span data-stu-id="1f34f-135">If you are using a USB hub, try connecting your Android device directly to your development machine.</span></span>  
*   <span data-ttu-id="1f34f-136">Android デバイスと開発コンピューターの間で USB ケーブルを抜いてから、USB ケーブルを再接続してみてください。</span><span class="sxs-lookup"><span data-stu-id="1f34f-136">Try unplugging the USB cable between your Android device and development machine, and then re-plugging your USB cable.</span></span>  <span data-ttu-id="1f34f-137">Android と開発コンピューターの画面のロックが解除されている間にタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-137">Complete the task while your Android and development machine screens are unlocked.</span></span>  
*   <span data-ttu-id="1f34f-138">USB ケーブルが動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f34f-138">Make sure that your USB cable works.</span></span>  <span data-ttu-id="1f34f-139">開発マシンから Android デバイス上のファイルを検査できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f34f-139">You should be able to inspect files on your Android device from your development machine.</span></span>  

<span data-ttu-id="1f34f-140">ソフトウェアが正しくセットアップされていることを確認するには、次のヒントを使用します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-140">Use the following tips to help you verify that your software is set up correctly.</span></span>  

*   <span data-ttu-id="1f34f-141">開発マシンが実行中の場合Windows、Android デバイスの USB ドライバーを手動でインストールしてみてください。</span><span class="sxs-lookup"><span data-stu-id="1f34f-141">If your development machine is running Windows, try manually installing the USB drivers for your Android device.</span></span>  <span data-ttu-id="1f34f-142">詳細については [、「OEM USB ドライバーのインストール」に移動します][AndroidDeveloperToolsOemUsb]。</span><span class="sxs-lookup"><span data-stu-id="1f34f-142">For more information, navigate to [Install OEM USB Drivers][AndroidDeveloperToolsOemUsb].</span></span>  
*   <span data-ttu-id="1f34f-143">一部の組みWindows Android デバイス \(特に Samsung\) では、追加の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="1f34f-143">Some combinations of Windows and Android devices \(especially Samsung\) require additional settings.</span></span>  <span data-ttu-id="1f34f-144">詳細については、「DevTools Devices に移動しても、接続時 [にデバイスが検出されない」に移動します][Stackoverflow21925992]。</span><span class="sxs-lookup"><span data-stu-id="1f34f-144">For more information, navigate to [DevTools Devices does not detect device when plugged in][Stackoverflow21925992].</span></span>  

<span data-ttu-id="1f34f-145">次のヒントを使用して、Android デバイスに **[USB** デバッグを許可する] プロンプトが表示されない場合のトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1f34f-145">Use the following tips to help you troubleshoot if the **Allow USB Debugging** prompt is not displayed on your Android device.</span></span>  

*   <span data-ttu-id="1f34f-146">DevTools が開発マシンに焦点を当て、Android のホームスクリーンが表示されている間に、USB ケーブルを切断してから再接続します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-146">Disconnecting and then re-connecting the USB cable while DevTools is in focus on your development machine and your Android homescreen is showing.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="1f34f-147">Android または開発コンピューターの画面がロックされている場合、プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f34f-147">The prompt is displayed if your Android or development machine screens are locked.</span></span>  

*   <span data-ttu-id="1f34f-148">Android デバイスと開発マシンの表示設定を更新して、それぞれがスリープ状態になじむのを行います。</span><span class="sxs-lookup"><span data-stu-id="1f34f-148">Updating the display settings for your Android device and development machine so that each never goes to sleep.</span></span>  
*   <span data-ttu-id="1f34f-149">Android の USB モードを PTP に設定します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-149">Setting the USB mode for Android to PTP.</span></span>  <span data-ttu-id="1f34f-150">詳細については、[Usb デバッグの承認] ダイアログ ボックスが表示されない [[Galaxy S4] に移動します][StackexchangeAndroid101933]。</span><span class="sxs-lookup"><span data-stu-id="1f34f-150">For more information, navigate to [Galaxy S4 does not show Authorize USB debugging dialog box][StackexchangeAndroid101933].</span></span>  
*   <span data-ttu-id="1f34f-151">Android**デバイスの [開発者オプション]** 画面から [USB デバッグの承認を取り消す] を選択して、新しい状態にリセットします。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1f34f-151">Choose **Revoke USB Debugging Authorizations** from the **Developer Options** screen on your Android device to reset it to a fresh state.</span></span>  

<span data-ttu-id="1f34f-152">このページまたは [DevTools デバイス][Stackoverflow21925992] でスタック オーバーフローに接続してもデバイスが検出されないソリューションを見つけた場合は、ソリューションをスタック オーバーフローの質問に追加してください</span><span class="sxs-lookup"><span data-stu-id="1f34f-152">If you find a solution that is not mentioned on this page or in [DevTools Devices does not detect device when plugged in][Stackoverflow21925992] on Stack Overflow, please add your solution to the Stack Overflow question</span></span><!--, or [open an issue in the webfundamentals repository][GitHubWebFundamentalsNewIssue]--><span data-ttu-id="1f34f-153">.</span><span class="sxs-lookup"><span data-stu-id="1f34f-153">.</span></span>  

## <a name="step-2-debug-content-on-your-android-device-from-your-development-machine"></a><span data-ttu-id="1f34f-154">手順 2: 開発マシンから Android デバイスのコンテンツをデバッグする</span><span class="sxs-lookup"><span data-stu-id="1f34f-154">Step 2: Debug content on your Android device from your development machine</span></span>  

1.  <span data-ttu-id="1f34f-155">Android Microsoft Edgeを開きます。</span><span class="sxs-lookup"><span data-stu-id="1f34f-155">Open Microsoft Edge on your Android device.</span></span>  
1.  <span data-ttu-id="1f34f-156">に移動 `edge://inspect` すると、Android デバイスのモデル名が表示され、その後にデバイスのシリアル番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f34f-156">Navigate to `edge://inspect`, the model name of your Android device is displayed, followed by the device serial number.</span></span>  <span data-ttu-id="1f34f-157">その下に、デバイスで実行Microsoft Edgeバージョン番号をかっこで囲んで表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f34f-157">Below that, the version of Microsoft Edge running on the device should be displayed, with the version number in parentheses.</span></span>  <span data-ttu-id="1f34f-158">開いている各Microsoft Edgeタブは、一意のセクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-158">Each open Microsoft Edge tab gets a unique section.</span></span>  <span data-ttu-id="1f34f-159">セクションからそのタブを操作できます。</span><span class="sxs-lookup"><span data-stu-id="1f34f-159">You may interact with that tab from a section.</span></span>  <!--If there are any apps using WebView, a section for each of those apps should be displayed, too.  --><!--In [**Figure 5**](#figure-5) there are no tabs or WebViews open.  -->  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets.msft.png" alt-text="接続されたリモート デバイス" lightbox="../media/remote-debugging-edge-inspect-with-targets.msft.png":::
       <span data-ttu-id="1f34f-161">図 3. </span><span class="sxs-lookup"><span data-stu-id="1f34f-161">Figure 3.</span></span>  <span data-ttu-id="1f34f-162">接続されたリモート デバイス</span><span class="sxs-lookup"><span data-stu-id="1f34f-162">A connected remote device</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1f34f-163">[URL を **指定して開く] タブ** で URL を入力し、[開く] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="1f34f-163">In the **Open tab with url** text box, enter a URL and then choose **Open**.</span></span>  <span data-ttu-id="1f34f-164">ページが Android デバイスの新しいタブで開きます。</span><span class="sxs-lookup"><span data-stu-id="1f34f-164">The page opens in a new tab on your Android device.</span></span>  
1.  <span data-ttu-id="1f34f-165">開 **いた URL** の横にある [検査] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-165">Choose **inspect** next to the URL that you just opened.</span></span>  <span data-ttu-id="1f34f-166">新しい DevTools インスタンスが開きます。</span><span class="sxs-lookup"><span data-stu-id="1f34f-166">A new DevTools instance opens.</span></span>  

<!-- The version of Microsoft Edge running on your Android device determines the version of DevTools that opens on your development machine.  
    So, if your Android device is running a very old version of Microsoft Edge, the DevTools instance may look very different than what you are used to.   -->

### <a name="more-actions-focus-refresh-or-close-a-tab"></a><span data-ttu-id="1f34f-167">その他のアクション: フォーカス、更新、またはタブを閉じる</span><span class="sxs-lookup"><span data-stu-id="1f34f-167">More actions: focus, refresh, or close a tab</span></span>  

<span data-ttu-id="1f34f-168">フォーカス **、更新、\*\*\*\*または\*\*\*\*閉じるタブ**の横にある [フォーカス] タブ、再読み込み、または閉じるを選択します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-168">Choose **focus tab**, **reload**, or **close** next to the tab that you want to focus, refresh, or close.</span></span>  

:::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png" alt-text="タブのフォーカス、更新、または閉じるボタン" lightbox="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png":::
   <span data-ttu-id="1f34f-170">図 4: </span><span class="sxs-lookup"><span data-stu-id="1f34f-170">Figure 4.</span></span>  <span data-ttu-id="1f34f-171">タブのフォーカス、更新、または閉じるボタン</span><span class="sxs-lookup"><span data-stu-id="1f34f-171">The buttons for focusing, refreshing, or closing a tab</span></span>  
:::image-end:::  

### <a name="inspect-elements"></a><span data-ttu-id="1f34f-172">要素を検査する</span><span class="sxs-lookup"><span data-stu-id="1f34f-172">Inspect elements</span></span>  

<span data-ttu-id="1f34f-173">DevTools **インスタンスの Elements** ツールに移動し、要素にカーソルを合わせると、Android デバイスのビューポートで強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f34f-173">Navigate to the **Elements** tool of your DevTools instance, and hover on an element to highlight it in the viewport of your Android device.</span></span>  

<span data-ttu-id="1f34f-174">Android デバイス画面で要素を選択して、[要素] **ツールで選択** することもできます。</span><span class="sxs-lookup"><span data-stu-id="1f34f-174">You may also select an element on your Android device screen to select it in the **Elements** tool.</span></span>  <span data-ttu-id="1f34f-175">DevTools **インスタンス** で [Select Element \( Select Element \) ] アイコンを選択し、Android デバイス画面で要素 ![ ](../media/select-element-icon.msft.png) を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-175">Choose **Select Element** \(![Select Element](../media/select-element-icon.msft.png)\) icon on your DevTools instance, and then select the element on your Android device screen.</span></span>  

> [!NOTE]
> <span data-ttu-id="1f34f-176">**最初の** 選択後に Select Element が無効になっているので、機能を使用する度に再び有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f34f-176">**Select Element** is disabled after the first selection, so you must re-enable it every time you want to use the feature.</span></span>  

### <a name="screencast-your-android-screen-to-your-development-machine"></a><span data-ttu-id="1f34f-177">開発マシンに Android 画面をスクリーンキャストする</span><span class="sxs-lookup"><span data-stu-id="1f34f-177">Screencast your Android screen to your development machine</span></span>  

<span data-ttu-id="1f34f-178">DevTools **インスタンスで** Android デバイスのコンテンツを表示するには、[画面キャストの切り替え \( 画面キャスト \) の切り替え] アイコン ![ ](../media/toggle-screencast-icon.msft.png) を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-178">Choose **Toggle Screencast** \(![Toggle Screencast](../media/toggle-screencast-icon.msft.png)\) icon to view the content of your Android device in your DevTools instance.</span></span>  

<span data-ttu-id="1f34f-179">スクリーンキャストを操作するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-179">You are able to interact with the screencast in the following ways.</span></span>  

*   <span data-ttu-id="1f34f-180">選択はタップに変換され、デバイスで適切なタッチ イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-180">Chooses are translated into taps, firing proper touch events on the device.</span></span>  
*   <span data-ttu-id="1f34f-181">コンピューター上のキーストロークがデバイスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="1f34f-181">Keystrokes on your computer are sent to the device.</span></span>  
*   <span data-ttu-id="1f34f-182">ピンチ ジェスチャをシミュレートするには、ドラッグ中 `Shift` に保持します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-182">To simulate a pinch gesture, hold `Shift` while dragging.</span></span>  
*   <span data-ttu-id="1f34f-183">スクロールするには、トラックパッドまたはマウス ホイールを使用するか、マウス ポインターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-183">To scroll, use your trackpad or mouse wheel, or fling with your mouse pointer.</span></span>

> [!NOTE]
> <span data-ttu-id="1f34f-184">スクリーンキャストに役立つヒントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-184">Use the following tips to help you screencast.</span></span>  
> 
> *   <span data-ttu-id="1f34f-185">スクリーンキャストは、ページコンテンツのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-185">Screencasts only display page content.</span></span>  <span data-ttu-id="1f34f-186">スクリーン キャストの透明な部分は、Microsoft Edge アドレス バー、Android ステータス バー、Android キーボードなどのデバイス インターフェイスを表します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-186">Transparent portions of the screencast represent device interfaces, such as the Microsoft Edge address bar, the Android status bar, or the Android keyboard.</span></span>  
> *   <span data-ttu-id="1f34f-187">スクリーンキャストはフレーム レートに悪影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="1f34f-187">Screencasts negatively affect frame rates.</span></span>  <span data-ttu-id="1f34f-188">スクロールやアニメーションの測定中にスクリーンキャストを無効にして、ページのパフォーマンスをより正確に把握します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-188">Disable screencasting while measuring scrolls or animations to get a more accurate picture of the performance of your page.</span></span>  
> *   <span data-ttu-id="1f34f-189">Android デバイスの画面がロックされている場合、スクリーンキャストのコンテンツは消えます。</span><span class="sxs-lookup"><span data-stu-id="1f34f-189">If your Android device screen locks, the content of your screencast disappears.</span></span>  <span data-ttu-id="1f34f-190">Android デバイス画面のロックを解除して、スクリーンキャストを自動的に再開します。</span><span class="sxs-lookup"><span data-stu-id="1f34f-190">Unlock your Android device screen to automatically resume the screencast.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="1f34f-191">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="1f34f-191">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[AndroidDeveloperStudioDevOptions]: https://developer.android.com/studio/debug/dev-options "デバイス上の開発者向けオプションを構成|Android 開発者"  
[AndroidDeveloperToolsOemUsb]: https://developer.android.com/tools/extras/oem-usb.html "OEM USB ドライバーをインストール|Android 開発者"  

[AppleDeveloperSafariTools]: https://developer.apple.com/safari/tools "Safari Web 開発ツール |Apple Developer"  

[BrightcoveSupportDebuggingMobileDevices]: https://support.brightcove.com/debugging-mobile-devices "モバイル デバイス のデバッグ |Brightcove サポート"  

<!-- [GitHubWebFundamentalsNewIssue]: https://github.com/Alphabet/webfundamentals/issues/new?title=[Remote%20Debugging] "GitHub - Web Fundamentals - New Issue"  -->  

[StackexchangeAndroid101933]: https://android.stackexchange.com/questions/101933 "adb - Android の熱狂的なスタック Exchange"  

[Stackoverflow21925992]: https://stackoverflow.com/questions/21925992 "DevTools デバイスは、接続時にデバイスを検出しません - スタック オーバーフロー"  

> [!NOTE]
> <span data-ttu-id="1f34f-198">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="1f34f-198">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="1f34f-199">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="1f34f-199">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="1f34f-201">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="1f34f-201">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
