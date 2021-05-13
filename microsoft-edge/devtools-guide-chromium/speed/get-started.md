---
description: DevTools で web サイトMicrosoft Edge読み込む方法を見つける方法について学習します。
title: DevTools を使用して web サイトMicrosoft Edge最適化する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 304cf9e36260b8637af38ed0dfe1ba91f3a56504
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564883"
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
# <a name="optimize-website-speed-with-microsoft-edge-devtools"></a><span data-ttu-id="32210-104">DevTools を使用して web サイトMicrosoft Edge最適化する</span><span class="sxs-lookup"><span data-stu-id="32210-104">Optimize website speed with Microsoft Edge DevTools</span></span>  

## <a name="goal-of-tutorial"></a><span data-ttu-id="32210-105">チュートリアルの目標</span><span class="sxs-lookup"><span data-stu-id="32210-105">Goal of tutorial</span></span>  

<span data-ttu-id="32210-106">このチュートリアルでは、DevTools Microsoft Edgeを使用して、Web サイトの読み込み速度を向上させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="32210-106">This tutorial teaches you how to use Microsoft Edge DevTools to find ways to make your websites load faster.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="32210-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="32210-107">Prerequisites</span></span>  

*   <span data-ttu-id="32210-108">この 「Web 開発の概要」クラスで説明されているのと同様に、基本的な Web 開発エクスペリエンス [が必要です][CourseraIntroductionWebDevelopmentClass]。</span><span class="sxs-lookup"><span data-stu-id="32210-108">You should have basic web development experience, similar to what is taught in this [Introduction to Web Development class][CourseraIntroductionWebDevelopmentClass].</span></span>  
*   <span data-ttu-id="32210-109">読み込みパフォーマンスについて何も知る必要はありません。</span><span class="sxs-lookup"><span data-stu-id="32210-109">You do not need to know anything about load performance.</span></span>  <span data-ttu-id="32210-110">詳細については、このチュートリアルで説明します。</span><span class="sxs-lookup"><span data-stu-id="32210-110">You learn about it in this tutorial.</span></span>  

## <a name="introduction"></a><span data-ttu-id="32210-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="32210-111">Introduction</span></span>  

<span data-ttu-id="32210-112">これは Tony です。</span><span class="sxs-lookup"><span data-stu-id="32210-112">This is Tony.</span></span>  <span data-ttu-id="32210-113">トニーは猫社会で非常に有名です。</span><span class="sxs-lookup"><span data-stu-id="32210-113">Tony is very famous in cat society.</span></span>  <span data-ttu-id="32210-114">ファンが自分の好きな食べ物について学べる Web サイトを構築しました。</span><span class="sxs-lookup"><span data-stu-id="32210-114">He has built a website so that his fans are able to learn about his favorite foods.</span></span>  <span data-ttu-id="32210-115">彼のファンはサイトを愛していますが、Tony はサイトの読み込み時間が遅いという苦情を聞き続ける。</span><span class="sxs-lookup"><span data-stu-id="32210-115">His fans love the site, but Tony keeps hearing complaints that the site loads slowly.</span></span>  <span data-ttu-id="32210-116">Tony は、サイトの速度を上げろと頼んだ。</span><span class="sxs-lookup"><span data-stu-id="32210-116">Tony has asked you to help him speed the site up.</span></span>  

:::image type="complex" source="../media/speed-tony.msft.png" alt-text="猫のトニー" lightbox="../media/speed-tony.msft.png":::
   <span data-ttu-id="32210-118">猫のトニー</span><span class="sxs-lookup"><span data-stu-id="32210-118">Tony the cat</span></span>  
:::image-end:::  

## <a name="step-1-audit-the-site"></a><span data-ttu-id="32210-119">手順 1: サイトを監査する</span><span class="sxs-lookup"><span data-stu-id="32210-119">Step 1: Audit the site</span></span>  

<span data-ttu-id="32210-120">サイトの読み込みパフォーマンスを向上させるために設定する場合は常に、 **監査から始める必要があります**。</span><span class="sxs-lookup"><span data-stu-id="32210-120">Whenever you set out to improve the load performance of a site, **always start with an audit**.</span></span>  
<span data-ttu-id="32210-121">監査には、次の 2 つの重要な機能があります。</span><span class="sxs-lookup"><span data-stu-id="32210-121">The audit has 2 important functions:</span></span>  

*   <span data-ttu-id="32210-122">それ以降の変更 **を測定** する基準を作成します。</span><span class="sxs-lookup"><span data-stu-id="32210-122">It creates a **baseline** for you to measure subsequent changes against.</span></span>  
*   <span data-ttu-id="32210-123">これは、変更 **が最も影響を** 与える影響に関する操作可能なヒントを提供します。</span><span class="sxs-lookup"><span data-stu-id="32210-123">It gives you **actionable tips** on what changes have the most impact.</span></span>  
    
### <a name="set-up"></a><span data-ttu-id="32210-124">設定</span><span class="sxs-lookup"><span data-stu-id="32210-124">Set up</span></span>  

<span data-ttu-id="32210-125">最初に、後で変更を加えるサイトをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="32210-125">First, you must set up the site so that you are able to make changes to it later.</span></span>  

1.  <span data-ttu-id="32210-126">[サイトのソース コードを開きます](https://glitch.com/edit/#!/tony)。</span><span class="sxs-lookup"><span data-stu-id="32210-126">[Open the source code for the site](https://glitch.com/edit/#!/tony).</span></span>  <span data-ttu-id="32210-127">このタブは、エディター タブと **呼ばれます**。</span><span class="sxs-lookup"><span data-stu-id="32210-127">This tab is referred to as the **editor tab**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js.msft.png" alt-text="[エディター] タブ" lightbox="../media/speed-glitch-tony-server-js.msft.png":::
       <span data-ttu-id="32210-129">[ **エディター] タブ**</span><span class="sxs-lookup"><span data-stu-id="32210-129">The **editor tab**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="32210-130">Tony **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="32210-130">Choose **tony**.</span></span>  <span data-ttu-id="32210-131">メニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="32210-131">A menu appears.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js-remix-project.msft.png" alt-text="tony を選択した後に表示されるメニュー" lightbox="../media/speed-glitch-tony-server-js-remix-project.msft.png":::
       <span data-ttu-id="32210-133">tony を選択した後に表示される **メニュー**</span><span class="sxs-lookup"><span data-stu-id="32210-133">The menu that appears after choosing **tony**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="32210-134">**[Remix Project] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="32210-134">Choose **Remix Project**.</span></span>  <span data-ttu-id="32210-135">プロジェクトの名前が **tony** からランダムに生成された名前に変わります。</span><span class="sxs-lookup"><span data-stu-id="32210-135">The name of the project changes from **tony** to some randomly-generated name.</span></span>  <span data-ttu-id="32210-136">これで、コードの独自の編集可能なコピーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="32210-136">You now have your own editable copy of the code.</span></span>  <span data-ttu-id="32210-137">後で、このコードを変更できます。</span><span class="sxs-lookup"><span data-stu-id="32210-137">Later on, you may make changes to this code.</span></span>  
1.  <span data-ttu-id="32210-138">[表示 **] を** 選択し、[ **新しいウィンドウ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="32210-138">Choose **Show** and choose **In a New Window**.</span></span>  <span data-ttu-id="32210-139">デモが新しいタブで開きます。 このタブは、デモ タブと **呼ばれます**。 サイトの読み込みには時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="32210-139">The demo opens in a new tab.  This tab is be referred to as the **demo tab**.  It may take a while for the site to load.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live.msft.png" alt-text="[デモ] タブ" lightbox="../media/speed-glitch-tony-show-live.msft.png":::
       <span data-ttu-id="32210-141">[デモ] タブ</span><span class="sxs-lookup"><span data-stu-id="32210-141">The demo tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="32210-142">`Control` + `Shift` + `J` \(Windows Linux\) または `Command` + `Option` + `J` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="32210-142">Select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  <span data-ttu-id="32210-143">Microsoft EdgeDevTools はデモと一緒に開きます。</span><span class="sxs-lookup"><span data-stu-id="32210-143">Microsoft Edge DevTools opens up alongside the demo.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live-console.msft.png" alt-text="DevTools とデモ" lightbox="../media/speed-glitch-tony-show-live-console.msft.png":::
       <span data-ttu-id="32210-145">DevTools とデモ</span><span class="sxs-lookup"><span data-stu-id="32210-145">DevTools and the demo</span></span>  
    :::image-end:::  
    
<span data-ttu-id="32210-146">このチュートリアルの残りのスクリーンショットについては、DevTools が別のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="32210-146">For the rest of the screenshots in this tutorial, DevTools is shown in a separate window.</span></span>  <span data-ttu-id="32210-147">`Control` + `Shift` + `P` \(Windows、Linux\) または `Command` + `Shift` + `P` \(macOS\) `Undock` \*\*\*\* を選択してコマンド メニューを開き、入力し、[別のウィンドウにドッキング解除] を選択します。</span><span class="sxs-lookup"><span data-stu-id="32210-147">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, typing `Undock`, and then selecting **Undock into separate window**.</span></span>  

:::image type="complex" source="../media/speed-console.msft.png" alt-text="ドッキングされていない DevTools" lightbox="../media/speed-console.msft.png":::
   <span data-ttu-id="32210-149">ドッキングされていない DevTools</span><span class="sxs-lookup"><span data-stu-id="32210-149">Undocked DevTools</span></span>  
:::image-end:::  

### <a name="establish-a-baseline"></a><span data-ttu-id="32210-150">ベースラインを確立する</span><span class="sxs-lookup"><span data-stu-id="32210-150">Establish a baseline</span></span>  

<span data-ttu-id="32210-151">ベースラインは、パフォーマンスを向上させる前にサイトがどのように実行されたのかの記録です。</span><span class="sxs-lookup"><span data-stu-id="32210-151">The baseline is a record of how the site performed before you made any performance improvements.</span></span>  

1.  <span data-ttu-id="32210-152">[監査] **ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="32210-152">Choose the **Audits** tool.</span></span>  <span data-ttu-id="32210-153">[その他のパネル] \( **More Panels** \) ボタン ![ の ](../media/more-panels-icon.msft.png) 背後に非表示になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="32210-153">It may be hidden behind the **More Panels** \(![More Panels](../media/more-panels-icon.msft.png)\) button.</span></span>  <span data-ttu-id="32210-154">このパネルには、監査パネルの電源を供給するプロジェクトが「ライトハウス」という名前なので、ライトハウス **があります**。</span><span class="sxs-lookup"><span data-stu-id="32210-154">There is a Lighthouse on this panel because the project that powers the Audits panel is named **Lighthouse**.</span></span>  
    
    [!INCLUDE [audits-panel-note](../includes/audits-panel-note.md)]  
    
    :::image type="complex" source="../media/speed-audits-performance.msft.png" alt-text="監査ツール" lightbox="../media/speed-audits-performance.msft.png":::
       <span data-ttu-id="32210-156">監査**ツール**</span><span class="sxs-lookup"><span data-stu-id="32210-156">The **Audits** tool</span></span>  
    :::image-end:::  
    
    <!--todo: add link to Lighthouse when section is available  -->  
    <!-- /web/tools/lighthouse  -->  
    
1.  <span data-ttu-id="32210-157">監査構成設定を前の図の監査構成設定と一致します。</span><span class="sxs-lookup"><span data-stu-id="32210-157">Match your audit configuration settings to those in the previous figure.</span></span>  <span data-ttu-id="32210-158">さまざまなオプションの説明を次に示します。</span><span class="sxs-lookup"><span data-stu-id="32210-158">Here is an explanation of the different options:</span></span>  
    
    *   <span data-ttu-id="32210-159">**デバイス .**</span><span class="sxs-lookup"><span data-stu-id="32210-159">**Device**.</span></span>  <span data-ttu-id="32210-160">[モバイル] **に設定** すると、ユーザー エージェント文字列が変更され、モバイル ビューポートがシミュレートされます。</span><span class="sxs-lookup"><span data-stu-id="32210-160">Set to **Mobile** changes the user agent string and simulates a mobile viewport.</span></span>  <span data-ttu-id="32210-161">デスクトップに **設定すると** 、モバイルの変更が **オフ** になります。</span><span class="sxs-lookup"><span data-stu-id="32210-161">Set to **Desktop** pretty much just turns off the **Mobile** changes.</span></span>  
    *   <span data-ttu-id="32210-162">**監査**。</span><span class="sxs-lookup"><span data-stu-id="32210-162">**Audits**.</span></span>  <span data-ttu-id="32210-163">カテゴリをオフにし、[監査] パネル **で** これらの監査を実行し、それらの監査をレポートから除外します。</span><span class="sxs-lookup"><span data-stu-id="32210-163">Turn off a category to prevent the **Audits** panel from running those audits, and excludes those audits from your report.</span></span>  <span data-ttu-id="32210-164">提供される推奨事項の種類を表示する場合は、他のカテゴリをオンのままにします。</span><span class="sxs-lookup"><span data-stu-id="32210-164">Leave the other categories Turned on, if you want to display the types of recommendations that are provided.</span></span>  <span data-ttu-id="32210-165">カテゴリをオフにし、監査プロセスを少し高速化します。</span><span class="sxs-lookup"><span data-stu-id="32210-165">Turn off categories to slightly speed up the auditing process.</span></span>  
    *   <span data-ttu-id="32210-166">**調整 .**</span><span class="sxs-lookup"><span data-stu-id="32210-166">**Throttling**.</span></span>  <span data-ttu-id="32210-167">[ **シミュレートされた低速 4G] に設定すると、4 倍の CPU** スローダウンによって、モバイル デバイスでの一般的なブラウズ条件がシミュレートされます。</span><span class="sxs-lookup"><span data-stu-id="32210-167">Set to **Simulated Slow 4G, 4x CPU Slowdown** simulates the typical conditions of browsing on a mobile device.</span></span>  <span data-ttu-id="32210-168">監査プロセス中に監査パネルが実際に調整されないので、"シミュレート" という名前が付きます。</span><span class="sxs-lookup"><span data-stu-id="32210-168">It is named "simulated" because the Audits panel does not actually throttle during the auditing process.</span></span>  <span data-ttu-id="32210-169">代わりに、モバイル条件下でページの読み込みにかかる時間を余分に表示します。</span><span class="sxs-lookup"><span data-stu-id="32210-169">Instead, it just extrapolates how long the page takes to load under mobile conditions.</span></span>  <span data-ttu-id="32210-170">一 **方、Applied...** の設定は、より長い監査プロセスのトレードオフを使用して、CPU とネットワークを実際に調整します。</span><span class="sxs-lookup"><span data-stu-id="32210-170">The **Applied...** setting, on the other hand, actually throttles your CPU and network, with the tradeoff of a longer auditing process.</span></span>  
    *   <span data-ttu-id="32210-171">**[Storage] をStorage**します。</span><span class="sxs-lookup"><span data-stu-id="32210-171">**Clear Storage**.</span></span>  <span data-ttu-id="32210-172">チェック ボックスをオンにすると、すべての監査の前にページに関連付けられているすべての記憶域がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="32210-172">Turn on the checkbox to clear all storage associated with the page before every audit.</span></span>  <span data-ttu-id="32210-173">初めての訪問者がサイトを体験する方法を監査する場合は、この設定をオンのままにします。</span><span class="sxs-lookup"><span data-stu-id="32210-173">Leave this setting on if you want to audit how first-time visitors experience your site.</span></span>  <span data-ttu-id="32210-174">繰り返し訪問エクスペリエンスが必要な場合は、この設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="32210-174">Turn off this setting when you want the repeat-visit experience.</span></span>  
    
1.  <span data-ttu-id="32210-175">[ **監査の実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="32210-175">Choose **Run Audits**.</span></span>  <span data-ttu-id="32210-176">10 ~ 30 秒後に、[ **監査** ] パネルにサイトのパフォーマンスのレポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="32210-176">After 10 to 30 seconds, the **Audits** panel displays a report of the performance of the site.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png" alt-text="サイトのパフォーマンスの [監査] パネルのレポート" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png":::
       <span data-ttu-id="32210-178">サイトのパフォーマンスの [監査] パネルのレポート</span><span class="sxs-lookup"><span data-stu-id="32210-178">The report for the Audits panel of the performance of the site</span></span>  
    :::image-end:::  
    
#### <a name="handling-report-errors"></a><span data-ttu-id="32210-179">レポート エラーの処理</span><span class="sxs-lookup"><span data-stu-id="32210-179">Handling report errors</span></span>  

<span data-ttu-id="32210-180">監査パネル レポートでエラーが発生した場合は、他のタブが開いていない **InPrivate** ウィンドウからデモ タブを実行してみてください。</span><span class="sxs-lookup"><span data-stu-id="32210-180">If you ever get an error in your Audits panel report, try running the demo tab from an **InPrivate** window with no other tabs open.</span></span>  <span data-ttu-id="32210-181">これにより、クリーンな状態からMicrosoft Edge実行できます。</span><span class="sxs-lookup"><span data-stu-id="32210-181">This ensures that you are running Microsoft Edge from a clean state.</span></span>  <span data-ttu-id="32210-182">Microsoft Edge特に拡張機能は、多くの場合、監査プロセスに干渉します。</span><span class="sxs-lookup"><span data-stu-id="32210-182">Microsoft Edge Extensions in particular often interfere with the auditing process.</span></span>  

<!--todo: add screen capture for error in audit -->  
<!--
:::image type="complex" source="../media/speed-.msft.png" alt-text="A report that errored" lightbox="../media/speed-.msft.png":::
   A report that errored  
:::image-end:::  
-->  

### <a name="understand-your-report"></a><span data-ttu-id="32210-183">レポートを理解する</span><span class="sxs-lookup"><span data-stu-id="32210-183">Understand your report</span></span>  

<span data-ttu-id="32210-184">レポートの上部にある数値は、サイトの全体的なパフォーマンス スコアです。</span><span class="sxs-lookup"><span data-stu-id="32210-184">The number at the top of your report is the overall performance score for the site.</span></span>  <span data-ttu-id="32210-185">後で、コードを変更すると、表示される番号が上がる必要があります。</span><span class="sxs-lookup"><span data-stu-id="32210-185">Later, as you make changes to the code, the number displayed should rise.</span></span>  <span data-ttu-id="32210-186">スコアが高いほど、パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="32210-186">A higher score means better performance.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png" alt-text="全体的なパフォーマンス スコア" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png":::
   <span data-ttu-id="32210-188">全体的なパフォーマンス スコア</span><span class="sxs-lookup"><span data-stu-id="32210-188">The overall performance score</span></span>  
:::image-end:::  

<span data-ttu-id="32210-189">[ **メトリック] セクション** には、サイトのパフォーマンスの定量測定値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="32210-189">The **Metrics** section provides quantitative measurements of the performance of the site.</span></span>  <span data-ttu-id="32210-190">各メトリックは、パフォーマンスの異なる側面に関する分析情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="32210-190">Each metric provides insight into a different aspect of the performance.</span></span>  <span data-ttu-id="32210-191">たとえば **、First Contentful ペイント**は、コンテンツが最初に画面にペイントされる時期を示します。これは、ページの読み込みに対するユーザーの認識における重要なマイルストーンですが、Time **To Interactive**は、ページがユーザーの操作を処理するのに十分な準備ができていると表示されるポイントをマークします。</span><span class="sxs-lookup"><span data-stu-id="32210-191">For example, **First Contentful Paint** tells you when content is first painted to the screen, which is an important milestone in the user's perception of the page load, whereas **Time To Interactive** marks the point at which the page appears ready enough to handle user interactions.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png" alt-text="[メトリック] セクション" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png":::
   <span data-ttu-id="32210-193">[ **メトリック]** セクション</span><span class="sxs-lookup"><span data-stu-id="32210-193">The **Metrics** section</span></span>  
:::image-end:::  

<span data-ttu-id="32210-194">次の図で強調表示されているトグル ボタンを選択して、各指標の説明を表示し\*\*\*\*、[詳細] を選択してドキュメントを読み取ってください。</span><span class="sxs-lookup"><span data-stu-id="32210-194">Choose the highlighted toggle button in the following figure to display a description for each metric, and choose **Learn More** to read documentation about it.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png" alt-text="[メトリック] アイテムを展開するには、強調表示されたトグル ボタンを選択します。" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png":::
   <span data-ttu-id="32210-196">[メトリック] アイテムを展開するには、強調表示されたトグル ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="32210-196">Choose the highlighted toggle button to expand the Metrics items</span></span>  
:::image-end:::  

<span data-ttu-id="32210-197">[指標] の下には、ページの読み込み時の外観を示すスクリーンショットのコレクションがあります。</span><span class="sxs-lookup"><span data-stu-id="32210-197">Below Metrics is a collection of screenshots that show you how the page looked as it loaded.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text="読み込み中のページの外観のスクリーンショット" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   <span data-ttu-id="32210-199">読み込み中のページの外観のスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="32210-199">Screenshots of how the page looked while loading</span></span>  
:::image-end:::  

<span data-ttu-id="32210-200">[ **機会] セクション** には、この特定のページの読み込みパフォーマンスを向上させる方法に関する具体的なヒントが示されています。</span><span class="sxs-lookup"><span data-stu-id="32210-200">The **Opportunities** section provides specific tips on how to improve the load performance of this specific page.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text="[商談] セクション" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   <span data-ttu-id="32210-202">[ **商談]** セクション</span><span class="sxs-lookup"><span data-stu-id="32210-202">The **Opportunities** section</span></span>  
:::image-end:::  

<span data-ttu-id="32210-203">その詳細を知る機会を選ぶ。</span><span class="sxs-lookup"><span data-stu-id="32210-203">Choose an opportunity to learn more about it.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png" alt-text="レンダリングブロックリソースの機会を排除する" lightbox="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png":::
   <span data-ttu-id="32210-205">**レンダリングブロックリソースの機会を排除** する</span><span class="sxs-lookup"><span data-stu-id="32210-205">**Eliminate render-blocking resources** opportunity</span></span>  
:::image-end:::  

<span data-ttu-id="32210-206">[ **詳細] を** 選択して、機会が重要な理由に関するドキュメントと、その修正方法に関する具体的な推奨事項を表示します。</span><span class="sxs-lookup"><span data-stu-id="32210-206">Choose **Learn More** to display documentation about why an opportunity is important, and specific recommendations on how to fix it.</span></span>  

:::image type="complex" source="../media/speed-web-dev-performance-audits.msft.png" alt-text="レンダリングブロックリソースの排除機会に関するドキュメント" lightbox="../media/speed-web-dev-performance-audits.msft.png":::
   <span data-ttu-id="32210-208">レンダリングブロックリソース**の排除機会に関するドキュメント**</span><span class="sxs-lookup"><span data-stu-id="32210-208">Documentation for the **Eliminate render-blocking resources** opportunity</span></span>  
:::image-end:::  

<span data-ttu-id="32210-209">[ **診断] セクション** では、ページの読み込み時間に寄与する要因の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="32210-209">The **Diagnostics** section provides more information about factors that contribute to the load time of the page.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png" alt-text="[診断] セクション" lightbox="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png":::
   <span data-ttu-id="32210-211">[ **診断]** セクション</span><span class="sxs-lookup"><span data-stu-id="32210-211">The **Diagnostics** section</span></span>  
:::image-end:::  

<span data-ttu-id="32210-212">[ **渡された監査] セクション** には、サイトの正常な動作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="32210-212">The **Passed Audits** section shows you what the site is doing correctly.</span></span>  <span data-ttu-id="32210-213">セクションを展開する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="32210-213">Choose to expand the section.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png" alt-text="[渡された監査] セクション" lightbox="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png":::
   <span data-ttu-id="32210-215">[ **渡された監査]** セクション</span><span class="sxs-lookup"><span data-stu-id="32210-215">The **Passed Audits** section</span></span>  
:::image-end:::  

## <a name="step-2-experiment"></a><span data-ttu-id="32210-216">手順 2: 実験</span><span class="sxs-lookup"><span data-stu-id="32210-216">Step 2: Experiment</span></span>  

<span data-ttu-id="32210-217">監査レポートの [機会] セクションには、ページのパフォーマンスを向上させる方法に関するヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="32210-217">The Opportunities section of your audit report gives you tips on how to improve the performance of the page.</span></span>  <span data-ttu-id="32210-218">このセクションでは、コードベースに対して推奨される変更を実装し、変更後にサイトを監査して、サイトの速度に与える影響を測定します。</span><span class="sxs-lookup"><span data-stu-id="32210-218">In this section, you implement the recommended changes to the codebase, auditing the site after each change to measure how it affects site speed.</span></span>  

### <a name="enable-text-compression"></a><span data-ttu-id="32210-219">テキスト圧縮を有効にする</span><span class="sxs-lookup"><span data-stu-id="32210-219">Enable text compression</span></span>  

<span data-ttu-id="32210-220">レポートでは、膨大なネットワーク ペイロードを避けることは、ページのパフォーマンスを向上させる最も重要な機会の 1 つだと述べています。</span><span class="sxs-lookup"><span data-stu-id="32210-220">Your report says that avoiding enormous network payloads is one of the top opportunities for improving the performance of the page.</span></span>  <span data-ttu-id="32210-221">テキスト圧縮を有効にすると、ページのパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="32210-221">Enabling text compression is an opportunity to improve the performance of the page.</span></span>  

<span data-ttu-id="32210-222">テキスト圧縮は、テキスト ファイルをネットワーク上で送信する前に、テキスト ファイルのサイズを小さくするか、圧縮する場合です。</span><span class="sxs-lookup"><span data-stu-id="32210-222">Text compression is when you reduce, or compress, the size of a text file before sending it over the network.</span></span>  <span data-ttu-id="32210-223">サイズを小さくするために、ディレクトリを送信する前にアーカイブする方法と同様です。</span><span class="sxs-lookup"><span data-stu-id="32210-223">Similar to how you may archive a directory before sending it to reduce the size.</span></span>  

<span data-ttu-id="32210-224">圧縮を有効にする前に、テキスト リソースが圧縮されているかどうかを手動で確認する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="32210-224">Before you enable compression, here are a couple of ways to manually check whether text resources are compressed.</span></span>  

1.  <span data-ttu-id="32210-225">[ネットワーク] **ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="32210-225">Choose the **Network** tool.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/speed-glitch-tony-remix-network.msft.png":::
       <span data-ttu-id="32210-227">ネットワーク**ツール**</span><span class="sxs-lookup"><span data-stu-id="32210-227">The **Network** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="32210-228">[ネットワーク設定 **] アイコンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="32210-228">Choose the **Network setting** icon.</span></span>  
1.  <span data-ttu-id="32210-229">[大きな **要求行を使用する] チェック ボックスを** オンにします。</span><span class="sxs-lookup"><span data-stu-id="32210-229">Choose the **Use Large Request Rows** checkbox.</span></span>  <span data-ttu-id="32210-230">ネットワーク要求のテーブル内の行の高さが増加します。</span><span class="sxs-lookup"><span data-stu-id="32210-230">The height of the rows in the table of network requests increases.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png" alt-text="ネットワーク要求テーブルの大きい行" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png":::
       <span data-ttu-id="32210-232">ネットワーク要求テーブルの大きい行</span><span class="sxs-lookup"><span data-stu-id="32210-232">Large rows in the network requests table</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="32210-233">ネットワーク要求 **の表** の [サイズ] 列が表示されない場合は、テーブル ヘッダーを [サイズ] > **選択します**。</span><span class="sxs-lookup"><span data-stu-id="32210-233">If the **Size** column in the table of network requests is not displayed, choose the table header > **Size**.</span></span>  

<span data-ttu-id="32210-234">[各 **サイズ] セル** には、2 つの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="32210-234">Each **Size** cell shows two values.</span></span>  <span data-ttu-id="32210-235">一番上の値は、ダウンロードしたリソースのサイズです。</span><span class="sxs-lookup"><span data-stu-id="32210-235">The top value is the size of the downloaded resource.</span></span>  
<span data-ttu-id="32210-236">一番下の値は、圧縮されていないリソースのサイズです。</span><span class="sxs-lookup"><span data-stu-id="32210-236">The bottom value is the size of the uncompressed resource.</span></span>  <span data-ttu-id="32210-237">2 つの値が同じ場合は、ネットワークを使用して送信するときにリソースが圧縮されません。</span><span class="sxs-lookup"><span data-stu-id="32210-237">If the two values are the same, then the resource is not being compressed when it is sent over the network.</span></span>  <span data-ttu-id="32210-238">たとえば、前の図では、上と下の値は `bundle.js` 、 `1.2 MB` と です `1.2 MB` 。</span><span class="sxs-lookup"><span data-stu-id="32210-238">For example, in the previous figure, the top and bottom values for `bundle.js` are `1.2 MB` and `1.2 MB`.</span></span>  

<span data-ttu-id="32210-239">リソースの HTTP ヘッダーを検査して圧縮を確認します。</span><span class="sxs-lookup"><span data-stu-id="32210-239">Check for compression by inspecting the HTTP headers of a resource:</span></span>  

1.  <span data-ttu-id="32210-240">を選択します `bundle.js` 。</span><span class="sxs-lookup"><span data-stu-id="32210-240">Choose `bundle.js`.</span></span>  
1.  <span data-ttu-id="32210-241">[ヘッダー] **パネルを選択** します。</span><span class="sxs-lookup"><span data-stu-id="32210-241">Choose the **Headers** panel.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png" alt-text="[ヘッダー] パネル" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png":::
       <span data-ttu-id="32210-243">[ **ヘッダー]** パネル</span><span class="sxs-lookup"><span data-stu-id="32210-243">The **Headers** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="32210-244">[応答ヘッダー **] セクションで** ヘッダーを `content-encoding` 検索します。</span><span class="sxs-lookup"><span data-stu-id="32210-244">Search the **Response Headers** section for a `content-encoding` header.</span></span>  <span data-ttu-id="32210-245">見出 `content-encoding` しは表示されません。つまり、圧縮 `bundle.js` されません。</span><span class="sxs-lookup"><span data-stu-id="32210-245">A `content-encoding` heading is not displayed, meaning that `bundle.js` was not compressed.</span></span>  <span data-ttu-id="32210-246">リソースが圧縮されている場合、通常、このヘッダーは `gzip` 、 、 または `deflate` に設定されます `br` 。</span><span class="sxs-lookup"><span data-stu-id="32210-246">When a resource is compressed, this header is usually set to `gzip`, `deflate`, or `br`.</span></span>  <span data-ttu-id="32210-247">値の説明については、「ディレクティブ」 [に移動します][MDNContentEncodingDirectives]。</span><span class="sxs-lookup"><span data-stu-id="32210-247">For an explanation of the values, navigate to [Directives][MDNContentEncodingDirectives].</span></span>  

<span data-ttu-id="32210-248">説明で十分です。</span><span class="sxs-lookup"><span data-stu-id="32210-248">Enough with the explanations.</span></span>  <span data-ttu-id="32210-249">いくつかの変更を加える時間。</span><span class="sxs-lookup"><span data-stu-id="32210-249">Time to make some changes.</span></span>  <span data-ttu-id="32210-250">次の 2 行のコードを追加して、テキスト圧縮を有効にします。</span><span class="sxs-lookup"><span data-stu-id="32210-250">Enable text compression by adding a couple of lines of code:</span></span>  

1.  <span data-ttu-id="32210-251">[エディター] タブで、[編集]\*\*をserver.js。 \*\*</span><span class="sxs-lookup"><span data-stu-id="32210-251">In the editor tab, choose **server.js**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js.msft.png" alt-text="編集server.js" lightbox="../media/speed-glitch-tony-remix-server-js.msft.png":::
       <span data-ttu-id="32210-253">Edit</span><span class="sxs-lookup"><span data-stu-id="32210-253">Edit</span></span> `server.js`  
    :::image-end:::  
    
1.  <span data-ttu-id="32210-254">次のコードを次のコード\*\*にserver.js。 \*\*</span><span class="sxs-lookup"><span data-stu-id="32210-254">Add the following code to **server.js**.</span></span>  <span data-ttu-id="32210-255">前に置く必要 `app.use(compression())` があります `app.use(express.static('build'))` 。</span><span class="sxs-lookup"><span data-stu-id="32210-255">Make sure to put `app.use(compression())` before `app.use(express.static('build'))`.</span></span>  

    ```javascript
    const express = require('express');
    const app = express();
    const fs = require('fs');
    const compression = require('compression');

    app.use(compression());
    app.use(express.static('build'));
    
    const listener = app.listen(process.env.PORT || 1234, function () {
        console.log(`Listening on port ${listener.address().port}`);
    });
    ```  
    
    > [!NOTE]
    > <span data-ttu-id="32210-256">通常は、パッケージをインストールする必要 `compression` がありますが、 `npm i -S compression` これは既に行っています。</span><span class="sxs-lookup"><span data-stu-id="32210-256">Usually, you have to install the `compression` package via something like `npm i -S compression`, but this has already been done for you.</span></span>  
    
1.  <span data-ttu-id="32210-257">Glitch がサイトの新しいビルドを展開するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="32210-257">Wait for Glitch to deploy the new build of the site.</span></span>  <span data-ttu-id="32210-258">[ツール] の横にある **アニメーションは** 、サイトが再構築され、再展開されるという意味です。</span><span class="sxs-lookup"><span data-stu-id="32210-258">The fancy animation next to **Tools** means that the site is getting rebuilt and redeployed.</span></span>  <span data-ttu-id="32210-259">ツールの横にあるアニメーションが消え去った場合、変更 **の準備** ができました。</span><span class="sxs-lookup"><span data-stu-id="32210-259">The change is ready when the animation next to **Tools** goes away.</span></span>  <span data-ttu-id="32210-260">[表示 **] を** 選択し、[ **新しいウィンドウ] を再度選択** します。</span><span class="sxs-lookup"><span data-stu-id="32210-260">Choose **Show** and choose **In a New Window** again.</span></span>  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js-edited.msft.png" alt-text="The animation that indicates that the site is getting built" lightbox="../media/speed-glitch-tony-remix-server-js-edited.msft.png":::
       The animation that indicates that the site is getting built  
    :::image-end:::  
    -->  
    
<span data-ttu-id="32210-261">前に説明したワークフローを使用して、圧縮が機能しているのを手動で確認します。</span><span class="sxs-lookup"><span data-stu-id="32210-261">Use the workflows that you learned earlier to manually check that the compression is working:</span></span>  

1.  <span data-ttu-id="32210-262">デモ タブに戻り、ページを更新します。</span><span class="sxs-lookup"><span data-stu-id="32210-262">Go back to the demo tab and refresh the page.</span></span>  <span data-ttu-id="32210-263">[ **サイズ] 列** には、次のようなテキスト リソースに 2 つの異なる値が表示されます `bundle.js` 。</span><span class="sxs-lookup"><span data-stu-id="32210-263">The **Size** column should now show 2 different values for text resources like `bundle.js`.</span></span>  <span data-ttu-id="32210-264">次の図では、for の上の値は、ネットワークを使用して送信されたファイルのサイズで、最下位の値は圧縮されていないファイル サイズ `256 KB` `bundle.js` `1.2 MB` です。</span><span class="sxs-lookup"><span data-stu-id="32210-264">In the figure after the following, the top value of `256 KB` for `bundle.js` is the size of the file that was sent over the network, and the bottom value of `1.2 MB` is the uncompressed file size.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-main.msft.png" alt-text="[サイズ] 列に、テキスト リソースに 2 つの異なる値が表示される" lightbox="../media/speed-glitch-tony-remix-network-main.msft.png":::
       <span data-ttu-id="32210-266">[ **サイズ] 列** に、テキスト リソースに 2 つの異なる値が表示される</span><span class="sxs-lookup"><span data-stu-id="32210-266">The **Size** column now shows 2 different values for text resources</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="32210-267">[ **応答ヘッダー]** セクションに `bundle.js` ヘッダーが含 `content-encoding: gzip` まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="32210-267">The **Response Headers** section for `bundle.js` should now include a `content-encoding: gzip` header.</span></span>
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png" alt-text="[応答ヘッダー] セクションにコンテンツ エンコード ヘッダーが含まれる" lightbox="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png":::
       <span data-ttu-id="32210-269">[ **応答ヘッダー]** セクションにコンテンツ エンコード ヘッダーが含まれる</span><span class="sxs-lookup"><span data-stu-id="32210-269">The **Response Headers** section now contains a content-encoding header</span></span>  
    :::image-end:::  
    
<span data-ttu-id="32210-270">ページを再度監査して、ページの読み込みパフォーマンスに与える影響の種類を測定します。</span><span class="sxs-lookup"><span data-stu-id="32210-270">Audit the page again to measure what kind of impact text compression has on the load performance of the page:</span></span>  

1.  <span data-ttu-id="32210-271">[監査] **ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="32210-271">Choose the **Audits** tool.</span></span>  
1.  <span data-ttu-id="32210-272">[ **監査を実行する** ]を選択します ![ ([監査を実行 ](../media/perform-icon.msft.png) する]\)。</span><span class="sxs-lookup"><span data-stu-id="32210-272">Choose **Perform an audit** \(![Perform an audit](../media/perform-icon.msft.png)\).</span></span>  
1.  <span data-ttu-id="32210-273">設定は以前と同じままにします。</span><span class="sxs-lookup"><span data-stu-id="32210-273">Leave the settings the same as before.</span></span>  
1.  <span data-ttu-id="32210-274">[監査 **の実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="32210-274">Choose **Run audit**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png" alt-text="テキスト圧縮を有効にした後の監査レポート" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png":::
       <span data-ttu-id="32210-276">テキスト圧縮を有効にした後の監査レポート</span><span class="sxs-lookup"><span data-stu-id="32210-276">An Audits report after enabling text compression</span></span>  
    :::image-end:::  
    
<!--  Woohoo!  That looks like progress.  -->  <span data-ttu-id="32210-277">全体的なパフォーマンス スコアが上がっている必要があります。つまり、サイトの速度が速くなります。</span><span class="sxs-lookup"><span data-stu-id="32210-277">Your overall performance score should have increased, meaning that the site is getting faster.</span></span>  

#### <a name="text-compression-in-the-real-world"></a><span data-ttu-id="32210-278">現実世界でのテキスト圧縮</span><span class="sxs-lookup"><span data-stu-id="32210-278">Text compression in the real world</span></span>  

<span data-ttu-id="32210-279">ほとんどのサーバーには、圧縮を有効にするための簡単な修正が実際に含まれています。</span><span class="sxs-lookup"><span data-stu-id="32210-279">Most servers really do have simple fixes like this for enabling compression!</span></span>  <span data-ttu-id="32210-280">テキストの圧縮に使用するサーバーを構成する方法を検索します。</span><span class="sxs-lookup"><span data-stu-id="32210-280">Just do a search on how to configure whatever server you use to compress text.</span></span>  

### <a name="resize-images"></a><span data-ttu-id="32210-281">画像のサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="32210-281">Resize images</span></span>  

<span data-ttu-id="32210-282">レポートは、膨大なネットワーク ペイロードを避けることは、ページのパフォーマンスを向上させる最も重要な機会の 1 つを示しています。</span><span class="sxs-lookup"><span data-stu-id="32210-282">Your report indicates that avoiding enormous network payloads is one of the top opportunities for improving the performance of the page.</span></span>  <span data-ttu-id="32210-283">イメージのサイズを変更すると、ネットワーク ペイロードのサイズを小さくすることができます。</span><span class="sxs-lookup"><span data-stu-id="32210-283">Resizing images helps reduce the size of the network payload.</span></span>  <span data-ttu-id="32210-284">ユーザーが 500 ピクセル幅のモバイル デバイス画面で画像を表示している場合、1500 ピクセル幅の画像を送信しても意味はありません。</span><span class="sxs-lookup"><span data-stu-id="32210-284">If your user is viewing your images on a mobile device screen that is 500-pixels-wide, there is really no point in sending a 1500-pixel-wide image.</span></span>  <span data-ttu-id="32210-285">理想的には、最大で 500 ピクセル幅の画像を送信します。</span><span class="sxs-lookup"><span data-stu-id="32210-285">Ideally, you send a 500-pixel-wide image, at most.</span></span>  

1.  <span data-ttu-id="32210-286">レポートで、[巨大な **ネットワーク ペイロードを避** ける] を選択して、サイズを変更する画像を表示します。</span><span class="sxs-lookup"><span data-stu-id="32210-286">In your report, choose **Avoid enormous network payloads** to display which images should be resized.</span></span>  <span data-ttu-id="32210-287">jpg ファイルの 2 つが 2000 KB を超え、必要以上に大きいように見えます。</span><span class="sxs-lookup"><span data-stu-id="32210-287">It looks like 2 of the jpg files are over 2000 KB, which is bigger than necessary.</span></span>  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png" alt-text="Details about the properly size images opportunity" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png":::
       Details about the properly size images opportunity  
    :::image-end:::  
    -->
    
1.  <span data-ttu-id="32210-288">[エディター] タブに戻り、を開きます `src/model.js` 。</span><span class="sxs-lookup"><span data-stu-id="32210-288">Back in the editor tab, open `src/model.js`.</span></span>  
1.  <span data-ttu-id="32210-289">に `const dir = 'big'` 置き換える `const dir = 'small'` 。</span><span class="sxs-lookup"><span data-stu-id="32210-289">Replace `const dir = 'big'` with `const dir = 'small'`.</span></span>  <span data-ttu-id="32210-290">このディレクトリには、サイズ変更された同じイメージのコピーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="32210-290">This directory contains copies of the same images which have been resized.</span></span>  
1.  <span data-ttu-id="32210-291">ページを再度監査して、変更が読み込みパフォーマンスに与える影響を表示します。</span><span class="sxs-lookup"><span data-stu-id="32210-291">Audit the page again to display how the change affects load performance.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-compression-small-images-audits-performance.msft.png" alt-text="イメージのサイズ変更後の監査レポート" lightbox="../media/speed-glitch-compression-small-images-audits-performance.msft.png":::
       <span data-ttu-id="32210-293">イメージのサイズ変更後の監査レポート</span><span class="sxs-lookup"><span data-stu-id="32210-293">An Audits report after resizing images</span></span>  
    :::image-end:::  
    
<span data-ttu-id="32210-294">この変更は、全体的なパフォーマンス スコアにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="32210-294">The change displays only has a minor affect on the overall performance score.</span></span>  <span data-ttu-id="32210-295">ただし、スコアが明確に表示されない点の 1 つは、ユーザーを保存しているネットワーク データの量です。</span><span class="sxs-lookup"><span data-stu-id="32210-295">However, one thing that the score does not show clearly is how much network data you are saving your users.</span></span>  <span data-ttu-id="32210-296">古い写真の合計サイズは約 5.3 メガバイトですが、現在は約 0.18 メガバイトです。</span><span class="sxs-lookup"><span data-stu-id="32210-296">The total size of the old photos was around 5.3 megabytes, whereas now it is only about 0.18 megabytes.</span></span>  

#### <a name="resizing-images-in-the-real-world"></a><span data-ttu-id="32210-297">実世界の画像のサイズ変更</span><span class="sxs-lookup"><span data-stu-id="32210-297">Resizing images in the real world</span></span>  

<span data-ttu-id="32210-298">小さなアプリの場合は、このような 1 回のサイズ変更で十分な場合があります。</span><span class="sxs-lookup"><span data-stu-id="32210-298">For a small app, doing a one-off resize like this may be good enough.</span></span>  <span data-ttu-id="32210-299">しかし、大規模なアプリの場合、これは明らかにスケーラブルではありません。</span><span class="sxs-lookup"><span data-stu-id="32210-299">But for a large app, this obviously is not scalable.</span></span>  <span data-ttu-id="32210-300">大規模なアプリで画像を管理するための戦略を次に示します。</span><span class="sxs-lookup"><span data-stu-id="32210-300">Here are some strategies for managing images in large apps:</span></span>  

*   <span data-ttu-id="32210-301">ビルド プロセス中にイメージのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="32210-301">Resize images during your build process.</span></span>  
*   <span data-ttu-id="32210-302">ビルド プロセス中に各イメージの複数のサイズを作成し、コード `srcset` で使用します。</span><span class="sxs-lookup"><span data-stu-id="32210-302">Create multiple sizes of each image during the build process and then use `srcset` in your code.</span></span>  <span data-ttu-id="32210-303">実行時に、ブラウザーはデバイスに最適なサイズを選択します。</span><span class="sxs-lookup"><span data-stu-id="32210-303">At runtime, the browser takes care of choosing which size is best for the device.</span></span>  
    <!--Navigate to [Relative-sized images][relative].  -->
    
<!--[relative]: /web/fundamentals/design-and-ux/responsive/images#relative_sized_images  -->  

*   <span data-ttu-id="32210-304">要求時にCDNサイズを動的に変更できるイメージ コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="32210-304">Use an image CDN that lets you dynamically resize an image when you request it.</span></span>  
*   <span data-ttu-id="32210-305">少なくとも、各画像を最適化します。</span><span class="sxs-lookup"><span data-stu-id="32210-305">At the very least, optimize each image.</span></span>  <span data-ttu-id="32210-306">これにより、大きな節約が生まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="32210-306">This may create huge savings.</span></span>  
  <span data-ttu-id="32210-307">最適化は、イメージ ファイルのサイズを小さくする特別なプログラムを使用してイメージを実行する場合です。</span><span class="sxs-lookup"><span data-stu-id="32210-307">Optimization is when you run an image through a special program that reduces the size of the image file.</span></span>  <span data-ttu-id="32210-308">その他のヒントについては、「Essential [Image Optimization」に移動します][EssentialImageOptimization]。</span><span class="sxs-lookup"><span data-stu-id="32210-308">For more tips, navigate to [Essential Image Optimization][EssentialImageOptimization].</span></span>  
    
### <a name="eliminate-render-blocking-resources"></a><span data-ttu-id="32210-309">レンダリングブロックリソースを排除する</span><span class="sxs-lookup"><span data-stu-id="32210-309">Eliminate render-blocking resources</span></span>  

<span data-ttu-id="32210-310">最新のレポートでは、レンダリング ブロック リソースを排除する機会が最大の機会です。</span><span class="sxs-lookup"><span data-stu-id="32210-310">Your latest report says that eliminating render-blocking resources is now the biggest opportunity.</span></span>  

<span data-ttu-id="32210-311">レンダリング ブロック リソースは、ブラウザーがページを表示する前にダウンロード、解析、および実行する必要がある外部 JavaScript または CSS ファイルです。</span><span class="sxs-lookup"><span data-stu-id="32210-311">A render-blocking resource is an external JavaScript or CSS file that the browser must download, parse, and run before it displays the page.</span></span>  <span data-ttu-id="32210-312">目標は、ページを適切に表示するために必要なコア CSS と JavaScript コードのみを実行します。</span><span class="sxs-lookup"><span data-stu-id="32210-312">The goal is to only run the core CSS and JavaScript code that is required to display the page properly.</span></span>  

<span data-ttu-id="32210-313">最初のタスクは、ページの読み込み時に実行する必要はないコードを見つける方法です。</span><span class="sxs-lookup"><span data-stu-id="32210-313">The first task, then, is to find code that you do not need to run on page load.</span></span>  

1.  <span data-ttu-id="32210-314">[ **レンダリング ブロック リソースを削除する] を選択** して、ブロックしているリソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="32210-314">Choose **Eliminate render-blocking resources** to display the resources that are blocking:</span></span>  
    `lodash.js` <span data-ttu-id="32210-315">と `jquery.js` .</span><span class="sxs-lookup"><span data-stu-id="32210-315">and `jquery.js`.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png" alt-text="レンダリングブロックリソースの排除機会の詳細" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png":::
       <span data-ttu-id="32210-317">レンダリングブロックリソースの**排除機会の詳細**</span><span class="sxs-lookup"><span data-stu-id="32210-317">More information about the **Eliminate render-blocking resources** opportunity</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="32210-318">`Control` + `Shift` + `P` \(Windows、Linux\) または `Command` + `Shift` + `P` \(macOS\) `Coverage` \*\*\*\* を選択してコマンド メニューを開き、入力を開始し、[カバレッジの表示] を選択します。</span><span class="sxs-lookup"><span data-stu-id="32210-318">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, start typing `Coverage`, and then choose **Show Coverage**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png" alt-text="[監査] パネルから [コマンド メニュー] を開きます。" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png":::
       <span data-ttu-id="32210-320">[監査] パネルから [コマンド メニュー **] を開** きます。</span><span class="sxs-lookup"><span data-stu-id="32210-320">Open the Command Menu from the **Audits** panel</span></span>  
    :::image-end:::  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png" alt-text="カバレッジ ツール" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png":::
       <span data-ttu-id="32210-322">カバレッジ**ツール**</span><span class="sxs-lookup"><span data-stu-id="32210-322">The **Coverage** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="32210-323">[ **更新** \( ![ Refresh ](../media/reload-icon.msft.png) \] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="32210-323">Choose **Refresh** \(![Refresh](../media/reload-icon.msft.png)\).</span></span>  <span data-ttu-id="32210-324">[ **カバレッジ** ] ツールは、ページの読み込み中に実行されるコードの量の `bundle.js` `jquery.js` `lodash.js` 概要を示します。</span><span class="sxs-lookup"><span data-stu-id="32210-324">The **Coverage** tool provides an overview of how much of the code in `bundle.js`, `jquery.js`, and `lodash.js` runs while the page loads.</span></span>  <span data-ttu-id="32210-325">次の図では、jQuery ファイルと Lodash ファイルの約 76% と 30% がそれぞれ使用されません。</span><span class="sxs-lookup"><span data-stu-id="32210-325">In the figure after the following, about 76% and 30% of the jQuery and Lodash files are not used, respectively.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png" alt-text="カバレッジ レポート" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png":::
       <span data-ttu-id="32210-327">カバレッジ レポート</span><span class="sxs-lookup"><span data-stu-id="32210-327">The Coverage report</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="32210-328">行を選択 `jquery.js` します。</span><span class="sxs-lookup"><span data-stu-id="32210-328">Choose the `jquery.js` row.</span></span>  <span data-ttu-id="32210-329">DevTools は、[ソース] ツールで **ファイルを開** きます。</span><span class="sxs-lookup"><span data-stu-id="32210-329">DevTools opens the file in the **Sources** tool.</span></span>  <span data-ttu-id="32210-330">コード行が実行された場合、その横に青いバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="32210-330">If a line of code ran, a blue bar appears next to it.</span></span>  <span data-ttu-id="32210-331">赤いバーは、コード行が実行されていないという意味で、Web ページの読み込み時には必ず必要とされません。</span><span class="sxs-lookup"><span data-stu-id="32210-331">A red bar means the line of code was not run, and is definitely not needed on load of the webpage.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png" alt-text="ソース ツールでの jQuery ファイルの表示" lightbox="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png":::
       <span data-ttu-id="32210-333">ソース ツールでの jQuery ファイル **の** 表示</span><span class="sxs-lookup"><span data-stu-id="32210-333">Viewing the jQuery file in the **Sources** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="32210-334">jQuery コードをスクロールします。</span><span class="sxs-lookup"><span data-stu-id="32210-334">Scroll through the jQuery code.</span></span>  <span data-ttu-id="32210-335">実行される行の一部は、実際にはコメントにすら見当たらされません。</span><span class="sxs-lookup"><span data-stu-id="32210-335">Some of the lines that run are actually just comments.</span></span>  <span data-ttu-id="32210-336">コメントを削除し、ファイルのサイズを小さくするには、ミニフィアー アプリまたはスクリプトを使用してコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="32210-336">To strip comments and reduce the size of the file, run the code through a minifier app or script.</span></span>  

<span data-ttu-id="32210-337">つまり、独自のコードを操作する場合、カバレッジ ツール\*\*\*\* を使用すると、コードを 1 行 1 行で分析し、ページ読み込みに必要なコードのみを出荷できます。</span><span class="sxs-lookup"><span data-stu-id="32210-337">In short, when you are working with your own code, the **Coverage** tool helps you analyze your code, line-by-line, and only ship the code that is needed for page load.</span></span>  

<span data-ttu-id="32210-338">ページを `jquery.js` 読 `lodash.js` み込むにはファイルも必要ですか?</span><span class="sxs-lookup"><span data-stu-id="32210-338">Are the `jquery.js` and `lodash.js` files even needed to load the page?</span></span>  <span data-ttu-id="32210-339">要求 **ブロック ツールは** 、リソースが利用できない場合の動作を表示します。</span><span class="sxs-lookup"><span data-stu-id="32210-339">The **Request blocking** tool displays what happens when resources are not available.</span></span>  

1.  <span data-ttu-id="32210-340">[ネットワーク] **ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="32210-340">Choose the **Network** tool.</span></span>  
1.  <span data-ttu-id="32210-341">`Control` + `Shift` + `P` \(Windows Linux\) または \(macOS\) を選択して、コマンド `Command` + `Shift` + `P` メニューを再度開きます。</span><span class="sxs-lookup"><span data-stu-id="32210-341">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu again.</span></span>  
1.  <span data-ttu-id="32210-342">入力を開始し `blocking` 、[要求ブロック **の表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="32210-342">Start typing `blocking` and then choose **Show Request Blocking**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png" alt-text="要求ブロック ツール" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png":::
       <span data-ttu-id="32210-344">要求 **ブロック** ツール</span><span class="sxs-lookup"><span data-stu-id="32210-344">The **Request blocking** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="32210-345">[ **パターンの追加** \( ![ Add Pattern ](../media/add-pattern-icon.msft.png) \), `/libs/*` type, and select to `Enter` confirm.</span><span class="sxs-lookup"><span data-stu-id="32210-345">Choose **Add Pattern** \(![Add Pattern](../media/add-pattern-icon.msft.png)\), type `/libs/*`, and then select `Enter` to confirm.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png" alt-text="libs ディレクトリへの要求をブロックするパターンを追加する" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png":::
       <span data-ttu-id="32210-347">ディレクトリへの要求をブロックするパターンを追加 `libs` する</span><span class="sxs-lookup"><span data-stu-id="32210-347">Add a pattern to block any request to the `libs` directory</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="32210-348">ページを最新の情報に更新してください。</span><span class="sxs-lookup"><span data-stu-id="32210-348">Refresh the page.</span></span>  <span data-ttu-id="32210-349">jQuery 要求と Lodash 要求は赤で、要求がブロックされました。</span><span class="sxs-lookup"><span data-stu-id="32210-349">The jQuery and Lodash requests are red, meaning that the requests were blocked.</span></span>   <span data-ttu-id="32210-350">ページは読み込み、対話型なので、これらのリソースは一切必要とされていないように見えます。</span><span class="sxs-lookup"><span data-stu-id="32210-350">The page still loads and is interactive, so it looks like these resources are not needed whatsoever!</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png" alt-text="[ネットワーク] パネルは、要求がブロックされたと表示されます。" lightbox="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png":::
       <span data-ttu-id="32210-352">ネットワーク **ツール** は、要求がブロックされたと表示されます。</span><span class="sxs-lookup"><span data-stu-id="32210-352">The **Network** tool shows that the requests have been blocked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="32210-353">[ **すべてのパターンを削除する** ] \( ![ Remove all patterns \) を選択して、ブロック ](../media/remove-icon.msft.png) パターンを `/libs/*` 削除します。</span><span class="sxs-lookup"><span data-stu-id="32210-353">Choose **Remove all patterns** \(![Remove all patterns](../media/remove-icon.msft.png)\) to delete the `/libs/*` blocking pattern.</span></span>  
    
<span data-ttu-id="32210-354">一般に、[ **要求のブロック** ] ツールは、特定のリソースが使用できない場合のページの動作をシミュレートする場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="32210-354">In general, the **Request blocking** tool is useful for simulating how your page behaves when any given resource is not available.</span></span>  

<span data-ttu-id="32210-355">次に、コードからこれらのファイルへの参照を削除し、ページを再度監査します。</span><span class="sxs-lookup"><span data-stu-id="32210-355">Now, remove the references to these files from the code and audit the page again:</span></span>  

1.  <span data-ttu-id="32210-356">[エディター] タブに戻り、を開きます `template.html` 。</span><span class="sxs-lookup"><span data-stu-id="32210-356">Back in the editor tab, open `template.html`.</span></span>  
1.  <span data-ttu-id="32210-357">`<script src="/libs/lodash.js">` と `<script src="/libs/jquery.js"></script>` を削除します。</span><span class="sxs-lookup"><span data-stu-id="32210-357">Delete `<script src="/libs/lodash.js">` and `<script src="/libs/jquery.js"></script>`.</span></span>  
1.  <span data-ttu-id="32210-358">サイトが再ビルドして再展開するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="32210-358">Wait for the site to re-build and re-deploy.</span></span>  
1.  <span data-ttu-id="32210-359">[監査] ツールからページ **を再度監査** します。</span><span class="sxs-lookup"><span data-stu-id="32210-359">Audit the page again from the **Audits** tool.</span></span>  <span data-ttu-id="32210-360">全体的なスコアが再び向上している必要があります。</span><span class="sxs-lookup"><span data-stu-id="32210-360">Your overall score should have improved again.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png" alt-text="レンダリング ブロック リソースを削除した後の監査レポート" lightbox="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png":::
       <span data-ttu-id="32210-362">レンダリング **ブロック リソースを** 削除した後の監査レポート</span><span class="sxs-lookup"><span data-stu-id="32210-362">An **Audits** report after removing the render-blocking resources</span></span>  
    :::image-end:::  
    
#### <a name="optimizing-the-critical-rendering-path-in-the-real-world"></a><span data-ttu-id="32210-363">現実世界でのクリティカル レンダリング パスの最適化</span><span class="sxs-lookup"><span data-stu-id="32210-363">Optimizing the Critical Rendering Path in the real-world</span></span>  

<span data-ttu-id="32210-364">クリティカル **レンダリング パスは** 、ページを読み込む必要があるコードを参照します。</span><span class="sxs-lookup"><span data-stu-id="32210-364">The **Critical Rendering Path** refers to the code that you need to load a page.</span></span>  <span data-ttu-id="32210-365">一般に、ページの読み込み中に重要なコードのみを出荷し、それ以外のコードを遅延読み込みすることで、ページの読み込みを高速化します。</span><span class="sxs-lookup"><span data-stu-id="32210-365">In general, speed up page load by only shipping critical code during the page load, and then lazy-loading everything else.</span></span>  

<!--[CRP]: /web/fundamentals/performance/critical-rendering-path/  -->  

*   <span data-ttu-id="32210-366">完全に削除できるスクリプトを見つけ出す可能性は低いですが、ページの読み込み中に要求する必要が生じ、代わりに非同期的に要求されるスクリプトが多数見つかるはずです。</span><span class="sxs-lookup"><span data-stu-id="32210-366">It is unlikely that you are able to find scripts that you are able to remove outright, but you may find many scripts that you do not need to request during the page load, and instead may be requested asynchronously.</span></span>  <!--Navigate to [Using async or defer][async].  -->  
*   <span data-ttu-id="32210-367">フレームワークを使用している場合は、実稼働モードを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="32210-367">If you are using a framework, check if it has a production mode.</span></span>  <span data-ttu-id="32210-368">このモードでは、重要なレンダリングを[][WebpackTreeShaking]ブロックしている不要なコードを排除するために、ツリーの揺れなどの機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="32210-368">This mode may use a feature such as [tree shaking][WebpackTreeShaking] in order to eliminate unnecessary code that is blocking the critical render.</span></span>  
    
<!--[async]: /web/fundamentals/performance/optimizing-content-efficiency/loading-third-party-javascript/#use_async_or_defer  -->  

### <a name="do-less-main-thread-work"></a><span data-ttu-id="32210-369">メイン スレッドの作業を減らします</span><span class="sxs-lookup"><span data-stu-id="32210-369">Do less main thread work</span></span>  

<span data-ttu-id="32210-370">最新のレポートには、[機会] セクションにわずかな節約が表示されますが、[診断] セクションを見下ろした場合、最大のボトルネックはメイン スレッド アクティビティが多すぎるように見えます。</span><span class="sxs-lookup"><span data-stu-id="32210-370">Your latest report shows some minor potential savings in the Opportunities section, but if you look down in the Diagnostics section, it looks like the biggest bottleneck is too much main thread activity.</span></span>  

<span data-ttu-id="32210-371">メイン スレッドは、HTML、CSS、JavaScript の解析と実行など、ページを表示するために必要なほとんどの作業をブラウザーが実行する場所です。</span><span class="sxs-lookup"><span data-stu-id="32210-371">The main thread is where the browser does most of the work needed to display a page, such as parsing and running HTML, CSS, and JavaScript.</span></span>  

<span data-ttu-id="32210-372">目標は、[パフォーマンス] パネルを使用して、ページの読み込み中にメイン スレッドが実行している作業を分析し、不要な作業を延期または削除する方法を見つけ出すことです。</span><span class="sxs-lookup"><span data-stu-id="32210-372">The goal is to use the Performance panel to analyze what work the main thread is doing while the page loads, and find ways to defer or remove unnecessary work.</span></span>  

1.  <span data-ttu-id="32210-373">[パフォーマンス] **ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="32210-373">Choose the **Performance** tool.</span></span>  
1.  <span data-ttu-id="32210-374">[**キャプチャ] 設定**\( ![ Capture 設定 ](../media/capture-icon.msft.png) \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="32210-374">Choose **Capture Settings** \(![Capture Settings](../media/capture-icon.msft.png)\).</span></span>  
1.  <span data-ttu-id="32210-375">[ **ネットワーク] を** **[低速 3G]** に設定し **、CPU** を **6 倍の低速に設定します**。</span><span class="sxs-lookup"><span data-stu-id="32210-375">Set **Network** to **Slow 3G** and **CPU** to **6x slowdown**.</span></span>  <span data-ttu-id="32210-376">モバイル デバイスは通常、ラップトップやデスクトップよりもハードウェアの制約が多いので、これらの設定を使用すると、より強力なデバイスを使用している場合と同様に、ページの読み込みも発生します。</span><span class="sxs-lookup"><span data-stu-id="32210-376">Mobile devices typically have more hardware constraints than laptops or desktops, so these settings let you experience the page load as if you were using a less powerful device.</span></span>  
1.  <span data-ttu-id="32210-377">[ **更新** \( ![ Refresh ](../media/reload-icon.msft.png) \] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="32210-377">Choose **Refresh** \(![Refresh](../media/reload-icon.msft.png)\).</span></span>  <span data-ttu-id="32210-378">DevTools はページを更新し、ページを読み込むのに実行されたすべての作業の視覚化を生成します。</span><span class="sxs-lookup"><span data-stu-id="32210-378">DevTools refreshes the page and then produces a visualization of all the work performed in order to load the page.</span></span>  <span data-ttu-id="32210-379">この視覚化は、トレースと呼 **ばれます**。</span><span class="sxs-lookup"><span data-stu-id="32210-379">This visualization is referred to as the **trace**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png" alt-text="ページ読み込み時のパフォーマンス ツールのトレース" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png":::
       <span data-ttu-id="32210-381">ページ **読み** 込み時のパフォーマンス ツールのトレース</span><span class="sxs-lookup"><span data-stu-id="32210-381">The **Performance** tool trace of the page load</span></span>  
    :::image-end:::  
    
<span data-ttu-id="32210-382">トレースは、左から右にアクティビティを時系列的に表示します。</span><span class="sxs-lookup"><span data-stu-id="32210-382">The trace shows activity chronologically, from left to right.</span></span>  <span data-ttu-id="32210-383">上部の FPS、CPU、および NET グラフでは、1 秒あたりのフレーム数、CPU アクティビティ、およびネットワーク アクティビティの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="32210-383">The FPS, CPU, and NET charts at the top give you an overview of frames per second, CPU activity, and network activity.</span></span>  <span data-ttu-id="32210-384">次の図の後の図で強調表示されている黄色のブロックは、CPU がスクリプトアクティビティで完全にビジー状態でした。</span><span class="sxs-lookup"><span data-stu-id="32210-384">The block of yellow highlighted in the figure after the next, the CPU was completely busy with scripting activity.</span></span>  <span data-ttu-id="32210-385">これは、JavaScript の作業を減らしてページの読み込み速度を上げ得る手がかりです。</span><span class="sxs-lookup"><span data-stu-id="32210-385">This is a clue that you may be able to speed up page load by doing less JavaScript work.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png" alt-text="トレースの [概要] セクション" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png":::
   <span data-ttu-id="32210-387">トレースの [概要] セクション</span><span class="sxs-lookup"><span data-stu-id="32210-387">The Overview section of the trace</span></span>  
:::image-end:::  

<span data-ttu-id="32210-388">トレースを調査して、JavaScript の作業を少なくする方法を探します。</span><span class="sxs-lookup"><span data-stu-id="32210-388">Investigate the trace to find ways to do less JavaScript work:</span></span>  

1.  <span data-ttu-id="32210-389">[タイミング **] セクションを選択** して展開します。</span><span class="sxs-lookup"><span data-stu-id="32210-389">Choose the **Timings** section to expand it.</span></span>  <span data-ttu-id="32210-390">React から多くのタイミング対策がある可能性があるという[][MDNUserTimingApi]事実に基づいて、Tony のアプリが React の開発モードを使用しているようです。</span><span class="sxs-lookup"><span data-stu-id="32210-390">Based on the fact that there may be a bunch of [Timings][MDNUserTimingApi] measures from React, it seems like Tony's app is using the development mode of React.</span></span>  <span data-ttu-id="32210-391">アプリケーションの実稼働モードに切り替Reactパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="32210-391">Switching to the production mode of React may yield some easy performance wins.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png" alt-text="[タイミング] セクション" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png":::
       <span data-ttu-id="32210-393">[ **タイミング]** セクション</span><span class="sxs-lookup"><span data-stu-id="32210-393">The **Timings** section</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="32210-394">もう **一度 [タイミング]** を選択して、そのセクションを折りたたみます。</span><span class="sxs-lookup"><span data-stu-id="32210-394">Choose **Timings** again to collapse that section.</span></span>  
1.  <span data-ttu-id="32210-395">[メイン] **セクションを参照** します。</span><span class="sxs-lookup"><span data-stu-id="32210-395">Browse the **Main** section.</span></span>  <span data-ttu-id="32210-396">このセクションでは、メイン スレッドアクティビティの時系列ログを左から右に示します。</span><span class="sxs-lookup"><span data-stu-id="32210-396">This section shows a chronological log of main thread activity, from left to right.</span></span>  <span data-ttu-id="32210-397">y 軸 (上から下) は、イベントが発生した理由を示します。</span><span class="sxs-lookup"><span data-stu-id="32210-397">The y-axis (top to bottom) shows why events occurred.</span></span>  <span data-ttu-id="32210-398">たとえば、次の後の図では、イベントによって関数が実行され、その結果、実行が発生し、実行が引き起こ `Evaluate Script` `(anonymous)` `(anonymous)` `__webpack__require__` されました。</span><span class="sxs-lookup"><span data-stu-id="32210-398">For example, in the figyre after the following, the `Evaluate Script` event caused the `(anonymous)` function to run, which caused `(anonymous)` to run, which caused `__webpack__require__` to run, and so on.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png" alt-text="[メイン] セクション" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png":::
       <span data-ttu-id="32210-400">[ **メイン]** セクション</span><span class="sxs-lookup"><span data-stu-id="32210-400">The **Main** section</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="32210-401">[メイン] セクションの下部まで **下にスクロール** します。</span><span class="sxs-lookup"><span data-stu-id="32210-401">Scroll down to the bottom of the **Main** section.</span></span>  <span data-ttu-id="32210-402">フレームワークを使用する場合、上位のアクティビティの大部分はフレームワークによって引き起こされ、通常は制御が取り外されています。</span><span class="sxs-lookup"><span data-stu-id="32210-402">When you use a framework, most of the upper activity is caused by the framework, which is usually out of your control.</span></span>  <span data-ttu-id="32210-403">アプリによって引き起こされたアクティビティは、通常、下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="32210-403">The activity caused by your app is usually at the bottom.</span></span>  <span data-ttu-id="32210-404">このアプリでは、という名前の関数が関数に対して多くの要求 `App` を引き起こしている `mineBitcoin` ようです。</span><span class="sxs-lookup"><span data-stu-id="32210-404">In this app, it seems like a function named `App` is causing a lot of requests to a `mineBitcoin` function.</span></span>  <span data-ttu-id="32210-405">トニーがファンのデバイスを使って暗号化を採掘している可能性があるように聞こえます。..</span><span class="sxs-lookup"><span data-stu-id="32210-405">It sounds like Tony may be using the devices of his fans to mine cryptocurrency...</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png" alt-text="mineBitcoin アクティビティにカーソルを合わせる" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png":::
       <span data-ttu-id="32210-407">アクティビティにカーソルを合 `mineBitcoin` わせる</span><span class="sxs-lookup"><span data-stu-id="32210-407">Hover on the `mineBitcoin` activity</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="32210-408">フレームワークが行う要求は通常は制御されませんが、フレームワークを非効率的に実行する方法でアプリを構造化する場合があります。</span><span class="sxs-lookup"><span data-stu-id="32210-408">Although the requests that your framework makes are usually out of your control, sometimes you may structure your app in a way that causes the framework to run inefficiently.</span></span>  <span data-ttu-id="32210-409">フレームワークを効率的に使用するためにアプリを再構築すると、メイン スレッドの作業を減らします。</span><span class="sxs-lookup"><span data-stu-id="32210-409">Restructuring your app to use the framework efficiently is a way to do less main thread work.</span></span>  <span data-ttu-id="32210-410">ただし、フレームワークをより効率的に使用するには、フレームワークの動作と、独自のコードで行う変更の種類について深く理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32210-410">However, this requires a deep understanding of how your framework works, and what kind of changes you make in your own code in order to use the framework more efficiently.</span></span>  
    
1.  <span data-ttu-id="32210-411">[ボトム **アップ] セクションを** 展開します。</span><span class="sxs-lookup"><span data-stu-id="32210-411">Expand the **Bottom-Up** section.</span></span>  <span data-ttu-id="32210-412">このタブでは、最も時間がかかったアクティビティを分解します。</span><span class="sxs-lookup"><span data-stu-id="32210-412">This tab breaks down what activities took up the most time.</span></span>  <span data-ttu-id="32210-413">[メイン] セクションに何もBottom-Up場合は、[メイン] セクションのラベルを **選択** します。</span><span class="sxs-lookup"><span data-stu-id="32210-413">If nothing is displayed in the Bottom-Up section, choose the label for **Main** section.</span></span>  <span data-ttu-id="32210-414">[ **ボトムアップ] セクション** には、現在選択しているアクティビティまたはアクティビティのグループに関する情報だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="32210-414">The **Bottom-Up** section only shows information for whatever activity, or group of activity, you have currently selected.</span></span>  <span data-ttu-id="32210-415">たとえば、アクティビティの 1 つを選択した場合、[ボトムアップ] セクションでは、その 1 つのアクティビティの `mineBitcoin` 情報のみを表示します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="32210-415">For example, if you chose one of the `mineBitcoin` activities, the **Bottom-Up** section is only going to show information for that one activity.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png" alt-text="[Bottom-Up] タブ" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png":::
       <span data-ttu-id="32210-417">[ **ボトムアップ]** タブ</span><span class="sxs-lookup"><span data-stu-id="32210-417">The **Bottom-Up** tab</span></span>  
    :::image-end:::  
    
<span data-ttu-id="32210-418">[Self **Time]** 列には、各アクティビティに直接費やされた時間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="32210-418">The **Self Time** column shows you how much time was spent directly in each activity.</span></span>  <span data-ttu-id="32210-419">たとえば、次の図では、メイン スレッド時間の約 63% が関数に費や `mineBitcoin` されています。</span><span class="sxs-lookup"><span data-stu-id="32210-419">For example, in the following figure, about 63% of main thread time was spent on the `mineBitcoin` function.</span></span>  

<span data-ttu-id="32210-420">実稼働モードを使用して JavaScript アクティビティを減らすと、ページの読み込み速度が上がる可能性があるかどうかを確認する時間。</span><span class="sxs-lookup"><span data-stu-id="32210-420">Time to review whether using production mode and reducing JavaScript activity may speed up the page load.</span></span>  <span data-ttu-id="32210-421">実稼働モードから開始します。</span><span class="sxs-lookup"><span data-stu-id="32210-421">Start with production mode:</span></span>  

1.  <span data-ttu-id="32210-422">[エディター] タブで、を開きます `webpack.config.js` 。</span><span class="sxs-lookup"><span data-stu-id="32210-422">In the editor tab, open `webpack.config.js`.</span></span>  
1.  <span data-ttu-id="32210-423">に `"mode":"development"` 変更します `"mode":"production"` 。</span><span class="sxs-lookup"><span data-stu-id="32210-423">Change `"mode":"development"` to `"mode":"production"`.</span></span>  
1.  <span data-ttu-id="32210-424">新しいビルドが展開されるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="32210-424">Wait for the new build to deploy.</span></span>  
1.  <span data-ttu-id="32210-425">ページを再度監査します。</span><span class="sxs-lookup"><span data-stu-id="32210-425">Audit the page again.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png" alt-text="実稼働モードを使用する Webpack を構成した後の監査レポート" lightbox="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png":::
       <span data-ttu-id="32210-427">実稼働モードを使用する Webpack を構成した後の監査レポート</span><span class="sxs-lookup"><span data-stu-id="32210-427">An Audits report after configuring webpack to use production mode</span></span>  
    :::image-end:::  
    
<span data-ttu-id="32210-428">要求を削除して JavaScript アクティビティを減らします `mineBitcoin` 。</span><span class="sxs-lookup"><span data-stu-id="32210-428">Reduce JavaScript activity by removing the request to `mineBitcoin`:</span></span>  

1.  <span data-ttu-id="32210-429">[エディター] タブで、を開きます `src/App.jsx` 。</span><span class="sxs-lookup"><span data-stu-id="32210-429">In the editor tab, open `src/App.jsx`.</span></span>  
1.  <span data-ttu-id="32210-430">に要求をコメント `this.mineBitcoin(1500)` アウト `constructor` します。</span><span class="sxs-lookup"><span data-stu-id="32210-430">Comment out the request to `this.mineBitcoin(1500)` in the `constructor`.</span></span>  
1.  <span data-ttu-id="32210-431">新しいビルドが展開されるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="32210-431">Wait for the new build to deploy.</span></span>  
1.  <span data-ttu-id="32210-432">ページを再度監査します。</span><span class="sxs-lookup"><span data-stu-id="32210-432">Audit the page again.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png" alt-text="不要な JavaScript 作業を削除した後の監査レポート" lightbox="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png":::
       <span data-ttu-id="32210-434">不要な JavaScript 作業を削除した後の監査レポート</span><span class="sxs-lookup"><span data-stu-id="32210-434">An Audits report after removing unnecessary JavaScript work</span></span>  
    :::image-end:::  
    
<span data-ttu-id="32210-435">その最後の変更がパフォーマンスの大きなジャンプを引き起こしたように見えます。</span><span class="sxs-lookup"><span data-stu-id="32210-435">Looks like that last change caused a massive jump in performance!</span></span>  

> [!NOTE]
> <span data-ttu-id="32210-436">このセクションでは、パフォーマンス パネルについて簡単に説明しました。</span><span class="sxs-lookup"><span data-stu-id="32210-436">This section provided a rather brief introduction to the Performance panel.</span></span>  <span data-ttu-id="32210-437">ページのパフォーマンスを分析する方法の詳細については、「パフォーマンス分析リファレンス [」に移動します][DevtoolsEvaluatePerformanceReference]。</span><span class="sxs-lookup"><span data-stu-id="32210-437">To learn more about how to analyze page performance, navigate to [Performance Analysis Reference][DevtoolsEvaluatePerformanceReference].</span></span>  

<!--todo: add section when available -->  

#### <a name="doing-less-main-thread-work-in-the-real-world"></a><span data-ttu-id="32210-438">実際の世界でメイン スレッドの動作を減らします</span><span class="sxs-lookup"><span data-stu-id="32210-438">Doing less main thread work in the real world</span></span>  

<span data-ttu-id="32210-439">一般に、 **パフォーマンス ツールは** 、サイトが読み込まれるとどのようなアクティビティを行うのかを理解し、不要なアクティビティを削除する方法を見つける最も一般的な方法です。</span><span class="sxs-lookup"><span data-stu-id="32210-439">In general, the **Performance** tool is the most common way to understand what activity your site does as it loads, and find ways to remove unnecessary activity.</span></span>  

<span data-ttu-id="32210-440">ユーザー タイミング API を使用すると、各フェーズにかかる時間を追跡するために、アプリのライフサイクルの特定のフェーズを任意にマークできます `console.log()` 。 [][MDNUserTimingApi]</span><span class="sxs-lookup"><span data-stu-id="32210-440">If you prefer an approach that feels more like `console.log()`, the [User Timing API][MDNUserTimingApi] enables you to arbitrarily mark up certain phases of your app lifecycle, in order to track how long each of those phases takes.</span></span>  

## <a name="summary"></a><span data-ttu-id="32210-441">要約</span><span class="sxs-lookup"><span data-stu-id="32210-441">Summary</span></span>  

*   <span data-ttu-id="32210-442">サイトの読み込みパフォーマンスを最適化するために設定するたびに、常に監査を開始します。</span><span class="sxs-lookup"><span data-stu-id="32210-442">Whenever you set out to optimize the load performance of a site, always start with an audit.</span></span>  <span data-ttu-id="32210-443">監査はベースラインを確立し、改善方法に関するヒントを提供します。</span><span class="sxs-lookup"><span data-stu-id="32210-443">The audit establishes a baseline, and gives you tips on how to improve.</span></span>  
*   <span data-ttu-id="32210-444">一度に 1 つの変更を行い、変更後に Web ページを監査して、分離された変更がパフォーマンスに与える影響を表示します。</span><span class="sxs-lookup"><span data-stu-id="32210-444">Make one change at a time, and audit the webpage after each change in order to display how that isolated change affects performance.</span></span>  

<!--
## Next steps  

*   Run audits on your own site!  If you need help interpreting your report, or finding ways to improve your load performance, check out [Feedback](#feedback) for ways to get help from the DevTools community.  Stack Overflow, the mailing list, or Twitter are probably best for these types of questions.  
*   Please leave [feedback](#feedback) on this tutorial.  I really do use the data to make better tutorials for you.  
-->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="32210-445">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="32210-445">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsEvaluatePerformanceReference]: ../evaluate-performance/reference.md "パフォーマンス分析|Microsoft Docs"  

[CourseraIntroductionWebDevelopmentClass]: https://www.coursera.org/learn/web-development#syllabus "Web 開発クラスの概要|Coursera"  

[EssentialImageOptimization]: https://images.guide "重要な画像の最適化"  

[MDNContentEncodingDirectives]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Encoding#Directives "ディレクティブ - コンテンツ エンコード |MDN"  
[MDNUserTimingApi]: https://developer.mozilla.org/docs/Web/API/User_Timing_API "ユーザー タイミング API |MDN"  

[WebpackTreeShaking]: https://webpack.js.org/guides/tree-shaking "ツリーの揺れ|webpack"  

> [!NOTE]
> <span data-ttu-id="32210-452">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="32210-452">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="32210-453">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/speed/get-started) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="32210-453">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/speed/get-started) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="32210-455">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="32210-455">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
