---
description: メディア ツールを使用して、情報を表示し、ブラウザータブごとにメディア プレーヤーをデバッグします。
title: メディア プレーヤーの情報を表示およびデバッグする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 7680faa13f65a2ea6f0a8b085316b5ed67bfdaba
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398407"
---
<!-- Copyright Jecelyn Yeen

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  

# <a name="view-and-debug-media-players-information"></a><span data-ttu-id="6e885-104">メディア プレーヤーの情報を表示およびデバッグする</span><span class="sxs-lookup"><span data-stu-id="6e885-104">View and debug media players information</span></span>  

<span data-ttu-id="6e885-105">Microsoft Edge **DevTools** のメディア ツールを使用して、情報を表示し、ブラウザータブごとにメディア プレーヤーをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="6e885-105">Use the **Media** tool in Microsoft Edge DevTools to view information and debug the media players per browser tab.</span></span>  

## <a name="open-the-media-tool"></a><span data-ttu-id="6e885-106">メディア ツールを開く</span><span class="sxs-lookup"><span data-stu-id="6e885-106">Open the Media tool</span></span>  

<span data-ttu-id="6e885-107">メディア **ツール** は、Web ページのメディア プレーヤーを検査する DevTools の主要な場所です。</span><span class="sxs-lookup"><span data-stu-id="6e885-107">The **Media** tool is the main place in DevTools for inspecting the media player of a webpage.</span></span>

1.  <span data-ttu-id="6e885-108">[DevTools を開きます][DevtoolsGuideChromiumOpen]。</span><span class="sxs-lookup"><span data-stu-id="6e885-108">[Open DevTools][DevtoolsGuideChromiumOpen].</span></span>  
1.  <span data-ttu-id="6e885-109">[メディア] パネル**を開く**場合は **、[DevTools のその他のツールメディアのカスタマイズと制御** `...`  >  **] を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="6e885-109">To open the **Media** panel, choose **Customize and control DevTools** `...` > **More tools** > **Media**.</span></span>  
    
    :::image type="complex" source="../media/media-panel-empty.msft.png" alt-text="メディア パネル" lightbox="../media/media-panel-empty.msft.png":::
       <span data-ttu-id="6e885-111">**メディア** パネル</span><span class="sxs-lookup"><span data-stu-id="6e885-111">**Media** panel</span></span>  
    :::image-end:::  
    
## <a name="view-media-players-information"></a><span data-ttu-id="6e885-112">メディア プレーヤーの情報を表示する</span><span class="sxs-lookup"><span data-stu-id="6e885-112">View media players information</span></span>  

1.  <span data-ttu-id="6e885-113">次の Web ページなどのメディア プレーヤーを含む Web ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="6e885-113">Navigate to a webpage with a media player, such as the following webpage.</span></span>  
    
    [<span data-ttu-id="6e885-114">エッジ開発者ツールによる生産性の最大化</span><span class="sxs-lookup"><span data-stu-id="6e885-114">Maximizing productivity with the Edge Developer Tools</span></span>][BingVideosSearchViewDetailMidE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8]  
    
1.  <span data-ttu-id="6e885-115">[プレイヤー **] メニュー** の下に、メディア プレーヤーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e885-115">Under the **Players** menu, a media player is displayed.</span></span>  
1.  <span data-ttu-id="6e885-116">プレイヤーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6e885-116">Choose the player.</span></span>  <span data-ttu-id="6e885-117">[ **プロパティ]** パネルには、メディア プレーヤーのプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e885-117">The **Properties** panel displays the properties of the media player.</span></span>  
    
    :::image type="complex" source="../media/media-panel-view.msft.png" alt-text="メディア プロパティ" lightbox="../media/media-panel-view.msft.png":::
       <span data-ttu-id="6e885-119">メディア プロパティ</span><span class="sxs-lookup"><span data-stu-id="6e885-119">Media properties</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6e885-120">すべてのメディア プレイヤー イベントを表示するには、[イベント] パネル **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="6e885-120">To view all the media player events, choose the **Events** panel.</span></span>  
    
    :::image type="complex" source="../media/media-panel-events.msft.png" alt-text="メディア イベント" lightbox="../media/media-panel-events.msft.png":::
       <span data-ttu-id="6e885-122">メディア イベント</span><span class="sxs-lookup"><span data-stu-id="6e885-122">Media events</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6e885-123">メディア プレーヤーのメッセージ ログを表示するには、[メッセージ] パネル **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="6e885-123">To view the media player message logs, choose the **Messages** panel.</span></span>  <span data-ttu-id="6e885-124">ログ レベルまたは文字列でメッセージをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="6e885-124">You may filter the messages by log level or string.</span></span>  
    
    :::image type="complex" source="../media/media-panel-messages.msft.png" alt-text="メディア メッセージ" lightbox="../media/media-panel-messages.msft.png":::
       <span data-ttu-id="6e885-126">メディア メッセージ</span><span class="sxs-lookup"><span data-stu-id="6e885-126">Media messages</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6e885-127">[タイムライン **] パネル** では、メディアの再生とバッファーの状態がライブで表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e885-127">On the **Timeline** panel, the media playback and buffer status is displayed live.</span></span>  
    
    :::image type="complex" source="../media/media-panel-timeline.msft.png" alt-text="メディアタイムライン" lightbox="../media/media-panel-timeline.msft.png":::
       <span data-ttu-id="6e885-129">メディアタイムライン</span><span class="sxs-lookup"><span data-stu-id="6e885-129">Media timeline</span></span>  
    :::image-end:::  
    
### <a name="remote-debugging"></a><span data-ttu-id="6e885-130">リモート デバッグ</span><span class="sxs-lookup"><span data-stu-id="6e885-130">Remote debugging</span></span>  

<span data-ttu-id="6e885-131">Windows または macOS コンピューターから Android デバイスのメディア プレーヤー情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="6e885-131">View the media players information on an Android device from your Windows or macOS computer.</span></span>  

1.  <span data-ttu-id="6e885-132">リモート デバッグを設定するには、[Android デバイスのリモート デバッグの開始 [] に移動します][DevtoolsGuideChromiumRemoteDebuggingIndex]。</span><span class="sxs-lookup"><span data-stu-id="6e885-132">To set up remote debugging, navigate to [Get started with remote debugging Android devices][DevtoolsGuideChromiumRemoteDebuggingIndex].</span></span>  
1.  <span data-ttu-id="6e885-133">メディア プレーヤーの情報をリモートで表示します。</span><span class="sxs-lookup"><span data-stu-id="6e885-133">View the media players information remotely.</span></span>  
    
    <!-- TODO: recreate image using an Android device -->  
    <!--  
    :::image type="complex" source="../media/media-panel-remote-debug.msft.png" alt-text="Remote debugging" lightbox="../media/media-panel-remote-debug.msft.png":::
       Remote debugging  
    :::image-end:::  
    -->  
    
## <a name="hide-and-show-media-players"></a><span data-ttu-id="6e885-134">メディア プレーヤーの非表示と表示</span><span class="sxs-lookup"><span data-stu-id="6e885-134">Hide and show media players</span></span>  

<span data-ttu-id="6e885-135">Web ページで複数のメディア プレーヤーを実行する場合や、同じブラウザー タブを使用して異なる Web ページを参照する場合があります。各 Web ページはメディア プレーヤーを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e885-135">Sometimes you run more than one media player on a webpage, or use the same browser tab to browse different webpages, each with media players.</span></span>

<span data-ttu-id="6e885-136">デバッグを容易にするために、各メディア プレーヤーを \(または show\) を非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="6e885-136">You may choose to hide \(or show\) each media player for an easier debugging experience.</span></span>  

1.  <span data-ttu-id="6e885-137">同じブラウザー タブを使用して、複数の異なるビデオ Web ページを参照します。</span><span class="sxs-lookup"><span data-stu-id="6e885-137">Browse to several different video webpages using the same browser tab.</span></span>  
1.  <span data-ttu-id="6e885-138">メディア プレーヤーを非表示にする場合は、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6e885-138">To hide media players, complete one of the following actions.</span></span>  
    *   <span data-ttu-id="6e885-139">1 つのメディア プレーヤーを非表示にする場合は、メディア プレーヤーにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[プレイヤーを非表示にする] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6e885-139">To hide one media player, hover on a media player, open the contextual menu \(right-click\), and choose **Hide player**.</span></span>  
    *   <span data-ttu-id="6e885-140">他のすべてのメディア プレーヤーを非表示にする場合は、メディア プレーヤーにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[他のすべてのメディア プレーヤーを非表示にする] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="6e885-140">To hide all of the other media players, hover on a media player, open the contextual menu \(right-click\), and choose **Hide all others**.</span></span>  
    
    :::image type="complex" source="../media/media-panel-hide-show.msft.png" alt-text="メディア プレーヤーを非表示にする" lightbox="../media/media-panel-hide-show.msft.png":::
       <span data-ttu-id="6e885-142">メディア プレーヤーを非表示にする</span><span class="sxs-lookup"><span data-stu-id="6e885-142">Hide media players</span></span>  
    :::image-end:::  
    
## <a name="export-media-player-information"></a><span data-ttu-id="6e885-143">メディア プレーヤー情報のエクスポート</span><span class="sxs-lookup"><span data-stu-id="6e885-143">Export media player information</span></span>  

1.  <span data-ttu-id="6e885-144">メディア プレーヤー情報を JSON ファイルとしてダウンロードするには、メディア プレーヤーにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[プレイヤー情報の保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="6e885-144">To download the media player info as a JSON file, hover on a media player, open the contextual menu \(right-click\), and choose **Save player info**.</span></span>  
    
    :::image type="complex" source="../media/media-panel-save.msft.png" alt-text="メディア情報のエクスポート" lightbox="../media/media-panel-save.msft.png":::
       <span data-ttu-id="6e885-146">メディア情報のエクスポート</span><span class="sxs-lookup"><span data-stu-id="6e885-146">Export media information</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="6e885-147">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="6e885-147">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open/index.md "Microsoft Edge (クロム) DevTools ファイルを開|Microsoft Docs"  

[DevtoolsGuideChromiumRemoteDebuggingIndex]: ../remote-debugging/index.md "Android デバイスのリモート デバッグの開始|Microsoft Docs"  

[BingVideosSearchViewDetailMidE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8]: https://www.bing.com/videos/search?view=detail&mid=DE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8 "エッジ開発者ツール を使用して生産性を最大化|Bing ビデオ"  

> [!NOTE]
> <span data-ttu-id="6e885-151">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="6e885-151">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="6e885-152">[Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/tools/chrome-devtools/media-panel/index)にあります。</span><span class="sxs-lookup"><span data-stu-id="6e885-152">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/media-panel/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="6e885-154">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="6e885-154">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  

