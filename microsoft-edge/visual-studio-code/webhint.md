---
description: Visual Studio コードでの webhint の使い方
title: webhint VS コード拡張
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、vs コード、visual studio コード、web ヒント
ms.openlocfilehash: ec218fab8cbfb8181a0416c8e0eadc0e00412529
ms.sourcegitcommit: c1b5fdd48d39d874a76c9b8f68309eb1b507fd0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "10695860"
---
# Webhint Vs コード拡張  

カスタマイズ可能なカスタマイズされたカスタマイズされた機能[を使って][WebhintMain]、アクセシビリティ、パフォーマンス、クロスブラウザーの互換性、PWA の互換性、およびサイトのセキュリティを向上させることができます。  ベストプラクティスと一般的なエラーについてコードを確認します。 このオープンソースプロジェクトは、最初に Microsoft Edge チームによって開発されたものであり、 [Openjs Foundation][OpenjsFoundation]に含まれています。  Microsoft Edge チームは、コミュニティの web 開発者と共に web ヒントに投稿し続けています。  

:::image type="complex" source="./media/webhint-extension.png" alt-text="Web ヒントとコード拡張のスクリーンショット":::
   Web ヒントとコード拡張のスクリーンショット  
:::image-end:::

<!--![Screenshot of webhint VS Code extension][ImageWebhintExtension]  -->  

[VS コードの webhint 拡張機能][VisualstudioMarketplaceWebhint]を追加して、HTML、CSS、JavaScript、TypeScript などの問題を特定して修正します。  ヒントはインライン下線として表示され、[**問題**] ウィンドウに集計されます。  

## 構成  

この拡張機能では、HTML、CSS、テンプレートシステム \ (JSX/TSX、角速度など)、JavaScript/TypeScript などのヒントとパーサーをアクティブ化する[既定の構成][GithubWebhintioIndexjson]json ファイルが使用されます。  

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

アクティブ化されるヒントとパーサーをさらに制御する必要がある場合は、 `.hintrc` web ヒントを構成するためのローカルファイルを作成します。  特定のヒントからの出力に関するヘルプについては、「 [webhint ユーザーガイド][WebhintDocsUserguideConfiguringSummary]」を参照してください。  

## Webhint チームと連絡を取り合う  

[Webhint github リポジトリ][GithubWebhintio]の[問題を提出][GithubWebhintioIssuesNew]して、フィードバックを送信します。  

拡張機能に参加するには、「 [webhint とコード拡張の投稿ガイド][GithubWebhintioExtensionVscodeContributing]」を参照してください。  

## 関連項目  

*   [アクセシビリティ][AccessibilityIndex]  
*   [Visual Studio Code][VisualstudiocodeIndex]  

<!-- image links -->  

<!--[ImageWebhintExtension]: ./media/webhint-extension.png "Screenshot of webhint VS Code extension"  -->  

<!--links -->  

[AccessibilityIndex]: /microsoft-edge/accessibility "アクセシビリティ |Microsoft ドキュメント"  

[VisualstudiocodeIndex]: /microsoft-edge/visual-studio-code/index "Visual Studio コード |Microsoft ドキュメント"  

[GithubWebhintio]: https://github.com/webhintio/hint "web ヒント |GitHub"  
[GithubWebhintioExtensionVscodeContributing]: https://github.com/webhintio/hint/blob/master/packages/extension-vscode/CONTRIBUTING.md "投稿-web ヒント |GitHub"  
[GithubWebhintioIndexjson]: https://github.com/webhintio/hint/blob/master/packages/configuration-development/index.json "webhintio/hint |GitHub"
[GithubWebhintioIssuesNew]: https://github.com/webhintio/hint/issues/new "新しい問題-webhintio/ヒント |GitHub"  

[VisualstudioMarketplaceWebhint]: https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint "web ヒント |Visual Studio Marketplace"  

[OpenjsFoundation]:  https://openjsf.org "OpenJS Foundation"  

[WebhintDocsUserguideConfiguringSummary]: https://webhint.io/docs/user-guide/configuring-webhint/summary "Webhint | の構成webhint に関するドキュメント"  
[WebhintMain]:  https://webhint.io "web ヒント"  
