---
description: webhint を使用するVisual Studio Code
title: webhint Visual Studio Code拡張子
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, vs code, visual studio code, webhint
ms.openlocfilehash: 3dfd900bf818d02dbc8123c00e7928e56d9b6ade
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399275"
---
# <a name="webhint-vs-code-extension"></a>Webhint Vs Code Extension  

カスタマイズ可能なリント ツールである[webhint][WebhintMain]を使用して、サイトのアクセシビリティ、パフォーマンス、ブラウザー間の互換性、PWA互換性、およびセキュリティを向上させます。  コードでベスト プラクティスと一般的なエラーをチェックします。 このオープンソース プロジェクトは、最初はチームによって開発Microsoft Edge [OpenJS Foundation の一部です][OpenjsFoundation]。  チームMicrosoft Edgeコミュニティの Web 開発者と共に webhint に貢献し続ける。  

:::image type="complex" source="./media/webhint-extension.png" alt-text="webhint ファイル拡張子Visual Studio Codeスクリーンショット":::
   webhint ファイル拡張子Visual Studio Codeスクリーンショット  
:::image-end:::

<!--![Screenshot of webhint Visual Studio Code extension][ImageWebhintExtension]  -->  

HTML、CSS、JavaScript、TypeScript など、HTML、CSS、TypeScript の問題を特定して[修正するには、webhint][VisualstudioMarketplaceWebhint]拡張機能を追加Visual Studio Code。  ヒントはインラインの下線として表示され、[問題] ウィンドウ **に要約** されます。  

## <a name="configuration"></a>構成  

この拡張機能では、HTML、CSS、テンプレート システム \(JSX/TSX、Angular など)、JavaScript/TypeScript などのヒントとパーサーをアクティブ化する既定の構成 json ファイルを使用します。 [][GithubWebhintioIndexjson]  

```json
{
    "connector": "local",
    "extends": [
        "accessibility",
        "progressive-web-apps"
    ],
    "formatters": [
        "html",
        "summary"
    ],
    "hints": [
        "apple-touch-icons",
        "button-type",
        "compat-api/css",
        "compat-api/html",
        "create-element-svg",
        "css-prefix-order",
        "disown-opener",
        "highest-available-document-mode",
        "manifest-exists",
        "meta-charset-utf-8",
        "meta-viewport",
        "no-bom",
        "no-protocol-relative-urls",
        "scoped-svg-styles",
        "sri",
        "typescript-config/consistent-casing",
        "typescript-config/import-helpers",
        "typescript-config/is-valid",
        "typescript-config/no-comments",
        "typescript-config/strict",
        "typescript-config/target"
    ],
    "hintsTimeout": 10000,
    "parsers": [
        "babel-config",
        "css",
        "html",
        "javascript",
        "jsx",
        "less",
        "sass",
        "typescript",
        "typescript-config",
        "webpack-config"
    ]
}
```  

アクティブ化されるヒントとパーサーを詳細に制御する場合は、webhint を構成するローカル ファイル `.hintrc` を作成します。  特定のヒントからの出力のヘルプについては [、webhint][WebhintDocsUserguideConfiguringSummary]ユーザー ガイドに移動します。  

## <a name="getting-in-touch-with-the-webhint-team"></a>webhint チームと連絡を取る  

[webhint][GithubWebhintio]ファイルに[問題を提出][GithubWebhintioIssuesNew]してフィードバックを送信GitHubします。  

拡張機能に貢献するには[、webhint Visual Studio Codeに移動します][GithubWebhintioExtensionVscodeContributing]。  

## <a name="see-also"></a>関連項目  

*   [アクセシビリティ][AccessibilityIndex]  
*   [Visual Studio Code][VisualstudiocodeIndex]  

<!-- image links -->  

<!--[ImageWebhintExtension]: ./media/webhint-extension.png "Screenshot of webhint Visual Studio Code extension"  -->  

<!--links -->  

[AccessibilityIndex]: /microsoft-edge/accessibility "アクセシビリティ |Microsoft Docs"  

[VisualstudiocodeIndex]: /microsoft-edge/visual-studio-code/index "Visual Studio Code |Microsoft Docs"  

[GithubWebhintio]: https://github.com/webhintio/hint "webhint |GitHub"  
[GithubWebhintioExtensionVscodeContributing]: https://github.com/webhintio/hint/blob/master/packages/extension-vscode/CONTRIBUTING.md "寄稿 - webhint |GitHub"  
[GithubWebhintioIndexjson]: https://github.com/webhintio/hint/blob/master/packages/configuration-development/index.json "index.js- webhintio/hint |GitHub"
[GithubWebhintioIssuesNew]: https://github.com/webhintio/hint/issues/new "新しい問題 - webhintio/hint |GitHub"  

[VisualstudioMarketplaceWebhint]: https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint "webhint |Visual StudioMarketplace"  

[OpenjsFoundation]:  https://openjsf.org "OpenJS Foundation"  

[WebhintDocsUserguideConfiguringSummary]: https://webhint.io/docs/user-guide/configuring-webhint/summary "Webhint ファイルの|webhint ドキュメント"  
[WebhintMain]:  https://webhint.io "webhint"  
