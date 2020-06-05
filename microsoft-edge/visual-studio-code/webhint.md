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
# <span data-ttu-id="25907-104">Webhint Vs コード拡張</span><span class="sxs-lookup"><span data-stu-id="25907-104">Webhint Vs Code Extension</span></span>  

<span data-ttu-id="25907-105">カスタマイズ可能なカスタマイズされたカスタマイズされた機能[を使って][WebhintMain]、アクセシビリティ、パフォーマンス、クロスブラウザーの互換性、PWA の互換性、およびサイトのセキュリティを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="25907-105">Use [webhint][WebhintMain], a customizable linting tool, to improve the accessibility, performance, cross-browser compatibility, PWA compatibility, and security of your site.</span></span>  <span data-ttu-id="25907-106">ベストプラクティスと一般的なエラーについてコードを確認します。</span><span class="sxs-lookup"><span data-stu-id="25907-106">It checks your code for best practices and common errors.</span></span> <span data-ttu-id="25907-107">このオープンソースプロジェクトは、最初に Microsoft Edge チームによって開発されたものであり、 [Openjs Foundation][OpenjsFoundation]に含まれています。</span><span class="sxs-lookup"><span data-stu-id="25907-107">This open-source project, initially developed by the Microsoft Edge team, is now part of the [OpenJS Foundation][OpenjsFoundation].</span></span>  <span data-ttu-id="25907-108">Microsoft Edge チームは、コミュニティの web 開発者と共に web ヒントに投稿し続けています。</span><span class="sxs-lookup"><span data-stu-id="25907-108">The Microsoft Edge team continues to contribute to webhint alongside web developers in the community.</span></span>  

:::image type="complex" source="./media/webhint-extension.png" alt-text="Web ヒントとコード拡張のスクリーンショット":::
   <span data-ttu-id="25907-110">Web ヒントとコード拡張のスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="25907-110">Screenshot of webhint VS Code extension</span></span>  
:::image-end:::

<!--![Screenshot of webhint VS Code extension][ImageWebhintExtension]  -->  

<span data-ttu-id="25907-111">[VS コードの webhint 拡張機能][VisualstudioMarketplaceWebhint]を追加して、HTML、CSS、JavaScript、TypeScript などの問題を特定して修正します。</span><span class="sxs-lookup"><span data-stu-id="25907-111">Identify and fix problems in your HTML, CSS, JavaScript, TypeScript, and more by adding the [webhint extension for VS Code][VisualstudioMarketplaceWebhint].</span></span>  <span data-ttu-id="25907-112">ヒントはインライン下線として表示され、[**問題**] ウィンドウに集計されます。</span><span class="sxs-lookup"><span data-stu-id="25907-112">Hints appear as inline underlines and are summarized in the **Problems** pane.</span></span>  

## <span data-ttu-id="25907-113">構成</span><span class="sxs-lookup"><span data-stu-id="25907-113">Configuration</span></span>  

<span data-ttu-id="25907-114">この拡張機能では、HTML、CSS、テンプレートシステム \ (JSX/TSX、角速度など)、JavaScript/TypeScript などのヒントとパーサーをアクティブ化する[既定の構成][GithubWebhintioIndexjson]json ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="25907-114">This extension uses a [default configuration][GithubWebhintioIndexjson] json file that activates hints and parsers for HTML, CSS, templating systems \(JSX/TSX, Angular, and so on\), JavaScript/TypeScript, and more.</span></span>  

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

<span data-ttu-id="25907-115">アクティブ化されるヒントとパーサーをさらに制御する必要がある場合は、 `.hintrc` web ヒントを構成するためのローカルファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="25907-115">If you want more control over the hints and parsers that get activated, create a local `.hintrc` file to configure webhint.</span></span>  <span data-ttu-id="25907-116">特定のヒントからの出力に関するヘルプについては、「 [webhint ユーザーガイド][WebhintDocsUserguideConfiguringSummary]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25907-116">For help with output from specific hints, see [webhint user guide][WebhintDocsUserguideConfiguringSummary].</span></span>  

## <span data-ttu-id="25907-117">Webhint チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="25907-117">Getting in touch with the webhint team</span></span>  

<span data-ttu-id="25907-118">[Webhint github リポジトリ][GithubWebhintio]の[問題を提出][GithubWebhintioIssuesNew]して、フィードバックを送信します。</span><span class="sxs-lookup"><span data-stu-id="25907-118">Send your feedback by [filing an issue][GithubWebhintioIssuesNew] in [webhint GitHub repo][GithubWebhintio].</span></span>  

<span data-ttu-id="25907-119">拡張機能に参加するには、「 [webhint とコード拡張の投稿ガイド][GithubWebhintioExtensionVscodeContributing]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25907-119">To contribute to the extension, see [webhint VS Code extension contribution guide][GithubWebhintioExtensionVscodeContributing].</span></span>  

## <span data-ttu-id="25907-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="25907-120">See also</span></span>  

*   [<span data-ttu-id="25907-121">アクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="25907-121">Accessibility</span></span>][AccessibilityIndex]  
*   [<span data-ttu-id="25907-122">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="25907-122">Visual Studio Code</span></span>][VisualstudiocodeIndex]  

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
