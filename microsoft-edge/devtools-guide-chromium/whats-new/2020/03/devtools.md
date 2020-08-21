---
title: DevTools の新機能 (Microsoft Edge 83)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: f1b5d147aac1b8b527cc7365f9f91a2a7974863e
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942220"
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

# <span data-ttu-id="1d8ef-103">DevTools の新機能 (Microsoft Edge 83)</span><span class="sxs-lookup"><span data-stu-id="1d8ef-103">What's New In DevTools (Microsoft Edge 83)</span></span>  

<span data-ttu-id="1d8ef-104">更新された Chromium スケジュールの後に、今後の Microsoft Edge リリースのスケジュールを調整し、Microsoft Edge 82 リリースをキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-104">Following the updated Chromium schedule, we are adjusting our schedule for upcoming Microsoft Edge releases and cancelling the Microsoft Edge 82 release.</span></span> <span data-ttu-id="1d8ef-105">詳細については、ブ [ログの投稿][WindowsBlogStableRelease] をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-105">Check out our [blog post][WindowsBlogStableRelease] for more info.</span></span>  

<span data-ttu-id="1d8ef-106">Microsoft Edge 83 の DevTools で使用可能な新機能を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-106">Here are the new features available in the DevTools in Microsoft Edge 83.</span></span>  

## <span data-ttu-id="1d8ef-107">Microsoft Edge DevTools チームからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="1d8ef-107">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="1d8ef-108">以下のセクションは、Microsoft Edge DevTools チームに見つからない可能性があるお知らせの一覧です。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-108">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span></span> <span data-ttu-id="1d8ef-109">デベロッパー、VS コード拡張機能などで新機能を試すようにしてください。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-109">Check them out to try new features in the DevTools, VS Code extensions, and more.</span></span>  <span data-ttu-id="1d8ef-110">開発者ツールの最新機能と最大の機能をすべて最新の状態に保つためには [、Microsoft Edge のプレビュー][MicrosoftEdgePreviewChannels] チャネルを [ダウンロードし、Twitter でフォローしてください][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-110">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="1d8ef-111">Windows 10 デバイスで Microsoft Edge をリモートでデバッグする</span><span class="sxs-lookup"><span data-stu-id="1d8ef-111">Remotely debug Microsoft Edge on Windows 10 Devices</span></span>  

<span data-ttu-id="1d8ef-112">Microsoft [Edge \(ベータ\)][RemoteTools] アプリが Microsoft Store で入手できるようにな [りました][MicrosoftStore]。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-112">The [Remote Tools for Microsoft Edge \(Beta\)][RemoteTools] app is now available in the [Microsoft Store][MicrosoftStore].</span></span>  <span data-ttu-id="1d8ef-113">このアプリを使用すると [、開][WindowsUwpDebugTestPerfDevicePortal]発機関で実行されている Microsoft Edge のインスタンスからリモート Windows 10 デバイスに接続できます。ターゲットのリストを確認し、ターゲットのリストを確認します (Windows 10 デバイスで開いた Microsoft Edge と [PWA の][PprgressiveWebAppsChromiumIndex] すべてのタブ)。開発用コンピューター上の DevTools を使用して、開発用コンピューターの DevTools をリモート Windows 10 デバイス上で実行しているターゲットと同じ方法で使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-113">Using this app, which extends the [Windows Device Portal][WindowsUwpDebugTestPerfDevicePortal], you are able to connect from the instance of Microsoft Edge running on your development machine to a remote Windows 10 device, see a list of targets \(all tabs in Microsoft Edge and [PWAs][PprgressiveWebAppsChromiumIndex] open on the Windows 10 device\), and use the DevTools on your development machine against a target running on the remote Windows 10 device.</span></span>  

:::image type="complex" source="../../media/2020/03/remote-tools.msft.png" alt-text="Microsoft Store で入手可能な Microsoft Edge (ベータ) アプリ" lightbox="../../media/2020/03/remote-tools.msft.png":::
   <span data-ttu-id="1d8ef-115">図 1: [Microsoft Store][MicrosoftStore]で入手可能[な Microsoft Edge (ベ][RemoteTools]ータ) アプリ</span><span class="sxs-lookup"><span data-stu-id="1d8ef-115">Figure 1:  The [Remote Tools for Microsoft Edge (Beta)][RemoteTools] app available in the [Microsoft Store][MicrosoftStore]</span></span>  
:::image-end:::  

<span data-ttu-id="1d8ef-116">[リモート デバッグ用に Windows 10][DevtoolsRemoteDebuggingWindows]デバイスと開発機関の開発機関のマシンをセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-116">[Read our guide for setting up your Windows 10 device and your development machine for remote debugging][DevtoolsRemoteDebuggingWindows].</span></span>  <span data-ttu-id="1d8ef-117">[フィードバックの送信] アイコンをタイルまたはクリックして、リ[tweeting][PostTweetEdgeDevTools]モート デバッグ エクスペリエンスについて[お知らせください](#getting-in-touch-with-microsoft-edge-devtools-team)。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-117">Let us know about your remote debugging experience by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

### <span data-ttu-id="1d8ef-118">[設定] にアクセスする新しい方法</span><span class="sxs-lookup"><span data-stu-id="1d8ef-118">New ways to access Settings</span></span>  

<span data-ttu-id="1d8ef-119">DevTools の設定には、DevTools の外観、操作などをカスタマイズできるものがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-119">There are tons of settings for the DevTools that you are able to customize to make the DevTools look, feel, and work the way you need.</span></span> <span data-ttu-id="1d8ef-120">Microsoft Edge 83 では、DevTools [の][DevtoolsCustomizeIndexSettings] 設定へのアクセスがさらに簡単になりました。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-120">In Microsoft Edge 83, accessing [Settings][DevtoolsCustomizeIndexSettings] in the DevTools is now much easier.</span></span> <span data-ttu-id="1d8ef-121">本体の通知とメイン メニューの横にあるギア アイコンを使用して [設定] を開きます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-121">Open Settings with the gear icon next to Console alerts and the main menu.</span></span>  

:::image type="complex" source="../../media/2020/03/settings.msft.png" alt-text="[開発ツール] の [設定] を開く" lightbox="../../media/2020/03/settings.msft.png":::
   <span data-ttu-id="1d8ef-123">図 2: ギア アイコンが開発ツール **の** [設定] を開く</span><span class="sxs-lookup"><span data-stu-id="1d8ef-123">Figure 2:  The gear icon opens **Settings** in the DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="1d8ef-124">[その他のツール] のメ [イン メニュー][DevtoolsCustomizeIndexSettings] から **設定** を **開く方法もあります**。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-124">You are also able to open [Settings][DevtoolsCustomizeIndexSettings] from the **Main Menu** under **More tools**.</span></span>

:::image type="complex" source="../../media/2020/03/settings2.msft.png" alt-text="メイン メニューの [>] タブの [>]" lightbox="../../media/2020/03/settings2.msft.png":::
   <span data-ttu-id="1d8ef-126">図 3: メ**イン メニュー**  >  **の [その他]**  >  **の [設定]**</span><span class="sxs-lookup"><span data-stu-id="1d8ef-126">Figure 3:  **Main Menu** > **More tools** > **Settings**</span></span>  
:::image-end:::  

<span data-ttu-id="1d8ef-127">Chromium の問題は、Chromium [の問題#1050855][CR1050855]</span><span class="sxs-lookup"><span data-stu-id="1d8ef-127">Chromium issue [#1050855][CR1050855]</span></span>

### <span data-ttu-id="1d8ef-128">新しい情報バーと改善された情報バー</span><span class="sxs-lookup"><span data-stu-id="1d8ef-128">New and improved infobars</span></span>

<span data-ttu-id="1d8ef-129">DevTools の情報通知バー \(infobars\) の外観が改善されました。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-129">Informational notification bars \(infobars\) in DevTools now have an improved look and more functionality.</span></span> <span data-ttu-id="1d8ef-130">Microsoft Edge 83 では、情報バーを読みやすく、ボタンを提供して、関連するアクションをすでに取り入れることができます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-130">In Microsoft Edge 83, infobars are easier to read and provide buttons so you are able to take the relevant action right away.</span></span>  

:::image type="complex" source="../../media/2020/03/infobar.msft.png" alt-text="Microsoft Edge 83 でマイニフェイド ファイルを印刷する情報バー" lightbox="../../media/2020/03/infobar.msft.png":::
   <span data-ttu-id="1d8ef-132">図 4:Microsoft Edge バージョン 83 でマイニファイド ファイルを印刷する場合の情報バー</span><span class="sxs-lookup"><span data-stu-id="1d8ef-132">Figure 4:  Infobar for pretty-printing a minified file in Microsoft Edge Version 83</span></span>  
:::image-end:::  

<span data-ttu-id="1d8ef-133">Chromium の [問題#1056348][CR1056348]</span><span class="sxs-lookup"><span data-stu-id="1d8ef-133">Chromium issue [#1056348][CR1056348]</span></span>

### <span data-ttu-id="1d8ef-134">キーボードで色の作成ウィンドウを移動する</span><span class="sxs-lookup"><span data-stu-id="1d8ef-134">Navigate the Color Picker with your keyboard</span></span>  

<span data-ttu-id="1d8ef-135">色 [の選択は要素][DevtoolsCssReferenceColorPicker] パネルの GUI で [、変更と][DevtoolsCssIndex] 宣 `color` `background-color` 宣表示を行います。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-135">The [Color Picker][DevtoolsCssReferenceColorPicker] is a GUI in the [Elements panel][DevtoolsCssIndex] for changing `color` and `background-color` declarations.</span></span>  <span data-ttu-id="1d8ef-136">以前のバージョンの Microsoft Edge では、キーボードを使用して、**Shades**カラー ピッカーのシェーディ[ング セクションを移動できな][DevtoolsCssReferenceColorPicker]かった。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-136">In previous versions of Microsoft Edge, you were not able to navigate the **Shades** section of the [Color Picker][DevtoolsCssReferenceColorPicker] with the keyboard.</span></span>  

:::image type="complex" source="../../media/2020/03/color-picker.msft.png" alt-text="キーボードを使用して、[色の作成] セクションの [シェーダー] セクションで選択者を移動できるようになりました" lightbox="../../media/2020/03/color-picker.msft.png":::
   <span data-ttu-id="1d8ef-138">図 5: キーボードを使用して、カラー ピッカーの [塗**Shades**りつぶし] セクションで選択者[を移動できるようになりました][DevtoolsCssReferenceColorPicker]</span><span class="sxs-lookup"><span data-stu-id="1d8ef-138">Figure 5:  You are now able to use your keyboard to move the selector in the **Shades** section of the [Color Picker][DevtoolsCssReferenceColorPicker]</span></span>  
:::image-end:::  

<span data-ttu-id="1d8ef-139">Microsoft Edge 83 では、キーボードを使用して、色の作成の **[** 塗りつぶし] セクションで選択者を移動できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-139">In Microsoft Edge 83, you are now able to use the keyboard to move the selector in the **Shades** section of the Color Picker.</span></span>  

<span data-ttu-id="1d8ef-140">Chromium の問題 [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="1d8ef-140">Chromium issue [#963183][CR963183]</span></span>  

### <span data-ttu-id="1d8ef-141">ページ更新後に [プロパティ] タブが表示されるようになりました</span><span class="sxs-lookup"><span data-stu-id="1d8ef-141">Properties tab now populates after a page refresh</span></span>  

<span data-ttu-id="1d8ef-142">Microsoft Edge 81 以前では、[ **要素** ] パネルの [プロパティ] [タブは][DevtoolsCssIndex] ページ更新によって分かれていました。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-142">In Microsoft Edge 81 and earlier, the **Properties tab** in the [Elements panel][DevtoolsCssIndex] was broken by page refreshes.</span></span>  <span data-ttu-id="1d8ef-143">ページを更新すると、[ **プロパティ] タブ** には現在選択されている要素のプロパティが設定されませんでした。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-143">When you refreshed the page, the **Properties tab** did not populate the properties of the currently-selected element.</span></span>  

:::image type="complex" source="../../media/2020/03/properties-in-81.msft.png" alt-text="Microsoft Edge 81 以前では、ページ更新後 、[プロパティ] タブが空白でした" lightbox="../../media/2020/03/properties-in-81.msft.png":::
   <span data-ttu-id="1d8ef-145">図 6:Microsoft Edge 81 以前では、ページ更新後 、[ **プロパティ** ] タブが空白でした</span><span class="sxs-lookup"><span data-stu-id="1d8ef-145">Figure 6:  In Microsoft Edge 81 and earlier, the **Properties tab** was blank after a page refresh</span></span>  
:::image-end:::  

<span data-ttu-id="1d8ef-146">Microsoft Edge 83 では、[プロパティ] タブでページを更新した後に現在選択されている要素のプロパティ **を表示できるようになりました**。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-146">In Microsoft Edge 83, you are now able to see the properties of the currently-selected element after a page refresh in the **Properties tab**.</span></span>  

:::image type="complex" source="../../media/2020/03/properties-in-82.msft.png" alt-text="Microsoft Edge 83 の [プロパティ] タブには、ページの更新後に現在選択されている要素のプロパティが表示される" lightbox="../../media/2020/03/properties-in-82.msft.png":::
   <span data-ttu-id="1d8ef-148">図 7:Microsoft Edge 83 の [ **プロパティ** ] タブには、ページの更新後に現在選択されている要素のプロパティが表示される</span><span class="sxs-lookup"><span data-stu-id="1d8ef-148">Figure 7:  In Microsoft Edge 83, the **Properties tab** displays the properties of the currently-selected element after a page refresh</span></span>  
:::image-end:::  

<span data-ttu-id="1d8ef-149">Chromium の [問題#1050999][CR1050999]</span><span class="sxs-lookup"><span data-stu-id="1d8ef-149">Chromium issue [#1050999][CR1050999]</span></span>  

### <span data-ttu-id="1d8ef-150">方向キーを使用して [変更] ツールのスクロール</span><span class="sxs-lookup"><span data-stu-id="1d8ef-150">Use the arrow keys to scroll in the Changes tool</span></span>  

<span data-ttu-id="1d8ef-151">変更 **ツールは** 、DevTools の CSS または JavaScript に加えたすべての変更を追跡します。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-151">The **Changes tool** tracks any changes you have made to CSS or JavaScript in the DevTools.</span></span>  <span data-ttu-id="1d8ef-152">変更ツールを使用すると **、すべての** 変更をすばやく確認し、それらを編集者/IDE に戻すようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-152">You are able to use the **Changes tool** to quickly see all your changes and take those back to your editor/IDE.</span></span>  

<span data-ttu-id="1d8ef-153">開いて**コマンド メニューを**開き入力して `Ctrl` + `Shift` + `P` 変更ツールを開きます[Command Menu][DevToolsCommandMenuIndex] `changes` 。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-153">Open the **Changes tool** by pressing `Ctrl`+`Shift`+`P` in the DevTools to open the [Command Menu][DevToolsCommandMenuIndex] and typing `changes`.</span></span>  <span data-ttu-id="1d8ef-154">[変更の表示 **]** コマンドを選択して**Changes tool**実行し、DevTools 描画ツールで変更ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-154">Select and run the **Show Changes** command to open the **Changes tool** in the DevTools drawer.</span></span>  

<span data-ttu-id="1d8ef-155">マイニフェイド ファイルに変更を加えた場合 **、変更** ツールを使用すると、すべてのミニバーのコードを表示できます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-155">When you have made a change to a minified file, the **Changes tool** enables you to scroll horizontally to see all of your minified code.</span></span>  <span data-ttu-id="1d8ef-156">Microsoft Edge 83 以降では、キーボードの方向キーを使用して横方向にスクロールできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-156">Starting in Microsoft Edge 83, you may now scroll horizontally using the arrow keys on your keyboard.</span></span>  

:::image type="complex" source="../../media/2020/03/changes.msft.png" alt-text="Microsoft Edge 83 では、方向キーで水平方向にスクロールすると、[変更] ツールでマイニフェイド コードが表示される場合があります。" lightbox="../../media/2020/03/changes.msft.png":::
   <span data-ttu-id="1d8ef-158">図 8: Microsoft Edge 83 では、矢印キーを使って横方向にスクロールし、[変更] ツールでマイニュアル コードに加えた変更を **確認できます。**</span><span class="sxs-lookup"><span data-stu-id="1d8ef-158">Figure 8:  In Microsoft Edge 83, you may scroll horizontally with the arrow keys to see the changes you made to your minified code in the **Changes tool**</span></span>  
:::image-end:::  

<span data-ttu-id="1d8ef-159">スクリーン リーダーまたはキーボードを使用して DevTools 内を移動する場合は、Microsoft における [タイル][PostTweetEdgeDevTools] をタイーションするか、[フィードバックの送信] アイコンをクリックして、フィードバック [を送信してください](#getting-in-touch-with-microsoft-edge-devtools-team) 。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-159">If you use screen readers or the keyboard to navigate around the DevTools, send us your feedback by [tweeting][PostTweetEdgeDevTools] at us or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="1d8ef-160">Chromium の問題 [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="1d8ef-160">Chromium issue [#963183][CR963183]</span></span>  

## <span data-ttu-id="1d8ef-161">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="1d8ef-161">Announcements from the Chromium project</span></span>  

<span data-ttu-id="1d8ef-162">次のセクションでは、Microsoft Edge 83 で使用可能な追加機能について、オープン ソース Chromium プロジェクトに投稿された追加機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-162">The following sections announce additional features available in Microsoft Edge 83 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="1d8ef-163">視図を使ってみる</span><span class="sxs-lookup"><span data-stu-id="1d8ef-163">Emulate vision deficiencies</span></span>  

<span data-ttu-id="1d8ef-164">[ [レンダリング][DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab] ] タブを開き、新しい **エ** ミュレートの視視性機能を使用して、サイトのさまざまな視視性を高めた人にどのように役立つかをより深く理由を理由を深めます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-164">Open the [Rendering tab][DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab] and use the new **Emulate vision deficiencies** feature to get a better idea of how people with different types of vision deficiencies experience your site.</span></span>  

:::image type="complex" source="../../media/2020/03/vision.msft.png" alt-text="ブレージの視図をエミュレートする" lightbox="../../media/2020/03/vision.msft.png":::
   <span data-ttu-id="1d8ef-166">図 9: ブレージング ブレージングのブレージ</span><span class="sxs-lookup"><span data-stu-id="1d8ef-166">Figure 9:  Emulating blurred vision</span></span>  
:::image-end:::  

<span data-ttu-id="1d8ef-167">DevTools では視認知度が向上し、次の色の視認度が向 [上します][ColorBlindnessTypes]。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-167">DevTools is able to emulate blurred vision and the following [types of color vision deficiencies][ColorBlindnessTypes].</span></span>  

| <span data-ttu-id="1d8ef-168">色の視差</span><span class="sxs-lookup"><span data-stu-id="1d8ef-168">Color Vision Deficiency</span></span> | <span data-ttu-id="1d8ef-169">詳細</span><span class="sxs-lookup"><span data-stu-id="1d8ef-169">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="1d8ef-170">Protanopia</span><span class="sxs-lookup"><span data-stu-id="1d8ef-170">Protanopia</span></span> | <span data-ttu-id="1d8ef-171">明るい光の割り付けを行う機能。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-171">The inability to perceive any red light.</span></span> |  
| <span data-ttu-id="1d8ef-172">Deuteranopia</span><span class="sxs-lookup"><span data-stu-id="1d8ef-172">Deuteranopia</span></span> | <span data-ttu-id="1d8ef-173">緑のライトに対する割り付けをおくといいえます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-173">The inability to perceive any green light.</span></span> |  
| <span data-ttu-id="1d8ef-174">トリタノピア</span><span class="sxs-lookup"><span data-stu-id="1d8ef-174">Tritanopia</span></span> | <span data-ttu-id="1d8ef-175">青色のライトを割りに合う機能。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-175">The inability to perceive any blue light.</span></span> |  
| <span data-ttu-id="1d8ef-176">アクロマトタ</span><span class="sxs-lookup"><span data-stu-id="1d8ef-176">Achromatopsia</span></span> | <span data-ttu-id="1d8ef-177">緑の \(とはみなかう) のシェーディングを除き、任意の色の色のパーセンティーをパーセンティブする機能。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-177">The inability to perceive any color, except for shades of grey \(extremely rare\).</span></span> |  

<span data-ttu-id="1d8ef-178">これらの色の視視用版が少なくなり、実に一般的です。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-178">Less extreme versions of these color vision deficiencies exist, and in fact they are more common.</span></span>  
<span data-ttu-id="1d8ef-179">たとえば、確率とは、明るさ (プロテールに対して認めないと完全にできる、プロテールに対しては小さいと見なされます)。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-179">For example, protanomaly is a reduced sensitivity to red light (as opposed to protanopia, which is the complete inability to perceive red light).</span></span> <span data-ttu-id="1d8ef-180">しかし、これらの -omaly 視認のデフォルトは明確に定義されていません。視認性を高めるすべてのユーザーが異なり、異なるように見える場合があります (色の割合をパーセント/縮小できる)。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-180">However, these -omaly vision deficiencies are not as clearly defined: every person with such a vision deficiency is different and might see things differently (being able to perceive more/less of the relevant colors).</span></span>  

<span data-ttu-id="1d8ef-181">開発ツールでの非常に拡張のシミュレーションを設計することで、Web アプリは、プロテノラル、デュラノイマ、トラマリのユーザーもアクセスできる保証されます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-181">By designing for the more extreme simulations in DevTools, your web apps are guaranteed to be accessible to people with protanomaly, deuteranomaly, tritanomaly, and achromatomaly as well.</span></span>  

<span data-ttu-id="1d8ef-182">フィードバックの送信アイコンをタ [イ][PostTweetEdgeDevTools] ロー化またはクリックして [、フィードバックを送信](#getting-in-touch-with-microsoft-edge-devtools-team) します。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-182">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="1d8ef-183">Chromium の問題はキ [#1003700][CR1003700]</span><span class="sxs-lookup"><span data-stu-id="1d8ef-183">Chromium issue [#1003700][CR1003700]</span></span>  

### <span data-ttu-id="1d8ef-184">エミュレート ロケール</span><span class="sxs-lookup"><span data-stu-id="1d8ef-184">Emulate locales</span></span>  

<span data-ttu-id="1d8ef-185">スニーズの場所に場所を設定することで **、ロケールをエミュレート**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-185">Emulate locales by setting a location in **Sensors** > **Location**.</span></span> <span data-ttu-id="1d8ef-186">[コマンド メニュー **を開**][DevToolsCommandMenuIndex] き `Sensors` **、「Sensors」タブにアクセス** する。 これらのアクションを実行すると、現在の既定のロケールが変更されるため、次のコードに影響します。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-186">[Open the **Command Menu**][DevToolsCommandMenuIndex] and type `Sensors` to access the **Sensors** tab.  After performing these actions, DevTools modifies the current default locale, affecting the following code.</span></span>  

*   `Intl.*` <span data-ttu-id="1d8ef-187">たとえば、API の例を示します。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-187">APIs, for example:</span></span> `new Intl.NumberFormat().resolvedOptions().locale`  
*   <span data-ttu-id="1d8ef-188">次に例を示します `String.prototype.localeCompare` `*.prototype.toLocaleString` 。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-188">Other locale-aware JavaScript APIs such as `String.prototype.localeCompare` and `*.prototype.toLocaleString`, for example:</span></span> `123_456..toLocaleString()`  
*   <span data-ttu-id="1d8ef-189">DOM API などの DOM `navigator.language` API</span><span class="sxs-lookup"><span data-stu-id="1d8ef-189">DOM APIs such as `navigator.language` and</span></span> `navigator.languages`  
*   <span data-ttu-id="1d8ef-190">[`Accept-Language`][MDNAcceptLanguage]HTTP 要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="1d8ef-190">The [`Accept-Language`][MDNAcceptLanguage] HTTP request header</span></span>  

> [!NOTE]
> <span data-ttu-id="1d8ef-191">更新内容とすぐには表示されませんが、次のナビゲーションまたはページ更新後 `navigator.language` `navigator.languages` にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-191">Updates to `navigator.language` and `navigator.languages` are not visible immediately, but only after the next navigation or page refresh.</span></span>  <span data-ttu-id="1d8ef-192">HTTP ヘッダーの変更は、以降の要求に対してのみ `Accept-Language` 表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-192">Changes to the `Accept-Language` HTTP header are only reflected for subsequent requests.</span></span>  

:::image type="complex" source="../../media/2020/03/locale.msft.png" alt-text="ロケールをエミュレートする" lightbox="../../media/2020/03/locale.msft.png":::
   <span data-ttu-id="1d8ef-194">図 10: ロケールをエミュレートする</span><span class="sxs-lookup"><span data-stu-id="1d8ef-194">Figure 10:  Emulating a locale</span></span>  
:::image-end:::  

<span data-ttu-id="1d8ef-195">デモを試すには、 [ロケールに依存するコードの例を参照してください][MathiasByensLocaleDemo]。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-195">To try a demo, see [Locale-dependent code example][MathiasByensLocaleDemo].</span></span>

<span data-ttu-id="1d8ef-196">Chromium の [問題#1051822][CR1051822]</span><span class="sxs-lookup"><span data-stu-id="1d8ef-196">Chromium issue [#1051822][CR1051822]</span></span>

### <span data-ttu-id="1d8ef-197">クロスプリッド ドライバー の埋め込みポリシー (COEP) デバッグ</span><span class="sxs-lookup"><span data-stu-id="1d8ef-197">Cross-Origin Embedder Policy (COEP) debugging</span></span>  

<span data-ttu-id="1d8ef-198">これで、[ネットワーク パネル] には、 [クロ][COEP] スクロステン 埋め込みポリシーデバッグ情報が提供されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-198">The Network panel now provides [Cross-Origin Embedder Policy][COEP] debugging information.</span></span>  

<span data-ttu-id="1d8ef-199">[ **状態** ] 列には、要求がブロックされた理由と、詳細にデバッグする必要があるその要求のヘッダーを表示するリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-199">The **Status** column now provides a quick explanation of why a request was blocked as well as a link to view the headers of that request for further debugging:</span></span>  

:::image type="complex" source="../../media/2020/03/status.msft.png" alt-text="**Status** 列のブロック要求" lightbox="../../media/2020/03/status.msft.png":::
   <span data-ttu-id="1d8ef-201">図 11:[状態] 列の [ブロックされたリクエスト]</span><span class="sxs-lookup"><span data-stu-id="1d8ef-201">Figure 11:  Blocked requests in the Status column</span></span>  
:::image-end:::  

<span data-ttu-id="1d8ef-202">[**ヘッダー] タブの**[応答ヘッダー]**Headers**セクションには、問題を解決する方法の詳細なガイダンスがあります。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-202">The **Response Headers** section of the **Headers** tab provides more guidance on how to resolve the issues:</span></span>  

:::image type="complex" source="../../media/2020/03/guidance.msft.png" alt-text="[応答ヘッダー] セクションのその他のガイダンス" lightbox="../../media/2020/03/guidance.msft.png":::
   <span data-ttu-id="1d8ef-204">図 12: [応答ヘッダー] セクションのその他のガイダンス</span><span class="sxs-lookup"><span data-stu-id="1d8ef-204">Figure 12:  More guidance in the Response Headers section</span></span>  
:::image-end:::  

<span data-ttu-id="1d8ef-205">フィードバックの送信アイコンをタ [イ][PostTweetEdgeDevTools] ロー化またはクリックして [、フィードバックを送信](#getting-in-touch-with-microsoft-edge-devtools-team) します。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-205">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="1d8ef-206">Chromium の [問題#1051466][CR1051466]</span><span class="sxs-lookup"><span data-stu-id="1d8ef-206">Chromium issue [#1051466][CR1051466]</span></span>  

### <span data-ttu-id="1d8ef-207">区切り点、条件付き改行ポイント、およびロゴの新しいアイコン</span><span class="sxs-lookup"><span data-stu-id="1d8ef-207">New icons for breakpoints, conditional breakpoints, and logpoints</span></span>  

<span data-ttu-id="1d8ef-208">[ソース] パネルには、区切りポイント、条件付きのブレークポイント、およびロゴの新しいアイコンがあります。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-208">The Sources panel has new icons for breakpoints, conditional breakpoints, and logpoints:</span></span>  

*   <span data-ttu-id="1d8ef-209">ブレークポイント \(</span><span class="sxs-lookup"><span data-stu-id="1d8ef-209">Breakpoints \(</span></span>![改ページ](../../media/2020/03/breakpoint.msft.png)<span data-ttu-id="1d8ef-211">\) は、リッドの回数で表されます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-211">\) are represented by red circles.</span></span>  
*   <span data-ttu-id="1d8ef-212">条件付き改行ポイント \(</span><span class="sxs-lookup"><span data-stu-id="1d8ef-212">Conditional Breakpoints \(</span></span>![条件付き改行ポイント](../../media/2020/03/conditional.msft.png)<span data-ttu-id="1d8ef-214">\) は、実数の下の中で表されます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-214">\) are represented by half-red half-white circles.</span></span>  
*   <span data-ttu-id="1d8ef-215">Logpoints \(</span><span class="sxs-lookup"><span data-stu-id="1d8ef-215">Logpoints \(</span></span>![Logpoint](../../media/2020/03/logpoint.msft.png)<span data-ttu-id="1d8ef-217">\) は、本体アイコン付きのリッド音の付きのシングルで表されます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-217">\) are represented by red circles with Console icons.</span></span>  

<span data-ttu-id="1d8ef-218">新しいアイコンのムービーは、UI デバッグ ツール (通常は色分けの破線) に一定性があり、3 つの機能を簡単に区別できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-218">The motivation for the new icons was to make the UI more consistent with other GUI debugging tools \(which usually color breakpoints red\) and to make it easier to distinguish between the 3 features at a glance.</span></span>  

<span data-ttu-id="1d8ef-219">Chromium[の問題][CR1041830]#1041830</span><span class="sxs-lookup"><span data-stu-id="1d8ef-219">Chromium issue [#1041830][CR1041830]</span></span>  

### <span data-ttu-id="1d8ef-220">特定の Cookie パスを設定するネットワーク要求を表示する</span><span class="sxs-lookup"><span data-stu-id="1d8ef-220">View network requests that set a specific cookie path</span></span>  

<span data-ttu-id="1d8ef-221">ネットワーク パネ `cookie-path` ルの新しいフィルター **キーワードを** 使用して、特定のクッキー パスを設定する [ネットワーク要求に注中します][MDNCookiePath]。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-221">Use the new `cookie-path` filter keyword in the **Network** panel to focus on the network requests that set a specific [cookie path][MDNCookiePath].</span></span>  

<span data-ttu-id="1d8ef-222">プロパティ別 [のフィルター要求をチェックして、その][DevtoolsNetworkReferenceFilterRequestsProperties] 他のキーワードを見つけます `cookie-path` 。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-222">Check out [Filter requests by properties][DevtoolsNetworkReferenceFilterRequestsProperties] to discover more keywords like `cookie-path`.</span></span>

### <span data-ttu-id="1d8ef-223">コマンド メニューからドックから左へドッキャッキ</span><span class="sxs-lookup"><span data-stu-id="1d8ef-223">Dock to left from the Command Menu</span></span>  

<span data-ttu-id="1d8ef-224">コマンド メニュー [を開き][DevToolsCommandMenuIndex] 、コマンド `Dock to left` を実行して、ビューポートの左側に DevTools を移動します。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-224">Open the [Command Menu][DevToolsCommandMenuIndex] and run the `Dock to left` command to move DevTools to the left of your viewport.</span></span>  

:::image type="complex" source="../../media/2020/03/dock-to-left.msft.png" alt-text="ビューポートの左側にドッキャッキ化された DevTools" lightbox="../../media/2020/03/dock-to-left.msft.png":::
   <span data-ttu-id="1d8ef-226">図 13: ビューポートの左側にドッキャッキ化された DevTools</span><span class="sxs-lookup"><span data-stu-id="1d8ef-226">Figure 13:  DevTools docked to the left of the viewport</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="1d8ef-227">**Dock から左**に表示される機能は、Microsoft Edge 75 以降利用可能になりましたが、以前はメイン メニューから[**のみアクセスできました**][DevtoolsCustomizePlacementsChangeMainMenu]。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-227">The **Dock to left** feature has been available since Microsoft Edge 75, but it was previously only accessible from the [**Main Menu**][DevtoolsCustomizePlacementsChangeMainMenu].</span></span>  <span data-ttu-id="1d8ef-228">Microsoft Edge 83 の新機能は、現在、[コマンド] メニューからこの機能にアクセスできる機能です。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-228">The new feature in Microsoft Edge 83 is that you may now access this feature from the Command Menu.</span></span>  

<span data-ttu-id="1d8ef-229">フィードバックの送信アイコンをタ [イ][PostTweetEdgeDevTools] ロー化またはクリックして [、フィードバックを送信](#getting-in-touch-with-microsoft-edge-devtools-team) します。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-229">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="1d8ef-230">Chromium の [問題#1011679][CR1011679]</span><span class="sxs-lookup"><span data-stu-id="1d8ef-230">Chromium issue [#1011679][CR1011679]</span></span>  

### <span data-ttu-id="1d8ef-231">[監査] パネルが灯した時にハッシュ パネルになりました</span><span class="sxs-lookup"><span data-stu-id="1d8ef-231">The Audits panel is now the Lighthouse panel</span></span>  

<span data-ttu-id="1d8ef-232">DevTools チームは、Web 開発者からフィードバックを受けました。このチームが、DevTools から Lighthouse を実行できなかったときに、"Lighthouse" パネルが見つからなかったときに、[Lighthouse] パネルが見つからなかったため、[**監**査] パネルが**強調表示**されています。 [Lighthouse][GithubGoogleChromeLighthouse]</span><span class="sxs-lookup"><span data-stu-id="1d8ef-232">The DevTools team frequently got feedback from web developers that while it was possible to run [Lighthouse][GithubGoogleChromeLighthouse] from DevTools, when they tried it out they were not able to find the "Lighthouse" panel, so the **Audits** panel is now the **Lighthouse** panel.</span></span>  

:::image type="complex" source="../../media/2020/03/lighthouse.msft.png" alt-text="灯" lightbox="../../media/2020/03/lighthouse.msft.png":::
   <span data-ttu-id="1d8ef-234">図 14: 灯カウント パネル</span><span class="sxs-lookup"><span data-stu-id="1d8ef-234">Figure 14:  The Lighthouse panel</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="1d8ef-235">**灯カウントには**、サード パーティの Web サイトでホストされているコンテンツへのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-235">The **Lighthouse** panel provides links to content hosted on third-party websites.</span></span>  <span data-ttu-id="1d8ef-236">Microsoft は、お客様のごなることは一切管理されており、これらのサイトのコンテンツや収集される可能性のあるすべてのデータを制御できません。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-236">Microsoft is not responsible for and has no control over the content of these sites and any data they may collect.</span></span>  

### <span data-ttu-id="1d8ef-237">フォルダー内のすべてのローカル オーバーライドを削除する</span><span class="sxs-lookup"><span data-stu-id="1d8ef-237">Delete all Local Overrides in a folder</span></span>  

<span data-ttu-id="1d8ef-238">ローカル オー **バーライドを設定した後** 、フォルダーを右クリックして[すべて削除] **オプション** を選択して、そのフォルダー内のすべてのローカル オーバーライドを削除できます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-238">After setting up **Local Overrides** you may right-click a folder and select the new **Delete all overrides** option to delete all Local Overrides in that folder.</span></span>  

:::image type="complex" source="../../media/2020/03/overrides.msft.png" alt-text="すべてのオーバーライドを削除する" lightbox="../../media/2020/03/overrides.msft.png":::
   <span data-ttu-id="1d8ef-240">図 15: すべてのオーバーライドを削除する</span><span class="sxs-lookup"><span data-stu-id="1d8ef-240">Figure 15:  Delete all overrides</span></span>  
:::image-end:::  

<span data-ttu-id="1d8ef-241">フィードバックの送信アイコンをタ [イ][PostTweetEdgeDevTools] ロー化またはクリックして [、フィードバックを送信](#getting-in-touch-with-microsoft-edge-devtools-team) します。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-241">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="1d8ef-242">Chromium の [問題#1016501][CR1016501]</span><span class="sxs-lookup"><span data-stu-id="1d8ef-242">Chromium issue [#1016501][CR1016501]</span></span>  

### <span data-ttu-id="1d8ef-243">更新された長いタスク UI</span><span class="sxs-lookup"><span data-stu-id="1d8ef-243">Updated Long tasks UI</span></span>  

<span data-ttu-id="1d8ef-244">長 **いタスクは** 、メイン スレッドを一定時間に移動する JavaScript コードで、Web ページが固定されるためにフリーズします。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-244">A **Long Task** is JavaScript code that monopolizes the main thread for a long time, causing a web page to freeze.</span></span>  

<span data-ttu-id="1d8ef-245">長いタスクをパフ[visualize Long Tasks in the Performance panel][DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity]ォーマンス パネルで視覚化できるのは、パフォーマンス パネルの長いタスク視覚エフェクト UI が更新されました。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-245">You have been able to [visualize Long Tasks in the Performance panel][DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity] for a while now, but in Microsoft Edge 83 the Long Task visualization UI in the Performance panel has been updated.</span></span>  <span data-ttu-id="1d8ef-246">タスクの長いタスク部分は、強い背景で色付けされます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-246">The Long Task portion of a task is now colored with a striped red background.</span></span>  

:::image type="complex" source="../../media/2020/03/long-task.msft.png" alt-text="新しい長いタスク UI" lightbox="../../media/2020/03/long-task.msft.png":::
   <span data-ttu-id="1d8ef-248">図 16: 新しい長いタスク UI</span><span class="sxs-lookup"><span data-stu-id="1d8ef-248">Figure 16:  The new Long Task UI</span></span>  
:::image-end:::  

<span data-ttu-id="1d8ef-249">フィードバックの送信アイコンをタ [イ][PostTweetEdgeDevTools] ロー化またはクリックして [、フィードバックを送信](#getting-in-touch-with-microsoft-edge-devtools-team) します。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-249">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="1d8ef-250">Chromium[の問題][CR1054447]#1054447</span><span class="sxs-lookup"><span data-stu-id="1d8ef-250">Chromium issue [#1054447][CR1054447]</span></span>  

### <span data-ttu-id="1d8ef-251">マスク可能なアイコンのサポート (マニフェスト) ウィンドウのサポート</span><span class="sxs-lookup"><span data-stu-id="1d8ef-251">Maskable icon support in the Manifest pane</span></span>  

<span data-ttu-id="1d8ef-252">Android Oreo に導入されたアダプティブ アイコンが導入されました。このアイコンは、さまざまなデバイス モデル間でアプリ のアイコンを表示します。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-252">Android Oreo introduced adaptive icons, which display app icons in a variety of shapes across different device models.</span></span>  <span data-ttu-id="1d8ef-253">**マスク可能なアイコンは** 、アダプティブ アイコンをサポートする新しいアイコンの書式で、マスク可能なアイコン標準をサポートするデバイスで [PWA][PprgressiveWebAppsChromiumIndex] アイコンが正しく表示されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-253">**Maskable icons** are a new icon format that support adaptive icons, which enable you to ensure that your [PWA][PprgressiveWebAppsChromiumIndex] icon looks good on devices that support the maskable icons standard.</span></span>  

<span data-ttu-id="1d8ef-254">マニフェ**スト ウィンドウ**のマスク可能なアイコンのみを表示するチェックボックスをオンにして**Manifest**、マスク可能なアイコンが Android またはデバイスで良い状態であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-254">Enable the new **Show only the minimum safe area for maskable icons** checkbox in the **Manifest** pane to check that your maskable icon looks good on Android Oreo devices.</span></span>  

<!-- Check out [Are my current icons ready?] to learn more.  -->  

:::image type="complex" source="../../media/2020/03/maskable-icons.msft.png" alt-text="[マスケートアイコンの最小値のみを表示する] チェック ボックス" lightbox="../../media/2020/03/maskable-icons.msft.png":::
   <span data-ttu-id="1d8ef-256">図 17: マスク可能なアイコンの最小の安全な領域 **のみを表示** する</span><span class="sxs-lookup"><span data-stu-id="1d8ef-256">Figure 17:  The **Show only the minimum safe area for maskable icons** checkbox</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="1d8ef-257">この機能は、Microsoft Edge 81 で起動しました。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-257">This feature launched in Microsoft Edge 81.</span></span>  <span data-ttu-id="1d8ef-258">Microsoft Edge 83 で説明した更新プログラムについては、Microsoft [Edge の新機能 (Microsoft Edge 81) には取り上がれませんでした][WhatsNew81]。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-258">The updates covered here in Microsoft Edge 83 were not covered in [What's New In DevTools (Microsoft Edge 81)][WhatsNew81].</span></span>  

## <span data-ttu-id="1d8ef-259">Microsoft Edge のプレビュー チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="1d8ef-259">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="1d8ef-260">Windows または macOS を使用している場合は [、Microsoft Edge のプレビュー][MicrosoftEdgePreviewChannels] チャネルを既定の開発ブラウザーとして使用することを検定してください。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-260">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="1d8ef-261">プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-261">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="1d8ef-262">Microsoft Edge DevTools チームとのつながりを手にする</span><span class="sxs-lookup"><span data-stu-id="1d8ef-262">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |チェットを投稿する"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "Twitter アカウント@EdgeDevTools Twitter アカウント"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新しい問題 - MicrosoftDocs/edge-developer - GitHub"  
[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Preview チャネル"  
[TheWebWeWant]: https://webwewant.fyi "必要な Web"  

[WhatsNew81]: ../01/devtools.md "Microsoft Edge 81 の新機能 |Microsoft ドキュメント"  

[DevToolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンド メニューでコマンドを実行する |Microsoft ドキュメント"  
[DevtoolsCssReferenceColorPicker]: /microsoft-edge/devtools-guide-chromium/css/reference#change-colors-with-the-color-picker "色の作成で色を変更する |Microsoft ドキュメント"  
[DevtoolsCssIndex]: /microsoft-edge/devtools-guide-chromium/css/index "CSS の表示と変更を開始する |Microsoft ドキュメント"  
[DevtoolsCustomizePlacementsChangeMainMenu]: /microsoft-edge/devtools-guide-chromium/customize/placement#change-placement-from-the-main-menu "配置をメイン メニューから変更する |Microsoft ドキュメント"  
[DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#view-main-thread-activity "メイン スレッド アクティビティを表示する |Microsoft ドキュメント"  
[DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "[レンダリング] タブを使用してレンダリングのパフォーマンスを分析する |Microsoft ドキュメント"  
[PprgressiveWebAppsChromiumIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 上のプレイ Web アプリ |Microsoft ドキュメント"  
[DevtoolsRemoteDebuggingWindows]: /microsoft-edge/devtools-guide-chromium/remote-debugging/windows "Windows 10 デバイスのリモート デバッグの使用を開始する |Microsoft ドキュメント"  
[DevtoolsJavascriptBreakpointsLineCode]: /microsoft-edge/devtools-guide-chromium/javascript/breakpoints#line-of-code-breakpoints "コードの改行 - Microsoft Edge DevTools で、コードをブレークポイントと一体化する方法 |Microsoft ドキュメント"
[DevtoolsNetworkReferenceFilterRequestsProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties "プロパティ別のフィルター要求 - ネットワーク分析リファレンス |Microsoft ドキュメント"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定 - Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"  

[WindowsUwpDebugTestPerfDevicePortal]: /windows/uwp/debug-test-perf/device-portal "Windows デバイス ポータルの概要"  

[RemoteTools]: https://www.microsoft.com/store/apps/9P6CMFV44ZLT "Microsoft Edge (ベータ) 用リモート ツール (ベータ)"  
[MicrosoftStore]: https://www.microsoft.com/store/apps/windows "Microsoft ストア"  

[WindowsBlogStableRelease]: https://blogs.windows.com/msedgedev/2020/03/20 "Microsoft Edge の、スタブル リリースの更新プログラム"

[MicrosoftVisualstudio]: https://visualstudio.microsoft.com "Visual Studio"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studioコード"  

[ColorBlindnessTypes]: http://www.colourblindawareness.org/colour-blindness/types-of-colour-blindness "コール ブリンジの種類"  
[MDNAcceptLanguage]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Accept-Language "承諾する言語"
[MathiasByensLocaleDemo]: https://mathiasbynens.be/demo/locale "ロケールに依存するコードの例"
[MDNCookiePath]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie#Directives

[CR963183]: https://crbug.com/963183 "発行 963183: DevTools は WCAG に準格していません"  
[CR1003700]: https://crbug.com/1003700 "問題 1003700: 色ビジエンシエンシェル シマーシュアルの DevTools サポートを追加する"  
[CR1011679]: https://crbug.com/1011679 "問題 1011679: [コマンド] メニューを使用して 'ドックを左に挿入する" を参照する"  
[CR1016501]: https://crbug.com/1016501 "問題 1016501: 機能リクエスト: すべてのローカル オーバーライドを削除するボタン"  
[CR1050999]: https://crbug.com/1050999 "問題 1050999: [プロパティ] タブ"  
[CR1051466]: https://crbug.com/1051466 "発行 1051466: DevTools での COOP/COEP デバッグをサポート"  
[CR1054447]: https://crbug.com/1054447 "問題 1054447: DevTools タイムラインでパフォーマンス測定を更新する"  
[CR1051822]: https://crbug.com/1051822 "問題 1051822: DevTools: DevTools: Add UI add UI add UI add UI add UI add UI add UI add UI add UI add UI add UI add UI add UI add UI add UI add UI add UI add uI add uI"
[CR1041830]: https://crbug.com/1041830 "問題 1041830: 区切りポイントの色を改善する"
[CR1050855]: https://crbug.com/1050855 "問題 1050855: 設定ビューが見つけにくい"
[CR1056348]: https://crbug.com/1056348 "1056348 の問題: Infobar Component 更新"

[COOP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.tu4hyy6v12wn "COOP と COEP の説明 - クロスプレーター ポリシー"  
[COEP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.uo6kivyh0ge2 "COOP と COEP の説明 - クロスクロスプレードダー ポリシー"  

[GithubGoogleChromeLighthouse]: https://github.com/GoogleChrome/lighthouse "Lighthouse GitHub リポジトリ"  

> [!NOTE]
> <span data-ttu-id="1d8ef-303">このページの一部は [、Google][GoogleSitePolicies] によって作成され共有された作業および共有に基づいて変更され、クリエイティブ コモンス属性 [4.0 国際ライセンス][CCA4IL]で説明されている用語に応じた使用されます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-303">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="1d8ef-304">ここには元のページが表示[され](https://developers.google.com/web/updates/2020/03/devtools/index)[、Kayce Basques][KayceBasques] \(テクニカル ライター, Chrome DevTools \& Lighthouse\) によって作成されます。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-304">The original page is found [here](https://developers.google.com/web/updates/2020/03/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブ コブル ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="1d8ef-306">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="1d8ef-306">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
