---
description: コードで webhint をVisual Studioする方法
title: webhint Visual Studio コード拡張機能
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
# <a name="webhint-vs-code-extension"></a><span data-ttu-id="2e301-104">Webhint Vs Code Extension</span><span class="sxs-lookup"><span data-stu-id="2e301-104">Webhint Vs Code Extension</span></span>  

<span data-ttu-id="2e301-105">カスタマイズ可能なリント ツールである [webhint][WebhintMain]を使用して、サイトのアクセシビリティ、パフォーマンス、ブラウザー間の互換性、PWA の互換性、およびセキュリティを向上させます。</span><span class="sxs-lookup"><span data-stu-id="2e301-105">Use [webhint][WebhintMain], a customizable linting tool, to improve the accessibility, performance, cross-browser compatibility, PWA compatibility, and security of your site.</span></span>  <span data-ttu-id="2e301-106">コードでベスト プラクティスと一般的なエラーをチェックします。</span><span class="sxs-lookup"><span data-stu-id="2e301-106">It checks your code for best practices and common errors.</span></span> <span data-ttu-id="2e301-107">このオープン ソース プロジェクトは、Microsoft Edge チームによって最初に開発されましたが、 [現在は OpenJS Foundation の一部です][OpenjsFoundation]。</span><span class="sxs-lookup"><span data-stu-id="2e301-107">This open-source project, initially developed by the Microsoft Edge team, is now part of the [OpenJS Foundation][OpenjsFoundation].</span></span>  <span data-ttu-id="2e301-108">Microsoft Edge チームは、コミュニティの Web 開発者と共に Webhint に引き続き貢献しています。</span><span class="sxs-lookup"><span data-stu-id="2e301-108">The Microsoft Edge team continues to contribute to webhint alongside web developers in the community.</span></span>  

:::image type="complex" source="./media/webhint-extension.png" alt-text="Webhint Visual Studio Code 拡張機能のスクリーンショット":::
   <span data-ttu-id="2e301-110">Webhint Visual Studio Code 拡張機能のスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="2e301-110">Screenshot of webhint Visual Studio Code extension</span></span>  
:::image-end:::

<!--![Screenshot of webhint Visual Studio Code extension][ImageWebhintExtension]  -->  

<span data-ttu-id="2e301-111">HTML、CSS、JavaScript、TypeScript など、コードの [webhint][VisualstudioMarketplaceWebhint]拡張機能を追加して、問題を特定Visual Studioします。</span><span class="sxs-lookup"><span data-stu-id="2e301-111">Identify and fix problems in your HTML, CSS, JavaScript, TypeScript, and more by adding the [webhint extension for Visual Studio Code][VisualstudioMarketplaceWebhint].</span></span>  <span data-ttu-id="2e301-112">ヒントはインラインの下線として表示され、[問題] ウィンドウ **に要約** されます。</span><span class="sxs-lookup"><span data-stu-id="2e301-112">Hints appear as inline underlines and are summarized in the **Problems** pane.</span></span>  

## <a name="configuration"></a><span data-ttu-id="2e301-113">構成</span><span class="sxs-lookup"><span data-stu-id="2e301-113">Configuration</span></span>  

<span data-ttu-id="2e301-114">この拡張機能では、HTML、CSS、テンプレート システム \(JSX/TSX、Angular など)、JavaScript/TypeScript などのヒントとパーサーをアクティブ化する既定の構成 json ファイルを使用します。 [][GithubWebhintioIndexjson]</span><span class="sxs-lookup"><span data-stu-id="2e301-114">This extension uses a [default configuration][GithubWebhintioIndexjson] json file that activates hints and parsers for HTML, CSS, templating systems \(JSX/TSX, Angular, and so on\), JavaScript/TypeScript, and more.</span></span>  

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

<span data-ttu-id="2e301-115">アクティブ化されるヒントとパーサーを詳細に制御する場合は、webhint を構成するローカル ファイル `.hintrc` を作成します。</span><span class="sxs-lookup"><span data-stu-id="2e301-115">If you want more control over the hints and parsers that get activated, create a local `.hintrc` file to configure webhint.</span></span>  <span data-ttu-id="2e301-116">特定のヒントからの出力のヘルプについては [、webhint][WebhintDocsUserguideConfiguringSummary]ユーザー ガイドに移動します。</span><span class="sxs-lookup"><span data-stu-id="2e301-116">For help with output from specific hints, navigate to [webhint user guide][WebhintDocsUserguideConfiguringSummary].</span></span>  

## <a name="getting-in-touch-with-the-webhint-team"></a><span data-ttu-id="2e301-117">webhint チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="2e301-117">Getting in touch with the webhint team</span></span>  

<span data-ttu-id="2e301-118">[webhint GitHub][GithubWebhintio]リポジトリに問題を提出してフィードバックを送信します。 [][GithubWebhintioIssuesNew]</span><span class="sxs-lookup"><span data-stu-id="2e301-118">Send your feedback by [filing an issue][GithubWebhintioIssuesNew] in [webhint GitHub repo][GithubWebhintio].</span></span>  

<span data-ttu-id="2e301-119">拡張機能に貢献するには [、webhint Visual Studio コード拡張機能の投稿ガイド に移動します][GithubWebhintioExtensionVscodeContributing]。</span><span class="sxs-lookup"><span data-stu-id="2e301-119">To contribute to the extension, navigate to [webhint Visual Studio Code extension contribution guide][GithubWebhintioExtensionVscodeContributing].</span></span>  

## <a name="see-also"></a><span data-ttu-id="2e301-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e301-120">See also</span></span>  

*   [<span data-ttu-id="2e301-121">アクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="2e301-121">Accessibility</span></span>][AccessibilityIndex]  
*   [<span data-ttu-id="2e301-122">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2e301-122">Visual Studio Code</span></span>][VisualstudiocodeIndex]  

<!-- image links -->  

<!--[ImageWebhintExtension]: ./media/webhint-extension.png "Screenshot of webhint Visual Studio Code extension"  -->  

<!--links -->  

[AccessibilityIndex]: /microsoft-edge/accessibility "アクセシビリティ |Microsoft Docs"  

[VisualstudiocodeIndex]: /microsoft-edge/visual-studio-code/index "Visual Studio コード |Microsoft Docs"  

[GithubWebhintio]: https://github.com/webhintio/hint "webhint |GitHub"  
[GithubWebhintioExtensionVscodeContributing]: https://github.com/webhintio/hint/blob/master/packages/extension-vscode/CONTRIBUTING.md "寄稿 - webhint |GitHub"  
[GithubWebhintioIndexjson]: https://github.com/webhintio/hint/blob/master/packages/configuration-development/index.json "index.js- webhintio/hint |GitHub"
[GithubWebhintioIssuesNew]: https://github.com/webhintio/hint/issues/new "新しい問題 - webhintio/hint |GitHub"  

[VisualstudioMarketplaceWebhint]: https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint "webhint |Visual Studio Marketplace"  

[OpenjsFoundation]:  https://openjsf.org "OpenJS Foundation"  

[WebhintDocsUserguideConfiguringSummary]: https://webhint.io/docs/user-guide/configuring-webhint/summary "Webhint ファイルの|webhint ドキュメント"  
[WebhintMain]:  https://webhint.io "webhint"  
