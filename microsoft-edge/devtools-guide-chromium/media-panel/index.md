---
description: メディア パネルを使って、ブラウザー タブごとに情報を表示し、メディア プレーヤーをデバッグします。
title: メディア プレーヤー情報の表示とデバッグ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: e6259cf573b76df7e281527ad30360b8f473a165
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230951"
---
# <span data-ttu-id="61372-104">メディア プレーヤー情報の表示とデバッグ</span><span class="sxs-lookup"><span data-stu-id="61372-104">View and debug media players information</span></span>  

<span data-ttu-id="61372-105">Microsoft \*\*\*\* Edge DevTools のメディア パネルを使用して、ブラウザータブごとに情報を表示し、メディア プレーヤーをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="61372-105">Use the **Media** panel in Microsoft Edge DevTools to view information and debug the media players per browser tab.</span></span>  

## <span data-ttu-id="61372-106">メディア パネルを開く</span><span class="sxs-lookup"><span data-stu-id="61372-106">Open the Media panel</span></span>  

<span data-ttu-id="61372-107">メディア **パネル** は、Web ページのメディア プレーヤーを検査する DevTools の主要な場所です。</span><span class="sxs-lookup"><span data-stu-id="61372-107">The **Media** panel is the main place in DevTools for inspecting the media player of a webpage.</span></span>

1.  <span data-ttu-id="61372-108">[DevTools を開きます][DevtoolsGuideChromiumOpen]。</span><span class="sxs-lookup"><span data-stu-id="61372-108">[Open DevTools][DevtoolsGuideChromiumOpen].</span></span>  
1.  <span data-ttu-id="61372-109">メディア パネルを開**く場合**は **、[DevTools** More tools Media のカスタマイズと制御 `...`  >  **] を選択**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="61372-109">To open the **Media** panel, choose **Customize and control DevTools** `...` > **More tools** > **Media**.</span></span>  
    
    :::image type="complex" source="../media/media-panel-empty.msft.png" alt-text="メディア パネル" lightbox="../media/media-panel-empty.msft.png":::
       <span data-ttu-id="61372-111">**メディア** パネル</span><span class="sxs-lookup"><span data-stu-id="61372-111">**Media** panel</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="61372-112">メディア プレーヤー情報の表示</span><span class="sxs-lookup"><span data-stu-id="61372-112">View media players information</span></span>  

1.  <span data-ttu-id="61372-113">次の Web ページなど、メディア プレーヤーを使用して Web ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="61372-113">Navigate to a webpage with a media player, such as the following webpage.</span></span>  
    
    [<span data-ttu-id="61372-114">エッジ開発者ツールによる生産性の最大化</span><span class="sxs-lookup"><span data-stu-id="61372-114">Maximizing productivity with the Edge Developer Tools</span></span>][BingVideosSearchViewDetailMidE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8]  
    
1.  <span data-ttu-id="61372-115">[ **プレイヤー] メニュー** の下に、メディア プレーヤーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="61372-115">Under the **Players** menu, a media player is displayed.</span></span>  
1.  <span data-ttu-id="61372-116">プレイヤーを選択します。</span><span class="sxs-lookup"><span data-stu-id="61372-116">Select the player.</span></span>  <span data-ttu-id="61372-117">[ **プロパティ]** タブには、メディア プレーヤーのプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="61372-117">The **Properties** tab displays the properties of the media player.</span></span>  
    
    :::image type="complex" source="../media/media-panel-view.msft.png" alt-text="メディア プロパティ" lightbox="../media/media-panel-view.msft.png":::
       <span data-ttu-id="61372-119">メディア プロパティ</span><span class="sxs-lookup"><span data-stu-id="61372-119">Media properties</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="61372-120">すべてのメディア プレーヤー イベントを表示するには、[イベント] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="61372-120">To view all the media player events, choose the **Events** tab.</span></span>  
    
    :::image type="complex" source="../media/media-panel-events.msft.png" alt-text="メディア イベント" lightbox="../media/media-panel-events.msft.png":::
       <span data-ttu-id="61372-122">メディア イベント</span><span class="sxs-lookup"><span data-stu-id="61372-122">Media events</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="61372-123">メディア プレーヤーのメッセージ ログを表示するには、[メッセージ] タブ **を選択** します。 メッセージはログ レベルまたは文字列でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="61372-123">To view the media player message logs, choose the **Messages** tab.  You may filter the messages by log level or string.</span></span>  
    
    :::image type="complex" source="../media/media-panel-messages.msft.png" alt-text="メディア メッセージ" lightbox="../media/media-panel-messages.msft.png":::
       <span data-ttu-id="61372-125">メディア メッセージ</span><span class="sxs-lookup"><span data-stu-id="61372-125">Media messages</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="61372-126">[ **タイムライン] タブ** では、メディアの再生とバッファーの状態がライブで表示されます。</span><span class="sxs-lookup"><span data-stu-id="61372-126">On the **Timeline** tab, the media playback and buffer status is displayed live.</span></span>  
    
    :::image type="complex" source="../media/media-panel-timeline.msft.png" alt-text="メディアのタイムライン" lightbox="../media/media-panel-timeline.msft.png":::
       <span data-ttu-id="61372-128">メディアのタイムライン</span><span class="sxs-lookup"><span data-stu-id="61372-128">Media timeline</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="61372-129">リモート デバッグ</span><span class="sxs-lookup"><span data-stu-id="61372-129">Remote debugging</span></span>  

<span data-ttu-id="61372-130">Windows または macOS コンピューターから Android デバイスのメディア プレーヤー情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="61372-130">View the media players information on an Android device from your Windows or macOS computer.</span></span>  

1.  <span data-ttu-id="61372-131">リモート デバッグをセットアップするには、Android デバイスのリモート デバッグの [開始に移動します][DevtoolsGuideChromiumRemoteDebuggingIndex]。</span><span class="sxs-lookup"><span data-stu-id="61372-131">To set up remote debugging, navigate to [Get started with remote debugging Android devices][DevtoolsGuideChromiumRemoteDebuggingIndex].</span></span>  
1.  <span data-ttu-id="61372-132">メディア プレーヤーの情報をリモートで表示します。</span><span class="sxs-lookup"><span data-stu-id="61372-132">View the media players information remotely.</span></span>  
    
    <!-- TODO: recreate image using an Android device -->  
    <!--  
    :::image type="complex" source="../media/media-panel-remote-debug.msft.png" alt-text="Remote debugging" lightbox="../media/media-panel-remote-debug.msft.png":::
       Remote debugging  
    :::image-end:::  
    -->  
    
## <span data-ttu-id="61372-133">メディア プレーヤーの非表示と表示</span><span class="sxs-lookup"><span data-stu-id="61372-133">Hide and show media players</span></span>  

<span data-ttu-id="61372-134">1 つの Web ページで複数のメディア プレーヤーを実行したり、同じブラウザー タブを使用して異なる Web ページを参照したり、メディア プレーヤーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="61372-134">Sometimes you run more than one media player on a webpage, or use the same browser tab to browse different webpages, each with media players.</span></span>

<span data-ttu-id="61372-135">デバッグを容易にするために、各メディア プレーヤーを \(または show\) 非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="61372-135">You may choose to hide \(or show\) each media player for an easier debugging experience.</span></span>  

1.  <span data-ttu-id="61372-136">同じブラウザー タブを使用して、複数の異なるビデオ Web ページを参照します。</span><span class="sxs-lookup"><span data-stu-id="61372-136">Browse to several different video webpages using the same browser tab.</span></span>  
1.  <span data-ttu-id="61372-137">メディア プレーヤーを非表示にする場合は、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="61372-137">To hide media players, complete one of the following actions.</span></span>  
    *   <span data-ttu-id="61372-138">1 つのメディア プレーヤーを非表示にする場合は、メディア プレーヤーをポイントし、コンテキスト メニュー \(右クリック\) を開き、[プレイヤーを非表示にする] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="61372-138">To hide one media player, hover on a media player, open the contextual menu \(right-click\), and choose **Hide player**.</span></span>  
    *   <span data-ttu-id="61372-139">他のすべてのメディア プレーヤーを非表示にする場合は、メディア プレーヤーにマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き、[他のすべてのメディア プレーヤーを非表示にする] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="61372-139">To hide all of the other media players, hover on a media player, open the contextual menu \(right-click\), and choose **Hide all others**.</span></span>  
    
    :::image type="complex" source="../media/media-panel-hide-show.msft.png" alt-text="メディア プレーヤーを非表示にする" lightbox="../media/media-panel-hide-show.msft.png":::
       <span data-ttu-id="61372-141">メディア プレーヤーを非表示にする</span><span class="sxs-lookup"><span data-stu-id="61372-141">Hide media players</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="61372-142">メディア プレーヤー情報のエクスポート</span><span class="sxs-lookup"><span data-stu-id="61372-142">Export media player information</span></span>  

1.  <span data-ttu-id="61372-143">メディア プレーヤーの情報を JSON ファイルとしてダウンロードするには、メディア プレーヤーにマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き、[プレイヤー情報の保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="61372-143">To download the media player info as a JSON file, hover on a media player, open the contextual menu \(right-click\), and choose **Save player info**.</span></span>  
    
    :::image type="complex" source="../media/media-panel-save.msft.png" alt-text="メディア情報のエクスポート" lightbox="../media/media-panel-save.msft.png":::
       <span data-ttu-id="61372-145">メディア情報のエクスポート</span><span class="sxs-lookup"><span data-stu-id="61372-145">Export media information</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="61372-146">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="61372-146">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open/index.md "Microsoft Edge (Chromium) DevTools を開く |Microsoft Docs"  

[DevtoolsGuideChromiumRemoteDebuggingIndex]: ../remote-debugging/index.md "Android デバイスのリモート デバッグの概要 |Microsoft Docs"  

[BingVideosSearchViewDetailMidE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8]: https://www.bing.com/videos/search?view=detail&mid=DE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8 "エッジ開発者ツールを使用して生産性を最大化する |Bing ビデオ"  

> [!NOTE]
> <span data-ttu-id="61372-150">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="61372-150">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="61372-151">[Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/tools/chrome-devtools/media-panel/index)にあります。</span><span class="sxs-lookup"><span data-stu-id="61372-151">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/media-panel/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="61372-153">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="61372-153">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  

