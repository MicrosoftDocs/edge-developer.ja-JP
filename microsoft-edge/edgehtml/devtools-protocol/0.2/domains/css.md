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
# CSS

このドメインは、CSS の読み取り/書き込み操作を公開します。 すべての CSS オブジェクト (スタイルシート、ルール、およびスタイル) は、関連するオブジェクトに対する後続の操作で使用 `id` されます。 各オブジェクトの種類は、特定の構造を持ち、異なる種類の `id` オブジェクト間で互換性を持つものではありません。 CSS オブジェクトは、呼び出し (DOM ノード ID を受 `get*ForNode()` け入れる) を使用して読み込まれます。 クライアントは、イベントを介してスタイルシートを追跡し、メソッドを使用して必要なスタイルシートの `styleSheetAdded` / `styleSheetRemoved` コンテンツを読み `getStyleSheet[Text]()` 込むすることもできます。

| | |
|-|-|
| [**メソッド**](#methods) | [enable](#enable)、 [disable](#disable)、 [getInlineStylesForNode](#getinlinestylesfornode)、 [getMatchedStylesForNode](#getmatchedstylesfornode)、 [getPlatformFontsForNode](#getplatformfontsfornode)、 [getComputedStyleForNode](#getcomputedstylefornode) |
| [**イベント**](#events) | [styleSheetAdded](#stylesheetadded)、 [styleSheetChanged](#stylesheetchanged)、 [styleSheetRemoved](#stylesheetremoved) |
| [**型**](#types) | [StyleSheetId](#stylesheetid), [PseudoElementMatches](#pseudoelementmatches), [InheritedStyleEntry](#inheritedstyleentry), [RuleMatch](#rulematch), [Value](#value), [SelectorList](#selectorlist), [CSSRule](#cssrule), [SourceRange](#sourcerange), [ShorthandEntry](#shorthandentry), [CSSStyle](#cssstyle), [CSSProperty](#cssproperty), [CSSMedia](#cssmedia), MediaQuery , [MediaQueryExpression](#mediaqueryexpression), [PlatformFontUsage](#platformfontusage), [](#mediaquery) [CSSKeyframesRule](#csskeyframesrule), [CSSKeyframeRule](#csskeyframerule), [CSSComputedStyleProperty](#csscomputedstyleproperty), [CSSStyleSheetHeader](#cssstylesheetheader) |
| [**依存関係**](#dependencies) | [DOM](dom.md) |
## メソッド

### [有効]
指定されたページの CSS エージェントを有効にする。 クライアントは、このコマンドの結果を受け取るまで CSS エージェントが有効になっていると想定していけずに使用します。

</p>

---

### [無効]
指定されたページの CSS エージェントを無効にします。

</p>

---

### getInlineStylesForNode
(明示的に "style" 属性で暗黙的に、DOM 属性を使用して) で識別される DOM ノードに対してインラインで定義されたスタイルを返します `nodeId` 。

<table>
    <thead>
        <tr>
            <th>パラメーター</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>nodeId</td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>戻り値</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>inlineStyle <br /> <i>オプション</i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>指定された DOM ノードのインライン スタイル。</td>
        </tr>
        <tr>
            <td>attributesStyle <br /> <i>オプション</i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>属性定義要素スタイル (例: "width=20 height=100%" の結果)。</td>
        </tr>
    </tbody>
</table>
</p>

---

### getMatchedStylesForNode
で識別される DOM ノードに対して要求されたスタイルを返します `nodeId` 。

<table>
    <thead>
        <tr>
            <th>パラメーター</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>nodeId</td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>戻り値</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>inlineStyle <br /> <i>オプション</i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>指定された DOM ノードのインライン スタイル。</td>
        </tr>
        <tr>
            <td>attributesStyle <br /> <i>オプション</i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>属性定義要素スタイル (例: "width=20 height=100%" の結果)。</td>
        </tr>
        <tr>
            <td>matchedCSSRules <br /> <i>オプション</i></td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td>該当するすべてのスタイルシートから、このノードに一致する CSS ルール。</td>
        </tr>
        <tr>
            <td>pseudoElements <br /> <i>オプション</i></td>
            <td><a href="#pseudoelementmatches"><code class="flyout">PseudoElementMatches[]</code></a></td>
            <td>このノードに一致する擬似スタイル。</td>
        </tr>
        <tr>
            <td>inherited <br /> <i>オプション</i></td>
            <td><a href="#inheritedstyleentry"><code class="flyout">InheritedStyleEntry[]</code></a></td>
            <td>継承されたスタイルのチェーン (即時ノードの親から DOM ツリー ルートまで)。</td>
        </tr>
        <tr>
            <td>cssKeyframesRules <br /> <i>オプション</i></td>
            <td><a href="#csskeyframesrule"><code class="flyout">CSSKeyframesRule[]</code></a></td>
            <td>このノードに一致する CSS キーフレーム アニメーションのリスト。</td>
        </tr>
    </tbody>
</table>
</p>

---

### getPlatformFontsForNode
指定されたノードで子 TextNodes をレンダリングするために使用したプラットフォーム フォントに関する情報を要求します。

<table>
    <thead>
        <tr>
            <th>パラメーター</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>nodeId</td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>戻り値</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>fonts</td>
            <td><a href="#platformfontusage"><code class="flyout">PlatformFontUsage[]</code></a></td>
            <td>使用しているすべてのプラットフォーム フォントの使用状況の統計。</td>
        </tr>
    </tbody>
</table>
</p>

---

### getComputedStyleForNode
で識別される DOM ノードの計算されたスタイルを返します `nodeId` 。

<table>
    <thead>
        <tr>
            <th>パラメーター</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>nodeId</td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>戻り値</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>computedStyle</td>
            <td><a href="#csscomputedstyleproperty"><code class="flyout">CSSComputedStyleProperty[]</code></a></td>
            <td>指定された DOM ノードの計算されたスタイル。</td>
        </tr>
    </tbody>
</table>
</p>

---

## イベント

### styleSheetAdded
アクティブなドキュメント スタイルシートが追加されるたびに発生します。

<table>
    <thead>
        <tr>
            <th>パラメーター</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>header</td>
            <td><a href="#cssstylesheetheader"><code class="flyout">CSSStyleSheetHeader</code></a></td>
            <td>スタイルシートメタ情報を追加しました。</td>
        </tr>
    </tbody>
</table>
</p>

---

### styleSheetChanged
クライアント操作の結果としてスタイルシートが変更されるたびに発生します。

<table>
    <thead>
        <tr>
            <th>パラメーター</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>styleSheetId</td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
</p>

---

### styleSheetRemoved
アクティブなドキュメント スタイルシートが削除されるたびに発生します。

<table>
    <thead>
        <tr>
            <th>パラメーター</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>styleSheetId</td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td>削除されたスタイルシートの識別子。</td>
        </tr>
    </tbody>
</table>
</p>

---

## 型

### <a name="stylesheetid"></a> StyleSheetId `string`



</p>

---

### <a name="pseudoelementmatches"></a> PseudoElementMatches `object`

単一の擬似スタイルの CSS ルール コレクション。

<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>pseudoType</td>
            <td><a href="dom.md#pseudotype"><code class="flyout">DOM.PseudoType</code></a></td>
            <td>擬似要素型。</td>
        </tr>
        <tr>
            <td>matches</td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td>擬似スタイルに適用可能な CSS ルールの一致。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="inheritedstyleentry"></a> InheritedStyleEntry `object`

先祖ノードから継承された CSS ルール コレクション。

<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>inlineStyle <br /> <i>オプション</i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>スタイル継承チェーン内の先祖ノードのインライン スタイル (インライン スタイルがある場合)。</td>
        </tr>
        <tr>
            <td>matchedCSSRules</td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td>スタイル継承チェーン内の先祖ノードと一致する CSS ルールの一致。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="rulematch"></a> RuleMatch `object`

CSS ルールのデータを一致します。

<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>rule</td>
            <td><a href="#cssrule"><code class="flyout">CSSRule</code></a></td>
            <td>一致する CSS ルール。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="value"></a> 設定値 `object`

単純なセレクターのデータ (セレクター リストではコンマで区切られます)。

<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>テキスト</td>
            <td><code class="flyout">string</code></td>
            <td>値のテキスト。</td>
        </tr>
        <tr>
            <td>range <br /> <i>オプション</i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td>基になるリソースの値の範囲 (使用可能な場合)。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="selectorlist"></a> SelectorList `object`

リスト データの選択。

<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>セレクター</td>
            <td><a href="#value"><code class="flyout">Value[]</code></a></td>
            <td>リスト内のセレクター。</td>
        </tr>
        <tr>
            <td>テキスト</td>
            <td><code class="flyout">string</code></td>
            <td>ルール選択テキスト。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssrule"></a> CSSRule `object`

CSS ルール表現。

<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>styleSheetId <br /> <i>オプション</i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td>このルールの基となる CSS スタイル シート識別子 (ユーザー エージェント スタイルシートおよびユーザー指定のスタイルシート ルールの場合は指定しません)。</td>
        </tr>
        <tr>
            <td>selectorList <br /> <i>オプション</i></td>
            <td><a href="#selectorlist"><code class="flyout">SelectorList</code></a></td>
            <td>ルールセレクター データ。</td>
        </tr>
        <tr>
            <td>origin <br /> <i>オプション</i></td>
            <td><<!--  <a href="#stylesheetorigin">  --><code class="flyout">StyleSheetOrigin</code><!--  </a>  --></td>
            <td>親スタイルシートの原点。</td>
        </tr>
        <tr>
            <td>style</td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>関連付けられたスタイル宣言。</td>
        </tr>
        <tr>
            <td>メディア <br /> <i>オプション</i></td>
            <td><a href="#cssmedia"><code class="flyout">CSSMedia[]</code></a></td>
            <td>メディア リスト配列 (メディア クエリが関係するルールの場合)。 配列は、最も内側から外側に向かってメディア クエリを列挙します。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="sourcerange"></a> SourceRange `object`

リソース内のテキスト範囲。 すべての数値は 0 から始ります。

<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>startLine</td>
            <td><code class="flyout">integer</code></td>
            <td>範囲の開始行。</td>
        </tr>
        <tr>
            <td>startColumn</td>
            <td><code class="flyout">integer</code></td>
            <td>範囲の開始列 (含む)。</td>
        </tr>
        <tr>
            <td>endLine</td>
            <td><code class="flyout">integer</code></td>
            <td>範囲の終了行</td>
        </tr>
        <tr>
            <td>endColumn</td>
            <td><code class="flyout">integer</code></td>
            <td>範囲の終了列 (排他的)。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="shorthandentry"></a> ShorthandEntry `object`



<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>name</td>
            <td><code class="flyout">string</code></td>
            <td>名前を短くします。</td>
        </tr>
        <tr>
            <td>value</td>
            <td><code class="flyout">string</code></td>
            <td>値を短くします。</td>
        </tr>
        <tr>
            <td>大事な <br /> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>プロパティが "!important" 注釈を持っているかどうか (存在しない `false` 場合を意味します)。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssstyle"></a> CSSStyle `object`

CSS スタイル表現。

<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>styleSheetId <br /> <i>オプション</i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td>このルールの基となる CSS スタイル シート識別子 (ユーザー エージェント スタイルシートおよびユーザー指定のスタイルシート ルールの場合は指定しません)。</td>
        </tr>
        <tr>
            <td>cssProperties</td>
            <td><a href="#cssproperty"><code class="flyout">CSSProperty[]</code></a></td>
            <td>スタイル内の CSS プロパティ。</td>
        </tr>
        <tr>
            <td>shorthandEntries</td>
            <td><a href="#shorthandentry"><code class="flyout">ShorthandEntry[]</code></a></td>
            <td>スタイルで見つかったすべての短い手の計算値。</td>
        </tr>
        <tr>
            <td>cssText <br /> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>スタイル宣言テキスト (使用可能な場合)。</td>
        </tr>
        <tr>
            <td>range <br /> <i>オプション</i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td>囲まれたスタイルシート内のスタイル宣言範囲 (使用可能な場合)。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssproperty"></a> CSSProperty `object`

CSS プロパティ宣言データ。

<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>name</td>
            <td><code class="flyout">string</code></td>
            <td>プロパティ名。</td>
        </tr>
        <tr>
            <td>value</td>
            <td><code class="flyout">string</code></td>
            <td>プロパティ値。</td>
        </tr>
        <tr>
            <td>大事な <br /> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>プロパティが "!important" 注釈を持っているかどうか (存在しない `false` 場合を意味します)。</td>
        </tr>
        <tr>
            <td>暗黙的 <br /> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>プロパティが暗黙的かどうか (存在しない `false` 場合に意味します)。</td>
        </tr>
        <tr>
            <td>テキスト <br /> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>スタイルで指定されたフル プロパティ テキスト。</td>
        </tr>
        <tr>
            <td>parsedOk <br /> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>ブラウザーによってプロパティが理解されるかどうか (存在しない場合 `true` を意味します)。</td>
        </tr>
        <tr>
            <td>disabled <br /> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>ユーザーがプロパティを無効にするかどうかを指定します (ソース ベースのプロパティの場合のみ)。</td>
        </tr>
        <tr>
            <td>range <br /> <i>オプション</i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td>囲むスタイル宣言のプロパティ範囲全体 (使用可能な場合)。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssmedia"></a> CSSMedia `object`

CSS メディア ルール記述子。

<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>テキスト</td>
            <td><code class="flyout">string</code></td>
            <td>メディア クエリ テキスト。</td>
        </tr>
        <tr>
            <td>source</td>
            <td><code class="flyout">string</code> <br /> <i>有効な値: mediaRule、importRule、linkedSheet、inlineSheet</i></td>
            <td>メディア クエリのソース: @media ルールで指定されている場合は "mediaRule"、@import ルールで指定されている場合は "importRule"、リンクされたスタイルシートの LINK タグの "media" 属性で指定する場合は "linkedSheet"、インライン スタイルシートの STYLE タグの "media" 属性で指定した場合は "inlineSheet" です。</td>
        </tr>
        <tr>
            <td>sourceURL <br /> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>メディア クエリの説明を含むドキュメントの URL。</td>
        </tr>
        <tr>
            <td>range <br /> <i>オプション</i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td>関連付けられたルール (@media または @import) ヘッダー範囲 (使用可能な場合)</td>
        </tr>
        <tr>
            <td>styleSheetId <br /> <i>オプション</i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td>このオブジェクトを含むスタイルシートの識別子 (存在する場合)。</td>
        </tr>
        <tr>
            <td>mediaList <br /> <i>オプション</i></td>
            <td><a href="#mediaquery"><code class="flyout">MediaQuery[]</code></a></td>
            <td>メディア クエリの配列。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="mediaquery"></a> MediaQuery `object`

メディア クエリ記述子。

<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>式</td>
            <td><a href="#mediaqueryexpression"><code class="flyout">MediaQueryExpression[]</code></a></td>
            <td>メディア クエリ式の配列。</td>
        </tr>
        <tr>
            <td>active</td>
            <td><code class="flyout">boolean</code></td>
            <td>メディア クエリ条件が満たされているかどうかを示します。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="mediaqueryexpression"></a> MediaQueryExpression `object`

メディア クエリ式記述子。

<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>value</td>
            <td><code class="flyout">number</code></td>
            <td>メディア クエリ式の値。</td>
        </tr>
        <tr>
            <td>unit</td>
            <td><code class="flyout">string</code></td>
            <td>メディア クエリ式の単位。</td>
        </tr>
        <tr>
            <td>機能</td>
            <td><code class="flyout">string</code></td>
            <td>メディア クエリ式機能。</td>
        </tr>
        <tr>
            <td>valueRange <br /> <i>オプション</i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td>囲むスタイルシート内の値テキストの関連付けられた範囲 (使用可能な場合)。</td>
        </tr>
        <tr>
            <td>computedLength <br /> <i>オプション</i></td>
            <td><code class="flyout">number</code></td>
            <td>メディア クエリ式の計算された長さ (該当する場合)。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="platformfontusage"></a> PlatformFontUsage `object`

指定されたフォントでレンダリングされたグリフの量に関する情報。

<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>familyName</td>
            <td><code class="flyout">string</code></td>
            <td>プラットフォームによって報告されるフォントのファミリ名。</td>
        </tr>
        <tr>
            <td>isCustomFont</td>
            <td><code class="flyout">boolean</code></td>
            <td>フォントがローカルでダウンロードまたは解決されたかどうかを示します。</td>
        </tr>
        <tr>
            <td>glyphCount</td>
            <td><code class="flyout">number</code></td>
            <td>このフォントでレンダリングされたグリフの量。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="csskeyframesrule"></a> CSSKeyframesRule `object`

CSS キーフレーム ルール表現。

<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>animationName</td>
            <td><a href="#value"><code class="flyout">Value</code></a></td>
            <td>アニメーション名。</td>
        </tr>
        <tr>
            <td>keyframes</td>
            <td><a href="#csskeyframerule"><code class="flyout">CSSKeyframeRule[]</code></a></td>
            <td>キー フレームの一覧。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="csskeyframerule"></a> CSSKeyframeRule `object`

CSS キーフレーム ルール表現。

<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>styleSheetId <br /> <i>オプション</i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td>このルールの基となる CSS スタイル シート識別子 (ユーザー エージェント スタイルシートおよびユーザー指定のスタイルシート ルールの場合は指定しません)。</td>
        </tr>
        <tr>
            <td>origin</td>
            <td><!--  <a href="#stylesheetorigin">  --><code class="flyout">StyleSheetOrigin</code><!--  </a>  --></td>
            <td>親スタイルシートの原点。</td>
        </tr>
        <tr>
            <td>keyText</td>
            <td><a href="#value"><code class="flyout">Value</code></a></td>
            <td>関連付けられたキー テキスト。</td>
        </tr>
        <tr>
            <td>style</td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>関連付けられたスタイル宣言。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="csscomputedstyleproperty"></a> CSSComputedStyleProperty `object`



<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>name</td>
            <td><code class="flyout">string</code></td>
            <td>計算されたスタイルのプロパティ名。</td>
        </tr>
        <tr>
            <td>value</td>
            <td><code class="flyout">string</code></td>
            <td>計算されたスタイルのプロパティ値。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssstylesheetheader"></a> CSSStyleSheetHeader `object`

CSS スタイルシートメタインフォーム。

<table>
    <thead>
        <tr>
            <th>プロパティ</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>styleSheetId</td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td>スタイルシート識別子。</td>
        </tr>
        <tr>
            <td>sourceURL</td>
            <td><code class="flyout">string</code></td>
            <td>スタイルシート リソースの URL。</td>
        </tr>
        <tr>
            <td>disabled</td>
            <td><code class="flyout">boolean</code></td>
            <td>スタイルシートが無効になっているかどうかを示します。</td>
        </tr>
        <tr>
            <td>isInline</td>
            <td><code class="flyout">boolean</code></td>
            <td>このスタイルシートがパーサーによって STYLE タグに対して作成されるかどうか。 このフラグは、document.written STYLE タグには設定できません。</td>
        </tr>
        <tr>
            <td>startLine</td>
            <td><code class="flyout">number</code></td>
            <td>リソース内のスタイルシートの行オフセット (ゼロベース)。</td>
        </tr>
        <tr>
            <td>startColumn</td>
            <td><code class="flyout">number</code></td>
            <td>リソース内のスタイルシートの列オフセット (ゼロベース)。</td>
        </tr>
        <tr>
            <td>length</td>
            <td><code class="flyout">number</code></td>
            <td>コンテンツのサイズ (文字)。</td>
        </tr>
    </tbody>
</table>
</p>

---

## 依存関係

[DOM](dom.md)
