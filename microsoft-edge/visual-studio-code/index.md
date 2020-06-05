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
# Visual Studio Code  

[Visual Studio コード][VisualStudioCodeDocs]は軽量であり、デスクトップで実行される強力なソースコードエディターで、Windows、MacOS、Linux で利用できます。  JavaScript、TypeScript、および node.js の組み込みサポートが含まれているため、このボックスから直接、web 開発者向けの便利なツールです。  まだ使っていない場合は、 [Visual Studio コード][VisualstudioCode]をダウンロードしてください。  

## 拡張機能  

<!--Todo: We want to put something like the tiles for extensions VS Code uses on this page https://code.visualstudio.com/Docs#top-extensions but I don't think this is a markdown page.  I think it's a web page.  I couldn't find anything in https://github.com/Microsoft/vscode-docs that looks like this page. In the meantime, here's what I've come up with: -->  

以下で強調表示されている拡張機能を取得するには、 `Ctrl` + `Shift` + `X` `Command` + `Shift` + `X` VS コードの [extensions] (Windows または macOS の場合) に移動します。  

市場で特定の拡張子を検索し、[**インストール**] を選択します。  

:::image type="complex" source="./media/vscode-debugger-install.png" alt-text="Microsoft Edge VS コード拡張用のデバッガーのインストール":::
   Microsoft Edge VS コード拡張用のデバッガーのインストール  
:::image-end:::  

:::row:::
   :::column span="1":::
      ### Microsoft Edge 用デバッガー  

      [Microsoft Edge VS のコード拡張用デバッガー][VisualstudioMarketplaceDebuggerMicrosoftEdge]を使用して、フロントエンド JavaScript コードを行ごとにデバッグし、 `console.log()` [Visual Studio コード][VisualstudioCode]からステートメントを直接デバッグします。  
      
      デバッガーツールを使って、Microsoft Edge \ (EdgeHTML \) と Microsoft Edge \ (Chromium \) の両方を起動または接続できます。  VS コードとサンプルの構成から Microsoft Edge をデバッグする方法のチュートリアルについ `launch.json` ては、「 [MICROSOFT Edge VS コード拡張のデバッガー][VscodeDebuggerEdge]」をご覧ください。  次の画像を選択して、拡張機能の動作を確認します。  

      :::image type="content" source="./media/debugger-for-edge.png" alt-text="Edge VS のコード拡張のデバッガー" lightbox="./media/debugger-for-edge.gif":::  
   :::column-end:::
   :::column span="1":::
      ### Microsoft Edge の要素  
      
      Microsoft Edge VS コード拡張[の要素][VisualstudioMarketplaceElementsMicrosoftEdgeChromium]を使って、Visual Studio コード内から microsoft edge ブラウザーの要素ツールを使用します。  起動またはアタッチのどちらでも、要素ツールは Microsoft Edge のインスタンスに接続され、ランタイム HTML 構造が表示され、レイアウトの変更やスタイルの問題の修正を行うことができます。  
      
      詳細については、「 [Microsoft EDGE VS コード拡張の要素][VscodeElementsEdge]」を参照してください。  次の画像を選択して、拡張機能の動作を確認します。  
      
      :::image type="content" source="./media/elements-for-edge.png" alt-text="Edge VS コード拡張機能の要素" lightbox="./media/elements-for-edge.gif":::  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      ### Webhint
      
      カスタマイズ可能なカスタマイズされたカスタマイズされた機能[を使って][WebhintMain]、アクセシビリティ、パフォーマンス、クロスブラウザーの互換性、PWA の互換性、およびサイトのセキュリティを向上させることができます。  ベストプラクティスと一般的なエラーについてコードを確認します。 Microsoft Edge チームによって最初に開発された webhint オープンソースプロジェクトが、 [Openjs Foundation][OpenjsFoundation]の一部になりました。  Microsoft Edge チームは、コミュニティの web 開発者と共に web ヒントに投稿し続けています。  <!--Select the following image to see the extension in action.  -->  
      
      :::image type="content" source="./media/webhint-extension.png" alt-text="Web ヒントとコード拡張のスクリーンショット" lightbox="./media/webhint-extension.png":::  
      
      [VS コードの webhint 拡張機能][VisualstudioMarketplaceWebhint]を追加して、HTML、CSS、JavaScript、TypeScript などの問題を特定して修正します。  ヒントはインライン下線として表示され、[**問題**] ウィンドウに集計されます。  
      
      詳細については、「 [Visual Studio コードでの webhint][VscodeWebhint]の使い方」を参照してください。  
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
