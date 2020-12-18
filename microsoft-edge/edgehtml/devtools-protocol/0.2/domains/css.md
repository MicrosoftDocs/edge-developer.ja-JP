---
description: CSS ドメインのリファレンス。 このドメインは、CSS の読み取り/書き込み操作を公開します。 すべての CSS オブジェクト (スタイルシート、ルール、およびスタイル) は、関連するオブジェクトに対する後続の操作で使用 `id` されます。 各オブジェクトの種類は、特定の構造を持ち、異なる種類の `id` オブジェクト間で互換性を持つものではありません。 CSS オブジェクトは、呼び出し (DOM ノード ID を受 `get*ForNode()` け入れる) を使用して読み込まれます。 クライアントは、イベントを介してスタイルシートを追跡し、メソッドを使用して必要なスタイルシートの `styleSheetAdded` / `styleSheetRemoved` コンテンツを読み `getStyleSheet[Text]()` 込むすることもできます。
title: CSS ドメイン - DevTools プロトコル バージョン 0.2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cf5efdef09b7e2d9041cd8536faaff8fb99a7f71
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234792"
---
# <span data-ttu-id="c7a83-108">CSS</span><span class="sxs-lookup"><span data-stu-id="c7a83-108">CSS</span></span>

<span data-ttu-id="c7a83-109">このドメインは、CSS の読み取り/書き込み操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="c7a83-109">This domain exposes CSS read/write operations.</span></span> <span data-ttu-id="c7a83-110">すべての CSS オブジェクト (スタイルシート、ルール、およびスタイル) は、関連するオブジェクトに対する後続の操作で使用 `id` されます。</span><span class="sxs-lookup"><span data-stu-id="c7a83-110">All CSS objects (stylesheets, rules, and styles) have an associated `id` used in subsequent operations on the related object.</span></span> <span data-ttu-id="c7a83-111">各オブジェクトの種類は、特定の構造を持ち、異なる種類の `id` オブジェクト間で互換性を持つものではありません。</span><span class="sxs-lookup"><span data-stu-id="c7a83-111">Each object type has a specific `id` structure, and those are not interchangeable between objects of different kinds.</span></span> <span data-ttu-id="c7a83-112">CSS オブジェクトは、呼び出し (DOM ノード ID を受 `get*ForNode()` け入れる) を使用して読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="c7a83-112">CSS objects can be loaded using the `get*ForNode()` calls (which accept a DOM node id).</span></span> <span data-ttu-id="c7a83-113">クライアントは、イベントを介してスタイルシートを追跡し、メソッドを使用して必要なスタイルシートの `styleSheetAdded` / `styleSheetRemoved` コンテンツを読み `getStyleSheet[Text]()` 込むすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c7a83-113">A client can also keep track of stylesheets via the `styleSheetAdded`/`styleSheetRemoved` events and subsequently load the required stylesheet contents using the `getStyleSheet[Text]()` methods.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="c7a83-114">メソッド</span><span class="sxs-lookup"><span data-stu-id="c7a83-114">Methods</span></span>**](#methods) | <span data-ttu-id="c7a83-115">[enable](#enable)、 [disable](#disable)、 [getInlineStylesForNode](#getinlinestylesfornode)、 [getMatchedStylesForNode](#getmatchedstylesfornode)、 [getPlatformFontsForNode](#getplatformfontsfornode)、 [getComputedStyleForNode](#getcomputedstylefornode)</span><span class="sxs-lookup"><span data-stu-id="c7a83-115">[enable](#enable), [disable](#disable), [getInlineStylesForNode](#getinlinestylesfornode), [getMatchedStylesForNode](#getmatchedstylesfornode), [getPlatformFontsForNode](#getplatformfontsfornode), [getComputedStyleForNode](#getcomputedstylefornode)</span></span> |
| [**<span data-ttu-id="c7a83-116">イベント</span><span class="sxs-lookup"><span data-stu-id="c7a83-116">Events</span></span>**](#events) | <span data-ttu-id="c7a83-117">[styleSheetAdded](#stylesheetadded)、 [styleSheetChanged](#stylesheetchanged)、 [styleSheetRemoved](#stylesheetremoved)</span><span class="sxs-lookup"><span data-stu-id="c7a83-117">[styleSheetAdded](#stylesheetadded), [styleSheetChanged](#stylesheetchanged), [styleSheetRemoved](#stylesheetremoved)</span></span> |
| [**<span data-ttu-id="c7a83-118">型</span><span class="sxs-lookup"><span data-stu-id="c7a83-118">Types</span></span>**](#types) | <span data-ttu-id="c7a83-119">[StyleSheetId](#stylesheetid), [PseudoElementMatches](#pseudoelementmatches), [InheritedStyleEntry](#inheritedstyleentry), [RuleMatch](#rulematch), [Value](#value), [SelectorList](#selectorlist), [CSSRule](#cssrule), [SourceRange](#sourcerange), [ShorthandEntry](#shorthandentry), [CSSStyle](#cssstyle), [CSSProperty](#cssproperty), [CSSMedia](#cssmedia), MediaQuery , [MediaQueryExpression](#mediaqueryexpression), [PlatformFontUsage](#platformfontusage), [](#mediaquery) [CSSKeyframesRule](#csskeyframesrule), [CSSKeyframeRule](#csskeyframerule), [CSSComputedStyleProperty](#csscomputedstyleproperty), [CSSStyleSheetHeader](#cssstylesheetheader)</span><span class="sxs-lookup"><span data-stu-id="c7a83-119">[StyleSheetId](#stylesheetid), [PseudoElementMatches](#pseudoelementmatches), [InheritedStyleEntry](#inheritedstyleentry), [RuleMatch](#rulematch), [Value](#value), [SelectorList](#selectorlist), [CSSRule](#cssrule), [SourceRange](#sourcerange), [ShorthandEntry](#shorthandentry), [CSSStyle](#cssstyle), [CSSProperty](#cssproperty), [CSSMedia](#cssmedia), [MediaQuery](#mediaquery), [MediaQueryExpression](#mediaqueryexpression), [PlatformFontUsage](#platformfontusage), [CSSKeyframesRule](#csskeyframesrule), [CSSKeyframeRule](#csskeyframerule), [CSSComputedStyleProperty](#csscomputedstyleproperty), [CSSStyleSheetHeader](#cssstylesheetheader)</span></span> |
| [**<span data-ttu-id="c7a83-120">依存関係</span><span class="sxs-lookup"><span data-stu-id="c7a83-120">Dependencies</span></span>**](#dependencies) | [<span data-ttu-id="c7a83-121">DOM</span><span class="sxs-lookup"><span data-stu-id="c7a83-121">DOM</span></span>](dom.md) |
## <span data-ttu-id="c7a83-122">メソッド</span><span class="sxs-lookup"><span data-stu-id="c7a83-122">Methods</span></span>

### <span data-ttu-id="c7a83-123">[有効]</span><span class="sxs-lookup"><span data-stu-id="c7a83-123">enable</span></span>
<span data-ttu-id="c7a83-124">指定されたページの CSS エージェントを有効にする。</span><span class="sxs-lookup"><span data-stu-id="c7a83-124">Enables the CSS agent for the given page.</span></span> <span data-ttu-id="c7a83-125">クライアントは、このコマンドの結果を受け取るまで CSS エージェントが有効になっていると想定していけずに使用します。</span><span class="sxs-lookup"><span data-stu-id="c7a83-125">Clients should not assume that the CSS agent has been enabled until the result of this command is received.</span></span>

</p>

---

### <span data-ttu-id="c7a83-126">[無効]</span><span class="sxs-lookup"><span data-stu-id="c7a83-126">disable</span></span>
<span data-ttu-id="c7a83-127">指定されたページの CSS エージェントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c7a83-127">Disables the CSS agent for the given page.</span></span>

</p>

---

### <span data-ttu-id="c7a83-128">getInlineStylesForNode</span><span class="sxs-lookup"><span data-stu-id="c7a83-128">getInlineStylesForNode</span></span>
<span data-ttu-id="c7a83-129">(明示的に "style" 属性で暗黙的に、DOM 属性を使用して) で識別される DOM ノードに対してインラインで定義されたスタイルを返します `nodeId` 。</span><span class="sxs-lookup"><span data-stu-id="c7a83-129">Returns the styles defined inline (explicitly in the "style" attribute and implicitly, using DOM attributes) for a DOM node identified by `nodeId`.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-130">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c7a83-130">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-131">nodeId</span><span class="sxs-lookup"><span data-stu-id="c7a83-131">nodeId</span></span></td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-132">戻り値</span><span class="sxs-lookup"><span data-stu-id="c7a83-132">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-133">inlineStyle</span><span class="sxs-lookup"><span data-stu-id="c7a83-133">inlineStyle</span></span> <br /> <i><span data-ttu-id="c7a83-134">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-134">optional</span></span></i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="c7a83-135">指定された DOM ノードのインライン スタイル。</span><span class="sxs-lookup"><span data-stu-id="c7a83-135">Inline style for the specified DOM node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-136">attributesStyle</span><span class="sxs-lookup"><span data-stu-id="c7a83-136">attributesStyle</span></span> <br /> <i><span data-ttu-id="c7a83-137">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-137">optional</span></span></i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="c7a83-138">属性定義要素スタイル (例: "width=20 height=100%" の結果)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-138">Attribute-defined element style (e.g. resulting from "width=20 height=100%").</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="c7a83-139">getMatchedStylesForNode</span><span class="sxs-lookup"><span data-stu-id="c7a83-139">getMatchedStylesForNode</span></span>
<span data-ttu-id="c7a83-140">で識別される DOM ノードに対して要求されたスタイルを返します `nodeId` 。</span><span class="sxs-lookup"><span data-stu-id="c7a83-140">Returns requested styles for a DOM node identified by `nodeId`.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-141">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c7a83-141">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-142">nodeId</span><span class="sxs-lookup"><span data-stu-id="c7a83-142">nodeId</span></span></td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-143">戻り値</span><span class="sxs-lookup"><span data-stu-id="c7a83-143">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-144">inlineStyle</span><span class="sxs-lookup"><span data-stu-id="c7a83-144">inlineStyle</span></span> <br /> <i><span data-ttu-id="c7a83-145">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-145">optional</span></span></i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="c7a83-146">指定された DOM ノードのインライン スタイル。</span><span class="sxs-lookup"><span data-stu-id="c7a83-146">Inline style for the specified DOM node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-147">attributesStyle</span><span class="sxs-lookup"><span data-stu-id="c7a83-147">attributesStyle</span></span> <br /> <i><span data-ttu-id="c7a83-148">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-148">optional</span></span></i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="c7a83-149">属性定義要素スタイル (例: "width=20 height=100%" の結果)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-149">Attribute-defined element style (e.g. resulting from "width=20 height=100%").</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-150">matchedCSSRules</span><span class="sxs-lookup"><span data-stu-id="c7a83-150">matchedCSSRules</span></span> <br /> <i><span data-ttu-id="c7a83-151">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-151">optional</span></span></i></td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td><span data-ttu-id="c7a83-152">該当するすべてのスタイルシートから、このノードに一致する CSS ルール。</span><span class="sxs-lookup"><span data-stu-id="c7a83-152">CSS rules matching this node, from all applicable stylesheets.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-153">pseudoElements</span><span class="sxs-lookup"><span data-stu-id="c7a83-153">pseudoElements</span></span> <br /> <i><span data-ttu-id="c7a83-154">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-154">optional</span></span></i></td>
            <td><a href="#pseudoelementmatches"><code class="flyout">PseudoElementMatches[]</code></a></td>
            <td><span data-ttu-id="c7a83-155">このノードに一致する擬似スタイル。</span><span class="sxs-lookup"><span data-stu-id="c7a83-155">Pseudo style matches for this node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-156">inherited</span><span class="sxs-lookup"><span data-stu-id="c7a83-156">inherited</span></span> <br /> <i><span data-ttu-id="c7a83-157">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-157">optional</span></span></i></td>
            <td><a href="#inheritedstyleentry"><code class="flyout">InheritedStyleEntry[]</code></a></td>
            <td><span data-ttu-id="c7a83-158">継承されたスタイルのチェーン (即時ノードの親から DOM ツリー ルートまで)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-158">A chain of inherited styles (from the immediate node parent up to the DOM tree root).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-159">cssKeyframesRules</span><span class="sxs-lookup"><span data-stu-id="c7a83-159">cssKeyframesRules</span></span> <br /> <i><span data-ttu-id="c7a83-160">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-160">optional</span></span></i></td>
            <td><a href="#csskeyframesrule"><code class="flyout">CSSKeyframesRule[]</code></a></td>
            <td><span data-ttu-id="c7a83-161">このノードに一致する CSS キーフレーム アニメーションのリスト。</span><span class="sxs-lookup"><span data-stu-id="c7a83-161">A list of CSS keyframed animations matching this node.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="c7a83-162">getPlatformFontsForNode</span><span class="sxs-lookup"><span data-stu-id="c7a83-162">getPlatformFontsForNode</span></span>
<span data-ttu-id="c7a83-163">指定されたノードで子 TextNodes をレンダリングするために使用したプラットフォーム フォントに関する情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="c7a83-163">Requests information about platform fonts which we used to render child TextNodes in the given node.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-164">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c7a83-164">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-165">nodeId</span><span class="sxs-lookup"><span data-stu-id="c7a83-165">nodeId</span></span></td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-166">戻り値</span><span class="sxs-lookup"><span data-stu-id="c7a83-166">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-167">fonts</span><span class="sxs-lookup"><span data-stu-id="c7a83-167">fonts</span></span></td>
            <td><a href="#platformfontusage"><code class="flyout">PlatformFontUsage[]</code></a></td>
            <td><span data-ttu-id="c7a83-168">使用しているすべてのプラットフォーム フォントの使用状況の統計。</span><span class="sxs-lookup"><span data-stu-id="c7a83-168">Usage statistics for every employed platform font.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="c7a83-169">getComputedStyleForNode</span><span class="sxs-lookup"><span data-stu-id="c7a83-169">getComputedStyleForNode</span></span>
<span data-ttu-id="c7a83-170">で識別される DOM ノードの計算されたスタイルを返します `nodeId` 。</span><span class="sxs-lookup"><span data-stu-id="c7a83-170">Returns the computed style for a DOM node identified by `nodeId`.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-171">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c7a83-171">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-172">nodeId</span><span class="sxs-lookup"><span data-stu-id="c7a83-172">nodeId</span></span></td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-173">戻り値</span><span class="sxs-lookup"><span data-stu-id="c7a83-173">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-174">computedStyle</span><span class="sxs-lookup"><span data-stu-id="c7a83-174">computedStyle</span></span></td>
            <td><a href="#csscomputedstyleproperty"><code class="flyout">CSSComputedStyleProperty[]</code></a></td>
            <td><span data-ttu-id="c7a83-175">指定された DOM ノードの計算されたスタイル。</span><span class="sxs-lookup"><span data-stu-id="c7a83-175">Computed style for the specified DOM node.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="c7a83-176">イベント</span><span class="sxs-lookup"><span data-stu-id="c7a83-176">Events</span></span>

### <span data-ttu-id="c7a83-177">styleSheetAdded</span><span class="sxs-lookup"><span data-stu-id="c7a83-177">styleSheetAdded</span></span>
<span data-ttu-id="c7a83-178">アクティブなドキュメント スタイルシートが追加されるたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="c7a83-178">Fired whenever an active document stylesheet is added.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-179">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c7a83-179">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-180">header</span><span class="sxs-lookup"><span data-stu-id="c7a83-180">header</span></span></td>
            <td><a href="#cssstylesheetheader"><code class="flyout">CSSStyleSheetHeader</code></a></td>
            <td><span data-ttu-id="c7a83-181">スタイルシートメタ情報を追加しました。</span><span class="sxs-lookup"><span data-stu-id="c7a83-181">Added stylesheet metainfo.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="c7a83-182">styleSheetChanged</span><span class="sxs-lookup"><span data-stu-id="c7a83-182">styleSheetChanged</span></span>
<span data-ttu-id="c7a83-183">クライアント操作の結果としてスタイルシートが変更されるたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="c7a83-183">Fired whenever a stylesheet is changed as a result of the client operation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-184">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c7a83-184">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-185">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="c7a83-185">styleSheetId</span></span></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="c7a83-186">styleSheetRemoved</span><span class="sxs-lookup"><span data-stu-id="c7a83-186">styleSheetRemoved</span></span>
<span data-ttu-id="c7a83-187">アクティブなドキュメント スタイルシートが削除されるたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="c7a83-187">Fired whenever an active document stylesheet is removed.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-188">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c7a83-188">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-189">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="c7a83-189">styleSheetId</span></span></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="c7a83-190">削除されたスタイルシートの識別子。</span><span class="sxs-lookup"><span data-stu-id="c7a83-190">Identifier of the removed stylesheet.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="c7a83-191">型</span><span class="sxs-lookup"><span data-stu-id="c7a83-191">Types</span></span>

### <a name="stylesheetid"></a> <span data-ttu-id="c7a83-192">StyleSheetId</span><span class="sxs-lookup"><span data-stu-id="c7a83-192">StyleSheetId</span></span> `string`



</p>

---

### <a name="pseudoelementmatches"></a> <span data-ttu-id="c7a83-193">PseudoElementMatches</span><span class="sxs-lookup"><span data-stu-id="c7a83-193">PseudoElementMatches</span></span> `object`

<span data-ttu-id="c7a83-194">単一の擬似スタイルの CSS ルール コレクション。</span><span class="sxs-lookup"><span data-stu-id="c7a83-194">CSS rule collection for a single pseudo style.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-195">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c7a83-195">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-196">pseudoType</span><span class="sxs-lookup"><span data-stu-id="c7a83-196">pseudoType</span></span></td>
            <td><a href="dom.md#pseudotype"><code class="flyout">DOM.PseudoType</code></a></td>
            <td><span data-ttu-id="c7a83-197">擬似要素型。</span><span class="sxs-lookup"><span data-stu-id="c7a83-197">Pseudo element type.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-198">matches</span><span class="sxs-lookup"><span data-stu-id="c7a83-198">matches</span></span></td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td><span data-ttu-id="c7a83-199">擬似スタイルに適用可能な CSS ルールの一致。</span><span class="sxs-lookup"><span data-stu-id="c7a83-199">Matches of CSS rules applicable to the pseudo style.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="inheritedstyleentry"></a> <span data-ttu-id="c7a83-200">InheritedStyleEntry</span><span class="sxs-lookup"><span data-stu-id="c7a83-200">InheritedStyleEntry</span></span> `object`

<span data-ttu-id="c7a83-201">先祖ノードから継承された CSS ルール コレクション。</span><span class="sxs-lookup"><span data-stu-id="c7a83-201">Inherited CSS rule collection from ancestor node.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-202">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c7a83-202">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-203">inlineStyle</span><span class="sxs-lookup"><span data-stu-id="c7a83-203">inlineStyle</span></span> <br /> <i><span data-ttu-id="c7a83-204">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-204">optional</span></span></i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="c7a83-205">スタイル継承チェーン内の先祖ノードのインライン スタイル (インライン スタイルがある場合)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-205">The ancestor node's inline style, if any, in the style inheritance chain.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-206">matchedCSSRules</span><span class="sxs-lookup"><span data-stu-id="c7a83-206">matchedCSSRules</span></span></td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td><span data-ttu-id="c7a83-207">スタイル継承チェーン内の先祖ノードと一致する CSS ルールの一致。</span><span class="sxs-lookup"><span data-stu-id="c7a83-207">Matches of CSS rules matching the ancestor node in the style inheritance chain.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="rulematch"></a> <span data-ttu-id="c7a83-208">RuleMatch</span><span class="sxs-lookup"><span data-stu-id="c7a83-208">RuleMatch</span></span> `object`

<span data-ttu-id="c7a83-209">CSS ルールのデータを一致します。</span><span class="sxs-lookup"><span data-stu-id="c7a83-209">Match data for a CSS rule.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-210">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c7a83-210">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-211">rule</span><span class="sxs-lookup"><span data-stu-id="c7a83-211">rule</span></span></td>
            <td><a href="#cssrule"><code class="flyout">CSSRule</code></a></td>
            <td><span data-ttu-id="c7a83-212">一致する CSS ルール。</span><span class="sxs-lookup"><span data-stu-id="c7a83-212">CSS rule in the match.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="value"></a> <span data-ttu-id="c7a83-213">設定値</span><span class="sxs-lookup"><span data-stu-id="c7a83-213">Value</span></span> `object`

<span data-ttu-id="c7a83-214">単純なセレクターのデータ (セレクター リストではコンマで区切られます)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-214">Data for a simple selector (these are delimited by commas in a selector list).</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-215">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c7a83-215">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-216">テキスト</span><span class="sxs-lookup"><span data-stu-id="c7a83-216">text</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="c7a83-217">値のテキスト。</span><span class="sxs-lookup"><span data-stu-id="c7a83-217">Value text.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-218">range</span><span class="sxs-lookup"><span data-stu-id="c7a83-218">range</span></span> <br /> <i><span data-ttu-id="c7a83-219">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-219">optional</span></span></i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td><span data-ttu-id="c7a83-220">基になるリソースの値の範囲 (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-220">Value range in the underlying resource (if available).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="selectorlist"></a> <span data-ttu-id="c7a83-221">SelectorList</span><span class="sxs-lookup"><span data-stu-id="c7a83-221">SelectorList</span></span> `object`

<span data-ttu-id="c7a83-222">リスト データの選択。</span><span class="sxs-lookup"><span data-stu-id="c7a83-222">Selector list data.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-223">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c7a83-223">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-224">セレクター</span><span class="sxs-lookup"><span data-stu-id="c7a83-224">selectors</span></span></td>
            <td><a href="#value"><code class="flyout">Value[]</code></a></td>
            <td><span data-ttu-id="c7a83-225">リスト内のセレクター。</span><span class="sxs-lookup"><span data-stu-id="c7a83-225">Selectors in the list.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-226">テキスト</span><span class="sxs-lookup"><span data-stu-id="c7a83-226">text</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="c7a83-227">ルール選択テキスト。</span><span class="sxs-lookup"><span data-stu-id="c7a83-227">Rule selector text.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssrule"></a> <span data-ttu-id="c7a83-228">CSSRule</span><span class="sxs-lookup"><span data-stu-id="c7a83-228">CSSRule</span></span> `object`

<span data-ttu-id="c7a83-229">CSS ルール表現。</span><span class="sxs-lookup"><span data-stu-id="c7a83-229">CSS rule representation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-230">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c7a83-230">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-231">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="c7a83-231">styleSheetId</span></span> <br /> <i><span data-ttu-id="c7a83-232">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-232">optional</span></span></i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="c7a83-233">このルールの基となる CSS スタイル シート識別子 (ユーザー エージェント スタイルシートおよびユーザー指定のスタイルシート ルールの場合は指定しません)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-233">The css style sheet identifier (absent for user agent stylesheet and user-specified stylesheet rules) this rule came from.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-234">selectorList</span><span class="sxs-lookup"><span data-stu-id="c7a83-234">selectorList</span></span> <br /> <i><span data-ttu-id="c7a83-235">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-235">optional</span></span></i></td>
            <td><a href="#selectorlist"><code class="flyout">SelectorList</code></a></td>
            <td><span data-ttu-id="c7a83-236">ルールセレクター データ。</span><span class="sxs-lookup"><span data-stu-id="c7a83-236">Rule selector data.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-237">origin</span><span class="sxs-lookup"><span data-stu-id="c7a83-237">origin</span></span> <br /> <i><span data-ttu-id="c7a83-238">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-238">optional</span></span></i></td>
            <td><<!--  <a href="#stylesheetorigin">  --><code class="flyout">StyleSheetOrigin</code><!--  </a>  --></td>
            <td><span data-ttu-id="c7a83-239">親スタイルシートの原点。</span><span class="sxs-lookup"><span data-stu-id="c7a83-239">Parent stylesheet's origin.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-240">style</span><span class="sxs-lookup"><span data-stu-id="c7a83-240">style</span></span></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="c7a83-241">関連付けられたスタイル宣言。</span><span class="sxs-lookup"><span data-stu-id="c7a83-241">Associated style declaration.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-242">メディア</span><span class="sxs-lookup"><span data-stu-id="c7a83-242">media</span></span> <br /> <i><span data-ttu-id="c7a83-243">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-243">optional</span></span></i></td>
            <td><a href="#cssmedia"><code class="flyout">CSSMedia[]</code></a></td>
            <td><span data-ttu-id="c7a83-244">メディア リスト配列 (メディア クエリが関係するルールの場合)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-244">Media list array (for rules involving media queries).</span></span> <span data-ttu-id="c7a83-245">配列は、最も内側から外側に向かってメディア クエリを列挙します。</span><span class="sxs-lookup"><span data-stu-id="c7a83-245">The array enumerates media queries starting with the innermost one, going outwards.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="sourcerange"></a> <span data-ttu-id="c7a83-246">SourceRange</span><span class="sxs-lookup"><span data-stu-id="c7a83-246">SourceRange</span></span> `object`

<span data-ttu-id="c7a83-247">リソース内のテキスト範囲。</span><span class="sxs-lookup"><span data-stu-id="c7a83-247">Text range within a resource.</span></span> <span data-ttu-id="c7a83-248">すべての数値は 0 から始ります。</span><span class="sxs-lookup"><span data-stu-id="c7a83-248">All numbers are zero-based.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-249">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c7a83-249">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-250">startLine</span><span class="sxs-lookup"><span data-stu-id="c7a83-250">startLine</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="c7a83-251">範囲の開始行。</span><span class="sxs-lookup"><span data-stu-id="c7a83-251">Start line of range.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-252">startColumn</span><span class="sxs-lookup"><span data-stu-id="c7a83-252">startColumn</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="c7a83-253">範囲の開始列 (含む)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-253">Start column of range (inclusive).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-254">endLine</span><span class="sxs-lookup"><span data-stu-id="c7a83-254">endLine</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="c7a83-255">範囲の終了行</span><span class="sxs-lookup"><span data-stu-id="c7a83-255">End line of range</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-256">endColumn</span><span class="sxs-lookup"><span data-stu-id="c7a83-256">endColumn</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="c7a83-257">範囲の終了列 (排他的)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-257">End column of range (exclusive).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="shorthandentry"></a> <span data-ttu-id="c7a83-258">ShorthandEntry</span><span class="sxs-lookup"><span data-stu-id="c7a83-258">ShorthandEntry</span></span> `object`



<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-259">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c7a83-259">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-260">name</span><span class="sxs-lookup"><span data-stu-id="c7a83-260">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="c7a83-261">名前を短くします。</span><span class="sxs-lookup"><span data-stu-id="c7a83-261">Shorthand name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-262">value</span><span class="sxs-lookup"><span data-stu-id="c7a83-262">value</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="c7a83-263">値を短くします。</span><span class="sxs-lookup"><span data-stu-id="c7a83-263">Shorthand value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-264">大事な</span><span class="sxs-lookup"><span data-stu-id="c7a83-264">important</span></span> <br /> <i><span data-ttu-id="c7a83-265">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-265">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="c7a83-266">プロパティが "!important" 注釈を持っているかどうか (存在しない `false` 場合を意味します)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-266">Whether the property has "!important" annotation (implies `false` if absent).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssstyle"></a> <span data-ttu-id="c7a83-267">CSSStyle</span><span class="sxs-lookup"><span data-stu-id="c7a83-267">CSSStyle</span></span> `object`

<span data-ttu-id="c7a83-268">CSS スタイル表現。</span><span class="sxs-lookup"><span data-stu-id="c7a83-268">CSS style representation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-269">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c7a83-269">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-270">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="c7a83-270">styleSheetId</span></span> <br /> <i><span data-ttu-id="c7a83-271">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-271">optional</span></span></i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="c7a83-272">このルールの基となる CSS スタイル シート識別子 (ユーザー エージェント スタイルシートおよびユーザー指定のスタイルシート ルールの場合は指定しません)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-272">The css style sheet identifier (absent for user agent stylesheet and user-specified stylesheet rules) this rule came from.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-273">cssProperties</span><span class="sxs-lookup"><span data-stu-id="c7a83-273">cssProperties</span></span></td>
            <td><a href="#cssproperty"><code class="flyout">CSSProperty[]</code></a></td>
            <td><span data-ttu-id="c7a83-274">スタイル内の CSS プロパティ。</span><span class="sxs-lookup"><span data-stu-id="c7a83-274">CSS properties in the style.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-275">shorthandEntries</span><span class="sxs-lookup"><span data-stu-id="c7a83-275">shorthandEntries</span></span></td>
            <td><a href="#shorthandentry"><code class="flyout">ShorthandEntry[]</code></a></td>
            <td><span data-ttu-id="c7a83-276">スタイルで見つかったすべての短い手の計算値。</span><span class="sxs-lookup"><span data-stu-id="c7a83-276">Computed values for all shorthands found in the style.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-277">cssText</span><span class="sxs-lookup"><span data-stu-id="c7a83-277">cssText</span></span> <br /> <i><span data-ttu-id="c7a83-278">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-278">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="c7a83-279">スタイル宣言テキスト (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-279">Style declaration text (if available).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-280">range</span><span class="sxs-lookup"><span data-stu-id="c7a83-280">range</span></span> <br /> <i><span data-ttu-id="c7a83-281">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-281">optional</span></span></i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td><span data-ttu-id="c7a83-282">囲まれたスタイルシート内のスタイル宣言範囲 (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-282">Style declaration range in the enclosing stylesheet (if available).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssproperty"></a> <span data-ttu-id="c7a83-283">CSSProperty</span><span class="sxs-lookup"><span data-stu-id="c7a83-283">CSSProperty</span></span> `object`

<span data-ttu-id="c7a83-284">CSS プロパティ宣言データ。</span><span class="sxs-lookup"><span data-stu-id="c7a83-284">CSS property declaration data.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-285">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c7a83-285">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-286">name</span><span class="sxs-lookup"><span data-stu-id="c7a83-286">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="c7a83-287">プロパティ名。</span><span class="sxs-lookup"><span data-stu-id="c7a83-287">The property name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-288">value</span><span class="sxs-lookup"><span data-stu-id="c7a83-288">value</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="c7a83-289">プロパティ値。</span><span class="sxs-lookup"><span data-stu-id="c7a83-289">The property value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-290">大事な</span><span class="sxs-lookup"><span data-stu-id="c7a83-290">important</span></span> <br /> <i><span data-ttu-id="c7a83-291">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-291">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="c7a83-292">プロパティが "!important" 注釈を持っているかどうか (存在しない `false` 場合を意味します)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-292">Whether the property has "!important" annotation (implies `false` if absent).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-293">暗黙的</span><span class="sxs-lookup"><span data-stu-id="c7a83-293">implicit</span></span> <br /> <i><span data-ttu-id="c7a83-294">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-294">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="c7a83-295">プロパティが暗黙的かどうか (存在しない `false` 場合に意味します)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-295">Whether the property is implicit (implies `false` if absent).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-296">テキスト</span><span class="sxs-lookup"><span data-stu-id="c7a83-296">text</span></span> <br /> <i><span data-ttu-id="c7a83-297">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-297">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="c7a83-298">スタイルで指定されたフル プロパティ テキスト。</span><span class="sxs-lookup"><span data-stu-id="c7a83-298">The full property text as specified in the style.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-299">parsedOk</span><span class="sxs-lookup"><span data-stu-id="c7a83-299">parsedOk</span></span> <br /> <i><span data-ttu-id="c7a83-300">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-300">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="c7a83-301">ブラウザーによってプロパティが理解されるかどうか (存在しない場合 `true` を意味します)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-301">Whether the property is understood by the browser (implies `true` if absent).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-302">disabled</span><span class="sxs-lookup"><span data-stu-id="c7a83-302">disabled</span></span> <br /> <i><span data-ttu-id="c7a83-303">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-303">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="c7a83-304">ユーザーがプロパティを無効にするかどうかを指定します (ソース ベースのプロパティの場合のみ)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-304">Whether the property is disabled by the user (present for source-based properties only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-305">range</span><span class="sxs-lookup"><span data-stu-id="c7a83-305">range</span></span> <br /> <i><span data-ttu-id="c7a83-306">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-306">optional</span></span></i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td><span data-ttu-id="c7a83-307">囲むスタイル宣言のプロパティ範囲全体 (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-307">The entire property range in the enclosing style declaration (if available).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssmedia"></a> <span data-ttu-id="c7a83-308">CSSMedia</span><span class="sxs-lookup"><span data-stu-id="c7a83-308">CSSMedia</span></span> `object`

<span data-ttu-id="c7a83-309">CSS メディア ルール記述子。</span><span class="sxs-lookup"><span data-stu-id="c7a83-309">CSS media rule descriptor.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-310">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c7a83-310">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-311">テキスト</span><span class="sxs-lookup"><span data-stu-id="c7a83-311">text</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="c7a83-312">メディア クエリ テキスト。</span><span class="sxs-lookup"><span data-stu-id="c7a83-312">Media query text.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-313">source</span><span class="sxs-lookup"><span data-stu-id="c7a83-313">source</span></span></td>
            <td><code class="flyout">string</code> <br /> <i><span data-ttu-id="c7a83-314">有効な値: mediaRule、importRule、linkedSheet、inlineSheet</span><span class="sxs-lookup"><span data-stu-id="c7a83-314">Allowed values: mediaRule, importRule, linkedSheet, inlineSheet</span></span></i></td>
            <td><span data-ttu-id="c7a83-315">メディア クエリのソース: @media ルールで指定されている場合は "mediaRule"、@import ルールで指定されている場合は "importRule"、リンクされたスタイルシートの LINK タグの "media" 属性で指定する場合は "linkedSheet"、インライン スタイルシートの STYLE タグの "media" 属性で指定した場合は "inlineSheet" です。</span><span class="sxs-lookup"><span data-stu-id="c7a83-315">Source of the media query: "mediaRule" if specified by a @media rule, "importRule" if specified by an @import rule, "linkedSheet" if specified by a "media" attribute in a linked stylesheet's LINK tag, "inlineSheet" if specified by a "media" attribute in an inline stylesheet's STYLE tag.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-316">sourceURL</span><span class="sxs-lookup"><span data-stu-id="c7a83-316">sourceURL</span></span> <br /> <i><span data-ttu-id="c7a83-317">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-317">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="c7a83-318">メディア クエリの説明を含むドキュメントの URL。</span><span class="sxs-lookup"><span data-stu-id="c7a83-318">URL of the document containing the media query description.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-319">range</span><span class="sxs-lookup"><span data-stu-id="c7a83-319">range</span></span> <br /> <i><span data-ttu-id="c7a83-320">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-320">optional</span></span></i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td><span data-ttu-id="c7a83-321">関連付けられたルール (@media または @import) ヘッダー範囲 (使用可能な場合)</span><span class="sxs-lookup"><span data-stu-id="c7a83-321">The associated rule (@media or @import) header range in the enclosing stylesheet (if available).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-322">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="c7a83-322">styleSheetId</span></span> <br /> <i><span data-ttu-id="c7a83-323">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-323">optional</span></span></i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="c7a83-324">このオブジェクトを含むスタイルシートの識別子 (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-324">Identifier of the stylesheet containing this object (if exists).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-325">mediaList</span><span class="sxs-lookup"><span data-stu-id="c7a83-325">mediaList</span></span> <br /> <i><span data-ttu-id="c7a83-326">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-326">optional</span></span></i></td>
            <td><a href="#mediaquery"><code class="flyout">MediaQuery[]</code></a></td>
            <td><span data-ttu-id="c7a83-327">メディア クエリの配列。</span><span class="sxs-lookup"><span data-stu-id="c7a83-327">Array of media queries.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="mediaquery"></a> <span data-ttu-id="c7a83-328">MediaQuery</span><span class="sxs-lookup"><span data-stu-id="c7a83-328">MediaQuery</span></span> `object`

<span data-ttu-id="c7a83-329">メディア クエリ記述子。</span><span class="sxs-lookup"><span data-stu-id="c7a83-329">Media query descriptor.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-330">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c7a83-330">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-331">式</span><span class="sxs-lookup"><span data-stu-id="c7a83-331">expressions</span></span></td>
            <td><a href="#mediaqueryexpression"><code class="flyout">MediaQueryExpression[]</code></a></td>
            <td><span data-ttu-id="c7a83-332">メディア クエリ式の配列。</span><span class="sxs-lookup"><span data-stu-id="c7a83-332">Array of media query expressions.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-333">active</span><span class="sxs-lookup"><span data-stu-id="c7a83-333">active</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="c7a83-334">メディア クエリ条件が満たされているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c7a83-334">Whether the media query condition is satisfied.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="mediaqueryexpression"></a> <span data-ttu-id="c7a83-335">MediaQueryExpression</span><span class="sxs-lookup"><span data-stu-id="c7a83-335">MediaQueryExpression</span></span> `object`

<span data-ttu-id="c7a83-336">メディア クエリ式記述子。</span><span class="sxs-lookup"><span data-stu-id="c7a83-336">Media query expression descriptor.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-337">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c7a83-337">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-338">value</span><span class="sxs-lookup"><span data-stu-id="c7a83-338">value</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="c7a83-339">メディア クエリ式の値。</span><span class="sxs-lookup"><span data-stu-id="c7a83-339">Media query expression value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-340">unit</span><span class="sxs-lookup"><span data-stu-id="c7a83-340">unit</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="c7a83-341">メディア クエリ式の単位。</span><span class="sxs-lookup"><span data-stu-id="c7a83-341">Media query expression units.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-342">機能</span><span class="sxs-lookup"><span data-stu-id="c7a83-342">feature</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="c7a83-343">メディア クエリ式機能。</span><span class="sxs-lookup"><span data-stu-id="c7a83-343">Media query expression feature.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-344">valueRange</span><span class="sxs-lookup"><span data-stu-id="c7a83-344">valueRange</span></span> <br /> <i><span data-ttu-id="c7a83-345">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-345">optional</span></span></i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td><span data-ttu-id="c7a83-346">囲むスタイルシート内の値テキストの関連付けられた範囲 (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-346">The associated range of the value text in the enclosing stylesheet (if available).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-347">computedLength</span><span class="sxs-lookup"><span data-stu-id="c7a83-347">computedLength</span></span> <br /> <i><span data-ttu-id="c7a83-348">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-348">optional</span></span></i></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="c7a83-349">メディア クエリ式の計算された長さ (該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-349">Computed length of media query expression (if applicable).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="platformfontusage"></a> <span data-ttu-id="c7a83-350">PlatformFontUsage</span><span class="sxs-lookup"><span data-stu-id="c7a83-350">PlatformFontUsage</span></span> `object`

<span data-ttu-id="c7a83-351">指定されたフォントでレンダリングされたグリフの量に関する情報。</span><span class="sxs-lookup"><span data-stu-id="c7a83-351">Information about amount of glyphs that were rendered with given font.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-352">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c7a83-352">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-353">familyName</span><span class="sxs-lookup"><span data-stu-id="c7a83-353">familyName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="c7a83-354">プラットフォームによって報告されるフォントのファミリ名。</span><span class="sxs-lookup"><span data-stu-id="c7a83-354">Font's family name reported by platform.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-355">isCustomFont</span><span class="sxs-lookup"><span data-stu-id="c7a83-355">isCustomFont</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="c7a83-356">フォントがローカルでダウンロードまたは解決されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c7a83-356">Indicates if the font was downloaded or resolved locally.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-357">glyphCount</span><span class="sxs-lookup"><span data-stu-id="c7a83-357">glyphCount</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="c7a83-358">このフォントでレンダリングされたグリフの量。</span><span class="sxs-lookup"><span data-stu-id="c7a83-358">Amount of glyphs that were rendered with this font.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="csskeyframesrule"></a> <span data-ttu-id="c7a83-359">CSSKeyframesRule</span><span class="sxs-lookup"><span data-stu-id="c7a83-359">CSSKeyframesRule</span></span> `object`

<span data-ttu-id="c7a83-360">CSS キーフレーム ルール表現。</span><span class="sxs-lookup"><span data-stu-id="c7a83-360">CSS keyframes rule representation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-361">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c7a83-361">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-362">animationName</span><span class="sxs-lookup"><span data-stu-id="c7a83-362">animationName</span></span></td>
            <td><a href="#value"><code class="flyout">Value</code></a></td>
            <td><span data-ttu-id="c7a83-363">アニメーション名。</span><span class="sxs-lookup"><span data-stu-id="c7a83-363">Animation name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-364">keyframes</span><span class="sxs-lookup"><span data-stu-id="c7a83-364">keyframes</span></span></td>
            <td><a href="#csskeyframerule"><code class="flyout">CSSKeyframeRule[]</code></a></td>
            <td><span data-ttu-id="c7a83-365">キー フレームの一覧。</span><span class="sxs-lookup"><span data-stu-id="c7a83-365">List of keyframes.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="csskeyframerule"></a> <span data-ttu-id="c7a83-366">CSSKeyframeRule</span><span class="sxs-lookup"><span data-stu-id="c7a83-366">CSSKeyframeRule</span></span> `object`

<span data-ttu-id="c7a83-367">CSS キーフレーム ルール表現。</span><span class="sxs-lookup"><span data-stu-id="c7a83-367">CSS keyframe rule representation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-368">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c7a83-368">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-369">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="c7a83-369">styleSheetId</span></span> <br /> <i><span data-ttu-id="c7a83-370">オプション</span><span class="sxs-lookup"><span data-stu-id="c7a83-370">optional</span></span></i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="c7a83-371">このルールの基となる CSS スタイル シート識別子 (ユーザー エージェント スタイルシートおよびユーザー指定のスタイルシート ルールの場合は指定しません)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-371">The css style sheet identifier (absent for user agent stylesheet and user-specified stylesheet rules) this rule came from.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-372">origin</span><span class="sxs-lookup"><span data-stu-id="c7a83-372">origin</span></span></td>
            <td><!--  <a href="#stylesheetorigin">  --><code class="flyout">StyleSheetOrigin</code><!--  </a>  --></td>
            <td><span data-ttu-id="c7a83-373">親スタイルシートの原点。</span><span class="sxs-lookup"><span data-stu-id="c7a83-373">Parent stylesheet's origin.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-374">keyText</span><span class="sxs-lookup"><span data-stu-id="c7a83-374">keyText</span></span></td>
            <td><a href="#value"><code class="flyout">Value</code></a></td>
            <td><span data-ttu-id="c7a83-375">関連付けられたキー テキスト。</span><span class="sxs-lookup"><span data-stu-id="c7a83-375">Associated key text.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-376">style</span><span class="sxs-lookup"><span data-stu-id="c7a83-376">style</span></span></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td><span data-ttu-id="c7a83-377">関連付けられたスタイル宣言。</span><span class="sxs-lookup"><span data-stu-id="c7a83-377">Associated style declaration.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="csscomputedstyleproperty"></a> <span data-ttu-id="c7a83-378">CSSComputedStyleProperty</span><span class="sxs-lookup"><span data-stu-id="c7a83-378">CSSComputedStyleProperty</span></span> `object`



<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-379">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c7a83-379">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-380">name</span><span class="sxs-lookup"><span data-stu-id="c7a83-380">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="c7a83-381">計算されたスタイルのプロパティ名。</span><span class="sxs-lookup"><span data-stu-id="c7a83-381">Computed style property name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-382">value</span><span class="sxs-lookup"><span data-stu-id="c7a83-382">value</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="c7a83-383">計算されたスタイルのプロパティ値。</span><span class="sxs-lookup"><span data-stu-id="c7a83-383">Computed style property value.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssstylesheetheader"></a> <span data-ttu-id="c7a83-384">CSSStyleSheetHeader</span><span class="sxs-lookup"><span data-stu-id="c7a83-384">CSSStyleSheetHeader</span></span> `object`

<span data-ttu-id="c7a83-385">CSS スタイルシートメタインフォーム。</span><span class="sxs-lookup"><span data-stu-id="c7a83-385">CSS stylesheet metainformation.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c7a83-386">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c7a83-386">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c7a83-387">styleSheetId</span><span class="sxs-lookup"><span data-stu-id="c7a83-387">styleSheetId</span></span></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td><span data-ttu-id="c7a83-388">スタイルシート識別子。</span><span class="sxs-lookup"><span data-stu-id="c7a83-388">The stylesheet identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-389">sourceURL</span><span class="sxs-lookup"><span data-stu-id="c7a83-389">sourceURL</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="c7a83-390">スタイルシート リソースの URL。</span><span class="sxs-lookup"><span data-stu-id="c7a83-390">Stylesheet resource URL.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-391">disabled</span><span class="sxs-lookup"><span data-stu-id="c7a83-391">disabled</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="c7a83-392">スタイルシートが無効になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c7a83-392">Denotes whether the stylesheet is disabled.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-393">isInline</span><span class="sxs-lookup"><span data-stu-id="c7a83-393">isInline</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="c7a83-394">このスタイルシートがパーサーによって STYLE タグに対して作成されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="c7a83-394">Whether this stylesheet is created for STYLE tag by parser.</span></span> <span data-ttu-id="c7a83-395">このフラグは、document.written STYLE タグには設定できません。</span><span class="sxs-lookup"><span data-stu-id="c7a83-395">This flag is not set for document.written STYLE tags.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-396">startLine</span><span class="sxs-lookup"><span data-stu-id="c7a83-396">startLine</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="c7a83-397">リソース内のスタイルシートの行オフセット (ゼロベース)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-397">Line offset of the stylesheet within the resource (zero based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-398">startColumn</span><span class="sxs-lookup"><span data-stu-id="c7a83-398">startColumn</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="c7a83-399">リソース内のスタイルシートの列オフセット (ゼロベース)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-399">Column offset of the stylesheet within the resource (zero based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c7a83-400">length</span><span class="sxs-lookup"><span data-stu-id="c7a83-400">length</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="c7a83-401">コンテンツのサイズ (文字)。</span><span class="sxs-lookup"><span data-stu-id="c7a83-401">Size of the content (in characters).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="c7a83-402">依存関係</span><span class="sxs-lookup"><span data-stu-id="c7a83-402">Dependencies</span></span>

[<span data-ttu-id="c7a83-403">DOM</span><span class="sxs-lookup"><span data-stu-id="c7a83-403">DOM</span></span>](dom.md)
