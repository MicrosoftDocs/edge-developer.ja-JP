---
description: Microsoft Edge DevTools を使用して、web サイトの読み込みを高速化する方法について説明します。
title: Microsoft Edge DevTools を使用して Web サイトの速度を最適化する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: dafcb9c4d1194239baed7507e505d74d2b4ce1c8
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993442"
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





# <span data-ttu-id="82ad5-104">Microsoft Edge DevTools を使用して web サイトの速度を最適化する</span><span class="sxs-lookup"><span data-stu-id="82ad5-104">Optimize website speed with Microsoft Edge DevTools</span></span>   



## <span data-ttu-id="82ad5-105">チュートリアルの目標</span><span class="sxs-lookup"><span data-stu-id="82ad5-105">Goal of tutorial</span></span>  

<span data-ttu-id="82ad5-106">このチュートリアルでは、Microsoft Edge DevTools を使って、web サイトの読み込みを高速化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-106">This tutorial teaches you how to use Microsoft Edge DevTools to find ways to make your websites load faster.</span></span>  

## <span data-ttu-id="82ad5-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="82ad5-107">Prerequisites</span></span>  

*   <span data-ttu-id="82ad5-108">この [Web 開発クラスの概要][CourseraIntroductionWebDevelopmentClass]で説明するように、基本的な web 開発環境を用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-108">You should have basic web development experience, similar to what is taught in this [Introduction to Web Development class][CourseraIntroductionWebDevelopmentClass].</span></span>  
*   <span data-ttu-id="82ad5-109">読み込みのパフォーマンスについて何も知りません。</span><span class="sxs-lookup"><span data-stu-id="82ad5-109">You do not need to know anything about load performance.</span></span>  <span data-ttu-id="82ad5-110">これについては、このチュートリアルで説明します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-110">You learn about it in this tutorial!</span></span>  

## <span data-ttu-id="82ad5-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="82ad5-111">Introduction</span></span>   

<span data-ttu-id="82ad5-112">これは Tony です。</span><span class="sxs-lookup"><span data-stu-id="82ad5-112">This is Tony.</span></span>  <span data-ttu-id="82ad5-113">Tony は、cat 協会で非常に有名です。</span><span class="sxs-lookup"><span data-stu-id="82ad5-113">Tony is very famous in cat society.</span></span>  <span data-ttu-id="82ad5-114">彼は、お客様がお気に入りの食品について知ることができるように、web サイトを構築しました。</span><span class="sxs-lookup"><span data-stu-id="82ad5-114">He has built a website so that his fans are able to learn about his favorite foods.</span></span>  <span data-ttu-id="82ad5-115">Tony のファンは、サイトを気に入っていますが、サイトの読み込み速度が遅いという苦情を耳にしています。</span><span class="sxs-lookup"><span data-stu-id="82ad5-115">His fans love the site, but Tony keeps hearing complaints that the site loads slowly.</span></span>  <span data-ttu-id="82ad5-116">Tony から、サイトの速度を向上させるように求められました。</span><span class="sxs-lookup"><span data-stu-id="82ad5-116">Tony has asked you to help him speed the site up.</span></span>  

:::image type="complex" source="../media/speed-tony.msft.png" alt-text="猫を Tony" lightbox="../media/speed-tony.msft.png":::
   <span data-ttu-id="82ad5-118">猫を Tony</span><span class="sxs-lookup"><span data-stu-id="82ad5-118">Tony the cat</span></span>  
:::image-end:::  

## <span data-ttu-id="82ad5-119">手順 1: サイトを監査する</span><span class="sxs-lookup"><span data-stu-id="82ad5-119">Step 1: Audit the site</span></span>   

<span data-ttu-id="82ad5-120">サイトの読み込みのパフォーマンスを向上させるために、 **必ず監査を開始して**ください。</span><span class="sxs-lookup"><span data-stu-id="82ad5-120">Whenever you set out to improve the load performance of a site, **always start with an audit**.</span></span>  
<span data-ttu-id="82ad5-121">監査には、次の2つの重要な機能があります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-121">The audit has 2 important functions:</span></span>  

*   <span data-ttu-id="82ad5-122">以降の変更を測定するための **基準計画** を作成します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-122">It creates a **baseline** for you to measure subsequent changes against.</span></span>  
*   <span data-ttu-id="82ad5-123">どのような変更が最も影響を与えるかに関する実用的な **ヒント** が提供されます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-123">It gives you **actionable tips** on what changes have the most impact.</span></span>  
    
### <span data-ttu-id="82ad5-124">設定</span><span class="sxs-lookup"><span data-stu-id="82ad5-124">Set up</span></span>   

<span data-ttu-id="82ad5-125">最初に、後で変更できるようにサイトを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-125">First, you must set up the site so that you are able to make changes to it later.</span></span>  

1.  <span data-ttu-id="82ad5-126">[サイトのソースコードを開き](https://glitch.com/edit/#!/tony)ます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-126">[Open the source code for the site](https://glitch.com/edit/#!/tony).</span></span>  <span data-ttu-id="82ad5-127">このタブは [ **エディター] タブ**と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-127">This tab is referred to as the **editor tab**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js.msft.png" alt-text="[エディター] タブ" lightbox="../media/speed-glitch-tony-server-js.msft.png":::
       <span data-ttu-id="82ad5-129">[ **エディター] タブ**</span><span class="sxs-lookup"><span data-stu-id="82ad5-129">The **editor tab**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="82ad5-130">[ **Tony**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-130">Select **tony**.</span></span>  <span data-ttu-id="82ad5-131">メニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-131">A menu appears.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js-remix-project.msft.png" alt-text="Tony をクリックした後に表示されるメニュー" lightbox="../media/speed-glitch-tony-server-js-remix-project.msft.png":::
       <span data-ttu-id="82ad5-133">**Tony**をクリックした後に表示されるメニュー</span><span class="sxs-lookup"><span data-stu-id="82ad5-133">The menu that appears after clicking **tony**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="82ad5-134">[ **Remix Project**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-134">Select **Remix Project**.</span></span>  <span data-ttu-id="82ad5-135">プロジェクトの名前が **tony** からランダムに生成された名前に変更されます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-135">The name of the project changes from **tony** to some randomly-generated name.</span></span>  <span data-ttu-id="82ad5-136">これで、独自のコードの編集可能なコピーが作成されました。</span><span class="sxs-lookup"><span data-stu-id="82ad5-136">You now have your own editable copy of the code.</span></span>  <span data-ttu-id="82ad5-137">後で、このコードを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-137">Later on, you may make changes to this code.</span></span>  
1.  <span data-ttu-id="82ad5-138">[ **表示** ] を選択し、 **新しいウィンドウで**を選択します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-138">Select **Show** and select **In a New Window**.</span></span>  <span data-ttu-id="82ad5-139">新しいタブでデモが開きます。 このタブは [ **デモ] タブ**として参照されます。 サイトが読み込まれるまでには時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-139">The demo opens in a new tab.  This tab is be referred to as the **demo tab**.  It may take a while for the site to load.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live.msft.png" alt-text="[デモ] タブ" lightbox="../media/speed-glitch-tony-show-live.msft.png":::
       <span data-ttu-id="82ad5-141">[デモ] タブ</span><span class="sxs-lookup"><span data-stu-id="82ad5-141">The demo tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="82ad5-142">`Control` + `Shift` + `J` \ (Windows \) または `Command` + `Option` + `J` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-142">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\).</span></span>  <span data-ttu-id="82ad5-143">Microsoft Edge の DevTools がデモと共に開きます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-143">Microsoft Edge DevTools opens up alongside the demo.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live-console.msft.png" alt-text="DevTools とデモ" lightbox="../media/speed-glitch-tony-show-live-console.msft.png":::
       <span data-ttu-id="82ad5-145">DevTools とデモ</span><span class="sxs-lookup"><span data-stu-id="82ad5-145">DevTools and the demo</span></span>  
    :::image-end:::  
    
<span data-ttu-id="82ad5-146">このチュートリアルの残りのスクリーンショットでは、DevTools が別のウィンドウに表示されています。</span><span class="sxs-lookup"><span data-stu-id="82ad5-146">For the rest of the screenshots in this tutorial, DevTools is shown in a separate window.</span></span>  <span data-ttu-id="82ad5-147">`Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) キーを押すと、コマンドメニューが開き、入力した `Undock` 後、**別のウィンドウに装着解除**することができます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-147">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, typing `Undock`, and then selecting **Undock into separate window**.</span></span>  

:::image type="complex" source="../media/speed-console.msft.png" alt-text="アンドックした DevTools" lightbox="../media/speed-console.msft.png":::
   <span data-ttu-id="82ad5-149">アンドックした DevTools</span><span class="sxs-lookup"><span data-stu-id="82ad5-149">Undocked DevTools</span></span>  
:::image-end:::  

### <span data-ttu-id="82ad5-150">ベースラインを確立する</span><span class="sxs-lookup"><span data-stu-id="82ad5-150">Establish a baseline</span></span>   

<span data-ttu-id="82ad5-151">ベースラインは、パフォーマンスを向上させる前に、サイトがどのように実行されたかを記録したものです。</span><span class="sxs-lookup"><span data-stu-id="82ad5-151">The baseline is a record of how the site performed before you made any performance improvements.</span></span>  

1.  <span data-ttu-id="82ad5-152">[ **監査** ] タブを選択します。 その **他のパネル** \ ([ ![ その他のパネル]) ボタンの背後に隠れている可能性があり ][ImageMorePanelsIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-152">Select the **Audits** tab.  It may be hidden behind the **More Panels** \(![More Panels][ImageMorePanelsIcon]\) button.</span></span>  <span data-ttu-id="82ad5-153">監査パネルを累乗するプロジェクトには、 **Lighthouse**という名前が付いているため、このパネルには Lighthouse があります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-153">There is a Lighthouse on this panel because the project that powers the Audits panel is named **Lighthouse**.</span></span>  
    
    [!INCLUDE [audits-panel-note](../includes/audits-panel-note.md)]  
    
    :::image type="complex" source="../media/speed-audits-performance.msft.png" alt-text="監査パネル" lightbox="../media/speed-audits-performance.msft.png":::
       <span data-ttu-id="82ad5-155">**監査**パネル</span><span class="sxs-lookup"><span data-stu-id="82ad5-155">The **Audits** panel</span></span>  
    :::image-end:::  
    
    <!--todo: add link to Lighthouse when section is available  -->  
    <!-- /web/tools/lighthouse  -->  
    
1.  <span data-ttu-id="82ad5-156">監査構成の設定と前の図の設定を一致させる。</span><span class="sxs-lookup"><span data-stu-id="82ad5-156">Match your audit configuration settings to those in the previous figure.</span></span>  <span data-ttu-id="82ad5-157">さまざまなオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-157">Here is an explanation of the different options:</span></span>  
    
    *   <span data-ttu-id="82ad5-158">**デバイス**。</span><span class="sxs-lookup"><span data-stu-id="82ad5-158">**Device**.</span></span>  <span data-ttu-id="82ad5-159">[ **モバイル** に設定] をオンにすると、ユーザーエージェント文字列が変更され、モバイルビューポートがシミュレートされます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-159">Setting to **Mobile** changes the user agent string and simulates a mobile viewport.</span></span>  <span data-ttu-id="82ad5-160">**デスクトップ**に設定することで、**モバイル**の変更が無効になります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-160">Setting to **Desktop** pretty much just disables the **Mobile** changes.</span></span>  
    *   <span data-ttu-id="82ad5-161">**監査**。</span><span class="sxs-lookup"><span data-stu-id="82ad5-161">**Audits**.</span></span>  <span data-ttu-id="82ad5-162">カテゴリを無効にすると、監査パネルでそれらの監査が実行されなくなり、レポートから監査が除外されます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-162">Disabling a category prevents the Audits panel from running those audits, and excludes those audits from your report.</span></span>  <span data-ttu-id="82ad5-163">提供されている推奨事項の種類を表示する場合は、その他のカテゴリを有効のままにします。</span><span class="sxs-lookup"><span data-stu-id="82ad5-163">Leave the other categories enabled, if you want to see the types of recommendations that are provide.</span></span>  <span data-ttu-id="82ad5-164">カテゴリを無効にすると、監査プロセスが少し速くなります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-164">Disabling categories slightly speeds up the auditing process.</span></span>  
    *   <span data-ttu-id="82ad5-165">**調整**。</span><span class="sxs-lookup"><span data-stu-id="82ad5-165">**Throttling**.</span></span>  <span data-ttu-id="82ad5-166">シミュレートされた **4g の4倍の CPU 速度** は、モバイルデバイスでの一般的な参照条件をシミュレートしています。</span><span class="sxs-lookup"><span data-stu-id="82ad5-166">Setting to **Simulated Slow 4G, 4x CPU Slowdown** simulates the typical conditions of browsing on a mobile device.</span></span>  <span data-ttu-id="82ad5-167">監査プロセス中に監査パネルで実際にスロットルされないので、"シミュレート" という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-167">It is named "simulated" because the Audits panel does not actually throttle during the auditing process.</span></span>  <span data-ttu-id="82ad5-168">代わりに、ページがモバイルの条件下で読み込むのにかかる時間を extrapolates だけです。</span><span class="sxs-lookup"><span data-stu-id="82ad5-168">Instead, it just extrapolates how long the page would take to load under mobile conditions.</span></span>  <span data-ttu-id="82ad5-169">一方、適用された [. **..** ] 設定では、より多くの監査プロセスの代わりに、CPU とネットワークのスロットルが実際に行われます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-169">The **Applied...** setting, on the other hand, actually throttles your CPU and network, with the tradeoff of a longer auditing process.</span></span>  
    *   <span data-ttu-id="82ad5-170">**ストレージをクリア**します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-170">**Clear Storage**.</span></span>  <span data-ttu-id="82ad5-171">このチェックボックスを有効にすると、ページに関連付けられているすべてのストレージが、各監査前に消去されます</span><span class="sxs-lookup"><span data-stu-id="82ad5-171">Enabling this checkbox clears all storage associated with the page before every audit.</span></span>  <span data-ttu-id="82ad5-172">この設定は、サイトでの初回の閲覧者の操作性を監査する場合にオンのままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-172">Leave this setting on if you want to audit how first-time visitors experience your site.</span></span>  <span data-ttu-id="82ad5-173">この設定は、ユーザーが繰り返しアクセスするときに無効にします。</span><span class="sxs-lookup"><span data-stu-id="82ad5-173">Disable this setting when you want the repeat-visit experience.</span></span>  
    
1.  <span data-ttu-id="82ad5-174">[ **監査の実行**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-174">Select **Run Audits**.</span></span>  <span data-ttu-id="82ad5-175">10秒から30秒後に、監査パネルにサイトのパフォーマンスのレポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-175">After 10 to 30 seconds, the Audits panel shows you a report of the performance of the site.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png" alt-text="サイトのパフォーマンスの監査パネルのレポート" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png":::
       <span data-ttu-id="82ad5-177">サイトのパフォーマンスの監査パネルのレポート</span><span class="sxs-lookup"><span data-stu-id="82ad5-177">The report for the Audits panel of the performance of the site</span></span>  
    :::image-end:::  
    
#### <span data-ttu-id="82ad5-178">レポートのエラーを処理する</span><span class="sxs-lookup"><span data-stu-id="82ad5-178">Handling report errors</span></span>   

<span data-ttu-id="82ad5-179">監査パネルレポートにエラーが表示された場合は、他のタブが開いていない **InPrivate** ウィンドウで [デモ] タブを実行してみてください。</span><span class="sxs-lookup"><span data-stu-id="82ad5-179">If you ever get an error in your Audits panel report, try running the demo tab from an **InPrivate** window with no other tabs open.</span></span>  <span data-ttu-id="82ad5-180">これにより、Microsoft Edge をクリーンな状態から実行することができます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-180">This ensures that you are running Microsoft Edge from a clean state.</span></span>  <span data-ttu-id="82ad5-181">特に Microsoft Edge Extensions は、監査プロセスの妨げになることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-181">Microsoft Edge Extensions in particular often interfere with the auditing process.</span></span>  

<!--todo: add screen capture for error in audit -->  
<!--
:::image type="complex" source="../media/speed-.msft.png" alt-text="A report that errored" lightbox="../media/speed-.msft.png":::
   A report that errored  
:::image-end:::  
-->  

### <span data-ttu-id="82ad5-182">レポートを理解する</span><span class="sxs-lookup"><span data-stu-id="82ad5-182">Understand your report</span></span>   

<span data-ttu-id="82ad5-183">レポートの上部に表示される数値は、サイトの全体的なパフォーマンススコアです。</span><span class="sxs-lookup"><span data-stu-id="82ad5-183">The number at the top of your report is the overall performance score for the site.</span></span>  <span data-ttu-id="82ad5-184">後でコードを変更すると、この数値の増加が確認できます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-184">Later, as you make changes to the code, you should see this number rise.</span></span>  <span data-ttu-id="82ad5-185">高いスコアは、パフォーマンスが向上することを意味します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-185">A higher score means better performance.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png" alt-text="全体的なパフォーマンススコア" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png":::
   <span data-ttu-id="82ad5-187">全体的なパフォーマンススコア</span><span class="sxs-lookup"><span data-stu-id="82ad5-187">The overall performance score</span></span>  
:::image-end:::  

<span data-ttu-id="82ad5-188">[ **メトリック** ] セクションには、サイトのパフォーマンスの定量的な測定値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-188">The **Metrics** section provides quantitative measurements of the performance of the site.</span></span>  <span data-ttu-id="82ad5-189">各メトリックは、パフォーマンスのさまざまな側面について把握します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-189">Each metric provides insight into a different aspect of the performance.</span></span>  <span data-ttu-id="82ad5-190">たとえば、 **最初の Contentful 塗料** は、画面に最初にコンテンツが描画されたときに表示されます。これは、ユーザーがページの読み込みにおいて重要なマイルストーンであり、 **対話型** のときには、ユーザーの操作を処理するのに必要なページが表示されている点を示します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-190">For example, **First Contentful Paint** tells you when content is first painted to the screen, which is an important milestone in the user's perception of the page load, whereas **Time To Interactive** marks the point at which the page appears ready enough to handle user interactions.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png" alt-text="[メトリック] セクション" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png":::
   <span data-ttu-id="82ad5-192">[ **メトリック** ] セクション</span><span class="sxs-lookup"><span data-stu-id="82ad5-192">The **Metrics** section</span></span>  
:::image-end:::  

<span data-ttu-id="82ad5-193">次の図の強調表示されたトグルボタンを選択すると、各メトリックの説明が表示され、[ **詳細** 情報] をクリックすると、その内容に関するドキュメントを参照できます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-193">Select the highlighted toggle button in the following figure to see a description for each metric, and click **Learn More** to read documentation about it.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png" alt-text="強調表示されたトグルボタンを選択して、[Metrics] 項目を展開する" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png":::
   <span data-ttu-id="82ad5-195">強調表示されたトグルボタンを選択して、[Metrics] 項目を展開する</span><span class="sxs-lookup"><span data-stu-id="82ad5-195">Select the highlighted toggle button to expand the Metrics items</span></span>  
:::image-end:::  

<span data-ttu-id="82ad5-196">メトリックの下には、ページが読み込まれたときにどのように見えるかを示すスクリーンショットのコレクションがあります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-196">Below Metrics is a collection of screenshots that show you how the page looked as it loaded.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text="ページの読み込み中の画面のスクリーンショット" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   <span data-ttu-id="82ad5-198">ページの読み込み中の画面のスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="82ad5-198">Screenshots of how the page looked while loading</span></span>  
:::image-end:::  

<span data-ttu-id="82ad5-199">[ **営業案件** ] セクションでは、この特定のページの読み込みパフォーマンスを向上させるためのヒントを紹介します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-199">The **Opportunities** section provides specific tips on how to improve the load performance of this specific page.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text="[営業案件] セクション" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   <span data-ttu-id="82ad5-201">[ **営業案件** ] セクション</span><span class="sxs-lookup"><span data-stu-id="82ad5-201">The **Opportunities** section</span></span>  
:::image-end:::  

<span data-ttu-id="82ad5-202">詳細については、[営業案件] を選択します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-202">Select an opportunity to learn more about it.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png" alt-text="レンダーブロックリソースの機会を排除する" lightbox="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png":::
   <span data-ttu-id="82ad5-204">**レンダーブロックリソースの機会を排除** する</span><span class="sxs-lookup"><span data-stu-id="82ad5-204">**Eliminate render-blocking resources** opportunity</span></span>  
:::image-end:::  

<span data-ttu-id="82ad5-205">[ **詳細情報** ] を選択して、営業案件が重要である理由と、その解決方法に関する具体的な推奨事項についてのドキュメントを表示します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-205">Select **Learn More** to see documentation about why an opportunity is important, and specific recommendations on how to fix it.</span></span>  

:::image type="complex" source="../media/speed-web-dev-performance-audits.msft.png" alt-text="レンダーブロックリソースの機会を減らすためのドキュメント" lightbox="../media/speed-web-dev-performance-audits.msft.png":::
   <span data-ttu-id="82ad5-207">**レンダーブロックリソース**の機会を減らすためのドキュメント</span><span class="sxs-lookup"><span data-stu-id="82ad5-207">Documentation for the **Eliminate render-blocking resources** opportunity</span></span>  
:::image-end:::  

<span data-ttu-id="82ad5-208">[ **診断** ] セクションには、ページの読み込み時間に影響する要因についての詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-208">The **Diagnostics** section provides more information about factors that contribute to the load time of the page.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png" alt-text="[診断] セクション" lightbox="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png":::
   <span data-ttu-id="82ad5-210">[ **診断** ] セクション</span><span class="sxs-lookup"><span data-stu-id="82ad5-210">The **Diagnostics** section</span></span>  
:::image-end:::  

<span data-ttu-id="82ad5-211">[ **成功** した監査] セクションには、サイトが正常に動作していることが示されます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-211">The **Passed Audits** section shows you what the site is doing correctly.</span></span>  <span data-ttu-id="82ad5-212">セクションを展開する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-212">Select to expand the section.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png" alt-text="[成功した監査] セクション" lightbox="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png":::
   <span data-ttu-id="82ad5-214">[ **成功** した監査] セクション</span><span class="sxs-lookup"><span data-stu-id="82ad5-214">The **Passed Audits** section</span></span>  
:::image-end:::  

## <span data-ttu-id="82ad5-215">手順 2: 実験</span><span class="sxs-lookup"><span data-stu-id="82ad5-215">Step 2: Experiment</span></span>   

<span data-ttu-id="82ad5-216">監査レポートの [営業案件] セクションには、ページのパフォーマンスを向上させるためのヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-216">The Opportunities section of your audit report gives you tips on how to improve the performance of the page.</span></span>  <span data-ttu-id="82ad5-217">このセクションでは、コードベースへの推奨される変更を実装します。各変更の後でサイトを監査し、サイトの速度にどのような影響があるかを測定します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-217">In this section, you implement the recommended changes to the codebase, auditing the site after each change to measure how it affects site speed.</span></span>  

### <span data-ttu-id="82ad5-218">テキストの圧縮を有効にする</span><span class="sxs-lookup"><span data-stu-id="82ad5-218">Enable text compression</span></span>   

<span data-ttu-id="82ad5-219">レポートでは、大量のネットワークペイロードを回避することが、ページのパフォーマンスを向上させるための最上位の機会の1つであることを示しています。</span><span class="sxs-lookup"><span data-stu-id="82ad5-219">Your report says that avoiding enormous network payloads is one of the top opportunities for improving the performance of the page.</span></span>  <span data-ttu-id="82ad5-220">テキスト圧縮を有効にすると、ページのパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-220">Enabling text compression is an opportunity to improve the performance of the page.</span></span>  

<span data-ttu-id="82ad5-221">テキストファイルをネットワーク経由で送信する前に、テキストファイルのサイズを縮小 (圧縮) する場合。</span><span class="sxs-lookup"><span data-stu-id="82ad5-221">Text compression is when you reduce, or compress, the size of a text file before sending it over the network.</span></span>  <span data-ttu-id="82ad5-222">メールのサイズを小さくするためにメールを送信する前に、どのようにしてフォルダーを zip 圧縮するかなどです。</span><span class="sxs-lookup"><span data-stu-id="82ad5-222">Kind of like how you might zip a folder before emailing it to reduce the size.</span></span>  

<span data-ttu-id="82ad5-223">圧縮を有効にする前に、テキストリソースが圧縮されているかどうかを手動で確認する方法がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-223">Before you enable compression, here are a couple of ways to manually check whether text resources are compressed.</span></span>  

1.  <span data-ttu-id="82ad5-224">[ **ネットワーク** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-224">Select the **Network** tab.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/speed-glitch-tony-remix-network.msft.png":::
       <span data-ttu-id="82ad5-226">[ **ネットワーク** ] パネル</span><span class="sxs-lookup"><span data-stu-id="82ad5-226">The **Network** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="82ad5-227">[ **ネットワーク設定** ] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-227">Select the **Network setting** icon.</span></span>  
1.  <span data-ttu-id="82ad5-228">[ **大きな要求行を使用する** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="82ad5-228">Select the **Use Large Request Rows** checkbox.</span></span>  <span data-ttu-id="82ad5-229">ネットワーク要求のテーブルの行の高さが増加します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-229">The height of the rows in the table of network requests increases.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png" alt-text="ネットワーク要求テーブルの大きな行" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png":::
       <span data-ttu-id="82ad5-231">ネットワーク要求テーブルの大きな行</span><span class="sxs-lookup"><span data-stu-id="82ad5-231">Large rows in the network requests table</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="82ad5-232">ネットワーク要求のテーブルに [ **サイズ** ] 列が表示されない場合は、テーブルの見出しをクリックして、[ **サイズ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-232">If you do not see the **Size** column in the table of network requests, click the table header and then select **Size**.</span></span>  

<span data-ttu-id="82ad5-233">各 **Size** セルには2つの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-233">Each **Size** cell shows two values.</span></span>  <span data-ttu-id="82ad5-234">上の値は、ダウンロードしたリソースのサイズです。</span><span class="sxs-lookup"><span data-stu-id="82ad5-234">The top value is the size of the downloaded resource.</span></span>  
<span data-ttu-id="82ad5-235">ボトム値は、圧縮されていないリソースのサイズです。</span><span class="sxs-lookup"><span data-stu-id="82ad5-235">The bottom value is the size of the uncompressed resource.</span></span>  <span data-ttu-id="82ad5-236">2つの値が同じである場合は、ネットワーク経由で送信されたときにリソースが圧縮されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-236">If the two values are the same, then the resource is not being compressed when it is sent over the network.</span></span>  <span data-ttu-id="82ad5-237">たとえば、上の図では、の上位と下位の値 `bundle.js` は and で指定し `1.2 MB` `1.2 MB` ます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-237">For example, in the previous figure, the top and bottom values for `bundle.js` are `1.2 MB` and `1.2 MB`.</span></span>  

<span data-ttu-id="82ad5-238">リソースの HTTP ヘッダーを調べて、圧縮を確認します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-238">Check for compression by inspecting the HTTP headers of a resource:</span></span>  

1.  <span data-ttu-id="82ad5-239">[ **bundle.js**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-239">Select **bundle.js**.</span></span>  
1.  <span data-ttu-id="82ad5-240">[ **ヘッダー** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-240">Select the **Headers** tab.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png" alt-text="[ヘッダー] タブ" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png":::
       <span data-ttu-id="82ad5-242">[ **ヘッダー** ] タブ</span><span class="sxs-lookup"><span data-stu-id="82ad5-242">The **Headers** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="82ad5-243">ヘッダーの [ **応答ヘッダー** ] セクションを検索し `content-encoding` ます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-243">Search the **Response Headers** section for a `content-encoding` header.</span></span>  <span data-ttu-id="82ad5-244">圧縮されていないことを示すものは表示されません `bundle.js` 。</span><span class="sxs-lookup"><span data-stu-id="82ad5-244">You should not see one, meaning that `bundle.js` was not compressed.</span></span>  <span data-ttu-id="82ad5-245">リソースが圧縮されている場合、このヘッダーは通常、、またはに設定され `gzip` `deflate` `br` ます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-245">When a resource is compressed, this header is usually set to `gzip`, `deflate`, or `br`.</span></span>  <span data-ttu-id="82ad5-246">これらの値の説明については、「 [ディレクティブ][MDNContentEncodingDirectives] 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82ad5-246">See [Directives][MDNContentEncodingDirectives] for an explanation of these values.</span></span>  

<span data-ttu-id="82ad5-247">説明が必要です。</span><span class="sxs-lookup"><span data-stu-id="82ad5-247">Enough with the explanations.</span></span>  <span data-ttu-id="82ad5-248">変更を加える時間</span><span class="sxs-lookup"><span data-stu-id="82ad5-248">Time to make some changes!</span></span>  <span data-ttu-id="82ad5-249">テキストの圧縮を有効にするには、数行のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-249">Enable text compression by adding a couple of lines of code:</span></span>  

1.  <span data-ttu-id="82ad5-250">[エディター] タブで、[ **server.js**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82ad5-250">In the editor tab, click **server.js**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js.msft.png" alt-text="server.js を編集する" lightbox="../media/speed-glitch-tony-remix-server-js.msft.png":::
       <span data-ttu-id="82ad5-252">Edit</span><span class="sxs-lookup"><span data-stu-id="82ad5-252">Edit</span></span> `server.js`  
    :::image-end:::  
    
1.  <span data-ttu-id="82ad5-253">**server.js**に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-253">Add the following code to **server.js**.</span></span>  <span data-ttu-id="82ad5-254">前に必ず入力してください `app.use(compression())` `app.use(express.static('build'))` 。</span><span class="sxs-lookup"><span data-stu-id="82ad5-254">Make sure to put `app.use(compression())` before `app.use(express.static('build'))`.</span></span>  

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
    > <span data-ttu-id="82ad5-255">通常は、次のような方法でパッケージをインストールする必要があり `compression` `npm i -S compression` ますが、これは既に行われています。</span><span class="sxs-lookup"><span data-stu-id="82ad5-255">Usually, you have to install the `compression` package via something like `npm i -S compression`, but this has already been done for you.</span></span>  
    
1.  <span data-ttu-id="82ad5-256">サイトの新しいビルドが展開されるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-256">Wait for Glitch to deploy the new build of the site.</span></span>  <span data-ttu-id="82ad5-257">[ **ツール** ] の横にある凝ったアニメーションは、サイトが再構築されて再展開されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-257">The fancy animation next to **Tools** means that the site is getting rebuilt and redeployed.</span></span>  <span data-ttu-id="82ad5-258">[ **ツール** ] の横にあるアニメーションが消えると、変更がすぐにできます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-258">The change is ready when the animation next to **Tools** goes away.</span></span>  <span data-ttu-id="82ad5-259">[ **表示** ] を選択し、 **新しいウィンドウで** もう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-259">Select **Show** and select **In a New Window** again.</span></span>  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js-edited.msft.png" alt-text="The animation that indicates that the site is getting built" lightbox="../media/speed-glitch-tony-remix-server-js-edited.msft.png":::
       The animation that indicates that the site is getting built  
    :::image-end:::  
    -->  
    
<span data-ttu-id="82ad5-260">以前に学習したワークフローを使用して、圧縮が機能していることを手動で確認します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-260">Use the workflows that you learned earlier to manually check that the compression is working:</span></span>  

1.  <span data-ttu-id="82ad5-261">[デモ] タブに戻り、ページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="82ad5-261">Go back to the demo tab and reload the page.</span></span>  <span data-ttu-id="82ad5-262">これで、[ **サイズ** ] 列に、次のようなテキストリソースの2つの異なる値が表示され `bundle.js` ます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-262">The **Size** column should now show 2 different values for text resources like `bundle.js`.</span></span>  <span data-ttu-id="82ad5-263">次の図では、の値 `256 KB` `bundle.js` はネットワーク経由で送信されたファイルのサイズであり、の下の値は圧縮されていない `1.2 MB` ファイルサイズです。</span><span class="sxs-lookup"><span data-stu-id="82ad5-263">In the figure after the following, the top value of `256 KB` for `bundle.js` is the size of the file that was sent over the network, and the bottom value of `1.2 MB` is the uncompressed file size.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-main.msft.png" alt-text="[サイズ] 列に、テキストリソースの2つの異なる値が表示されるようになりました" lightbox="../media/speed-glitch-tony-remix-network-main.msft.png":::
       <span data-ttu-id="82ad5-265">[ **サイズ** ] 列に、テキストリソースの2つの異なる値が表示されるようになりました</span><span class="sxs-lookup"><span data-stu-id="82ad5-265">The **Size** column now shows 2 different values for text resources</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="82ad5-266">[ **応答ヘッダー** ] セクションに、 `bundle.js` ヘッダーを含めるようになりました `content-encoding: gzip` 。</span><span class="sxs-lookup"><span data-stu-id="82ad5-266">The **Response Headers** section for `bundle.js` should now include a `content-encoding: gzip` header.</span></span>
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png" alt-text="応答ヘッダーセクションにコンテンツエンコードヘッダーが含まれるようになりました" lightbox="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png":::
       <span data-ttu-id="82ad5-268">**応答ヘッダー**セクションにコンテンツエンコードヘッダーが含まれるようになりました</span><span class="sxs-lookup"><span data-stu-id="82ad5-268">The **Response Headers** section now contains a content-encoding header</span></span>  
    :::image-end:::  
    
<span data-ttu-id="82ad5-269">ページをもう一度監査して、ページの読み込みパフォーマンスにどのような影響があるかを測定します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-269">Audit the page again to measure what kind of impact text compression has on the load performance of the page:</span></span>  

1.  <span data-ttu-id="82ad5-270">[ **監査** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-270">Select the **Audits** tab.</span></span>  
1.  <span data-ttu-id="82ad5-271">[ **監査を実行する** ] を選択し ![ ます (監査を実行 ][ImagePerformIcon] します)。</span><span class="sxs-lookup"><span data-stu-id="82ad5-271">Select **Perform an audit** \(![Perform an audit][ImagePerformIcon]\).</span></span>  
1.  <span data-ttu-id="82ad5-272">設定は前の設定のままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-272">Leave the settings the same as before.</span></span>  
1.  <span data-ttu-id="82ad5-273">[ **監査の実行**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-273">Select **Run audit**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png" alt-text="テキストの圧縮を有効にした後の監査レポート" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png":::
       <span data-ttu-id="82ad5-275">テキストの圧縮を有効にした後の監査レポート</span><span class="sxs-lookup"><span data-stu-id="82ad5-275">An Audits report after enabling text compression</span></span>  
    :::image-end:::  
    
<!--  Woohoo!  That looks like progress.  -->  <span data-ttu-id="82ad5-276">全体的なパフォーマンススコアは高くなります。つまり、サイトの速度が速くなります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-276">Your overall performance score should have increased, meaning that the site is getting faster.</span></span>  

#### <span data-ttu-id="82ad5-277">現実世界でのテキスト圧縮</span><span class="sxs-lookup"><span data-stu-id="82ad5-277">Text compression in the real world</span></span>   

<span data-ttu-id="82ad5-278">ほとんどのサーバーでは、圧縮を有効にするための単純な修正プログラムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="82ad5-278">Most servers really do have simple fixes like this for enabling compression!</span></span>  <span data-ttu-id="82ad5-279">テキストの圧縮に使用するサーバーを構成する方法について、検索を行うだけです。</span><span class="sxs-lookup"><span data-stu-id="82ad5-279">Just do a search on how to configure whatever server you use to compress text.</span></span>  

### <span data-ttu-id="82ad5-280">画像のサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="82ad5-280">Resize images</span></span>   

<span data-ttu-id="82ad5-281">レポートでは、大量のネットワークペイロードを回避することが、ページのパフォーマンスを向上させるための最上位の機会の1つであることを示しています。</span><span class="sxs-lookup"><span data-stu-id="82ad5-281">Your report indicates that avoiding enormous network payloads is one of the top opportunities for improving the performance of the page.</span></span>  <span data-ttu-id="82ad5-282">画像のサイズを変更すると、ネットワークペイロードのサイズを小さくすることができます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-282">Resizing images helps reduce the size of the network payload.</span></span>  <span data-ttu-id="82ad5-283">ユーザーが500ピクセル幅のモバイルデバイス画面で画像を表示している場合、1500ピクセル幅の画像を送信することはまったくありません。</span><span class="sxs-lookup"><span data-stu-id="82ad5-283">If your user is viewing your images on a mobile device screen that is 500-pixels-wide, there is really no point in sending a 1500-pixel-wide image.</span></span>  <span data-ttu-id="82ad5-284">理想的には、500ピクセル幅の画像を送信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="82ad5-284">Ideally, you send a 500-pixel-wide image, at most.</span></span>  

1.  <span data-ttu-id="82ad5-285">レポートで、[ **大量のネットワークペイロード** を使用しない] をクリックして、サイズを変更する画像を確認します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-285">In your report, click **Avoid enormous network payloads** to see which images should be resized.</span></span>  <span data-ttu-id="82ad5-286">Jpg ファイルのうち2つは 2000 KB を超えるようですが、これは必要以上に大きくなります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-286">It looks like 2 of the jpg files are over 2000 KB, which is bigger than necessary.</span></span>  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png" alt-text="Details about the properly size images opportunity" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png":::
       Details about the properly size images opportunity  
    :::image-end:::  
    -->
    
1.  <span data-ttu-id="82ad5-287">[エディター] タブに戻り、[] を開き `src/model.js` ます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-287">Back in the editor tab, open `src/model.js`.</span></span>  
1.  <span data-ttu-id="82ad5-288">置換後 `const dir = 'big'` の文字列 `const dir = 'small'`</span><span class="sxs-lookup"><span data-stu-id="82ad5-288">Replace `const dir = 'big'` with `const dir = 'small'`.</span></span>  <span data-ttu-id="82ad5-289">このディレクトリには、サイズ変更された同じ画像のコピーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="82ad5-289">This directory contains copies of the same images which have been resized.</span></span>  
1.  <span data-ttu-id="82ad5-290">この変更が読み込みのパフォーマンスにどのように影響するかを確認するには、ページをもう一度監査します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-290">Audit the page again to see how this change affects load performance.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-compression-small-images-audits-performance.msft.png" alt-text="画像のサイズを変更した後の監査レポート" lightbox="../media/speed-glitch-compression-small-images-audits-performance.msft.png":::
       <span data-ttu-id="82ad5-292">画像のサイズを変更した後の監査レポート</span><span class="sxs-lookup"><span data-stu-id="82ad5-292">An Audits report after resizing images</span></span>  
    :::image-end:::  
    
<span data-ttu-id="82ad5-293">変更は、全体的なパフォーマンススコアに対して軽微な影響を与えるようです。</span><span class="sxs-lookup"><span data-stu-id="82ad5-293">Looks like the change only has a minor affect on the overall performance score.</span></span>  <span data-ttu-id="82ad5-294">ただし、スコアが明確に表示されない場合は、ユーザーに保存されているネットワークデータの量です。</span><span class="sxs-lookup"><span data-stu-id="82ad5-294">However, one thing that the score does not show clearly is how much network data you are saving your users.</span></span>  <span data-ttu-id="82ad5-295">以前の写真の合計サイズは、5.3 mb になりましたが、現時点では 0.18 mb にすぎません。</span><span class="sxs-lookup"><span data-stu-id="82ad5-295">The total size of the old photos was around 5.3 megabytes, whereas now it is only about 0.18 megabytes.</span></span>  

#### <span data-ttu-id="82ad5-296">実際の画像のサイズ変更</span><span class="sxs-lookup"><span data-stu-id="82ad5-296">Resizing images in the real world</span></span>   

<span data-ttu-id="82ad5-297">小規模のアプリでは、1回限りのサイズ変更を行っても問題が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-297">For a small app, doing a one-off resize like this may be good enough.</span></span>  <span data-ttu-id="82ad5-298">ただし、大規模なアプリでは、このようなスケーラビリティはありません。</span><span class="sxs-lookup"><span data-stu-id="82ad5-298">But for a large app, this obviously is not scalable.</span></span>  <span data-ttu-id="82ad5-299">大規模なアプリでイメージを管理するためのいくつかの方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-299">Here are some strategies for managing images in large apps:</span></span>  

*   <span data-ttu-id="82ad5-300">ビルドプロセス中に画像のサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-300">Resize images during your build process.</span></span>  
*   <span data-ttu-id="82ad5-301">ビルドプロセス中に各画像のサイズを複数作成し、 `srcset` コードで使用します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-301">Create multiple sizes of each image during the build process and then use `srcset` in your code.</span></span>  <span data-ttu-id="82ad5-302">実行時には、ブラウザーは、デバイスに最適なサイズを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-302">At runtime, the browser takes care of choosing which size is best for the device.</span></span>  
    <!--See [Relative-sized images][relative].  -->
    
<!--[relative]: /web/fundamentals/design-and-ux/responsive/images#relative_sized_images  -->  

*   <span data-ttu-id="82ad5-303">要求時に画像のサイズを動的に変更できるようにするイメージ CDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-303">Use an image CDN that lets you dynamically resize an image when you request it.</span></span>  
*   <span data-ttu-id="82ad5-304">少なくとも、各画像を最適化します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-304">At the very least, optimize each image.</span></span>  <span data-ttu-id="82ad5-305">これにより、大幅に節約できます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-305">This may create huge savings.</span></span>  
  <span data-ttu-id="82ad5-306">最適化とは、画像ファイルのサイズを小さくする特殊なプログラムで画像を実行する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-306">Optimization is when you run an image through a special program that reduces the size of the image file.</span></span>  <span data-ttu-id="82ad5-307">その他のヒントについては、「 [重要な画像の最適化][EssentialImageOptimization] 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="82ad5-307">See [Essential Image Optimization][EssentialImageOptimization] for more tips.</span></span>  
    
### <span data-ttu-id="82ad5-308">レンダーブロックリソースを排除する</span><span class="sxs-lookup"><span data-stu-id="82ad5-308">Eliminate render-blocking resources</span></span>   

<span data-ttu-id="82ad5-309">最新のレポートでは、レンダーブロックのリソースを除去することが最大の機会になりました。</span><span class="sxs-lookup"><span data-stu-id="82ad5-309">Your latest report says that eliminating render-blocking resources is now the biggest opportunity.</span></span>  

<span data-ttu-id="82ad5-310">レンダーブロックリソースは、ページを表示する前に、ブラウザーがダウンロード、解析、実行する必要がある外部 JavaScript または CSS ファイルです。</span><span class="sxs-lookup"><span data-stu-id="82ad5-310">A render-blocking resource is an external JavaScript or CSS file that the browser must download, parse, and run before it displays the page.</span></span>  <span data-ttu-id="82ad5-311">目的は、ページを適切に表示するために必要なコア CSS と JavaScript コードを実行することだけです。</span><span class="sxs-lookup"><span data-stu-id="82ad5-311">The goal is to only run the core CSS and JavaScript code that is required to display the page properly.</span></span>  

<span data-ttu-id="82ad5-312">最初のタスクでは、ページの読み込み時に実行する必要がないコードが検索されます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-312">The first task, then, is to find code that you do not need to run on page load.</span></span>  

1.  <span data-ttu-id="82ad5-313">[ **レンダーブロックリソースの削除** ] を選択して、ブロックされているリソースを確認します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-313">Select **Eliminate render-blocking resources** to see the resources that are blocking:</span></span>  
    `lodash.js` <span data-ttu-id="82ad5-314">および `jquery.js` 。</span><span class="sxs-lookup"><span data-stu-id="82ad5-314">and `jquery.js`.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png" alt-text="レンダーブロックリソースの機会の削減に関するその他の情報" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png":::
       <span data-ttu-id="82ad5-316">**レンダーブロックリソース**の機会の削減に関するその他の情報</span><span class="sxs-lookup"><span data-stu-id="82ad5-316">More information about the **Eliminate render-blocking resources** opportunity</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="82ad5-317">`Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) キーを押してコマンドメニューを開き、入力を開始して、[ `Coverage` **カバレッジの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-317">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, start typing `Coverage`, and then select **Show Coverage**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png" alt-text="[監査] パネルからコマンドメニューを開く" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png":::
       <span data-ttu-id="82ad5-319">[ **監査** ] パネルからコマンドメニューを開く</span><span class="sxs-lookup"><span data-stu-id="82ad5-319">Open the Command Menu from the **Audits** panel</span></span>  
    :::image-end:::  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png" alt-text="[カバレッジ] タブ" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png":::
       <span data-ttu-id="82ad5-321">[ **カバレッジ** ] タブ</span><span class="sxs-lookup"><span data-stu-id="82ad5-321">The **Coverage** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="82ad5-322">[ **Refresh** (更新)] を選び ![ ][ImageRefreshIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-322">Select **Refresh** \(![Refresh][ImageRefreshIcon]\).</span></span>  <span data-ttu-id="82ad5-323">[ **カバレッジ** ] タブには、ページの読み込み時にのコードの量の概要が表示され `bundle.js` `jquery.js` `lodash.js` ます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-323">The **Coverage** tab provides an overview of how much of the code in `bundle.js`, `jquery.js`, and `lodash.js` runs while the page loads.</span></span>  <span data-ttu-id="82ad5-324">次の図では、それぞれ、jQuery と Lodash のファイルの76% と30% は使用されません。</span><span class="sxs-lookup"><span data-stu-id="82ad5-324">In the figure after the following, about 76% and 30% of the jQuery and Lodash files are not used, respectively.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png" alt-text="カバレッジレポート" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png":::
       <span data-ttu-id="82ad5-326">カバレッジレポート</span><span class="sxs-lookup"><span data-stu-id="82ad5-326">The Coverage report</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="82ad5-327">[ **jquery.js** ] 行を選択します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-327">Select the **jquery.js** row.</span></span>  <span data-ttu-id="82ad5-328">DevTools [ソース] パネルでファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-328">DevTools opens the file in the Sources panel.</span></span>  <span data-ttu-id="82ad5-329">横に青色のバーが表示されている場合は、コード行が実行されます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-329">A line of code ran if it has a blue bar next to it.</span></span>  <span data-ttu-id="82ad5-330">赤色のバーは、実行されなかったため、ページの読み込み時には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="82ad5-330">A red bar means it was not run, and is definitely not needed on page load.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png" alt-text="ソースパネルで jQuery ファイルを表示する" lightbox="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png":::
       <span data-ttu-id="82ad5-332">**ソース**パネルで jQuery ファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="82ad5-332">Viewing the jQuery file in the **Sources** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="82ad5-333">JQuery コードを1ビットずつスクロールします。</span><span class="sxs-lookup"><span data-stu-id="82ad5-333">Scroll through the jQuery code a bit.</span></span>  <span data-ttu-id="82ad5-334">"実行" を取得する行の一部は、実際にはコメントにすぎません。</span><span class="sxs-lookup"><span data-stu-id="82ad5-334">Some of the lines that get "run" are actually just comments.</span></span>  <span data-ttu-id="82ad5-335">このコードを実行するときには、コメントを取り除くための別の方法として、このファイルのサイズを小さくする方法もあります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-335">Running this code through a minifier that strips comments is another way to reduce the size of this file.</span></span>  

<span data-ttu-id="82ad5-336">つまり、独自のコードを操作している場合、[カバレッジ] タブでは、コードの分析や行ごとの分析を行うことができます。また、ページの読み込みに必要なコードのみを提供します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-336">In short, when you are working with your own code, the Coverage tab helps you analyze your code, line-by-line, and only ship the code that is needed for page load.</span></span>  

<span data-ttu-id="82ad5-337">ページの `jquery.js` `lodash.js` 読み込みにもファイルが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="82ad5-337">Are the `jquery.js` and `lodash.js` files even needed to load the page?</span></span>  <span data-ttu-id="82ad5-338">[要求のブロック] タブには、リソースが利用できない場合の動作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-338">The Request Blocking tab displays what happens when resources are not available.</span></span>  

1.  <span data-ttu-id="82ad5-339">[ **ネットワーク** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-339">Select the **Network** tab.</span></span>  
1.  <span data-ttu-id="82ad5-340">`Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) キーを押して、もう一度コマンドメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-340">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu again.</span></span>  
1.  <span data-ttu-id="82ad5-341">入力を開始し `blocking` 、[ **要求ブロックの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-341">Start typing `blocking` and then select **Show Request Blocking**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png" alt-text="[要求のブロック] タブ" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png":::
       <span data-ttu-id="82ad5-343">[ **要求のブロック** ] タブ</span><span class="sxs-lookup"><span data-stu-id="82ad5-343">The **Request Blocking** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="82ad5-344">[ **パターンの追加** \ (パターンの追加 \)] を選択し、 ![ ][ImageAddPatternIcon] 「 `/libs/*` 」と入力して、[確認] `Enter` を押します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-344">Select **Add Pattern** \(![Add Pattern][ImageAddPatternIcon]\), type `/libs/*`, and then press `Enter` to confirm.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png" alt-text="すべての要求をライブラリディレクトリにブロックするためのパターンを追加する" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png":::
       <span data-ttu-id="82ad5-346">ディレクトリへの要求をブロックするためのパターンを追加する `libs`</span><span class="sxs-lookup"><span data-stu-id="82ad5-346">Add a pattern to block any request to the `libs` directory</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="82ad5-347">ページを最新の情報に更新してください。</span><span class="sxs-lookup"><span data-stu-id="82ad5-347">Refresh the page.</span></span>  <span data-ttu-id="82ad5-348">JQuery と Lodash の要求は赤で、要求がブロックされたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-348">The jQuery and Lodash requests are red, meaning that the requests were blocked.</span></span>   <span data-ttu-id="82ad5-349">ページは依然として読み込まれ、対話型であるため、これらのリソースは必要ではないようです。</span><span class="sxs-lookup"><span data-stu-id="82ad5-349">The page still loads and is interactive, so it looks like these resources are not needed whatsoever!</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png" alt-text="[ネットワーク] パネルに、リクエストがブロックされていることが示される" lightbox="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png":::
       <span data-ttu-id="82ad5-351">[ **ネットワーク** ] パネルに、リクエストがブロックされていることが示される</span><span class="sxs-lookup"><span data-stu-id="82ad5-351">The **Network** panel shows that the requests have been blocked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="82ad5-352">**Remove all patterns** ![ ][ImageRemoveIcon] ブロックパターンを削除するには、[すべてのパターンを削除する] (すべてのパターンを削除) を選択し `/libs/*` ます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-352">Select **Remove all patterns** \(![Remove all patterns][ImageRemoveIcon]\) to delete the `/libs/*` blocking pattern.</span></span>  
    
<span data-ttu-id="82ad5-353">一般的に、[要求のブロック] タブは、特定のリソースが利用できない場合にページがどのように動作するかをシミュレートするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-353">In general, the Request Blocking tab is useful for simulating how your page behaves when any given resource is not available.</span></span>  

<span data-ttu-id="82ad5-354">次に、これらのファイルへの参照をコードから削除して、ページをもう一度監査します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-354">Now, remove the references to these files from the code and audit the page again:</span></span>  

1.  <span data-ttu-id="82ad5-355">[エディター] タブに戻り、[] を開き `template.html` ます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-355">Back in the editor tab, open `template.html`.</span></span>  
1.  <span data-ttu-id="82ad5-356">`<script src="/libs/lodash.js">` と `<script src="/libs/jquery.js"></script>` を削除します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-356">Delete `<script src="/libs/lodash.js">` and `<script src="/libs/jquery.js"></script>`.</span></span>  
1.  <span data-ttu-id="82ad5-357">サイトが再構築され、再展開されるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-357">Wait for the site to re-build and re-deploy.</span></span>  
1.  <span data-ttu-id="82ad5-358">**監査パネルから**ページをもう一度監査します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-358">Audit the page again from the **Audits** panel.</span></span>  <span data-ttu-id="82ad5-359">全体的なスコアは、もう一度向上させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-359">Your overall score should have improved again.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png" alt-text="レンダーブロックリソースを削除した後の監査レポート" lightbox="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png":::
       <span data-ttu-id="82ad5-361">レンダーブロックリソースを削除した後の **監査** レポート</span><span class="sxs-lookup"><span data-stu-id="82ad5-361">An **Audits** report after removing the render-blocking resources</span></span>  
    :::image-end:::  
    
#### <span data-ttu-id="82ad5-362">現実世界での重大なレンダリングパスの最適化</span><span class="sxs-lookup"><span data-stu-id="82ad5-362">Optimizing the Critical Rendering Path in the real-world</span></span>   

<span data-ttu-id="82ad5-363">**クリティカルレンダリングパス**は、ページの読み込みに必要なコードを指します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-363">The **Critical Rendering Path** refers to the code that you need to load a page.</span></span>  <span data-ttu-id="82ad5-364">一般的には、ページの読み込み中にクリティカルコードのみを配布することにより、ページの読み込みを高速化し、その他のすべての機能を遅延読み込みします。</span><span class="sxs-lookup"><span data-stu-id="82ad5-364">In general, speed up page load by only shipping critical code during the page load, and then lazy-loading everything else.</span></span>  

<!--[CRP]: /web/fundamentals/performance/critical-rendering-path/  -->  

*   <span data-ttu-id="82ad5-365">完全に削除できるスクリプトを見つけることはできませんが、ページの読み込み中に要求する必要のないスクリプトが数多くあり、非同期で要求される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-365">It is unlikely that you are able to find scripts that you are able to remove outright, but you may find many scripts that you do not need to request during the page load, and instead may be requested asynchronously.</span></span>  <!--See [Using async or defer][async].  -->  
*   <span data-ttu-id="82ad5-366">フレームワークを使用している場合は、プロダクションモードであるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-366">If you are using a framework, check if it has a production mode.</span></span>  <span data-ttu-id="82ad5-367">このモードでは、重大なレンダリングをブロックしている不要なコードを取り除くために、 [ツリーのシェイク][WebpackTreeShaking] などの機能を使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-367">This mode may use a feature such as [tree shaking][WebpackTreeShaking] in order to eliminate unnecessary code that is blocking the critical render.</span></span>  
    
<!--[async]: /web/fundamentals/performance/optimizing-content-efficiency/loading-third-party-javascript/#use_async_or_defer  -->  

### <span data-ttu-id="82ad5-368">メインスレッドの作業量を少なくする</span><span class="sxs-lookup"><span data-stu-id="82ad5-368">Do less main thread work</span></span>   

<span data-ttu-id="82ad5-369">最新のレポートでは、[営業案件] セクションで若干の節約が可能になりますが、[診断] セクションで確認すると、最大のボトルネックはメインスレッドのアクティビティが多すぎるようです。</span><span class="sxs-lookup"><span data-stu-id="82ad5-369">Your latest report shows some minor potential savings in the Opportunities section, but if you look down in the Diagnostics section, it looks like the biggest bottleneck is too much main thread activity.</span></span>  

<span data-ttu-id="82ad5-370">メインスレッドでは、HTML、CSS、JavaScript の解析や実行など、ページを表示するために必要な作業のほとんどがブラウザーで行われます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-370">The main thread is where the browser does most of the work needed to display a page, such as parsing and running HTML, CSS, and JavaScript.</span></span>  

<span data-ttu-id="82ad5-371">目標として、[パフォーマンス] パネルを使用して、ページの読み込み中にメインスレッドで実行されている作業を分析し、不要な作業を延期または削除する方法を見つけます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-371">The goal is to use the Performance panel to analyze what work the main thread is doing while the page loads, and find ways to defer or remove unnecessary work.</span></span>  

1.  <span data-ttu-id="82ad5-372">[ **パフォーマンス** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-372">Select the **Performance** tab.</span></span>  
1.  <span data-ttu-id="82ad5-373">[ **キャプチャ設定** ] ( ![ キャプチャ設定 ][ImageCaptureIcon] ) を選びます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-373">Select **Capture Settings** \(![Capture Settings][ImageCaptureIcon]\).</span></span>  
1.  <span data-ttu-id="82ad5-374">[ **ネットワーク** ] を [ **3g** ] と [ **CPU** ] から [ **6x**] の速度に設定します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-374">Set **Network** to **Slow 3G** and **CPU** to **6x slowdown**.</span></span>  <span data-ttu-id="82ad5-375">通常、モバイルデバイスでは、ノート pc やデスクトップよりも多くのハードウェア制約があります。そのため、これらの設定では、より強力なデバイスを使用している場合と同じようにページの読み込みを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-375">Mobile devices typically have more hardware constraints than laptops or desktops, so these settings let you experience the page load as if you were using a less powerful device.</span></span>  
1.  <span data-ttu-id="82ad5-376">[ **Refresh** (更新)] を選び ![ ][ImageRefreshIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-376">Select **Refresh** \(![Refresh][ImageRefreshIcon]\).</span></span>  <span data-ttu-id="82ad5-377">DevTools はページを更新し、ページを読み込むために実行されたすべての作業の視覚エフェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-377">DevTools refreshes the page and then produces a visualization of all the work performed in order to load the page.</span></span>  <span data-ttu-id="82ad5-378">この視覚エフェクトは、 **トレース**として参照されます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-378">This visualization is referred to as the **trace**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png" alt-text="ページの読み込みのパフォーマンスパネルトレース" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png":::
       <span data-ttu-id="82ad5-380">ページの読み込みの **パフォーマンス** パネルトレース</span><span class="sxs-lookup"><span data-stu-id="82ad5-380">The **Performance** panel trace of the page load</span></span>  
    :::image-end:::  
    
<span data-ttu-id="82ad5-381">トレースには、左から右へのアクティビティが時系列で表示されます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-381">The trace shows activity chronologically, from left to right.</span></span>  <span data-ttu-id="82ad5-382">上の FPS、CPU、およびネットチャートでは、1秒あたりのフレーム数、CPU アクティビティ、ネットワークアクティビティの概要がわかります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-382">The FPS, CPU, and NET charts at the top give you an overview of frames per second, CPU activity, and network activity.</span></span>  <span data-ttu-id="82ad5-383">図の中で、次のように表示される黄色のブロック。これにより、CPU はスクリプトアクティビティで完全にビジー状態になりました。</span><span class="sxs-lookup"><span data-stu-id="82ad5-383">The block of yellow selected that you see in the figure after the following, the CPU was completely busy with scripting activity.</span></span>  <span data-ttu-id="82ad5-384">これは、JavaScript の作業を少なくすることで、ページの読み込み速度を向上させることができることを示しています。</span><span class="sxs-lookup"><span data-stu-id="82ad5-384">This is a clue that you may be able to speed up page load by doing less JavaScript work.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png" alt-text="トレースの概要セクション" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png":::
   <span data-ttu-id="82ad5-386">トレースの概要セクション</span><span class="sxs-lookup"><span data-stu-id="82ad5-386">The Overview section of the trace</span></span>  
:::image-end:::  

<span data-ttu-id="82ad5-387">トレースを調べて、JavaScript の作業を軽減する方法を見つけます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-387">Investigate the trace to find ways to do less JavaScript work:</span></span>  

1.  <span data-ttu-id="82ad5-388">[ **タイミング** ] セクションを選択して展開します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-388">Select the **Timings** section to expand it.</span></span>  <span data-ttu-id="82ad5-389">反応しない [タイミング][MDNUserTimingApi] が存在する可能性があるという事実に基づいて、Tony のアプリでは、反応の開発モードが使用されているように見えます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-389">Based on the fact that there may be a bunch of [Timings][MDNUserTimingApi] measures from React, it seems like Tony's app is using the development mode of React.</span></span>  <span data-ttu-id="82ad5-390">処理の運用モードに切り替えると、パフォーマンスが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-390">Switching to the production mode of React may yield some easy performance wins.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png" alt-text="[タイミング] セクション" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png":::
       <span data-ttu-id="82ad5-392">[ **タイミング** ] セクション</span><span class="sxs-lookup"><span data-stu-id="82ad5-392">The **Timings** section</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="82ad5-393">[ **タイミング** ] をもう一度選択すると、そのセクションが折りたたまれます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-393">Select **Timings** again to collapse that section.</span></span>  
1.  <span data-ttu-id="82ad5-394">**メイン**セクションを参照します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-394">Browse the **Main** section.</span></span>  <span data-ttu-id="82ad5-395">このセクションでは、左から右へのメインスレッドアクティビティの時系列ログを示します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-395">This section shows a chronological log of main thread activity, from left to right.</span></span>  <span data-ttu-id="82ad5-396">Y 軸 (上から下) は、イベントが発生した理由を示しています。</span><span class="sxs-lookup"><span data-stu-id="82ad5-396">The y-axis (top to bottom) shows why events occurred.</span></span>  <span data-ttu-id="82ad5-397">たとえば、次のようにした後に、イベントによって関数が実行されました。これは、実行の原因となった場合などに発生し `Evaluate Script` `(anonymous)` `(anonymous)` `__webpack__require__` ます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-397">For example, in the figyre after the following, the `Evaluate Script` event caused the `(anonymous)` function to run, which caused `(anonymous)` to run, which caused `__webpack__require__` to run, and so on.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png" alt-text="メインセクション" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png":::
       <span data-ttu-id="82ad5-399">**メイン**セクション</span><span class="sxs-lookup"><span data-stu-id="82ad5-399">The **Main** section</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="82ad5-400">**メイン**セクションの下部まで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="82ad5-400">Scroll down to the bottom of the **Main** section.</span></span>  <span data-ttu-id="82ad5-401">フレームワークを使っている場合、ほとんどのアクティビティは、通常はコントロール以外のフレームワークによって発生します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-401">When you use a framework, most of the upper activity is caused by the framework, which is usually out of your control.</span></span>  <span data-ttu-id="82ad5-402">アプリが原因で発生するアクティビティは、通常、下部にあります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-402">The activity caused by your app is usually at the bottom.</span></span>  <span data-ttu-id="82ad5-403">このアプリでは、という名前の関数 `App` が多くの要求を処理しているように見え `mineBitcoin` ます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-403">In this app, it seems like a function named `App` is causing a lot of requests to a `mineBitcoin` function.</span></span>  <span data-ttu-id="82ad5-404">Tony のように、ファンのデバイスを使用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-404">It sounds like Tony might be using the devices of his fans to mine cryptocurrency...</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png" alt-text="MineBitcoin アクティビティにカーソルを移動する" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png":::
       <span data-ttu-id="82ad5-406">アクティビティにマウスポインターを合わせる `mineBitcoin`</span><span class="sxs-lookup"><span data-stu-id="82ad5-406">Hover on the `mineBitcoin` activity</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="82ad5-407">通常、フレームワークによって行われる要求はコントロールから除外されますが、フレームワークを効率的に実行するための方法でアプリを構成することもあります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-407">Although the requests that your framework makes are usually out of your control, sometimes you may structure your app in a way that causes the framework to run inefficiently.</span></span>  <span data-ttu-id="82ad5-408">フレームワークを効果的に使用するようにアプリを再構築することは、メインスレッドの作業を少なくするための手段です。</span><span class="sxs-lookup"><span data-stu-id="82ad5-408">Restructuring your app to use the framework efficiently is a way to do less main thread work.</span></span>  <span data-ttu-id="82ad5-409">ただし、フレームワークの動作について深く理解している必要があります。また、フレームワークをより効率的に使用するために、独自のコードで行った変更の種類についても理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="82ad5-409">However, this requires a deep understanding of how your framework works, and what kind of changes you make in your own code in order to use the framework more efficiently.</span></span>  
    
1.  <span data-ttu-id="82ad5-410">[ **ボトムアップ** ] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-410">Expand the **Bottom-Up** section.</span></span>  <span data-ttu-id="82ad5-411">このタブでは、最も時間がかかるアクティビティを中断します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-411">This tab breaks down what activities took up the most time.</span></span>  <span data-ttu-id="82ad5-412">下のセクションに何も表示されない場合は、 **メイン** セクションのラベルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="82ad5-412">If you do not see anything in the Bottom-Up section, click the label for **Main** section.</span></span>  <span data-ttu-id="82ad5-413">**ボトムアップ**セクションには、現在選択されているすべてのアクティビティまたは活動のグループの情報のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-413">The **Bottom-Up** section only shows information for whatever activity, or group of activity, you have currently selected.</span></span>  <span data-ttu-id="82ad5-414">たとえば、アクティビティの1つをクリックした場合、 `mineBitcoin` **ボトムアップ** セクションには、その1つのアクティビティの情報のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-414">For example, if you clicked on one of the `mineBitcoin` activities, the **Bottom-Up** section is only going to show information for that one activity.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png" alt-text="[ボトムアップ] タブ" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png":::
       <span data-ttu-id="82ad5-416">[ **ボトムアップ** ] タブ</span><span class="sxs-lookup"><span data-stu-id="82ad5-416">The **Bottom-Up** tab</span></span>  
    :::image-end:::  
    
<span data-ttu-id="82ad5-417">[ **セルフ時刻** の列には、各アクティビティで直接費やした時間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-417">The **Self Time** column shows you how much time was spent directly in each activity.</span></span>  <span data-ttu-id="82ad5-418">たとえば、次の図では、メインスレッドの63% が関数に費やした時間を示してい `mineBitcoin` ます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-418">For example, in the following figure, about 63% of main thread time was spent on the `mineBitcoin` function.</span></span>  

<span data-ttu-id="82ad5-419">実行モードを使用し、JavaScript アクティビティを減らすことで、ページの読み込み速度を向上させることができるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-419">Time to see whether using production mode and reducing JavaScript activity may speed up the page load.</span></span>  <span data-ttu-id="82ad5-420">プロダクションモードで開始する:</span><span class="sxs-lookup"><span data-stu-id="82ad5-420">Start with production mode:</span></span>  

1.  <span data-ttu-id="82ad5-421">[エディター] タブで、を開き `webpack.config.js` ます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-421">In the editor tab, open `webpack.config.js`.</span></span>  
1.  <span data-ttu-id="82ad5-422">`"mode":"development"`をに変更 `"mode":"production"` します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-422">Change `"mode":"development"` to `"mode":"production"`.</span></span>  
1.  <span data-ttu-id="82ad5-423">新しいビルドが展開されるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-423">Wait for the new build to deploy.</span></span>  
1.  <span data-ttu-id="82ad5-424">ページをもう一度監査します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-424">Audit the page again.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png" alt-text="プロダクションモードを使用するように webpack を構成した後の監査レポート" lightbox="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png":::
       <span data-ttu-id="82ad5-426">プロダクションモードを使用するように webpack を構成した後の監査レポート</span><span class="sxs-lookup"><span data-stu-id="82ad5-426">An Audits report after configuring webpack to use production mode</span></span>  
    :::image-end:::  
    
<span data-ttu-id="82ad5-427">要求を削除して JavaScript のアクティビティを減らし `mineBitcoin` ます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-427">Reduce JavaScript activity by removing the request to `mineBitcoin`:</span></span>  

1.  <span data-ttu-id="82ad5-428">[エディター] タブで、を開き `src/App.jsx` ます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-428">In the editor tab, open `src/App.jsx`.</span></span>  
1.  <span data-ttu-id="82ad5-429">の要求をにコメントアウトし `this.mineBitcoin(1500)` `constructor` ます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-429">Comment out the request to `this.mineBitcoin(1500)` in the `constructor`.</span></span>  
1.  <span data-ttu-id="82ad5-430">新しいビルドが展開されるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-430">Wait for the new build to deploy.</span></span>  
1.  <span data-ttu-id="82ad5-431">ページをもう一度監査します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-431">Audit the page again.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png" alt-text="不要な JavaScript 作業を削除した後の監査レポート" lightbox="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png":::
       <span data-ttu-id="82ad5-433">不要な JavaScript 作業を削除した後の監査レポート</span><span class="sxs-lookup"><span data-stu-id="82ad5-433">An Audits report after removing unnecessary JavaScript work</span></span>  
    :::image-end:::  
    
<span data-ttu-id="82ad5-434">前回の変更によってパフォーマンスが大幅に向上したようです。</span><span class="sxs-lookup"><span data-stu-id="82ad5-434">Looks like that last change caused a massive jump in performance!</span></span>  

> [!NOTE]
> <span data-ttu-id="82ad5-435">このセクションでは、パフォーマンスパネルについて簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-435">This section provided a rather brief introduction to the Performance panel.</span></span>  <span data-ttu-id="82ad5-436">ページのパフォーマンスを分析する方法について詳しくは、「 [パフォーマンス分析のリファレンス][DevtoolsEvaluatePerformanceReference] 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="82ad5-436">See [Performance Analysis Reference][DevtoolsEvaluatePerformanceReference] to learn more about how to analyze page performance.</span></span>  

<!--todo: add section when available -->  

#### <span data-ttu-id="82ad5-437">実際の環境でのメインスレッドの使用量を少なくする</span><span class="sxs-lookup"><span data-stu-id="82ad5-437">Doing less main thread work in the real world</span></span>   

<span data-ttu-id="82ad5-438">一般的に、 **パフォーマンス** パネルは、サイトが読み込むときのアクティビティを理解するための最も一般的な方法です。また、不要なアクティビティを削除する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="82ad5-438">In general, the **Performance** panel is the most common way to understand what activity your site does as it loads, and find ways to remove unnecessary activity.</span></span>  

<span data-ttu-id="82ad5-439">もっと気に入ったアプローチが必要な場合は、 `console.log()` [ユーザーのタイミング API][MDNUserTimingApi] を使用して、各フェーズの所要時間を追跡するために、アプリのライフサイクルの特定のフェーズを任意にマークすることができます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-439">If you prefer an approach that feels more like `console.log()`, the [User Timing API][MDNUserTimingApi] enables you to arbitrarily mark up certain phases of your app lifecycle, in order to track how long each of those phases takes.</span></span>  

## <span data-ttu-id="82ad5-440">まとめ</span><span class="sxs-lookup"><span data-stu-id="82ad5-440">Summary</span></span>   

*   <span data-ttu-id="82ad5-441">サイトの読み込みパフォーマンスを最適化するために、必ず監査を開始してください。</span><span class="sxs-lookup"><span data-stu-id="82ad5-441">Whenever you set out to optimize the load performance of a site, always start with an audit.</span></span>  <span data-ttu-id="82ad5-442">監査によって基準計画が設定され、改善のヒントを得ることができます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-442">The audit establishes a baseline, and gives you tips on how to improve.</span></span>  
*   <span data-ttu-id="82ad5-443">一度に1つずつ変更し、そのたびにページがどのように変化するかを確認するために、個別に変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-443">Make one change at a time, and audit the page after each change in order to see how that isolated change affects performance.</span></span>  

<!--
## Next steps   

*   Run audits on your own site!  If you need help interpreting your report, or finding ways to improve your load performance, check out [Feedback](#feedback) for ways to get help from the DevTools community.  Stack Overflow, the mailing list, or Twitter are probably best for these types of questions.  
*   Please leave [feedback](#feedback) on this tutorial.  I really do use the data to make better tutorials for you.  
-->  

<!--  
  


-->  

<!-- image links -->  

[ImageAddPatternIcon]: ../media/add-pattern-icon.msft.png  
[ImageCaptureIcon]: ../media/capture-icon.msft.png  
[ImageLargeResourceRowsButtonIcon]: ../media/large-resource-rows-button-icon.msft.png  
[ImageMorePanelsIcon]: ../media/more-panels-icon.msft.png  
[ImagePerformIcon]: ../media/perform-icon.msft.png  
[ImageRefreshIcon]: ../media/reload-icon.msft.png  
[ImageRemoveIcon]: ../media/remove-icon.msft.png  
<!-- links -->  

[DevtoolsEvaluatePerformanceReference]: ../evaluate-performance/reference.md "業績分析リファレンス |Microsoft ドキュメント"  

[CourseraIntroductionWebDevelopmentClass]: https://www.coursera.org/learn/web-development#syllabus "Web 開発クラスの概要 |Coursera"  

[EssentialImageOptimization]: https://images.guide "基本的な画像の最適化"  

[MDNContentEncodingDirectives]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Encoding#Directives "ディレクティブ-コンテンツのエンコード |MDN"  
[MDNUserTimingApi]: https://developer.mozilla.org/docs/Web/API/User_Timing_API "ユーザーのタイミング API |MDN"  

[WebpackTreeShaking]: https://webpack.js.org/guides/tree-shaking "木のぶれ |webpack"  

> [!NOTE]
> <span data-ttu-id="82ad5-450">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="82ad5-450">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="82ad5-451">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/speed/get-started) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="82ad5-451">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/speed/get-started) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="82ad5-453">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="82ad5-453">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
