---
description: カラービジョンの欠陥のエミュレート、コマンドメニューの左側へのドッキングなどを行います。
title: DevTools の新機能 (Microsoft Edge 83)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: f9eb306ab7b30495c91ff4a70797898459d7e722
ms.sourcegitcommit: b337717957529239434b4e8e1e167aebf0543518
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015483"
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

# <span data-ttu-id="52d85-104">DevTools の新機能 (Microsoft Edge 83)</span><span class="sxs-lookup"><span data-stu-id="52d85-104">What's New In DevTools (Microsoft Edge 83)</span></span>  

<span data-ttu-id="52d85-105">更新された Chromium のスケジュールに従って、今後の Microsoft Edge リリースのスケジュールを調整し、Microsoft Edge 82 リリースをキャンセルしています。</span><span class="sxs-lookup"><span data-stu-id="52d85-105">Following the updated Chromium schedule, we are adjusting our schedule for upcoming Microsoft Edge releases and cancelling the Microsoft Edge 82 release.</span></span> <span data-ttu-id="52d85-106">詳しくは、 [ブログの投稿][WindowsBlogStableRelease] をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="52d85-106">Check out our [blog post][WindowsBlogStableRelease] for more info.</span></span>  

<span data-ttu-id="52d85-107">Microsoft Edge 83 の DevTools で利用できる新機能を紹介します。</span><span class="sxs-lookup"><span data-stu-id="52d85-107">Here are the new features available in the DevTools in Microsoft Edge 83.</span></span>  

## <span data-ttu-id="52d85-108">Microsoft Edge DevTools チームからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="52d85-108">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="52d85-109">以下のセクションでは、Microsoft Edge DevTools チームから見落とした可能性があるお知らせの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="52d85-109">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span></span> <span data-ttu-id="52d85-110">それらを確認して、DevTools、Visual Studio コード拡張などの新機能を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="52d85-110">Check them out to try new features in the DevTools, Visual Studio Code extensions, and more.</span></span>  <span data-ttu-id="52d85-111">開発者ツールの最新の機能と最大の機能を常に最新の状態に維持するには、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] をダウンロードして、 [Twitter に従っ][EdgeDevToolsTwitterAccount]てください。</span><span class="sxs-lookup"><span data-stu-id="52d85-111">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="52d85-112">Windows 10 デバイスで Microsoft Edge をリモートでデバッグする</span><span class="sxs-lookup"><span data-stu-id="52d85-112">Remotely debug Microsoft Edge on Windows 10 Devices</span></span>  

<span data-ttu-id="52d85-113">Microsoft [Edge \ (ベータ版) アプリのリモートツール][RemoteTools] は、 [microsoft Store][MicrosoftStore]で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="52d85-113">The [Remote Tools for Microsoft Edge \(Beta\)][RemoteTools] app is now available in the [Microsoft Store][MicrosoftStore].</span></span>  <span data-ttu-id="52d85-114">[Windows Device Portal][WindowsUwpDebugTestPerfDevicePortal]を拡張するこのアプリを使うと、開発用コンピューター上で実行されている microsoft edge のインスタンスからリモートの windows 10 デバイスに接続することができます。ターゲットの一覧 (Microsoft Edge と Pwas は Windows 10 デバイスで開か[れていました][PprgressiveWebAppsChromiumIndex]) をご覧ください。また、開発用コンピューターで、リモートの windows 10 デバイスで実行さ</span><span class="sxs-lookup"><span data-stu-id="52d85-114">Using this app, which extends the [Windows Device Portal][WindowsUwpDebugTestPerfDevicePortal], you are able to connect from the instance of Microsoft Edge running on your development machine to a remote Windows 10 device, see a list of targets \(all tabs in Microsoft Edge and [PWAs][PprgressiveWebAppsChromiumIndex] open on the Windows 10 device\), and use the DevTools on your development machine against a target running on the remote Windows 10 device.</span></span>  

:::image type="complex" source="../../media/2020/03/remote-tools.msft.png" alt-text="Microsoft Store で利用できる Microsoft Edge (ベータ版) アプリのリモートツール" lightbox="../../media/2020/03/remote-tools.msft.png":::
   <span data-ttu-id="52d85-116">Microsoft [Store][MicrosoftStore]で利用できる[Microsoft Edge (ベータ版) アプリのリモートツール][RemoteTools]</span><span class="sxs-lookup"><span data-stu-id="52d85-116">The [Remote Tools for Microsoft Edge (Beta)][RemoteTools] app available in the [Microsoft Store][MicrosoftStore]</span></span>  
:::image-end:::  

<span data-ttu-id="52d85-117">[Windows 10 デバイスと、リモートデバッグ用の開発マシンのセットアップガイドを参照][DevtoolsRemoteDebuggingWindows]してください。</span><span class="sxs-lookup"><span data-stu-id="52d85-117">[Read our guide for setting up your Windows 10 device and your development machine for remote debugging][DevtoolsRemoteDebuggingWindows].</span></span>  <span data-ttu-id="52d85-118">[ツイート][PostTweetEdgeDevTools]または [[フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team)] アイコンをクリックして、リモートデバッグのエクスペリエンスについてお知らせください。</span><span class="sxs-lookup"><span data-stu-id="52d85-118">Let us know about your remote debugging experience by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

### <span data-ttu-id="52d85-119">新しい設定へのアクセス方法</span><span class="sxs-lookup"><span data-stu-id="52d85-119">New ways to access Settings</span></span>  

<span data-ttu-id="52d85-120">Devtools にはさまざまな設定が用意されており、これらをカスタマイズして、開発者向けツールの外観、操作性、および作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="52d85-120">There are tons of settings for the DevTools that you are able to customize to make the DevTools look, feel, and work the way you need.</span></span> <span data-ttu-id="52d85-121">Microsoft Edge 83 では、DevTools の [設定][DevtoolsCustomizeIndexSettings] へのアクセスが非常に簡単になりました。</span><span class="sxs-lookup"><span data-stu-id="52d85-121">In Microsoft Edge 83, accessing [Settings][DevtoolsCustomizeIndexSettings] in the DevTools is now much easier.</span></span> <span data-ttu-id="52d85-122">[コンソール通知] の横にある歯車アイコンとメインメニューの [設定] を開きます。</span><span class="sxs-lookup"><span data-stu-id="52d85-122">Open Settings with the gear icon next to Console alerts and the main menu.</span></span>  

:::image type="complex" source="../../media/2020/03/settings.msft.png" alt-text="歯車アイコンによって、DevTools の設定が開きます。" lightbox="../../media/2020/03/settings.msft.png":::
   <span data-ttu-id="52d85-124">歯車アイコンによって、DevTools の **設定** が開きます。</span><span class="sxs-lookup"><span data-stu-id="52d85-124">The gear icon opens **Settings** in the DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="52d85-125">[**その他のツール**] の下にある**メインメニュー**から[設定][DevtoolsCustomizeIndexSettings]を開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="52d85-125">You are also able to open [Settings][DevtoolsCustomizeIndexSettings] from the **Main Menu** under **More tools**.</span></span>

:::image type="complex" source="../../media/2020/03/settings2.msft.png" alt-text="> の [その他のツール > 設定] のメインメニュー" lightbox="../../media/2020/03/settings2.msft.png":::
   <span data-ttu-id="52d85-127">**メインメニュー**  > **その他のツール**  > **設定**</span><span class="sxs-lookup"><span data-stu-id="52d85-127">**Main Menu** > **More tools** > **Settings**</span></span>  
:::image-end:::  

<span data-ttu-id="52d85-128">Chromium の問題 [#1050855][CR1050855]</span><span class="sxs-lookup"><span data-stu-id="52d85-128">Chromium issue [#1050855][CR1050855]</span></span>

### <span data-ttu-id="52d85-129">新機能と改善された infobars</span><span class="sxs-lookup"><span data-stu-id="52d85-129">New and improved infobars</span></span>

<span data-ttu-id="52d85-130">DevTools の情報通知バー \ (infobars) では、見栄えと機能が改善されました。</span><span class="sxs-lookup"><span data-stu-id="52d85-130">Informational notification bars \(infobars\) in DevTools now have an improved look and more functionality.</span></span> <span data-ttu-id="52d85-131">Microsoft Edge 83 では、適切な操作をすぐに行うことができるように、infobars ボタンが読みやすく、提供されています。</span><span class="sxs-lookup"><span data-stu-id="52d85-131">In Microsoft Edge 83, infobars are easier to read and provide buttons so you are able to take the relevant action right away.</span></span>  

:::image type="complex" source="../../media/2020/03/infobar.msft.png" alt-text="Microsoft Edge 83 で縮小版のファイルをきれいに印刷するための情報バー" lightbox="../../media/2020/03/infobar.msft.png":::
   <span data-ttu-id="52d85-133">Microsoft Edge バージョン83でミニのファイルを印刷するための情報バー</span><span class="sxs-lookup"><span data-stu-id="52d85-133">Infobar for pretty-printing a minified file in Microsoft Edge Version 83</span></span>  
:::image-end:::  

<span data-ttu-id="52d85-134">Chromium の問題 [#1056348][CR1056348]</span><span class="sxs-lookup"><span data-stu-id="52d85-134">Chromium issue [#1056348][CR1056348]</span></span>

### <span data-ttu-id="52d85-135">キーボードでカラーピッカー内を移動する</span><span class="sxs-lookup"><span data-stu-id="52d85-135">Navigate the Color Picker with your keyboard</span></span>  

<span data-ttu-id="52d85-136">[カラーピッカー][DevtoolsCssReferenceColorPicker]は、変更と宣言のための[要素パネル][DevtoolsCssIndex]の GUI です `color` `background-color` 。</span><span class="sxs-lookup"><span data-stu-id="52d85-136">The [Color Picker][DevtoolsCssReferenceColorPicker] is a GUI in the [Elements panel][DevtoolsCssIndex] for changing `color` and `background-color` declarations.</span></span>  <span data-ttu-id="52d85-137">以前のバージョンの Microsoft Edge では、キーボードを使って[カラーピッカー][DevtoolsCssReferenceColorPicker]の [**階調**] セクションを移動できませんでした。</span><span class="sxs-lookup"><span data-stu-id="52d85-137">In previous versions of Microsoft Edge, you were not able to navigate the **Shades** section of the [Color Picker][DevtoolsCssReferenceColorPicker] with the keyboard.</span></span>  

:::image type="complex" source="../../media/2020/03/color-picker.msft.png" alt-text="これでキーボードを使用して、カラーピッカーの [階調] セクションでセレクターを移動できるようになりました" lightbox="../../media/2020/03/color-picker.msft.png":::
   <span data-ttu-id="52d85-139">これでキーボードを使用して、[カラーピッカー][DevtoolsCssReferenceColorPicker]の [**階調**] セクションでセレクターを移動できるようになりました</span><span class="sxs-lookup"><span data-stu-id="52d85-139">You are now able to use your keyboard to move the selector in the **Shades** section of the [Color Picker][DevtoolsCssReferenceColorPicker]</span></span>  
:::image-end:::  

<span data-ttu-id="52d85-140">Microsoft Edge 83 では、キーボードを使用して、カラーピッカーの [ **階調** ] セクションでセレクターを移動できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="52d85-140">In Microsoft Edge 83, you are now able to use the keyboard to move the selector in the **Shades** section of the Color Picker.</span></span>  

<span data-ttu-id="52d85-141">Chromium の問題 [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="52d85-141">Chromium issue [#963183][CR963183]</span></span>  

### <span data-ttu-id="52d85-142">ページの更新後に [プロパティ] タブが表示されるようになりました</span><span class="sxs-lookup"><span data-stu-id="52d85-142">Properties tab now populates after a page refresh</span></span>  

<span data-ttu-id="52d85-143">Microsoft Edge 81 以前では、[[要素] パネル][DevtoolsCssIndex]の [**プロパティ] タブ**は、ページの更新によって解除されました。</span><span class="sxs-lookup"><span data-stu-id="52d85-143">In Microsoft Edge 81 and earlier, the **Properties tab** in the [Elements panel][DevtoolsCssIndex] was broken by page refreshes.</span></span>  <span data-ttu-id="52d85-144">ページを更新すると、[ **プロパティ] タブ** に現在選択されている要素のプロパティが設定されませんでした。</span><span class="sxs-lookup"><span data-stu-id="52d85-144">When you refreshed the page, the **Properties tab** did not populate the properties of the currently-selected element.</span></span>  

:::image type="complex" source="../../media/2020/03/properties-in-81.msft.png" alt-text="Microsoft Edge 81 以前のバージョンでは、ページの更新後に [プロパティ] タブが空白になっていました" lightbox="../../media/2020/03/properties-in-81.msft.png":::
   <span data-ttu-id="52d85-146">Microsoft Edge 81 以前のバージョンでは、ページの更新後に [ **プロパティ] タブ** が空白になっていました</span><span class="sxs-lookup"><span data-stu-id="52d85-146">In Microsoft Edge 81 and earlier, the **Properties tab** was blank after a page refresh</span></span>  
:::image-end:::  

<span data-ttu-id="52d85-147">Microsoft Edge 83 では、[ **プロパティ] タブ**のページを更新した後に、現在選択されている要素のプロパティを表示できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="52d85-147">In Microsoft Edge 83, you are now able to see the properties of the currently-selected element after a page refresh in the **Properties tab**.</span></span>  

:::image type="complex" source="../../media/2020/03/properties-in-82.msft.png" alt-text="Microsoft Edge 83 の [プロパティ] タブには、ページの更新後に現在選択されている要素のプロパティが表示されます。" lightbox="../../media/2020/03/properties-in-82.msft.png":::
   <span data-ttu-id="52d85-149">Microsoft Edge 83 の [ **プロパティ] タブ** には、ページの更新後に現在選択されている要素のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="52d85-149">In Microsoft Edge 83, the **Properties tab** displays the properties of the currently-selected element after a page refresh</span></span>  
:::image-end:::  

<span data-ttu-id="52d85-150">Chromium の問題 [#1050999][CR1050999]</span><span class="sxs-lookup"><span data-stu-id="52d85-150">Chromium issue [#1050999][CR1050999]</span></span>  

### <span data-ttu-id="52d85-151">方向キーを使用して変更ツールをスクロールする</span><span class="sxs-lookup"><span data-stu-id="52d85-151">Use the arrow keys to scroll in the Changes tool</span></span>  

<span data-ttu-id="52d85-152">[ **変更] ツール** では、DEVTOOLS で CSS または JavaScript に加えた変更を追跡します。</span><span class="sxs-lookup"><span data-stu-id="52d85-152">The **Changes tool** tracks any changes you have made to CSS or JavaScript in the DevTools.</span></span>  <span data-ttu-id="52d85-153">[ **変更] ツール** を使用して、すべての変更をすばやく確認して、エディター/IDE に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="52d85-153">You are able to use the **Changes tool** to quickly see all your changes and take those back to your editor/IDE.</span></span>  

<span data-ttu-id="52d85-154">Devtools を押して [**変更] ツール**を開き、 `Ctrl` + `Shift` + `P` [コマンドメニュー][DevToolsCommandMenuIndex]を開き、入力 `changes` します。</span><span class="sxs-lookup"><span data-stu-id="52d85-154">Open the **Changes tool** by pressing `Ctrl`+`Shift`+`P` in the DevTools to open the [Command Menu][DevToolsCommandMenuIndex] and typing `changes`.</span></span>  <span data-ttu-id="52d85-155">[ **変更箇所の表示** ] コマンドを選択して実行し、[devtools] ドローワの [ **変更] ツール** を開きます。</span><span class="sxs-lookup"><span data-stu-id="52d85-155">Select and run the **Show Changes** command to open the **Changes tool** in the DevTools drawer.</span></span>  

<span data-ttu-id="52d85-156">縮小されたファイルに変更を加えた場合は、[ **変更] ツール** を使って横方向にスクロールして、表示されているすべてのコードを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="52d85-156">When you have made a change to a minified file, the **Changes tool** enables you to scroll horizontally to see all of your minified code.</span></span>  <span data-ttu-id="52d85-157">Microsoft Edge 83 以降、キーボードの方向キーを使用して水平方向にスクロールできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="52d85-157">Starting in Microsoft Edge 83, you may now scroll horizontally using the arrow keys on your keyboard.</span></span>  

:::image type="complex" source="../../media/2020/03/changes.msft.png" alt-text="Microsoft Edge 83 では、方向キーを使用して水平方向にスクロールして、[変更] ツールに表示されているバーを表示することができます。" lightbox="../../media/2020/03/changes.msft.png":::
   <span data-ttu-id="52d85-159">Microsoft Edge 83 では、方向キーを使用して水平方向にスクロールして、[**変更] ツール**の縮小表示コードに加えた変更を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="52d85-159">In Microsoft Edge 83, you may scroll horizontally with the arrow keys to see the changes you made to your minified code in the **Changes tool**</span></span>  
:::image-end:::  

<span data-ttu-id="52d85-160">スクリーンリーダーまたはキーボードを使用して DevTools を移動する場合は、 [ツイート][PostTweetEdgeDevTools] でフィードバックを送信するか、[ [フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team) ] アイコンをクリックしてフィードバックを送信してください。</span><span class="sxs-lookup"><span data-stu-id="52d85-160">If you use screen readers or the keyboard to navigate around the DevTools, send us your feedback by [tweeting][PostTweetEdgeDevTools] at us or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="52d85-161">Chromium の問題 [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="52d85-161">Chromium issue [#963183][CR963183]</span></span>  

## <span data-ttu-id="52d85-162">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="52d85-162">Announcements from the Chromium project</span></span>  

<span data-ttu-id="52d85-163">次のセクションでは、open source Chromium プロジェクトに寄与した Microsoft Edge 83 で利用可能なその他の機能を示します。</span><span class="sxs-lookup"><span data-stu-id="52d85-163">The following sections announce additional features available in Microsoft Edge 83 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="52d85-164">ビジョンの欠陥のエミュレート</span><span class="sxs-lookup"><span data-stu-id="52d85-164">Emulate vision deficiencies</span></span>  

<span data-ttu-id="52d85-165">[ [レンダリング] タブ][DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab] を開き、新しい **エミュレート** されたビジョンの機能を使用して、さまざまな視覚障碍を持つユーザーがサイトでどのように利用できるかをわかりやすく把握します。</span><span class="sxs-lookup"><span data-stu-id="52d85-165">Open the [Rendering tab][DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab] and use the new **Emulate vision deficiencies** feature to get a better idea of how people with different types of vision deficiencies experience your site.</span></span>  

:::image type="complex" source="../../media/2020/03/vision.msft.png" alt-text="ぼやけたビジョンのエミュレート" lightbox="../../media/2020/03/vision.msft.png":::
   <span data-ttu-id="52d85-167">ぼやけたビジョンのエミュレート</span><span class="sxs-lookup"><span data-stu-id="52d85-167">Emulating blurred vision</span></span>  
:::image-end:::  

<span data-ttu-id="52d85-168">DevTools は、ぼやけたビジョンと次の [種類の色ビジョンの欠陥][ColorBlindnessTypes]をエミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="52d85-168">DevTools is able to emulate blurred vision and the following [types of color vision deficiencies][ColorBlindnessTypes].</span></span>  

| <span data-ttu-id="52d85-169">カラービジョンの欠陥</span><span class="sxs-lookup"><span data-stu-id="52d85-169">Color Vision Deficiency</span></span> | <span data-ttu-id="52d85-170">詳細</span><span class="sxs-lookup"><span data-stu-id="52d85-170">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="52d85-171">Protanopia</span><span class="sxs-lookup"><span data-stu-id="52d85-171">Protanopia</span></span> | <span data-ttu-id="52d85-172">赤の光を感じることはできません。</span><span class="sxs-lookup"><span data-stu-id="52d85-172">The inability to perceive any red light.</span></span> |  
| <span data-ttu-id="52d85-173">Deuteranopia</span><span class="sxs-lookup"><span data-stu-id="52d85-173">Deuteranopia</span></span> | <span data-ttu-id="52d85-174">緑の光を感じることはできません。</span><span class="sxs-lookup"><span data-stu-id="52d85-174">The inability to perceive any green light.</span></span> |  
| <span data-ttu-id="52d85-175">Tritanopia</span><span class="sxs-lookup"><span data-stu-id="52d85-175">Tritanopia</span></span> | <span data-ttu-id="52d85-176">青い光を感じることはできません。</span><span class="sxs-lookup"><span data-stu-id="52d85-176">The inability to perceive any blue light.</span></span> |  
| <span data-ttu-id="52d85-177">Achroopsia</span><span class="sxs-lookup"><span data-stu-id="52d85-177">Achromatopsia</span></span> | <span data-ttu-id="52d85-178">灰色の階調 (非常に珍しい) を除き、どの色もまったく感じられません。</span><span class="sxs-lookup"><span data-stu-id="52d85-178">The inability to perceive any color, except for shades of grey \(extremely rare\).</span></span> |  

<span data-ttu-id="52d85-179">これらのカラービジョンの低画質バージョンが存在しますが、実際にはもっと一般的です。</span><span class="sxs-lookup"><span data-stu-id="52d85-179">Less extreme versions of these color vision deficiencies exist, and in fact they are more common.</span></span>  
<span data-ttu-id="52d85-180">たとえば、protanomaly は赤の光に対する感度が低くなっています (protanopia とは異なり、赤の光を完全に認識できないことを示します)。</span><span class="sxs-lookup"><span data-stu-id="52d85-180">For example, protanomaly is a reduced sensitivity to red light (as opposed to protanopia, which is the complete inability to perceive red light).</span></span> <span data-ttu-id="52d85-181">ただし、これらの視覚に障碍がある方が明確に定義されているわけではありません。このような視覚に障碍がある方は、どのユーザーも異なっている可能性があります (関連する色をもっと少なくしたり、小さくしたりできます)。</span><span class="sxs-lookup"><span data-stu-id="52d85-181">However, these -omaly vision deficiencies are not as clearly defined: every person with such a vision deficiency is different and might see things differently (being able to perceive more/less of the relevant colors).</span></span>  

<span data-ttu-id="52d85-182">DevTools での極端なシミュレーションを設計することで、web アプリは、protanomaly、deuteranomaly、tritanomaly、および achromatomaly のユーザーからもアクセスできることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="52d85-182">By designing for the more extreme simulations in DevTools, your web apps are guaranteed to be accessible to people with protanomaly, deuteranomaly, tritanomaly, and achromatomaly as well.</span></span>  

<span data-ttu-id="52d85-183">[ツイート][PostTweetEdgeDevTools]でフィードバックを送信するか、[[フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team)] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="52d85-183">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="52d85-184">Chromium の問題 [#1003700][CR1003700]</span><span class="sxs-lookup"><span data-stu-id="52d85-184">Chromium issue [#1003700][CR1003700]</span></span>  

### <span data-ttu-id="52d85-185">ロケールのエミュレート</span><span class="sxs-lookup"><span data-stu-id="52d85-185">Emulate locales</span></span>  

<span data-ttu-id="52d85-186">**センサー**の場所の位置を設定して、ロケールをエミュレート  >  **Location**します。</span><span class="sxs-lookup"><span data-stu-id="52d85-186">Emulate locales by setting a location in **Sensors** > **Location**.</span></span> <span data-ttu-id="52d85-187">[**コマンドメニュー**を開き][DevToolsCommandMenuIndex]、「 `Sensors` **センサー** 」タブにアクセスして入力します。 これらの操作を実行すると、DevTools で現在の既定のロケールが変更され、次のコードに影響します。</span><span class="sxs-lookup"><span data-stu-id="52d85-187">[Open the **Command Menu**][DevToolsCommandMenuIndex] and type `Sensors` to access the **Sensors** tab.  After performing these actions, DevTools modifies the current default locale, affecting the following code.</span></span>  

*   `Intl.*` <span data-ttu-id="52d85-188">Api などの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="52d85-188">APIs, for example:</span></span> `new Intl.NumberFormat().resolvedOptions().locale`  
*   <span data-ttu-id="52d85-189">その他のロケールに対応した JavaScript Api (など) `String.prototype.localeCompare` `*.prototype.toLocaleString` :</span><span class="sxs-lookup"><span data-stu-id="52d85-189">Other locale-aware JavaScript APIs such as `String.prototype.localeCompare` and `*.prototype.toLocaleString`, for example:</span></span> `123_456..toLocaleString()`  
*   <span data-ttu-id="52d85-190">などの DOM Api `navigator.language`</span><span class="sxs-lookup"><span data-stu-id="52d85-190">DOM APIs such as `navigator.language` and</span></span> `navigator.languages`  
*   <span data-ttu-id="52d85-191">[承認言語][MDNAcceptLanguage]の HTTP 要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="52d85-191">The [Accept-Language][MDNAcceptLanguage] HTTP request header</span></span>  

> [!NOTE]
> <span data-ttu-id="52d85-192">の更新はすぐには `navigator.language` `navigator.languages` 表示されませんが、次のナビゲーションまたはページの更新後にのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="52d85-192">Updates to `navigator.language` and `navigator.languages` are not visible immediately, but only after the next navigation or page refresh.</span></span>  <span data-ttu-id="52d85-193">HTTP ヘッダーへの変更 `Accept-Language` は、以降の要求に対してのみ反映されます。</span><span class="sxs-lookup"><span data-stu-id="52d85-193">Changes to the `Accept-Language` HTTP header are only reflected for subsequent requests.</span></span>  

:::image type="complex" source="../../media/2020/03/locale.msft.png" alt-text="ロケールのエミュレート" lightbox="../../media/2020/03/locale.msft.png":::
   <span data-ttu-id="52d85-195">ロケールのエミュレート</span><span class="sxs-lookup"><span data-stu-id="52d85-195">Emulating a locale</span></span>  
:::image-end:::  

<span data-ttu-id="52d85-196">デモについては、「 [ロケールに依存するコードの例][MathiasByensLocaleDemo]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="52d85-196">To try a demo, see [Locale-dependent code example][MathiasByensLocaleDemo].</span></span>

<span data-ttu-id="52d85-197">Chromium の問題 [#1051822][CR1051822]</span><span class="sxs-lookup"><span data-stu-id="52d85-197">Chromium issue [#1051822][CR1051822]</span></span>

### <span data-ttu-id="52d85-198">Cross-origin Embedder Policy (COEP) のデバッグ</span><span class="sxs-lookup"><span data-stu-id="52d85-198">Cross-Origin Embedder Policy (COEP) debugging</span></span>  

<span data-ttu-id="52d85-199">ネットワークパネルでは、 [クロスオリジンの Embedder ポリシー][COEP] のデバッグ情報が提供されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="52d85-199">The Network panel now provides [Cross-Origin Embedder Policy][COEP] debugging information.</span></span>  

<span data-ttu-id="52d85-200">[ **状態** ] 列には、要求がブロックされた理由と、さらにデバッグのためにその要求のヘッダーを表示するためのリンクが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="52d85-200">The **Status** column now provides a quick explanation of why a request was blocked as well as a link to view the headers of that request for further debugging:</span></span>  

:::image type="complex" source="../../media/2020/03/status.msft.png" alt-text="\* \* Status \* \* 列のブロックされたリクエスト" lightbox="../../media/2020/03/status.msft.png":::
   <span data-ttu-id="52d85-202">[ **状態** 」列でブロックされたリクエスト</span><span class="sxs-lookup"><span data-stu-id="52d85-202">Blocked requests in the **Status** column</span></span>  
:::image-end:::  

<span data-ttu-id="52d85-203">[**ヘッダー** ] タブの [**応答ヘッダー** ] セクションには、問題を解決するための詳しいガイダンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="52d85-203">The **Response Headers** section of the **Headers** tab provides more guidance on how to resolve the issues:</span></span>  

:::image type="complex" source="../../media/2020/03/guidance.msft.png" alt-text="[応答ヘッダー] セクションのその他のガイダンス" lightbox="../../media/2020/03/guidance.msft.png":::
   <span data-ttu-id="52d85-205">[ **応答ヘッダー** ] セクションのその他のガイダンス</span><span class="sxs-lookup"><span data-stu-id="52d85-205">More guidance in the **Response Headers** section</span></span>  
:::image-end:::  

<span data-ttu-id="52d85-206">[ツイート][PostTweetEdgeDevTools]でフィードバックを送信するか、[[フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team)] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="52d85-206">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="52d85-207">Chromium の問題 [#1051466][CR1051466]</span><span class="sxs-lookup"><span data-stu-id="52d85-207">Chromium issue [#1051466][CR1051466]</span></span>  

### <span data-ttu-id="52d85-208">ブレークポイント、条件付きブレークポイント、および logpoints の新しいアイコン</span><span class="sxs-lookup"><span data-stu-id="52d85-208">New icons for breakpoints, conditional breakpoints, and logpoints</span></span>  

<span data-ttu-id="52d85-209">[ソース] パネルには、ブレークポイント、条件付きブレークポイント、および logpoints の新しいアイコンがあります。</span><span class="sxs-lookup"><span data-stu-id="52d85-209">The Sources panel has new icons for breakpoints, conditional breakpoints, and logpoints:</span></span>  

*   <span data-ttu-id="52d85-210">ブレークポイント \ (</span><span class="sxs-lookup"><span data-stu-id="52d85-210">Breakpoints \(</span></span>![まで](../../media/2020/03/breakpoint.msft.png)<span data-ttu-id="52d85-212">\) は赤い円で表されます。</span><span class="sxs-lookup"><span data-stu-id="52d85-212">\) are represented by red circles.</span></span>  
*   <span data-ttu-id="52d85-213">条件付きブレークポイント \ (</span><span class="sxs-lookup"><span data-stu-id="52d85-213">Conditional Breakpoints \(</span></span>![条件付きブレークポイント](../../media/2020/03/conditional.msft.png)<span data-ttu-id="52d85-215">\) は、半赤の半分が白の丸で表されます。</span><span class="sxs-lookup"><span data-stu-id="52d85-215">\) are represented by half-red half-white circles.</span></span>  
*   <span data-ttu-id="52d85-216">Logpoints \ (</span><span class="sxs-lookup"><span data-stu-id="52d85-216">Logpoints \(</span></span>![Logpoint](../../media/2020/03/logpoint.msft.png)<span data-ttu-id="52d85-218">\) は、コンソールアイコンが付いた赤い円で表されます。</span><span class="sxs-lookup"><span data-stu-id="52d85-218">\) are represented by red circles with Console icons.</span></span>  

<span data-ttu-id="52d85-219">新しいアイコンの動機は、他の GUI デバッグツール (通常は色のブレークポイントが赤) との一貫性を高め、3つの機能を一目で簡単に区別できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="52d85-219">The motivation for the new icons was to make the UI more consistent with other GUI debugging tools \(which usually color breakpoints red\) and to make it easier to distinguish between the 3 features at a glance.</span></span>  

<span data-ttu-id="52d85-220">Chromium の問題 [#1041830][CR1041830]</span><span class="sxs-lookup"><span data-stu-id="52d85-220">Chromium issue [#1041830][CR1041830]</span></span>  

### <span data-ttu-id="52d85-221">特定の cookie パスを設定するネットワーク要求を表示する</span><span class="sxs-lookup"><span data-stu-id="52d85-221">View network requests that set a specific cookie path</span></span>  

<span data-ttu-id="52d85-222">[ネットワーク] パネルの [新しいフィルター] キーワードを使用して、 `cookie-path` 特定の[cookie パス][MDNCookiePath]を設定するネットワーク要求に注目します。 **Network**</span><span class="sxs-lookup"><span data-stu-id="52d85-222">Use the new `cookie-path` filter keyword in the **Network** panel to focus on the network requests that set a specific [cookie path][MDNCookiePath].</span></span>  

<span data-ttu-id="52d85-223">他のキーワードを検索するには [、プロパティ別のフィルター要求][DevtoolsNetworkReferenceFilterRequestsProperties] を確認し `cookie-path` ます。</span><span class="sxs-lookup"><span data-stu-id="52d85-223">Check out [Filter requests by properties][DevtoolsNetworkReferenceFilterRequestsProperties] to discover more keywords like `cookie-path`.</span></span>

### <span data-ttu-id="52d85-224">[コマンド] メニューから左へドッキングする</span><span class="sxs-lookup"><span data-stu-id="52d85-224">Dock to left from the Command Menu</span></span>  

<span data-ttu-id="52d85-225">[コマンドメニュー][DevToolsCommandMenuIndex]を開き、コマンドを実行して、 `Dock to left` ビューポートの左側に devtools を移動します。</span><span class="sxs-lookup"><span data-stu-id="52d85-225">Open the [Command Menu][DevToolsCommandMenuIndex] and run the `Dock to left` command to move DevTools to the left of your viewport.</span></span>  

:::image type="complex" source="../../media/2020/03/dock-to-left.msft.png" alt-text="ビューポートの左側にドッキングされた DevTools" lightbox="../../media/2020/03/dock-to-left.msft.png":::
   <span data-ttu-id="52d85-227">ビューポートの左側にドッキングされた DevTools</span><span class="sxs-lookup"><span data-stu-id="52d85-227">DevTools docked to the left of the viewport</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="52d85-228">[ **左から左** ] 機能は、Microsoft Edge 75 以降で使用できますが、以前は [メインメニュー][DevtoolsCustomizePlacementsChangeMainMenu]からしかアクセスできませんでした。</span><span class="sxs-lookup"><span data-stu-id="52d85-228">The **Dock to left** feature has been available since Microsoft Edge 75, but it was previously only accessible from the [Main Menu][DevtoolsCustomizePlacementsChangeMainMenu].</span></span>  <span data-ttu-id="52d85-229">Microsoft Edge 83 の新機能は、コマンドメニューからこの機能にアクセスできるということです。</span><span class="sxs-lookup"><span data-stu-id="52d85-229">The new feature in Microsoft Edge 83 is that you may now access this feature from the Command Menu.</span></span>  

<span data-ttu-id="52d85-230">[ツイート][PostTweetEdgeDevTools]でフィードバックを送信するか、[[フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team)] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="52d85-230">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="52d85-231">Chromium の問題 [#1011679][CR1011679]</span><span class="sxs-lookup"><span data-stu-id="52d85-231">Chromium issue [#1011679][CR1011679]</span></span>  

### <span data-ttu-id="52d85-232">監査パネルが Lighthouse パネルになりました</span><span class="sxs-lookup"><span data-stu-id="52d85-232">The Audits panel is now the Lighthouse panel</span></span>  

<span data-ttu-id="52d85-233">DevTools チームは、開発者からのフィードバックを頻繁に発生させていますが、開発者は [Lighthouse][GithubGoogleChromeLighthouse] を試してみても、"Lighthouse" パネルを見つけることができなかったため、 **監査** パネルは **Lighthouse** パネルになりました。</span><span class="sxs-lookup"><span data-stu-id="52d85-233">The DevTools team frequently got feedback from web developers that while it was possible to run [Lighthouse][GithubGoogleChromeLighthouse] from DevTools, when they tried it out they were not able to find the "Lighthouse" panel, so the **Audits** panel is now the **Lighthouse** panel.</span></span>  

:::image type="complex" source="../../media/2020/03/lighthouse.msft.png" alt-text="Lighthouse パネル" lightbox="../../media/2020/03/lighthouse.msft.png":::
   <span data-ttu-id="52d85-235">Lighthouse パネル</span><span class="sxs-lookup"><span data-stu-id="52d85-235">The Lighthouse panel</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="52d85-236">**Lighthouse**パネルには、サードパーティの web サイトでホストされているコンテンツへのリンクが用意されています。</span><span class="sxs-lookup"><span data-stu-id="52d85-236">The **Lighthouse** panel provides links to content hosted on third-party websites.</span></span>  <span data-ttu-id="52d85-237">Microsoft は、これらのサイトのコンテンツと収集されるデータを管理する責任を負わないものとします。</span><span class="sxs-lookup"><span data-stu-id="52d85-237">Microsoft is not responsible for and has no control over the content of these sites and any data they may collect.</span></span>  

### <span data-ttu-id="52d85-238">フォルダー内のすべてのローカル上書きを削除する</span><span class="sxs-lookup"><span data-stu-id="52d85-238">Delete all Local Overrides in a folder</span></span>  

<span data-ttu-id="52d85-239">**ローカルの上書き**を設定した後、フォルダーを右クリックし、[**すべての上書きの削除**] オプションを選択して、そのフォルダー内のすべてのローカル上書きを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="52d85-239">After setting up **Local Overrides** you may right-click a folder and select the new **Delete all overrides** option to delete all Local Overrides in that folder.</span></span>  

:::image type="complex" source="../../media/2020/03/overrides.msft.png" alt-text="すべての上書きを削除する" lightbox="../../media/2020/03/overrides.msft.png":::
   <span data-ttu-id="52d85-241">すべての上書きを削除する</span><span class="sxs-lookup"><span data-stu-id="52d85-241">Delete all overrides</span></span>  
:::image-end:::  

<span data-ttu-id="52d85-242">[ツイート][PostTweetEdgeDevTools]でフィードバックを送信するか、[[フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team)] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="52d85-242">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="52d85-243">Chromium の問題 [#1016501][CR1016501]</span><span class="sxs-lookup"><span data-stu-id="52d85-243">Chromium issue [#1016501][CR1016501]</span></span>  

### <span data-ttu-id="52d85-244">長いタスクの UI を更新しました</span><span class="sxs-lookup"><span data-stu-id="52d85-244">Updated Long tasks UI</span></span>  

<span data-ttu-id="52d85-245">**長いタスク**とは、web ページをフリーズさせることによって、メインスレッドを長時間 Monopolizes する JavaScript コードです。</span><span class="sxs-lookup"><span data-stu-id="52d85-245">A **Long Task** is JavaScript code that monopolizes the main thread for a long time, causing a web page to freeze.</span></span>  

<span data-ttu-id="52d85-246">現時点では、[ [パフォーマンス] パネルで長いタスクをビジュアル][DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity] 化することができましたが、Microsoft Edge 83 では、[パフォーマンス] パネルに長いタスクの視覚エフェクト UI が更新されています。</span><span class="sxs-lookup"><span data-stu-id="52d85-246">You have been able to [visualize Long Tasks in the Performance panel][DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity] for a while now, but in Microsoft Edge 83 the Long Task visualization UI in the Performance panel has been updated.</span></span>  <span data-ttu-id="52d85-247">タスクの長いタスクの部分が色付きの赤の背景で色付けされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="52d85-247">The Long Task portion of a task is now colored with a striped red background.</span></span>  

:::image type="complex" source="../../media/2020/03/long-task.msft.png" alt-text="新しい長いタスク UI" lightbox="../../media/2020/03/long-task.msft.png":::
   <span data-ttu-id="52d85-249">新しい長いタスク UI</span><span class="sxs-lookup"><span data-stu-id="52d85-249">The new Long Task UI</span></span>  
:::image-end:::  

<span data-ttu-id="52d85-250">[ツイート][PostTweetEdgeDevTools]でフィードバックを送信するか、[[フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team)] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="52d85-250">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="52d85-251">Chromium の問題 [#1054447][CR1054447]</span><span class="sxs-lookup"><span data-stu-id="52d85-251">Chromium issue [#1054447][CR1054447]</span></span>  

### <span data-ttu-id="52d85-252">[マニフェスト] ウィンドウでのマスクのアイコンのサポート</span><span class="sxs-lookup"><span data-stu-id="52d85-252">Maskable icon support in the Manifest pane</span></span>  

<span data-ttu-id="52d85-253">Android Oreo では、さまざまなデバイスモデルのさまざまな図形にアプリのアイコンを表示するアダプティブアイコンが導入されました。</span><span class="sxs-lookup"><span data-stu-id="52d85-253">Android Oreo introduced adaptive icons, which display app icons in a variety of shapes across different device models.</span></span>  <span data-ttu-id="52d85-254">**マスクのアイコン** は、アダプティブアイコンをサポートする新しいアイコン形式であり、これにより、 [PWA][PprgressiveWebAppsChromiumIndex] アイコンが、マスクアイコン標準をサポートするデバイスで適切に表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="52d85-254">**Maskable icons** are a new icon format that support adaptive icons, which enable you to ensure that your [PWA][PprgressiveWebAppsChromiumIndex] icon looks good on devices that support the maskable icons standard.</span></span>  

<span data-ttu-id="52d85-255">[**マニフェスト**] ウィンドウの [新しい**マスクアイコンの最小安全領域のみを表示**する] チェックボックスをオンにして、Oreo デバイスでのマスクアイコンが適切であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="52d85-255">Enable the new **Show only the minimum safe area for maskable icons** checkbox in the **Manifest** pane to check that your maskable icon looks good on Android Oreo devices.</span></span>  

<!-- Check out [Are my current icons ready?] to learn more.  -->  

:::image type="complex" source="../../media/2020/03/maskable-icons.msft.png" alt-text="[マスクアイコンの最小安全な領域のみを表示する] チェックボックス" lightbox="../../media/2020/03/maskable-icons.msft.png":::
   <span data-ttu-id="52d85-257">[ **マスクアイコンの最小安全領域のみを表示** する] チェックボックス</span><span class="sxs-lookup"><span data-stu-id="52d85-257">The **Show only the minimum safe area for maskable icons** checkbox</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="52d85-258">この機能は、Microsoft Edge 81 で開始されました。</span><span class="sxs-lookup"><span data-stu-id="52d85-258">This feature launched in Microsoft Edge 81.</span></span>  <span data-ttu-id="52d85-259">Microsoft Edge 83 で取り上げられている更新プログラムについては、 [「DevTools (Microsoft edge 81) の新機能][WhatsNew81]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52d85-259">The updates covered here in Microsoft Edge 83 were not covered in [What's New In DevTools (Microsoft Edge 81)][WhatsNew81].</span></span>  

## <span data-ttu-id="52d85-260">Microsoft Edge preview チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="52d85-260">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="52d85-261">Windows または macOS を使用している場合は、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="52d85-261">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="52d85-262">プレビューチャネルを使うと、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="52d85-262">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="52d85-263">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="52d85-263">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[WhatsNew81]: ../01/devtools.md "DevTools の新機能 (Microsoft Edge 81) |Microsoft ドキュメント"  

[DevToolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する |Microsoft ドキュメント"  
[DevtoolsCssReferenceColorPicker]: /microsoft-edge/devtools-guide-chromium/css/reference#change-colors-with-the-color-picker "カラーピッカーを使用して色を変更する |Microsoft ドキュメント"  
[DevtoolsCssIndex]: /microsoft-edge/devtools-guide-chromium/css/index "CSS の表示と変更の概要 |Microsoft ドキュメント"  
[DevtoolsCustomizePlacementsChangeMainMenu]: /microsoft-edge/devtools-guide-chromium/customize/placement#change-placement-from-the-main-menu "メインメニューから配置を変更する |Microsoft ドキュメント"  
[DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#view-main-thread-activity "メインスレッドアクティビティの表示 |Microsoft ドキュメント"  
[DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "[レンダリング] タブでのレンダリングのパフォーマンスの分析 |Microsoft ドキュメント"  
[PprgressiveWebAppsChromiumIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows のプログレッシブ Web アプリ |Microsoft ドキュメント"  
[DevtoolsRemoteDebuggingWindows]: /microsoft-edge/devtools-guide-chromium/remote-debugging/windows "Windows 10 デバイスのリモートデバッグの概要 |Microsoft ドキュメント"  
[DevtoolsJavascriptBreakpointsLineCode]: /microsoft-edge/devtools-guide-chromium/javascript/breakpoints#line-of-code-breakpoints "行コードのブレークポイント-Microsoft Edge DevTools のブレークポイントでコードを一時停止する方法 |Microsoft ドキュメント"
[DevtoolsNetworkReferenceFilterRequestsProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties "プロパティによるフィルター要求-ネットワーク分析のリファレンス |Microsoft ドキュメント"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定-Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"  

[WindowsUwpDebugTestPerfDevicePortal]: /windows/uwp/debug-test-perf/device-portal "Windows Device Portal の概要"  

[RemoteTools]: https://www.microsoft.com/store/apps/9P6CMFV44ZLT "Microsoft Edge 向けリモートツール (ベータ版)"  
[MicrosoftStore]: https://www.microsoft.com/store/apps/windows "Microsoft ストア"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Preview チャネル"  

[WindowsBlogStableRelease]: https://blogs.windows.com/msedgedev/2020/03/20 "Microsoft Edge の安定したチャネルリリースでの更新"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新しい問題-Microsoft のドキュメント/エッジ-開発者-GitHub"  

[MicrosoftVisualstudio]: https://visualstudio.microsoft.com "Visual Studio"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio コード"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |ツイートを投稿する"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter アカウント"  
[TheWebWeWant]: https://webwewant.fyi "必要な Web"  

[ColorBlindnessTypes]: http://www.colourblindawareness.org/colour-blindness/types-of-colour-blindness "色障碍のある種類"  

[MDNAcceptLanguage]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Accept-Language "受諾-言語 |MDN"  
[MDNCookiePath]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie#Directives "Cookie の設定 |MDN"  

[MathiasByensLocaleDemo]: https://mathiasbynens.be/demo/locale "ロケールに依存するコードの例"  

[CR963183]: https://crbug.com/963183 "問題 963183: DevTools は WCAG に準拠していません"  
[CR1003700]: https://crbug.com/1003700 "問題 1003700: カラービジョンの欠陥シミュレーションのための DevTools のサポートを追加する"  
[CR1011679]: https://crbug.com/1011679 "問題 1011679: コマンドメニューを使用して "Dock to Left" を導入する"  
[CR1016501]: https://crbug.com/1016501 "問題 1016501: 機能の要求: すべてのローカル上書きを削除するためのボタン"  
[CR1050999]: https://crbug.com/1050999 "問題 1050999: [プロパティ] タブ"  
[CR1051466]: https://crbug.com/1051466 "問題 1051466: DevTools での CO-OP/COEP のデバッグのサポート"  
[CR1054447]: https://crbug.com/1054447 "問題 1054447: DevTools のタイムラインでのパフォーマンスメトリックの更新"  
[CR1051822]: https://crbug.com/1051822 "問題 1051822: DevTools: ロケールをエミュレートするための UI を追加する"
[CR1041830]: https://crbug.com/1041830 "問題 1041830: ブレークポイントの色を改善する"
[CR1050855]: https://crbug.com/1050855 "問題 1050855: 設定ビューを見つけるのが難しい"
[CR1056348]: https://crbug.com/1056348 "問題 1056348: 情報バーのコンポーネントの更新"

[COOP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.tu4hyy6v12wn "CO-OP および COEP についての説明 (クロスオリジンの Opener ポリシー)"  
[COEP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.uo6kivyh0ge2 "CO-OP および COEP についての説明 (クロスオリジンの Embedder ポリシー)"  

[GithubGoogleChromeLighthouse]: https://github.com/GoogleChrome/lighthouse "Lighthouse |GitHub"  

> [!NOTE]
> <span data-ttu-id="52d85-305">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="52d85-305">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="52d85-306">元のページは [ここ](https://developers.google.com/web/updates/2020/03/devtools/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="52d85-306">The original page is found [here](https://developers.google.com/web/updates/2020/03/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="52d85-308">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="52d85-308">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
