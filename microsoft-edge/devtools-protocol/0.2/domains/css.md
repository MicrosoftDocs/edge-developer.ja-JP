---
description: CSS ドメインの参照。 このドメインは CSS の読み取り/書き込み操作を公開します。 すべての CSS オブジェクト (スタイルシート、ルール、スタイル) には、 `id` 関連オブジェクトの後続の操作で使用される関連付けがあります。 各オブジェクト型には特定の構造体があり、 `id` さまざまな種類のオブジェクト間で相互に交換することはできません。 CSS オブジェクトは、 `get*ForNode()` 呼び出し (DOM ノード id を受け取る) を使って読み込むことができます。 クライアントは、イベントによってスタイル変更 `styleSheetAdded` / `styleSheetRemoved` を追跡し、そのメソッドを使って必要なスタイルシートの内容を読み込むこともでき `getStyleSheet[Text]()` ます。
title: CSS ドメイン-DevTools プロトコルバージョン0.2
author: pelavall
ms.author: pelavall
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 939eda0ae2f5228657d35899ab75b39493eff917
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569612"
---
# <span data-ttu-id="40fd9-108">CSS</span><span class="sxs-lookup"><span data-stu-id="40fd9-108">CSS</span></span>
<span data-ttu-id="40fd9-109">このドメインは CSS の読み取り/書き込み操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="40fd9-109">This domain exposes CSS read/write operations.</span></span> <span data-ttu-id="40fd9-110">すべての CSS オブジェクト (スタイルシート、ルール、スタイル) には、 `id` 関連オブジェクトの後続の操作で使用される関連付けがあります。</span><span class="sxs-lookup"><span data-stu-id="40fd9-110">All CSS objects (stylesheets, rules, and styles) have an associated `id` used in subsequent operations on the related object.</span></span> <span data-ttu-id="40fd9-111">各オブジェクト型には特定の構造体があり、 `id` さまざまな種類のオブジェクト間で相互に交換することはできません。</span><span class="sxs-lookup"><span data-stu-id="40fd9-111">Each object type has a specific `id` structure, and those are not interchangeable between objects of different kinds.</span></span> <span data-ttu-id="40fd9-112">CSS オブジェクトは、 `get*ForNode()` 呼び出し (DOM ノード id を受け取る) を使って読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="40fd9-112">CSS objects can be loaded using the `get*ForNode()` calls (which accept a DOM node id).</span></span> <span data-ttu-id="40fd9-113">クライアントは、イベントによってスタイル変更 `styleSheetAdded` / `styleSheetRemoved` を追跡し、そのメソッドを使って必要なスタイルシートの内容を読み込むこともでき `getStyleSheet[Text]()` ます。</span><span class="sxs-lookup"><span data-stu-id="40fd9-113">A client can also keep track of stylesheets via the `styleSheetAdded`/`styleSheetRemoved` events and subsequently load the required stylesheet contents using the `getStyleSheet[Text]()` methods.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="40fd9-114">メソッド</span><span class="sxs-lookup"><span data-stu-id="40fd9-114">Methods</span></span>**](#methods) | <span data-ttu-id="40fd9-115">[enable](#enable)、 [disable](#disable)、 [getInlineStylesForNode](#getinlinestylesfornode)、 [getmatched文法 fornode](#getmatchedstylesfornode)、 [getplatformの](#getplatformfontsfornode) [getComputedStyleForNode](#getcomputedstylefornode)</span><span class="sxs-lookup"><span data-stu-id="40fd9-115">[enable](#enable), [disable](#disable), [getInlineStylesForNode](#getinlinestylesfornode), [getMatchedStylesForNode](#getmatchedstylesfornode), [getPlatformFontsForNode](#getplatformfontsfornode), [getComputedStyleForNode](#getcomputedstylefornode)</span></span> |
| [**<span data-ttu-id="40fd9-116">イベント</span><span class="sxs-lookup"><span data-stu-id="40fd9-116">Events</span></span>**](#events) | <span data-ttu-id="40fd9-117">[styleSheetAdded](#stylesheetadded)、 [styleSheetChanged](#stylesheetchanged)、 [styleSheetRemoved](#stylesheetremoved)</span><span class="sxs-lookup"><span data-stu-id="40fd9-117">[styleSheetAdded](#stylesheetadded), [styleSheetChanged](#stylesheetchanged), [styleSheetRemoved](#stylesheetremoved)</span></span> |
| [**<span data-ttu-id="40fd9-118">型</span><span class="sxs-lookup"><span data-stu-id="40fd9-118">Types</span></span>**](#types) | <span data-ttu-id="40fd9-119">[StyleSheetId](#stylesheetid)、[擬似要素一致](#pseudoelementmatches)、 [inherited entry](#inheritedstyleentry)、 [RuleMatch](#rulematch)、 [Value](#value)、 [SelectorList](#selectorlist)、 [CSSRule](#cssrule)、 [SourceRange、ShorthandEntry](#sourcerange)、 [CSSStyle](#cssstyle)、 [CSSProperty](#cssproperty)、 [CSSMedia](#cssmedia)、 [mediaquery](#mediaquery)、 [mediaqueryexpression](#mediaqueryexpression)、 [platformfontusage](#platformfontusage)、 [CSSKeyframesRule](#csskeyframesrule)、 [CSSKeyframeRule](#csskeyframerule)、 [CSSComputedStyleProperty](#csscomputedstyleproperty)、 [CSSStyleSheetHeader](#cssstylesheetheader) [ShorthandEntry](#shorthandentry)</span><span class="sxs-lookup"><span data-stu-id="40fd9-119">[StyleSheetId](#stylesheetid), [PseudoElementMatches](#pseudoelementmatches), [InheritedStyleEntry](#inheritedstyleentry), [RuleMatch](#rulematch), [Value](#value), [SelectorList](#selectorlist), [CSSRule](#cssrule), [SourceRange](#sourcerange), [ShorthandEntry](#shorthandentry), [CSSStyle](#cssstyle), [CSSProperty](#cssproperty), [CSSMedia](#cssmedia), [MediaQuery](#mediaquery), [MediaQueryExpression](#mediaqueryexpression), [PlatformFontUsage](#platformfontusage), [CSSKeyframesRule](#csskeyframesrule), [CSSKeyframeRule](#csskeyframerule), [CSSComputedStyleProperty](#csscomputedstyleproperty), [CSSStyleSheetHeader](#cssstylesheetheader)</span></span> |
| [**<span data-ttu-id="40fd9-120">依存関係</span><span class="sxs-lookup"><span data-stu-id="40fd9-120">Dependencies</span></span>**](#dependencies) | [<span data-ttu-id="40fd9-121">DOM</span><span class="sxs-lookup"><span data-stu-id="40fd9-121">DOM</span></span>](dom.md) |
## <span data-ttu-id="40fd9-122">メソッド</span><span class="sxs-lookup"><span data-stu-id="40fd9-122">Methods</span></span>

### <span data-ttu-id="40fd9-123">[有効]</span><span class="sxs-lookup"><span data-stu-id="40fd9-123">enable</span></span>
<span data-ttu-id="40fd9-124">指定したページの CSS エージェントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="40fd9-124">Enables the CSS agent for the given page.</span></span> <span data-ttu-id="40fd9-125">クライアントは、このコマンドの結果が受信されるまで CSS エージェントが有効になっていると想定することはできません。</span><span class="sxs-lookup"><span data-stu-id="40fd9-125">Clients should not assume that the CSS agent has been enabled until the result of this command is received.</span></span>

</p>

---

### <span data-ttu-id="40fd9-126">[無効]</span><span class="sxs-lookup"><span data-stu-id="40fd9-126">disable</span></span>
<span data-ttu-id="40fd9-127">指定されたページの CSS エージェントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="40fd9-127">Disables the CSS agent for the given page.</span></span>

</p>

---

### <span data-ttu-id="40fd9-128">getInlineStylesForNode</span><span class="sxs-lookup"><span data-stu-id="40fd9-128">getInlineStylesForNode</span></span>
<span data-ttu-id="40fd9-129">によって識別される DOM ノードのインライン ("style" 属性で明示的に、DOM 属性を使って暗黙的に) 定義されたスタイルを返し `nodeId` ます。</span><span class="sxs-lookup"><span data-stu-id="40fd9-129">Returns the styles defined inline (explicitly in the "style" attribute and implicitly, using DOM attributes) for a DOM node identified by `nodeId`.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-130">パラメーター</span><span class="sxs-lookup"><span data-stu-id="40fd9-130">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-131">nodeId</span><span class="sxs-lookup"><span data-stu-id="40fd9-131">nodeId</span></span></td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-132">返し</span><span class="sxs-lookup"><span data-stu-id="40fd9-132">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-133">inlineStyle</span><span class="sxs-lookup"><span data-stu-id="40fd9-133">inlineStyle</span></span> <br /> <i><span data-ttu-id="40fd9-134">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-134">optional</span></span></i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="40fd9-135">指定した DOM ノードのインラインスタイル。</span><span class="sxs-lookup"><span data-stu-id="40fd9-135">Inline style for the specified DOM node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-136">属性スタイル</span><span class="sxs-lookup"><span data-stu-id="40fd9-136">attributesStyle</span></span> <br /> <i><span data-ttu-id="40fd9-137">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-137">optional</span></span></i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="40fd9-138">属性で定義された要素のスタイル (例: "width = 20 height = 100%")。</span><span class="sxs-lookup"><span data-stu-id="40fd9-138">Attribute-defined element style (e.g. resulting from "width=20 height=100%").</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="40fd9-139">Getmatchedの Fornode</span><span class="sxs-lookup"><span data-stu-id="40fd9-139">getMatchedStylesForNode</span></span>
<span data-ttu-id="40fd9-140">によって識別される DOM ノードに対して要求されたスタイルを返し `nodeId` ます。</span><span class="sxs-lookup"><span data-stu-id="40fd9-140">Returns requested styles for a DOM node identified by `nodeId`.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-141">パラメーター</span><span class="sxs-lookup"><span data-stu-id="40fd9-141">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-142">nodeId</span><span class="sxs-lookup"><span data-stu-id="40fd9-142">nodeId</span></span></td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-143">返し</span><span class="sxs-lookup"><span data-stu-id="40fd9-143">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-144">inlineStyle</span><span class="sxs-lookup"><span data-stu-id="40fd9-144">inlineStyle</span></span> <br /> <i><span data-ttu-id="40fd9-145">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-145">optional</span></span></i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="40fd9-146">指定した DOM ノードのインラインスタイル。</span><span class="sxs-lookup"><span data-stu-id="40fd9-146">Inline style for the specified DOM node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-147">属性スタイル</span><span class="sxs-lookup"><span data-stu-id="40fd9-147">attributesStyle</span></span> <br /> <i><span data-ttu-id="40fd9-148">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-148">optional</span></span></i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="40fd9-149">属性で定義された要素のスタイル (例: "width = 20 height = 100%")。</span><span class="sxs-lookup"><span data-stu-id="40fd9-149">Attribute-defined element style (e.g. resulting from "width=20 height=100%").</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-150">matchedCSSRules</span><span class="sxs-lookup"><span data-stu-id="40fd9-150">matchedCSSRules</span></span> <br /> <i><span data-ttu-id="40fd9-151">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-151">optional</span></span></i></td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td><span data-ttu-id="40fd9-152">該当するすべてのスタイルシートから、このノードに一致する CSS ルール。</span><span class="sxs-lookup"><span data-stu-id="40fd9-152">CSS rules matching this node, from all applicable stylesheets.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-153">疑似要素</span><span class="sxs-lookup"><span data-stu-id="40fd9-153">pseudoElements</span></span> <br /> <i><span data-ttu-id="40fd9-154">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-154">optional</span></span></i></td>
            <td><a href="#pseudoelementmatches"><code class="flyout">PseudoElementMatches[]</code></a></td>
            <td><span data-ttu-id="40fd9-155">このノードでは、擬似スタイルが一致します。</span><span class="sxs-lookup"><span data-stu-id="40fd9-155">Pseudo style matches for this node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-156">引き継が</span><span class="sxs-lookup"><span data-stu-id="40fd9-156">inherited</span></span> <br /> <i><span data-ttu-id="40fd9-157">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-157">optional</span></span></i></td>
            <td><a href="#inheritedstyleentry"><code class="flyout">InheritedStyleEntry[]</code></a></td>
            <td><span data-ttu-id="40fd9-158">継承されたスタイルのチェーン (イミディエイトノードの親から DOM ツリーのルートまで)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-158">A chain of inherited styles (from the immediate node parent up to the DOM tree root).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-159">cssKeyframesRules</span><span class="sxs-lookup"><span data-stu-id="40fd9-159">cssKeyframesRules</span></span> <br /> <i><span data-ttu-id="40fd9-160">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-160">optional</span></span></i></td>
            <td><a href="#csskeyframesrule"><code class="flyout">CSSKeyframesRule[]</code></a></td>
            <td><span data-ttu-id="40fd9-161">このノードに対応する CSS keyframed のアニメーションの一覧です。</span><span class="sxs-lookup"><span data-stu-id="40fd9-161">A list of CSS keyframed animations matching this node.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="40fd9-162">Getplatformフォント Fornode</span><span class="sxs-lookup"><span data-stu-id="40fd9-162">getPlatformFontsForNode</span></span>
<span data-ttu-id="40fd9-163">指定したノードで子テキストノードをレンダリングするために使用したプラットフォームフォントに関する情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="40fd9-163">Requests information about platform fonts which we used to render child TextNodes in the given node.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-164">パラメーター</span><span class="sxs-lookup"><span data-stu-id="40fd9-164">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-165">nodeId</span><span class="sxs-lookup"><span data-stu-id="40fd9-165">nodeId</span></span></td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-166">返し</span><span class="sxs-lookup"><span data-stu-id="40fd9-166">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-167">フォント</span><span class="sxs-lookup"><span data-stu-id="40fd9-167">fonts</span></span></td>
            <td><a href="#platformfontusage"><code class="flyout">PlatformFontUsage[]</code></a></td>
            <td><span data-ttu-id="40fd9-168">使用しているすべてのプラットフォームフォントの利用統計情報</span><span class="sxs-lookup"><span data-stu-id="40fd9-168">Usage statistics for every employed platform font.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="40fd9-169">getComputedStyleForNode</span><span class="sxs-lookup"><span data-stu-id="40fd9-169">getComputedStyleForNode</span></span>
<span data-ttu-id="40fd9-170">によって識別される DOM ノードの計算されたスタイルを返し `nodeId` ます。</span><span class="sxs-lookup"><span data-stu-id="40fd9-170">Returns the computed style for a DOM node identified by `nodeId`.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-171">パラメーター</span><span class="sxs-lookup"><span data-stu-id="40fd9-171">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-172">nodeId</span><span class="sxs-lookup"><span data-stu-id="40fd9-172">nodeId</span></span></td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-173">返し</span><span class="sxs-lookup"><span data-stu-id="40fd9-173">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-174">computedStyle</span><span class="sxs-lookup"><span data-stu-id="40fd9-174">computedStyle</span></span></td>
            <td><a href="#csscomputedstyleproperty"><code class="flyout">CSSComputedStyleProperty[]</code></a></td>
            <td><span data-ttu-id="40fd9-175">指定した DOM ノードの計算されたスタイル。</span><span class="sxs-lookup"><span data-stu-id="40fd9-175">Computed style for the specified DOM node.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="40fd9-176">イベント</span><span class="sxs-lookup"><span data-stu-id="40fd9-176">Events</span></span>

### <span data-ttu-id="40fd9-177">styleSheetAdded</span><span class="sxs-lookup"><span data-stu-id="40fd9-177">styleSheetAdded</span></span>
<span data-ttu-id="40fd9-178">アクティブなドキュメントのスタイルシートが追加されるたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="40fd9-178">Fired whenever an active document stylesheet is added.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-179">パラメーター</span><span class="sxs-lookup"><span data-stu-id="40fd9-179">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-180">header</span><span class="sxs-lookup"><span data-stu-id="40fd9-180">header</span></span></td>
            <td><a href="#cssstylesheetheader"><code class="flyout">CSSStyleSheetHeader</code></a></td>
            <td><span data-ttu-id="40fd9-181">スタイルシート metainfo を追加しました。</span><span class="sxs-lookup"><span data-stu-id="40fd9-181">Added stylesheet metainfo.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="40fd9-182">styleSheetChanged</span><span class="sxs-lookup"><span data-stu-id="40fd9-182">styleSheetChanged</span></span>
<span data-ttu-id="40fd9-183">クライアントの操作の結果として、スタイルシートが変更されるたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="40fd9-183">Fired whenever a stylesheet is changed as a result of the client operation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-184">パラメーター</span><span class="sxs-lookup"><span data-stu-id="40fd9-184">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-185">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="40fd9-185">styleSheetId</span></span></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="40fd9-186">styleSheetRemoved</span><span class="sxs-lookup"><span data-stu-id="40fd9-186">styleSheetRemoved</span></span>
<span data-ttu-id="40fd9-187">アクティブなドキュメントのスタイルシートが削除されるたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="40fd9-187">Fired whenever an active document stylesheet is removed.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-188">パラメーター</span><span class="sxs-lookup"><span data-stu-id="40fd9-188">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-189">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="40fd9-189">styleSheetId</span></span></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="40fd9-190">削除されたスタイルシートの識別子。</span><span class="sxs-lookup"><span data-stu-id="40fd9-190">Identifier of the removed stylesheet.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="40fd9-191">型</span><span class="sxs-lookup"><span data-stu-id="40fd9-191">Types</span></span>

### <a name="stylesheetid"></a> <span data-ttu-id="40fd9-192">StyleSheetId</span><span class="sxs-lookup"><span data-stu-id="40fd9-192">StyleSheetId</span></span> `string`



</p>

---

### <a name="pseudoelementmatches"></a> <span data-ttu-id="40fd9-193">擬似要素の一致</span><span class="sxs-lookup"><span data-stu-id="40fd9-193">PseudoElementMatches</span></span> `object`

<span data-ttu-id="40fd9-194">1つの擬似スタイルの CSS ルールコレクション。</span><span class="sxs-lookup"><span data-stu-id="40fd9-194">CSS rule collection for a single pseudo style.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-195">プロパティ</span><span class="sxs-lookup"><span data-stu-id="40fd9-195">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-196">擬似の型</span><span class="sxs-lookup"><span data-stu-id="40fd9-196">pseudoType</span></span></td>
            <td><a href="dom.md#pseudotype"><code class="flyout">DOM.PseudoType</code></a></td>
            <td><span data-ttu-id="40fd9-197">疑似要素型。</span><span class="sxs-lookup"><span data-stu-id="40fd9-197">Pseudo element type.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-198">一致</span><span class="sxs-lookup"><span data-stu-id="40fd9-198">matches</span></span></td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td><span data-ttu-id="40fd9-199">擬似スタイルに適用される CSS ルールの一致</span><span class="sxs-lookup"><span data-stu-id="40fd9-199">Matches of CSS rules applicable to the pseudo style.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="inheritedstyleentry"></a> <span data-ttu-id="40fd9-200">Inheritedスタイルエントリ</span><span class="sxs-lookup"><span data-stu-id="40fd9-200">InheritedStyleEntry</span></span> `object`

<span data-ttu-id="40fd9-201">先祖ノードから継承された CSS ルールコレクション。</span><span class="sxs-lookup"><span data-stu-id="40fd9-201">Inherited CSS rule collection from ancestor node.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-202">プロパティ</span><span class="sxs-lookup"><span data-stu-id="40fd9-202">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-203">inlineStyle</span><span class="sxs-lookup"><span data-stu-id="40fd9-203">inlineStyle</span></span> <br /> <i><span data-ttu-id="40fd9-204">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-204">optional</span></span></i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="40fd9-205">Style 継承チェーン内の先祖ノードのインラインスタイル (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-205">The ancestor node's inline style, if any, in the style inheritance chain.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-206">matchedCSSRules</span><span class="sxs-lookup"><span data-stu-id="40fd9-206">matchedCSSRules</span></span></td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td><span data-ttu-id="40fd9-207">スタイル継承チェーンの先祖ノードと一致する CSS ルールの一致</span><span class="sxs-lookup"><span data-stu-id="40fd9-207">Matches of CSS rules matching the ancestor node in the style inheritance chain.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="rulematch"></a> <span data-ttu-id="40fd9-208">RuleMatch</span><span class="sxs-lookup"><span data-stu-id="40fd9-208">RuleMatch</span></span> `object`

<span data-ttu-id="40fd9-209">CSS ルールのデータを照合します。</span><span class="sxs-lookup"><span data-stu-id="40fd9-209">Match data for a CSS rule.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-210">プロパティ</span><span class="sxs-lookup"><span data-stu-id="40fd9-210">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-211">ルール</span><span class="sxs-lookup"><span data-stu-id="40fd9-211">rule</span></span></td>
            <td><a href="#cssrule"><code class="flyout">CSSRule</code></a></td>
            <td><span data-ttu-id="40fd9-212">一致する CSS ルール。</span><span class="sxs-lookup"><span data-stu-id="40fd9-212">CSS rule in the match.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="value"></a> <span data-ttu-id="40fd9-213">値</span><span class="sxs-lookup"><span data-stu-id="40fd9-213">Value</span></span> `object`

<span data-ttu-id="40fd9-214">単純なセレクターのデータ (セレクターリストでコンマで区切られています)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-214">Data for a simple selector (these are delimited by commas in a selector list).</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-215">プロパティ</span><span class="sxs-lookup"><span data-stu-id="40fd9-215">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-216">テキスト</span><span class="sxs-lookup"><span data-stu-id="40fd9-216">text</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="40fd9-217">値のテキスト。</span><span class="sxs-lookup"><span data-stu-id="40fd9-217">Value text.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-218">範囲</span><span class="sxs-lookup"><span data-stu-id="40fd9-218">range</span></span> <br /> <i><span data-ttu-id="40fd9-219">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-219">optional</span></span></i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td><span data-ttu-id="40fd9-220">基になるリソースの値の範囲 (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-220">Value range in the underlying resource (if available).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="selectorlist"></a> <span data-ttu-id="40fd9-221">SelectorList</span><span class="sxs-lookup"><span data-stu-id="40fd9-221">SelectorList</span></span> `object`

<span data-ttu-id="40fd9-222">セレクターリストのデータ。</span><span class="sxs-lookup"><span data-stu-id="40fd9-222">Selector list data.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-223">プロパティ</span><span class="sxs-lookup"><span data-stu-id="40fd9-223">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-224">軸</span><span class="sxs-lookup"><span data-stu-id="40fd9-224">selectors</span></span></td>
            <td><a href="#value"><code class="flyout">Value[]</code></a></td>
            <td><span data-ttu-id="40fd9-225">リスト内のセレクター。</span><span class="sxs-lookup"><span data-stu-id="40fd9-225">Selectors in the list.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-226">テキスト</span><span class="sxs-lookup"><span data-stu-id="40fd9-226">text</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="40fd9-227">ルールセレクターのテキスト。</span><span class="sxs-lookup"><span data-stu-id="40fd9-227">Rule selector text.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssrule"></a> <span data-ttu-id="40fd9-228">CSSRule</span><span class="sxs-lookup"><span data-stu-id="40fd9-228">CSSRule</span></span> `object`

<span data-ttu-id="40fd9-229">CSS ルール表現。</span><span class="sxs-lookup"><span data-stu-id="40fd9-229">CSS rule representation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-230">プロパティ</span><span class="sxs-lookup"><span data-stu-id="40fd9-230">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-231">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="40fd9-231">styleSheetId</span></span> <br /> <i><span data-ttu-id="40fd9-232">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-232">optional</span></span></i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="40fd9-233">この仕分けルールの適用元の css スタイルシート識別子 (ユーザーエージェントスタイルシートとユーザー指定のスタイルシートルールにはありません)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-233">The css style sheet identifier (absent for user agent stylesheet and user-specified stylesheet rules) this rule came from.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-234">selectorList</span><span class="sxs-lookup"><span data-stu-id="40fd9-234">selectorList</span></span> <br /> <i><span data-ttu-id="40fd9-235">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-235">optional</span></span></i></td>
            <td><a href="#selectorlist"><code class="flyout">SelectorList</code></a></td>
            <td><span data-ttu-id="40fd9-236">ルールセレクターのデータ。</span><span class="sxs-lookup"><span data-stu-id="40fd9-236">Rule selector data.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-237">cdn</span><span class="sxs-lookup"><span data-stu-id="40fd9-237">origin</span></span> <br /> <i><span data-ttu-id="40fd9-238">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-238">optional</span></span></i></td>
            <td><<!--  <a href="#stylesheetorigin">  --><code class="flyout">StyleSheetOrigin</code><!--  </a>  --></td>
            <td><span data-ttu-id="40fd9-239">親スタイルシートの原点。</span><span class="sxs-lookup"><span data-stu-id="40fd9-239">Parent stylesheet's origin.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-240">スタイル</span><span class="sxs-lookup"><span data-stu-id="40fd9-240">style</span></span></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="40fd9-241">関連付けられたスタイル宣言。</span><span class="sxs-lookup"><span data-stu-id="40fd9-241">Associated style declaration.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-242">メディア</span><span class="sxs-lookup"><span data-stu-id="40fd9-242">media</span></span> <br /> <i><span data-ttu-id="40fd9-243">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-243">optional</span></span></i></td>
            <td><a href="#cssmedia"><code class="flyout">CSSMedia[]</code></a></td>
            <td><span data-ttu-id="40fd9-244">メディア一覧の配列 (メディアクエリを含むルールの場合)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-244">Media list array (for rules involving media queries).</span></span> <span data-ttu-id="40fd9-245">配列は、最も内側にあるメディアクエリを、外側に向かって列挙します。</span><span class="sxs-lookup"><span data-stu-id="40fd9-245">The array enumerates media queries starting with the innermost one, going outwards.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="sourcerange"></a> <span data-ttu-id="40fd9-246">SourceRange</span><span class="sxs-lookup"><span data-stu-id="40fd9-246">SourceRange</span></span> `object`

<span data-ttu-id="40fd9-247">リソース内のテキスト範囲。</span><span class="sxs-lookup"><span data-stu-id="40fd9-247">Text range within a resource.</span></span> <span data-ttu-id="40fd9-248">すべての数値は0から始まります。</span><span class="sxs-lookup"><span data-stu-id="40fd9-248">All numbers are zero-based.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-249">プロパティ</span><span class="sxs-lookup"><span data-stu-id="40fd9-249">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-250">startLine</span><span class="sxs-lookup"><span data-stu-id="40fd9-250">startLine</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="40fd9-251">範囲の開始行。</span><span class="sxs-lookup"><span data-stu-id="40fd9-251">Start line of range.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-252">startColumn</span><span class="sxs-lookup"><span data-stu-id="40fd9-252">startColumn</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="40fd9-253">範囲の開始列 (両端を含む)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-253">Start column of range (inclusive).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-254">endLine</span><span class="sxs-lookup"><span data-stu-id="40fd9-254">endLine</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="40fd9-255">範囲の最後の行</span><span class="sxs-lookup"><span data-stu-id="40fd9-255">End line of range</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-256">endColumn</span><span class="sxs-lookup"><span data-stu-id="40fd9-256">endColumn</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="40fd9-257">範囲の終了列 (排他)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-257">End column of range (exclusive).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="shorthandentry"></a> <span data-ttu-id="40fd9-258">ShorthandEntry</span><span class="sxs-lookup"><span data-stu-id="40fd9-258">ShorthandEntry</span></span> `object`



<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-259">プロパティ</span><span class="sxs-lookup"><span data-stu-id="40fd9-259">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-260">name</span><span class="sxs-lookup"><span data-stu-id="40fd9-260">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="40fd9-261">短縮名。</span><span class="sxs-lookup"><span data-stu-id="40fd9-261">Shorthand name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-262">value</span><span class="sxs-lookup"><span data-stu-id="40fd9-262">value</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="40fd9-263">短縮値。</span><span class="sxs-lookup"><span data-stu-id="40fd9-263">Shorthand value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-264">大事な</span><span class="sxs-lookup"><span data-stu-id="40fd9-264">important</span></span> <br /> <i><span data-ttu-id="40fd9-265">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-265">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="40fd9-266">プロパティに "! 重要" の注釈が含まれているかどうか ( `false` 存在しない場合は意味)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-266">Whether the property has "!important" annotation (implies `false` if absent).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssstyle"></a> <span data-ttu-id="40fd9-267">CSSStyle</span><span class="sxs-lookup"><span data-stu-id="40fd9-267">CSSStyle</span></span> `object`

<span data-ttu-id="40fd9-268">CSS スタイル表現。</span><span class="sxs-lookup"><span data-stu-id="40fd9-268">CSS style representation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-269">プロパティ</span><span class="sxs-lookup"><span data-stu-id="40fd9-269">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-270">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="40fd9-270">styleSheetId</span></span> <br /> <i><span data-ttu-id="40fd9-271">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-271">optional</span></span></i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="40fd9-272">この仕分けルールの適用元の css スタイルシート識別子 (ユーザーエージェントスタイルシートとユーザー指定のスタイルシートルールにはありません)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-272">The css style sheet identifier (absent for user agent stylesheet and user-specified stylesheet rules) this rule came from.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-273">cssProperties</span><span class="sxs-lookup"><span data-stu-id="40fd9-273">cssProperties</span></span></td>
            <td><a href="#cssproperty"><code class="flyout">CSSProperty[]</code></a></td>
            <td><span data-ttu-id="40fd9-274">スタイルの CSS プロパティ。</span><span class="sxs-lookup"><span data-stu-id="40fd9-274">CSS properties in the style.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-275">shorthandEntries</span><span class="sxs-lookup"><span data-stu-id="40fd9-275">shorthandEntries</span></span></td>
            <td><a href="#shorthandentry"><code class="flyout">ShorthandEntry[]</code></a></td>
            <td><span data-ttu-id="40fd9-276">スタイルに含まれるすべての shorthands について計算された値。</span><span class="sxs-lookup"><span data-stu-id="40fd9-276">Computed values for all shorthands found in the style.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-277">cssText</span><span class="sxs-lookup"><span data-stu-id="40fd9-277">cssText</span></span> <br /> <i><span data-ttu-id="40fd9-278">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-278">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="40fd9-279">スタイル宣言のテキスト (使用できる場合)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-279">Style declaration text (if available).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-280">範囲</span><span class="sxs-lookup"><span data-stu-id="40fd9-280">range</span></span> <br /> <i><span data-ttu-id="40fd9-281">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-281">optional</span></span></i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td><span data-ttu-id="40fd9-282">囲まれたスタイル宣言の範囲 (使用できる場合)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-282">Style declaration range in the enclosing stylesheet (if available).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssproperty"></a> <span data-ttu-id="40fd9-283">CSSProperty</span><span class="sxs-lookup"><span data-stu-id="40fd9-283">CSSProperty</span></span> `object`

<span data-ttu-id="40fd9-284">CSS プロパティ宣言データ。</span><span class="sxs-lookup"><span data-stu-id="40fd9-284">CSS property declaration data.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-285">プロパティ</span><span class="sxs-lookup"><span data-stu-id="40fd9-285">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-286">name</span><span class="sxs-lookup"><span data-stu-id="40fd9-286">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="40fd9-287">プロパティ名。</span><span class="sxs-lookup"><span data-stu-id="40fd9-287">The property name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-288">value</span><span class="sxs-lookup"><span data-stu-id="40fd9-288">value</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="40fd9-289">プロパティ値。</span><span class="sxs-lookup"><span data-stu-id="40fd9-289">The property value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-290">大事な</span><span class="sxs-lookup"><span data-stu-id="40fd9-290">important</span></span> <br /> <i><span data-ttu-id="40fd9-291">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-291">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="40fd9-292">プロパティに "! 重要" の注釈が含まれているかどうか ( `false` 存在しない場合は意味)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-292">Whether the property has "!important" annotation (implies `false` if absent).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-293">明示</span><span class="sxs-lookup"><span data-stu-id="40fd9-293">implicit</span></span> <br /> <i><span data-ttu-id="40fd9-294">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-294">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="40fd9-295">プロパティが暗黙的であるかどうかを `false` 示します (存在しない場合を意味します)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-295">Whether the property is implicit (implies `false` if absent).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-296">テキスト</span><span class="sxs-lookup"><span data-stu-id="40fd9-296">text</span></span> <br /> <i><span data-ttu-id="40fd9-297">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-297">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="40fd9-298">スタイルで指定されている完全なプロパティテキスト。</span><span class="sxs-lookup"><span data-stu-id="40fd9-298">The full property text as specified in the style.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-299">Parsek</span><span class="sxs-lookup"><span data-stu-id="40fd9-299">parsedOk</span></span> <br /> <i><span data-ttu-id="40fd9-300">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-300">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="40fd9-301">プロパティがブラウザーによって認識されるかどうか ( `true` 存在しない場合)</span><span class="sxs-lookup"><span data-stu-id="40fd9-301">Whether the property is understood by the browser (implies `true` if absent).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-302">無効に</span><span class="sxs-lookup"><span data-stu-id="40fd9-302">disabled</span></span> <br /> <i><span data-ttu-id="40fd9-303">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-303">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="40fd9-304">プロパティがユーザーによって無効にされているかどうか (ソースベースのプロパティのみに存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-304">Whether the property is disabled by the user (present for source-based properties only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-305">範囲</span><span class="sxs-lookup"><span data-stu-id="40fd9-305">range</span></span> <br /> <i><span data-ttu-id="40fd9-306">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-306">optional</span></span></i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td><span data-ttu-id="40fd9-307">囲む style 宣言のプロパティ範囲全体 (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-307">The entire property range in the enclosing style declaration (if available).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssmedia"></a> <span data-ttu-id="40fd9-308">CSSMedia</span><span class="sxs-lookup"><span data-stu-id="40fd9-308">CSSMedia</span></span> `object`

<span data-ttu-id="40fd9-309">CSS メディアルール記述子。</span><span class="sxs-lookup"><span data-stu-id="40fd9-309">CSS media rule descriptor.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-310">プロパティ</span><span class="sxs-lookup"><span data-stu-id="40fd9-310">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-311">テキスト</span><span class="sxs-lookup"><span data-stu-id="40fd9-311">text</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="40fd9-312">メディアクエリテキスト。</span><span class="sxs-lookup"><span data-stu-id="40fd9-312">Media query text.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-313">ソース</span><span class="sxs-lookup"><span data-stu-id="40fd9-313">source</span></span></td>
            <td><code class="flyout">string</code> <br /> <i><span data-ttu-id="40fd9-314">許可される値: mediaRule、inlineSheet、linkedSheet、</span><span class="sxs-lookup"><span data-stu-id="40fd9-314">Allowed values: mediaRule, importRule, linkedSheet, inlineSheet</span></span></i></td>
            <td><span data-ttu-id="40fd9-315">メディアクエリのソース: "Medi@media ArimportRule" は、インラインスタイルシートの STYLE タグで "media" 属性によって指定されている場合に、リンクされたスタイルのリンクタグで "media" 属性で指定されている場合、"inlineSheet" を指定すると、"" を指定すると、"@import" となります。</span><span class="sxs-lookup"><span data-stu-id="40fd9-315">Source of the media query: "mediaRule" if specified by a @media rule, "importRule" if specified by an @import rule, "linkedSheet" if specified by a "media" attribute in a linked stylesheet's LINK tag, "inlineSheet" if specified by a "media" attribute in an inline stylesheet's STYLE tag.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-316">sourceURL</span><span class="sxs-lookup"><span data-stu-id="40fd9-316">sourceURL</span></span> <br /> <i><span data-ttu-id="40fd9-317">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-317">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="40fd9-318">メディアクエリの説明が含まれているドキュメントの URL です。</span><span class="sxs-lookup"><span data-stu-id="40fd9-318">URL of the document containing the media query description.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-319">範囲</span><span class="sxs-lookup"><span data-stu-id="40fd9-319">range</span></span> <br /> <i><span data-ttu-id="40fd9-320">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-320">optional</span></span></i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td><span data-ttu-id="40fd9-321">包含されたルール (@media または @import) ヘッダー範囲 (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-321">The associated rule (@media or @import) header range in the enclosing stylesheet (if available).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-322">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="40fd9-322">styleSheetId</span></span> <br /> <i><span data-ttu-id="40fd9-323">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-323">optional</span></span></i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="40fd9-324">このオブジェクトが含まれているスタイルシートの識別子 (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-324">Identifier of the stylesheet containing this object (if exists).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-325">mediaList</span><span class="sxs-lookup"><span data-stu-id="40fd9-325">mediaList</span></span> <br /> <i><span data-ttu-id="40fd9-326">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-326">optional</span></span></i></td>
            <td><a href="#mediaquery"><code class="flyout">MediaQuery[]</code></a></td>
            <td><span data-ttu-id="40fd9-327">メディアクエリの配列。</span><span class="sxs-lookup"><span data-stu-id="40fd9-327">Array of media queries.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="mediaquery"></a> <span data-ttu-id="40fd9-328">MediaQuery</span><span class="sxs-lookup"><span data-stu-id="40fd9-328">MediaQuery</span></span> `object`

<span data-ttu-id="40fd9-329">メディアクエリ記述子。</span><span class="sxs-lookup"><span data-stu-id="40fd9-329">Media query descriptor.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-330">プロパティ</span><span class="sxs-lookup"><span data-stu-id="40fd9-330">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-331">式</span><span class="sxs-lookup"><span data-stu-id="40fd9-331">expressions</span></span></td>
            <td><a href="#mediaqueryexpression"><code class="flyout">MediaQueryExpression[]</code></a></td>
            <td><span data-ttu-id="40fd9-332">メディアクエリ式の配列。</span><span class="sxs-lookup"><span data-stu-id="40fd9-332">Array of media query expressions.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-333">active</span><span class="sxs-lookup"><span data-stu-id="40fd9-333">active</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="40fd9-334">メディアクエリ条件が満たされているかどうか。</span><span class="sxs-lookup"><span data-stu-id="40fd9-334">Whether the media query condition is satisfied.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="mediaqueryexpression"></a> <span data-ttu-id="40fd9-335">MediaQueryExpression</span><span class="sxs-lookup"><span data-stu-id="40fd9-335">MediaQueryExpression</span></span> `object`

<span data-ttu-id="40fd9-336">メディアクエリ式記述子。</span><span class="sxs-lookup"><span data-stu-id="40fd9-336">Media query expression descriptor.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-337">プロパティ</span><span class="sxs-lookup"><span data-stu-id="40fd9-337">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-338">value</span><span class="sxs-lookup"><span data-stu-id="40fd9-338">value</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="40fd9-339">メディアクエリ式の値。</span><span class="sxs-lookup"><span data-stu-id="40fd9-339">Media query expression value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-340">配電</span><span class="sxs-lookup"><span data-stu-id="40fd9-340">unit</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="40fd9-341">メディアクエリ式の単位。</span><span class="sxs-lookup"><span data-stu-id="40fd9-341">Media query expression units.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-342">機能</span><span class="sxs-lookup"><span data-stu-id="40fd9-342">feature</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="40fd9-343">メディアクエリ式機能。</span><span class="sxs-lookup"><span data-stu-id="40fd9-343">Media query expression feature.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-344">valueRange</span><span class="sxs-lookup"><span data-stu-id="40fd9-344">valueRange</span></span> <br /> <i><span data-ttu-id="40fd9-345">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-345">optional</span></span></i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td><span data-ttu-id="40fd9-346">包含するスタイルシート内の値のテキストに関連付けられている範囲 (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-346">The associated range of the value text in the enclosing stylesheet (if available).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-347">computedLength</span><span class="sxs-lookup"><span data-stu-id="40fd9-347">computedLength</span></span> <br /> <i><span data-ttu-id="40fd9-348">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-348">optional</span></span></i></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="40fd9-349">メディアクエリ式の計算された長さ (該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-349">Computed length of media query expression (if applicable).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="platformfontusage"></a> <span data-ttu-id="40fd9-350">PlatformFontUsage</span><span class="sxs-lookup"><span data-stu-id="40fd9-350">PlatformFontUsage</span></span> `object`

<span data-ttu-id="40fd9-351">指定したフォントでレンダリングされたグリフの量に関する情報。</span><span class="sxs-lookup"><span data-stu-id="40fd9-351">Information about amount of glyphs that were rendered with given font.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-352">プロパティ</span><span class="sxs-lookup"><span data-stu-id="40fd9-352">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-353">familyName</span><span class="sxs-lookup"><span data-stu-id="40fd9-353">familyName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="40fd9-354">プラットフォームによって報告されるフォントのファミリ名。</span><span class="sxs-lookup"><span data-stu-id="40fd9-354">Font's family name reported by platform.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-355">isCustomFont</span><span class="sxs-lookup"><span data-stu-id="40fd9-355">isCustomFont</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="40fd9-356">フォントがローカルでダウンロードまたは解決されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="40fd9-356">Indicates if the font was downloaded or resolved locally.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-357">glyphCount</span><span class="sxs-lookup"><span data-stu-id="40fd9-357">glyphCount</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="40fd9-358">このフォントでレンダリングされたグリフの量。</span><span class="sxs-lookup"><span data-stu-id="40fd9-358">Amount of glyphs that were rendered with this font.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="csskeyframesrule"></a> <span data-ttu-id="40fd9-359">CSSKeyframesRule</span><span class="sxs-lookup"><span data-stu-id="40fd9-359">CSSKeyframesRule</span></span> `object`

<span data-ttu-id="40fd9-360">CSS キーフレームルール表現。</span><span class="sxs-lookup"><span data-stu-id="40fd9-360">CSS keyframes rule representation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-361">プロパティ</span><span class="sxs-lookup"><span data-stu-id="40fd9-361">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-362">アニメーション名</span><span class="sxs-lookup"><span data-stu-id="40fd9-362">animationName</span></span></td>
            <td><a href="#value"><code class="flyout">Value</code></a></td>
            <td><span data-ttu-id="40fd9-363">アニメーション名。</span><span class="sxs-lookup"><span data-stu-id="40fd9-363">Animation name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-364">持つ</span><span class="sxs-lookup"><span data-stu-id="40fd9-364">keyframes</span></span></td>
            <td><a href="#csskeyframerule"><code class="flyout">CSSKeyframeRule[]</code></a></td>
            <td><span data-ttu-id="40fd9-365">キーフレームの一覧。</span><span class="sxs-lookup"><span data-stu-id="40fd9-365">List of keyframes.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="csskeyframerule"></a> <span data-ttu-id="40fd9-366">CSSKeyframeRule</span><span class="sxs-lookup"><span data-stu-id="40fd9-366">CSSKeyframeRule</span></span> `object`

<span data-ttu-id="40fd9-367">CSS キーフレームルール表現。</span><span class="sxs-lookup"><span data-stu-id="40fd9-367">CSS keyframe rule representation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-368">プロパティ</span><span class="sxs-lookup"><span data-stu-id="40fd9-368">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-369">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="40fd9-369">styleSheetId</span></span> <br /> <i><span data-ttu-id="40fd9-370">オプション</span><span class="sxs-lookup"><span data-stu-id="40fd9-370">optional</span></span></i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="40fd9-371">この仕分けルールの適用元の css スタイルシート識別子 (ユーザーエージェントスタイルシートとユーザー指定のスタイルシートルールにはありません)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-371">The css style sheet identifier (absent for user agent stylesheet and user-specified stylesheet rules) this rule came from.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-372">cdn</span><span class="sxs-lookup"><span data-stu-id="40fd9-372">origin</span></span></td>
            <td><!--  <a href="#stylesheetorigin">  --><code class="flyout">StyleSheetOrigin</code><!--  </a>  --></td>
            <td><span data-ttu-id="40fd9-373">親スタイルシートの原点。</span><span class="sxs-lookup"><span data-stu-id="40fd9-373">Parent stylesheet's origin.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-374">keyText</span><span class="sxs-lookup"><span data-stu-id="40fd9-374">keyText</span></span></td>
            <td><a href="#value"><code class="flyout">Value</code></a></td>
            <td><span data-ttu-id="40fd9-375">関連付けられているキーテキスト。</span><span class="sxs-lookup"><span data-stu-id="40fd9-375">Associated key text.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-376">スタイル</span><span class="sxs-lookup"><span data-stu-id="40fd9-376">style</span></span></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="40fd9-377">関連付けられたスタイル宣言。</span><span class="sxs-lookup"><span data-stu-id="40fd9-377">Associated style declaration.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="csscomputedstyleproperty"></a> <span data-ttu-id="40fd9-378">CSSComputedStyleProperty</span><span class="sxs-lookup"><span data-stu-id="40fd9-378">CSSComputedStyleProperty</span></span> `object`



<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-379">プロパティ</span><span class="sxs-lookup"><span data-stu-id="40fd9-379">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-380">name</span><span class="sxs-lookup"><span data-stu-id="40fd9-380">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="40fd9-381">計算されたスタイルプロパティの名前。</span><span class="sxs-lookup"><span data-stu-id="40fd9-381">Computed style property name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-382">value</span><span class="sxs-lookup"><span data-stu-id="40fd9-382">value</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="40fd9-383">計算された style プロパティの値。</span><span class="sxs-lookup"><span data-stu-id="40fd9-383">Computed style property value.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssstylesheetheader"></a> <span data-ttu-id="40fd9-384">CSSStyleSheetHeader</span><span class="sxs-lookup"><span data-stu-id="40fd9-384">CSSStyleSheetHeader</span></span> `object`

<span data-ttu-id="40fd9-385">CSS スタイルシート metainformation。</span><span class="sxs-lookup"><span data-stu-id="40fd9-385">CSS stylesheet metainformation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="40fd9-386">プロパティ</span><span class="sxs-lookup"><span data-stu-id="40fd9-386">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="40fd9-387">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="40fd9-387">styleSheetId</span></span></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="40fd9-388">スタイルシートの識別子。</span><span class="sxs-lookup"><span data-stu-id="40fd9-388">The stylesheet identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-389">sourceURL</span><span class="sxs-lookup"><span data-stu-id="40fd9-389">sourceURL</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="40fd9-390">スタイルシートリソースの URL。</span><span class="sxs-lookup"><span data-stu-id="40fd9-390">Stylesheet resource URL.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-391">無効に</span><span class="sxs-lookup"><span data-stu-id="40fd9-391">disabled</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="40fd9-392">スタイルシートが無効になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="40fd9-392">Denotes whether the stylesheet is disabled.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-393">isInline</span><span class="sxs-lookup"><span data-stu-id="40fd9-393">isInline</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="40fd9-394">パーサーによってこのスタイルタグにこのスタイルシートが作成されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="40fd9-394">Whether this stylesheet is created for STYLE tag by parser.</span></span> <span data-ttu-id="40fd9-395">このフラグは、文書に記述されたスタイルタグには設定されません。</span><span class="sxs-lookup"><span data-stu-id="40fd9-395">This flag is not set for document.written STYLE tags.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-396">startLine</span><span class="sxs-lookup"><span data-stu-id="40fd9-396">startLine</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="40fd9-397">リソース内のスタイルシートの線のオフセット (ゼロに基づく)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-397">Line offset of the stylesheet within the resource (zero based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-398">startColumn</span><span class="sxs-lookup"><span data-stu-id="40fd9-398">startColumn</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="40fd9-399">リソース内のスタイルシートの列オフセット (ゼロに基づく)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-399">Column offset of the stylesheet within the resource (zero based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="40fd9-400">全長</span><span class="sxs-lookup"><span data-stu-id="40fd9-400">length</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="40fd9-401">コンテンツのサイズ (文字単位)。</span><span class="sxs-lookup"><span data-stu-id="40fd9-401">Size of the content (in characters).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="40fd9-402">依存関係</span><span class="sxs-lookup"><span data-stu-id="40fd9-402">Dependencies</span></span>

[<span data-ttu-id="40fd9-403">DOM</span><span class="sxs-lookup"><span data-stu-id="40fd9-403">DOM</span></span>](dom.md)
