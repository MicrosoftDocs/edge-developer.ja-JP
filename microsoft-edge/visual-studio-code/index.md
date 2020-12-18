---
description: Microsoft Edge (Chromium) および Visual Studio Code
title: Visual Studio Code
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/20/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, vs code, visual studio code, debugger, webhint
ms.openlocfilehash: 1aa5b66043e87ebb0f1b848dcd60e2553b378f36
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230692"
---
# <span data-ttu-id="fc740-104">Visual Studio Code の概要</span><span class="sxs-lookup"><span data-stu-id="fc740-104">Visual Studio Code overview</span></span>  

<span data-ttu-id="fc740-105">[Visual Studioは][VisualStudioCodeDocs] 、軽量で強力なソース コード エディターです。</span><span class="sxs-lookup"><span data-stu-id="fc740-105">[Visual Studio Code][VisualStudioCodeDocs] is a lightweight, but powerful source code editor.</span></span>  <span data-ttu-id="fc740-106">[Visual Studioコード][VisualStudioCodeDocs] は、Windows、Linux、macOS で利用できます。</span><span class="sxs-lookup"><span data-stu-id="fc740-106">[Visual Studio Code][VisualStudioCodeDocs] is available for Windows, Linux, and macOS.</span></span>  <span data-ttu-id="fc740-107">JavaScript、TypeScript、および Node.js の組み込みサポートが含まれるので、カスタマイズする前に Web 開発者に最適なツールです。</span><span class="sxs-lookup"><span data-stu-id="fc740-107">It includes built-in support for JavaScript, TypeScript, and Node.js, so it is a great tool for web developers before you customize it.</span></span>  <span data-ttu-id="fc740-108">If you are not using it yet, download [Visual Studio Code][VisualstudioCode].</span><span class="sxs-lookup"><span data-stu-id="fc740-108">If you are not using it yet, download [Visual Studio Code][VisualstudioCode].</span></span>  

## <span data-ttu-id="fc740-109">拡張機能</span><span class="sxs-lookup"><span data-stu-id="fc740-109">Extensions</span></span>  

<!--todo: We want to put something like the tiles for extensions Visual Studio Code uses on this page https://code.visualstudio.com/Docs#top-extensions but I don't think this is a markdown page.  I think it's a web page.  I couldn't find anything in https://github.com/Microsoft/vscode-docs that looks like this page. In the meantime, here's what I've come up with: -->  

<span data-ttu-id="fc740-110">以下で強調表示されている拡張機能を取得するには、Visual Studio Code で Extensions \(Windows/Linux または macOS で選択 `Ctrl` + `Shift` + `X` `Command` + `Shift` + `X` )に移動します。</span><span class="sxs-lookup"><span data-stu-id="fc740-110">To acquire any of the extensions highlighted below, navigate to Extensions \(select `Ctrl`+`Shift`+`X` on Windows/Linux or `Command`+`Shift`+`X` on macOS\) in Visual Studio Code.</span></span>  

<span data-ttu-id="fc740-111">Marketplace で特定の拡張機能を検索し、[インストール] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="fc740-111">Search the Marketplace for the specific extension and choose **Install**.</span></span>  

:::image type="complex" source="./media/vscode-debugger-install.png" alt-text="Microsoft Edge Visual Studio Code 拡張機能のデバッガーをインストールする" lightbox="./media/vscode-debugger-install.png":::
   <span data-ttu-id="fc740-113">Microsoft **Edge Visual Studio** Code 拡張機能のデバッガーをインストールする</span><span class="sxs-lookup"><span data-stu-id="fc740-113">Install the **Debugger for Microsoft Edge** Visual Studio Code extension</span></span>  
:::image-end:::  

:::row:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-debugger-for-microsoft-edge.msft.png" alt-text="Microsoft Edge Visual Studio Code 拡張機能のデバッガー" lightbox="./media/visual-studio-code-extension-debugger-for-microsoft-edge.msft.png":::
         <span data-ttu-id="fc740-115">**Microsoft Edge のデバッガー** Visual Studioコード拡張機能</span><span class="sxs-lookup"><span data-stu-id="fc740-115">**Debugger for Microsoft Edge** Visual Studio Code extension</span></span>  
      :::image-end:::  
      [<span data-ttu-id="fc740-116">Microsoft Edge のデバッガー</span><span class="sxs-lookup"><span data-stu-id="fc740-116">Debugger for Microsoft Edge</span></span>](#debugger-for-microsoft-edge)  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-microsoft-edge-tools-for-visual-studio-code.msft.png" alt-text="Microsoft Edge Tools for Visual Studio Code Visual Studio Extension" lightbox="./media/visual-studio-code-extension-microsoft-edge-tools-for-visual-studio-code.msft.png":::
         <span data-ttu-id="fc740-118">**Microsoft Edge Tools for Visual Studio Code** Visual Studioコード拡張機能</span><span class="sxs-lookup"><span data-stu-id="fc740-118">**Microsoft Edge Tools for Visual Studio Code** Visual Studio Code extension</span></span>  
      :::image-end:::  
      [<span data-ttu-id="fc740-119">Microsoft Edge Tools for Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="fc740-119">Microsoft Edge Tools for Visual Studio Code</span></span>](#microsoft-edge-tools-for-visual-studio-code)  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-webhint.msft.png" alt-text="webhint Visual Studio コード拡張機能" lightbox="./media/visual-studio-code-extension-webhint.msft.png":::
         <span data-ttu-id="fc740-121">**webhint** Visual Studioコード拡張機能</span><span class="sxs-lookup"><span data-stu-id="fc740-121">**webhint** Visual Studio Code extension</span></span>  
      :::image-end:::  
      [<span data-ttu-id="fc740-122">Webhint</span><span class="sxs-lookup"><span data-stu-id="fc740-122">webhint</span></span>](#webhint)  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="fc740-123">Microsoft Edge のデバッガー</span><span class="sxs-lookup"><span data-stu-id="fc740-123">Debugger for Microsoft Edge</span></span>  

<span data-ttu-id="fc740-124">Microsoft [Edge Visual Studio][VisualstudioMarketplaceDebuggerMicrosoftEdge] Code 拡張機能のデバッガーを使用して、フロントエンド JavaScript コードを 1 行でデバッグし、コードから直接ステートメント `console.log()` [Visual Studioします][VisualstudioCode]。</span><span class="sxs-lookup"><span data-stu-id="fc740-124">With the [Debugger for Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] Visual Studio Code extension, debug your front-end JavaScript code line-by-line and see `console.log()` statements directly from [Visual Studio Code][VisualstudioCode].</span></span>  
      
<span data-ttu-id="fc740-125">デバッガー ツールを使用すると、Microsoft Edge \(EdgeHTML\) と Microsoft Edge \(Chromium\) の両方を起動またはアタッチできます。</span><span class="sxs-lookup"><span data-stu-id="fc740-125">Using the Debugger tool, you may launch or attach to both Microsoft Edge \(EdgeHTML\) and Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="fc740-126">Visual Studio コードとサンプル構成から Microsoft Edge をデバッグするチュートリアルについては、Debugger For Microsoft Edge Visual Studio Code Extension に `launch.json` [移動します][VisualStudioCodeDebuggerEdge]。</span><span class="sxs-lookup"><span data-stu-id="fc740-126">For a walkthrough of debugging Microsoft Edge from Visual Studio Code and sample `launch.json` configurations, navigate to [Debugger For Microsoft Edge Visual Studio Code Extension][VisualStudioCodeDebuggerEdge].</span></span>  <span data-ttu-id="fc740-127">次の画像を選択して、拡張機能の動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="fc740-127">Choose the following image to see the extension in action.</span></span>  

:::image type="complex" source="./media/debugger-for-edge.png" alt-text="Edge Visual Studio コード拡張機能のデバッガーの動作" lightbox="./media/debugger-for-edge.gif":::
   <span data-ttu-id="fc740-129">**Microsoft Edge のデバッガー** Visual Studioコード拡張機能の動作</span><span class="sxs-lookup"><span data-stu-id="fc740-129">**Debugger for Microsoft Edge** Visual Studio Code extension in action</span></span>  
:::image-end:::  

## <span data-ttu-id="fc740-130">Microsoft Edge Tools for Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="fc740-130">Microsoft Edge Tools for Visual Studio Code</span></span>

<span data-ttu-id="fc740-131">Microsoft [Edge Tools for Visual Studio Code][VisualstudioMarketplaceMicrosoftEdgeToolsVisualStudioCode] Visual Studio拡張機能を使用して、Microsoft Edge ブラウザーの **Elements** ツールを Visual Studio Code 内で使用します。</span><span class="sxs-lookup"><span data-stu-id="fc740-131">With the [Microsoft Edge Tools for Visual Studio Code][VisualstudioMarketplaceMicrosoftEdgeToolsVisualStudioCode] Visual Studio Code extension, use the **Elements** tool of the Microsoft Edge browser within Visual Studio Code.</span></span>  <span data-ttu-id="fc740-132">次のアクションに使用します。</span><span class="sxs-lookup"><span data-stu-id="fc740-132">Use it for the following actions.</span></span>  

*   <span data-ttu-id="fc740-133">インスタンスにアタッチするか、Microsoft Edge のインスタンスを起動します。</span><span class="sxs-lookup"><span data-stu-id="fc740-133">Attach to an instance or launch an instance of Microsoft Edge.</span></span>  
*   <span data-ttu-id="fc740-134">ランタイム HTML 構造を表示します。</span><span class="sxs-lookup"><span data-stu-id="fc740-134">Display the runtime HTML structure.</span></span>  
*   <span data-ttu-id="fc740-135">レイアウトを更新します。</span><span class="sxs-lookup"><span data-stu-id="fc740-135">Update the layout.</span></span>  
*   <span data-ttu-id="fc740-136">スタイルの問題を修正します。</span><span class="sxs-lookup"><span data-stu-id="fc740-136">Fix styling issues.</span></span>  
    
<span data-ttu-id="fc740-137">詳細については [、Microsoft Edge Tools for][VisualStudioCodeMicrosoftEdgeDevtoolsExtension]Visual Studio Code Visual Studio してください。</span><span class="sxs-lookup"><span data-stu-id="fc740-137">For more information, navigate to [Microsoft Edge Tools for Visual Studio Code Visual Studio Code extension][VisualStudioCodeMicrosoftEdgeDevtoolsExtension].</span></span>  <!--  Choose the following image to see the extension in action.  -->  
      
:::image type="complex" source="./media/microsoft-edge-tools-for-visual-studio-code.png" alt-text="Microsoft Edge Tools for Visual Studio Code Visual Studio Code extension in action" lightbox="./media/microsoft-edge-tools-for-visual-studio-code.png":::
   <span data-ttu-id="fc740-139">**Microsoft Edge Tools for Visual Studio Code** Visual Studioコード拡張機能の動作</span><span class="sxs-lookup"><span data-stu-id="fc740-139">**Microsoft Edge Tools for Visual Studio Code** Visual Studio Code extension in action</span></span>  
:::image-end:::  

## <span data-ttu-id="fc740-140">Webhint</span><span class="sxs-lookup"><span data-stu-id="fc740-140">webhint</span></span>  
      
<span data-ttu-id="fc740-141">[Webhint (カスタマイズ][WebhintMain]可能な linting ツール) を使用して、サイトの次の機能を向上します。</span><span class="sxs-lookup"><span data-stu-id="fc740-141">Use [webhint][WebhintMain], a customizable linting tool, to improve the following functionality of your site.</span></span>  

*   <span data-ttu-id="fc740-142">アクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="fc740-142">Accessibility</span></span>
*   <span data-ttu-id="fc740-143">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="fc740-143">Performance</span></span>
*   <span data-ttu-id="fc740-144">ブラウザー間の互換性</span><span class="sxs-lookup"><span data-stu-id="fc740-144">Cross-browser compatibility</span></span>
*   <span data-ttu-id="fc740-145">PWA の互換性</span><span class="sxs-lookup"><span data-stu-id="fc740-145">PWA compatibility</span></span>
*   <span data-ttu-id="fc740-146">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="fc740-146">Security</span></span>

<span data-ttu-id="fc740-147">コードでコーディングのプラクティスと一般的なエラーをチェックします。</span><span class="sxs-lookup"><span data-stu-id="fc740-147">It checks your code for coding practices and common errors.</span></span> <span data-ttu-id="fc740-148">最初に Microsoft Edge チームによって開発された webhint オープン ソース プロジェクトは [、OpenJS Foundation][OpenjsFoundation]の一部です。</span><span class="sxs-lookup"><span data-stu-id="fc740-148">The webhint open-source project, initially developed by the Microsoft Edge team, is now part of the [OpenJS Foundation][OpenjsFoundation].</span></span>  <span data-ttu-id="fc740-149">Microsoft Edge チームは、コミュニティの Web 開発者と共に Webhint に引き続き投稿します。</span><span class="sxs-lookup"><span data-stu-id="fc740-149">The Microsoft Edge team continues to contribute to webhint alongside web developers in the community.</span></span>  <!--  Choose the following image to see the extension in action.  -->  
      
:::image type="complex" source="./media/webhint-extension.png" alt-text="Webhint とコードVisual Studioのスクリーンショット" lightbox="./media/webhint-extension.png":::
   <span data-ttu-id="fc740-151">**Webhint Visual Studio** Code 拡張機能のスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="fc740-151">Screenshot of **webhint** Visual Studio Code extension</span></span>  
:::image-end:::  
      
<span data-ttu-id="fc740-152">Web サイトの問題を特定し、修正するには、Web サイト コードの [webhint 拡張機能Visual Studioします][VisualstudioMarketplaceWebhint]。</span><span class="sxs-lookup"><span data-stu-id="fc740-152">Identify and fix problems in your website by adding the [webhint extension for Visual Studio Code][VisualstudioMarketplaceWebhint].</span></span>  <span data-ttu-id="fc740-153">ヒントでは、HTML、CSS、JavaScript、TypeScript などについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fc740-153">Hints examine HTML, CSS, JavaScript, TypeScript, and more.</span></span>  <span data-ttu-id="fc740-154">ヒントはインラインの下線として表示され、[問題] ウィンドウ **に要約** されます。</span><span class="sxs-lookup"><span data-stu-id="fc740-154">Hints appear as inline underlines and are summarized in the **Problems** pane.</span></span>  
      
<span data-ttu-id="fc740-155">詳細については、コードで [webhint を使用する方法にVisual Studioしてください][VisualStudioCodeWebhint]。</span><span class="sxs-lookup"><span data-stu-id="fc740-155">For more information, navigate to [How to use webhint in Visual Studio Code][VisualStudioCodeWebhint].</span></span>  

<!--links -->  

[VisualStudioCodeDebuggerEdge]: ./debugger-for-edge.md "Microsoft Edge Visual Studio コード拡張機能のデバッガー |Microsoft Docs"  
[VisualStudioCodeMicrosoftEdgeDevtoolsExtension]: ./microsoft-edge-devtools-extension.md "Microsoft Edge DevTools for Visual Studio Code extension |Microsoft Docs"  
[VisualStudioCodeWebhint]: ./webhint.md "Webhint Visual Studio コード拡張 |Microsoft Docs"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio コード"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "ドキュメント |Visual Studio コード"   

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Microsoft Edge のデバッガー |Visual Studio Marketplace"  
[VisualstudioMarketplaceMicrosoftEdgeToolsVisualStudioCode]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code |Visual Studio Marketplace"  

[VisualstudioMarketplaceWebhint]: https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint "webhint |Visual Studio Marketplace"  

[WebhintMain]:  https://webhint.io "webhint"  
[OpenjsFoundation]:  https://openjsf.org "OpenJS Foundation"  
