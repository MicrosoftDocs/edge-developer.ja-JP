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
# Visual Studio Code の概要  

[Visual Studio Code][VisualStudioCodeDocs]軽量で強力なソース コード エディターです。  [Visual Studio Code、Linux、][VisualStudioCodeDocs]および macOS でWindows使用できます。  JavaScript、TypeScript、および Node.jsの組み込みサポートが含まれるので、カスタマイズする前に Web 開発者に最適なツールです。  まだ使用していない場合は[、次の][VisualstudioCode]Visual Studio Code。  

##  <a name="extensions"></a>拡張機能  

<!--todo: We want to put something like the tiles for extensions Visual Studio Code uses on this page https://code.visualstudio.com/Docs#top-extensions but I don't think this is a markdown page.  I think it's a web page.  I couldn't find anything in https://github.com/Microsoft/vscode-docs that looks like this page. In the meantime, here's what I've come up with: -->  

以下で強調表示されている拡張機能を取得するには、Visual Studio Code の拡張機能 \(Windows/Linux または `Ctrl` + `Shift` + `X` `Command` + `Shift` + `X` macOS\上で選択) に移動します。  

Marketplace で特定の拡張機能を検索し、[インストール] を **選択します**。  

:::image type="complex" source="./media/vscode-debugger-install.png" alt-text="デバッガーをインストールして拡張機能Microsoft Edge Visual Studio Codeする" lightbox="./media/vscode-debugger-install.png":::
   拡張機能の**デバッガーをMicrosoft Edge Visual Studio Code**する  
:::image-end:::  

:::row:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-debugger-for-microsoft-edge.msft.png" alt-text="デバッガーの拡張機能Microsoft Edge Visual Studio Codeする" lightbox="./media/visual-studio-code-extension-debugger-for-microsoft-edge.msft.png":::
         **拡張機能の**Microsoft Edge Visual Studio Codeデバッガー  
      :::image-end:::  
      [デバッガーのMicrosoft Edge](#debugger-for-microsoft-edge)  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-microsoft-edge-tools-for-visual-studio-code.msft.png" alt-text="Microsoft Edge拡張機能のVisual Studio Code Visual Studio Codeツール" lightbox="./media/visual-studio-code-extension-microsoft-edge-tools-for-visual-studio-code.msft.png":::
         **Microsoft Edge拡張機能のVisual Studio Code Visual Studio Code**ツール  
      :::image-end:::  
      [Microsoft EdgeツールのVisual Studio Code](#microsoft-edge-tools-for-visual-studio-code)  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-webhint.msft.png" alt-text="webhint Visual Studio Code拡張子" lightbox="./media/visual-studio-code-extension-webhint.msft.png":::
         **webhint Visual Studio Code**拡張子  
      :::image-end:::  
      [Webhint](#webhint)  
   :::column-end:::
:::row-end:::  

## デバッガーのMicrosoft Edge  

デバッガーの[拡張機能Microsoft Edge Visual Studio Code、][VisualstudioMarketplaceDebuggerMicrosoftEdge]フロントエンド JavaScript コードを 1 行に 1 行でデバッグし、そのコードから直接ステートメント `console.log()` [を参照][VisualstudioCode]Visual Studio Code。  
      
デバッガー ツールを使用すると、\(EdgeHTML\) と \(edgeHTML\) Microsoft Edge \(Chromium\Microsoft Edge) の両方を起動または接続できます。  アプリケーション構成とサンプル構成Microsoft EdgeデバッグVisual Studio Codeチュートリアルについては `launch.json` [、「Debugger For Microsoft Edge Visual Studio Code 拡張機能」に移動します][VisualStudioCodeDebuggerEdge]。  次の画像を選択して、拡張機能の動作を確認します。  

:::image type="complex" source="./media/debugger-for-edge.png" alt-text="アクション内のエッジ Visual Studio Codeデバッガー" lightbox="./media/debugger-for-edge.gif":::
   **アクション内Microsoft Edge Visual Studio Code**デバッガー  
:::image-end:::  

##  <a name="accessibility-in-microsoft-edge"></a>Microsoft EdgeツールのVisual Studio Code

拡張機能Microsoft Edge[ツールVisual Studio Code Visual Studio Code、Microsoft Edge][VisualstudioMarketplaceMicrosoftEdgeToolsVisualStudioCode]ブラウザーの Elements ツールを使用Visual Studio Code。 ****  次のアクションに使用します。  

*   インスタンスに接続するか、インスタンスのインスタンスを起動Microsoft Edge。  
*   ランタイム HTML 構造を表示します。  
*   レイアウトを更新します。  
*   スタイルの問題を修正します。  
    
詳細については、拡張機能の [Microsoft Edge[ツール] にVisual Studio Code Visual Studio Codeします][VisualStudioCodeMicrosoftEdgeDevtoolsExtension]。  <!--  Choose the following image to see the extension in action.  -->  
      
:::image type="complex" source="./media/microsoft-edge-tools-for-visual-studio-code.png" alt-text="Microsoft Edge操作中Visual Studio Code Visual Studio Code拡張機能のツール" lightbox="./media/microsoft-edge-tools-for-visual-studio-code.png":::
   **Microsoft Edge内線Visual Studio Code Visual Studio Code**ツール  
:::image-end:::  

##  <a name="webhint--"></a>webhint  
      
[Webhint (][WebhintMain]カスタマイズ可能なリント ツール) を使用して、サイトの次の機能を改善します。  

*   アクセシビリティ
*   パフォーマンス
*   ブラウザー間の互換性
*   PWA互換性
*   セキュリティ

コードのコーディング方法と一般的なエラーをチェックします。 webhint オープンソース プロジェクトは、当初はチームによって開発Microsoft Edge [OpenJS Foundation の一部です][OpenjsFoundation]。  チームMicrosoft Edgeコミュニティの Web 開発者と共に webhint に貢献し続ける。  <!--  Choose the following image to see the extension in action.  -->  
      
:::image type="complex" source="./media/webhint-extension.png" alt-text="webhint ファイル拡張子Visual Studio Codeスクリーンショット" lightbox="./media/webhint-extension.png":::
   **webhint ファイル拡張子**Visual Studio Codeスクリーンショット  
:::image-end:::  
      
webhint 拡張機能を追加して、Web サイトの問題を特定して[修正Visual Studio Code。][VisualstudioMarketplaceWebhint]  ヒントは、HTML、CSS、JavaScript、TypeScript などについて調べる。  ヒントはインラインの下線として表示され、[問題] ウィンドウ **に要約** されます。  
      
詳細については、「Webhint を使用[する方法」を参照Visual Studio Code。][VisualStudioCodeWebhint]  

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
