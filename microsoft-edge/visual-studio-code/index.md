---
description: Microsoft Edge (Chromium) と Visual Studio Code
title: Visual Studio Code
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/20/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, vs code, visual studio code, Debugger, webhint
ms.openlocfilehash: 1aa5b66043e87ebb0f1b848dcd60e2553b378f36
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230692"
---
# <span data-ttu-id="dac22-104">Visual Studio Code の概要</span><span class="sxs-lookup"><span data-stu-id="dac22-104">Visual Studio Code overview</span></span>  

<span data-ttu-id="dac22-105">[Visual Studio Code][VisualStudioCodeDocs]軽量で強力なソース コード エディターです。</span><span class="sxs-lookup"><span data-stu-id="dac22-105">[Visual Studio Code][VisualStudioCodeDocs] is a lightweight, but powerful source code editor.</span></span>  <span data-ttu-id="dac22-106">[Visual Studio Code、Linux、][VisualStudioCodeDocs]および macOS でWindows使用できます。</span><span class="sxs-lookup"><span data-stu-id="dac22-106">[Visual Studio Code][VisualStudioCodeDocs] is available for Windows, Linux, and macOS.</span></span>  <span data-ttu-id="dac22-107">JavaScript、TypeScript、および Node.jsの組み込みサポートが含まれるので、カスタマイズする前に Web 開発者に最適なツールです。</span><span class="sxs-lookup"><span data-stu-id="dac22-107">It includes built-in support for JavaScript, TypeScript, and Node.js, so it is a great tool for web developers before you customize it.</span></span>  <span data-ttu-id="dac22-108">まだ使用していない場合は[、次の][VisualstudioCode]Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="dac22-108">If you are not using it yet, download [Visual Studio Code][VisualstudioCode].</span></span>  

## <span data-ttu-id="dac22-109">拡張機能</span><span class="sxs-lookup"><span data-stu-id="dac22-109">Extensions</span></span>  

<!--todo: We want to put something like the tiles for extensions Visual Studio Code uses on this page https://code.visualstudio.com/Docs#top-extensions but I don't think this is a markdown page.  I think it's a web page.  I couldn't find anything in https://github.com/Microsoft/vscode-docs that looks like this page. In the meantime, here's what I've come up with: -->  

<span data-ttu-id="dac22-110">以下で強調表示されている拡張機能を取得するには、Visual Studio Code の拡張機能 \(Windows/Linux または `Ctrl` + `Shift` + `X` `Command` + `Shift` + `X` macOS\上で選択) に移動します。</span><span class="sxs-lookup"><span data-stu-id="dac22-110">To acquire any of the extensions highlighted below, navigate to Extensions \(select `Ctrl`+`Shift`+`X` on Windows/Linux or `Command`+`Shift`+`X` on macOS\) in Visual Studio Code.</span></span>  

<span data-ttu-id="dac22-111">Marketplace で特定の拡張機能を検索し、[インストール] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="dac22-111">Search the Marketplace for the specific extension and choose **Install**.</span></span>  

:::image type="complex" source="./media/vscode-debugger-install.png" alt-text="デバッガーをインストールして拡張機能Microsoft Edge Visual Studio Codeする" lightbox="./media/vscode-debugger-install.png":::
   <span data-ttu-id="dac22-113">拡張機能の**デバッガーをMicrosoft Edge Visual Studio Code**する</span><span class="sxs-lookup"><span data-stu-id="dac22-113">Install the **Debugger for Microsoft Edge** Visual Studio Code extension</span></span>  
:::image-end:::  

:::row:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-debugger-for-microsoft-edge.msft.png" alt-text="デバッガーの拡張機能Microsoft Edge Visual Studio Codeする" lightbox="./media/visual-studio-code-extension-debugger-for-microsoft-edge.msft.png":::
         <span data-ttu-id="dac22-115">**拡張機能の**Microsoft Edge Visual Studio Codeデバッガー</span><span class="sxs-lookup"><span data-stu-id="dac22-115">**Debugger for Microsoft Edge** Visual Studio Code extension</span></span>  
      :::image-end:::  
      [<span data-ttu-id="dac22-116">デバッガーのMicrosoft Edge</span><span class="sxs-lookup"><span data-stu-id="dac22-116">Debugger for Microsoft Edge</span></span>](#debugger-for-microsoft-edge)  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-microsoft-edge-tools-for-visual-studio-code.msft.png" alt-text="Microsoft Edge拡張機能のVisual Studio Code Visual Studio Codeツール" lightbox="./media/visual-studio-code-extension-microsoft-edge-tools-for-visual-studio-code.msft.png":::
         <span data-ttu-id="dac22-118">**Microsoft Edge拡張機能のVisual Studio Code Visual Studio Code**ツール</span><span class="sxs-lookup"><span data-stu-id="dac22-118">**Microsoft Edge Tools for Visual Studio Code** Visual Studio Code extension</span></span>  
      :::image-end:::  
      [<span data-ttu-id="dac22-119">Microsoft EdgeツールのVisual Studio Code</span><span class="sxs-lookup"><span data-stu-id="dac22-119">Microsoft Edge Tools for Visual Studio Code</span></span>](#microsoft-edge-tools-for-visual-studio-code)  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-webhint.msft.png" alt-text="webhint Visual Studio Code拡張子" lightbox="./media/visual-studio-code-extension-webhint.msft.png":::
         <span data-ttu-id="dac22-121">**webhint Visual Studio Code**拡張子</span><span class="sxs-lookup"><span data-stu-id="dac22-121">**webhint** Visual Studio Code extension</span></span>  
      :::image-end:::  
      [<span data-ttu-id="dac22-122">Webhint</span><span class="sxs-lookup"><span data-stu-id="dac22-122">webhint</span></span>](#webhint)  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="dac22-123">デバッガーのMicrosoft Edge</span><span class="sxs-lookup"><span data-stu-id="dac22-123">Debugger for Microsoft Edge</span></span>  

<span data-ttu-id="dac22-124">デバッガーの[拡張機能Microsoft Edge Visual Studio Code、][VisualstudioMarketplaceDebuggerMicrosoftEdge]フロントエンド JavaScript コードを 1 行に 1 行でデバッグし、そのコードから直接ステートメント `console.log()` [を参照][VisualstudioCode]Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="dac22-124">With the [Debugger for Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] Visual Studio Code extension, debug your front-end JavaScript code line-by-line and see `console.log()` statements directly from [Visual Studio Code][VisualstudioCode].</span></span>  
      
<span data-ttu-id="dac22-125">デバッガー ツールを使用すると、\(EdgeHTML\) と \(edgeHTML\) Microsoft Edge \(Chromium\Microsoft Edge) の両方を起動または接続できます。</span><span class="sxs-lookup"><span data-stu-id="dac22-125">Using the Debugger tool, you may launch or attach to both Microsoft Edge \(EdgeHTML\) and Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="dac22-126">アプリケーション構成とサンプル構成Microsoft EdgeデバッグVisual Studio Codeチュートリアルについては `launch.json` [、「Debugger For Microsoft Edge Visual Studio Code 拡張機能」に移動します][VisualStudioCodeDebuggerEdge]。</span><span class="sxs-lookup"><span data-stu-id="dac22-126">For a walkthrough of debugging Microsoft Edge from Visual Studio Code and sample `launch.json` configurations, navigate to [Debugger For Microsoft Edge Visual Studio Code Extension][VisualStudioCodeDebuggerEdge].</span></span>  <span data-ttu-id="dac22-127">次の画像を選択して、拡張機能の動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="dac22-127">Choose the following image to see the extension in action.</span></span>  

:::image type="complex" source="./media/debugger-for-edge.png" alt-text="アクション内のエッジ Visual Studio Codeデバッガー" lightbox="./media/debugger-for-edge.gif":::
   <span data-ttu-id="dac22-129">**アクション内Microsoft Edge Visual Studio Code**デバッガー</span><span class="sxs-lookup"><span data-stu-id="dac22-129">**Debugger for Microsoft Edge** Visual Studio Code extension in action</span></span>  
:::image-end:::  

## <span data-ttu-id="dac22-130">Microsoft EdgeツールのVisual Studio Code</span><span class="sxs-lookup"><span data-stu-id="dac22-130">Microsoft Edge Tools for Visual Studio Code</span></span>

<span data-ttu-id="dac22-131">拡張機能Microsoft Edge[ツールVisual Studio Code Visual Studio Code、Microsoft Edge][VisualstudioMarketplaceMicrosoftEdgeToolsVisualStudioCode]ブラウザーの Elements ツールを使用Visual Studio Code。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="dac22-131">With the [Microsoft Edge Tools for Visual Studio Code][VisualstudioMarketplaceMicrosoftEdgeToolsVisualStudioCode] Visual Studio Code extension, use the **Elements** tool of the Microsoft Edge browser within Visual Studio Code.</span></span>  <span data-ttu-id="dac22-132">次のアクションに使用します。</span><span class="sxs-lookup"><span data-stu-id="dac22-132">Use it for the following actions.</span></span>  

*   <span data-ttu-id="dac22-133">インスタンスに接続するか、インスタンスのインスタンスを起動Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="dac22-133">Attach to an instance or launch an instance of Microsoft Edge.</span></span>  
*   <span data-ttu-id="dac22-134">ランタイム HTML 構造を表示します。</span><span class="sxs-lookup"><span data-stu-id="dac22-134">Display the runtime HTML structure.</span></span>  
*   <span data-ttu-id="dac22-135">レイアウトを更新します。</span><span class="sxs-lookup"><span data-stu-id="dac22-135">Update the layout.</span></span>  
*   <span data-ttu-id="dac22-136">スタイルの問題を修正します。</span><span class="sxs-lookup"><span data-stu-id="dac22-136">Fix styling issues.</span></span>  
    
<span data-ttu-id="dac22-137">詳細については、拡張機能の [Microsoft Edge[ツール] にVisual Studio Code Visual Studio Codeします][VisualStudioCodeMicrosoftEdgeDevtoolsExtension]。</span><span class="sxs-lookup"><span data-stu-id="dac22-137">For more information, navigate to [Microsoft Edge Tools for Visual Studio Code Visual Studio Code extension][VisualStudioCodeMicrosoftEdgeDevtoolsExtension].</span></span>  <!--  Choose the following image to see the extension in action.  -->  
      
:::image type="complex" source="./media/microsoft-edge-tools-for-visual-studio-code.png" alt-text="Microsoft Edge操作中Visual Studio Code Visual Studio Code拡張機能のツール" lightbox="./media/microsoft-edge-tools-for-visual-studio-code.png":::
   <span data-ttu-id="dac22-139">**Microsoft Edge内線Visual Studio Code Visual Studio Code**ツール</span><span class="sxs-lookup"><span data-stu-id="dac22-139">**Microsoft Edge Tools for Visual Studio Code** Visual Studio Code extension in action</span></span>  
:::image-end:::  

## <span data-ttu-id="dac22-140">Webhint</span><span class="sxs-lookup"><span data-stu-id="dac22-140">webhint</span></span>  
      
<span data-ttu-id="dac22-141">[Webhint (][WebhintMain]カスタマイズ可能なリント ツール) を使用して、サイトの次の機能を改善します。</span><span class="sxs-lookup"><span data-stu-id="dac22-141">Use [webhint][WebhintMain], a customizable linting tool, to improve the following functionality of your site.</span></span>  

*   <span data-ttu-id="dac22-142">アクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="dac22-142">Accessibility</span></span>
*   <span data-ttu-id="dac22-143">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="dac22-143">Performance</span></span>
*   <span data-ttu-id="dac22-144">ブラウザー間の互換性</span><span class="sxs-lookup"><span data-stu-id="dac22-144">Cross-browser compatibility</span></span>
*   <span data-ttu-id="dac22-145">PWA互換性</span><span class="sxs-lookup"><span data-stu-id="dac22-145">PWA compatibility</span></span>
*   <span data-ttu-id="dac22-146">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="dac22-146">Security</span></span>

<span data-ttu-id="dac22-147">コードのコーディング方法と一般的なエラーをチェックします。</span><span class="sxs-lookup"><span data-stu-id="dac22-147">It checks your code for coding practices and common errors.</span></span> <span data-ttu-id="dac22-148">webhint オープンソース プロジェクトは、当初はチームによって開発Microsoft Edge [OpenJS Foundation の一部です][OpenjsFoundation]。</span><span class="sxs-lookup"><span data-stu-id="dac22-148">The webhint open-source project, initially developed by the Microsoft Edge team, is now part of the [OpenJS Foundation][OpenjsFoundation].</span></span>  <span data-ttu-id="dac22-149">チームMicrosoft Edgeコミュニティの Web 開発者と共に webhint に貢献し続ける。</span><span class="sxs-lookup"><span data-stu-id="dac22-149">The Microsoft Edge team continues to contribute to webhint alongside web developers in the community.</span></span>  <!--  Choose the following image to see the extension in action.  -->  
      
:::image type="complex" source="./media/webhint-extension.png" alt-text="webhint ファイル拡張子Visual Studio Codeスクリーンショット" lightbox="./media/webhint-extension.png":::
   <span data-ttu-id="dac22-151">**webhint ファイル拡張子**Visual Studio Codeスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="dac22-151">Screenshot of **webhint** Visual Studio Code extension</span></span>  
:::image-end:::  
      
<span data-ttu-id="dac22-152">webhint 拡張機能を追加して、Web サイトの問題を特定して[修正Visual Studio Code。][VisualstudioMarketplaceWebhint]</span><span class="sxs-lookup"><span data-stu-id="dac22-152">Identify and fix problems in your website by adding the [webhint extension for Visual Studio Code][VisualstudioMarketplaceWebhint].</span></span>  <span data-ttu-id="dac22-153">ヒントは、HTML、CSS、JavaScript、TypeScript などについて調べる。</span><span class="sxs-lookup"><span data-stu-id="dac22-153">Hints examine HTML, CSS, JavaScript, TypeScript, and more.</span></span>  <span data-ttu-id="dac22-154">ヒントはインラインの下線として表示され、[問題] ウィンドウ **に要約** されます。</span><span class="sxs-lookup"><span data-stu-id="dac22-154">Hints appear as inline underlines and are summarized in the **Problems** pane.</span></span>  
      
<span data-ttu-id="dac22-155">詳細については、「Webhint を使用[する方法」を参照Visual Studio Code。][VisualStudioCodeWebhint]</span><span class="sxs-lookup"><span data-stu-id="dac22-155">For more information, navigate to [How to use webhint in Visual Studio Code][VisualStudioCodeWebhint].</span></span>  

<!--links -->  

[VisualStudioCodeDebuggerEdge]: ./debugger-for-edge.md "デバッガー の拡張機能Microsoft Edge Visual Studio Codeの|Microsoft Docs"  
[VisualStudioCodeMicrosoftEdgeDevtoolsExtension]: ./microsoft-edge-devtools-extension.md "Microsoft EdgeDevTools for Visual Studio Code |Microsoft Docs"  
[VisualStudioCodeWebhint]: ./webhint.md "Webhint Visual Studio Code 拡張機能 |Microsoft Docs"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio Code"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "ドキュメント |Visual Studio Code"   

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "デバッガーのMicrosoft Edge |Visual StudioMarketplace"  
[VisualstudioMarketplaceMicrosoftEdgeToolsVisualStudioCode]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code | Visual Studio Marketplace"  

[VisualstudioMarketplaceWebhint]: https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint "webhint |Visual StudioMarketplace"  

[WebhintMain]:  https://webhint.io "webhint"  
[OpenjsFoundation]:  https://openjsf.org "OpenJS Foundation"  
