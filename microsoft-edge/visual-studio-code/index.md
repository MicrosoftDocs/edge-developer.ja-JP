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
# Visual Studio Code  

[Visual Studio コード][VisualStudioCodeDocs] は、軽量であり、強力なソースコードエディターです。  [Visual Studio コード][VisualStudioCodeDocs] は、Windows、Linux、macOS で利用できます。  JavaScript、TypeScript、Node.js の組み込みサポートが含まれているため、これをカスタマイズするには、web 開発者向けの優れたツールです。  まだ使っていない場合は、 [Visual Studio コード][VisualstudioCode]をダウンロードしてください。  

## 拡張機能  

<!--todo: We want to put something like the tiles for extensions Visual Studio Code uses on this page https://code.visualstudio.com/Docs#top-extensions but I don't think this is a markdown page.  I think it's a web page.  I couldn't find anything in https://github.com/Microsoft/vscode-docs that looks like this page. In the meantime, here's what I've come up with: -->  

以下で強調表示されている拡張機能を取得するには、 `Ctrl` + `Shift` + `X` `Command` + `Shift` + `X` Visual Studio コードで [extensions] ([Windows/Linux または macOS 上)] に移動します。  

市場で特定の拡張子を検索し、[ **インストール**] を選択します。  

:::image type="complex" source="./media/vscode-debugger-install.png" alt-text="Microsoft Edge Visual Studio のコード拡張用のデバッガーをインストールする" lightbox="./media/vscode-debugger-install.png":::
   Microsoft Edge Visual Studio のコード拡張 **用のデバッガーを** インストールする  
:::image-end:::  

:::row:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-debugger-for-microsoft-edge.msft.png" alt-text="Microsoft Edge Visual Studio コード拡張用デバッガー" lightbox="./media/visual-studio-code-extension-debugger-for-microsoft-edge.msft.png":::
         **Microsoft Edge 用デバッガー** Visual Studio コード拡張機能  
      :::image-end:::  
      [Microsoft Edge 用デバッガー](#debugger-for-microsoft-edge)  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-microsoft-edge-tools-for-visual-studio-code.msft.png" alt-text="Visual Studio コードの visual studio コード拡張のための Microsoft Edge ツール" lightbox="./media/visual-studio-code-extension-microsoft-edge-tools-for-visual-studio-code.msft.png":::
         **Microsoft Edge Tools For Visual Studio コード** Visual Studio コード拡張機能  
      :::image-end:::  
      [Microsoft Edge Tools for Visual Studio コード](#microsoft-edge-tools-for-visual-studio-code)  
   :::column-end:::
   :::column span="1":::
      :::image type="complex" source="./media/visual-studio-code-extension-webhint.msft.png" alt-text="webhint Visual Studio コード拡張" lightbox="./media/visual-studio-code-extension-webhint.msft.png":::
         **web ヒント** Visual Studio コード拡張機能  
      :::image-end:::  
      [Webhint](#webhint)  
   :::column-end:::
:::row-end:::  

## Microsoft Edge 用デバッガー  

Microsoft Edge Visual Studio コード拡張機能 [用のデバッガー][VisualstudioMarketplaceDebuggerMicrosoftEdge] を使うと、フロントエンド JavaScript コードを行ごとにデバッグし、 `console.log()` [Visual Studio コード][VisualstudioCode]からステートメントを直接表示することができます。  
      
デバッガーツールを使って、Microsoft Edge \ (EdgeHTML \) と Microsoft Edge \ (Chromium \) の両方を起動または接続できます。  Visual Studio のコードと構成例から Microsoft Edge をデバッグする方法のチュートリアルについては `launch.json` 、「 [Microsoft Edge Visual Studio のコード拡張のデバッガー][VisualStudioCodeDebuggerEdge]」を参照してください。  次の画像を選択して、拡張機能の動作を確認します。  

:::image type="complex" source="./media/debugger-for-edge.png" alt-text="Edge Visual Studio コード拡張機能のデバッガー" lightbox="./media/debugger-for-edge.gif":::
   **Microsoft Edge 用デバッガー** Visual Studio のコード拡張機能の動作  
:::image-end:::  

## Microsoft Edge Tools for Visual Studio コード

[Microsoft Edge ツールの][VisualstudioMarketplaceMicrosoftEdgeToolsVisualStudioCode]visual studio コード拡張機能を使って、Visual studio コード内で microsoft edge ブラウザーの**要素**ツールを使用します。  次の操作に使用します。  

*   インスタンスにアタッチするか、Microsoft Edge のインスタンスを起動します。  
*   実行時の HTML 構造を表示します。  
*   レイアウトを更新します。  
*   スタイルの問題を解決します。  
    
詳細については、「 [Microsoft Edge Tools For Visual studio Code Visual studio code extension][VisualStudioCodeMicrosoftEdgeDevtoolsExtension]」を参照してください。  <!--  Choose the following image to see the extension in action.  -->  
      
:::image type="complex" source="./media/microsoft-edge-tools-for-visual-studio-code.png" alt-text="Visual Studio の Visual studio のコード拡張機能を使用するための Microsoft Edge ツール" lightbox="./media/microsoft-edge-tools-for-visual-studio-code.png":::
   **Microsoft Edge Tools For Visual Studio コード** Visual Studio のコード拡張機能の動作  
:::image-end:::  

## Webhint  
      
[Web][WebhintMain]サイトの次の機能を向上させるために、カスタマイズ可能なカスタマイズされたカスタマイズされた機能を使用します。  

*   アクセシビリティ
*   パフォーマンス
*   ブラウザー間の互換性
*   PWA の互換性
*   セキュリティ

コードでコーディングの問題や一般的なエラーをチェックします。 Microsoft Edge チームによって最初に開発された webhint オープンソースプロジェクトが、 [Openjs Foundation][OpenjsFoundation]の一部になりました。  Microsoft Edge チームは、コミュニティの web 開発者と共に web ヒントに投稿し続けています。  <!--  Choose the following image to see the extension in action.  -->  
      
:::image type="complex" source="./media/webhint-extension.png" alt-text="Webhint Visual Studio コード拡張のスクリーンショット" lightbox="./media/webhint-extension.png":::
   **Webhint** Visual Studio コード拡張のスクリーンショット  
:::image-end:::  
      
[Visual Studio コードの webhint 拡張機能][VisualstudioMarketplaceWebhint]を追加して、web サイトの問題を特定して修正します。  ヒント HTML、CSS、JavaScript、TypeScript などを調べます。  ヒントはインライン下線として表示され、[ **問題** ] ウィンドウに集計されます。  
      
詳細については、「 [Visual Studio コードでの webhint の使い方」][VisualStudioCodeWebhint]を参照してください。  

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
