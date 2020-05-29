---
ms.assetid: 2bc29371-4f2e-4b59-a588-30b107d751f6
description: Microsoft Edge で web ページの閲覧表示がどのように提供されるかをご覧ください。
title: 開発ガイド-閲覧表示
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: e84edb5cc29b644939895f2996c50f3b4ec23379
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568833"
---
# 読み取りビュー

Microsoft Edge には、ページ上の関連性のない、または他の二次的なコンテンツを気にせずに、web ページをより効率的に使用できるようにするための*閲覧表示*が用意されています。 閲覧表示は、**アドレスバー**の (または Ctrl キーを**押し**ながら R を押しながら)**閲覧表示**(ブックアイコン) ボタンでオンまたはオフにすることができ  +  **Shift**  +  **R**ます。 閲覧表示では、次のメタデータがページから抽出されます。

* タイトル
* 著者
* 日付
* 発行元
* 主要イメージ
* 主要な画像のキャプション
* セカンダリイメージ
* ページのメインテキストコンテンツ
* 著作権

ユーザーは、Microsoft Edge の [**設定**] パネルでページのコントラストとフォントサイズを調整することができます。

## メタデータの抽出


ここでは、閲覧表示によってレンダリングされるページメタデータの詳細について説明します。

### タイトル

閲覧表示で記事のタイトルをレンダリングするには、次の操作を行います。

* ヘッダーに**タイトル**要素を含める
* 次のメタタグを含める `name="title"`
* 記事本文のタイトルテキストと、メタタグのコンテンツ文字列を一致させます。 `|`コンテンツ文字列のパイプリーダービューがアクティブにならないように、代わりに hypens を使用してみてください `-` 。

### 著者

閲覧表示では、要素を検索 `class = "byline-name"` します。 ベストプラクティスとして、タイトルの後と記事本文の前に作成者の名前を配置することをお勧めします。

```html
<div class="byline-name">Author name</div>
```

### 日付

閲覧表示では、publisher と日付の情報が同じ行にまとめて表示され、この情報を強調するためのスタイルが追加されます。 記事の発行日は、文字列に表示されるとおりに表示されます。 閲覧表示は特定の日付形式に変換されません。

記事の本文に日付があり、閲覧表示で表示する必要がある場合は、次のように、日付を含む要素をクラスに割り当て `'dateline'` ます。

```html
<div class="dateline"> Wednesday, September 18, 2013 7:38 AM </div>
```

記事の本文に日付が表示されておらず、閲覧表示で日付を表示したい場合は、meta タグを使用し `name='displaydate'` ます。

```html
<meta name="displaydate" content=" Wednesday, September 18, 2013 7:38 AM ">
```

### 発行元

閲覧表示では、publisher の情報を表示するために、 *Open Graph*プロトコルが検索され `"og:site_name"` ます。 また、 `source_organization` `publisher` どの html タグでも、ページ上の publisher 情報のセカンダリインジケーターとして属性を検索し、属性を探します。 Publisher のテキストは、[閲覧表示] ページのハイパーリンクスタイルを使用して、ページの URL にハイパーリンクされます。

```html
<meta content="Name of organization source" property="og:site_name">
```

### 画像

閲覧表示では、幅 >= 400px、縦横比 >= 1/3 and =< 3.0 のほとんどの raw 画像がキャプチャされます。 これらの寸法を満たしていない画像はまだ抽出されている可能性があります。たとえば、幅が400px より小さく、キャプションがある画像などです。 最初の対象となる画像は、記事の主要な画像になります。 主要な画像は、コンテンツの最初の部分と、すべての列の幅としてレンダリングされます。 次の画像はすべて、記事内のインライン画像としてレンダリングされます。

### 字幕

ベストプラクティスとして、3つの入れ子になった[figcaption](https://msdn.microsoft.com/library/gg593037(v=vs.85).aspx)タグを持たない[図](https://msdn.microsoft.com/library/gg593038(v=vs.85).aspx)のタグに画像を配置することをお勧めします。

### 本文

ページのすべての本文のテキストを閲覧表示で確実にキャプチャするために、ほとんどの記事のテキストを同じフォントサイズと DOM 深度にしておくことができます。 閲覧表示アルゴリズムでは、publishers が行または単語に自由に追加できるように、このルールによって一定の誤差を与えることができます。

### 著作権

閲覧表示では、meta タグで示されている著作権情報が抽出され `name = "copyright"` 、メタタグ情報が存在しない場合は、著作権 (**©**) 記号を含むテキストノードが表示されます。 [閲覧表示] は、本文の本文より小さいフォントサイズでスタイルが適用された、記事の本文の最後に著作権情報を表示します。

```html
<meta name="copyright" content="Your copyright information">
```

## 閲覧表示を終了する


閲覧表示に適していないコンテンツの場合は、次の meta タグを使用してこの機能を無効にすることができます。

```html
<meta name="IE_RM_OFF" content="true">
```

このタグを使用すると、ユーザーがページを表示したときに、[**閲覧表示**] ボタンがアドレスバーに表示されません。
