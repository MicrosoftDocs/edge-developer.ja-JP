---
ms.assetid: 2bc29371-4f2e-4b59-a588-30b107d751f6
description: Microsoft Edge が Web ページの閲覧ビューを提供し、無料の閲覧を有効にする方法を確認します。
title: 閲覧ビュー - 開発者ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 30c01d61ff896cca7b0af90b345a8619307f91c0
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234900"
---
# 読み取りビュー  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Microsoft Edge は、ページ上の無関係なコンテンツや他のセカンダリ コンテンツを気を散らさずに、Web ページの読み書きのような読み上がりを効率化する閲覧ビューを提供します。  閲覧ビューは、アドレス バーの閲覧ビュー **\(** ブック アイコン\) ボタンからオンまたはオフに切り替え、または次の操作を行えます `Ctrl` + `Shift` + `R` 。  閲覧ビューは、ページから次のメタデータを抽出します。  

*   タイトル
*   著者
*   日付
*   発行元
*   Dominant image\(s\)
*   優先する画像のキャプション\(s\)
*   セカンダリ イメージ
*   ページのメイン テキスト コンテンツ
*   著作権

ユーザーは、Microsoft Edge の [設定] パネルからページのコントラストとフォント サイズを **調整** できます。  

## メタデータ抽出  

閲覧ビューによってレンダリングされるページ メタデータの詳細を次に示します。  

### タイトル  

読み取りビューで記事のタイトルが表示されるのを確認するには、次の方法を使用します。  

*   ヘッダーに `title` 要素を含める  
*   次のメタ タグを含める `name="title"`  
*   記事本文のタイトル テキストをメタ タグのコンテンツ文字列と一致します。  コンテンツ文字列内のパイプ \( \) はリーダー ビューがアクティブになることを防ぎ、代わりにハイフン `|` \( `-` \) を使用してみてください。  

### 著者  

閲覧ビューでは、次の要素が探されます `class = "byline-name"` 。  ベスト プラクティスは、作成者名をタイトルの後に、記事の本文の前に配置する方法です。  

```html
<div class="byline-name">Author name</div>
```  

### 日付  

閲覧ビューは、発行元と日付の情報を同じ行にまとめてレンダリングし、この情報を強調表示する追加のスタイルを設定します。  記事の発行日は、文字列に表示されるとおりにレンダリングされます。  閲覧ビューは、特定の日付形式には変換されます。  

記事の本文に日付を含め、読み取りビューで表示する場合は、クラスで日付を含む要素を割り当てします `'dateline'` 。  

```html
<div class="dateline"> Wednesday, September 18, 2013 7:38 AM </div>
```  

記事の本文に日付が含んでいなのに、読み取りビューで日付をレンダリングする場合は、メタ タグを使用します `name='displaydate'` 。  

```html
<meta name="displaydate" content=" Wednesday, September 18, 2013 7:38 AM ">
```  

### 発行元  

閲覧ビューは、発行元情報をレンダリングする Open Graph `"og:site_name"` プロトコルを探します。  また、ページ上の発行元情報のセカンダリ インジケーターとして、任意の html タグ内の属性 `source_organization` `publisher` を検索します。  発行元のテキストは、閲覧ビュー ページのハイパーリンク スタイルを使用して、ページの URL にハイパーリンクされます。  

```html
<meta content="Name of organization source" property="og:site_name">
```  

### 画像  

読み取りビューでは、幅 >= 400px、縦横比 >= 1/3、= 3.0 の生の画像<キャプチャします。  これらのサイズを満たしていない画像は、幅が 400 ピクセル未満でキャプションが付いた画像など、引き続き抽出できます。  最初の対象となる画像は、記事の主要なイメージになります。  主要な画像は、コンテンツの最初の部分としてレンダリングされ、列全体の幅が指定されます。  次のすべての画像は、記事内でインライン画像としてレンダリングされます。  

### 字幕  

ベスト プラクティスは、画像を[](https://developer.mozilla.org/docs/Web/HTML/Element/figure)2 つ以下の入れ子の[figcaption](https://developer.mozilla.org/docs/Web/HTML/Element/figcaption)タグを持つ図タグに配置します。  

### 本文  

読み取りビューでページのすべての本文テキストを確実にキャプチャするために、ほとんどの記事のテキストを同じフォント サイズと DOM の深さに保つために役立ちます。  閲覧表示アルゴリズムを使用すると、このルールからある程度のずれが生じ、パブリッシャーは自由に行や単語を強調することができます。  

### 著作権  

閲覧ビューは、メタ タグで示される著作権情報を抽出して表示します。メタ タグ情報が存在しない場合は、著作権 \( \) 記号を含むテキスト ノード `name = "copyright"` `©` が表示されます。  閲覧ビューには、本文の末尾に著作権情報が表示され、本文のテキストよりも小さいフォント サイズでスタイル設定されます。  

```html
<meta name="copyright" content="Your copyright information">
```  

## 読み取りビューをオプトアウトする  

コンテンツが閲覧ビューに適していないと感じた場合は、次のメタ タグを使用してこの機能をオプトアウトできます。  

```html
<meta name="IE_RM_OFF" content="true">
```  

このタグを使用すると****、ユーザーがページを表示するときに[閲覧ビュー] ボタンがアドレス バーに表示されません。  
