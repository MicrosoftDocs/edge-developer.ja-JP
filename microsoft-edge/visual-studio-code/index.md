---
description: Microsoft Edge (Chromium) と Visual Studio コード
title: Visual Studio Code
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/20/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、vs コード、visual studio コード、デバッガー、webhint
ms.openlocfilehash: 0d13c6eb9411f89e3a681176ade0caf8d59d46d8
ms.sourcegitcommit: 02c602379537ab3b9d0a355cea7fcf96fdbd8870
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2020
ms.locfileid: "11182745"
---
# <span data-ttu-id="c396f-104">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c396f-104">Visual Studio Code</span></span>  

<span data-ttu-id="c396f-105">[Visual Studio コード][VisualStudioCodeDocs] は、軽量であり、強力なソースコードエディターです。</span><span class="sxs-lookup"><span data-stu-id="c396f-105">[Visual Studio Code][VisualStudioCodeDocs] is a lightweight, but powerful source code editor.</span></span>  <span data-ttu-id="c396f-106">[Visual Studio コード][VisualStudioCodeDocs] は、Windows、Linux、macOS で利用できます。</span><span class="sxs-lookup"><span data-stu-id="c396f-106">[Visual Studio Code][VisualStudioCodeDocs] is available for Windows, Linux, and macOS.</span></span>  <span data-ttu-id="c396f-107">JavaScript、TypeScript、Node.js の組み込みサポートが含まれているため、これをカスタマイズするには、web 開発者向けの優れたツールです。</span><span class="sxs-lookup"><span data-stu-id="c396f-107">It includes built-in support for JavaScript, TypeScript, and Node.js, so it is a great tool for web developers before you customize it.</span></span>  <span data-ttu-id="c396f-108">まだ使っていない場合は、 [Visual Studio コード][VisualstudioCode]をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="c396f-108">If you are not using it yet, download [Visual Studio Code][VisualstudioCode].</span></span>  

## <span data-ttu-id="c396f-109">拡張機能</span><span class="sxs-lookup"><span data-stu-id="c396f-109">Extensions</span></span>  

<!--todo: We want to put something like the tiles for extensions Visual Studio Code uses on this page https://code.visualstudio.com/Docs#top-extensions but I don't think this is a markdown page.  I think it's a web page.  I couldn't find anything in https://github.com/Microsoft/vscode-docs that looks like this page. In the meantime, here's what I've come up with: -->  

<span data-ttu-id="c396f-110">以下で強調表示されている拡張機能を取得するには、 `Ctrl` + `Shift` + `X` `Command` + `Shift` + `X` Visual Studio コードで [extensions] ([Windows/Linux または macOS 上)] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c396f-110">To acquire any of the extensions highlighted below, navigate to Extensions \(select `Ctrl`+`Shift`+`X` on Windows/Linux or `Command`+`Shift`+`X` on macOS\) in Visual Studio Code.</span></span>  

<span data-ttu-id="c396f-111">市場で特定の拡張子を検索し、[ **インストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c396f-111">Search the Marketplace for the specific extension and choose **Install**.</span></span>  

:::image type="complex" source="./media/vscode-debugger-install.png" alt-text="Microsoft Edge Visual Studio のコード拡張用のデバッガーをインストールする" lightbox="./media/vscode-debugger-install.png":::
   <span data-ttu-id="c396f-113">Microsoft Edge Visual Studio のコード拡張 **用のデバッガーを** インストールする</span><span class="sxs-lookup"><span data-stu-id="c396f-113">Install the **Debugger for Microsoft Edge** Visual Studio Code extension</span></span>  
:::image-end:::  

:::row:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-debugger-for-microsoft-edge.msft.png" alt-text="Microsoft Edge Visual Studio コード拡張用デバッガー" lightbox="./media/visual-studio-code-extension-debugger-for-microsoft-edge.msft.png":::
         <span data-ttu-id="c396f-115">**Microsoft Edge 用デバッガー** Visual Studio コード拡張機能</span><span class="sxs-lookup"><span data-stu-id="c396f-115">**Debugger for Microsoft Edge** Visual Studio Code extension</span></span>  
      :::image-end:::  
      [<span data-ttu-id="c396f-116">Microsoft Edge 用デバッガー</span><span class="sxs-lookup"><span data-stu-id="c396f-116">Debugger for Microsoft Edge</span></span>](#debugger-for-microsoft-edge)  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-microsoft-edge-tools-for-visual-studio-code.msft.png" alt-text="Visual Studio コードの visual studio コード拡張のための Microsoft Edge ツール" lightbox="./media/visual-studio-code-extension-microsoft-edge-tools-for-visual-studio-code.msft.png":::
         <span data-ttu-id="c396f-118">**Microsoft Edge Tools For Visual Studio コード** Visual Studio コード拡張機能</span><span class="sxs-lookup"><span data-stu-id="c396f-118">**Microsoft Edge Tools for Visual Studio Code** Visual Studio Code extension</span></span>  
      :::image-end:::  
      [<span data-ttu-id="c396f-119">Microsoft Edge Tools for Visual Studio コード</span><span class="sxs-lookup"><span data-stu-id="c396f-119">Microsoft Edge Tools for Visual Studio Code</span></span>](#microsoft-edge-tools-for-visual-studio-code)  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-webhint.msft.png" alt-text="webhint Visual Studio コード拡張" lightbox="./media/visual-studio-code-extension-webhint.msft.png":::
         <span data-ttu-id="c396f-121">**web ヒント** Visual Studio コード拡張機能</span><span class="sxs-lookup"><span data-stu-id="c396f-121">**webhint** Visual Studio Code extension</span></span>  
      :::image-end:::  
      [<span data-ttu-id="c396f-122">Webhint</span><span class="sxs-lookup"><span data-stu-id="c396f-122">webhint</span></span>](#webhint)  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="c396f-123">Microsoft Edge 用デバッガー</span><span class="sxs-lookup"><span data-stu-id="c396f-123">Debugger for Microsoft Edge</span></span>  

<span data-ttu-id="c396f-124">Microsoft Edge Visual Studio コード拡張機能 [用のデバッガー][VisualstudioMarketplaceDebuggerMicrosoftEdge] を使うと、フロントエンド JavaScript コードを行ごとにデバッグし、 `console.log()` [Visual Studio コード][VisualstudioCode]からステートメントを直接表示することができます。</span><span class="sxs-lookup"><span data-stu-id="c396f-124">With the [Debugger for Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] Visual Studio Code extension, debug your front-end JavaScript code line-by-line and see `console.log()` statements directly from [Visual Studio Code][VisualstudioCode].</span></span>  
      
<span data-ttu-id="c396f-125">デバッガーツールを使って、Microsoft Edge \ (EdgeHTML \) と Microsoft Edge \ (Chromium \) の両方を起動または接続できます。</span><span class="sxs-lookup"><span data-stu-id="c396f-125">Using the Debugger tool, you may launch or attach to both Microsoft Edge \(EdgeHTML\) and Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="c396f-126">Visual Studio のコードと構成例から Microsoft Edge をデバッグする方法のチュートリアルについては `launch.json` 、「 [Microsoft Edge Visual Studio のコード拡張のデバッガー][VisualStudioCodeDebuggerEdge]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c396f-126">For a walkthrough of debugging Microsoft Edge from Visual Studio Code and sample `launch.json` configurations, navigate to [Debugger For Microsoft Edge Visual Studio Code Extension][VisualStudioCodeDebuggerEdge].</span></span>  <span data-ttu-id="c396f-127">次の画像を選択して、拡張機能の動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="c396f-127">Choose the following image to see the extension in action.</span></span>  

:::image type="complex" source="./media/debugger-for-edge.png" alt-text="Edge Visual Studio コード拡張機能のデバッガー" lightbox="./media/debugger-for-edge.gif":::
   <span data-ttu-id="c396f-129">**Microsoft Edge 用デバッガー** Visual Studio のコード拡張機能の動作</span><span class="sxs-lookup"><span data-stu-id="c396f-129">**Debugger for Microsoft Edge** Visual Studio Code extension in action</span></span>  
:::image-end:::  

## <span data-ttu-id="c396f-130">Microsoft Edge Tools for Visual Studio コード</span><span class="sxs-lookup"><span data-stu-id="c396f-130">Microsoft Edge Tools for Visual Studio Code</span></span>

<span data-ttu-id="c396f-131">[Microsoft Edge ツールの][VisualstudioMarketplaceMicrosoftEdgeToolsVisualStudioCode]visual studio コード拡張機能を使って、Visual studio コード内で microsoft edge ブラウザーの**要素**ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="c396f-131">With the [Microsoft Edge Tools for Visual Studio Code][VisualstudioMarketplaceMicrosoftEdgeToolsVisualStudioCode] Visual Studio Code extension, use the **Elements** tool of the Microsoft Edge browser within Visual Studio Code.</span></span>  <span data-ttu-id="c396f-132">次の操作に使用します。</span><span class="sxs-lookup"><span data-stu-id="c396f-132">Use it for the following actions.</span></span>  

*   <span data-ttu-id="c396f-133">インスタンスにアタッチするか、Microsoft Edge のインスタンスを起動します。</span><span class="sxs-lookup"><span data-stu-id="c396f-133">Attach to an instance or launch an instance of Microsoft Edge.</span></span>  
*   <span data-ttu-id="c396f-134">実行時の HTML 構造を表示します。</span><span class="sxs-lookup"><span data-stu-id="c396f-134">Display the runtime HTML structure.</span></span>  
*   <span data-ttu-id="c396f-135">レイアウトを更新します。</span><span class="sxs-lookup"><span data-stu-id="c396f-135">Update the layout.</span></span>  
*   <span data-ttu-id="c396f-136">スタイルの問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="c396f-136">Fix styling issues.</span></span>  
    
<span data-ttu-id="c396f-137">詳細については、「 [Microsoft Edge Tools For Visual studio Code Visual studio code extension][VisualStudioCodeMicrosoftEdgeDevtoolsExtension]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c396f-137">For more information, navigate to [Microsoft Edge Tools for Visual Studio Code Visual Studio Code extension][VisualStudioCodeMicrosoftEdgeDevtoolsExtension].</span></span>  <!--  Choose the following image to see the extension in action.  -->  
      
:::image type="complex" source="./media/microsoft-edge-tools-for-visual-studio-code.png" alt-text="Visual Studio の Visual studio のコード拡張機能を使用するための Microsoft Edge ツール" lightbox="./media/microsoft-edge-tools-for-visual-studio-code.png":::
   <span data-ttu-id="c396f-139">**Microsoft Edge Tools For Visual Studio コード** Visual Studio のコード拡張機能の動作</span><span class="sxs-lookup"><span data-stu-id="c396f-139">**Microsoft Edge Tools for Visual Studio Code** Visual Studio Code extension in action</span></span>  
:::image-end:::  

## <span data-ttu-id="c396f-140">Webhint</span><span class="sxs-lookup"><span data-stu-id="c396f-140">webhint</span></span>  
      
<span data-ttu-id="c396f-141">[Web][WebhintMain]サイトの次の機能を向上させるために、カスタマイズ可能なカスタマイズされたカスタマイズされた機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="c396f-141">Use [webhint][WebhintMain], a customizable linting tool, to improve the following functionality of your site.</span></span>  

*   <span data-ttu-id="c396f-142">アクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="c396f-142">Accessibility</span></span>
*   <span data-ttu-id="c396f-143">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="c396f-143">Performance</span></span>
*   <span data-ttu-id="c396f-144">ブラウザー間の互換性</span><span class="sxs-lookup"><span data-stu-id="c396f-144">Cross-browser compatibility</span></span>
*   <span data-ttu-id="c396f-145">PWA の互換性</span><span class="sxs-lookup"><span data-stu-id="c396f-145">PWA compatibility</span></span>
*   <span data-ttu-id="c396f-146">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="c396f-146">Security</span></span>

<span data-ttu-id="c396f-147">コードでコーディングの問題や一般的なエラーをチェックします。</span><span class="sxs-lookup"><span data-stu-id="c396f-147">It checks your code for coding practices and common errors.</span></span> <span data-ttu-id="c396f-148">Microsoft Edge チームによって最初に開発された webhint オープンソースプロジェクトが、 [Openjs Foundation][OpenjsFoundation]の一部になりました。</span><span class="sxs-lookup"><span data-stu-id="c396f-148">The webhint open-source project, initially developed by the Microsoft Edge team, is now part of the [OpenJS Foundation][OpenjsFoundation].</span></span>  <span data-ttu-id="c396f-149">Microsoft Edge チームは、コミュニティの web 開発者と共に web ヒントに投稿し続けています。</span><span class="sxs-lookup"><span data-stu-id="c396f-149">The Microsoft Edge team continues to contribute to webhint alongside web developers in the community.</span></span>  <!--  Choose the following image to see the extension in action.  -->  
      
:::image type="complex" source="./media/webhint-extension.png" alt-text="Webhint Visual Studio コード拡張のスクリーンショット" lightbox="./media/webhint-extension.png":::
   <span data-ttu-id="c396f-151">**Webhint** Visual Studio コード拡張のスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="c396f-151">Screenshot of **webhint** Visual Studio Code extension</span></span>  
:::image-end:::  
      
<span data-ttu-id="c396f-152">[Visual Studio コードの webhint 拡張機能][VisualstudioMarketplaceWebhint]を追加して、web サイトの問題を特定して修正します。</span><span class="sxs-lookup"><span data-stu-id="c396f-152">Identify and fix problems in your website by adding the [webhint extension for Visual Studio Code][VisualstudioMarketplaceWebhint].</span></span>  <span data-ttu-id="c396f-153">ヒント HTML、CSS、JavaScript、TypeScript などを調べます。</span><span class="sxs-lookup"><span data-stu-id="c396f-153">Hints examine HTML, CSS, JavaScript, TypeScript, and more.</span></span>  <span data-ttu-id="c396f-154">ヒントはインライン下線として表示され、[ **問題** ] ウィンドウに集計されます。</span><span class="sxs-lookup"><span data-stu-id="c396f-154">Hints appear as inline underlines and are summarized in the **Problems** pane.</span></span>  
      
<span data-ttu-id="c396f-155">詳細については、「 [Visual Studio コードでの webhint の使い方」][VisualStudioCodeWebhint]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c396f-155">For more information, navigate to [How to use webhint in Visual Studio Code][VisualStudioCodeWebhint].</span></span>  

<!--links -->  

[VisualStudioCodeDebuggerEdge]: ./debugger-for-edge.md "Microsoft Edge Visual Studio コード拡張機能のデバッガー |Microsoft ドキュメント"  
[VisualStudioCodeMicrosoftEdgeDevtoolsExtension]: ./microsoft-edge-devtools-extension.md "Microsoft Edge DevTools for Visual Studio コード拡張機能 |Microsoft ドキュメント"  
[VisualStudioCodeWebhint]: ./webhint.md "Webhint Visual Studio のコード拡張 |Microsoft ドキュメント"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio コード"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "ドキュメント |Visual Studio コード"   

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Microsoft Edge 用デバッガー |Visual Studio Marketplace"  
[VisualstudioMarketplaceMicrosoftEdgeToolsVisualStudioCode]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio コード |Visual Studio Marketplace"  

[VisualstudioMarketplaceWebhint]: https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint "web ヒント |Visual Studio Marketplace"  

[WebhintMain]:  https://webhint.io "web ヒント"  
[OpenjsFoundation]:  https://openjsf.org "OpenJS Foundation"  
