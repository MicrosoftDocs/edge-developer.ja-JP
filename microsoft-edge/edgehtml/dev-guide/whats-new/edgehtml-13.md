---
description: このページでは、EdgeHTML 13 の新機能の概要について説明します。
title: EdgeHTML 13 の新機能と API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2119e576a637d5f78e073f49a3cb1868a7ce1ca4
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235008"
---
# <span data-ttu-id="9e9e1-104">EdgeHTML 13 の新機能</span><span class="sxs-lookup"><span data-stu-id="9e9e1-104">What's new in EdgeHTML 13</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="9e9e1-105">ここでは、EdgeHTML 13 に同梱されている変更点を示します。このエンジンは、Windows [](https://blogs.windows.com/windowsexperience/2015/11/12) 10 用の最初のメジャー更新プログラム (11/2015、ビルド 10586\) で Microsoft Edge ブラウザーを起動します。</span><span class="sxs-lookup"><span data-stu-id="9e9e1-105">Here are the changes shipped with EdgeHTML 13, the engine powering the Microsoft Edge browser in the [first major update](https://blogs.windows.com/windowsexperience/2015/11/12) for Windows 10 \(11/2015, Build 10586\).</span></span>  <span data-ttu-id="9e9e1-106">Microsoft Edge ブラウザー全体の変更点の概要については、「Microsoft Edge の最初のプラットフォーム更新プログラム [である EdgeHTML 13](https://blogs.windows.com/msedgedev/2015/11/16)の導入」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e9e1-106">For an overview of changes to the overall Microsoft Edge browser, see [Introducing EdgeHTML 13, our first platform update for Microsoft Edge](https://blogs.windows.com/msedgedev/2015/11/16).</span></span>  

<span data-ttu-id="9e9e1-107">次の変更の一覧の permalink を次に示します  [https://aka.ms/devguide_edgehtml_13](./edgehtml-13.md) 。</span><span class="sxs-lookup"><span data-stu-id="9e9e1-107">Here's the permalink for the following list of changes:  [https://aka.ms/devguide_edgehtml_13](./edgehtml-13.md).</span></span>  

## <span data-ttu-id="9e9e1-108">機能</span><span class="sxs-lookup"><span data-stu-id="9e9e1-108">Features</span></span>  

### <span data-ttu-id="9e9e1-109">CSS</span><span class="sxs-lookup"><span data-stu-id="9e9e1-109">CSS</span></span>  

<span data-ttu-id="9e9e1-110">EdgeHTML 13 は、次の新しい CSS 機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9e9e1-110">EdgeHTML 13 supports new CSS features, including:</span></span>  

*   [<span data-ttu-id="9e9e1-111">CSS の変更可能性擬似クラス</span><span class="sxs-lookup"><span data-stu-id="9e9e1-111">CSS Mutability Pseudo-classes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/cssmutabilitypseudoclasses)  
*   [<span data-ttu-id="9e9e1-112">CSS 範囲擬似クラス</span><span class="sxs-lookup"><span data-stu-id="9e9e1-112">CSS Range Pseudo-classes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/cssrangepseudoclasses)  
*   <span data-ttu-id="9e9e1-113">CSS[の初期](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue)[キーワードと未設定](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue)キーワード</span><span class="sxs-lookup"><span data-stu-id="9e9e1-113">CSS [initial](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue) and [unset](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue) keywords</span></span>  

### <span data-ttu-id="9e9e1-114">暗号化されたメディア拡張機能</span><span class="sxs-lookup"><span data-stu-id="9e9e1-114">Encrypted Media Extensions</span></span>  

<span data-ttu-id="9e9e1-115">Microsoft Edge では、新しい固定されていない [暗号化メディア拡張機能](https://w3.org/TR/encrypted-media) API がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9e9e1-115">Microsoft Edge now supports the new unprefixed [Encrypted Media Extensions](https://w3.org/TR/encrypted-media) APIs.</span></span>  <span data-ttu-id="9e9e1-116">Encrypted Media Extensions \(EME\) は、プラグインを使用せずにデジタル著作権管理 \(DRM\) で保護されたコンテンツを有効にするようにビデオ要素とオーディオ要素を拡張します。 EME:  [Encrypted Media Extensions について詳しくは、以下を参照してください](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API)。</span><span class="sxs-lookup"><span data-stu-id="9e9e1-116">Encrypted Media Extensions \(EME\) extends the video and audio elements to enable Digital Rights Management \(DRM\) protected content without using plug-ins.  Read more about EME:  [Encrypted Media Extensions](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API).</span></span>  

### <span data-ttu-id="9e9e1-117">グラフィックス</span><span class="sxs-lookup"><span data-stu-id="9e9e1-117">Graphics</span></span>  

<span data-ttu-id="9e9e1-118">EdgeHTML 13 では、次のグラフィックス更新プログラムが導入されています。</span><span class="sxs-lookup"><span data-stu-id="9e9e1-118">EdgeHTML 13 introduces the following graphics updates:</span></span>  

*   [<span data-ttu-id="9e9e1-119">キャンバスの楕円</span><span class="sxs-lookup"><span data-stu-id="9e9e1-119">Canvas ellipse</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/canvas2dellipse)  
*   [<span data-ttu-id="9e9e1-120">キャンバス ブレンド モード</span><span class="sxs-lookup"><span data-stu-id="9e9e1-120">Canvas blending modes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/compositingandblendingincanvas2d)  
*   [<picture> <span data-ttu-id="9e9e1-121">要素</span><span class="sxs-lookup"><span data-stu-id="9e9e1-121">element</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/pictureelement)  
*   [<span data-ttu-id="9e9e1-122">SVG 外部コンテンツ</span><span class="sxs-lookup"><span data-stu-id="9e9e1-122">SVG external content</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/svgexternalcontent)  

### <span data-ttu-id="9e9e1-123">JavaScript</span><span class="sxs-lookup"><span data-stu-id="9e9e1-123">JavaScript</span></span>  

<span data-ttu-id="9e9e1-124">EdgeHTML 13 には、Microsoft Edge を強化する JavaScript エンジン [である Chakra](https://blogs.windows.com/msedgedev/2015/09/30)の主な機能強化と新機能のサポートが含まれています。これには次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9e9e1-124">EdgeHTML 13 includes [major improvements and new feature support in Chakra](https://blogs.windows.com/msedgedev/2015/09/30), the JavaScript engine powering Microsoft Edge, including:</span></span>  

#### <span data-ttu-id="9e9e1-125">新機能</span><span class="sxs-lookup"><span data-stu-id="9e9e1-125">New features</span></span>  

<span data-ttu-id="9e9e1-126">既定でオン</span><span class="sxs-lookup"><span data-stu-id="9e9e1-126">On by default</span></span>  

*   <span data-ttu-id="9e9e1-127">[asm.js](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js) 既定で有効になっている \([ブログ投稿](https://blogs.windows.com/msedgedev/2015/11/10), [demo](https://dev.windows.com/microsoft-edge/testdrive/demos/chess)\)</span><span class="sxs-lookup"><span data-stu-id="9e9e1-127">[asm.js](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js) enabled by default \([blog post](https://blogs.windows.com/msedgedev/2015/11/10), [demo](https://dev.windows.com/microsoft-edge/testdrive/demos/chess)\)</span></span>  
*   <span data-ttu-id="9e9e1-128">[Classes](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes) \(ES2015\)</span><span class="sxs-lookup"><span data-stu-id="9e9e1-128">[Classes](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes) \(ES2015\)</span></span>  

#### <span data-ttu-id="9e9e1-129">試験的な JavaScript 機能</span><span class="sxs-lookup"><span data-stu-id="9e9e1-129">Experimental JavaScript features</span></span>  

<span data-ttu-id="9e9e1-130">有効</span><span class="sxs-lookup"><span data-stu-id="9e9e1-130">Enabled with</span></span> `about:flags`  

*   <span data-ttu-id="9e9e1-131">[非同期関数](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions) \(ES2016\)</span><span class="sxs-lookup"><span data-stu-id="9e9e1-131">[Async functions](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions) \(ES2016\)</span></span>  
*   <span data-ttu-id="9e9e1-132">[指数演算子](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator) \(ES2016\)</span><span class="sxs-lookup"><span data-stu-id="9e9e1-132">[Exponentiation operator](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator) \(ES2016\)</span></span>  
*   <span data-ttu-id="9e9e1-133">[デストラクター](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) \(ES2015\)</span><span class="sxs-lookup"><span data-stu-id="9e9e1-133">[Destructuring](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) \(ES2015\)</span></span>  

### <span data-ttu-id="9e9e1-134">ユーザー入力</span><span class="sxs-lookup"><span data-stu-id="9e9e1-134">User Input</span></span>  

<span data-ttu-id="9e9e1-135">EdgeHTML 13 で導入された次の機能により、ユーザー入力が向上します。</span><span class="sxs-lookup"><span data-stu-id="9e9e1-135">The following features introduced in EdgeHTML 13 improve user input:</span></span>  

*   [\<meter\> <span data-ttu-id="9e9e1-136">要素</span><span class="sxs-lookup"><span data-stu-id="9e9e1-136">element</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/meterelement)  
*   [<span data-ttu-id="9e9e1-137">要素ドキュメントとウィンドウの oninvalid イベント ハンドラー</span><span class="sxs-lookup"><span data-stu-id="9e9e1-137">oninvalid event handler for the element document and window</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/oninvalideventhandler)  

### <span data-ttu-id="9e9e1-138">ポインター ロック</span><span class="sxs-lookup"><span data-stu-id="9e9e1-138">Pointer Lock</span></span>  

<span data-ttu-id="9e9e1-139">Microsoft Edge では、マウスの生の移動にアクセスするためのポインター ロック API \(以前のマウス ロック\ と呼ばれていました) がサポートされ、マウス イベントのターゲットを 1 つの要素にロックし、マウスの移動が 1 方向に移動する範囲の制限を排除し、カーソルをビューから削除します。</span><span class="sxs-lookup"><span data-stu-id="9e9e1-139">Microsoft Edge now supports the Pointer Lock API \(previously called Mouse Lock\) for access to raw mouse movement, locking the target of mouse events to a single element, eliminating limits of how far mouse movement can go in a single direction, and removing the cursor from view.</span></span>  

## <span data-ttu-id="9e9e1-140">EdgeHTML 13 の新しい API</span><span class="sxs-lookup"><span data-stu-id="9e9e1-140">New APIs in EdgeHTML 13</span></span>  

<span data-ttu-id="9e9e1-141">EdgeHTML 13 の新しい API の完全な一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9e9e1-141">Here's the full list of new APIs in EdgeHTML 13.</span></span>  <span data-ttu-id="9e9e1-142">これらは次の形式で一覧表示されます `[interface name].[api name]` 。</span><span class="sxs-lookup"><span data-stu-id="9e9e1-142">They are listed in the format of `[interface name].[api name]`.</span></span>  

<iframe height='584' scrolling='no' title='<span data-ttu-id="9e9e1-143">EdgeHTML 13 の新しい API</span><span class="sxs-lookup"><span data-stu-id="9e9e1-143">New APIs in EdgeHTML 13</span></span>' src='//codepen.io/MicrosoftEdgeDocumentation/embed/vmzxEY/?height=584&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width:  100%;'><span data-ttu-id="9e9e1-144">CodePen の Microsoft Edge Docs ( @MicrosoftEdgeDocumentation ) による <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'> EdgeHTML 13 </a> のペンの新しい API <a href='http://codepen.io/MicrosoftEdgeDocumentation'> </a> <a href='http://codepen.io'> をご覧ください </a> 。</span><span class="sxs-lookup"><span data-stu-id="9e9e1-144">See the Pen <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'>New APIs in EdgeHTML 13</a> by Microsoft Edge Docs (<a href='http://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='http://codepen.io'>CodePen</a>.</span></span></iframe>  
