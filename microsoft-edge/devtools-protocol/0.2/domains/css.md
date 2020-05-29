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
# CSS
このドメインは CSS の読み取り/書き込み操作を公開します。 すべての CSS オブジェクト (スタイルシート、ルール、スタイル) には、 `id` 関連オブジェクトの後続の操作で使用される関連付けがあります。 各オブジェクト型には特定の構造体があり、 `id` さまざまな種類のオブジェクト間で相互に交換することはできません。 CSS オブジェクトは、 `get*ForNode()` 呼び出し (DOM ノード id を受け取る) を使って読み込むことができます。 クライアントは、イベントによってスタイル変更 `styleSheetAdded` / `styleSheetRemoved` を追跡し、そのメソッドを使って必要なスタイルシートの内容を読み込むこともでき `getStyleSheet[Text]()` ます。

| | |
|-|-|
| [**メソッド**](#methods) | [enable](#enable)、 [disable](#disable)、 [getInlineStylesForNode](#getinlinestylesfornode)、 [getmatched文法 fornode](#getmatchedstylesfornode)、 [getplatformの](#getplatformfontsfornode) [getComputedStyleForNode](#getcomputedstylefornode) |
| [**イベント**](#events) | [styleSheetAdded](#stylesheetadded)、 [styleSheetChanged](#stylesheetchanged)、 [styleSheetRemoved](#stylesheetremoved) |
| [**型**](#types) | [StyleSheetId](#stylesheetid)、[擬似要素一致](#pseudoelementmatches)、 [inherited entry](#inheritedstyleentry)、 [RuleMatch](#rulematch)、 [Value](#value)、 [SelectorList](#selectorlist)、 [CSSRule](#cssrule)、 [SourceRange、ShorthandEntry](#sourcerange)、 [CSSStyle](#cssstyle)、 [CSSProperty](#cssproperty)、 [CSSMedia](#cssmedia)、 [mediaquery](#mediaquery)、 [mediaqueryexpression](#mediaqueryexpression)、 [platformfontusage](#platformfontusage)、 [CSSKeyframesRule](#csskeyframesrule)、 [CSSKeyframeRule](#csskeyframerule)、 [CSSComputedStyleProperty](#csscomputedstyleproperty)、 [CSSStyleSheetHeader](#cssstylesheetheader) [ShorthandEntry](#shorthandentry) |
| [**依存関係**](#dependencies) | [DOM](dom.md) |
## メソッド

### [有効]
指定したページの CSS エージェントを有効にします。 クライアントは、このコマンドの結果が受信されるまで CSS エージェントが有効になっていると想定することはできません。

</p>

---

### [無効]
指定されたページの CSS エージェントを無効にします。

</p>

---

### getInlineStylesForNode
によって識別される DOM ノードのインライン ("style" 属性で明示的に、DOM 属性を使って暗黙的に) 定義されたスタイルを返し `nodeId` ます。

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
            <th>返し</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>inlineStyle <br /> <i>オプション</i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>指定した DOM ノードのインラインスタイル。</td>
        </tr>
        <tr>
            <td>属性スタイル <br /> <i>オプション</i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>属性で定義された要素のスタイル (例: "width = 20 height = 100%")。</td>
        </tr>
    </tbody>
</table>
</p>

---

### Getmatchedの Fornode
によって識別される DOM ノードに対して要求されたスタイルを返し `nodeId` ます。

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
            <th>返し</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>inlineStyle <br /> <i>オプション</i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>指定した DOM ノードのインラインスタイル。</td>
        </tr>
        <tr>
            <td>属性スタイル <br /> <i>オプション</i></td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>属性で定義された要素のスタイル (例: "width = 20 height = 100%")。</td>
        </tr>
        <tr>
            <td>matchedCSSRules <br /> <i>オプション</i></td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td>該当するすべてのスタイルシートから、このノードに一致する CSS ルール。</td>
        </tr>
        <tr>
            <td>疑似要素 <br /> <i>オプション</i></td>
            <td><a href="#pseudoelementmatches"><code class="flyout">PseudoElementMatches[]</code></a></td>
            <td>このノードでは、擬似スタイルが一致します。</td>
        </tr>
        <tr>
            <td>引き継が <br /> <i>オプション</i></td>
            <td><a href="#inheritedstyleentry"><code class="flyout">InheritedStyleEntry[]</code></a></td>
            <td>継承されたスタイルのチェーン (イミディエイトノードの親から DOM ツリーのルートまで)。</td>
        </tr>
        <tr>
            <td>cssKeyframesRules <br /> <i>オプション</i></td>
            <td><a href="#csskeyframesrule"><code class="flyout">CSSKeyframesRule[]</code></a></td>
            <td>このノードに対応する CSS keyframed のアニメーションの一覧です。</td>
        </tr>
    </tbody>
</table>
</p>

---

### Getplatformフォント Fornode
指定したノードで子テキストノードをレンダリングするために使用したプラットフォームフォントに関する情報を要求します。

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
            <th>返し</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>フォント</td>
            <td><a href="#platformfontusage"><code class="flyout">PlatformFontUsage[]</code></a></td>
            <td>使用しているすべてのプラットフォームフォントの利用統計情報</td>
        </tr>
    </tbody>
</table>
</p>

---

### getComputedStyleForNode
によって識別される DOM ノードの計算されたスタイルを返し `nodeId` ます。

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
            <th>返し</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>computedStyle</td>
            <td><a href="#csscomputedstyleproperty"><code class="flyout">CSSComputedStyleProperty[]</code></a></td>
            <td>指定した DOM ノードの計算されたスタイル。</td>
        </tr>
    </tbody>
</table>
</p>

---

## イベント

### styleSheetAdded
アクティブなドキュメントのスタイルシートが追加されるたびに発生します。

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
            <td>スタイルシート metainfo を追加しました。</td>
        </tr>
    </tbody>
</table>
</p>

---

### styleSheetChanged
クライアントの操作の結果として、スタイルシートが変更されるたびに発生します。

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
アクティブなドキュメントのスタイルシートが削除されるたびに発生します。

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

### <a name="pseudoelementmatches"></a> 擬似要素の一致 `object`

1つの擬似スタイルの CSS ルールコレクション。

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
            <td>擬似の型</td>
            <td><a href="dom.md#pseudotype"><code class="flyout">DOM.PseudoType</code></a></td>
            <td>疑似要素型。</td>
        </tr>
        <tr>
            <td>一致</td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td>擬似スタイルに適用される CSS ルールの一致</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="inheritedstyleentry"></a> Inheritedスタイルエントリ `object`

先祖ノードから継承された CSS ルールコレクション。

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
            <td>Style 継承チェーン内の先祖ノードのインラインスタイル (存在する場合)。</td>
        </tr>
        <tr>
            <td>matchedCSSRules</td>
            <td><a href="#rulematch"><code class="flyout">RuleMatch[]</code></a></td>
            <td>スタイル継承チェーンの先祖ノードと一致する CSS ルールの一致</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="rulematch"></a> RuleMatch `object`

CSS ルールのデータを照合します。

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
            <td>ルール</td>
            <td><a href="#cssrule"><code class="flyout">CSSRule</code></a></td>
            <td>一致する CSS ルール。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="value"></a> 値 `object`

単純なセレクターのデータ (セレクターリストでコンマで区切られています)。

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
            <td>範囲 <br /> <i>オプション</i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td>基になるリソースの値の範囲 (存在する場合)。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="selectorlist"></a> SelectorList `object`

セレクターリストのデータ。

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
            <td>軸</td>
            <td><a href="#value"><code class="flyout">Value[]</code></a></td>
            <td>リスト内のセレクター。</td>
        </tr>
        <tr>
            <td>テキスト</td>
            <td><code class="flyout">string</code></td>
            <td>ルールセレクターのテキスト。</td>
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
            <td>この仕分けルールの適用元の css スタイルシート識別子 (ユーザーエージェントスタイルシートとユーザー指定のスタイルシートルールにはありません)。</td>
        </tr>
        <tr>
            <td>selectorList <br /> <i>オプション</i></td>
            <td><a href="#selectorlist"><code class="flyout">SelectorList</code></a></td>
            <td>ルールセレクターのデータ。</td>
        </tr>
        <tr>
            <td>cdn <br /> <i>オプション</i></td>
            <td><<!--  <a href="#stylesheetorigin">  --><code class="flyout">StyleSheetOrigin</code><!--  </a>  --></td>
            <td>親スタイルシートの原点。</td>
        </tr>
        <tr>
            <td>スタイル</td>
            <td><a href="#cssstyle"><code class="flyout">CSSStyle</code></a></td>
            <td>関連付けられたスタイル宣言。</td>
        </tr>
        <tr>
            <td>メディア <br /> <i>オプション</i></td>
            <td><a href="#cssmedia"><code class="flyout">CSSMedia[]</code></a></td>
            <td>メディア一覧の配列 (メディアクエリを含むルールの場合)。 配列は、最も内側にあるメディアクエリを、外側に向かって列挙します。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="sourcerange"></a> SourceRange `object`

リソース内のテキスト範囲。 すべての数値は0から始まります。

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
            <td>範囲の開始列 (両端を含む)。</td>
        </tr>
        <tr>
            <td>endLine</td>
            <td><code class="flyout">integer</code></td>
            <td>範囲の最後の行</td>
        </tr>
        <tr>
            <td>endColumn</td>
            <td><code class="flyout">integer</code></td>
            <td>範囲の終了列 (排他)。</td>
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
            <td>短縮名。</td>
        </tr>
        <tr>
            <td>value</td>
            <td><code class="flyout">string</code></td>
            <td>短縮値。</td>
        </tr>
        <tr>
            <td>大事な <br /> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>プロパティに "! 重要" の注釈が含まれているかどうか ( `false` 存在しない場合は意味)。</td>
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
            <td>この仕分けルールの適用元の css スタイルシート識別子 (ユーザーエージェントスタイルシートとユーザー指定のスタイルシートルールにはありません)。</td>
        </tr>
        <tr>
            <td>cssProperties</td>
            <td><a href="#cssproperty"><code class="flyout">CSSProperty[]</code></a></td>
            <td>スタイルの CSS プロパティ。</td>
        </tr>
        <tr>
            <td>shorthandEntries</td>
            <td><a href="#shorthandentry"><code class="flyout">ShorthandEntry[]</code></a></td>
            <td>スタイルに含まれるすべての shorthands について計算された値。</td>
        </tr>
        <tr>
            <td>cssText <br /> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>スタイル宣言のテキスト (使用できる場合)。</td>
        </tr>
        <tr>
            <td>範囲 <br /> <i>オプション</i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td>囲まれたスタイル宣言の範囲 (使用できる場合)。</td>
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
            <td>プロパティに "! 重要" の注釈が含まれているかどうか ( `false` 存在しない場合は意味)。</td>
        </tr>
        <tr>
            <td>明示 <br /> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>プロパティが暗黙的であるかどうかを `false` 示します (存在しない場合を意味します)。</td>
        </tr>
        <tr>
            <td>テキスト <br /> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>スタイルで指定されている完全なプロパティテキスト。</td>
        </tr>
        <tr>
            <td>Parsek <br /> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>プロパティがブラウザーによって認識されるかどうか ( `true` 存在しない場合)</td>
        </tr>
        <tr>
            <td>無効に <br /> <i>オプション</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>プロパティがユーザーによって無効にされているかどうか (ソースベースのプロパティのみに存在する場合)。</td>
        </tr>
        <tr>
            <td>範囲 <br /> <i>オプション</i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td>囲む style 宣言のプロパティ範囲全体 (使用可能な場合)。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssmedia"></a> CSSMedia `object`

CSS メディアルール記述子。

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
            <td>メディアクエリテキスト。</td>
        </tr>
        <tr>
            <td>ソース</td>
            <td><code class="flyout">string</code> <br /> <i>許可される値: mediaRule、inlineSheet、linkedSheet、</i></td>
            <td>メディアクエリのソース: "Medi@media ArimportRule" は、インラインスタイルシートの STYLE タグで "media" 属性によって指定されている場合に、リンクされたスタイルのリンクタグで "media" 属性で指定されている場合、"inlineSheet" を指定すると、"" を指定すると、"@import" となります。</td>
        </tr>
        <tr>
            <td>sourceURL <br /> <i>オプション</i></td>
            <td><code class="flyout">string</code></td>
            <td>メディアクエリの説明が含まれているドキュメントの URL です。</td>
        </tr>
        <tr>
            <td>範囲 <br /> <i>オプション</i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td>包含されたルール (@media または @import) ヘッダー範囲 (使用可能な場合)。</td>
        </tr>
        <tr>
            <td>styleSheetId <br /> <i>オプション</i></td>
            <td><a href="#stylesheetid"><code class="flyout">StyleSheetId</code></a></td>
            <td>このオブジェクトが含まれているスタイルシートの識別子 (存在する場合)。</td>
        </tr>
        <tr>
            <td>mediaList <br /> <i>オプション</i></td>
            <td><a href="#mediaquery"><code class="flyout">MediaQuery[]</code></a></td>
            <td>メディアクエリの配列。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="mediaquery"></a> MediaQuery `object`

メディアクエリ記述子。

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
            <td>メディアクエリ式の配列。</td>
        </tr>
        <tr>
            <td>active</td>
            <td><code class="flyout">boolean</code></td>
            <td>メディアクエリ条件が満たされているかどうか。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="mediaqueryexpression"></a> MediaQueryExpression `object`

メディアクエリ式記述子。

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
            <td>メディアクエリ式の値。</td>
        </tr>
        <tr>
            <td>配電</td>
            <td><code class="flyout">string</code></td>
            <td>メディアクエリ式の単位。</td>
        </tr>
        <tr>
            <td>機能</td>
            <td><code class="flyout">string</code></td>
            <td>メディアクエリ式機能。</td>
        </tr>
        <tr>
            <td>valueRange <br /> <i>オプション</i></td>
            <td><a href="#sourcerange"><code class="flyout">SourceRange</code></a></td>
            <td>包含するスタイルシート内の値のテキストに関連付けられている範囲 (存在する場合)。</td>
        </tr>
        <tr>
            <td>computedLength <br /> <i>オプション</i></td>
            <td><code class="flyout">number</code></td>
            <td>メディアクエリ式の計算された長さ (該当する場合)。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="platformfontusage"></a> PlatformFontUsage `object`

指定したフォントでレンダリングされたグリフの量に関する情報。

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

CSS キーフレームルール表現。

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
            <td>アニメーション名</td>
            <td><a href="#value"><code class="flyout">Value</code></a></td>
            <td>アニメーション名。</td>
        </tr>
        <tr>
            <td>持つ</td>
            <td><a href="#csskeyframerule"><code class="flyout">CSSKeyframeRule[]</code></a></td>
            <td>キーフレームの一覧。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="csskeyframerule"></a> CSSKeyframeRule `object`

CSS キーフレームルール表現。

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
            <td>この仕分けルールの適用元の css スタイルシート識別子 (ユーザーエージェントスタイルシートとユーザー指定のスタイルシートルールにはありません)。</td>
        </tr>
        <tr>
            <td>cdn</td>
            <td><!--  <a href="#stylesheetorigin">  --><code class="flyout">StyleSheetOrigin</code><!--  </a>  --></td>
            <td>親スタイルシートの原点。</td>
        </tr>
        <tr>
            <td>keyText</td>
            <td><a href="#value"><code class="flyout">Value</code></a></td>
            <td>関連付けられているキーテキスト。</td>
        </tr>
        <tr>
            <td>スタイル</td>
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
            <td>計算されたスタイルプロパティの名前。</td>
        </tr>
        <tr>
            <td>value</td>
            <td><code class="flyout">string</code></td>
            <td>計算された style プロパティの値。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="cssstylesheetheader"></a> CSSStyleSheetHeader `object`

CSS スタイルシート metainformation。

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
            <td>スタイルシートの識別子。</td>
        </tr>
        <tr>
            <td>sourceURL</td>
            <td><code class="flyout">string</code></td>
            <td>スタイルシートリソースの URL。</td>
        </tr>
        <tr>
            <td>無効に</td>
            <td><code class="flyout">boolean</code></td>
            <td>スタイルシートが無効になっているかどうかを示します。</td>
        </tr>
        <tr>
            <td>isInline</td>
            <td><code class="flyout">boolean</code></td>
            <td>パーサーによってこのスタイルタグにこのスタイルシートが作成されるかどうか。 このフラグは、文書に記述されたスタイルタグには設定されません。</td>
        </tr>
        <tr>
            <td>startLine</td>
            <td><code class="flyout">number</code></td>
            <td>リソース内のスタイルシートの線のオフセット (ゼロに基づく)。</td>
        </tr>
        <tr>
            <td>startColumn</td>
            <td><code class="flyout">number</code></td>
            <td>リソース内のスタイルシートの列オフセット (ゼロに基づく)。</td>
        </tr>
        <tr>
            <td>全長</td>
            <td><code class="flyout">number</code></td>
            <td>コンテンツのサイズ (文字単位)。</td>
        </tr>
    </tbody>
</table>
</p>

---

## 依存関係

[DOM](dom.md)
