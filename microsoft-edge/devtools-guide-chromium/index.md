---
description: Microsoft Edge (Chromium) 開発者ツールについて
title: Microsoft Edge (Chromium) 開発者ツールの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 7f9a4288980dd938a43b229e1d5396adc7937c67
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597011"
---
# <a name="microsoft-edge-chromium-developer-tools-overview"></a><span data-ttu-id="9858c-104">Microsoft Edge (Chromium) 開発者ツールの概要</span><span class="sxs-lookup"><span data-stu-id="9858c-104">Microsoft Edge (Chromium) Developer Tools overview</span></span>  

<span data-ttu-id="9858c-105">アプリケーションをインストールするとMicrosoft Edgeブラウザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9858c-105">When you install Microsoft Edge, you get a browser.</span></span> <span data-ttu-id="9858c-106">また、Web プロジェクトを検査、デバッグ、作成する強力な方法も提供します。</span><span class="sxs-lookup"><span data-stu-id="9858c-106">Also, you get a powerful way to inspect, debug, and even create web projects.</span></span>  <span data-ttu-id="9858c-107">ブラウザーに同梱されている開発者ツールは、Chromium オープンソース プロジェクトのツールに基づいて作成されます。そのため、ツールに関する理解が既にある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9858c-107">The Developer Tools shipped with the browser are based on the tools in the Chromium open-source project, so you may already be familiar with the tools.</span></span>  <span data-ttu-id="9858c-108">この記事では、説明を短くするために、 と `Microsoft Edge Developer Tools` 呼ばれます `DevTools` 。</span><span class="sxs-lookup"><span data-stu-id="9858c-108">To keep descriptions shorter in this article, the `Microsoft Edge Developer Tools` are now referred to as `DevTools` .</span></span>  

<span data-ttu-id="9858c-109">DevTools を使用して、次の開発タスクについて確認し、詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="9858c-109">Use DevTools to review and learn more about the following development tasks.</span></span>  

*   <span data-ttu-id="9858c-110">[ブラウザーで現在の Web ページのライブを][DevtoolsGuideDomIndex] 検査および変更します。</span><span class="sxs-lookup"><span data-stu-id="9858c-110">[Inspect and change the current webpage][DevtoolsGuideDomIndex] live in the browser.</span></span>  
*   <span data-ttu-id="9858c-111">[製品が異なるデバイスでどのように動作するのかをエミュレートし、][DevtoolsGuideDeviceModeIndex] 異なるネットワーク条件を満たしたモバイル環境をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="9858c-111">[Emulate how your product behaves on different devices][DevtoolsGuideDeviceModeIndex] and simulate a mobile environment complete with different network conditions.</span></span>  
*   <span data-ttu-id="9858c-112">[ビジュアル インターフェイスを備えるライブ ツール][DevtoolsGuideInspectStylesEditFonts] を使用して、Web ページ内の要素のスタイルを検査、調整、および変更します。</span><span class="sxs-lookup"><span data-stu-id="9858c-112">[Inspect, tweak, and change the styles of elements][DevtoolsGuideInspectStylesEditFonts] in the webpage using live tools with a visual interface.</span></span>  
*   <span data-ttu-id="9858c-113">[ブレークポイントのデバッグとライブ][DevtoolsGuideJavascriptIndex] コンソールを使用して JavaScript [をデバッグします][DevtoolsGuideConsoleIndex]。</span><span class="sxs-lookup"><span data-stu-id="9858c-113">[Debug your JavaScript][DevtoolsGuideJavascriptIndex] using breakpoint debugging and with the [live console][DevtoolsGuideConsoleIndex].</span></span>  
*   <span data-ttu-id="9858c-114">製品 [のアクセシビリティ、パフォーマンス、互換性][DevtoolsGuideIssuesIndex] 、セキュリティの問題を確認し、DevTools を使用してそれぞれの問題を解決する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9858c-114">Find [accessibility, performance, compatibility, and security issues][DevtoolsGuideIssuesIndex] in your products and learn how to use DevTools to fix each.</span></span>  
*   <span data-ttu-id="9858c-115">[ネットワーク トラフィックを検査し][DevtoolsGuideNetworkIndex] 、問題の場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="9858c-115">[Inspect the network traffic][DevtoolsGuideNetworkIndex] and review the location of the problems.</span></span>  
*   <span data-ttu-id="9858c-116">[ブラウザーがコンテンツをさまざまな形式で保存][DevtoolsGuideStorageSessionstorage] した場所を調します。</span><span class="sxs-lookup"><span data-stu-id="9858c-116">[Inspect where the browser stored content][DevtoolsGuideStorageSessionstorage] in various formats.</span></span>  
*   <span data-ttu-id="9858c-117">[製品のパフォーマンスを][DevtoolsGuideEvaluatePerformanceIndex] 評価して、メモリの問題 [とレンダリングの][DevtoolsGuideMemoryProblemsIndex] 問題 [を見つける][DevtoolsGuideRenderingToolsIndex]。</span><span class="sxs-lookup"><span data-stu-id="9858c-117">[Evaluate the performance][DevtoolsGuideEvaluatePerformanceIndex] of your product to find [memory problems][DevtoolsGuideMemoryProblemsIndex] and [rendering issues][DevtoolsGuideRenderingToolsIndex].</span></span>  
*   <span data-ttu-id="9858c-118">[開発環境を使用して][DevtoolsGuideSourcesIndex][、DevTools][DevtoolsGuideWorkspacesIndex]の変更をファイル システムと同期し、Web[からファイル][DevtoolsGuideJavascriptOverrides]を上書きします。</span><span class="sxs-lookup"><span data-stu-id="9858c-118">[Use a development environment][DevtoolsGuideSourcesIndex] to [sync changes in DevTools with the file system][DevtoolsGuideWorkspacesIndex] and [override files][DevtoolsGuideJavascriptOverrides] from the web.</span></span>  
    
<!-- Is the link meant to be local or session storage for "inspect where the browser stored content"? -->  

<span data-ttu-id="9858c-119">そして、より多くの。</span><span class="sxs-lookup"><span data-stu-id="9858c-119">And a lot more.</span></span>  <span data-ttu-id="9858c-120">すべては、DevTools を開き、各ツールをニーズに合わせてカスタマイズするときに開始されます。</span><span class="sxs-lookup"><span data-stu-id="9858c-120">It all starts when you open DevTools and customize each tool to your needs.</span></span>  

## <a name="open-the-devtools"></a><span data-ttu-id="9858c-121">DevTools を開く</span><span class="sxs-lookup"><span data-stu-id="9858c-121">Open the DevTools</span></span>  

<span data-ttu-id="9858c-122">DevTools を開いて探索するには、次のいずれかのアクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="9858c-122">To open and explore the DevTools, use one any of the following actions.</span></span>  

*   <span data-ttu-id="9858c-123">Web ページ上の任意の要素にカーソルを合わせると、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9858c-123">Hover on any element on the webpage, open the contextual menu \(right-click\), and then choose **Inspect**.</span></span>  <span data-ttu-id="9858c-124">このアクションを実行すると、[要素] **ツールが開** きます。</span><span class="sxs-lookup"><span data-stu-id="9858c-124">This action opens the **Elements** tool.</span></span>  
*   <span data-ttu-id="9858c-125">`F12` を選択します。</span><span class="sxs-lookup"><span data-stu-id="9858c-125">Select `F12`.</span></span>  
*   <span data-ttu-id="9858c-126">`Ctrl` + `Shift` + `I` [Windows/Linux または `Command` + `Option` + `I` macOS で選択します。</span><span class="sxs-lookup"><span data-stu-id="9858c-126">Select `Ctrl`+`Shift`+`I` on Windows/Linux or `Command`+`Option`+`I` on macOS.</span></span>  
    
:::row:::  
   :::column span="":::  
      :::image type="complex" source="./media/devtools-intro-inspect.msft.png" alt-text="任意の要素のコンテキスト メニューから [検査] を選択する" lightbox="./media/devtools-intro-inspect.msft.png":::  
         <span data-ttu-id="9858c-128">任意 **の要素の** コンテキスト メニューから [検査] を選択する</span><span class="sxs-lookup"><span data-stu-id="9858c-128">Choose **Inspect** from the contextual menu on any element</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::  
      :::image type="complex" source="./media/devtools-intro-inspect-devtools-open.png" alt-text="選択した要素が強調表示された DevTools が開きます" lightbox="./media/devtools-intro-inspect-devtools-open.png":::  
         <span data-ttu-id="9858c-130">選択した要素が強調表示された DevTools が開きます</span><span class="sxs-lookup"><span data-stu-id="9858c-130">The DevTools opens with the chosen element highlighted</span></span>  
      :::image-end:::  
   :::column-end:::  
:::row-end:::  

<span data-ttu-id="9858c-131">DevTools を操作するには、主に 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="9858c-131">There are two main ways to interact with the DevTools.</span></span>
*   <span data-ttu-id="9858c-132">マウスを使用する</span><span class="sxs-lookup"><span data-stu-id="9858c-132">Use the mouse</span></span>  
*   <span data-ttu-id="9858c-133">[キーボード ショートカット][DevtoolsGuideShortcutsIndex]。</span><span class="sxs-lookup"><span data-stu-id="9858c-133">[Keyboard shortcuts][DevtoolsGuideShortcutsIndex].</span></span>  <span data-ttu-id="9858c-134">キーボード ショートカットは、機能にすばやくアクセスする方法を提供し、アクセシビリティのために必要です。</span><span class="sxs-lookup"><span data-stu-id="9858c-134">Keyboard shortcuts provide a quick way to access functionality and are needed for accessibility.</span></span>  <span data-ttu-id="9858c-135">DevTools Microsoft Edgeチームは、キーボードやスクリーン リーダーなどの支援テクノロジを使用してすべてのツールを利用できる環境に一生懸命取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="9858c-135">The Microsoft Edge DevTools team works hard to make all the tools available using the keyboard and assistive technologies such as screen readers.</span></span>  <span data-ttu-id="9858c-136">DevTools でさまざまな機能を開く方法の詳細については、「DevTools キーボード ショートカット[」Microsoft Edgeに移動します][DevtoolsGuideOpenIndex]。</span><span class="sxs-lookup"><span data-stu-id="9858c-136">For more information about how to open the different features in the DevTools, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevtoolsGuideOpenIndex].</span></span>  

## <a name="dock-the-devtools-in-your-browser"></a><span data-ttu-id="9858c-137">ブラウザーに DevTools をドッキングする</span><span class="sxs-lookup"><span data-stu-id="9858c-137">Dock the DevTools in your browser</span></span>  

<span data-ttu-id="9858c-138">DevTools を開いた場合、ブラウザーの左側にドッキングされます。</span><span class="sxs-lookup"><span data-stu-id="9858c-138">When you open the DevTools, it docks to the left of your browser.</span></span>  <span data-ttu-id="9858c-139">DevTools のドッキング位置を変更するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="9858c-139">To change the docked location of the DevTools, complete the following actions.</span></span>  

1.  <span data-ttu-id="9858c-140">**[DevTools のカスタマイズと制御]** \( `...` \) ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="9858c-140">Choose the **Customize And Control DevTools** \(`...`\) button.</span></span>  
1.  <span data-ttu-id="9858c-141">ページ**\(** ドック側 \) を基準に**した DevTools**の配置の右側で、[ドック側] オプション**を選択**します。</span><span class="sxs-lookup"><span data-stu-id="9858c-141">To the right of **Placement of the DevTools relative to the page** \(**Dock side**\), choose a **Dock side** option.</span></span>  
    
<span data-ttu-id="9858c-142">詳細については[、「DevTools 配置の変更Microsoft Edge (Undock、Dock to Bottom、Dock to Left) に移動します][DevtoolsGuideCustomizePlacement]。</span><span class="sxs-lookup"><span data-stu-id="9858c-142">For more information, navigate to [Change Microsoft Edge DevTools placement (Undock, Dock To Bottom, Dock To Left)][DevtoolsGuideCustomizePlacement].</span></span>  

:::image type="complex" source="./media/devtools-intro-docking-menu.msft.png" alt-text="DevTools のドック側メニューのスクリーンショット" lightbox="./media/devtools-intro-docking-menu.msft.png":::  
   <span data-ttu-id="9858c-144">DevTools のドック側メニューのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="9858c-144">Screenshot of the Dock side menu in DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="9858c-145">[ **ドック側] で**、次のレイアウト オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9858c-145">In **Dock side**, choose any of the following layout options.</span></span>  

*   <span data-ttu-id="9858c-146">**別のウィンドウにドッキングを解除します**。</span><span class="sxs-lookup"><span data-stu-id="9858c-146">**Undock into separate window**.</span></span>   <span data-ttu-id="9858c-147">複数のモニターを使用したり、フルスクリーン アプリで作業する必要がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9858c-147">Helps you work with several monitors or if you need to work on a full screen app.</span></span>  
*   <span data-ttu-id="9858c-148">**左にドッキングするか** 、 **右にドッキングします**。</span><span class="sxs-lookup"><span data-stu-id="9858c-148">**Dock to left** or **Dock to right**.</span></span>  <span data-ttu-id="9858c-149">DevTools を Web 製品と並べて維持するのに役立ち、モバイル デバイスをエミュレートすると優れています。</span><span class="sxs-lookup"><span data-stu-id="9858c-149">Helps you keep the DevTools side by side with your web product, and is excellent when you emulate mobile devices.</span></span>  <span data-ttu-id="9858c-150">[ **左へドック] オプションと** **[右へドッキング** ] オプションは、高解像度ディスプレイで最適に機能します。</span><span class="sxs-lookup"><span data-stu-id="9858c-150">The **Dock to left** and **Dock to right** options work best with high-resolution displays.</span></span>  <span data-ttu-id="9858c-151">エミュレーション デバイスの詳細については、「DevTools でモバイル デバイスをエミュレート[する」Microsoft Edge移動します][DevtoolsGuideDeviceModeIndex]。</span><span class="sxs-lookup"><span data-stu-id="9858c-151">For more information about emulation devices, navigate to [Emulate mobile devices in Microsoft Edge DevTools][DevtoolsGuideDeviceModeIndex].</span></span>  
*   <span data-ttu-id="9858c-152">**下にドッキングします**。</span><span class="sxs-lookup"><span data-stu-id="9858c-152">**Dock to bottom**.</span></span>  <span data-ttu-id="9858c-153">水平表示領域が足りない場合や、DOM またはコンソールで長いテキストをデバッグする場合に役立 **ちます**。</span><span class="sxs-lookup"><span data-stu-id="9858c-153">Helps you when you do not have enough horizontal display space, or you want to debug long text in the DOM or **Console**.</span></span>  
    
:::row:::  
   :::column span="":::  
      :::image type="complex" source="./media/devtools-intro-docking-left.msft.png" alt-text="[左にドッキング] を選択する" lightbox="./media/devtools-intro-docking-left.msft.png":::  
         <span data-ttu-id="9858c-155">[左 **にドッキング] を選択する**</span><span class="sxs-lookup"><span data-stu-id="9858c-155">Choose **Dock To Left**</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::  
      :::image type="complex" source="media/devtools-intro-docking-bottom.msft.png" alt-text="[下へドッキング] を選択する" lightbox="media/devtools-intro-docking-bottom.msft.png":::  
         <span data-ttu-id="9858c-157">[下 **へドッキング] を選択する**</span><span class="sxs-lookup"><span data-stu-id="9858c-157">Choose **Dock To Bottom**</span></span>  
      :::image-end:::  
   :::column-end:::  
:::row-end:::  
:::row:::  
   :::column span="":::  
      :::image type="complex" source="media/devtools-intro-docking-right.msft.png" alt-text="[右へドッキング] を選択する" lightbox="media/devtools-intro-docking-right.msft.png":::  
         <span data-ttu-id="9858c-159">[右 **へドッキング] を選択する**</span><span class="sxs-lookup"><span data-stu-id="9858c-159">Choose **Dock To Right**</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::  
      :::image type="complex" source="media/devtools-intro-docking-own-window.msft.png" alt-text="[別のウィンドウにドッキングを解除する] を選択する" lightbox="media/devtools-intro-docking-own-window.msft.png":::  
         <span data-ttu-id="9858c-161">[別 **のウィンドウにドッキングを解除する] を選択する**</span><span class="sxs-lookup"><span data-stu-id="9858c-161">Choose **Undock into separate window**</span></span>  
      :::image-end:::  
   :::column-end:::  
:::row-end:::  

## <a name="learn-about-the-core-tools"></a><span data-ttu-id="9858c-162">コア ツールの詳細</span><span class="sxs-lookup"><span data-stu-id="9858c-162">Learn about the core tools</span></span>  

<span data-ttu-id="9858c-163">DevTools を使用すると、ブラウザーに現在表示されている Web 製品を検査、デバッグ、および変更する機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="9858c-163">DevTools give you an amazing amount of power to inspect, debug, and change the web product currently displayed in the browser.</span></span>  <span data-ttu-id="9858c-164">ほとんどのツールは、変更をライブで表示します。</span><span class="sxs-lookup"><span data-stu-id="9858c-164">Most of the tools display the changes live.</span></span>  <span data-ttu-id="9858c-165">ライブ更新プログラムを使用すると、Web プロジェクトを更新またはビルドすることなく、Web プロジェクトの外観とナビゲーションや機能を絞り込むツールが非常に便利です。</span><span class="sxs-lookup"><span data-stu-id="9858c-165">Live updates make the tools incredibly useful to refine the appearance and navigation or functionality of a web project without the need to refresh or build it.</span></span>  <span data-ttu-id="9858c-166">DevTools を使用すると、コンピューター上の Web ベースのサード パーティ製品を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="9858c-166">The DevTools also allow you to change web-based third-party products on your computer.</span></span>  

<span data-ttu-id="9858c-167">DevTools は数年間にわたり成長しました。</span><span class="sxs-lookup"><span data-stu-id="9858c-167">DevTools grew over a period of several years.</span></span>  <span data-ttu-id="9858c-168">DevTools は、最初にツールを開く際に学習するのが難しいと考える場合があります。</span><span class="sxs-lookup"><span data-stu-id="9858c-168">You may assume that DevTools are difficult to learn when you first open any of tools.</span></span>  <span data-ttu-id="9858c-169">次のテキストでは、さまざまな部分をすばやく紹介します。</span><span class="sxs-lookup"><span data-stu-id="9858c-169">The following text quickly introduces the different parts.</span></span>  <span data-ttu-id="9858c-170">メイン ツールバーにはいくつかのセクションが用意され、セクションは左から右に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="9858c-170">The main toolbar offers you a few sections and the sections are ordered from left to right.</span></span>  

:::image type="complex" source="./media/devtools-intro-menu-bar.msft.png" alt-text="さまざまなセクションを説明するラベル付き DevTools のメニュー バーのスクリーンショット。  順序: ツール、デバイス エミュレーション ツール、ツール タブ グループ、JavaScript エラー、問題、設定、フィードバック、カスタマイズ、および閉じるを検査します。" lightbox="./media/devtools-intro-menu-bar.msft.png":::  
   <span data-ttu-id="9858c-173">さまざまなセクションを説明するラベル付き DevTools のメニュー バーのスクリーンショット。</span><span class="sxs-lookup"><span data-stu-id="9858c-173">Screenshot of the menu bar of the DevTools with labels that explain the different sections.</span></span>  <span data-ttu-id="9858c-174">順序: 検査ツール、デバイス エミュレーション ツール、ツール タブ グループ、JavaScript エラー、問題、設定、フィードバック、カスタマイズ、閉じる。</span><span class="sxs-lookup"><span data-stu-id="9858c-174">In order: Inspect tool, Device Emulation tool, Tools tab group, JavaScript Errors, Issues, Settings, Feedback, Customize, and Close.</span></span>  
:::image-end:::  

*   <span data-ttu-id="9858c-175">[検査] ツールを使用すると、現在の Web ページで要素を選択できます。</span><span class="sxs-lookup"><span data-stu-id="9858c-175">The Inspect tool allows you to choose an element on the current webpage.</span></span>  <span data-ttu-id="9858c-176">アクティブ化した後、Web ページの別の部分にマウスを移動して、要素に関する詳細情報と、サイズ、パディング、余白を表示するカラー オーバーレイを取得できます。</span><span class="sxs-lookup"><span data-stu-id="9858c-176">After you activate it, you may move your mouse over different parts of the webpage to get detailed information about the element and a color overlay to display dimensions, padding, and margin.</span></span>  
    
    :::image type="complex" source="./media/devtools-intro-inspect-tool.msft.png" alt-text="この記事の最初の見出しが選択された検査ツール" lightbox="./media/devtools-intro-inspect-tool.msft.png":::  
       <span data-ttu-id="9858c-178">この記事の最初の見出しが選択された検査ツール</span><span class="sxs-lookup"><span data-stu-id="9858c-178">The Inspect tool with the first headline of this article chosen</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="9858c-179">デバイス [エミュレーション ツールは][DevtoolsGuideDeviceModeIndex] 、エミュレートされたデバイス モードで現在の Web 製品を表示します。</span><span class="sxs-lookup"><span data-stu-id="9858c-179">The [Device Emulation][DevtoolsGuideDeviceModeIndex] tool displays the current web product in an emulated device mode.</span></span>  <span data-ttu-id="9858c-180">デバイス **エミュレーション ツールを** 使用すると、ブラウザーのサイズを変更するときに製品の反応を実行してテストできます。</span><span class="sxs-lookup"><span data-stu-id="9858c-180">The **Device Emulation** tool allows you to run and test how your product reacts when you resize the browser.</span></span>  <span data-ttu-id="9858c-181">また、モバイル デバイス上のレイアウトと動作を推定することもできます。</span><span class="sxs-lookup"><span data-stu-id="9858c-181">It also gives you an estimation of the layout and behavior on a mobile device.</span></span>  
    
    :::image type="complex" source="./media/devtools-intro-device-emulation.msft.png" alt-text="エミュレートされた携帯電話でのこの記事の DevTools 表示のスクリーンショット" lightbox="./media/devtools-intro-device-emulation.msft.png":::  
       <span data-ttu-id="9858c-183">エミュレートされた携帯電話でのこの記事の DevTools 表示のスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="9858c-183">Screenshot of the DevTools display of this article in an emulated mobile phone</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="9858c-184">[ツール] タブ グループは、さまざまなシナリオで使用されるさまざまなツールを表すタブのグループです。</span><span class="sxs-lookup"><span data-stu-id="9858c-184">The Tools tab group is a group of tabs that represent different tools that are used in different scenarios.</span></span>  <span data-ttu-id="9858c-185">各ツールをカスタマイズして、コンテキストに基づいて各ツールが変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="9858c-185">You may customize each of the tools and each tool may change based on the context.</span></span>  <span data-ttu-id="9858c-186">その他のツールのドロップダウン メニューを開く場合は、[ **その他]** タブ \( `>>` \) ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="9858c-186">To open a dropdown menu of more tools, choose the **More tabs** \(`>>`\) button.</span></span>  <span data-ttu-id="9858c-187">各ツールは、後で次のセクションで紹介します。</span><span class="sxs-lookup"><span data-stu-id="9858c-187">Each of the tools is introduced later in the following section.</span></span>  
*   <span data-ttu-id="9858c-188">[ツール] タブ グループの横にはオプションのエラーと問題のショートカットがあります。</span><span class="sxs-lookup"><span data-stu-id="9858c-188">Next to the Tools tab group are optional error and issues shortcuts.</span></span>  <span data-ttu-id="9858c-189">現在の Web ページで JavaScript のエラーや問題が発生すると、ショートカットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9858c-189">The shortcuts display when JavaScript errors or issues occur on the current webpage.</span></span>  <span data-ttu-id="9858c-190">Open **Console to view # errors, # warnings** \(**JavaScript Errors**\) ボタンは、赤い円を表示し、その後に JavaScript エラーの `X` 数を表示します。</span><span class="sxs-lookup"><span data-stu-id="9858c-190">The **Open Console to view # errors, # warnings** \(**JavaScript Errors**\) button displays a red circle with an `X` followed by the number of JavaScript errors.</span></span>  <span data-ttu-id="9858c-191">コンソールを開き [、][DevtoolsGuideConsoleIndex] エラーの詳細を確認するには **、[JavaScript Errors] ボタンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="9858c-191">To open the [Console][DevtoolsGuideConsoleIndex] and learn about the error, choose the **JavaScript Errors** button.</span></span>  <span data-ttu-id="9858c-192">[ **表示する問題を開く] #issues** \(**Issues**\) ボタンは、青いメッセージ アイコンの後に問題の数が続きます。</span><span class="sxs-lookup"><span data-stu-id="9858c-192">The **Open Issues to view # issues** \(**Issues**\) button is a blue message icon followed by the number of issues.</span></span>  <span data-ttu-id="9858c-193">[問題] ツール [を開く][DevtoolsGuideIssuesIndex] 場合は、[問題] **ボタンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="9858c-193">To open the [Issues][DevtoolsGuideIssuesIndex] tool, choose **Issues** button.</span></span>  
*   <span data-ttu-id="9858c-194">**[設定]** ボタンには、歯車アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9858c-194">The **Settings** button displays a gear icon.</span></span>  <span data-ttu-id="9858c-195">Web ページで DevTools**設定**開く場合は、次のボタン**を設定**します。</span><span class="sxs-lookup"><span data-stu-id="9858c-195">To open DevTools **Settings** webpage, choose the **Settings** button.</span></span>  <span data-ttu-id="9858c-196">Web**ページ設定、\*\*\*\*基本設定の**変更、**実験のオン**、その他のメニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9858c-196">The **Settings** webpage displays a menu to change **Preferences**, turn on **Experiments**, and much more.</span></span>  
*   <span data-ttu-id="9858c-197">[ **フィードバックの送信]** ボタンは、その横にチャット バブルが表示された torso を表示します。</span><span class="sxs-lookup"><span data-stu-id="9858c-197">The **Send Feedback** button displays torso with a chat bubble next to it.</span></span>  <span data-ttu-id="9858c-198">[フィードバックの送信 **] ダイアログを開** くには、[フィードバックの送信 **] ボタンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="9858c-198">To open the **Send Feedback** dialog, choose the **Send Feedback** button.</span></span>  <span data-ttu-id="9858c-199">[ **フィードバックの送信** ] ダイアログでは、何が起こったのかを説明する情報を入力し、スクリーンショットを自動的に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9858c-199">The **Send Feedback** dialog allows you to enter information to describe what happened and automatically includes a screenshot.</span></span>  <span data-ttu-id="9858c-200">DevTools チームと接続して、問題、問題、またはアイデアを提案するために使用します。</span><span class="sxs-lookup"><span data-stu-id="9858c-200">Use it to connect with the DevTools team to report problems, issues, or suggest ideas.</span></span>  
*   <span data-ttu-id="9858c-201">**[Devtools \(** \) のカスタマイズと制御] ボタン `...` をクリックすると、ドロップダウン メニューが開きます。</span><span class="sxs-lookup"><span data-stu-id="9858c-201">The **Customize and control Devtools** \(`...`\) button opens a dropdown menu.</span></span>  <span data-ttu-id="9858c-202">DevTools をドッキングする場所、検索場所、さまざまなツールを開く場所を定義できます。</span><span class="sxs-lookup"><span data-stu-id="9858c-202">It allows you to define where to dock the DevTools, search, open different tools, and much more.</span></span>  
    
<span data-ttu-id="9858c-203">[ツール] タブ グループで、DevTools で使用できるさまざまなツールを開く場合があります。</span><span class="sxs-lookup"><span data-stu-id="9858c-203">In the Tools tab group, you may open the different tools that are available in the DevTools.</span></span>  <span data-ttu-id="9858c-204">次の一覧では、DevTools で最も一般的に使用されるツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9858c-204">The following list describes the most commonly used tools in the DevTools.</span></span>  

*   <span data-ttu-id="9858c-205">**ようこそ**。</span><span class="sxs-lookup"><span data-stu-id="9858c-205">**Welcome**.</span></span>  <span data-ttu-id="9858c-206">DevTools の新機能、チームに連絡する方法、および特定の機能に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9858c-206">Includes information about the new features of DevTools, how to contact the team, and provides information about certain features.</span></span>  
*   <span data-ttu-id="9858c-207">**要素**.</span><span class="sxs-lookup"><span data-stu-id="9858c-207">**Elements**.</span></span>  <span data-ttu-id="9858c-208">HTML と CSS を編集または検査できます。</span><span class="sxs-lookup"><span data-stu-id="9858c-208">Allows you to edit or inspect HTML and CSS.</span></span>  <span data-ttu-id="9858c-209">ツールの両方を編集し、ブラウザーに変更内容を表示できます。</span><span class="sxs-lookup"><span data-stu-id="9858c-209">You may edit both in the tool and display the changes live in the browser.</span></span>  
*   <span data-ttu-id="9858c-210">[コンソール][DevtoolsGuideConsoleIndex].</span><span class="sxs-lookup"><span data-stu-id="9858c-210">[Console][DevtoolsGuideConsoleIndex].</span></span>  <span data-ttu-id="9858c-211">ログ メッセージを表示およびフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="9858c-211">Allows you to display and filter log messages.</span></span>  <span data-ttu-id="9858c-212">ログ メッセージは、ネットワーク要求や開発者が生成したログなど、ブラウザーの自動ログです。</span><span class="sxs-lookup"><span data-stu-id="9858c-212">Log messages are automated logs of the browser like network requests and developer-generated logs.</span></span>  <span data-ttu-id="9858c-213">現在のウィンドウまたはフレームのコンテキストで **、コンソール** で JavaScript を直接実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="9858c-213">You may also run JavaScript directly in the **Console** in the context of the current window or frame.</span></span>  
*   <span data-ttu-id="9858c-214">[Sources][DevtoolsGuideSourcesIndex].</span><span class="sxs-lookup"><span data-stu-id="9858c-214">[Sources][DevtoolsGuideSourcesIndex].</span></span>  <span data-ttu-id="9858c-215">コード エディターと JavaScript デバッガー。</span><span class="sxs-lookup"><span data-stu-id="9858c-215">A code editor and JavaScript debugger.</span></span>  <span data-ttu-id="9858c-216">プロジェクトの編集、スニペットの管理、現在のプロジェクトのデバッグを行えます。</span><span class="sxs-lookup"><span data-stu-id="9858c-216">You may edit projects, maintain snippets, and debug your current project.</span></span>  
*   <span data-ttu-id="9858c-217">[ネットワーク][DevtoolsGuideNetworkIndex].</span><span class="sxs-lookup"><span data-stu-id="9858c-217">[Network][DevtoolsGuideNetworkIndex].</span></span>  <span data-ttu-id="9858c-218">ネットワークキャッシュとブラウザー キャッシュからの要求または応答を監視および検査できます。</span><span class="sxs-lookup"><span data-stu-id="9858c-218">Allows you to monitor and inspect requests or responses from the network and browser cache.</span></span>  <span data-ttu-id="9858c-219">ニーズに合わせて要求と応答をフィルター処理し、さまざまなネットワーク条件をシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="9858c-219">You may filter requests and responses to fit your needs and simulate different network conditions.</span></span>  <span data-ttu-id="9858c-220">パフォーマンス、メモリ、アプリケーション、セキュリティ、監査など\*\*\*\*、その\*\*\*\* 他の\*\*\*\* 特殊**な**ツールも**利用できます**。</span><span class="sxs-lookup"><span data-stu-id="9858c-220">Other specialized tools are also available, such as **Performance**, **Memory**, **Application**, **Security**, and **Audits**.</span></span>  

## <a name="power-tip-use-the-command-menu"></a><span data-ttu-id="9858c-221">電源ヒント: コマンド メニューを使用する</span><span class="sxs-lookup"><span data-stu-id="9858c-221">Power tip: Use the command menu</span></span>  

<span data-ttu-id="9858c-222">DevTools には、Web 製品で使用する多くの機能と機能が提供されています。</span><span class="sxs-lookup"><span data-stu-id="9858c-222">The DevTools provides lots of features and functionality to use with your web product.</span></span>  <span data-ttu-id="9858c-223">さまざまな方法で DevTools の各部分にアクセスしますが、必要な機能に最も速くアクセスするには、コマンド メニューを使用します。</span><span class="sxs-lookup"><span data-stu-id="9858c-223">Access the different parts of the DevTools in many ways, but the fastest way to access the features you need is to use the command menu.</span></span>  <span data-ttu-id="9858c-224">詳細については、[DevTools コマンド] メニューの [[コマンドMicrosoft Edge実行] に移動します][DevtoolsGuideCommandMenuIndex]。</span><span class="sxs-lookup"><span data-stu-id="9858c-224">For more information, navigate to [Run commands with the Microsoft Edge DevTools Command menu][DevtoolsGuideCommandMenuIndex].</span></span>  <span data-ttu-id="9858c-225">コマンド メニューを開く場合は、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9858c-225">To open the command menu, complete one of the following actions.</span></span>  

*   <span data-ttu-id="9858c-226">`Control` + `Shift` + `P` \(Windows Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="9858c-226">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  
*   <span data-ttu-id="9858c-227">**[DevTools \(** \) のカスタマイズと制御 `...` ] を選択し、[コマンドの実行]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9858c-227">Choose **Customize And Control DevTools** \(`...`\), and then choose **Run Command**.</span></span>  

:::image type="complex" source="./media/devtools-intro-command-menu.msft.png" alt-text="DevTools のコマンド メニューのスクリーンショット" lightbox="./media/devtools-intro-command-menu.msft.png":::  
<span data-ttu-id="9858c-229">DevTools のコマンド メニューのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="9858c-229">Screenshot of the command menu in DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="9858c-230">コマンド メニューでは、DevTools の機能を表示、非表示、または実行するコマンドを入力できます。</span><span class="sxs-lookup"><span data-stu-id="9858c-230">The command menu allows you to type commands to display, hide, or run features in the DevTools.</span></span>  <span data-ttu-id="9858c-231">コマンド メニューを開いて、変更という単語を入力 **し、[ドロ**ワーの変更の表示] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9858c-231">With the command menu open, enter the word **changes**, and then choose **Drawer Show Changes**.</span></span>  <span data-ttu-id="9858c-232">変更 **ツール** が開き、CSS を編集するときに便利ですが、DevTools UI で見つけるのは困難です。</span><span class="sxs-lookup"><span data-stu-id="9858c-232">The **Changes** tool opens which is useful when you edit CSS, but is difficult to find in the DevTools UI.</span></span>  

:::row:::  
   :::column span="":::  
      :::image type="complex" source="./media/devtools-intro-command-menu-show-changes.msft.png" alt-text="コマンド メニューは、変更を入力した後にオプションを表示します。" lightbox="./media/devtools-intro-command-menu-show-changes.msft.png":::  
         <span data-ttu-id="9858c-234">コマンド メニューは、入力後にオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="9858c-234">Command menu displays the options after you type</span></span> `changes`  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::  
      :::image type="complex" source="./media/devtools-intro-showing-changes.msft.png" alt-text="変更ツールを開いた DevTools" lightbox="./media/devtools-intro-showing-changes.msft.png":::  
         <span data-ttu-id="9858c-236">変更ツールを開いた**DevTools**</span><span class="sxs-lookup"><span data-stu-id="9858c-236">DevTools with the **Changes** tool open</span></span>  
      :::image-end:::  
   :::column-end:::  
:::row-end:::  

## <a name="customize-the-devtools"></a><span data-ttu-id="9858c-237">DevTools をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="9858c-237">Customize the DevTools</span></span>  

<span data-ttu-id="9858c-238">DevTools は、ニーズや作業方法に合わせてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="9858c-238">DevTools are customizable to meet your needs or the way you work.</span></span>  <span data-ttu-id="9858c-239">設定を変更するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9858c-239">To change settings, complete one of the following actions.</span></span>  

*   <span data-ttu-id="9858c-240">**[設定**\(右上の歯車アイコン\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="9858c-240">Choose **Settings** \(the gear icon on the top right\)</span></span>  
*   <span data-ttu-id="9858c-241">を `F1` 選択するか `?` 、 を選択します。</span><span class="sxs-lookup"><span data-stu-id="9858c-241">Select `F1` or `?`.</span></span>  
    
<span data-ttu-id="9858c-242">[基本設定 **] セクション** では、DevTools のいくつかの部分を変更できます。</span><span class="sxs-lookup"><span data-stu-id="9858c-242">In the **Preferences** section, you may change several parts of the DevTools.</span></span>  <span data-ttu-id="9858c-243">たとえば、[ブラウザー言語の一致 **]** 設定を使用して、ブラウザーで使用する DevTools で同じ言語を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9858c-243">For example, you may use the **Match the browser language** setting to use the same language in the DevTools that is use in your browser.</span></span>  <span data-ttu-id="9858c-244">別の例として、 **テーマ設定を** 使用して DevTools のテーマを変更します。</span><span class="sxs-lookup"><span data-stu-id="9858c-244">For another example, use the **Theme** setting to change the theme of the DevTools.</span></span>  

:::image type="complex" source="media/devtools-intro-all-settings.msft.png" alt-text="DevTools のすべての設定のスクリーンショット" lightbox="./media/devtools-intro-all-settings.msft.png":::  
   <span data-ttu-id="9858c-246">DevTools のすべての設定のスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="9858c-246">Screenshot of all the settings in DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="9858c-247">また、次の機能を含む高度な機能の設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="9858c-247">You may also change the settings of advanced features including the following features.</span></span>    

*   <span data-ttu-id="9858c-248">[Workspaces][DevtoolsGuideWorkspacesIndex].</span><span class="sxs-lookup"><span data-stu-id="9858c-248">[Workspaces][DevtoolsGuideWorkspacesIndex].</span></span>  
*   <span data-ttu-id="9858c-249">[リストを無視] を使用して **ライブラリ コードをフィルター処理します**。</span><span class="sxs-lookup"><span data-stu-id="9858c-249">Filter library code with the **Ignore List**.</span></span>  
*   <span data-ttu-id="9858c-250">デバイス シミュレーション **とテスト** モードに含めるデバイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="9858c-250">Define the **Devices** you want to include in the device simulation and test mode.</span></span>  <span data-ttu-id="9858c-251">詳細については、「デバイス DevTools でモバイル デバイスをエミュレート[するMicrosoft Edge移動します][DevtoolsGuideDeviceModeIndex]。</span><span class="sxs-lookup"><span data-stu-id="9858c-251">For more information, navigate to [Emulate mobile devices in Microsoft Edge DevTools][DevtoolsGuideDeviceModeIndex].</span></span>  
*   <span data-ttu-id="9858c-252">ネットワーク調整プロファイル **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="9858c-252">Choose a network **Throttling** profile.</span></span>  
*   <span data-ttu-id="9858c-253">シミュレートされた場所 **を定義します**。</span><span class="sxs-lookup"><span data-stu-id="9858c-253">Define simulated **Locations**.</span></span>  
*   <span data-ttu-id="9858c-254">キーボード ショートカットをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="9858c-254">Customize keyboard shortcuts.</span></span>  <span data-ttu-id="9858c-255">DevTools で同じショートカットを使用するには、次Visual Studio Code操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9858c-255">To use the same shortcuts in the DevTools as Visual Studio Code, complete the following actions.</span></span>  
    1.  <span data-ttu-id="9858c-256">プリセットから **[ショートカットの一致] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9858c-256">Choose **Match shortcuts from preset**.</span></span>  
    1.  <span data-ttu-id="9858c-257">[Visual Studio Code]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9858c-257">Choose **Visual Studio Code**.</span></span>  
        
    :::image type="complex" source="./media/devtools-intro-match-keys.msft.png" alt-text="すべてのキーボード ショートカットとメニューのスクリーンショットで、各ショートカットと一致Visual Studio Code" lightbox="./media/devtools-intro-match-keys.msft.png":::  
       <span data-ttu-id="9858c-259">すべてのキーボード ショートカットとメニューのスクリーンショットで、各ショートカットと一致Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="9858c-259">Screenshot of all the keyboard shortcuts and the menu to match each to the shortcuts in Visual Studio Code</span></span>  
    :::image-end:::  
    
## <a name="try-experimental-features"></a><span data-ttu-id="9858c-260">実験的な機能を試す</span><span class="sxs-lookup"><span data-stu-id="9858c-260">Try experimental features</span></span>  

<span data-ttu-id="9858c-261">DevTools チームは、DevTools の実験として新機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="9858c-261">The DevTools team provides new features as experiments in the DevTools.</span></span>  <span data-ttu-id="9858c-262">実験の完全な一覧を取得するには、DevTools 設定に移動し **、[** 実験]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9858c-262">To get the full list of experiments, navigate to the DevTools **Settings**, and then choose **Experiments**.</span></span>  <span data-ttu-id="9858c-263">各実験をオンまたはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="9858c-263">You may turn each of the experiments on or off.</span></span>  <span data-ttu-id="9858c-264">どの実験が有益かを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9858c-264">Help decide which one of the experiments is valuable to you.</span></span>  <span data-ttu-id="9858c-265">実験の詳細については、「実験機能」 [に移動します][DevtoolsGuideExperimentalFeaturesIndex]。</span><span class="sxs-lookup"><span data-stu-id="9858c-265">For more information on the experiments, navigate to [Experimental features][DevtoolsGuideExperimentalFeaturesIndex].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="9858c-266">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="9858c-266">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  

<span data-ttu-id="9858c-267">近々ある [DevTools][DevtoolsGuideWhatsNew202102Devtools] の最新の機能をプレビューする場合は、毎晩ビルドされる [Microsoft Edge Canary][MicrosoftedgeinsiderDownload] をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9858c-267">If you want to preview the [latest features coming to the DevTools][DevtoolsGuideWhatsNew202102Devtools], download [Microsoft Edge Canary][MicrosoftedgeinsiderDownload], which builds nightly.</span></span>  

## <a name="see-also"></a><span data-ttu-id="9858c-268">関連項目</span><span class="sxs-lookup"><span data-stu-id="9858c-268">See also</span></span>  

*   [<span data-ttu-id="9858c-269">DevtoolsGuide for Beginners: html はじめに DOM を使用したユーザー設定</span><span class="sxs-lookup"><span data-stu-id="9858c-269">DevtoolsGuide for Beginners: Get Started with HTML and the DOM</span></span>][DevtoolsGuideBeginnersHtml]  
*   [<span data-ttu-id="9858c-270">Microsoft Edge (Chromium) DevTools プロトコル</span><span class="sxs-lookup"><span data-stu-id="9858c-270">Microsoft Edge (Chromium) DevTools Protocol</span></span>][DevtoolsProtocolIndex]  
    
<!-- links -->  

[DevtoolsGuideBeginnersHtml]: ./beginners/html.md "初級者向け DevTools: HTML と DOM の使用を|Microsoft Docs"  
[DevtoolsGuideCommandMenuIndex]: ./command-menu/index.md "[DevTools コマンド] メニューの [Microsoft Edgeを使用してコマンドを実行|Microsoft Docs"  
[DevtoolsGuideConsoleIndex]: ./console/index.md "コンソールの概要|Microsoft Docs"  
[DevtoolsGuideCustomizePlacement]: ./customize/placement.md "DevTools Microsoft Edge配置を変更する (Undock、Dock to Bottom、Dock to Left) |Microsoft Docs"  
[DevtoolsGuideDeviceModeIndex]: ./device-mode/index.md "Microsoft Edge DevTools でモバイル デバイスをエミュレートする | Microsoft Docs"  
[DevtoolsGuideDomIndex]: ./dom/index.md "DOM ファイルの表示と変更を開始|Microsoft Docs"  
[DevtoolsGuideEvaluatePerformanceIndex]: ./evaluate-performance/index.md "ランタイム パフォーマンス の分析の開始|Microsoft Docs"  
[DevtoolsGuideExperimentalFeaturesIndex]: ./experimental-features/index.md "実験的な機能|Microsoft Docs"  
[DevtoolsGuideMemoryProblemsIndex]: ./memory-problems/index.md "メモリの問題を修正|Microsoft Docs"  
[DevtoolsGuideInspectStylesEditFonts]: ./inspect-styles/edit-fonts.md "[スタイル] ウィンドウの [CSS フォントのスタイルと設定を編集|Microsoft Docs"  
[DevtoolsGuideIssuesIndex]: ./issues/index.md "Microsoft Edge DevTools の問題ツールに関する問題を見つけて修正する | Microsoft Docs"  
[DevtoolsGuideJavascriptIndex]: ./javascript/index.md "DevTools アプリケーションの JavaScript のデバッグMicrosoft Edge開始|Microsoft Docs"  
[DevtoolsGuideJavascriptOverrides]: ./javascript/overrides.md "DevTools を使用して Web ページ リソースをローカル コピー Microsoft Edgeオーバーライド|Microsoft Docs"  
[DevtoolsGuideNetworkIndex]: ./network/index.md "DevTools サーバーでネットワークMicrosoft Edgeを調|Microsoft Docs"  
[DevtoolsGuideOpenIndex]: ./open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  
[DevtoolsGuideRenderingToolsIndex]: ./rendering-tools/index.md "ランタイム パフォーマンス の分析|Microsoft Docs"  
[DevtoolsGuideShortcutsIndex]: ./shortcuts/index.md "Microsoft EdgeDevTools キーボード ショートカット |Microsoft Docs"  
[DevtoolsGuideSourcesIndex]: ./sources/index.md "ソース ツールの概要|Microsoft Docs"  
[DevtoolsGuideStorageSessionstorage]: ./storage/sessionstorage.md "DevTools を使用してセッション ストレージを表示Microsoft Edge編集|Microsoft Docs"  
[DevtoolsGuideWhatsNew202102Devtools]: ./whats-new/2021/02/devtools.md "DevTools の新機能 (Microsoft Edge 90) |Microsoft Docs"  
[DevtoolsGuideWorkspacesIndex]: ./workspaces/index.md "Workspaces を使用してファイルを編集|Microsoft Docs"  
[DevtoolsProtocolIndex]: ../devtools-protocol-chromium/index.md "Microsoft Edge (Chromium) DevTools プロトコルの概要 | Microsoft Docs"  

[MicrosoftEdgeAddonsExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge アドオン"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channelsをダウンロードする"  

[GoogleChromeWebstoreExtensions]: https://chrome.google.com/webstore/category/extensions "拡張機能 | Chrome Web ストア"  
