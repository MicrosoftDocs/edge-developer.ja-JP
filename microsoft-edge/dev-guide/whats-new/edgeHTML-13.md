---
description: このページでは、EdgeHTML 13 の新機能の概要を説明します。
title: EdgeHTML 13 の新機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: 8fb9d6bd78af5d595e217fa2bf210632f4c1a61f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568816"
---
# <span data-ttu-id="51498-104">EdgeHTML 13 の新機能</span><span class="sxs-lookup"><span data-stu-id="51498-104">What's New in EdgeHTML 13</span></span>
<span data-ttu-id="51498-105">この変更は、EdgeHTML 13 に同梱されています。エンジンは、Windows 10 の[最初のメジャー更新プログラム](https://blogs.windows.com/windowsexperience/2015/11/12/first-major-update-for-windows-10-available-today/)(11/2015、ビルド 10586) で Microsoft Edge ブラウザーを電源投入します。</span><span class="sxs-lookup"><span data-stu-id="51498-105">Here are the changes shipped with EdgeHTML 13, the engine powering the Microsoft Edge browser in the [first major update](https://blogs.windows.com/windowsexperience/2015/11/12/first-major-update-for-windows-10-available-today/) for Windows 10 (11/2015, Build 10586).</span></span> <span data-ttu-id="51498-106">Microsoft Edge ブラウザー全体の変更の概要については、「 [Microsoft edge の最初のプラットフォーム更新プログラム EdgeHTML 13」を](https://blogs.windows.com/msedgedev/2015/11/16/introducing-edgehtml-13-our-first-platform-update-for-microsoft-edge/)参照してください。</span><span class="sxs-lookup"><span data-stu-id="51498-106">For an overview of changes to the overall Microsoft Edge browser, see [Introducing EdgeHTML 13, our first platform update for Microsoft Edge](https://blogs.windows.com/msedgedev/2015/11/16/introducing-edgehtml-13-our-first-platform-update-for-microsoft-edge/).</span></span>

<span data-ttu-id="51498-107">次の変更の固定リンクを示し [https://aka.ms/devguide_edgehtml_13](https://aka.ms/devguide_edgehtml_13) ます。</span><span class="sxs-lookup"><span data-stu-id="51498-107">Here's the permalink for the following list of changes: [https://aka.ms/devguide_edgehtml_13](https://aka.ms/devguide_edgehtml_13).</span></span>

## <span data-ttu-id="51498-108">機能</span><span class="sxs-lookup"><span data-stu-id="51498-108">Features</span></span>

### <span data-ttu-id="51498-109">CSS</span><span class="sxs-lookup"><span data-stu-id="51498-109">CSS</span></span>
<span data-ttu-id="51498-110">' ' EdgeHTML 13 では、次のような新しい CSS 機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="51498-110">'' EdgeHTML 13 supports new CSS features, including:</span></span>
* [<span data-ttu-id="51498-111">CSS の可能性のある擬似クラス</span><span class="sxs-lookup"><span data-stu-id="51498-111">CSS Mutability Pseudo-classes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/cssmutabilitypseudoclasses/)
* [<span data-ttu-id="51498-112">CSS 範囲擬似クラス</span><span class="sxs-lookup"><span data-stu-id="51498-112">CSS Range Pseudo-classes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/cssrangepseudoclasses/)
* <span data-ttu-id="51498-113">CSS の[イニシャル](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue/)と[未](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue/)設定のキーワード</span><span class="sxs-lookup"><span data-stu-id="51498-113">CSS [initial](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue/) and [unset](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue/) keywords</span></span>

### <span data-ttu-id="51498-114">暗号化されたメディアの拡張子</span><span class="sxs-lookup"><span data-stu-id="51498-114">Encrypted Media Extensions</span></span>
<span data-ttu-id="51498-115">Microsoft Edge で、新しいプレフィックスのない[暗号化メディア拡張](https://w3.org/TR/encrypted-media/)api がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="51498-115">Microsoft Edge now supports the new unprefixed [Encrypted Media Extensions](https://w3.org/TR/encrypted-media/) APIs.</span></span> <span data-ttu-id="51498-116">暗号化されたメディア拡張機能 (EME) は、プラグインを使わずに、デジタル著作権管理 (DRM) で保護されたコンテンツを有効にするために、ビデオ要素とオーディオ要素を拡張します。 EME: [Encrypted Media Extensions](https://docs.microsoft.com/microsoft-edge/dev-guide/multimedia/encrypted-media-extensions)の詳細</span><span class="sxs-lookup"><span data-stu-id="51498-116">Encrypted Media Extensions (EME) extends the video and audio elements to enable Digital Rights Management (DRM) protected content without using plug-ins. Read more about EME: [Encrypted Media Extensions](https://docs.microsoft.com/microsoft-edge/dev-guide/multimedia/encrypted-media-extensions).</span></span>

### <span data-ttu-id="51498-117">グラフィックス</span><span class="sxs-lookup"><span data-stu-id="51498-117">Graphics</span></span>

<span data-ttu-id="51498-118">EdgeHTML 13 では、次のグラフィックスの更新が導入されています。</span><span class="sxs-lookup"><span data-stu-id="51498-118">EdgeHTML 13 introduces the following graphics updates:</span></span>
* [<span data-ttu-id="51498-119">キャンバス楕円</span><span class="sxs-lookup"><span data-stu-id="51498-119">Canvas ellipse</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/canvas2dellipse/)
* [<span data-ttu-id="51498-120">キャンバスブレンドモード</span><span class="sxs-lookup"><span data-stu-id="51498-120">Canvas blending modes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/compositingandblendingincanvas2d/)
* [`<picture>` <span data-ttu-id="51498-121">要素</span><span class="sxs-lookup"><span data-stu-id="51498-121">element</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/pictureelement/)
* [<span data-ttu-id="51498-122">SVG 外部コンテンツ</span><span class="sxs-lookup"><span data-stu-id="51498-122">SVG external content</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/svgexternalcontent/)

### <span data-ttu-id="51498-123">JavaScript</span><span class="sxs-lookup"><span data-stu-id="51498-123">JavaScript</span></span>
<span data-ttu-id="51498-124">EdgeHTML 13 には、次のような Microsoft Edge を搭載した、JavaScript エンジンの[Chakra での主な改善と新機能のサポート](https://blogs.windows.com/msedgedev/2015/09/30/asynchronous-code-gets-easier-with-es2016-async-function-support-in-chakra-and-microsoft-edge/)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="51498-124">EdgeHTML 13 includes [major improvements and new feature support in Chakra](https://blogs.windows.com/msedgedev/2015/09/30/asynchronous-code-gets-easier-with-es2016-async-function-support-in-chakra-and-microsoft-edge/), the JavaScript engine powering Microsoft Edge, including:</span></span>

#### <span data-ttu-id="51498-125">新機能 (既定でオン)</span><span class="sxs-lookup"><span data-stu-id="51498-125">New features (on by default)</span></span>

* <span data-ttu-id="51498-126">既定で有効になっている[.asm .js](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js) ([ブログの投稿](https://blogs.windows.com/msedgedev/2015/11/10/supercharging-javascript-performance-with-asm-js/)、[デモ](https://dev.windows.com/microsoft-edge/testdrive/demos/chess/))</span><span class="sxs-lookup"><span data-stu-id="51498-126">[asm.js](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js) enabled by default ([blog post](https://blogs.windows.com/msedgedev/2015/11/10/supercharging-javascript-performance-with-asm-js/), [demo](https://dev.windows.com/microsoft-edge/testdrive/demos/chess/))</span></span>
* <span data-ttu-id="51498-127">[クラス](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes)(ES2015)</span><span class="sxs-lookup"><span data-stu-id="51498-127">[Classes](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes) (ES2015)</span></span>

#### <span data-ttu-id="51498-128">実験的な JavaScript 機能 ( *about: flags*で有効)</span><span class="sxs-lookup"><span data-stu-id="51498-128">Experimental JavaScript features (enabled with *about:flags*)</span></span>

* <span data-ttu-id="51498-129">[Async 関数](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions)(ES2016)</span><span class="sxs-lookup"><span data-stu-id="51498-129">[Async functions](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions) (ES2016)</span></span>
* <span data-ttu-id="51498-130">[指数演算子](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator)(ES2016)</span><span class="sxs-lookup"><span data-stu-id="51498-130">[Exponentiation operator](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator) (ES2016)</span></span>
* <span data-ttu-id="51498-131">[Destructuring](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) (ES2015)</span><span class="sxs-lookup"><span data-stu-id="51498-131">[Destructuring](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) (ES2015)</span></span>

### <span data-ttu-id="51498-132">ユーザー入力</span><span class="sxs-lookup"><span data-stu-id="51498-132">User Input</span></span>
<span data-ttu-id="51498-133">EdgeHTML 13 で導入された次の機能により、ユーザー入力が向上します。</span><span class="sxs-lookup"><span data-stu-id="51498-133">The following features introduced in EdgeHTML 13 improve user input:</span></span>
* [`<meter>` <span data-ttu-id="51498-134">要素</span><span class="sxs-lookup"><span data-stu-id="51498-134">element</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/meterelement/)
* [`oninvalid` <span data-ttu-id="51498-135">要素のドキュメントとウィンドウのイベントハンドラー</span><span class="sxs-lookup"><span data-stu-id="51498-135">event handler for the element document and window</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/oninvalideventhandler/)

### <span data-ttu-id="51498-136">ポインターのロック</span><span class="sxs-lookup"><span data-stu-id="51498-136">Pointer Lock</span></span>
<span data-ttu-id="51498-137">Microsoft Edge では、ポインターロック API (以前のマウスロック) がサポートされるようになりました。マウスの動作のターゲットを単一の要素にロックし、マウスの動きを1方向に移動し、カーソルをビューから削除します。</span><span class="sxs-lookup"><span data-stu-id="51498-137">Microsoft Edge now supports the Pointer Lock API (previously called Mouse Lock) for access to raw mouse movement, locking the target of mouse events to a single element, eliminating limits of how far mouse movement can go in a single direction, and removing the cursor from view.</span></span> 


## <span data-ttu-id="51498-138">EdgeHTML 13 "" "の新しい Api</span><span class="sxs-lookup"><span data-stu-id="51498-138">New APIs in EdgeHTML 13""""</span></span>

<span data-ttu-id="51498-139">EdgeHTML 13 の新しい Api の全一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="51498-139">Here's the full list of new APIs in EdgeHTML 13.</span></span> <span data-ttu-id="51498-140">[Interface name] の形式で一覧表示され**ます。 [api 名]**。</span><span class="sxs-lookup"><span data-stu-id="51498-140">They are listed in the format of **[interface name].[api name]**.</span></span>
<iframe height='584' scrolling='no' title='<span data-ttu-id="51498-141">EdgeHTML 13 の新しい Api</span><span class="sxs-lookup"><span data-stu-id="51498-141">New APIs in EdgeHTML 13</span></span>' src='//codepen.io/MicrosoftEdgeDocumentation/embed/vmzxEY/?height=584&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="51498-142"><a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'> </a> CodePen の Microsoft Edge ドキュメント (@MicrosoftEdgeDocumentation) で EdgeHTML 13 の Pen 新しい api を参照してください <a href='http://codepen.io/MicrosoftEdgeDocumentation'> </a> <a href='http://codepen.io'> </a> 。</span><span class="sxs-lookup"><span data-stu-id="51498-142">See the Pen <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'>New APIs in EdgeHTML 13</a> by Microsoft Edge Docs (<a href='http://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='http://codepen.io'>CodePen</a>.</span></span></iframe><span data-ttu-id="51498-143">""''""''""</span><span class="sxs-lookup"><span data-stu-id="51498-143">""''""''""</span></span>
