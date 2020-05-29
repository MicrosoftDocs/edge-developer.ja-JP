---
title: Microsoft Edge DevTools を使用して Web サイトの速度を最適化する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 7efc76fbcb3d1ed6cbd0760f789c8c952030d70c
ms.sourcegitcommit: 4c24edbd1c591914cb4109511534851570a614cb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611890"
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





# <span data-ttu-id="a7e29-103">Microsoft Edge DevTools を使用して Web サイトの速度を最適化する</span><span class="sxs-lookup"><span data-stu-id="a7e29-103">Optimize Website Speed With Microsoft Edge DevTools</span></span>   



## <span data-ttu-id="a7e29-104">チュートリアルの目標</span><span class="sxs-lookup"><span data-stu-id="a7e29-104">Goal of tutorial</span></span>  

<span data-ttu-id="a7e29-105">このチュートリアルでは、Microsoft Edge DevTools を使って、web サイトの読み込みを高速化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-105">This tutorial teaches you how to use Microsoft Edge DevTools to find ways to make your websites load faster.</span></span>  

## <span data-ttu-id="a7e29-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="a7e29-106">Prerequisites</span></span>  

*   <span data-ttu-id="a7e29-107">この[Web 開発クラスの概要][CourseraIntroductionWebDevelopmentClass]で説明するように、基本的な web 開発環境を用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-107">You should have basic web development experience, similar to what is taught in this [Introduction to Web Development class][CourseraIntroductionWebDevelopmentClass].</span></span>  
*   <span data-ttu-id="a7e29-108">読み込みのパフォーマンスについて何も知りません。</span><span class="sxs-lookup"><span data-stu-id="a7e29-108">You do not need to know anything about load performance.</span></span>  <span data-ttu-id="a7e29-109">これについては、このチュートリアルで説明します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-109">You learn about it in this tutorial!</span></span>  

## <span data-ttu-id="a7e29-110">はじめに</span><span class="sxs-lookup"><span data-stu-id="a7e29-110">Introduction</span></span>   

<span data-ttu-id="a7e29-111">これは Tony です。</span><span class="sxs-lookup"><span data-stu-id="a7e29-111">This is Tony.</span></span>  <span data-ttu-id="a7e29-112">Tony は、cat 協会で非常に有名です。</span><span class="sxs-lookup"><span data-stu-id="a7e29-112">Tony is very famous in cat society.</span></span>  <span data-ttu-id="a7e29-113">彼は、お客様がお気に入りの食品について知ることができるように、web サイトを構築しました。</span><span class="sxs-lookup"><span data-stu-id="a7e29-113">He has built a website so that his fans are able to learn about his favorite foods.</span></span>  <span data-ttu-id="a7e29-114">Tony のファンは、サイトを気に入っていますが、サイトの読み込み速度が遅いという苦情を耳にしています。</span><span class="sxs-lookup"><span data-stu-id="a7e29-114">His fans love the site, but Tony keeps hearing complaints that the site loads slowly.</span></span>  <span data-ttu-id="a7e29-115">Tony から、サイトの速度を向上させるように求められました。</span><span class="sxs-lookup"><span data-stu-id="a7e29-115">Tony has asked you to help him speed the site up.</span></span>  

> ##### <span data-ttu-id="a7e29-116">図 1</span><span class="sxs-lookup"><span data-stu-id="a7e29-116">Figure 1</span></span>  
> <span data-ttu-id="a7e29-117">猫を Tony</span><span class="sxs-lookup"><span data-stu-id="a7e29-117">Tony the cat</span></span>  
> ![猫を Tony][ImageTony]  

## <span data-ttu-id="a7e29-119">手順 1: サイトを監査する</span><span class="sxs-lookup"><span data-stu-id="a7e29-119">Step 1: Audit the site</span></span>   

<span data-ttu-id="a7e29-120">サイトの読み込みのパフォーマンスを向上させるために、**必ず監査を開始して**ください。</span><span class="sxs-lookup"><span data-stu-id="a7e29-120">Whenever you set out to improve the load performance of a site, **always start with an audit**.</span></span>  
<span data-ttu-id="a7e29-121">監査には、次の2つの重要な機能があります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-121">The audit has 2 important functions:</span></span>  

*   <span data-ttu-id="a7e29-122">以降の変更を測定するための**基準計画**を作成します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-122">It creates a **baseline** for you to measure subsequent changes against.</span></span>  
*   <span data-ttu-id="a7e29-123">どのような変更が最も影響を与えるかに関する実用的な**ヒント**が提供されます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-123">It gives you **actionable tips** on what changes have the most impact.</span></span>  

### <span data-ttu-id="a7e29-124">設定</span><span class="sxs-lookup"><span data-stu-id="a7e29-124">Set up</span></span>   

<span data-ttu-id="a7e29-125">最初に、後で変更できるようにサイトを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-125">First, you must set up the site so that you are able to make changes to it later.</span></span>  

1.  <span data-ttu-id="a7e29-126">[サイトのソースコードを開き](https://glitch.com/edit/#!/tony)ます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-126">[Open the source code for the site](https://glitch.com/edit/#!/tony).</span></span>  <span data-ttu-id="a7e29-127">このタブは [**エディター] タブ**と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-127">This tab is referred to as the **editor tab**.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-128">図 2</span><span class="sxs-lookup"><span data-stu-id="a7e29-128">Figure 2</span></span>  
    > <span data-ttu-id="a7e29-129">[エディター] タブ</span><span class="sxs-lookup"><span data-stu-id="a7e29-129">The editor tab</span></span>  
    > ![[エディター] タブ][ImageEditor]  

1.  <span data-ttu-id="a7e29-131">[ **Tony**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-131">Select **tony**.</span></span>  <span data-ttu-id="a7e29-132">メニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-132">A menu appears.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-133">図 3</span><span class="sxs-lookup"><span data-stu-id="a7e29-133">Figure 3</span></span>  
    > <span data-ttu-id="a7e29-134">**Tony**をクリックした後に表示されるメニュー</span><span class="sxs-lookup"><span data-stu-id="a7e29-134">The menu that appears after clicking **tony**</span></span>  
    > ![Tony をクリックした後に表示されるメニュー][ImageMenu]  
    
1.  <span data-ttu-id="a7e29-136">[ **Remix Project**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-136">Select **Remix Project**.</span></span>  <span data-ttu-id="a7e29-137">プロジェクトの名前が**tony**からランダムに生成された名前に変更されます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-137">The name of the project changes from **tony** to some randomly-generated name.</span></span>  <span data-ttu-id="a7e29-138">これで、独自のコードの編集可能なコピーが作成されました。</span><span class="sxs-lookup"><span data-stu-id="a7e29-138">You now have your own editable copy of the code.</span></span>  <span data-ttu-id="a7e29-139">後で、このコードを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-139">Later on, you may make changes to this code.</span></span>  
1.  <span data-ttu-id="a7e29-140">[**表示**] を選択し、**新しいウィンドウで**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-140">Select **Show** and select **In a New Window**.</span></span>  <span data-ttu-id="a7e29-141">新しいタブでデモが開きます。 このタブは [**デモ] タブ**として参照されます。 サイトが読み込まれるまでには時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-141">The demo opens in a new tab.  This tab is be referred to as the **demo tab**.  It may take a while for the site to load.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-142">図 4</span><span class="sxs-lookup"><span data-stu-id="a7e29-142">Figure 4</span></span>  
    > <span data-ttu-id="a7e29-143">[デモ] タブ</span><span class="sxs-lookup"><span data-stu-id="a7e29-143">The demo tab</span></span>  
    > ![[デモ] タブ][ImageDemo]  

1.  <span data-ttu-id="a7e29-145">`Control` + `Shift` + `J` \ (Windows \) または `Command` + `Option` + `J` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-145">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\).</span></span>  <span data-ttu-id="a7e29-146">Microsoft Edge の DevTools がデモと共に開きます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-146">Microsoft Edge DevTools opens up alongside the demo.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-147">図 5</span><span class="sxs-lookup"><span data-stu-id="a7e29-147">Figure 5</span></span>  
    > <span data-ttu-id="a7e29-148">DevTools とデモ</span><span class="sxs-lookup"><span data-stu-id="a7e29-148">DevTools and the demo</span></span>  
    > ![DevTools とデモ][ImageDevtools]  

<span data-ttu-id="a7e29-150">このチュートリアルの残りのスクリーンショットでは、DevTools が別のウィンドウに表示されています。</span><span class="sxs-lookup"><span data-stu-id="a7e29-150">For the rest of the screenshots in this tutorial, DevTools is shown in a separate window.</span></span>  <span data-ttu-id="a7e29-151">`Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) キーを押すと、コマンドメニューが開き、入力した `Undock` 後、**別のウィンドウに装着解除**することができます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-151">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, typing `Undock`, and then selecting **Undock into separate window**.</span></span>  

> ##### <span data-ttu-id="a7e29-152">図 6</span><span class="sxs-lookup"><span data-stu-id="a7e29-152">Figure 6</span></span>  
> <span data-ttu-id="a7e29-153">アンドックした DevTools</span><span class="sxs-lookup"><span data-stu-id="a7e29-153">Undocked DevTools</span></span>  
> ![アンドックした DevTools][ImageUndocked]  

### <span data-ttu-id="a7e29-155">ベースラインを確立する</span><span class="sxs-lookup"><span data-stu-id="a7e29-155">Establish a baseline</span></span>   

<span data-ttu-id="a7e29-156">ベースラインは、パフォーマンスを向上させる前に、サイトがどのように実行されたかを記録したものです。</span><span class="sxs-lookup"><span data-stu-id="a7e29-156">The baseline is a record of how the site performed before you made any performance improvements.</span></span>  

1.  <span data-ttu-id="a7e29-157">[**監査**] タブを選択します。 **さら**に多くのパネルボタンが隠れている可能性があり ![ ][ImageMorePanelsIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-157">Select the **Audits** tab.  It may be hidden behind the **More Panels** ![More Panels][ImageMorePanelsIcon] button.</span></span>  <span data-ttu-id="a7e29-158">監査パネルを累乗するプロジェクトには、 **Lighthouse**という名前が付いているため、このパネルには Lighthouse があります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-158">There is a Lighthouse on this panel because the project that powers the Audits panel is named **Lighthouse**.</span></span>  
    
    [!INCLUDE [audits-panel-note](../includes/audits-panel-note.md)]  
    
    > ##### <span data-ttu-id="a7e29-159">図 7</span><span class="sxs-lookup"><span data-stu-id="a7e29-159">Figure 7</span></span>  
    > <span data-ttu-id="a7e29-160">監査パネル</span><span class="sxs-lookup"><span data-stu-id="a7e29-160">The Audits panel</span></span>  
    > ![監査パネル][ImageAudits]  
    
    <!--todo: add link to Lighthouse when section is available  -->  
    <!-- /web/tools/lighthouse  -->  
    
1.  <span data-ttu-id="a7e29-162">監査構成の設定を[図 7](#figure-7)の設定と一致させる。</span><span class="sxs-lookup"><span data-stu-id="a7e29-162">Match your audit configuration settings to those in [Figure 7](#figure-7).</span></span>  <span data-ttu-id="a7e29-163">さまざまなオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-163">Here is an explanation of the different options:</span></span>  

    *   <span data-ttu-id="a7e29-164">**デバイス**。</span><span class="sxs-lookup"><span data-stu-id="a7e29-164">**Device**.</span></span>  <span data-ttu-id="a7e29-165">[**モバイル**に設定] をオンにすると、ユーザーエージェント文字列が変更され、モバイルビューポートがシミュレートされます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-165">Setting to **Mobile** changes the user agent string and simulates a mobile viewport.</span></span>  <span data-ttu-id="a7e29-166">**デスクトップ**に設定することで、**モバイル**の変更が無効になります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-166">Setting to **Desktop** pretty much just disables the **Mobile** changes.</span></span>  
    *   <span data-ttu-id="a7e29-167">**監査**。</span><span class="sxs-lookup"><span data-stu-id="a7e29-167">**Audits**.</span></span>  <span data-ttu-id="a7e29-168">カテゴリを無効にすると、監査パネルでそれらの監査が実行されなくなり、レポートから監査が除外されます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-168">Disabling a category prevents the Audits panel from running those audits, and excludes those audits from your report.</span></span>  <span data-ttu-id="a7e29-169">提供されている推奨事項の種類を表示する場合は、その他のカテゴリを有効のままにします。</span><span class="sxs-lookup"><span data-stu-id="a7e29-169">Leave the other categories enabled, if you want to see the types of recommendations that are provide.</span></span>  <span data-ttu-id="a7e29-170">カテゴリを無効にすると、監査プロセスが少し速くなります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-170">Disabling categories slightly speeds up the auditing process.</span></span>  
    *   <span data-ttu-id="a7e29-171">**調整**。</span><span class="sxs-lookup"><span data-stu-id="a7e29-171">**Throttling**.</span></span>  <span data-ttu-id="a7e29-172">シミュレートされた**4g の4倍の CPU 速度**は、モバイルデバイスでの一般的な参照条件をシミュレートしています。</span><span class="sxs-lookup"><span data-stu-id="a7e29-172">Setting to **Simulated Slow 4G, 4x CPU Slowdown** simulates the typical conditions of browsing on a mobile device.</span></span>  <span data-ttu-id="a7e29-173">監査プロセス中に監査パネルで実際にスロットルされないので、"シミュレート" という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-173">It is named "simulated" because the Audits panel does not actually throttle during the auditing process.</span></span>  <span data-ttu-id="a7e29-174">代わりに、ページがモバイルの条件下で読み込むのにかかる時間を extrapolates だけです。</span><span class="sxs-lookup"><span data-stu-id="a7e29-174">Instead, it just extrapolates how long the page would take to load under mobile conditions.</span></span>  <span data-ttu-id="a7e29-175">一方、適用された [. **..** ] 設定では、より多くの監査プロセスの代わりに、CPU とネットワークのスロットルが実際に行われます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-175">The **Applied...** setting, on the other hand, actually throttles your CPU and network, with the tradeoff of a longer auditing process.</span></span>  
    *   <span data-ttu-id="a7e29-176">**ストレージをクリア**します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-176">**Clear Storage**.</span></span>  <span data-ttu-id="a7e29-177">このチェックボックスを有効にすると、ページに関連付けられているすべてのストレージが、各監査前に消去されます</span><span class="sxs-lookup"><span data-stu-id="a7e29-177">Enabling this checkbox clears all storage associated with the page before every audit.</span></span>  <span data-ttu-id="a7e29-178">この設定は、サイトでの初回の閲覧者の操作性を監査する場合にオンのままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-178">Leave this setting on if you want to audit how first-time visitors experience your site.</span></span>  <span data-ttu-id="a7e29-179">この設定は、ユーザーが繰り返しアクセスするときに無効にします。</span><span class="sxs-lookup"><span data-stu-id="a7e29-179">Disable this setting when you want the repeat-visit experience.</span></span>  

1.  <span data-ttu-id="a7e29-180">[**監査の実行**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-180">Select **Run Audits**.</span></span>  <span data-ttu-id="a7e29-181">10秒から30秒後に、監査パネルにサイトのパフォーマンスのレポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-181">After 10 to 30 seconds, the Audits panel shows you a report of the performance of the site.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-182">図 8</span><span class="sxs-lookup"><span data-stu-id="a7e29-182">Figure 8</span></span>  
    > <span data-ttu-id="a7e29-183">サイトのパフォーマンスの監査パネルのレポート</span><span class="sxs-lookup"><span data-stu-id="a7e29-183">The report for the Audits panel of the performance of the site</span></span>  
    > ![サイトのパフォーマンスの監査パネルのレポート][ImageReport]  

#### <span data-ttu-id="a7e29-185">レポートのエラーを処理する</span><span class="sxs-lookup"><span data-stu-id="a7e29-185">Handling report errors</span></span>   

<span data-ttu-id="a7e29-186">監査パネルレポートにエラーが表示された場合は、他のタブが開いていない**InPrivate**ウィンドウで [デモ] タブを実行してみてください。</span><span class="sxs-lookup"><span data-stu-id="a7e29-186">If you ever get an error in your Audits panel report, try running the demo tab from an **InPrivate** window with no other tabs open.</span></span>  <span data-ttu-id="a7e29-187">これにより、Microsoft Edge をクリーンな状態から実行することができます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-187">This ensures that you are running Microsoft Edge from a clean state.</span></span>  <span data-ttu-id="a7e29-188">特に Microsoft Edge Extensions は、監査プロセスの妨げになることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-188">Microsoft Edge Extensions in particular often interfere with the auditing process.</span></span>  

<!--todo: add screen capture for error in audit -->  
<!--
> ##### old Figure 9  
> A report that errored  
> ![A report that errored][ImageError]  
-->  

### <span data-ttu-id="a7e29-189">レポートを理解する</span><span class="sxs-lookup"><span data-stu-id="a7e29-189">Understand your report</span></span>   

<span data-ttu-id="a7e29-190">レポートの上部に表示される数値は、サイトの全体的なパフォーマンススコアです。</span><span class="sxs-lookup"><span data-stu-id="a7e29-190">The number at the top of your report is the overall performance score for the site.</span></span>  <span data-ttu-id="a7e29-191">後でコードを変更すると、この数値の増加が確認できます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-191">Later, as you make changes to the code, you should see this number rise.</span></span>  <span data-ttu-id="a7e29-192">高いスコアは、パフォーマンスが向上することを意味します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-192">A higher score means better performance.</span></span>  

> ##### <span data-ttu-id="a7e29-193">図 9</span><span class="sxs-lookup"><span data-stu-id="a7e29-193">Figure 9</span></span>  
> <span data-ttu-id="a7e29-194">全体的なパフォーマンススコア</span><span class="sxs-lookup"><span data-stu-id="a7e29-194">The overall performance score</span></span>  
> <span data-ttu-id="a7e29-195">![全体的なパフォーマンススコア][ImageOverall]</span><span class="sxs-lookup"><span data-stu-id="a7e29-195">![The overall performance score][ImageOverall]</span></span>  

<span data-ttu-id="a7e29-196">[**メトリック**] セクションには、サイトのパフォーマンスの定量的な測定値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-196">The **Metrics** section provides quantitative measurements of the performance of the site.</span></span>  <span data-ttu-id="a7e29-197">各メトリックは、パフォーマンスのさまざまな側面について把握します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-197">Each metric provides insight into a different aspect of the performance.</span></span>  <span data-ttu-id="a7e29-198">たとえば、**最初の Contentful 塗料**は、画面に最初にコンテンツが描画されたときに表示されます。これは、ユーザーがページの読み込みにおいて重要なマイルストーンであり、**対話型**のときには、ユーザーの操作を処理するのに必要なページが表示されている点を示します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-198">For example, **First Contentful Paint** tells you when content is first painted to the screen, which is an important milestone in the user's perception of the page load, whereas **Time To Interactive** marks the point at which the page appears ready enough to handle user interactions.</span></span>  

> ##### <span data-ttu-id="a7e29-199">図 10</span><span class="sxs-lookup"><span data-stu-id="a7e29-199">Figure 10</span></span>  
> <span data-ttu-id="a7e29-200">[メトリック] セクション</span><span class="sxs-lookup"><span data-stu-id="a7e29-200">The Metrics section</span></span>  
> <span data-ttu-id="a7e29-201">![Metrics] セクション[ImageMetrics]</span><span class="sxs-lookup"><span data-stu-id="a7e29-201">![The Metrics section][ImageMetrics]</span></span>  

<span data-ttu-id="a7e29-202">[図 11](#figure-11)の強調表示されたトグルボタンを選択して各指標の説明を表示し、[**詳細**情報] をクリックしてその概要に関するドキュメントを参照します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-202">Select the highlighted toggle button in [Figure 11](#figure-11) to see a description for each metric, and click **Learn More** to read documentation about it.</span></span>  

> ##### <span data-ttu-id="a7e29-203">図 11</span><span class="sxs-lookup"><span data-stu-id="a7e29-203">Figure 11</span></span>  
> <span data-ttu-id="a7e29-204">強調表示されたトグルボタンを選択して、[ **Metrics** ] 項目を展開する</span><span class="sxs-lookup"><span data-stu-id="a7e29-204">Select the highlighted toggle button to expand the **Metrics** items</span></span>  
> <span data-ttu-id="a7e29-205">![強調表示されているトグルボタンを選択して指標項目を展開する][ImageFirstMeaningfulPaint]</span><span class="sxs-lookup"><span data-stu-id="a7e29-205">![Select the highlighted toggle button to expand the Metrics items][ImageFirstMeaningfulPaint]</span></span>  

<span data-ttu-id="a7e29-206">メトリックの下には、ページが読み込まれたときにどのように見えるかを示すスクリーンショットのコレクションがあります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-206">Below Metrics is a collection of screenshots that show you how the page looked as it loaded.</span></span>  

> ##### <span data-ttu-id="a7e29-207">図 12</span><span class="sxs-lookup"><span data-stu-id="a7e29-207">Figure 12</span></span>  
> <span data-ttu-id="a7e29-208">ページの読み込み中の画面のスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="a7e29-208">Screenshots of how the page looked while loading</span></span>  
> <span data-ttu-id="a7e29-209">![読み込み中のページの外観のスクリーンショット][ImageScreenshots]</span><span class="sxs-lookup"><span data-stu-id="a7e29-209">![Screenshots of how the page looked while loading][ImageScreenshots]</span></span>  

<span data-ttu-id="a7e29-210">[**営業案件**] セクションでは、この特定のページの読み込みパフォーマンスを向上させるためのヒントを紹介します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-210">The **Opportunities** section provides specific tips on how to improve the load performance of this specific page.</span></span>  

> ##### <span data-ttu-id="a7e29-211">図 13</span><span class="sxs-lookup"><span data-stu-id="a7e29-211">Figure 13</span></span>  
> <span data-ttu-id="a7e29-212">[営業案件] セクション</span><span class="sxs-lookup"><span data-stu-id="a7e29-212">The Opportunities section</span></span>  
> <span data-ttu-id="a7e29-213">![営業案件] セクション[ImageOpportunities]</span><span class="sxs-lookup"><span data-stu-id="a7e29-213">![The Opportunities section][ImageOpportunities]</span></span>  

<span data-ttu-id="a7e29-214">詳細については、[営業案件] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-214">Select an opportunity to learn more about it.</span></span>  

> ##### <span data-ttu-id="a7e29-215">図 14</span><span class="sxs-lookup"><span data-stu-id="a7e29-215">Figure 14</span></span>  
> <span data-ttu-id="a7e29-216">**レンダーブロックリソースの機会を排除**する</span><span class="sxs-lookup"><span data-stu-id="a7e29-216">**Eliminate render-blocking resources** opportunity</span></span>  
> <span data-ttu-id="a7e29-217">![レンダーブロックリソースの機会の排除][ImageCompression]</span><span class="sxs-lookup"><span data-stu-id="a7e29-217">![Eliminate render-blocking resources opportunity][ImageCompression]</span></span>  

<span data-ttu-id="a7e29-218">[**詳細情報**] を選択して、営業案件が重要である理由と、その解決方法に関する具体的な推奨事項についてのドキュメントを表示します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-218">Select **Learn More** to see documentation about why an opportunity is important, and specific recommendations on how to fix it.</span></span>  

> ##### <span data-ttu-id="a7e29-219">図 15</span><span class="sxs-lookup"><span data-stu-id="a7e29-219">Figure 15</span></span>  
> <span data-ttu-id="a7e29-220">**レンダーブロックリソース**の機会を減らすためのドキュメント</span><span class="sxs-lookup"><span data-stu-id="a7e29-220">Documentation for the **Eliminate render-blocking resources** opportunity</span></span>  
> <span data-ttu-id="a7e29-221">![レンダーブロックリソースの機会の削減] のドキュメント[ImageReference]</span><span class="sxs-lookup"><span data-stu-id="a7e29-221">![Documentation for the Eliminate render-blocking resources opportunity][ImageReference]</span></span>  

<span data-ttu-id="a7e29-222">[**診断**] セクションには、ページの読み込み時間に影響する要因についての詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-222">The **Diagnostics** section provides more information about factors that contribute to the load time of the page.</span></span>  

> ##### <span data-ttu-id="a7e29-223">図 16</span><span class="sxs-lookup"><span data-stu-id="a7e29-223">Figure 16</span></span>  
> <span data-ttu-id="a7e29-224">[診断] セクション</span><span class="sxs-lookup"><span data-stu-id="a7e29-224">The Diagnostics section</span></span>  
> <span data-ttu-id="a7e29-225">![診断セクション][ImageDiagnostics]</span><span class="sxs-lookup"><span data-stu-id="a7e29-225">![The Diagnostics section][ImageDiagnostics]</span></span>  

<span data-ttu-id="a7e29-226">[**成功**した監査] セクションには、サイトが正常に動作していることが示されます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-226">The **Passed Audits** section shows you what the site is doing correctly.</span></span>  <span data-ttu-id="a7e29-227">セクションを展開する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-227">Select to expand the section.</span></span>  

> ##### <span data-ttu-id="a7e29-228">図 17</span><span class="sxs-lookup"><span data-stu-id="a7e29-228">Figure 17</span></span>  
> <span data-ttu-id="a7e29-229">[成功した監査] セクション</span><span class="sxs-lookup"><span data-stu-id="a7e29-229">The Passed Audits section</span></span>  
> <span data-ttu-id="a7e29-230">![成功した監査] セクション[ImagePassed]</span><span class="sxs-lookup"><span data-stu-id="a7e29-230">![The Passed Audits section][ImagePassed]</span></span>  

## <span data-ttu-id="a7e29-231">手順 2: 実験</span><span class="sxs-lookup"><span data-stu-id="a7e29-231">Step 2: Experiment</span></span>   

<span data-ttu-id="a7e29-232">監査レポートの [営業案件] セクションには、ページのパフォーマンスを向上させるためのヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-232">The Opportunities section of your audit report gives you tips on how to improve the performance of the page.</span></span>  <span data-ttu-id="a7e29-233">このセクションでは、コードベースへの推奨される変更を実装します。各変更の後でサイトを監査し、サイトの速度にどのような影響があるかを測定します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-233">In this section, you implement the recommended changes to the codebase, auditing the site after each change to measure how it affects site speed.</span></span>  

### <span data-ttu-id="a7e29-234">テキストの圧縮を有効にする</span><span class="sxs-lookup"><span data-stu-id="a7e29-234">Enable text compression</span></span>   

<span data-ttu-id="a7e29-235">レポートでは、大量のネットワークペイロードを回避することが、ページのパフォーマンスを向上させるための最上位の機会の1つであることを示しています。</span><span class="sxs-lookup"><span data-stu-id="a7e29-235">Your report says that avoiding enormous network payloads is one of the top opportunities for improving the performance of the page.</span></span>  <span data-ttu-id="a7e29-236">テキスト圧縮を有効にすると、ページのパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-236">Enabling text compression is an opportunity to improve the performance of the page.</span></span>  

<span data-ttu-id="a7e29-237">テキストファイルをネットワーク経由で送信する前に、テキストファイルのサイズを縮小 (圧縮) する場合。</span><span class="sxs-lookup"><span data-stu-id="a7e29-237">Text compression is when you reduce, or compress, the size of a text file before sending it over the network.</span></span>  <span data-ttu-id="a7e29-238">メールのサイズを小さくするためにメールを送信する前に、どのようにしてフォルダーを zip 圧縮するかなどです。</span><span class="sxs-lookup"><span data-stu-id="a7e29-238">Kind of like how you might zip a folder before emailing it to reduce the size.</span></span>  

<span data-ttu-id="a7e29-239">圧縮を有効にする前に、テキストリソースが圧縮されているかどうかを手動で確認する方法がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-239">Before you enable compression, here are a couple of ways to manually check whether text resources are compressed.</span></span>  

1.  <span data-ttu-id="a7e29-240">[**ネットワーク**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-240">Select the **Network** tab.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-241">図18</span><span class="sxs-lookup"><span data-stu-id="a7e29-241">Figure 18</span></span>  
    > <span data-ttu-id="a7e29-242">[ネットワーク] パネル</span><span class="sxs-lookup"><span data-stu-id="a7e29-242">The Network panel</span></span>  
    > <span data-ttu-id="a7e29-243">![ネットワークパネル][ImageNetwork]</span><span class="sxs-lookup"><span data-stu-id="a7e29-243">![The Network panel][ImageNetwork]</span></span>  
    
1.  <span data-ttu-id="a7e29-244">[**ネットワーク設定**] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-244">Select the **Network setting** icon.</span></span>  
1.  <span data-ttu-id="a7e29-245">[**大きな要求行を使用する**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a7e29-245">Select the **Use Large Request Rows** checkbox.</span></span>  <span data-ttu-id="a7e29-246">ネットワーク要求のテーブルの行の高さが増加します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-246">The height of the rows in the table of network requests increases.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-247">図19</span><span class="sxs-lookup"><span data-stu-id="a7e29-247">Figure 19</span></span>  
    > <span data-ttu-id="a7e29-248">ネットワーク要求テーブルの大きな行</span><span class="sxs-lookup"><span data-stu-id="a7e29-248">Large rows in the network requests table</span></span>  
    > <span data-ttu-id="a7e29-249">![ネットワーク要求テーブルの大きい行][ImageLargeRows]</span><span class="sxs-lookup"><span data-stu-id="a7e29-249">![Large rows in the network requests table][ImageLargeRows]</span></span>  
    
1.  <span data-ttu-id="a7e29-250">ネットワーク要求のテーブルに [**サイズ**] 列が表示されない場合は、テーブルの見出しをクリックして、[**サイズ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-250">If you do not see the **Size** column in the table of network requests, click the table header and then select **Size**.</span></span>  

<span data-ttu-id="a7e29-251">各**Size**セルには2つの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-251">Each **Size** cell shows two values.</span></span>  <span data-ttu-id="a7e29-252">上の値は、ダウンロードしたリソースのサイズです。</span><span class="sxs-lookup"><span data-stu-id="a7e29-252">The top value is the size of the downloaded resource.</span></span>  
<span data-ttu-id="a7e29-253">ボトム値は、圧縮されていないリソースのサイズです。</span><span class="sxs-lookup"><span data-stu-id="a7e29-253">The bottom value is the size of the uncompressed resource.</span></span>  <span data-ttu-id="a7e29-254">2つの値が同じである場合は、ネットワーク経由で送信されたときにリソースが圧縮されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-254">If the two values are the same, then the resource is not being compressed when it is sent over the network.</span></span>  <span data-ttu-id="a7e29-255">たとえば、[図 19](#figure-19)では、の上位と下位の値は and で指定し `bundle.js` `1.2 MB` `1.2 MB` ます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-255">For example, in [Figure 19](#figure-19) the top and bottom values for `bundle.js` are `1.2 MB` and `1.2 MB`.</span></span>  

<span data-ttu-id="a7e29-256">リソースの HTTP ヘッダーを調べて、圧縮を確認します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-256">Check for compression by inspecting the HTTP headers of a resource:</span></span>  

1.  <span data-ttu-id="a7e29-257">[ **Js**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-257">Select **bundle.js**.</span></span>  
1.  <span data-ttu-id="a7e29-258">[**ヘッダー** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-258">Select the **Headers** tab.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-259">図20</span><span class="sxs-lookup"><span data-stu-id="a7e29-259">Figure 20</span></span>  
    > <span data-ttu-id="a7e29-260">[ヘッダー] タブ</span><span class="sxs-lookup"><span data-stu-id="a7e29-260">The Headers tab</span></span>  
    > <span data-ttu-id="a7e29-261">![ヘッダー] タブ[ImageHeaders]</span><span class="sxs-lookup"><span data-stu-id="a7e29-261">![The Headers tab][ImageHeaders]</span></span>  
    
1.  <span data-ttu-id="a7e29-262">ヘッダーの [**応答ヘッダー** ] セクションを検索し `content-encoding` ます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-262">Search the **Response Headers** section for a `content-encoding` header.</span></span>  <span data-ttu-id="a7e29-263">圧縮されていないことを示すものは表示されません `bundle.js` 。</span><span class="sxs-lookup"><span data-stu-id="a7e29-263">You should not see one, meaning that `bundle.js` was not compressed.</span></span>  <span data-ttu-id="a7e29-264">リソースが圧縮されている場合、このヘッダーは通常、、またはに設定され `gzip` `deflate` `br` ます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-264">When a resource is compressed, this header is usually set to `gzip`, `deflate`, or `br`.</span></span>  <span data-ttu-id="a7e29-265">これらの値の説明については、「[ディレクティブ][MDNContentEncodingDirectives]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7e29-265">See [Directives][MDNContentEncodingDirectives] for an explanation of these values.</span></span>  

<span data-ttu-id="a7e29-266">説明が必要です。</span><span class="sxs-lookup"><span data-stu-id="a7e29-266">Enough with the explanations.</span></span>  <span data-ttu-id="a7e29-267">変更を加える時間</span><span class="sxs-lookup"><span data-stu-id="a7e29-267">Time to make some changes!</span></span>  <span data-ttu-id="a7e29-268">テキストの圧縮を有効にするには、数行のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-268">Enable text compression by adding a couple of lines of code:</span></span>  

1.  <span data-ttu-id="a7e29-269">[エディター] タブで、[**サーバー .js**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7e29-269">In the editor tab, click **server.js**.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-270">図21</span><span class="sxs-lookup"><span data-stu-id="a7e29-270">Figure 21</span></span>  
    > <span data-ttu-id="a7e29-271">サーバーの編集</span><span class="sxs-lookup"><span data-stu-id="a7e29-271">Editing server.js</span></span>  
    > <span data-ttu-id="a7e29-272">![編集サーバー .js][ImageServer]</span><span class="sxs-lookup"><span data-stu-id="a7e29-272">![Editing server.js][ImageServer]</span></span>  
    
1.  <span data-ttu-id="a7e29-273">次のコードを**サーバー .js**に追加します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-273">Add the following code to **server.js**.</span></span>  <span data-ttu-id="a7e29-274">前に必ず入力してください `app.use(compression())` `app.use(express.static('build'))` 。</span><span class="sxs-lookup"><span data-stu-id="a7e29-274">Make sure to put `app.use(compression())` before `app.use(express.static('build'))`.</span></span>  

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
    > <span data-ttu-id="a7e29-275">通常は、次のような方法でパッケージをインストールする必要があり `compression` `npm i -S compression` ますが、これは既に行われています。</span><span class="sxs-lookup"><span data-stu-id="a7e29-275">Usually, you have to install the `compression` package via something like `npm i -S compression`, but this has already been done for you.</span></span>  
    
1.  <span data-ttu-id="a7e29-276">サイトの新しいビルドが展開されるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-276">Wait for Glitch to deploy the new build of the site.</span></span>  <span data-ttu-id="a7e29-277">[**ツール**] の横にある凝ったアニメーションは、サイトが再構築されて再展開されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-277">The fancy animation next to **Tools** means that the site is getting rebuilt and redeployed.</span></span>  <span data-ttu-id="a7e29-278">[**ツール**] の横にあるアニメーションが消えると、変更がすぐにできます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-278">The change is ready when the animation next to **Tools** goes away.</span></span>  <span data-ttu-id="a7e29-279">[**表示**] を選択し、**新しいウィンドウで**もう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-279">Select **Show** and select **In a New Window** again.</span></span>  
    
    <!--
    > ##### Old Figure 22  
    > The animation that indicates that the site is getting built  
    > ![The animation that indicates that the site is getting built][ImageBuilding]  
    -->  
    
<span data-ttu-id="a7e29-280">以前に学習したワークフローを使用して、圧縮が機能していることを手動で確認します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-280">Use the workflows that you learned earlier to manually check that the compression is working:</span></span>  

1.  <span data-ttu-id="a7e29-281">[デモ] タブに戻り、ページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="a7e29-281">Go back to the demo tab and reload the page.</span></span>  <span data-ttu-id="a7e29-282">これで、[**サイズ**] 列に、次のようなテキストリソースの2つの異なる値が表示され `bundle.js` ます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-282">The **Size** column should now show 2 different values for text resources like `bundle.js`.</span></span>  <span data-ttu-id="a7e29-283">[図 23](#figure-23)では、[の最大値 `256 KB` `bundle.js` ] はネットワーク経由で送信されたファイルのサイズであり、の下の値は圧縮されていない `1.2 MB` ファイルサイズです。</span><span class="sxs-lookup"><span data-stu-id="a7e29-283">In [Figure 23](#figure-23) the top value of `256 KB` for `bundle.js` is the size of the file that was sent over the network, and the bottom value of `1.2 MB` is the uncompressed file size.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-284">図22</span><span class="sxs-lookup"><span data-stu-id="a7e29-284">Figure 22</span></span>  
    > <span data-ttu-id="a7e29-285">[サイズ] 列に、テキストリソースの2つの異なる値が表示されるようになりました</span><span class="sxs-lookup"><span data-stu-id="a7e29-285">The Size column now shows 2 different values for text resources</span></span>  
    > <span data-ttu-id="a7e29-286">![Size] 列には、テキストリソースに対して2つの異なる値が表示されるようになりました。[ImageRequests]</span><span class="sxs-lookup"><span data-stu-id="a7e29-286">![The Size column now shows 2 different values for text resources][ImageRequests]</span></span>  
    
1.  <span data-ttu-id="a7e29-287">[**応答ヘッダー** ] セクションに、 `bundle.js` ヘッダーを含めるようになりました `content-encoding: gzip` 。</span><span class="sxs-lookup"><span data-stu-id="a7e29-287">The **Response Headers** section for `bundle.js` should now include a `content-encoding: gzip` header.</span></span>
    
    > ##### <span data-ttu-id="a7e29-288">図23</span><span class="sxs-lookup"><span data-stu-id="a7e29-288">Figure 23</span></span>  
    > <span data-ttu-id="a7e29-289">応答ヘッダーセクションにコンテンツエンコードヘッダーが含まれるようになりました</span><span class="sxs-lookup"><span data-stu-id="a7e29-289">The Response Headers section now contains a content-encoding header</span></span>  
    > <span data-ttu-id="a7e29-290">![応答ヘッダー] セクションには、コンテンツエンコードヘッダーが含まれています。[ImageGzip]</span><span class="sxs-lookup"><span data-stu-id="a7e29-290">![The Response Headers section now contains a content-encoding header][ImageGzip]</span></span>  
    
<span data-ttu-id="a7e29-291">ページをもう一度監査して、ページの読み込みパフォーマンスにどのような影響があるかを測定します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-291">Audit the page again to measure what kind of impact text compression has on the load performance of the page:</span></span>  

1.  <span data-ttu-id="a7e29-292">[**監査**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-292">Select the **Audits** tab.</span></span>  
1.  <span data-ttu-id="a7e29-293">[**監査**の実行] を選択し ![ ][ImagePerformIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-293">Select **Perform an audit** ![Perform an audit][ImagePerformIcon].</span></span>  
1.  <span data-ttu-id="a7e29-294">設定は前の設定のままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-294">Leave the settings the same as before.</span></span>  
1.  <span data-ttu-id="a7e29-295">[**監査の実行**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-295">Select **Run audit**.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-296">図24</span><span class="sxs-lookup"><span data-stu-id="a7e29-296">Figure 24</span></span>  
    > <span data-ttu-id="a7e29-297">テキストの圧縮を有効にした後の監査レポート</span><span class="sxs-lookup"><span data-stu-id="a7e29-297">An Audits report after enabling text compression</span></span>  
    > <span data-ttu-id="a7e29-298">![テキスト圧縮を有効にした後の監査レポート][ImageReport2]</span><span class="sxs-lookup"><span data-stu-id="a7e29-298">![An Audits report after enabling text compression][ImageReport2]</span></span>  
    
<span data-ttu-id="a7e29-299">Woohoo!</span><span class="sxs-lookup"><span data-stu-id="a7e29-299">Woohoo!</span></span>  <span data-ttu-id="a7e29-300">進行状況のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-300">That looks like progress.</span></span>  <span data-ttu-id="a7e29-301">全体的なパフォーマンススコアは高くなります。つまり、サイトの速度が速くなります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-301">Your overall performance score should have increased, meaning that the site is getting faster.</span></span>  

#### <span data-ttu-id="a7e29-302">現実世界でのテキスト圧縮</span><span class="sxs-lookup"><span data-stu-id="a7e29-302">Text compression in the real world</span></span>   

<span data-ttu-id="a7e29-303">ほとんどのサーバーでは、圧縮を有効にするための単純な修正プログラムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="a7e29-303">Most servers really do have simple fixes like this for enabling compression!</span></span>  <span data-ttu-id="a7e29-304">テキストの圧縮に使用するサーバーを構成する方法について、検索を行うだけです。</span><span class="sxs-lookup"><span data-stu-id="a7e29-304">Just do a search on how to configure whatever server you use to compress text.</span></span>  

### <span data-ttu-id="a7e29-305">画像のサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="a7e29-305">Resize images</span></span>   

<span data-ttu-id="a7e29-306">レポートでは、大量のネットワークペイロードを回避することが、ページのパフォーマンスを向上させるための最上位の機会の1つであることを示しています。</span><span class="sxs-lookup"><span data-stu-id="a7e29-306">Your report indicates that avoiding enormous network payloads is one of the top opportunities for improving the performance of the page.</span></span>  <span data-ttu-id="a7e29-307">画像のサイズを変更すると、ネットワークペイロードのサイズを小さくすることができます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-307">Resizing images helps reduce the size of the network payload.</span></span>  <span data-ttu-id="a7e29-308">ユーザーが500ピクセル幅のモバイルデバイス画面で画像を表示している場合、1500ピクセル幅の画像を送信することはまったくありません。</span><span class="sxs-lookup"><span data-stu-id="a7e29-308">If your user is viewing your images on a mobile device screen that is 500-pixels-wide, there is really no point in sending a 1500-pixel-wide image.</span></span>  <span data-ttu-id="a7e29-309">理想的には、500ピクセル幅の画像を送信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a7e29-309">Ideally, you send a 500-pixel-wide image, at most.</span></span>  

1.  <span data-ttu-id="a7e29-310">レポートで、[**大量のネットワークペイロード**を使用しない] をクリックして、サイズを変更する画像を確認します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-310">In your report, click **Avoid enormous network payloads** to see which images should be resized.</span></span>  <span data-ttu-id="a7e29-311">Jpg ファイルのうち2つは 2000 KB を超えるようですが、これは必要以上に大きくなります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-311">It looks like 2 of the jpg files are over 2000 KB, which is bigger than necessary.</span></span>  
    
    <!--
    > ##### Old Figure 27  
    > Details about the **Properly size images** opportunity  
    > ![Details about the properly size images opportunity][ImageResize]  
    -->

1.  <span data-ttu-id="a7e29-312">[エディター] タブに戻り、[] を開き `src/model.js` ます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-312">Back in the editor tab, open `src/model.js`.</span></span>  
1.  <span data-ttu-id="a7e29-313">置換後 `const dir = 'big'` の文字列 `const dir = 'small'`</span><span class="sxs-lookup"><span data-stu-id="a7e29-313">Replace `const dir = 'big'` with `const dir = 'small'`.</span></span>  <span data-ttu-id="a7e29-314">このディレクトリには、サイズ変更された同じ画像のコピーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a7e29-314">This directory contains copies of the same images which have been resized.</span></span>  
1.  <span data-ttu-id="a7e29-315">この変更が読み込みのパフォーマンスにどのように影響するかを確認するには、ページをもう一度監査します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-315">Audit the page again to see how this change affects load performance.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-316">図25</span><span class="sxs-lookup"><span data-stu-id="a7e29-316">Figure 25</span></span>  
    > <span data-ttu-id="a7e29-317">画像のサイズを変更した後の監査レポート</span><span class="sxs-lookup"><span data-stu-id="a7e29-317">An Audits report after resizing images</span></span>  
    > <span data-ttu-id="a7e29-318">!(画像のサイズを変更した後の監査レポート)[ImageReport3]</span><span class="sxs-lookup"><span data-stu-id="a7e29-318">![An Audits report after resizing images][ImageReport3]</span></span>  

<span data-ttu-id="a7e29-319">変更は、全体的なパフォーマンススコアに対して軽微な影響を与えるようです。</span><span class="sxs-lookup"><span data-stu-id="a7e29-319">Looks like the change only has a minor affect on the overall performance score.</span></span>  <span data-ttu-id="a7e29-320">ただし、スコアが明確に表示されない場合は、ユーザーに保存されているネットワークデータの量です。</span><span class="sxs-lookup"><span data-stu-id="a7e29-320">However, one thing that the score does not show clearly is how much network data you are saving your users.</span></span>  <span data-ttu-id="a7e29-321">以前の写真の合計サイズは、5.3 mb になりましたが、現時点では 0.18 mb にすぎません。</span><span class="sxs-lookup"><span data-stu-id="a7e29-321">The total size of the old photos was around 5.3 megabytes, whereas now it is only about 0.18 megabytes.</span></span>  

#### <span data-ttu-id="a7e29-322">実際の画像のサイズ変更</span><span class="sxs-lookup"><span data-stu-id="a7e29-322">Resizing images in the real world</span></span>   

<span data-ttu-id="a7e29-323">小規模のアプリでは、1回限りのサイズ変更を行っても問題が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-323">For a small app, doing a one-off resize like this may be good enough.</span></span>  <span data-ttu-id="a7e29-324">ただし、大規模なアプリでは、このようなスケーラビリティはありません。</span><span class="sxs-lookup"><span data-stu-id="a7e29-324">But for a large app, this obviously is not scalable.</span></span>  <span data-ttu-id="a7e29-325">大規模なアプリでイメージを管理するためのいくつかの方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-325">Here are some strategies for managing images in large apps:</span></span>  

*   <span data-ttu-id="a7e29-326">ビルドプロセス中に画像のサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-326">Resize images during your build process.</span></span>  
*   <span data-ttu-id="a7e29-327">ビルドプロセス中に各画像のサイズを複数作成し、 `srcset` コードで使用します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-327">Create multiple sizes of each image during the build process and then use `srcset` in your code.</span></span>  <span data-ttu-id="a7e29-328">実行時には、ブラウザーは、デバイスに最適なサイズを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-328">At runtime, the browser takes care of choosing which size is best for the device.</span></span>  
    <!--See [Relative-sized images][relative].  -->

<!--[relative]: /web/fundamentals/design-and-ux/responsive/images#relative_sized_images  -->  

*   <span data-ttu-id="a7e29-329">要求時に画像のサイズを動的に変更できるようにするイメージ CDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-329">Use an image CDN that lets you dynamically resize an image when you request it.</span></span>  
*   <span data-ttu-id="a7e29-330">少なくとも、各画像を最適化します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-330">At the very least, optimize each image.</span></span>  <span data-ttu-id="a7e29-331">これにより、大幅に節約できます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-331">This may create huge savings.</span></span>  
  <span data-ttu-id="a7e29-332">最適化とは、画像ファイルのサイズを小さくする特殊なプログラムで画像を実行する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-332">Optimization is when you run an image through a special program that reduces the size of the image file.</span></span>  <span data-ttu-id="a7e29-333">その他のヒントについては、「[重要な画像の最適化][EssentialImageOptimization]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a7e29-333">See [Essential Image Optimization][EssentialImageOptimization] for more tips.</span></span>  

### <span data-ttu-id="a7e29-334">レンダーブロックリソースを排除する</span><span class="sxs-lookup"><span data-stu-id="a7e29-334">Eliminate render-blocking resources</span></span>   

<span data-ttu-id="a7e29-335">最新のレポートでは、レンダーブロックのリソースを除去することが最大の機会になりました。</span><span class="sxs-lookup"><span data-stu-id="a7e29-335">Your latest report says that eliminating render-blocking resources is now the biggest opportunity.</span></span>  

<span data-ttu-id="a7e29-336">レンダーブロックリソースは、ページを表示する前に、ブラウザーがダウンロード、解析、実行する必要がある外部 JavaScript または CSS ファイルです。</span><span class="sxs-lookup"><span data-stu-id="a7e29-336">A render-blocking resource is an external JavaScript or CSS file that the browser must download, parse, and run before it displays the page.</span></span>  <span data-ttu-id="a7e29-337">目的は、ページを適切に表示するために必要なコア CSS と JavaScript コードを実行することだけです。</span><span class="sxs-lookup"><span data-stu-id="a7e29-337">The goal is to only run the core CSS and JavaScript code that is required to display the page properly.</span></span>  

<span data-ttu-id="a7e29-338">最初のタスクでは、ページの読み込み時に実行する必要がないコードが検索されます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-338">The first task, then, is to find code that you do not need to run on page load.</span></span>  

1.  <span data-ttu-id="a7e29-339">[**レンダーブロックリソースの削除**] を選択して、ブロックされているリソースを確認します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-339">Select **Eliminate render-blocking resources** to see the resources that are blocking:</span></span>  
    `lodash.js` <span data-ttu-id="a7e29-340">および `jquery.js` 。</span><span class="sxs-lookup"><span data-stu-id="a7e29-340">and `jquery.js`.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-341">図26</span><span class="sxs-lookup"><span data-stu-id="a7e29-341">Figure 26</span></span>  
    > <span data-ttu-id="a7e29-342">**レンダーブロックリソース**の機会の削減に関するその他の情報</span><span class="sxs-lookup"><span data-stu-id="a7e29-342">More information about the **Eliminate render-blocking resources** opportunity</span></span>  
    > <span data-ttu-id="a7e29-343">![レンダーブロックリソースの機会の削減] の詳細情報[ImageRender]</span><span class="sxs-lookup"><span data-stu-id="a7e29-343">![More information about the Eliminate render-blocking resources opportunity][ImageRender]</span></span>  
    
1.  <span data-ttu-id="a7e29-344">`Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) キーを押してコマンドメニューを開き、入力を開始して、[ `Coverage` **カバレッジの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-344">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, start typing `Coverage`, and then select **Show Coverage**.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-345">図27</span><span class="sxs-lookup"><span data-stu-id="a7e29-345">Figure 27</span></span>  
    > <span data-ttu-id="a7e29-346">監査パネルからコマンドメニューを開く</span><span class="sxs-lookup"><span data-stu-id="a7e29-346">Opening the Command Menu from the Audits panel</span></span>  
    > <span data-ttu-id="a7e29-347">![監査パネルからコマンドメニューを開く][ImageCommandMenu]</span><span class="sxs-lookup"><span data-stu-id="a7e29-347">![Opening the Command Menu from the Audits panel][ImageCommandMenu]</span></span>  
    
    > ##### <span data-ttu-id="a7e29-348">図28</span><span class="sxs-lookup"><span data-stu-id="a7e29-348">Figure 28</span></span>  
    > <span data-ttu-id="a7e29-349">[カバレッジ] タブ</span><span class="sxs-lookup"><span data-stu-id="a7e29-349">The Coverage tab</span></span>  
    > <span data-ttu-id="a7e29-350">![範囲] タブ[ImageCoverage]</span><span class="sxs-lookup"><span data-stu-id="a7e29-350">![The Coverage tab][ImageCoverage]</span></span>  
    
1.  <span data-ttu-id="a7e29-351">[**更新の更新]** を選び ![ ][ImageRefreshIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-351">Select **Refresh** ![Refresh][ImageRefreshIcon].</span></span>  <span data-ttu-id="a7e29-352">[**カバレッジ**] タブには、ページの読み込み時にのコードの量の概要が表示され `bundle.js` `jquery.js` `lodash.js` ます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-352">The **Coverage** tab provides an overview of how much of the code in `bundle.js`, `jquery.js`, and `lodash.js` runs while the page loads.</span></span>  <span data-ttu-id="a7e29-353">[図 30](#figure-30)は、76% と JQuery と lodash のファイルの30% が使用されないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="a7e29-353">[Figure 30](#figure-30) says that about 76% and 30% of the jQuery and Lodash files are not used, respectively.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-354">図29</span><span class="sxs-lookup"><span data-stu-id="a7e29-354">Figure 29</span></span>  
    > <span data-ttu-id="a7e29-355">カバレッジレポート</span><span class="sxs-lookup"><span data-stu-id="a7e29-355">The Coverage report</span></span>  
    > <span data-ttu-id="a7e29-356">![カバレージレポート][ImageCoverageReport]</span><span class="sxs-lookup"><span data-stu-id="a7e29-356">![The Coverage report][ImageCoverageReport]</span></span>  
    
1.  <span data-ttu-id="a7e29-357">**Jquery**という行を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-357">Select the **jquery.js** row.</span></span>  <span data-ttu-id="a7e29-358">DevTools [ソース] パネルでファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-358">DevTools opens the file in the Sources panel.</span></span>  <span data-ttu-id="a7e29-359">横に青色のバーが表示されている場合は、コード行が実行されます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-359">A line of code ran if it has a blue bar next to it.</span></span>  <span data-ttu-id="a7e29-360">赤色のバーは、実行されなかったため、ページの読み込み時には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a7e29-360">A red bar means it was not run, and is definitely not needed on page load.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-361">図30</span><span class="sxs-lookup"><span data-stu-id="a7e29-361">Figure 30</span></span>  
    > <span data-ttu-id="a7e29-362">ソースパネルで jQuery ファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="a7e29-362">Viewing the jQuery file in the Sources panel</span></span>  
    > <span data-ttu-id="a7e29-363">![ソースパネルで jQuery ファイルを表示][ImageJQuery]</span><span class="sxs-lookup"><span data-stu-id="a7e29-363">![Viewing the jQuery file in the Sources panel][ImageJQuery]</span></span>  
    
1.  <span data-ttu-id="a7e29-364">JQuery コードを1ビットずつスクロールします。</span><span class="sxs-lookup"><span data-stu-id="a7e29-364">Scroll through the jQuery code a bit.</span></span>  <span data-ttu-id="a7e29-365">"実行" を取得する行の一部は、実際にはコメントにすぎません。</span><span class="sxs-lookup"><span data-stu-id="a7e29-365">Some of the lines that get "run" are actually just comments.</span></span>  <span data-ttu-id="a7e29-366">このコードを実行するときには、コメントを取り除くための別の方法として、このファイルのサイズを小さくする方法もあります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-366">Running this code through a minifier that strips comments is another way to reduce the size of this file.</span></span>  

<span data-ttu-id="a7e29-367">つまり、独自のコードを操作している場合、[カバレッジ] タブでは、コードの分析や行ごとの分析を行うことができます。また、ページの読み込みに必要なコードのみを提供します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-367">In short, when you are working with your own code, the Coverage tab helps you analyze your code, line-by-line, and only ship the code that is needed for page load.</span></span>  

<span data-ttu-id="a7e29-368">ページの `jquery.js` `lodash.js` 読み込みにもファイルが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="a7e29-368">Are the `jquery.js` and `lodash.js` files even needed to load the page?</span></span>  <span data-ttu-id="a7e29-369">[要求のブロック] タブには、リソースが利用できない場合の動作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-369">The Request Blocking tab displays what happens when resources are not available.</span></span>  

1.  <span data-ttu-id="a7e29-370">[**ネットワーク**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-370">Select the **Network** tab.</span></span>  
1.  <span data-ttu-id="a7e29-371">`Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) キーを押して、もう一度コマンドメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-371">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu again.</span></span>  
1.  <span data-ttu-id="a7e29-372">入力を開始し `blocking` 、[**要求ブロックの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-372">Start typing `blocking` and then select **Show Request Blocking**.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-373">図31</span><span class="sxs-lookup"><span data-stu-id="a7e29-373">Figure 31</span></span>  
    > <span data-ttu-id="a7e29-374">[要求のブロック] タブ</span><span class="sxs-lookup"><span data-stu-id="a7e29-374">The Request Blocking tab</span></span>  
    > <span data-ttu-id="a7e29-375">![要求のブロック] タブ[ImageBlocking]</span><span class="sxs-lookup"><span data-stu-id="a7e29-375">![The Request Blocking tab][ImageBlocking]</span></span>  
    
1.  <span data-ttu-id="a7e29-376">[模様の追加パターンの**追加**] を選択し、 ![ ][ImageAddPatternIcon] 「 `/libs/*` 」と入力して、 `Enter` 確認します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-376">Select **Add Pattern** ![Add Pattern][ImageAddPatternIcon], type `/libs/*`, and then press `Enter` to confirm.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-377">図32</span><span class="sxs-lookup"><span data-stu-id="a7e29-377">Figure 32</span></span>  
    > <span data-ttu-id="a7e29-378">ディレクトリへの要求をブロックするためのパターンを追加する `libs`</span><span class="sxs-lookup"><span data-stu-id="a7e29-378">Adding a pattern to block any request to the `libs` directory</span></span>  
    > <span data-ttu-id="a7e29-379">![パターンを追加して、ライブラリディレクトリへの要求をブロックする][Imagん Bs]</span><span class="sxs-lookup"><span data-stu-id="a7e29-379">![Adding a pattern to block any request to the libs directory][ImageLibs]</span></span>  
    
1.  <span data-ttu-id="a7e29-380">ページを最新の情報に更新してください。</span><span class="sxs-lookup"><span data-stu-id="a7e29-380">Refresh the page.</span></span>  <span data-ttu-id="a7e29-381">JQuery と Lodash の要求は赤で、要求がブロックされたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-381">The jQuery and Lodash requests are red, meaning that the requests were blocked.</span></span>   <span data-ttu-id="a7e29-382">ページは依然として読み込まれ、対話型であるため、これらのリソースは必要ではないようです。</span><span class="sxs-lookup"><span data-stu-id="a7e29-382">The page still loads and is interactive, so it looks like these resources are not needed whatsoever!</span></span>  
    
    > ##### <span data-ttu-id="a7e29-383">図33</span><span class="sxs-lookup"><span data-stu-id="a7e29-383">Figure 33</span></span>  
    > <span data-ttu-id="a7e29-384">[ネットワーク] パネルに、リクエストがブロックされていることが示される</span><span class="sxs-lookup"><span data-stu-id="a7e29-384">The Network panel shows that the requests have been blocked</span></span>  
    > <span data-ttu-id="a7e29-385">![ネットワーク] パネルには、リクエストがブロックされていることが示されます。[ImageBlockedLibs]</span><span class="sxs-lookup"><span data-stu-id="a7e29-385">![The Network panel shows that the requests have been blocked][ImageBlockedLibs]</span></span>  
    
1.  <span data-ttu-id="a7e29-386">[**すべてのパターンの削除**] を選択 ![ ][ImageRemoveIcon] すると、すべてのパターンが削除され、ブロックパターンが削除さ `/libs/*` れます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-386">Select **Remove all patterns** ![Remove all patterns][ImageRemoveIcon] to delete the `/libs/*` blocking pattern.</span></span>  

<span data-ttu-id="a7e29-387">一般的に、[要求のブロック] タブは、特定のリソースが利用できない場合にページがどのように動作するかをシミュレートするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-387">In general, the Request Blocking tab is useful for simulating how your page behaves when any given resource is not available.</span></span>  

<span data-ttu-id="a7e29-388">次に、これらのファイルへの参照をコードから削除して、ページをもう一度監査します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-388">Now, remove the references to these files from the code and audit the page again:</span></span>  

1.  <span data-ttu-id="a7e29-389">[エディター] タブに戻り、[] を開き `template.html` ます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-389">Back in the editor tab, open `template.html`.</span></span>  
1.  <span data-ttu-id="a7e29-390">`<script src="/libs/lodash.js">` と `<script src="/libs/jquery.js"></script>` を削除します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-390">Delete `<script src="/libs/lodash.js">` and `<script src="/libs/jquery.js"></script>`.</span></span>  
1.  <span data-ttu-id="a7e29-391">サイトが再構築され、再展開されるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-391">Wait for the site to re-build and re-deploy.</span></span>  
1.  <span data-ttu-id="a7e29-392">**監査パネルから**ページをもう一度監査します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-392">Audit the page again from the **Audits** panel.</span></span>  <span data-ttu-id="a7e29-393">全体的なスコアは、もう一度向上させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-393">Your overall score should have improved again.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-394">図34</span><span class="sxs-lookup"><span data-stu-id="a7e29-394">Figure 34</span></span>  
    > <span data-ttu-id="a7e29-395">レンダーブロックリソースを削除した後の監査レポート</span><span class="sxs-lookup"><span data-stu-id="a7e29-395">An Audits report after removing the render-blocking resources</span></span>  
    > <span data-ttu-id="a7e29-396">![レンダーブロックリソースを削除した後の監査レポート][ImageReport4]</span><span class="sxs-lookup"><span data-stu-id="a7e29-396">![An Audits report after removing the render-blocking resources][ImageReport4]</span></span>  

#### <span data-ttu-id="a7e29-397">現実世界での重大なレンダリングパスの最適化</span><span class="sxs-lookup"><span data-stu-id="a7e29-397">Optimizing the Critical Rendering Path in the real-world</span></span>   

<span data-ttu-id="a7e29-398">**クリティカルレンダリングパス**は、ページの読み込みに必要なコードを指します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-398">The **Critical Rendering Path** refers to the code that you need to load a page.</span></span>  <span data-ttu-id="a7e29-399">一般的には、ページの読み込み中にクリティカルコードのみを配布することにより、ページの読み込みを高速化し、その他のすべての機能を遅延読み込みします。</span><span class="sxs-lookup"><span data-stu-id="a7e29-399">In general, speed up page load by only shipping critical code during the page load, and then lazy-loading everything else.</span></span>  

<!--[CRP]: /web/fundamentals/performance/critical-rendering-path/  -->  

*   <span data-ttu-id="a7e29-400">完全に削除できるスクリプトを見つけることはできませんが、ページの読み込み中に要求する必要のないスクリプトが数多くあり、非同期で要求される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-400">It is unlikely that you are able to find scripts that you are able to remove outright, but you may find many scripts that you do not need to request during the page load, and instead may be requested asynchronously.</span></span>  <!--See [Using async or defer][async].  -->  
*   <span data-ttu-id="a7e29-401">フレームワークを使用している場合は、プロダクションモードであるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-401">If you are using a framework, check if it has a production mode.</span></span>  <span data-ttu-id="a7e29-402">このモードでは、重大なレンダリングをブロックしている不要なコードを取り除くために、[ツリーのシェイク][WebpackTreeShaking]などの機能を使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-402">This mode may use a feature such as [tree shaking][WebpackTreeShaking] in order to eliminate unnecessary code that is blocking the critical render.</span></span>  

<!--[async]: /web/fundamentals/performance/optimizing-content-efficiency/loading-third-party-javascript/#use_async_or_defer  -->  

### <span data-ttu-id="a7e29-403">メインスレッドの作業量を少なくする</span><span class="sxs-lookup"><span data-stu-id="a7e29-403">Do less main thread work</span></span>   

<span data-ttu-id="a7e29-404">最新のレポートでは、[営業案件] セクションで若干の節約が可能になりますが、[診断] セクションで確認すると、最大のボトルネックはメインスレッドのアクティビティが多すぎるようです。</span><span class="sxs-lookup"><span data-stu-id="a7e29-404">Your latest report shows some minor potential savings in the Opportunities section, but if you look down in the Diagnostics section, it looks like the biggest bottleneck is too much main thread activity.</span></span>  

<span data-ttu-id="a7e29-405">メインスレッドでは、HTML、CSS、JavaScript の解析や実行など、ページを表示するために必要な作業のほとんどがブラウザーで行われます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-405">The main thread is where the browser does most of the work needed to display a page, such as parsing and running HTML, CSS, and JavaScript.</span></span>  

<span data-ttu-id="a7e29-406">目標として、[パフォーマンス] パネルを使用して、ページの読み込み中にメインスレッドで実行されている作業を分析し、不要な作業を延期または削除する方法を見つけます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-406">The goal is to use the Performance panel to analyze what work the main thread is doing while the page loads, and find ways to defer or remove unnecessary work.</span></span>  

1.  <span data-ttu-id="a7e29-407">[**パフォーマンス**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-407">Select the **Performance** tab.</span></span>  
1.  <span data-ttu-id="a7e29-408">[**キャプチャ設定** ![ キャプチャの設定] を選択し ][ImageCaptureIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-408">Select **Capture Settings** ![Capture Settings][ImageCaptureIcon].</span></span>  
1.  <span data-ttu-id="a7e29-409">[**ネットワーク**] を [ **3g** ] と [ **CPU** ] から [ **6x**] の速度に設定します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-409">Set **Network** to **Slow 3G** and **CPU** to **6x slowdown**.</span></span>  <span data-ttu-id="a7e29-410">通常、モバイルデバイスでは、ノート pc やデスクトップよりも多くのハードウェア制約があります。そのため、これらの設定では、より強力なデバイスを使用している場合と同じようにページの読み込みを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-410">Mobile devices typically have more hardware constraints than laptops or desktops, so these settings let you experience the page load as if you were using a less powerful device.</span></span>  
1.  <span data-ttu-id="a7e29-411">[**更新の更新]** を選び ![ ][ImageRefreshIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-411">Select **Refresh** ![Refresh][ImageRefreshIcon].</span></span>  <span data-ttu-id="a7e29-412">DevTools はページを更新し、ページを読み込むために実行されたすべての作業の視覚エフェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-412">DevTools refreshes the page and then produces a visualization of all the work performed in order to load the page.</span></span>  <span data-ttu-id="a7e29-413">この視覚エフェクトは、**トレース**として参照されます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-413">This visualization is referred to as the **trace**.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-414">図35</span><span class="sxs-lookup"><span data-stu-id="a7e29-414">Figure 35</span></span>  
    > <span data-ttu-id="a7e29-415">ページの読み込みのパフォーマンスパネルトレース</span><span class="sxs-lookup"><span data-stu-id="a7e29-415">The Performance panel trace of the page load</span></span>  
    > <span data-ttu-id="a7e29-416">![ページの読み込みのパフォーマンスパネルトレース][ImagePerformance]</span><span class="sxs-lookup"><span data-stu-id="a7e29-416">![The Performance panel trace of the page load][ImagePerformance]</span></span>  

<span data-ttu-id="a7e29-417">トレースには、左から右へのアクティビティが時系列で表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-417">The trace shows activity chronologically, from left to right.</span></span>  <span data-ttu-id="a7e29-418">上の FPS、CPU、およびネットチャートでは、1秒あたりのフレーム数、CPU アクティビティ、ネットワークアクティビティの概要がわかります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-418">The FPS, CPU, and NET charts at the top give you an overview of frames per second, CPU activity, and network activity.</span></span>  <span data-ttu-id="a7e29-419">[図 37](#figure-37)に表示される黄色のブロックは、CPU がスクリプト処理によって完全にビジー状態であったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-419">The block of yellow selected that you see in [Figure 37](#figure-37) means that the CPU was completely busy with scripting activity.</span></span>  <span data-ttu-id="a7e29-420">これは、JavaScript の作業を少なくすることで、ページの読み込み速度を向上させることができることを示しています。</span><span class="sxs-lookup"><span data-stu-id="a7e29-420">This is a clue that you may be able to speed up page load by doing less JavaScript work.</span></span>  

> ##### <span data-ttu-id="a7e29-421">図36</span><span class="sxs-lookup"><span data-stu-id="a7e29-421">Figure 36</span></span>  
> <span data-ttu-id="a7e29-422">トレースの概要セクション</span><span class="sxs-lookup"><span data-stu-id="a7e29-422">The Overview section of the trace</span></span>  
> <span data-ttu-id="a7e29-423">![トレースの概要] セクション[ImageOverview]</span><span class="sxs-lookup"><span data-stu-id="a7e29-423">![The Overview section of the trace][ImageOverview]</span></span>  

<span data-ttu-id="a7e29-424">トレースを調べて、JavaScript の作業を軽減する方法を見つけます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-424">Investigate the trace to find ways to do less JavaScript work:</span></span>  

1.  <span data-ttu-id="a7e29-425">[**タイミング**] セクションを選択して展開します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-425">Select the **Timings** section to expand it.</span></span>  <span data-ttu-id="a7e29-426">反応しない[タイミング][MDNUserTimingApi]が存在する可能性があるという事実に基づいて、Tony のアプリでは、反応の開発モードが使用されているように見えます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-426">Based on the fact that there may be a bunch of [Timings][MDNUserTimingApi] measures from React, it seems like Tony's app is using the development mode of React.</span></span>  <span data-ttu-id="a7e29-427">処理の運用モードに切り替えると、パフォーマンスが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-427">Switching to the production mode of React may yield some easy performance wins.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-428">図37</span><span class="sxs-lookup"><span data-stu-id="a7e29-428">Figure 37</span></span>  
    > <span data-ttu-id="a7e29-429">[タイミング] セクション</span><span class="sxs-lookup"><span data-stu-id="a7e29-429">The Timings section</span></span>  
    > <span data-ttu-id="a7e29-430">![タイミング] セクション[ImageUserTiming]</span><span class="sxs-lookup"><span data-stu-id="a7e29-430">![The Timings section][ImageUserTiming]</span></span>  

1.  <span data-ttu-id="a7e29-431">[**タイミング**] をもう一度選択すると、そのセクションが折りたたまれます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-431">Select **Timings** again to collapse that section.</span></span>  
1.  <span data-ttu-id="a7e29-432">**メイン**セクションを参照します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-432">Browse the **Main** section.</span></span>  <span data-ttu-id="a7e29-433">このセクションでは、左から右へのメインスレッドアクティビティの時系列ログを示します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-433">This section shows a chronological log of main thread activity, from left to right.</span></span>  <span data-ttu-id="a7e29-434">Y 軸 (上から下) は、イベントが発生した理由を示しています。</span><span class="sxs-lookup"><span data-stu-id="a7e29-434">The y-axis (top to bottom) shows why events occurred.</span></span>  <span data-ttu-id="a7e29-435">たとえば、[図 39](#figure-39)では、このイベントによって関数が実行されていました。これは、実行の原因となった実行の原因 `Evaluate Script` となり `(anonymous)` `(anonymous)` `__webpack__require__` ます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-435">For example, in [Figure 39](#figure-39), the `Evaluate Script` event caused the `(anonymous)` function to run, which caused `(anonymous)` to run, which caused `__webpack__require__` to run, and so on.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-436">図38</span><span class="sxs-lookup"><span data-stu-id="a7e29-436">Figure 38</span></span>  
    > <span data-ttu-id="a7e29-437">メインセクション</span><span class="sxs-lookup"><span data-stu-id="a7e29-437">The Main section</span></span>  
    > <span data-ttu-id="a7e29-438">![メイン] セクション[ImageMain]</span><span class="sxs-lookup"><span data-stu-id="a7e29-438">![The Main section][ImageMain]</span></span>  

1.  <span data-ttu-id="a7e29-439">**メイン**セクションの下部まで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="a7e29-439">Scroll down to the bottom of the **Main** section.</span></span>  <span data-ttu-id="a7e29-440">フレームワークを使っている場合、ほとんどのアクティビティは、通常はコントロール以外のフレームワークによって発生します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-440">When you use a framework, most of the upper activity is caused by the framework, which is usually out of your control.</span></span>  <span data-ttu-id="a7e29-441">アプリが原因で発生するアクティビティは、通常、下部にあります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-441">The activity caused by your app is usually at the bottom.</span></span>  <span data-ttu-id="a7e29-442">このアプリでは、という名前の関数 `App` が多くの要求を処理しているように見え `mineBitcoin` ます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-442">In this app, it seems like a function named `App` is causing a lot of requests to a `mineBitcoin` function.</span></span>  <span data-ttu-id="a7e29-443">Tony のように、ファンのデバイスを使用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-443">It sounds like Tony might be using the devices of his fans to mine cryptocurrency...</span></span>  
    
    > ##### <span data-ttu-id="a7e29-444">図39</span><span class="sxs-lookup"><span data-stu-id="a7e29-444">Figure 39</span></span>  
    > <span data-ttu-id="a7e29-445">アクティビティの上にマウスポインターを置く `mineBitcoin`</span><span class="sxs-lookup"><span data-stu-id="a7e29-445">Hovering over the `mineBitcoin` activity</span></span>  
    > <span data-ttu-id="a7e29-446">![MineBitcoin アクティビティの上にマウスポインターを置く][ImageMine]</span><span class="sxs-lookup"><span data-stu-id="a7e29-446">![Hovering over the mineBitcoin activity][ImageMine]</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="a7e29-447">通常、フレームワークによって行われる要求はコントロールから除外されますが、フレームワークを効率的に実行するための方法でアプリを構成することもあります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-447">Although the requests that your framework makes are usually out of your control, sometimes you may structure your app in a way that causes the framework to run inefficiently.</span></span>  <span data-ttu-id="a7e29-448">フレームワークを効果的に使用するようにアプリを再構築することは、メインスレッドの作業を少なくするための手段です。</span><span class="sxs-lookup"><span data-stu-id="a7e29-448">Restructuring your app to use the framework efficiently is a way to do less main thread work.</span></span>  <span data-ttu-id="a7e29-449">ただし、フレームワークの動作について深く理解している必要があります。また、フレームワークをより効率的に使用するために、独自のコードで行った変更の種類についても理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7e29-449">However, this requires a deep understanding of how your framework works, and what kind of changes you make in your own code in order to use the framework more efficiently.</span></span>  

1.  <span data-ttu-id="a7e29-450">[**ボトムアップ**] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-450">Expand the **Bottom-Up** section.</span></span>  <span data-ttu-id="a7e29-451">このタブでは、最も時間がかかるアクティビティを中断します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-451">This tab breaks down what activities took up the most time.</span></span>  <span data-ttu-id="a7e29-452">下のセクションに何も表示されない場合は、**メイン**セクションのラベルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7e29-452">If you do not see anything in the Bottom-Up section, click the label for **Main** section.</span></span>  <span data-ttu-id="a7e29-453">**ボトムアップ**セクションには、現在選択されているすべてのアクティビティまたは活動のグループの情報のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-453">The **Bottom-Up** section only shows information for whatever activity, or group of activity, you have currently selected.</span></span>  <span data-ttu-id="a7e29-454">たとえば、アクティビティの1つをクリックした場合、 `mineBitcoin` **ボトムアップ**セクションには、その1つのアクティビティの情報のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-454">For example, if you clicked on one of the `mineBitcoin` activities, the **Bottom-Up** section is only going to show information for that one activity.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-455">図40</span><span class="sxs-lookup"><span data-stu-id="a7e29-455">Figure 40</span></span>  
    > <span data-ttu-id="a7e29-456">[ボトムアップ] タブ</span><span class="sxs-lookup"><span data-stu-id="a7e29-456">The Bottom-Up tab</span></span>  
    > <span data-ttu-id="a7e29-457">![ボトムアップ] タブ[Imageボトムアップ]</span><span class="sxs-lookup"><span data-stu-id="a7e29-457">![The Bottom-Up tab][ImageBottomUp]</span></span>  

<span data-ttu-id="a7e29-458">[**セルフ時刻**の列には、各アクティビティで直接費やした時間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-458">The **Self Time** column shows you how much time was spent directly in each activity.</span></span>  <span data-ttu-id="a7e29-459">たとえば、[図 41](#figure-41)は、メインスレッドの63% が関数に費やした時間を示してい `mineBitcoin` ます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-459">For example, [Figure 41](#figure-41) shows that about 63% of main thread time was spent on the `mineBitcoin` function.</span></span>  

<span data-ttu-id="a7e29-460">実行モードを使用し、JavaScript アクティビティを減らすことで、ページの読み込み速度を向上させることができるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-460">Time to see whether using production mode and reducing JavaScript activity may speed up the page load.</span></span>  <span data-ttu-id="a7e29-461">プロダクションモードで開始する:</span><span class="sxs-lookup"><span data-stu-id="a7e29-461">Start with production mode:</span></span>  

1.  <span data-ttu-id="a7e29-462">[エディター] タブで、を開き `webpack.config.js` ます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-462">In the editor tab, open `webpack.config.js`.</span></span>  
1.  <span data-ttu-id="a7e29-463">`"mode":"development"`をに変更 `"mode":"production"` します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-463">Change `"mode":"development"` to `"mode":"production"`.</span></span>  
1.  <span data-ttu-id="a7e29-464">新しいビルドが展開されるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-464">Wait for the new build to deploy.</span></span>  
1.  <span data-ttu-id="a7e29-465">ページをもう一度監査します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-465">Audit the page again.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-466">図41</span><span class="sxs-lookup"><span data-stu-id="a7e29-466">Figure 41</span></span>  
    > <span data-ttu-id="a7e29-467">プロダクションモードを使用するように webpack を構成した後の監査レポート</span><span class="sxs-lookup"><span data-stu-id="a7e29-467">An Audits report after configuring webpack to use production mode</span></span>  
    > <span data-ttu-id="a7e29-468">![運用モードを使用するように webpack を構成した後の監査レポート][ImageReport5]</span><span class="sxs-lookup"><span data-stu-id="a7e29-468">![An Audits report after configuring webpack to use production mode][ImageReport5]</span></span>  

<span data-ttu-id="a7e29-469">要求を削除して JavaScript のアクティビティを減らし `mineBitcoin` ます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-469">Reduce JavaScript activity by removing the request to `mineBitcoin`:</span></span>  

1.  <span data-ttu-id="a7e29-470">[エディター] タブで、を開き `src/App.jsx` ます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-470">In the editor tab, open `src/App.jsx`.</span></span>  
1.  <span data-ttu-id="a7e29-471">の要求をにコメントアウトし `this.mineBitcoin(1500)` `constructor` ます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-471">Comment out the request to `this.mineBitcoin(1500)` in the `constructor`.</span></span>  
1.  <span data-ttu-id="a7e29-472">新しいビルドが展開されるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-472">Wait for the new build to deploy.</span></span>  
1.  <span data-ttu-id="a7e29-473">ページをもう一度監査します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-473">Audit the page again.</span></span>  
    
    > ##### <span data-ttu-id="a7e29-474">図42</span><span class="sxs-lookup"><span data-stu-id="a7e29-474">Figure 42</span></span>  
    > <span data-ttu-id="a7e29-475">不要な JavaScript 作業を削除した後の監査レポート</span><span class="sxs-lookup"><span data-stu-id="a7e29-475">An Audits report after removing unnecessary JavaScript work</span></span>  
    > <span data-ttu-id="a7e29-476">![監査レポートの不要な JavaScript 作業を削除した後][ImageReport6]</span><span class="sxs-lookup"><span data-stu-id="a7e29-476">![An Audits report after removing unnecessary JavaScript work][ImageReport6]</span></span>  

<span data-ttu-id="a7e29-477">前回の変更によってパフォーマンスが大幅に向上したようです。</span><span class="sxs-lookup"><span data-stu-id="a7e29-477">Looks like that last change caused a massive jump in performance!</span></span>  

> [!NOTE]
> <span data-ttu-id="a7e29-478">このセクションでは、パフォーマンスパネルについて簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-478">This section provided a rather brief introduction to the Performance panel.</span></span>  <span data-ttu-id="a7e29-479">ページのパフォーマンスを分析する方法について詳しくは、「[パフォーマンス分析のリファレンス][DevtoolsEvaluatePerformanceReference]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a7e29-479">See [Performance Analysis Reference][DevtoolsEvaluatePerformanceReference] to learn more about how to analyze page performance.</span></span>  

<!--todo: add section when available -->  

#### <span data-ttu-id="a7e29-480">実際の環境でのメインスレッドの使用量を少なくする</span><span class="sxs-lookup"><span data-stu-id="a7e29-480">Doing less main thread work in the real world</span></span>   

<span data-ttu-id="a7e29-481">一般的に、**パフォーマンス**パネルは、サイトが読み込むときのアクティビティを理解するための最も一般的な方法です。また、不要なアクティビティを削除する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="a7e29-481">In general, the **Performance** panel is the most common way to understand what activity your site does as it loads, and find ways to remove unnecessary activity.</span></span>  

<span data-ttu-id="a7e29-482">もっと気に入ったアプローチが必要な場合は、 `console.log()` [ユーザーのタイミング API][MDNUserTimingApi]を使用して、各フェーズの所要時間を追跡するために、アプリのライフサイクルの特定のフェーズを任意にマークすることができます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-482">If you prefer an approach that feels more like `console.log()`, the [User Timing API][MDNUserTimingApi] enables you to arbitrarily mark up certain phases of your app lifecycle, in order to track how long each of those phases takes.</span></span>  

## <span data-ttu-id="a7e29-483">まとめ</span><span class="sxs-lookup"><span data-stu-id="a7e29-483">Summary</span></span>   

*   <span data-ttu-id="a7e29-484">サイトの読み込みパフォーマンスを最適化するために、必ず監査を開始してください。</span><span class="sxs-lookup"><span data-stu-id="a7e29-484">Whenever you set out to optimize the load performance of a site, always start with an audit.</span></span>  <span data-ttu-id="a7e29-485">監査によって基準計画が設定され、改善のヒントを得ることができます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-485">The audit establishes a baseline, and gives you tips on how to improve.</span></span>  
*   <span data-ttu-id="a7e29-486">一度に1つずつ変更し、そのたびにページがどのように変化するかを確認するために、個別に変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-486">Make one change at a time, and audit the page after each change in order to see how that isolated change affects performance.</span></span>  

<!--
## Next steps   

*   Run audits on your own site!  If you need help interpreting your report, or finding ways to improve your load performance, check out [Feedback](#feedback) for ways to get help from the DevTools community.  Stack Overflow, the mailing list, or Twitter are probably best for these types of questions.  
*   Please leave [feedback](#feedback) on this tutorial.  I really do use the data to make better tutorials for you.  
-->  

<!--    -->  



<!-- image links -->  

[ImageAddPatternIcon]: /microsoft-edge/devtools-guide-chromium/media/add-pattern-icon.msft.png  
[ImageCaptureIcon]: /microsoft-edge/devtools-guide-chromium/media/capture-icon.msft.png  
[ImageLargeResourceRowsButtonIcon]: /microsoft-edge/devtools-guide-chromium/media/large-resource-rows-button-icon.msft.png  
[ImageMorePanelsIcon]: /microsoft-edge/devtools-guide-chromium/media/more-panels-icon.msft.png  
[ImagePerformIcon]: /microsoft-edge/devtools-guide-chromium/media/perform-icon.msft.png  
[ImageRefreshIcon]: /microsoft-edge/devtools-guide-chromium/media/reload-icon.msft.png  
[ImageRemoveIcon]: /microsoft-edge/devtools-guide-chromium/media/remove-icon.msft.png  

[ImageTony]: /microsoft-edge/devtools-guide-chromium/media/speed-tony.msft.png "図 1: 猫を Tony"  
[ImageEditor]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-server-js.msft.png "図 2: [エディター] タブ"  
[ImageMenu]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-server-js-remix-project.msft.png "図 3: [tony] をクリックした後に表示されるメニュー"  
[ImageDemo]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-show-live.msft.png "図 4: [デモ] タブ"  
[ImageDevtools]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-show-live-console.msft.png "図 5: DevTools とデモ"  
[ImageUndocked]: /microsoft-edge/devtools-guide-chromium/media/speed-console.msft.png "図 6: アンドックした DevTools"  
[ImageAudits]: /microsoft-edge/devtools-guide-chromium/media/speed-audits-performance.msft.png "図 7: 監査パネル"  
[ImageReport]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png "図 8: サイトのパフォーマンスの監査パネルのレポート"  
<!--[ImageError]: /microsoft-edge/devtools-guide-chromium/media/speed-.msft.png "Old Figure 9: A report that errored"  -->  
[ImageOverall]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png "図 9: 全体的なパフォーマンススコア"  
[ImageMetrics]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png "図 10: メトリックセクション"  
[ImageFirstMeaningfulPaint]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png "図 11: 強調表示されたトグルボタンを選択して、メトリクス項目を展開する"  
[ImageScreenshots]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png "図 12: 読み込み中のページの外観のスクリーンショット"  
[ImageOpportunities]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-opportunities.msft.png "図 13: 営業案件セクション"  
[ImageCompression]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png "図 14: レンダーブロックリソースの営業案件を除去する"  
[ImageReference]:/microsoft-edge/devtools-guide-chromium/media/speed-web-dev-performance-audits.msft.png "図 15: レンダーブロックリソースの機会を減らすためのドキュメント"  
[ImageDiagnostics]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png "図 16: 診断セクション"  
[ImagePassed]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png "図 17: 成功した監査セクション"  
[ImageNetwork]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-network.msft.png "図 18: [ネットワーク] パネル  
[ImageLargeRows]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png "図 19: ネットワーク要求テーブルの大きな行"  
[ImageHeaders]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png "図 20: [ヘッダー] タブ  
[ImageServer]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-server-js.msft.png "図 21: サーバーの編集"  
<!--[ImageBuilding]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-server-js-edited.msft.png "Old Figure 22: The animation that indicates that the site is getting built"  -->  
[ImageRequests]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-network-main.msft.png "図 22: Size 列にテキストリソースの2つの異なる値が表示されるようになりました"  
[ImageGzip]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png "図 23: 応答ヘッダーセクションにヘッダーが表示されるようになりました `content-encoding` "  
[ImageReport2]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance.msft.png "図 24: テキストの圧縮を有効にした後の監査レポート"  
<!--[ImageResize]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png "Old Figure 27: Details about the properly size images opportunity"  -->
[ImageReport3]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-compression-small-images-audits-performance.msft.png "図 25: 画像のサイズを変更した後の監査レポート"  
[ImageRender]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png "図 26: レンダーブロックリソースの機会の削減」に関する詳細情報  
[ImageCommandMenu]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png "図 27: [監査] パネルからコマンドメニューを開く」  
[ImageCoverage]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png "Figure 28: [カバレッジ] タブ  
[ImageCoverageReport]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png "図 29: カバレッジレポート"  
[ImageJQuery]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png "図 30: ソースパネルでの jQuery ファイルの表示"  
[ImageBlocking]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png "図 31: [要求のブロック] タブ"  
[Imagん Bs]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png "図 32: パターンを追加して、ライブラリディレクトリへの要求をブロックする"
[ImageLibs]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png "Figure 32: Adding a pattern to block any request to the libs directory"  
[ImageBlockedLibs]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png "図 33: ネットワークパネルに要求がブロックされていることが示されています"  
[ImageReport4]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png "図 34: レンダーブロックリソースを削除した後の監査レポート"  
[ImagePerformance]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png "図 35: ページの読み込みのパフォーマンスパネルトレース  
[ImageOverview]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png "図 36: トレースの概要セクション  
[ImageUserTiming]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png "図 37: タイミングセクション"  
[ImageMain]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png "図 38: メインセクション"  
[ImageMine]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png "図 39: mineBitcoin アクティビティをマウスでポイントする  
[Imagebottom Up]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png "図 40: ボトムアップタブ"
[ImageBottomUp]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png "Figure 40: The Bottom-Up tab"  
[ImageReport5]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png "図 41: webpack を使用して運用モードを使うように構成した後の監査レポート  
[ImageReport6]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png "図 42: 不要な JavaScript 作業を削除した後の監査レポート"  

<!-- links -->  

[DevtoolsEvaluatePerformanceReference]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference "業績分析のリファレンス"  

[CourseraIntroductionWebDevelopmentClass]: https://www.coursera.org/learn/web-development#syllabus "Web 開発クラスの概要 |Coursera"  

[EssentialImageOptimization]: https://images.guide "基本的な画像の最適化"  

[MDNContentEncodingDirectives]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Encoding#Directives "ディレクティブ-コンテンツのエンコード |MDN"  
[MDNUserTimingApi]: https://developer.mozilla.org/docs/Web/API/User_Timing_API "ユーザーのタイミング API |MDN"  

[WebpackTreeShaking]: https://webpack.js.org/guides/tree-shaking "木のぶれ |webpack"  

> [!NOTE]
> <span data-ttu-id="a7e29-535">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="a7e29-535">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="a7e29-536">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/speed/get-started)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="a7e29-536">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/speed/get-started) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="a7e29-538">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="a7e29-538">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
