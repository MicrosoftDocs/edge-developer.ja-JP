---
description: 色覚の欠陥をエミュレートする、コマンド メニューで左にドッキングする、など。
title: DevTools の新機能 (Microsoft Edge 83)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: e5fa4b066e47b0779fcdf2b3e814c598e9615ccf
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564953"
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
# <a name="whats-new-in-devtools-microsoft-edge-83"></a><span data-ttu-id="4e33a-104">DevTools の新機能 (Microsoft Edge 83)</span><span class="sxs-lookup"><span data-stu-id="4e33a-104">What's New In DevTools (Microsoft Edge 83)</span></span>  

<span data-ttu-id="4e33a-105">更新されたスケジュールにChromium、今後のリリースのスケジュールを調整し、Microsoft Edge 82 リリースMicrosoft Edgeキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="4e33a-105">Following the updated Chromium schedule, we are adjusting our schedule for upcoming Microsoft Edge releases and cancelling the Microsoft Edge 82 release.</span></span> <span data-ttu-id="4e33a-106">詳細については、 [ブログの][WindowsBlogStableRelease] 投稿をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4e33a-106">Check out our [blog post][WindowsBlogStableRelease] for more info.</span></span>  

<span data-ttu-id="4e33a-107">83 の DevTools で利用できる新機能を次にMicrosoft Edgeします。</span><span class="sxs-lookup"><span data-stu-id="4e33a-107">Here are the new features available in the DevTools in Microsoft Edge 83.</span></span>  

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a><span data-ttu-id="4e33a-108">Microsoft Edge DevTools チームからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="4e33a-108">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="4e33a-109">以下のセクションでは、Microsoft Edge DevTools チームからのもので、見落としがあった可能性のあるお知らせの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="4e33a-109">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team.</span></span>  <span data-ttu-id="4e33a-110">DevTools、コード拡張機能、その他の新機能を試Microsoft Visual Studioお知らせをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4e33a-110">Check out the announcements to try new features in the DevTools, Microsoft Visual Studio Code extensions, and more.</span></span>  <span data-ttu-id="4e33a-111">開発者ツールのすべての最新および最大の機能を最新の情報に更新するには、プレビュー チャネルMicrosoft Edge[][MicrosoftEdgePreviewChannels]ダウンロードし[、Twitter][EdgeDevToolsTwitterAccount]でフォローしてください。</span><span class="sxs-lookup"><span data-stu-id="4e33a-111">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <a name="remotely-debug-microsoft-edge-on-windows-10-devices"></a><span data-ttu-id="4e33a-112">デバイスでリモートMicrosoft EdgeデバッグWindows 10する</span><span class="sxs-lookup"><span data-stu-id="4e33a-112">Remotely debug Microsoft Edge on Windows 10 Devices</span></span>  

<span data-ttu-id="4e33a-113">[\(Beta\)][RemoteTools]アプリMicrosoft Edgeリモート ツールは、このアプリで使用[Microsoft Store。][MicrosoftStore]</span><span class="sxs-lookup"><span data-stu-id="4e33a-113">The [Remote Tools for Microsoft Edge \(Beta\)][RemoteTools] app is now available in the [Microsoft Store][MicrosoftStore].</span></span>  <span data-ttu-id="4e33a-114">Windows デバイス ポータルを拡張するこのアプリを使用すると、開発マシンで実行されている[Microsoft Edge][WindowsUwpDebugTestPerfDevicePortal]のインスタンスからリモート Windows 10 デバイスに接続し、ターゲット \(Microsoft Edge のすべてのタブと Windows 10 デバイスで開いている[PWAs][ProgressiveWebAppsChromiumIndex]の一覧を表示し、リモート Windows 10 デバイスで実行されているターゲットに対して開発マシンで DevTools を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4e33a-114">Using this app, which extends the [Windows Device Portal][WindowsUwpDebugTestPerfDevicePortal], you are able to connect from the instance of Microsoft Edge running on your development machine to a remote Windows 10 device, display a list of targets \(all tabs in Microsoft Edge and [PWAs][ProgressiveWebAppsChromiumIndex] open on the Windows 10 device\), and use the DevTools on your development machine against a target running on the remote Windows 10 device.</span></span>  

:::image type="complex" source="../../media/2020/03/remote-tools.msft.png" alt-text="アプリで使用Microsoft Edge (Beta) アプリのリモート Microsoft Store" lightbox="../../media/2020/03/remote-tools.msft.png":::
   <span data-ttu-id="4e33a-116">アプリ[で使用Microsoft Edge (Beta)][RemoteTools]アプリのリモート[Microsoft Store][MicrosoftStore]</span><span class="sxs-lookup"><span data-stu-id="4e33a-116">The [Remote Tools for Microsoft Edge (Beta)][RemoteTools] app available in the [Microsoft Store][MicrosoftStore]</span></span>  
:::image-end:::  

<span data-ttu-id="4e33a-117">[リモート デバッグ用にデバイス][DevtoolsRemoteDebuggingWindows]とWindows 10コンピューターをセットアップする方法については、このガイドをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4e33a-117">[Read our guide for setting up your Windows 10 device and your development machine for remote debugging][DevtoolsRemoteDebuggingWindows].</span></span>  <span data-ttu-id="4e33a-118">フィードバックの送信アイコンをツイートまたは選択して、[][PostTweetEdgeDevTools]リモート デバッグ エクスペリエンスについて[お知](#getting-in-touch-with-microsoft-edge-devtools-team)らせします。</span><span class="sxs-lookup"><span data-stu-id="4e33a-118">Let us know about your remote debugging experience by [tweeting][PostTweetEdgeDevTools] orchoosing the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

### <a name="new-ways-to-access-settings"></a><span data-ttu-id="4e33a-119">新しいアクセス方法設定</span><span class="sxs-lookup"><span data-stu-id="4e33a-119">New ways to access Settings</span></span>  

<span data-ttu-id="4e33a-120">DevTools には、DevTools の外観、使い方、作業を必要な方法でカスタマイズできる数多くの設定があります。</span><span class="sxs-lookup"><span data-stu-id="4e33a-120">There are tons of settings for the DevTools that you are able to customize to make the DevTools look, feel, and work the way you need.</span></span> <span data-ttu-id="4e33a-121">83 Microsoft Edgeでは、DevTools[設定にアクセス][DevtoolsCustomizeIndexSettings]する方がずっと簡単になりました。</span><span class="sxs-lookup"><span data-stu-id="4e33a-121">In Microsoft Edge 83, accessing [Settings][DevtoolsCustomizeIndexSettings] in the DevTools is now much easier.</span></span>  <span data-ttu-id="4e33a-122">[コンソール設定メイン メニュー] の横にある歯車アイコンを使用して、このアイコンを開きます。</span><span class="sxs-lookup"><span data-stu-id="4e33a-122">Open Settings with the gear icon next to Console alerts and the main menu.</span></span>  

:::image type="complex" source="../../media/2020/03/settings.msft.png" alt-text="歯車アイコンが DevTools 設定開きます" lightbox="../../media/2020/03/settings.msft.png":::
   <span data-ttu-id="4e33a-124">歯車アイコンが DevTools**設定**開きます</span><span class="sxs-lookup"><span data-stu-id="4e33a-124">The gear icon opens **Settings** in the DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="4e33a-125">[その他のツール] の[設定][DevtoolsCustomizeIndexSettings]メニューからファイル**を\*\*\*\*開くすることもできます**。</span><span class="sxs-lookup"><span data-stu-id="4e33a-125">You are also able to open [Settings][DevtoolsCustomizeIndexSettings] from the **Main Menu** under **More tools**.</span></span>

:::image type="complex" source="../../media/2020/03/settings2.msft.png" alt-text="メイン メニュー > その他の> 設定" lightbox="../../media/2020/03/settings2.msft.png":::
   <span data-ttu-id="4e33a-127">**メイン メニュー**  > **その他のツール**  > **設定**</span><span class="sxs-lookup"><span data-stu-id="4e33a-127">**Main Menu** > **More tools** > **Settings**</span></span>  
:::image-end:::  

<span data-ttu-id="4e33a-128">Chromium[問題#1050855][CR1050855]</span><span class="sxs-lookup"><span data-stu-id="4e33a-128">Chromium issue [#1050855][CR1050855]</span></span>

### <a name="new-and-improved-infobars"></a><span data-ttu-id="4e33a-129">新しい情報バーと改善された情報バー</span><span class="sxs-lookup"><span data-stu-id="4e33a-129">New and improved infobars</span></span>

<span data-ttu-id="4e33a-130">DevTools の情報通知バー \(infobars\) の外観が改善され、機能が強化されました。</span><span class="sxs-lookup"><span data-stu-id="4e33a-130">Informational notification bars \(infobars\) in DevTools now have an improved look and more functionality.</span></span> <span data-ttu-id="4e33a-131">83 Microsoft Edgeでは、infobars の方が読みやすく、ボタンを提供し、関連するアクションを簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="4e33a-131">In Microsoft Edge 83, infobars are easier to read and provide buttons so you are able to take the relevant action right away.</span></span>  

:::image type="complex" source="../../media/2020/03/infobar.msft.png" alt-text="83 でファイルを美しい印刷用の infobar Microsoft Edge 83" lightbox="../../media/2020/03/infobar.msft.png":::
   <span data-ttu-id="4e33a-133">バージョン 83 でファイルをかなり印刷Microsoft Edge Infobar</span><span class="sxs-lookup"><span data-stu-id="4e33a-133">Infobar for pretty-printing a minified file in Microsoft Edge Version 83</span></span>  
:::image-end:::  

<span data-ttu-id="4e33a-134">Chromium[問題#1056348][CR1056348]</span><span class="sxs-lookup"><span data-stu-id="4e33a-134">Chromium issue [#1056348][CR1056348]</span></span>

### <a name="navigate-the-color-picker-with-your-keyboard"></a><span data-ttu-id="4e33a-135">キーボードでカラー ピッカーを移動する</span><span class="sxs-lookup"><span data-stu-id="4e33a-135">Navigate the Color Picker with your keyboard</span></span>  

<span data-ttu-id="4e33a-136">Color [Picker は][DevtoolsCssReferenceColorPicker] 、変更と宣言を [行う要素パネル][DevtoolsCssIndex] `color` の GUI `background-color` です。</span><span class="sxs-lookup"><span data-stu-id="4e33a-136">The [Color Picker][DevtoolsCssReferenceColorPicker] is a GUI in the [Elements panel][DevtoolsCssIndex] for changing `color` and `background-color` declarations.</span></span>  <span data-ttu-id="4e33a-137">以前のバージョンの Microsoft Edgeでは、キーボードを使用してカラー ピッカーの\*\*\*\*[網掛け][セクションを][DevtoolsCssReferenceColorPicker]移動する必要が生じていました。</span><span class="sxs-lookup"><span data-stu-id="4e33a-137">In previous versions of Microsoft Edge, you were not able to navigate the **Shades** section of the [Color Picker][DevtoolsCssReferenceColorPicker] with the keyboard.</span></span>  

:::image type="complex" source="../../media/2020/03/color-picker.msft.png" alt-text="これで、キーボードを使用して、カラー ピッカーの [網掛け] セクションでセレクターを移動できます。" lightbox="../../media/2020/03/color-picker.msft.png":::
   <span data-ttu-id="4e33a-139">これで、キーボードを使用して、カラー ピッカーの [ **網** 掛け] セクションでセレクターを [移動できます。][DevtoolsCssReferenceColorPicker]</span><span class="sxs-lookup"><span data-stu-id="4e33a-139">You are now able to use your keyboard to move the selector in the **Shades** section of the [Color Picker][DevtoolsCssReferenceColorPicker]</span></span>  
:::image-end:::  

<span data-ttu-id="4e33a-140">83 Microsoft Edgeでは、キーボードを使用して、カラー ピッカーの [網掛け]\*\*\*\* セクションでセレクターを移動できます。</span><span class="sxs-lookup"><span data-stu-id="4e33a-140">In Microsoft Edge 83, you are now able to use the keyboard to move the selector in the **Shades** section of the Color Picker.</span></span>  

<span data-ttu-id="4e33a-141">Chromium[の問題][CR963183]#963183</span><span class="sxs-lookup"><span data-stu-id="4e33a-141">Chromium issue [#963183][CR963183]</span></span>  

### <a name="properties-tab-now-populates-after-a-page-refresh"></a><span data-ttu-id="4e33a-142">ページの更新後に [プロパティ] タブが設定される</span><span class="sxs-lookup"><span data-stu-id="4e33a-142">Properties tab now populates after a page refresh</span></span>  

<span data-ttu-id="4e33a-143">81 Microsoft Edge以前のバージョンでは、[要素\*\*\*\*] パネルの[][DevtoolsCssIndex][プロパティ] タブがページ更新によって壊れています。</span><span class="sxs-lookup"><span data-stu-id="4e33a-143">In Microsoft Edge 81 and earlier, the **Properties tab** in the [Elements panel][DevtoolsCssIndex] was broken by page refreshes.</span></span>  <span data-ttu-id="4e33a-144">ページを更新すると、[プロパティ] **タブに** 現在選択されている要素のプロパティが設定されません。</span><span class="sxs-lookup"><span data-stu-id="4e33a-144">When you refreshed the page, the **Properties tab** did not populate the properties of the currently-selected element.</span></span>  

:::image type="complex" source="../../media/2020/03/properties-in-81.msft.png" alt-text="81 Microsoft Edge以前のバージョンでは、ページの更新後に [プロパティ] タブが空白でした" lightbox="../../media/2020/03/properties-in-81.msft.png":::
   <span data-ttu-id="4e33a-146">81 Microsoft Edge以前のバージョンでは、ページの更新**後**に [プロパティ] タブが空白でした</span><span class="sxs-lookup"><span data-stu-id="4e33a-146">In Microsoft Edge 81 and earlier, the **Properties tab** was blank after a page refresh</span></span>  
:::image-end:::  

<span data-ttu-id="4e33a-147">83 Microsoft Edgeページ更新後に、現在選択されている要素のプロパティを [プロパティ] タブに**表示できます**。</span><span class="sxs-lookup"><span data-stu-id="4e33a-147">In Microsoft Edge 83, you are now able to display the properties of the currently-selected element after a page refresh in the **Properties tab**.</span></span>  

:::image type="complex" source="../../media/2020/03/properties-in-82.msft.png" alt-text="83 Microsoft Edge、[プロパティ] タブには、ページ更新後に現在選択されている要素のプロパティが表示されます。" lightbox="../../media/2020/03/properties-in-82.msft.png":::
   <span data-ttu-id="4e33a-149">83 Microsoft Edge、[プロパティ] タブ\*\*\*\* には、ページ更新後に現在選択されている要素のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e33a-149">In Microsoft Edge 83, the **Properties tab** displays the properties of the currently-selected element after a page refresh</span></span>  
:::image-end:::  

<span data-ttu-id="4e33a-150">Chromium[問題#1050999][CR1050999]</span><span class="sxs-lookup"><span data-stu-id="4e33a-150">Chromium issue [#1050999][CR1050999]</span></span>  

### <a name="use-the-arrow-keys-to-scroll-in-the-changes-tool"></a><span data-ttu-id="4e33a-151">[変更] ツールで矢印キーを使用してスクロールする</span><span class="sxs-lookup"><span data-stu-id="4e33a-151">Use the arrow keys to scroll in the Changes tool</span></span>  

<span data-ttu-id="4e33a-152">[ **変更] ツール** は、DevTools で CSS または JavaScript に加えた変更を追跡します。</span><span class="sxs-lookup"><span data-stu-id="4e33a-152">The **Changes tool** tracks any changes you have made to CSS or JavaScript in the DevTools.</span></span>  <span data-ttu-id="4e33a-153">[変更] ツールを **使用すると** 、すべての変更をすばやく表示し、エディター/IDE に戻します。</span><span class="sxs-lookup"><span data-stu-id="4e33a-153">You are able to use the **Changes tool** to quickly display all your changes and take those back to your editor/IDE.</span></span>  

<span data-ttu-id="4e33a-154">[変更] ツール**を開く**には `Ctrl` + `Shift` + `P` 、DevTools で選択してコマンド メニュー[を開き、と][DevtoolsCommandMenuIndex]入力します `changes` 。</span><span class="sxs-lookup"><span data-stu-id="4e33a-154">To open the **Changes tool**, select `Ctrl`+`Shift`+`P` in the DevTools to open the [Command Menu][DevtoolsCommandMenuIndex] and type `changes`.</span></span>  <span data-ttu-id="4e33a-155">[変更の表示]**コマンドを**選択して\*\*\*\* 実行して、DevTools ドロワーで [変更] ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="4e33a-155">choose and run the **Show Changes** command to open the **Changes tool** in the DevTools drawer.</span></span>  

<span data-ttu-id="4e33a-156">ファイルを変更すると、[変更] ツールを使用すると、\*\*\*\* 水平方向にスクロールして、すべてのコードを表示できます。</span><span class="sxs-lookup"><span data-stu-id="4e33a-156">When you have made a change to a minified file, the **Changes tool** enables you to scroll horizontally to display all of your minified code.</span></span>  <span data-ttu-id="4e33a-157">83 Microsoft Edgeから、キーボードの矢印キーを使用して水平方向にスクロールできます。</span><span class="sxs-lookup"><span data-stu-id="4e33a-157">Starting in Microsoft Edge 83, you may now scroll horizontally using the arrow keys on your keyboard.</span></span>  

:::image type="complex" source="../../media/2020/03/changes.msft.png" alt-text="83 Microsoft Edgeでは、矢印キーを使用して水平方向にスクロールして、変更ツールにコードを表示できます。" lightbox="../../media/2020/03/changes.msft.png":::
   <span data-ttu-id="4e33a-159">83 Microsoft Edgeでは、矢印キーを使用して水平方向にスクロールして、変更ツールでコードの変更を表示**できます**。</span><span class="sxs-lookup"><span data-stu-id="4e33a-159">In Microsoft Edge 83, you may scroll horizontally with the arrow keys to display the changes you made to your minified code in the **Changes tool**</span></span>  
:::image-end:::  

<span data-ttu-id="4e33a-160">スクリーン リーダーまたはキーボードを使用して DevTools の周りを移動する場合は[][PostTweetEdgeDevTools]、フィードバックの送信アイコンをツイートするか、フィードバックの送信アイコンを選択してフィードバック[を送信](#getting-in-touch-with-microsoft-edge-devtools-team)してください。</span><span class="sxs-lookup"><span data-stu-id="4e33a-160">If you use screen readers or the keyboard to navigate around the DevTools, send us your feedback by [tweeting][PostTweetEdgeDevTools] at us orchoosing the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="4e33a-161">Chromium[の問題][CR963183]#963183</span><span class="sxs-lookup"><span data-stu-id="4e33a-161">Chromium issue [#963183][CR963183]</span></span>  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="4e33a-162">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="4e33a-162">Announcements from the Chromium project</span></span>  

<span data-ttu-id="4e33a-163">次のセクションでは、Microsoft Edge 83 で利用可能な追加の機能についてChromiumします。</span><span class="sxs-lookup"><span data-stu-id="4e33a-163">The following sections announce additional features available in Microsoft Edge 83 that were contributed to the open source Chromium project.</span></span>  

### <a name="emulate-vision-deficiencies"></a><span data-ttu-id="4e33a-164">視覚欠陥をエミュレートする</span><span class="sxs-lookup"><span data-stu-id="4e33a-164">Emulate vision deficiencies</span></span>  

<span data-ttu-id="4e33a-165">[レンダリング [] タブを][DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTool] 開き、新しい **エミュレート** ビジョンの欠陥機能を使用して、さまざまな種類のビジョンの欠陥を持つユーザーがサイトをどのように経験するのかについて、より良いアイデアを得る。</span><span class="sxs-lookup"><span data-stu-id="4e33a-165">Open the [Rendering tab][DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTool] and use the new **Emulate vision deficiencies** feature to get a better idea of how people with different types of vision deficiencies experience your site.</span></span>  

:::image type="complex" source="../../media/2020/03/vision.msft.png" alt-text="ぼやけたビジョンの画像を表示する" lightbox="../../media/2020/03/vision.msft.png":::
   <span data-ttu-id="4e33a-167">ぼやけたビジョンの画像を表示する</span><span class="sxs-lookup"><span data-stu-id="4e33a-167">Emulating blurred vision</span></span>  
:::image-end:::  

<span data-ttu-id="4e33a-168">DevTools は、ぼやけたビジョンと次の種類のカラー ビジョンの欠陥 [をエミュレートできます][ColorBlindnessTypes]。</span><span class="sxs-lookup"><span data-stu-id="4e33a-168">DevTools is able to emulate blurred vision and the following [types of color vision deficiencies][ColorBlindnessTypes].</span></span>  

| <span data-ttu-id="4e33a-169">カラー ビジョンの不足</span><span class="sxs-lookup"><span data-stu-id="4e33a-169">Color Vision Deficiency</span></span> | <span data-ttu-id="4e33a-170">詳細</span><span class="sxs-lookup"><span data-stu-id="4e33a-170">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="4e33a-171">Protanopia</span><span class="sxs-lookup"><span data-stu-id="4e33a-171">Protanopia</span></span> | <span data-ttu-id="4e33a-172">赤い光を認識しきれない。</span><span class="sxs-lookup"><span data-stu-id="4e33a-172">The inability to perceive any red light.</span></span> |  
| <span data-ttu-id="4e33a-173">Deuteranopia</span><span class="sxs-lookup"><span data-stu-id="4e33a-173">Deuteranopia</span></span> | <span data-ttu-id="4e33a-174">緑色の光を認識しきれない。</span><span class="sxs-lookup"><span data-stu-id="4e33a-174">The inability to perceive any green light.</span></span> |  
| <span data-ttu-id="4e33a-175">トリタニア</span><span class="sxs-lookup"><span data-stu-id="4e33a-175">Tritanopia</span></span> | <span data-ttu-id="4e33a-176">青い光を認識しきれな</span><span class="sxs-lookup"><span data-stu-id="4e33a-176">The inability to perceive any blue light.</span></span> |  
| <span data-ttu-id="4e33a-177">アクロマトプシア</span><span class="sxs-lookup"><span data-stu-id="4e33a-177">Achromatopsia</span></span> | <span data-ttu-id="4e33a-178">灰色 \(極めてまれな\) の色合いを除き、色を認識することの困難。</span><span class="sxs-lookup"><span data-stu-id="4e33a-178">The inability to perceive any color, except for shades of grey \(extremely rare\).</span></span> |  

<span data-ttu-id="4e33a-179">これらの色覚の欠陥の極端なバージョンは少なく、実際にはより一般的です。</span><span class="sxs-lookup"><span data-stu-id="4e33a-179">Less extreme versions of these color vision deficiencies exist, and in fact they are more common.</span></span>  
<span data-ttu-id="4e33a-180">たとえば、protanomaly は赤色光に対する感度の低下です (protanopia とは対照的に、赤い光を認識する完全な機能がなくなります)。</span><span class="sxs-lookup"><span data-stu-id="4e33a-180">For example, protanomaly is a reduced sensitivity to red light (as opposed to protanopia, which is the complete inability to perceive red light).</span></span> <span data-ttu-id="4e33a-181">しかし、 **これらの -omaly** ビジョンの欠陥は、明確に定義されているわけではありません。このような視力不足を持つすべての人は異なって、物事が異なって見える場合があります\(関連する色のより多く/より少なく認識できる\)。</span><span class="sxs-lookup"><span data-stu-id="4e33a-181">However, these **-omaly** vision deficiencies are not as clearly defined:  every person with such a vision deficiency is different and may see things differently \(being able to perceive more/less of the relevant colors\).</span></span>  

<span data-ttu-id="4e33a-182">DevTools のより極端なシミュレーションを設計することで、Web アプリは、protanomaly、deuteranomaly、tritanomaly、および achromatomaly を持つユーザーにもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4e33a-182">By designing for the more extreme simulations in DevTools, your web apps are guaranteed to be accessible to people with protanomaly, deuteranomaly, tritanomaly, and achromatomaly as well.</span></span>  

<span data-ttu-id="4e33a-183">[フィードバックの送信] [アイコンをツイート][PostTweetEdgeDevTools] または選択してフィードバック [を送信](#getting-in-touch-with-microsoft-edge-devtools-team) します。</span><span class="sxs-lookup"><span data-stu-id="4e33a-183">Send your feedback by [tweeting][PostTweetEdgeDevTools] orchoosing the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="4e33a-184">Chromium[の問題][CR1003700]#1003700</span><span class="sxs-lookup"><span data-stu-id="4e33a-184">Chromium issue [#1003700][CR1003700]</span></span>  

### <a name="emulate-locales"></a><span data-ttu-id="4e33a-185">ローカルをエミュレートする</span><span class="sxs-lookup"><span data-stu-id="4e33a-185">Emulate locales</span></span>  

<span data-ttu-id="4e33a-186">Sensors Location で場所を設定して、**ローカルをエミュレート**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="4e33a-186">Emulate locales by setting a location in **Sensors** > **Location**.</span></span> <span data-ttu-id="4e33a-187">[コマンド メニュー **を開き、**][DevtoolsCommandMenuIndex] センサー `Sensors` タブに **アクセスします** 。 これらのアクションを実行した後、DevTools は現在の既定のロケールを変更し、次のコードに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="4e33a-187">[Open the **Command Menu**][DevtoolsCommandMenuIndex] and type `Sensors` to access the **Sensors** tab.  After performing these actions, DevTools modifies the current default locale, affecting the following code.</span></span>  

*   `Intl.*` <span data-ttu-id="4e33a-188">API の例:</span><span class="sxs-lookup"><span data-stu-id="4e33a-188">APIs, for example:</span></span> `new Intl.NumberFormat().resolvedOptions().locale`  
*   <span data-ttu-id="4e33a-189">その他のロケール対応 JavaScript API (たとえば、次のように `String.prototype.localeCompare` `*.prototype.toLocaleString` )</span><span class="sxs-lookup"><span data-stu-id="4e33a-189">Other locale-aware JavaScript APIs such as `String.prototype.localeCompare` and `*.prototype.toLocaleString`, for example:</span></span> `123_456..toLocaleString()`  
*   <span data-ttu-id="4e33a-190">DOM API (次のような `navigator.language` DOM API)</span><span class="sxs-lookup"><span data-stu-id="4e33a-190">DOM APIs such as `navigator.language` and</span></span> `navigator.languages`  
*   <span data-ttu-id="4e33a-191">[Accept-Language][MDNAcceptLanguage] HTTP 要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="4e33a-191">The [Accept-Language][MDNAcceptLanguage] HTTP request header</span></span>  

> [!NOTE]
> <span data-ttu-id="4e33a-192">更新プログラム `navigator.language` は `navigator.languages` 、すぐには表示されませんが、次のナビゲーションまたはページ更新後にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e33a-192">Updates to `navigator.language` and `navigator.languages` are not visible immediately, but only after the next navigation or page refresh.</span></span>  <span data-ttu-id="4e33a-193">HTTP ヘッダーへの `Accept-Language` 変更は、後続の要求にのみ反映されます。</span><span class="sxs-lookup"><span data-stu-id="4e33a-193">Changes to the `Accept-Language` HTTP header are only reflected for subsequent requests.</span></span>  

:::image type="complex" source="../../media/2020/03/locale.msft.png" alt-text="ロケールの表示" lightbox="../../media/2020/03/locale.msft.png":::
   <span data-ttu-id="4e33a-195">ロケールの表示</span><span class="sxs-lookup"><span data-stu-id="4e33a-195">Emulating a locale</span></span>  
:::image-end:::  

<span data-ttu-id="4e33a-196">デモを試す場合は、[ロケールに依存 [するコード例] に移動します][MathiasByensLocaleDemo]。</span><span class="sxs-lookup"><span data-stu-id="4e33a-196">To try a demo, navigate to [Locale-dependent code example][MathiasByensLocaleDemo].</span></span>

<span data-ttu-id="4e33a-197">Chromium[問題#1051822][CR1051822]</span><span class="sxs-lookup"><span data-stu-id="4e33a-197">Chromium issue [#1051822][CR1051822]</span></span>

### <a name="cross-origin-embedder-policy-coep-debugging"></a><span data-ttu-id="4e33a-198">クロスオリジン エンベダー ポリシー (COEP) のデバッグ</span><span class="sxs-lookup"><span data-stu-id="4e33a-198">Cross-Origin Embedder Policy (COEP) debugging</span></span>  

<span data-ttu-id="4e33a-199">[ネットワーク] パネルには、 [クロスオリジン エンベダー ポリシーのデバッグ情報][COEP] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e33a-199">The Network panel now provides [Cross-Origin Embedder Policy][COEP] debugging information.</span></span>  

<span data-ttu-id="4e33a-200">[ **状態]** 列には、要求がブロックされた理由の簡単な説明と、その要求のヘッダーを表示するリンクが表示され、さらにデバッグが行えます。</span><span class="sxs-lookup"><span data-stu-id="4e33a-200">The **Status** column now provides a quick explanation of why a request was blocked as well as a link to view the headers of that request for further debugging:</span></span>  

:::image type="complex" source="../../media/2020/03/status.msft.png" alt-text="**Status** 列のブロックされた要求" lightbox="../../media/2020/03/status.msft.png":::
   <span data-ttu-id="4e33a-202">[状態] 列のブロック **された** 要求</span><span class="sxs-lookup"><span data-stu-id="4e33a-202">Blocked requests in the **Status** column</span></span>  
:::image-end:::  

<span data-ttu-id="4e33a-203">[ **ヘッダー] タブの** [応答 **ヘッダー** ] セクションでは、問題を解決する方法について詳しいガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4e33a-203">The **Response Headers** section of the **Headers** tab provides more guidance on how to resolve the issues:</span></span>  

:::image type="complex" source="../../media/2020/03/guidance.msft.png" alt-text="[応答ヘッダー] セクションの詳細なガイダンス" lightbox="../../media/2020/03/guidance.msft.png":::
   <span data-ttu-id="4e33a-205">[応答ヘッダー] セクション **の詳細な** ガイダンス</span><span class="sxs-lookup"><span data-stu-id="4e33a-205">More guidance in the **Response Headers** section</span></span>  
:::image-end:::  

<span data-ttu-id="4e33a-206">[フィードバックの送信] [アイコンをツイート][PostTweetEdgeDevTools] または選択してフィードバック [を送信](#getting-in-touch-with-microsoft-edge-devtools-team) します。</span><span class="sxs-lookup"><span data-stu-id="4e33a-206">Send your feedback by [tweeting][PostTweetEdgeDevTools] orchoosing the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="4e33a-207">Chromium[問題#1051466][CR1051466]</span><span class="sxs-lookup"><span data-stu-id="4e33a-207">Chromium issue [#1051466][CR1051466]</span></span>  

### <a name="new-icons-for-breakpoints-conditional-breakpoints-and-logpoints"></a><span data-ttu-id="4e33a-208">ブレークポイント、条件付きブレークポイント、およびログポイントの新しいアイコン</span><span class="sxs-lookup"><span data-stu-id="4e33a-208">New icons for breakpoints, conditional breakpoints, and logpoints</span></span>  

<span data-ttu-id="4e33a-209">[ソース] パネルには、ブレークポイント、条件付きブレークポイント、およびログポイントの新しいアイコンがあります。</span><span class="sxs-lookup"><span data-stu-id="4e33a-209">The Sources panel has new icons for breakpoints, conditional breakpoints, and logpoints:</span></span>  

*   <span data-ttu-id="4e33a-210">ブレークポイント \(</span><span class="sxs-lookup"><span data-stu-id="4e33a-210">Breakpoints \(</span></span>![ブレークポイント](../../media/2020/03/breakpoint.msft.png)<span data-ttu-id="4e33a-212">\) は赤い円で表されます。</span><span class="sxs-lookup"><span data-stu-id="4e33a-212">\) are represented by red circles.</span></span>  
*   <span data-ttu-id="4e33a-213">条件付きブレークポイント \(</span><span class="sxs-lookup"><span data-stu-id="4e33a-213">Conditional Breakpoints \(</span></span>![条件付きブレークポイント](../../media/2020/03/conditional.msft.png)<span data-ttu-id="4e33a-215">\) は、半赤の半白の円で表されます。</span><span class="sxs-lookup"><span data-stu-id="4e33a-215">\) are represented by half-red half-white circles.</span></span>  
*   <span data-ttu-id="4e33a-216">Logpoints \(</span><span class="sxs-lookup"><span data-stu-id="4e33a-216">Logpoints \(</span></span>![Logpoint](../../media/2020/03/logpoint.msft.png)<span data-ttu-id="4e33a-218">\) は、コンソール アイコンを持つ赤い円で表されます。</span><span class="sxs-lookup"><span data-stu-id="4e33a-218">\) are represented by red circles with Console icons.</span></span>  

<span data-ttu-id="4e33a-219">新しいアイコンの動機は、UI を他の GUI デバッグ ツール \(通常は色ブレークポイント赤\) と整合性を高め、3 つの機能を一目で区別しやすくする点でした。</span><span class="sxs-lookup"><span data-stu-id="4e33a-219">The motivation for the new icons was to make the UI more consistent with other GUI debugging tools \(which usually color breakpoints red\) and to make it easier to distinguish between the 3 features at a glance.</span></span>  

<span data-ttu-id="4e33a-220">Chromium の問題 [#1041830][CR1041830]</span><span class="sxs-lookup"><span data-stu-id="4e33a-220">Chromium issue [#1041830][CR1041830]</span></span>  

### <a name="view-network-requests-that-set-a-specific-cookie-path"></a><span data-ttu-id="4e33a-221">特定の Cookie パスを設定するネットワーク要求を表示する</span><span class="sxs-lookup"><span data-stu-id="4e33a-221">View network requests that set a specific cookie path</span></span>  

<span data-ttu-id="4e33a-222">ネットワーク ツールの新しいフィルター キーワードを使用して、特定の Cookie パスを設定する `cookie-path` ネットワーク要求に[集中します][MDNCookiePath]。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4e33a-222">Use the new `cookie-path` filter keyword in the **Network** tool to focus on the network requests that set a specific [cookie path][MDNCookiePath].</span></span>  

<span data-ttu-id="4e33a-223">プロパティで [要求をフィルター処理して、その][DevtoolsNetworkReferenceFilterRequestsProperties] 他のキーワード (など) を確認してください `cookie-path` 。</span><span class="sxs-lookup"><span data-stu-id="4e33a-223">Check out [Filter requests by properties][DevtoolsNetworkReferenceFilterRequestsProperties] to discover more keywords like `cookie-path`.</span></span>

### <a name="dock-to-left-from-the-command-menu"></a><span data-ttu-id="4e33a-224">コマンド メニューから左にドッキングする</span><span class="sxs-lookup"><span data-stu-id="4e33a-224">Dock to left from the Command Menu</span></span>  

<span data-ttu-id="4e33a-225">コマンド メニュー [を開き][DevtoolsCommandMenuIndex] 、コマンド `Dock to left` を実行して DevTools をビューポートの左側に移動します。</span><span class="sxs-lookup"><span data-stu-id="4e33a-225">Open the [Command Menu][DevtoolsCommandMenuIndex] and run the `Dock to left` command to move DevTools to the left of your viewport.</span></span>  

:::image type="complex" source="../../media/2020/03/dock-to-left.msft.png" alt-text="ビューポートの左側にドッキングされた DevTools" lightbox="../../media/2020/03/dock-to-left.msft.png":::
   <span data-ttu-id="4e33a-227">ビューポートの左側にドッキングされた DevTools</span><span class="sxs-lookup"><span data-stu-id="4e33a-227">DevTools docked to the left of the viewport</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="4e33a-228">左側**のドック機能**は 75 以降Microsoft Edge使用できますが、以前はメイン メニューから[しかアクセスできません][DevtoolsCustomizePlacementsChangeMainMenu]。</span><span class="sxs-lookup"><span data-stu-id="4e33a-228">The **Dock to left** feature has been available since Microsoft Edge 75, but it was previously only accessible from the [Main Menu][DevtoolsCustomizePlacementsChangeMainMenu].</span></span>  <span data-ttu-id="4e33a-229">83 の新機能Microsoft Edgeコマンド メニューからこの機能にアクセスできる点です。</span><span class="sxs-lookup"><span data-stu-id="4e33a-229">The new feature in Microsoft Edge 83 is that you may now access this feature from the Command Menu.</span></span>  

<span data-ttu-id="4e33a-230">[フィードバックの送信] [アイコンをツイート][PostTweetEdgeDevTools] または選択してフィードバック [を送信](#getting-in-touch-with-microsoft-edge-devtools-team) します。</span><span class="sxs-lookup"><span data-stu-id="4e33a-230">Send your feedback by [tweeting][PostTweetEdgeDevTools] orchoosing the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="4e33a-231">Chromium[問題#1011679][CR1011679]</span><span class="sxs-lookup"><span data-stu-id="4e33a-231">Chromium issue [#1011679][CR1011679]</span></span>  

### <a name="the-audits-panel-is-now-the-lighthouse-panel"></a><span data-ttu-id="4e33a-232">[監査] パネルが [ライトハウス] パネル</span><span class="sxs-lookup"><span data-stu-id="4e33a-232">The Audits panel is now the Lighthouse panel</span></span>  

<span data-ttu-id="4e33a-233">DevTools チームは、多くの場合、Web 開発者から、DevTools から[ライト][GithubGoogleChromeLighthouse]ハウスを実行できる一方で、「ライトハウス」パネルが見つからないので、Audits パネルが\*\*\*\* ライトハウス パネルに変更\*\*\*\* されたというフィードバックを頻繁に受け取っています。</span><span class="sxs-lookup"><span data-stu-id="4e33a-233">The DevTools team frequently got feedback from web developers that while it was possible to run [Lighthouse][GithubGoogleChromeLighthouse] from DevTools, when they tried it out they were not able to find the "Lighthouse" panel, so the **Audits** panel is now the **Lighthouse** panel.</span></span>  

:::image type="complex" source="../../media/2020/03/lighthouse.msft.png" alt-text="[ライトハウス] パネル" lightbox="../../media/2020/03/lighthouse.msft.png":::
   <span data-ttu-id="4e33a-235">[ライトハウス] パネル</span><span class="sxs-lookup"><span data-stu-id="4e33a-235">The Lighthouse panel</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="4e33a-236">[ **ライトハウス** ] パネルには、サードパーティの Web サイトでホストされているコンテンツへのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e33a-236">The **Lighthouse** panel provides links to content hosted on third-party websites.</span></span>  <span data-ttu-id="4e33a-237">Microsoft は、これらのサイトのコンテンツおよび収集する可能性があるデータに対して責任を負う責任を負いません。</span><span class="sxs-lookup"><span data-stu-id="4e33a-237">Microsoft is not responsible for and has no control over the content of these sites and any data they may collect.</span></span>  

### <a name="delete-all-local-overrides-in-a-folder"></a><span data-ttu-id="4e33a-238">フォルダー内のすべてのローカル オーバーライドを削除する</span><span class="sxs-lookup"><span data-stu-id="4e33a-238">Delete all Local Overrides in a folder</span></span>  

<span data-ttu-id="4e33a-239">ローカル オーバーライド**を設定**した後、ディレクトリにマウス ポインターを置き、コンテキスト メニュー \(右クリック\)\*\*\*\* を開き、新しい [すべての上書きを削除] オプションを選択して、そのフォルダー内のすべてのローカル オーバーライドを削除します。</span><span class="sxs-lookup"><span data-stu-id="4e33a-239">After setting up **Local Overrides** you may hover on a directory, open the contextual menu \(right-click\), and choose the new **Delete all overrides** option to delete all Local Overrides in that folder.</span></span>  

:::image type="complex" source="../../media/2020/03/overrides.msft.png" alt-text="すべての上書きを削除する" lightbox="../../media/2020/03/overrides.msft.png":::
   <span data-ttu-id="4e33a-241">すべての上書きを削除する</span><span class="sxs-lookup"><span data-stu-id="4e33a-241">Delete all overrides</span></span>  
:::image-end:::  

<span data-ttu-id="4e33a-242">[フィードバックの送信] [アイコンをツイート][PostTweetEdgeDevTools] または選択してフィードバック [を送信](#getting-in-touch-with-microsoft-edge-devtools-team) します。</span><span class="sxs-lookup"><span data-stu-id="4e33a-242">Send your feedback by [tweeting][PostTweetEdgeDevTools] orchoosing the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="4e33a-243">Chromiumの問題[#1016501][CR1016501]</span><span class="sxs-lookup"><span data-stu-id="4e33a-243">Chromium issue [#1016501][CR1016501]</span></span>  

### <a name="updated-long-tasks-ui"></a><span data-ttu-id="4e33a-244">更新された長いタスクの UI</span><span class="sxs-lookup"><span data-stu-id="4e33a-244">Updated Long tasks UI</span></span>  

<span data-ttu-id="4e33a-245">Long **Task は** JavaScript コードで、メイン スレッドを長時間独占し、Web ページがフリーズします。</span><span class="sxs-lookup"><span data-stu-id="4e33a-245">A **Long Task** is JavaScript code that monopolizes the main thread for a long time, causing a web page to freeze.</span></span>  

<span data-ttu-id="4e33a-246">しばらくの間、[パフォーマンス[][DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity]] パネルで長いタスクを視覚化できますが、Microsoft Edge 83 では、[パフォーマンス] パネルの [長いタスク] の視覚化 UI が更新されました。</span><span class="sxs-lookup"><span data-stu-id="4e33a-246">You have been able to [visualize Long Tasks in the Performance panel][DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity] for a while now, but in Microsoft Edge 83 the Long Task visualization UI in the Performance panel has been updated.</span></span>  <span data-ttu-id="4e33a-247">タスクの長いタスク部分が、ストライプの赤い背景で色付けされました。</span><span class="sxs-lookup"><span data-stu-id="4e33a-247">The Long Task portion of a task is now colored with a striped red background.</span></span>  

:::image type="complex" source="../../media/2020/03/long-task.msft.png" alt-text="新しい長いタスク UI" lightbox="../../media/2020/03/long-task.msft.png":::
   <span data-ttu-id="4e33a-249">新しい長いタスク UI</span><span class="sxs-lookup"><span data-stu-id="4e33a-249">The new Long Task UI</span></span>  
:::image-end:::  

<span data-ttu-id="4e33a-250">[フィードバックの送信] [アイコンをツイート][PostTweetEdgeDevTools] または選択してフィードバック [を送信](#getting-in-touch-with-microsoft-edge-devtools-team) します。</span><span class="sxs-lookup"><span data-stu-id="4e33a-250">Send your feedback by [tweeting][PostTweetEdgeDevTools] orchoosing the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="4e33a-251">Chromiumの問題[#1054447][CR1054447]</span><span class="sxs-lookup"><span data-stu-id="4e33a-251">Chromium issue [#1054447][CR1054447]</span></span>  

### <a name="maskable-icon-support-in-the-manifest-pane"></a><span data-ttu-id="4e33a-252">マニフェスト ウィンドウでのマスク可能なアイコンのサポート</span><span class="sxs-lookup"><span data-stu-id="4e33a-252">Maskable icon support in the Manifest pane</span></span>  

<span data-ttu-id="4e33a-253">Android Oreo では、さまざまなデバイス モデルのさまざまな図形にアプリ アイコンを表示するアダプティブ アイコンが導入されました。</span><span class="sxs-lookup"><span data-stu-id="4e33a-253">Android Oreo introduced adaptive icons, which display app icons in a variety of shapes across different device models.</span></span>  <span data-ttu-id="4e33a-254">**マスク可能なアイコン**は、アダプティブ アイコンをサポートする新しいアイコン形式で、マスク可能なアイコンの標準をサポートするデバイスで PWA アイコン[が][ProgressiveWebAppsChromiumIndex]適切に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e33a-254">**Maskable icons** are a new icon format that support adaptive icons, which enable you to ensure that your [PWA][ProgressiveWebAppsChromiumIndex] icon looks good on devices that support the maskable icons standard.</span></span>  

<span data-ttu-id="4e33a-255">[マニフェスト]**ウィンドウの**[マスク可能なアイコンの最小セーフ\*\*\*\* 領域のみを表示する] チェック ボックスをオンにして、Android Oreo デバイスでマスク可能なアイコンが良好に表示されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="4e33a-255">Enable the new **Show only the minimum safe area for maskable icons** checkbox in the **Manifest** pane to check that your maskable icon looks good on Android Oreo devices.</span></span>  

<!-- Check out [Are my current icons ready?] to learn more.  -->  

:::image type="complex" source="../../media/2020/03/maskable-icons.msft.png" alt-text="[マスク可能なアイコンの最小安全領域のみを表示する] チェック ボックス" lightbox="../../media/2020/03/maskable-icons.msft.png":::
   <span data-ttu-id="4e33a-257">[**マスク可能なアイコンの最小安全領域のみを表示する] チェック ボックス**</span><span class="sxs-lookup"><span data-stu-id="4e33a-257">The **Show only the minimum safe area for maskable icons** checkbox</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="4e33a-258">この機能は、Microsoft Edge 81 で起動しました。</span><span class="sxs-lookup"><span data-stu-id="4e33a-258">This feature launched in Microsoft Edge 81.</span></span>  <span data-ttu-id="4e33a-259">この 83 のMicrosoft Edgeについては[、「What's New In DevTools (Microsoft Edge 81) 」で説明されていない][WhatsNew81]。</span><span class="sxs-lookup"><span data-stu-id="4e33a-259">The updates covered here in Microsoft Edge 83 were not covered in [What's New In DevTools (Microsoft Edge 81)][WhatsNew81].</span></span>  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="4e33a-260">Microsoft Edge プレビュー チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="4e33a-260">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="4e33a-261">Windows または macOS を使用している場合、[Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="4e33a-261">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="4e33a-262">プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4e33a-262">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="4e33a-263">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="4e33a-263">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[WhatsNew81]: ../01/devtools.md "DevTools の新機能 (Microsoft Edge 81) |Microsoft Docs"  

[DevtoolsCommandMenuIndex]: ../../../command-menu/index.md "[DevTools コマンド メニュー] Microsoft Edgeを使用してコマンドを実行|Microsoft Docs"  
[DevtoolsCssIndex]: ../../../css/index.md "はじめにCSS の表示と変更を使用|Microsoft Docs"  
[DevtoolsCssReferenceColorPicker]: ../../../css/reference.md#change-colors-with-the-color-picker "[カラー ピッカー] を使用して色を|Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: ../../../customize/index.md#settings "設定 - DevTools Microsoft Edgeをカスタマイズ|Microsoft Docs"  
[DevtoolsCustomizePlacementsChangeMainMenu]: ../../../customize/placement.md#change-placement-from-the-main-menu "メイン メニューから配置を変更|Microsoft Docs"  
[DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTool]: ../../../evaluate-performance/reference.md#analyze-rendering-performance-with-the-rendering-tool "レンダリング ツール を使用してレンダリングパフォーマンスを分析|Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity]: ../../../evaluate-performance/reference.md#view-main-thread-activity "メイン スレッドアクティビティの|Microsoft Docs"  
[DevtoolsJavascriptBreakpointsLineCode]: ../../../javascript/breakpoints.md#line-of-code-breakpoints "コード行ブレークポイント - DevTools アプリケーションでブレークポイントを使用してコードMicrosoft Edgeする|Microsoft Docs"  
[DevtoolsNetworkReferenceFilterRequestsProperties]: ../../../network/reference.md#filter-requests-by-properties "プロパティ別に要求をフィルター処理する - ネットワーク分析|Microsoft Docs"  
[DevtoolsRemoteDebuggingWindows]: ../../../remote-debugging/windows.md "Windows 10 デバイスのリモート デバッグの概要 | Microsoft Docs"  

[ProgressiveWebAppsChromiumIndex]: ../../../../progressive-web-apps-chromium/index.md "Windows 上のプログレッシブ Web アプリ | Microsoft Docs"  

[WindowsUwpDebugTestPerfDevicePortal]: /windows/uwp/debug-test-perf/device-portal "Windowsデバイス ポータルの概要"  

[RemoteTools]: https://www.microsoft.com/store/apps/9P6CMFV44ZLT "リモート ツール for Microsoft Edge (Beta)"  
[MicrosoftStore]: https://www.microsoft.com/store/apps/windows "Microsoft Store"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[WindowsBlogStableRelease]: https://blogs.windows.com/msedgedev/2020/03/20 "システムの安定したチャネル リリースMicrosoft Edge"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[Devtools%20Docs%20Feedback] "新しい問題 - MicrosoftDocs/edge-developer - GitHub"  

[MicrosoftVisualstudioMain]: https://visualstudio.microsoft.com "Visual Studio"  

[VisualstudioCodeMain]: https://code.visualstudio.com "Visual Studio Code"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools | ツイートを投稿する"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter アカウント"  
[TheWebWeWantMain]: https://webwewant.fyi "必要な Web"  

[ColorBlindnessTypes]: http://www.colourblindawareness.org/colour-blindness/types-of-colour-blindness "色覚の種類"  
<!-- this link must be http, not https -->  

[MDNAcceptLanguage]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Accept-Language "Accept-Language |MDN"  
[MDNCookiePath]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie#Directives "Set-Cookie |MDN"  

[MathiasByensLocaleDemo]: https://mathiasbynens.be/demo/locale "ロケールに依存するコード例"  

[CR963183]: https://crbug.com/963183 "問題 963183: DevTools が WCAG 準拠ではない"  
[CR1003700]: https://crbug.com/1003700 "Issue 1003700: カラー ビジョン不足シミュレーションの DevTools サポートの追加"  
[CR1011679]: https://crbug.com/1011679 "問題 1011679: コマンド メニューを使用して 'Dock to Left' を導入する"  
[CR1016501]: https://crbug.com/1016501 "問題 1016501: 機能要求: すべてのローカルオーバーライドを削除するボタン"  
[CR1050999]: https://crbug.com/1050999 "問題 1050999: [プロパティ] タブ"  
[CR1051466]: https://crbug.com/1051466 "問題 1051466: DevTools での COOP/COEP デバッグのサポート"  
[CR1054447]: https://crbug.com/1054447 "問題 1054447: DevTools タイムラインでパフォーマンス 指標を更新する"  
[CR1051822]: https://crbug.com/1051822 "問題 1051822: DevTools: ロケールをエミュレートするための UI の追加"
[CR1041830]: https://crbug.com/1041830 "問題 1041830: ブレークポイントの色を改善する"
[CR1050855]: https://crbug.com/1050855 "問題 1050855: 設定が検出しにくい"
[CR1056348]: https://crbug.com/1056348 "問題 1056348: Infobar コンポーネントの更新"

[COOP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.tu4hyy6v12wn "COOP と COEP の説明 - クロスオリジン の Opener ポリシー"  
[COEP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.uo6kivyh0ge2 "COOP と COEP の説明 - クロスオリジン エンベダー ポリシー"  

[GithubGoogleChromeLighthouse]: https://github.com/GoogleChrome/lighthouse "ライトハウス |GitHub"  

> [!NOTE]
> <span data-ttu-id="4e33a-305">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="4e33a-305">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="4e33a-306">元のページは [ここ](https://developer.chrome.com/blog/new-in-devtools-83) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="4e33a-306">The original page is found [here](https://developer.chrome.com/blog/new-in-devtools-83) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="4e33a-308">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="4e33a-308">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
