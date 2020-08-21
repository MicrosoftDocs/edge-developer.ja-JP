---
description: このページでは、EdgeHTML 13 の新機能の概要を示します。
title: EdgeHTML 13 の新機能と API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、Web 開発、html、cs、javascript、開発者
ms.openlocfilehash: 033b8dacb107492624f3b8c7775a47285c9893dd
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941916"
---
# <span data-ttu-id="41a28-104">Microsoft EdgeHTML 13 の新機能</span><span class="sxs-lookup"><span data-stu-id="41a28-104">What's new in EdgeHTML 13</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="41a28-105">EdgeHTML 13 に出荷される変更は、Microsoft Edge ブラウザーの初回のメジャー更新プログラム[first major update](https://blogs.windows.com/windowsexperience/2015/11/12)(2015/11/2015、ビルド 10586\) でリリースされる変更です。</span><span class="sxs-lookup"><span data-stu-id="41a28-105">Here are the changes shipped with EdgeHTML 13, the engine powering the Microsoft Edge browser in the [first major update](https://blogs.windows.com/windowsexperience/2015/11/12) for Windows 10 \(11/2015, Build 10586\).</span></span>  <span data-ttu-id="41a28-106">Microsoft Edge ブラウザー全体の変更の概要については、Microsoft Edge の初回プラット [フォーム更新プログラムの概要をご覧ください](https://blogs.windows.com/msedgedev/2015/11/16)。</span><span class="sxs-lookup"><span data-stu-id="41a28-106">For an overview of changes to the overall Microsoft Edge browser, see [Introducing EdgeHTML 13, our first platform update for Microsoft Edge](https://blogs.windows.com/msedgedev/2015/11/16).</span></span>  

<span data-ttu-id="41a28-107">次の一覧を行うと、この機能が利用できます  [https://aka.ms/devguide_edgehtml_13](./edgehtml-13.md) 。</span><span class="sxs-lookup"><span data-stu-id="41a28-107">Here's the permalink for the following list of changes:  [https://aka.ms/devguide_edgehtml_13](./edgehtml-13.md).</span></span>  

## <span data-ttu-id="41a28-108">機能</span><span class="sxs-lookup"><span data-stu-id="41a28-108">Features</span></span>  

### <span data-ttu-id="41a28-109">CSS</span><span class="sxs-lookup"><span data-stu-id="41a28-109">CSS</span></span>  

<span data-ttu-id="41a28-110">EdgeHTML 13 では、次のような新しい CSS 機能がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="41a28-110">EdgeHTML 13 supports new CSS features, including:</span></span>  

*   [<span data-ttu-id="41a28-111">CSS ミュート機能 Pseudo クラス</span><span class="sxs-lookup"><span data-stu-id="41a28-111">CSS Mutability Pseudo-classes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/cssmutabilitypseudoclasses)  
*   [<span data-ttu-id="41a28-112">CSS 範囲のプッピド クラス</span><span class="sxs-lookup"><span data-stu-id="41a28-112">CSS Range Pseudo-classes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/cssrangepseudoclasses)  
*   <span data-ttu-id="41a28-113">CSS [のイニシャル](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue) と設定 [を](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue) 解除する</span><span class="sxs-lookup"><span data-stu-id="41a28-113">CSS [initial](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue) and [unset](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue) keywords</span></span>  

### <span data-ttu-id="41a28-114">暗号化されたメディア拡張機能</span><span class="sxs-lookup"><span data-stu-id="41a28-114">Encrypted Media Extensions</span></span>  

<span data-ttu-id="41a28-115">Microsoft Edge では、予期しない暗号化された暗号化メディア拡張 API が [サポートされるようになり](https://w3.org/TR/encrypted-media) ました。</span><span class="sxs-lookup"><span data-stu-id="41a28-115">Microsoft Edge now supports the new unprefixed [Encrypted Media Extensions](https://w3.org/TR/encrypted-media) APIs.</span></span>  <span data-ttu-id="41a28-116">Encrypted Media Extensions \(EME\) は、ビデオ要素およびオーディオ要素を拡張して、プラグインを使用せずに Digital Rights Management \(DRM\) 保護コンテンツを有効にします。 EME: 暗号  [化されたメディア拡張機能の詳細について説明します](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API)。</span><span class="sxs-lookup"><span data-stu-id="41a28-116">Encrypted Media Extensions \(EME\) extends the video and audio elements to enable Digital Rights Management \(DRM\) protected content without using plug-ins.  Read more about EME:  [Encrypted Media Extensions](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API).</span></span>  

### <span data-ttu-id="41a28-117">グラフィックス</span><span class="sxs-lookup"><span data-stu-id="41a28-117">Graphics</span></span>  

<span data-ttu-id="41a28-118">Microsoft EdgeHTML 13 では、次のグラフィック更新プログラムが追加されました。</span><span class="sxs-lookup"><span data-stu-id="41a28-118">EdgeHTML 13 introduces the following graphics updates:</span></span>  

*   [<span data-ttu-id="41a28-119">キャンバスの省略語</span><span class="sxs-lookup"><span data-stu-id="41a28-119">Canvas ellipse</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/canvas2dellipse)  
*   [<span data-ttu-id="41a28-120">キャンバス ブレンド モード</span><span class="sxs-lookup"><span data-stu-id="41a28-120">Canvas blending modes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/compositingandblendingincanvas2d)  
*   [<picture> <span data-ttu-id="41a28-121">要素</span><span class="sxs-lookup"><span data-stu-id="41a28-121">element</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/pictureelement)  
*   [<span data-ttu-id="41a28-122">SVG 外部コンテンツ</span><span class="sxs-lookup"><span data-stu-id="41a28-122">SVG external content</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/svgexternalcontent)  

### <span data-ttu-id="41a28-123">JavaScript</span><span class="sxs-lookup"><span data-stu-id="41a28-123">JavaScript</span></span>  

<span data-ttu-id="41a28-124">Microsoft EdgeHTML 13 には、 [次のような Javakra](https://blogs.windows.com/msedgedev/2015/09/30)での主な機能の主な改善と新機能のサポートが含まれており、次のような Microsoft Edge を利用できます。</span><span class="sxs-lookup"><span data-stu-id="41a28-124">EdgeHTML 13 includes [major improvements and new feature support in Chakra](https://blogs.windows.com/msedgedev/2015/09/30), the JavaScript engine powering Microsoft Edge, including:</span></span>  

#### <span data-ttu-id="41a28-125">新機能</span><span class="sxs-lookup"><span data-stu-id="41a28-125">New features</span></span>  

<span data-ttu-id="41a28-126">既定でオン</span><span class="sxs-lookup"><span data-stu-id="41a28-126">On by default</span></span>  

*   <span data-ttu-id="41a28-127">[asm.js](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js) 既定で有効にされた \([ブログ投稿](https://blogs.windows.com/msedgedev/2015/11/10), [デモ](https://dev.windows.com/microsoft-edge/testdrive/demos/chess)\)</span><span class="sxs-lookup"><span data-stu-id="41a28-127">[asm.js](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js) enabled by default \([blog post](https://blogs.windows.com/msedgedev/2015/11/10), [demo](https://dev.windows.com/microsoft-edge/testdrive/demos/chess)\)</span></span>  
*   <span data-ttu-id="41a28-128">[Classes](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes) \(ES2015\)</span><span class="sxs-lookup"><span data-stu-id="41a28-128">[Classes](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes) \(ES2015\)</span></span>  

#### <span data-ttu-id="41a28-129">実用 JavaScript 機能</span><span class="sxs-lookup"><span data-stu-id="41a28-129">Experimental JavaScript features</span></span>  

<span data-ttu-id="41a28-130">有効</span><span class="sxs-lookup"><span data-stu-id="41a28-130">Enabled with</span></span> `about:flags`  

*   <span data-ttu-id="41a28-131">[Async 関数](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions) \(ES2016\)</span><span class="sxs-lookup"><span data-stu-id="41a28-131">[Async functions](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions) \(ES2016\)</span></span>  
*   <span data-ttu-id="41a28-132">[Exponentiation operator](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator) \(ES2016\)</span><span class="sxs-lookup"><span data-stu-id="41a28-132">[Exponentiation operator](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator) \(ES2016\)</span></span>  
*   <span data-ttu-id="41a28-133">[Destructuring](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) \(ES2015\)</span><span class="sxs-lookup"><span data-stu-id="41a28-133">[Destructuring](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) \(ES2015\)</span></span>  

### <span data-ttu-id="41a28-134">ユーザー入力</span><span class="sxs-lookup"><span data-stu-id="41a28-134">User Input</span></span>  

<span data-ttu-id="41a28-135">EdgeHTML 13 で追加された次の機能では、ユーザー入力が改善されます。</span><span class="sxs-lookup"><span data-stu-id="41a28-135">The following features introduced in EdgeHTML 13 improve user input:</span></span>  

*   [<meter> <span data-ttu-id="41a28-136">要素</span><span class="sxs-lookup"><span data-stu-id="41a28-136">element</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/meterelement)  
*   [<span data-ttu-id="41a28-137">要素のドキュメントとウィンドウのオンのイベント ハンドラー</span><span class="sxs-lookup"><span data-stu-id="41a28-137">oninvalid event handler for the element document and window</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/oninvalideventhandler)  

### <span data-ttu-id="41a28-138">ポインターのロック</span><span class="sxs-lookup"><span data-stu-id="41a28-138">Pointer Lock</span></span>  

<span data-ttu-id="41a28-139">Microsoft Edge では、放射時のマウスの移動にアクセスできるようにポインター Lock API \(以前はマウス ロック\) がサポートされ、マウス イベントのターゲットを 1 つの要素にロックし、マウスの移動が 1 つの方向でどのように行き入れるかの制限をなくしたり、ビューからカーソルを削除したりできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="41a28-139">Microsoft Edge now supports the Pointer Lock API \(previously called Mouse Lock\) for access to raw mouse movement, locking the target of mouse events to a single element, eliminating limits of how far mouse movement can go in a single direction, and removing the cursor from view.</span></span>  

## <span data-ttu-id="41a28-140">EdgeHTML 13 の新しい API</span><span class="sxs-lookup"><span data-stu-id="41a28-140">New APIs in EdgeHTML 13</span></span>  

<span data-ttu-id="41a28-141">EdgeHTML 13 の新しい API の完全な一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="41a28-141">Here's the full list of new APIs in EdgeHTML 13.</span></span>  <span data-ttu-id="41a28-142">これらは形式で表示されます `[interface name].[api name]` 。</span><span class="sxs-lookup"><span data-stu-id="41a28-142">They are listed in the format of `[interface name].[api name]`.</span></span>  

<iframe height='584' scrolling='no' title='<span data-ttu-id="41a28-143">EdgeHTML 13 の新しい API</span><span class="sxs-lookup"><span data-stu-id="41a28-143">New APIs in EdgeHTML 13</span></span>' src='//codepen.io/MicrosoftEdgeDocumentation/embed/vmzxEY/?height=584&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width:  100%;'><span data-ttu-id="41a28-144"><a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'> </a> CodePen の Microsoft Edge Docs (新しい <a href='http://codepen.io/MicrosoftEdgeDocumentation'> API) @MicrosoftEdgeDocumentation </a> 参照 <a href='http://codepen.io'> してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="41a28-144">See the Pen <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'>New APIs in EdgeHTML 13</a> by Microsoft Edge Docs (<a href='http://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='http://codepen.io'>CodePen</a>.</span></span></iframe>  
