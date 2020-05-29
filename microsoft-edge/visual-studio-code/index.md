---
description: Microsoft Edge (Chromium) と Visual Studio コード
title: Visual Studio Code
author: zoherghadyali
ms.author: zoghadya
ms.date: 03/12/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、vs コード、visual studio コード、デバッガー、webhint
ms.openlocfilehash: 94148864edbd43adbe2dc9f3d0c2fa0c1f7f0b43
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570740"
---
# <span data-ttu-id="6f811-104">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6f811-104">Visual Studio Code</span></span>

<span data-ttu-id="6f811-105">[Visual Studio コード](https://code.visualstudio.com/Docs)は、デスクトップで実行される強力なソースコードエディターであり、Windows、MacOS、Linux で利用できます。</span><span class="sxs-lookup"><span data-stu-id="6f811-105">[Visual Studio Code](https://code.visualstudio.com/Docs) is a lightweight but powerful source code editor which runs on your desktop and is available for Windows, macOS and Linux.</span></span> <span data-ttu-id="6f811-106">JavaScript、TypeScript、および node.js の組み込みサポートが含まれているので、このボックスから直接、web 開発者に最適なツールです。</span><span class="sxs-lookup"><span data-stu-id="6f811-106">It comes with built-in support for JavaScript, TypeScript and Node.js so it's a great tool for web developers right out of the box!</span></span> <span data-ttu-id="6f811-107">まだ使用していない場合は、[このページ](https://code.visualstudio.com/)にアクセスして Visual Studio のコードをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="6f811-107">Head to [this page](https://code.visualstudio.com/) to download Visual Studio Code if you aren't using it yet.</span></span>

## <span data-ttu-id="6f811-108">拡張機能</span><span class="sxs-lookup"><span data-stu-id="6f811-108">Extensions</span></span>

<!-- We want to put something like the tiles for extensions VS Code uses on this page https://code.visualstudio.com/Docs#top-extensions but I don't think this is a markdown page. I think it's a web page. I couldn't find anything in https://github.com/Microsoft/vscode-docs that looks like this page. In the meantime, here's what I've come up with: -->

<span data-ttu-id="6f811-109">以下で強調表示されている拡張機能を取得するには、 `Ctrl`  +  `Shift`  +  `X` `Command`  +  `Shift`  +  `X` VS コードの [拡張機能] (Windows または Mac の場合) に移動します。</span><span class="sxs-lookup"><span data-stu-id="6f811-109">To acquire any of the extensions highlighted below, navigate to Extensions (`Ctrl` + `Shift` + `X` on Windows or `Command` + `Shift` + `X` on Mac) in VS Code.</span></span>

<span data-ttu-id="6f811-110">市場で特定の拡張子を検索し、[**インストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f811-110">Search the Marketplace for the specific extension and select **Install**.</span></span>

![Microsoft Edge VS コード拡張用のデバッガーのインストール](./media/vscode-debugger-install.png)

## <span data-ttu-id="6f811-112">Microsoft Edge 用デバッガー</span><span class="sxs-lookup"><span data-stu-id="6f811-112">Debugger for Microsoft Edge</span></span>

<span data-ttu-id="6f811-113">`console.log()`Microsoft Edge VS コード拡張機能[のデバッガー](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge)を使って、フロントエンド JavaScript コードを行単位でデバッグし、 [Visual Studio コード](https://code.visualstudio.com/)でステートメントを直接表示します。</span><span class="sxs-lookup"><span data-stu-id="6f811-113">Debug your front-end JavaScript code line by line and display `console.log()` statements directly in [Visual Studio Code](https://code.visualstudio.com/) using the the [Debugger for Microsoft Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) VS Code extension!</span></span>

<span data-ttu-id="6f811-114">Microsoft [edge VS のデバッガー](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge)を使って、microsoft Edge (EdgeHTML) と microsoft Edge (Chromium) の両方を起動またはアタッチします。</span><span class="sxs-lookup"><span data-stu-id="6f811-114">Use the [Debugger for Microsoft Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) VS Code extension to launch or attach to both Microsoft Edge (EdgeHTML) and Microsoft Edge (Chromium).</span></span> <span data-ttu-id="6f811-115">[このページ](./debugger-for-edge.md)では、VS コードからの Microsoft Edge のデバッグ方法と、サンプルの**起動. json**構成のチュートリアルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6f811-115">Check out [this page](./debugger-for-edge.md) for a walkthrough of debugging Microsoft Edge from VS Code and sample **launch.json** configurations.</span></span>

![Edge VS コード拡張のためのデバッガーの GIF](./media/debugger-for-edge.gif)

## <span data-ttu-id="6f811-117">Microsoft Edge の要素</span><span class="sxs-lookup"><span data-stu-id="6f811-117">Elements for Microsoft Edge</span></span>

<span data-ttu-id="6f811-118">Microsoft Edge VS コード拡張[用の要素](https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools)を追加することで、ブラウザーの要素ツールを Visual Studio コード内から使うことができます。</span><span class="sxs-lookup"><span data-stu-id="6f811-118">By adding the [Elements for Microsoft Edge](https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools) VS Code extension, you can use the browser's Elements tool from within Visual Studio Code.</span></span> <span data-ttu-id="6f811-119">起動またはアタッチのどちらの場合も、要素ツールは Microsoft Edge のインスタンスに接続され、ランタイム HTML 構造を表示し、レイアウトを変更したり、スタイル設定の問題を修正したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="6f811-119">By either launching or attaching, the Elements tool will connect to an instance of Microsoft Edge, display the runtime HTML structure, and allow you to alter the layout or fix styling issues.</span></span>

<span data-ttu-id="6f811-120">詳細については、[このページ](./elements-for-edge.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6f811-120">For more information, check out [this page](./elements-for-edge.md).</span></span>

![Edge VS コード拡張の要素の GIF。](./media/elements-for-edge.gif)

## <span data-ttu-id="6f811-122">web ヒント</span><span class="sxs-lookup"><span data-stu-id="6f811-122">webhint</span></span>

<span data-ttu-id="6f811-123">カスタマイズ可能なカスタマイズされたカスタマイズされた機能[を使って](https://webhint.io)、アクセシビリティ、パフォーマンス、クロスブラウザーの互換性、PWA の互換性、およびサイトのセキュリティを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="6f811-123">Use [webhint](https://webhint.io), a customizable linting tool, to improve the accessibility, performance, cross-browser compatibility, PWA compatibility, and security of your site.</span></span> <span data-ttu-id="6f811-124">ベストプラクティスと一般的なエラーについてコードを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f811-124">It checks your code for best practices and common errors.</span></span> <span data-ttu-id="6f811-125">このオープンソースプロジェクトは、最初に Microsoft Edge チームによって開発されたものであり、 [Openjs Foundation](https://openjsf.org/)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="6f811-125">This open-source project, initially developed by the Microsoft Edge team, is now part of the [OpenJS Foundation](https://openjsf.org/).</span></span> <span data-ttu-id="6f811-126">Microsoft Edge チームは、コミュニティの web 開発者と共に web ヒントに投稿し続けています。</span><span class="sxs-lookup"><span data-stu-id="6f811-126">The Microsoft Edge team continues to contribute to webhint alongside web developers in the community.</span></span>

![Web ヒントとコード拡張のスクリーンショット](./media/webhint-extension.png)

<span data-ttu-id="6f811-128">[VS コードの webhint 拡張機能](https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint)を追加して、HTML、CSS、JavaScript、TypeScript などの問題を特定して修正します。</span><span class="sxs-lookup"><span data-stu-id="6f811-128">Identify and fix problems in your HTML, CSS, JavaScript, TypeScript, and more by adding the [webhint extension for VS Code](https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint).</span></span> <span data-ttu-id="6f811-129">ヒントはインライン下線として表示され、[問題] ウィンドウに集計されます。</span><span class="sxs-lookup"><span data-stu-id="6f811-129">Hints appear as inline underlines and are summarized in the Problems pane.</span></span>

<span data-ttu-id="6f811-130">詳細については、「 [Visual Studio コードでの webhint](./webhint.md)の使い方」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f811-130">For more information, see [How to use webhint in Visual Studio Code](./webhint.md).</span></span>
