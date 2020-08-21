---
ms.assetid: 2bc29371-4f2e-4b59-a588-30b107d751f6
description: Microsoft Edge が Web ページの閲覧ビューを提供し、アドインの閲覧を有効にする方法を説明します。
title: 閲覧表示 - 開発ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、Web 開発、html、cs、javascript、開発者
ms.openlocfilehash: 0d2076a63f97ecf2b4699795b0036736d0f95c9c
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941995"
---
# 読み取りビュー  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Microsoft Edge では、ページ上の関連しないコンテンツや他の第 2 のコンテンツに気がついていることなく、より効率的で、より効率的に Web ページの閲覧表示機能が用意されています。  閲覧表示は、アドレス バーの閲覧**表示の**\(書籍アイコン\) ボタンまたは使用してオンまたはオフに切り替えることができます `Ctrl` + `Shift` + `R` 。  読み取りビューでは、次のメタデータがページから取り込みられます。  

*   タイトル
*   著者
*   日付
*   発行元
*   Dominant image\(s\)
*   ドマニア語画像\(s\) のキャプション
*   セカンダリ画像
*   ページのメイン テキスト コンテンツ
*   著作権

ユーザーは、Microsoft Edge の [設定] パネルからページのコントラストとフォント サイズ **を調整** できます。  

## メタデータの追加  

閲覧表示によってレンダリングされるページのメタデータの詳細は次のとおりです。  

### タイトル  

閲覧表示で、記事のタイトルが表示されるようにするには、次の手順に従います。  

*   ヘッダーに `title` 要素を含める  
*   メタ タグを追加する `name="title"`  
*   記事本文のタイトル テキストとメタ タグのコンテンツ文字列と一致します。  コンテンツ文字列に含めた \(\) を使用すると、閲覧者ビューがアクティブになるのを防 `|` げます。代わりにハイフン \( `-` \) を使用してみてください。  

### 著者  

閲覧表示で要素が検索されます `class = "byline-name"` 。  ベスト プラクティスは、タイトルの後と記事本文の前に作成者名を配置する方法です。  

```html
<div class="byline-name">Author name</div>
```  

### 日付  

閲覧表示では、パブリッシャーと日付の情報を同じ行にまとめて表示し、この情報を強調表示するスタイルが追加されます。  記事の公開日は、文字列に含まれる場合とまる正しく表示されます。  閲覧表示では特定の日付形式に変換されません。  

記事の本文に日付があり、閲覧ビューでそれを表示する場合は、次のクラスの日付を含む要素を割り当てます `'dateline'` 。  

```html
<div class="dateline"> Wednesday, September 18, 2013 7:38 AM </div>
```  

記事本文に日付がなく、閲覧表示に同じ日付を表示する場合は、メタグを使用します `name='displaydate'` 。  

```html
<meta name="displaydate" content=" Wednesday, September 18, 2013 7:38 AM ">
```  

### 発行元  

閲覧表示では、Open Graph プロトコルを探して `"og:site_name"` 、発行元情報を表示します。  また、ページ上の発行元情報のセカンダリ インジケーターとして、html タグで、必要な html タグ `source_organization` `publisher` を探して属性を探して属性を探します。  発行元のテキストは、読み取りビュー ページのハイパーリンク スタイルを使用してページの URL にハイパーリンクされます。  

```html
<meta content="Name of organization source" property="og:site_name">
```  

### 画像  

閲覧表示では、幅 >= 400px と縦比率 >= 1/3、=< 3.0 を使用したほとんどの生画像が取り出されます。  サイズが 400px より小さい画像など、図は引き続き取り出す可能性があります。  最初の対象となる画像が記事のイメージになりました。  ドマン画像は、最初のコンテンツと全列幅が指定されたコンテンツの一部として表示されます。  以下の画像はすべて、記事内でインライン 画像として表示されます。  

### 字幕  

ベスト プラクティスは、画像を図タ[figure](https://developer.mozilla.org/docs/Web/HTML/Element/figure)グに、ネストされた 3 つ以上の図表番号タグがない[図タグに配置](https://developer.mozilla.org/docs/Web/HTML/Element/figcaption)する方法です。  

### 本文  

ページの本文のすべての本文が閲覧表示でキャプチャされるように、記事のテキストをすべて同じフォント サイズと DOM の詳細を常に保持するのに役立ちます。  読み取りビュー アルゴリズムでは、このルールからいくつかの考えに使用できるため、パブリッシャーが線や単語に表や単語を追加できるようになります。  

### 著作権  

閲覧表示では、メタ タグによって示される著作権情報が取り出され、メタタタ グ情報が `name = "copyright"` 存在しない場合は、著作権 \( \( \) 記号を含むテキスト ノー `©` ドです。  閲覧表示では、記事の本文の最後に著作権の情報が表示されます。このサイズは、メインの本文よりも小さいフォント サイズで表示されます。  

```html
<meta name="copyright" content="Your copyright information">
```  

## 閲覧表示からオプトアウトする  

閲覧表示にとってうまくいかないコンテンツが見つからない場合は、次のメタグを使用してこの機能を無効にすることができます。  

```html
<meta name="IE_RM_OFF" content="true">
```  

このタグを使用すると、ユーザー **がページ** を表示したときに、閲覧ビュー ボタンはアドレス バーに表示されません。  
