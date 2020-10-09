---
description: メディアパネルを使用して情報を表示し、[ブラウザー] タブごとにメディアプレーヤーをデバッグします。
title: メディアプレーヤー情報を表示してデバッグする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: dfcf17861c0296e347007bc3a1a02a2b80661e6f
ms.sourcegitcommit: 912609aa49864e3363aaa3b245ff2aa4bec3fc3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "11105204"
---
# <span data-ttu-id="b9500-104">メディアプレーヤー情報を表示してデバッグする</span><span class="sxs-lookup"><span data-stu-id="b9500-104">View and debug media players information</span></span>  

<span data-ttu-id="b9500-105">Microsoft Edge DevTools の **メディア** パネルを使用して、情報を表示し、ブラウザータブごとにメディアプレーヤーをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="b9500-105">Use the **Media** panel in Microsoft Edge DevTools to view information and debug the media players per browser tab.</span></span>  

## <span data-ttu-id="b9500-106">メディアパネルを開く</span><span class="sxs-lookup"><span data-stu-id="b9500-106">Open the Media panel</span></span>  

<span data-ttu-id="b9500-107">**メディア**パネルは、web ページのメディアプレーヤーを調べるための devtools の主要な場所です。</span><span class="sxs-lookup"><span data-stu-id="b9500-107">The **Media** panel is the main place in DevTools for inspecting the media player of a webpage.</span></span>

1.  <span data-ttu-id="b9500-108">[DevTools を開き][DevtoolsGuideChromiumOpen]ます。</span><span class="sxs-lookup"><span data-stu-id="b9500-108">[Open DevTools][DevtoolsGuideChromiumOpen].</span></span>  
1.  <span data-ttu-id="b9500-109">**メディア**パネルを開くには、[カスタマイズ] を選択し、[ **devtools** `...`  >  **その他のツール**  >  **メディア**] をコントロールします。</span><span class="sxs-lookup"><span data-stu-id="b9500-109">To open the **Media** panel, choose **Customize and control DevTools** `...` > **More tools** > **Media**.</span></span>  
    
    :::image type="complex" source="../media/media-panel-empty.msft.png" alt-text="メディアパネル" lightbox="../media/media-panel-empty.msft.png":::
       <span data-ttu-id="b9500-111">**メディア** パネル</span><span class="sxs-lookup"><span data-stu-id="b9500-111">**Media** panel</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="b9500-112">メディアプレーヤー情報の表示</span><span class="sxs-lookup"><span data-stu-id="b9500-112">View media players information</span></span>  

1.  <span data-ttu-id="b9500-113">次の web ページのように、メディアプレーヤーを使用して web ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="b9500-113">Navigate to a webpage with a media player, such as the following webpage.</span></span>  
    
    [<span data-ttu-id="b9500-114">Microsoft Edge 開発者ツールを使用した生産性の最大化</span><span class="sxs-lookup"><span data-stu-id="b9500-114">Maximizing productivity with the Edge Developer Tools</span></span>][BingVideosSearchViewDetailMidE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8]  
    
1.  <span data-ttu-id="b9500-115">[ **プレーヤー** ] メニューには、メディアプレーヤーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9500-115">Under the **Players** menu, a media player is displayed.</span></span>  
1.  <span data-ttu-id="b9500-116">プレーヤーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b9500-116">Select the player.</span></span>  <span data-ttu-id="b9500-117">[ **プロパティ** ] タブには、メディアプレーヤーのプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9500-117">The **Properties** tab displays the properties of the media player.</span></span>  
    
    :::image type="complex" source="../media/media-panel-view.msft.png" alt-text="メディアパネル" lightbox="../media/media-panel-view.msft.png":::
       <span data-ttu-id="b9500-119">メディアのプロパティ</span><span class="sxs-lookup"><span data-stu-id="b9500-119">Media properties</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b9500-120">メディアプレーヤーのイベントをすべて表示するには、[ **イベント** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="b9500-120">To view all the media player events, choose the **Events** tab.</span></span>  
    
    :::image type="complex" source="../media/media-panel-events.msft.png" alt-text="メディアパネル" lightbox="../media/media-panel-events.msft.png":::
       <span data-ttu-id="b9500-122">メディアイベント</span><span class="sxs-lookup"><span data-stu-id="b9500-122">Media events</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b9500-123">メディアプレーヤーのメッセージログを表示するには、[ **メッセージ** ] タブを選びます。 ログレベルまたは文字列でメッセージをフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="b9500-123">To view the media player message logs, choose the **Messages** tab.  You may filter the messages by log level or string.</span></span>  
    
    :::image type="complex" source="../media/media-panel-messages.msft.png" alt-text="メディアパネル" lightbox="../media/media-panel-messages.msft.png":::
       <span data-ttu-id="b9500-125">メディアメッセージ</span><span class="sxs-lookup"><span data-stu-id="b9500-125">Media messages</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b9500-126">[ **タイムライン** ] タブでは、メディアの再生とバッファーの状態がライブで表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9500-126">On the **Timeline** tab, the media playback and buffer status is displayed live.</span></span>  
    
    :::image type="complex" source="../media/media-panel-timeline.msft.png" alt-text="メディアパネル" lightbox="../media/media-panel-timeline.msft.png":::
       <span data-ttu-id="b9500-128">メディアタイムライン</span><span class="sxs-lookup"><span data-stu-id="b9500-128">Media timeline</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="b9500-129">リモート デバッグ</span><span class="sxs-lookup"><span data-stu-id="b9500-129">Remote debugging</span></span>  

<span data-ttu-id="b9500-130">Windows または macOS コンピューターから Android デバイスでメディアプレーヤー情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="b9500-130">View the media players information on an Android device from your Windows or macOS computer.</span></span>  

1.  <span data-ttu-id="b9500-131">リモートデバッグをセットアップするには、「 [リモートデバッグの Android デバイスの使用を開始][DevtoolsGuideChromiumRemoteDebuggingIndex]する」に移動します。</span><span class="sxs-lookup"><span data-stu-id="b9500-131">To set up remote debugging, navigate to [Get started with remote debugging Android devices][DevtoolsGuideChromiumRemoteDebuggingIndex].</span></span>  
1.  <span data-ttu-id="b9500-132">メディアプレーヤー情報をリモートで表示します。</span><span class="sxs-lookup"><span data-stu-id="b9500-132">View the media players information remotely.</span></span>  
    
    <!-- TODO: recreate image using an Android device -->  
    <!--  
    :::image type="complex" source="../media/media-panel-remote-debug.msft.png" alt-text="メディアパネル" lightbox="../media/media-panel-remote-debug.msft.png":::
       Remote debugging  
    :::image-end:::  
    -->  
    
## <span data-ttu-id="b9500-133">メディアプレーヤーの表示と非表示を切り替える</span><span class="sxs-lookup"><span data-stu-id="b9500-133">Hide and show media players</span></span>  

<span data-ttu-id="b9500-134">複数のメディアプレーヤーを web ページで実行している場合、または同じブラウザーのタブを使用して別の web ページを参照している場合があります。それぞれのメディアプレーヤーを使用します。</span><span class="sxs-lookup"><span data-stu-id="b9500-134">Sometimes you run more than one media player on a webpage, or use the same browser tab to browse different webpages, each with media players.</span></span>

<span data-ttu-id="b9500-135">簡単なデバッグエクスペリエンスを実現するために、各メディアプレーヤーを非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b9500-135">You may choose to hide \(or show\) each media player for an easier debugging experience.</span></span>  

1.  <span data-ttu-id="b9500-136">同じブラウザータブを使用して、複数の異なるビデオ web ページを参照します。</span><span class="sxs-lookup"><span data-stu-id="b9500-136">Browse to several different video webpages using the same browser tab.</span></span>  
1.  <span data-ttu-id="b9500-137">メディアプレーヤーを非表示にするには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b9500-137">To hide media players, complete one of the following actions.</span></span>  
    *   <span data-ttu-id="b9500-138">1つのメディアプレーヤーを非表示にするには、メディアプレーヤーにマウスポインターを合わせて、コンテキストメニューを開き (\ を右クリックし)、[ **プレーヤーを表示**しない] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b9500-138">To hide one media player, hover on a media player, open the contextual menu \(right-click\), and choose **Hide player**.</span></span>  
    *   <span data-ttu-id="b9500-139">他のすべてのメディアプレーヤーを非表示にするには、メディアプレーヤーにマウスポインターを合わせて、コンテキストメニュー \ (右クリック \) を開いて、[ **すべてのユーザーを表示**しない] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b9500-139">To hide all of the other media players, hover on a media player, open the contextual menu \(right-click\), and choose **Hide all others**.</span></span>  
    
    :::image type="complex" source="../media/media-panel-hide-show.msft.png" alt-text="メディアパネル" lightbox="../media/media-panel-hide-show.msft.png":::
       <span data-ttu-id="b9500-141">メディアプレーヤーを非表示にする</span><span class="sxs-lookup"><span data-stu-id="b9500-141">Hide media players</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="b9500-142">メディアプレーヤー情報をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="b9500-142">Export media player information</span></span>  

1.  <span data-ttu-id="b9500-143">メディアプレーヤー情報を JSON ファイルとしてダウンロードするには、メディアプレーヤーにマウスポインターを合わせて、コンテキストメニュー \ (右クリック \) を開き、[ **プレーヤーの情報を保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9500-143">To download the media player info as a JSON file, hover on a media player, open the contextual menu \(right-click\), and choose **Save player info**.</span></span>  
    
    :::image type="complex" source="../media/media-panel-save.msft.png" alt-text="メディアパネル" lightbox="../media/media-panel-save.msft.png":::
       <span data-ttu-id="b9500-145">メディア情報をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="b9500-145">Export media information</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="b9500-146">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="b9500-146">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open.md "Microsoft Edge DevTools を開く"  

[DevtoolsGuideChromiumRemoteDebuggingIndex]: ../remote-debugging/index.md "Android デバイスのリモートデバッグの概要 |Microsoft ドキュメント"  

[BingVideosSearchViewDetailMidE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8]: https://www.bing.com/videos/search?view=detail&mid=DE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8 "Microsoft Edge 開発者向けツールを使った生産性の最大化 |Bing ビデオ"  

> [!NOTE]
> <span data-ttu-id="b9500-150">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="b9500-150">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b9500-151">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/media-panel/index) にあり、 [Jecelyn][JecelynYeen] で作成されています (開発者の代表者、Chrome devtools \)。</span><span class="sxs-lookup"><span data-stu-id="b9500-151">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/media-panel/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="b9500-153">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="b9500-153">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  

