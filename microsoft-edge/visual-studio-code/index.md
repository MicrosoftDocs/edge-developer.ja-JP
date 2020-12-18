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
# Visual Studio Code の概要  

[Visual Studioは][VisualStudioCodeDocs] 、軽量で強力なソース コード エディターです。  [Visual Studioコード][VisualStudioCodeDocs] は、Windows、Linux、macOS で利用できます。  JavaScript、TypeScript、および Node.js の組み込みサポートが含まれるので、カスタマイズする前に Web 開発者に最適なツールです。  If you are not using it yet, download [Visual Studio Code][VisualstudioCode].  

## 拡張機能  

<!--todo: We want to put something like the tiles for extensions Visual Studio Code uses on this page https://code.visualstudio.com/Docs#top-extensions but I don't think this is a markdown page.  I think it's a web page.  I couldn't find anything in https://github.com/Microsoft/vscode-docs that looks like this page. In the meantime, here's what I've come up with: -->  

以下で強調表示されている拡張機能を取得するには、Visual Studio Code で Extensions \(Windows/Linux または macOS で選択 `Ctrl` + `Shift` + `X` `Command` + `Shift` + `X` )に移動します。  

Marketplace で特定の拡張機能を検索し、[インストール] を **選択します**。  

:::image type="complex" source="./media/vscode-debugger-install.png" alt-text="Microsoft Edge Visual Studio Code 拡張機能のデバッガーをインストールする" lightbox="./media/vscode-debugger-install.png":::
   Microsoft **Edge Visual Studio** Code 拡張機能のデバッガーをインストールする  
:::image-end:::  

:::row:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-debugger-for-microsoft-edge.msft.png" alt-text="Microsoft Edge Visual Studio Code 拡張機能のデバッガー" lightbox="./media/visual-studio-code-extension-debugger-for-microsoft-edge.msft.png":::
         **Microsoft Edge のデバッガー** Visual Studioコード拡張機能  
      :::image-end:::  
      [Microsoft Edge のデバッガー](#debugger-for-microsoft-edge)  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-microsoft-edge-tools-for-visual-studio-code.msft.png" alt-text="Microsoft Edge Tools for Visual Studio Code Visual Studio Extension" lightbox="./media/visual-studio-code-extension-microsoft-edge-tools-for-visual-studio-code.msft.png":::
         **Microsoft Edge Tools for Visual Studio Code** Visual Studioコード拡張機能  
      :::image-end:::  
      [Microsoft Edge Tools for Visual Studio Code](#microsoft-edge-tools-for-visual-studio-code)  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-webhint.msft.png" alt-text="webhint Visual Studio コード拡張機能" lightbox="./media/visual-studio-code-extension-webhint.msft.png":::
         **webhint** Visual Studioコード拡張機能  
      :::image-end:::  
      [Webhint](#webhint)  
   :::column-end:::
:::row-end:::  

## Microsoft Edge のデバッガー  

Microsoft [Edge Visual Studio][VisualstudioMarketplaceDebuggerMicrosoftEdge] Code 拡張機能のデバッガーを使用して、フロントエンド JavaScript コードを 1 行でデバッグし、コードから直接ステートメント `console.log()` [Visual Studioします][VisualstudioCode]。  
      
デバッガー ツールを使用すると、Microsoft Edge \(EdgeHTML\) と Microsoft Edge \(Chromium\) の両方を起動またはアタッチできます。  Visual Studio コードとサンプル構成から Microsoft Edge をデバッグするチュートリアルについては、Debugger For Microsoft Edge Visual Studio Code Extension に `launch.json` [移動します][VisualStudioCodeDebuggerEdge]。  次の画像を選択して、拡張機能の動作を確認します。  

:::image type="complex" source="./media/debugger-for-edge.png" alt-text="Edge Visual Studio コード拡張機能のデバッガーの動作" lightbox="./media/debugger-for-edge.gif":::
   **Microsoft Edge のデバッガー** Visual Studioコード拡張機能の動作  
:::image-end:::  

## Microsoft Edge Tools for Visual Studio Code

Microsoft [Edge Tools for Visual Studio Code][VisualstudioMarketplaceMicrosoftEdgeToolsVisualStudioCode] Visual Studio拡張機能を使用して、Microsoft Edge ブラウザーの **Elements** ツールを Visual Studio Code 内で使用します。  次のアクションに使用します。  

*   インスタンスにアタッチするか、Microsoft Edge のインスタンスを起動します。  
*   ランタイム HTML 構造を表示します。  
*   レイアウトを更新します。  
*   スタイルの問題を修正します。  
    
詳細については [、Microsoft Edge Tools for][VisualStudioCodeMicrosoftEdgeDevtoolsExtension]Visual Studio Code Visual Studio してください。  <!--  Choose the following image to see the extension in action.  -->  
      
:::image type="complex" source="./media/microsoft-edge-tools-for-visual-studio-code.png" alt-text="Microsoft Edge Tools for Visual Studio Code Visual Studio Code extension in action" lightbox="./media/microsoft-edge-tools-for-visual-studio-code.png":::
   **Microsoft Edge Tools for Visual Studio Code** Visual Studioコード拡張機能の動作  
:::image-end:::  

## Webhint  
      
[Webhint (カスタマイズ][WebhintMain]可能な linting ツール) を使用して、サイトの次の機能を向上します。  

*   アクセシビリティ
*   パフォーマンス
*   ブラウザー間の互換性
*   PWA の互換性
*   セキュリティ

コードでコーディングのプラクティスと一般的なエラーをチェックします。 最初に Microsoft Edge チームによって開発された webhint オープン ソース プロジェクトは [、OpenJS Foundation][OpenjsFoundation]の一部です。  Microsoft Edge チームは、コミュニティの Web 開発者と共に Webhint に引き続き投稿します。  <!--  Choose the following image to see the extension in action.  -->  
      
:::image type="complex" source="./media/webhint-extension.png" alt-text="Webhint とコードVisual Studioのスクリーンショット" lightbox="./media/webhint-extension.png":::
   **Webhint Visual Studio** Code 拡張機能のスクリーンショット  
:::image-end:::  
      
Web サイトの問題を特定し、修正するには、Web サイト コードの [webhint 拡張機能Visual Studioします][VisualstudioMarketplaceWebhint]。  ヒントでは、HTML、CSS、JavaScript、TypeScript などについて説明します。  ヒントはインラインの下線として表示され、[問題] ウィンドウ **に要約** されます。  
      
詳細については、コードで [webhint を使用する方法にVisual Studioしてください][VisualStudioCodeWebhint]。  

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
