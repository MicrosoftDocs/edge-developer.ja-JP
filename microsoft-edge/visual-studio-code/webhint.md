---
description: Visual Studio コードでの webhint の使い方
title: webhint VS コード拡張
author: hxlnt
ms.author: raweil
ms.date: 03/26/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、vs コード、visual studio コード、web ヒント
ms.openlocfilehash: d3102bf4d8d4a8bba9225d8d3f68432197f775ac
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570723"
---
# <span data-ttu-id="b07df-104">webhint VS コード拡張</span><span class="sxs-lookup"><span data-stu-id="b07df-104">webhint VS Code extension</span></span>

<span data-ttu-id="b07df-105">カスタマイズ可能なカスタマイズされたカスタマイズされた機能[を使って](https://webhint.io)、アクセシビリティ、パフォーマンス、クロスブラウザーの互換性、PWA の互換性、およびサイトのセキュリティを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="b07df-105">Use [webhint](https://webhint.io), a customizable linting tool, to improve the accessibility, performance, cross-browser compatibility, PWA compatibility, and security of your site.</span></span> <span data-ttu-id="b07df-106">ベストプラクティスと一般的なエラーについてコードを確認します。</span><span class="sxs-lookup"><span data-stu-id="b07df-106">It checks your code for best practices and common errors.</span></span> <span data-ttu-id="b07df-107">このオープンソースプロジェクトは、最初に Microsoft Edge チームによって開発されたものであり、 [Openjs Foundation](https://openjsf.org/)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="b07df-107">This open-source project, initially developed by the Microsoft Edge team, is now part of the [OpenJS Foundation](https://openjsf.org/).</span></span> <span data-ttu-id="b07df-108">Microsoft Edge チームは、コミュニティの web 開発者と共に web ヒントに投稿し続けています。</span><span class="sxs-lookup"><span data-stu-id="b07df-108">The Microsoft Edge team continues to contribute to webhint alongside web developers in the community.</span></span>

![Web ヒントとコード拡張のスクリーンショット](./media/webhint-extension.png)

<span data-ttu-id="b07df-110">[VS コードの webhint 拡張機能](https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint)を追加して、HTML、CSS、JavaScript、TypeScript などの問題を特定して修正します。</span><span class="sxs-lookup"><span data-stu-id="b07df-110">Identify and fix problems in your HTML, CSS, JavaScript, TypeScript, and more by adding the [webhint extension for VS Code](https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint).</span></span> <span data-ttu-id="b07df-111">ヒントはインライン下線として表示され、[問題] ウィンドウに集計されます。</span><span class="sxs-lookup"><span data-stu-id="b07df-111">Hints appear as inline underlines and are summarized in the Problems pane.</span></span>

## <span data-ttu-id="b07df-112">構成</span><span class="sxs-lookup"><span data-stu-id="b07df-112">Configuration</span></span>

<span data-ttu-id="b07df-113">この拡張機能では、HTML、CSS、テンプレートシステム (JSX/TSX、角速度など)、JavaScript/TypeScript などのヒントとパーサーをアクティブ化する[既定の構成](https://github.com/webhintio/hint/blob/master/packages/configuration-development/index.json)json ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b07df-113">This extension uses a [default configuration](https://github.com/webhintio/hint/blob/master/packages/configuration-development/index.json) json file that activates hints and parsers for HTML, CSS, templating systems (JSX/TSX, Angular, and so on), JavaScript/TypeScript, and more.</span></span>

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

<span data-ttu-id="b07df-114">アクティブ化されるヒントとパーサーをさらに制御する必要がある場合は、 `.hintrc` web ヒントを構成するためのローカルファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b07df-114">If you want more control over the hints and parsers that get activated, create a local `.hintrc` file to configure webhint.</span></span> <span data-ttu-id="b07df-115">特定のヒントからの出力に関するヘルプについては、「 [webhint ユーザーガイド](https://webhint.io/docs/user-guide/configuring-webhint/summary/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b07df-115">For help with output from specific hints, see the [webhint user guide](https://webhint.io/docs/user-guide/configuring-webhint/summary/).</span></span>

## <span data-ttu-id="b07df-116">フィードバック</span><span class="sxs-lookup"><span data-stu-id="b07df-116">Feedback</span></span>

<span data-ttu-id="b07df-117">[Web ヒント GitHub リポジトリ](https://github.com/webhintio/hint)に[問題を提出](https://github.com/webhintio/hint/issues/new)して、フィードバックを送信してください。</span><span class="sxs-lookup"><span data-stu-id="b07df-117">Send us your feedback by [filing an issue](https://github.com/webhintio/hint/issues/new) on the [webhint GitHub repo](https://github.com/webhintio/hint).</span></span> 

<span data-ttu-id="b07df-118">拡張機能に参加するには、 [webhint とコード拡張の投稿ガイド](https://github.com/webhintio/hint/blob/master/packages/extension-vscode/CONTRIBUTING.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b07df-118">To contribute to the extension, please read the [webhint VS Code extension contribution guide](https://github.com/webhintio/hint/blob/master/packages/extension-vscode/CONTRIBUTING.md).</span></span>

## <span data-ttu-id="b07df-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="b07df-119">See also</span></span>
  - [<span data-ttu-id="b07df-120">アクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="b07df-120">Accessibility</span></span>](/microsoft-edge/accessibility)
  - [<span data-ttu-id="b07df-121">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b07df-121">Visual Studio Code</span></span>](/microsoft-edge/visual-studio-code/)
