---
description: Microsoft Edge (Chromium) と Visual Studio コード
title: Visual Studio Code
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、vs コード、visual studio コード、デバッガー、webhint
ms.openlocfilehash: e178612d9db8ce3223bb5158c4557675d3314e15
ms.sourcegitcommit: c1b5fdd48d39d874a76c9b8f68309eb1b507fd0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "10695884"
---
# <span data-ttu-id="57e5f-104">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="57e5f-104">Visual Studio Code</span></span>  

<span data-ttu-id="57e5f-105">[Visual Studio コード][VisualStudioCodeDocs]は軽量であり、デスクトップで実行される強力なソースコードエディターで、Windows、MacOS、Linux で利用できます。</span><span class="sxs-lookup"><span data-stu-id="57e5f-105">[Visual Studio Code][VisualStudioCodeDocs] is a lightweight, but powerful source code editor that runs on your desktop and is available for Windows, macOS, and Linux.</span></span>  <span data-ttu-id="57e5f-106">JavaScript、TypeScript、および node.js の組み込みサポートが含まれているため、このボックスから直接、web 開発者向けの便利なツールです。</span><span class="sxs-lookup"><span data-stu-id="57e5f-106">It comes with built-in support for JavaScript, TypeScript, and Node.js, so it is a great tool for web developers right out of the box!</span></span>  <span data-ttu-id="57e5f-107">まだ使っていない場合は、 [Visual Studio コード][VisualstudioCode]をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="57e5f-107">If you are not using it yet, download [Visual Studio Code][VisualstudioCode].</span></span>  

## <span data-ttu-id="57e5f-108">拡張機能</span><span class="sxs-lookup"><span data-stu-id="57e5f-108">Extensions</span></span>  

<!--Todo: We want to put something like the tiles for extensions VS Code uses on this page https://code.visualstudio.com/Docs#top-extensions but I don't think this is a markdown page.  I think it's a web page.  I couldn't find anything in https://github.com/Microsoft/vscode-docs that looks like this page. In the meantime, here's what I've come up with: -->  

<span data-ttu-id="57e5f-109">以下で強調表示されている拡張機能を取得するには、 `Ctrl` + `Shift` + `X` `Command` + `Shift` + `X` VS コードの [extensions] (Windows または macOS の場合) に移動します。</span><span class="sxs-lookup"><span data-stu-id="57e5f-109">To acquire any of the extensions highlighted below, navigate to Extensions \(`Ctrl`+`Shift`+`X` on Windows or `Command`+`Shift`+`X` on macOS\) in VS Code.</span></span>  

<span data-ttu-id="57e5f-110">市場で特定の拡張子を検索し、[**インストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="57e5f-110">Search the Marketplace for the specific extension and select **Install**.</span></span>  

:::image type="complex" source="./media/vscode-debugger-install.png" alt-text="Microsoft Edge VS コード拡張用のデバッガーのインストール":::
   <span data-ttu-id="57e5f-112">Microsoft Edge VS コード拡張用のデバッガーのインストール</span><span class="sxs-lookup"><span data-stu-id="57e5f-112">Installing the Debugger for Microsoft Edge VS Code extension</span></span>  
:::image-end:::  

:::row:::
   :::column span="1":::
      ### <span data-ttu-id="57e5f-113">Microsoft Edge 用デバッガー</span><span class="sxs-lookup"><span data-stu-id="57e5f-113">Debugger for Microsoft Edge</span></span>  

      <span data-ttu-id="57e5f-114">[Microsoft Edge VS のコード拡張用デバッガー][VisualstudioMarketplaceDebuggerMicrosoftEdge]を使用して、フロントエンド JavaScript コードを行ごとにデバッグし、 `console.log()` [Visual Studio コード][VisualstudioCode]からステートメントを直接デバッグします。</span><span class="sxs-lookup"><span data-stu-id="57e5f-114">With the [Debugger for Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] VS Code extension, debug your front-end JavaScript code line-by-line and see `console.log()` statements directly from [Visual Studio Code][VisualstudioCode]!</span></span>  
      
      <span data-ttu-id="57e5f-115">デバッガーツールを使って、Microsoft Edge \ (EdgeHTML \) と Microsoft Edge \ (Chromium \) の両方を起動または接続できます。</span><span class="sxs-lookup"><span data-stu-id="57e5f-115">Using the Debugger tool, you may launch or attach to both Microsoft Edge \(EdgeHTML\) and Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="57e5f-116">VS コードとサンプルの構成から Microsoft Edge をデバッグする方法のチュートリアルについ `launch.json` ては、「 [MICROSOFT Edge VS コード拡張のデバッガー][VscodeDebuggerEdge]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="57e5f-116">For a walkthrough of debugging Microsoft Edge from VS Code and sample `launch.json` configurations, see [Debugger For Microsoft Edge VS Code Extension][VscodeDebuggerEdge].</span></span>  <span data-ttu-id="57e5f-117">次の画像を選択して、拡張機能の動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="57e5f-117">Select the following image to see the extension in action.</span></span>  

      :::image type="content" source="./media/debugger-for-edge.png" alt-text="Edge VS のコード拡張のデバッガー" lightbox="./media/debugger-for-edge.gif":::  
   :::column-end:::
   :::column span="1":::
      ### <span data-ttu-id="57e5f-119">Microsoft Edge の要素</span><span class="sxs-lookup"><span data-stu-id="57e5f-119">Elements for Microsoft Edge</span></span>  
      
      <span data-ttu-id="57e5f-120">Microsoft Edge VS コード拡張[の要素][VisualstudioMarketplaceElementsMicrosoftEdgeChromium]を使って、Visual Studio コード内から microsoft edge ブラウザーの要素ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="57e5f-120">With the [Elements for Microsoft Edge][VisualstudioMarketplaceElementsMicrosoftEdgeChromium] VS Code extension, use the Elements tool of the Microsoft Edge browser from within Visual Studio Code.</span></span>  <span data-ttu-id="57e5f-121">起動またはアタッチのどちらでも、要素ツールは Microsoft Edge のインスタンスに接続され、ランタイム HTML 構造が表示され、レイアウトの変更やスタイルの問題の修正を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="57e5f-121">By either launching or attaching, the Elements tool connects to an instance of Microsoft Edge, displays the runtime HTML structure, and allows you to alter the layout or fix styling issues.</span></span>  
      
      <span data-ttu-id="57e5f-122">詳細については、「 [Microsoft EDGE VS コード拡張の要素][VscodeElementsEdge]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57e5f-122">For more information, see [Elements for Microsoft Edge VS Code extension][VscodeElementsEdge].</span></span>  <span data-ttu-id="57e5f-123">次の画像を選択して、拡張機能の動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="57e5f-123">Select the following image to see the extension in action.</span></span>  
      
      :::image type="content" source="./media/elements-for-edge.png" alt-text="Edge VS コード拡張機能の要素" lightbox="./media/elements-for-edge.gif":::  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      ### <span data-ttu-id="57e5f-125">Webhint</span><span class="sxs-lookup"><span data-stu-id="57e5f-125">webhint</span></span>
      
      <span data-ttu-id="57e5f-126">カスタマイズ可能なカスタマイズされたカスタマイズされた機能[を使って][WebhintMain]、アクセシビリティ、パフォーマンス、クロスブラウザーの互換性、PWA の互換性、およびサイトのセキュリティを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="57e5f-126">Use [webhint][WebhintMain], a customizable linting tool, to improve the accessibility, performance, cross-browser compatibility, PWA compatibility, and security of your site.</span></span>  <span data-ttu-id="57e5f-127">ベストプラクティスと一般的なエラーについてコードを確認します。</span><span class="sxs-lookup"><span data-stu-id="57e5f-127">It checks your code for best practices and common errors.</span></span> <span data-ttu-id="57e5f-128">Microsoft Edge チームによって最初に開発された webhint オープンソースプロジェクトが、 [Openjs Foundation][OpenjsFoundation]の一部になりました。</span><span class="sxs-lookup"><span data-stu-id="57e5f-128">The webhint open-source project, initially developed by the Microsoft Edge team, is now part of the [OpenJS Foundation][OpenjsFoundation].</span></span>  <span data-ttu-id="57e5f-129">Microsoft Edge チームは、コミュニティの web 開発者と共に web ヒントに投稿し続けています。</span><span class="sxs-lookup"><span data-stu-id="57e5f-129">The Microsoft Edge team continues to contribute to webhint alongside web developers in the community.</span></span>  <!--Select the following image to see the extension in action.  -->  
      
      :::image type="content" source="./media/webhint-extension.png" alt-text="Web ヒントとコード拡張のスクリーンショット" lightbox="./media/webhint-extension.png":::  
      
      <span data-ttu-id="57e5f-131">[VS コードの webhint 拡張機能][VisualstudioMarketplaceWebhint]を追加して、HTML、CSS、JavaScript、TypeScript などの問題を特定して修正します。</span><span class="sxs-lookup"><span data-stu-id="57e5f-131">Identify and fix problems in your HTML, CSS, JavaScript, TypeScript, and more by adding the [webhint extension for VS Code][VisualstudioMarketplaceWebhint].</span></span>  <span data-ttu-id="57e5f-132">ヒントはインライン下線として表示され、[**問題**] ウィンドウに集計されます。</span><span class="sxs-lookup"><span data-stu-id="57e5f-132">Hints appear as inline underlines and are summarized in the **Problems** pane.</span></span>  
      
      <span data-ttu-id="57e5f-133">詳細については、「 [Visual Studio コードでの webhint][VscodeWebhint]の使い方」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57e5f-133">For more information, see [How to use webhint in Visual Studio Code][VscodeWebhint].</span></span>  
   :::column-end:::
   :::column span="1":::
      <!--Empty to retain grid  -->  
   :::column-end:::
:::row-end:::

<!-- image links -->  

<!--links -->  

[VscodeDebuggerEdge]: ./debugger-for-edge.md "Microsoft Edge VS コード拡張用デバッガー |Microsoft ドキュメント"  
[VscodeElementsEdge]: ./elements-for-edge.md "Microsoft Edge VS コード拡張の要素 |Microsoft ドキュメント"  
[VscodeWebhint]: ./webhint.md "Webhint VS コード拡張 |Microsoft ドキュメント"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio コード"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "ドキュメント |Visual Studio コード"   

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Microsoft Edge 用デバッガー |Visual Studio Marketplace"  
[VisualstudioMarketplaceElementsMicrosoftEdgeChromium]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge の要素 (Chromium) |Visual Studio Marketplace"  

[VisualstudioMarketplaceWebhint]: https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint "web ヒント |Visual Studio Marketplace"  

[WebhintMain]:  https://webhint.io "web ヒント"  
[OpenjsFoundation]:  https://openjsf.org "OpenJS Foundation"  
