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
# <span data-ttu-id="6d004-104">読み取りビュー</span><span class="sxs-lookup"><span data-stu-id="6d004-104">Reading view</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="6d004-105">Microsoft Edge は、ページ上の無関係なコンテンツや他のセカンダリ コンテンツを気を散らさずに、Web ページの読み書きのような読み上がりを効率化する閲覧ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="6d004-105">Microsoft Edge provides a reading view for a more streamlined, book-like reading experience of webpages without the distraction of unrelated or other secondary content on the page.</span></span>  <span data-ttu-id="6d004-106">閲覧ビューは、アドレス バーの閲覧ビュー **\(** ブック アイコン\) ボタンからオンまたはオフに切り替え、または次の操作を行えます `Ctrl` + `Shift` + `R` 。</span><span class="sxs-lookup"><span data-stu-id="6d004-106">Reading view can be toggled on or off from the **Reading view** \(book icon\) button on the address bar or with `Ctrl`+`Shift`+`R`.</span></span>  <span data-ttu-id="6d004-107">閲覧ビューは、ページから次のメタデータを抽出します。</span><span class="sxs-lookup"><span data-stu-id="6d004-107">Reading view extracts the following metadata from a page:</span></span>  

*   <span data-ttu-id="6d004-108">タイトル</span><span class="sxs-lookup"><span data-stu-id="6d004-108">Title</span></span>
*   <span data-ttu-id="6d004-109">著者</span><span class="sxs-lookup"><span data-stu-id="6d004-109">Author</span></span>
*   <span data-ttu-id="6d004-110">日付</span><span class="sxs-lookup"><span data-stu-id="6d004-110">Date</span></span>
*   <span data-ttu-id="6d004-111">発行元</span><span class="sxs-lookup"><span data-stu-id="6d004-111">Publisher</span></span>
*   <span data-ttu-id="6d004-112">Dominant image\(s\)</span><span class="sxs-lookup"><span data-stu-id="6d004-112">Dominant image\(s\)</span></span>
*   <span data-ttu-id="6d004-113">優先する画像のキャプション\(s\)</span><span class="sxs-lookup"><span data-stu-id="6d004-113">Captions of dominant image\(s\)</span></span>
*   <span data-ttu-id="6d004-114">セカンダリ イメージ</span><span class="sxs-lookup"><span data-stu-id="6d004-114">Secondary images</span></span>
*   <span data-ttu-id="6d004-115">ページのメイン テキスト コンテンツ</span><span class="sxs-lookup"><span data-stu-id="6d004-115">Main text content of the page</span></span>
*   <span data-ttu-id="6d004-116">著作権</span><span class="sxs-lookup"><span data-stu-id="6d004-116">Copyright</span></span>

<span data-ttu-id="6d004-117">ユーザーは、Microsoft Edge の [設定] パネルからページのコントラストとフォント サイズを **調整** できます。</span><span class="sxs-lookup"><span data-stu-id="6d004-117">Users can then adjust the page contrast and font size from the Microsoft Edge **Settings** panel.</span></span>  

## <span data-ttu-id="6d004-118">メタデータ抽出</span><span class="sxs-lookup"><span data-stu-id="6d004-118">Metadata extraction</span></span>  

<span data-ttu-id="6d004-119">閲覧ビューによってレンダリングされるページ メタデータの詳細を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6d004-119">Here are details of the page metadata rendered by reading view.</span></span>  

### <span data-ttu-id="6d004-120">タイトル</span><span class="sxs-lookup"><span data-stu-id="6d004-120">Title</span></span>  

<span data-ttu-id="6d004-121">読み取りビューで記事のタイトルが表示されるのを確認するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="6d004-121">To ensure Reading view renders your article's title:</span></span>  

*   <span data-ttu-id="6d004-122">ヘッダーに `title` 要素を含める</span><span class="sxs-lookup"><span data-stu-id="6d004-122">Include a `title` element in your header</span></span>  
*   <span data-ttu-id="6d004-123">次のメタ タグを含める</span><span class="sxs-lookup"><span data-stu-id="6d004-123">Include a meta tag with</span></span> `name="title"`  
*   <span data-ttu-id="6d004-124">記事本文のタイトル テキストをメタ タグのコンテンツ文字列と一致します。</span><span class="sxs-lookup"><span data-stu-id="6d004-124">Match the title text in your article body with the content string of your meta tag.</span></span>  <span data-ttu-id="6d004-125">コンテンツ文字列内のパイプ \( \) はリーダー ビューがアクティブになることを防ぎ、代わりにハイフン `|` \( `-` \) を使用してみてください。</span><span class="sxs-lookup"><span data-stu-id="6d004-125">Pipes \(`|`\) in your content string prevent the reader view from becoming active, try using hyphens \(`-`\) instead.</span></span>  

### <span data-ttu-id="6d004-126">著者</span><span class="sxs-lookup"><span data-stu-id="6d004-126">Author</span></span>  

<span data-ttu-id="6d004-127">閲覧ビューでは、次の要素が探されます `class = "byline-name"` 。</span><span class="sxs-lookup"><span data-stu-id="6d004-127">Reading View will look for an element with `class = "byline-name"`.</span></span>  <span data-ttu-id="6d004-128">ベスト プラクティスは、作成者名をタイトルの後に、記事の本文の前に配置する方法です。</span><span class="sxs-lookup"><span data-stu-id="6d004-128">Best practice is to place the author name after the title and before the article body.</span></span>  

```html
<div class="byline-name">Author name</div>
```  

### <span data-ttu-id="6d004-129">日付</span><span class="sxs-lookup"><span data-stu-id="6d004-129">Date</span></span>  

<span data-ttu-id="6d004-130">閲覧ビューは、発行元と日付の情報を同じ行にまとめてレンダリングし、この情報を強調表示する追加のスタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="6d004-130">Reading view will render the publisher and date information together on the same line, with additional styling to highlight this information.</span></span>  <span data-ttu-id="6d004-131">記事の発行日は、文字列に表示されるとおりにレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="6d004-131">The article's publishing date will render exactly as it appears in the string.</span></span>  <span data-ttu-id="6d004-132">閲覧ビューは、特定の日付形式には変換されます。</span><span class="sxs-lookup"><span data-stu-id="6d004-132">Reading view does not convert to a specific date format.</span></span>  

<span data-ttu-id="6d004-133">記事の本文に日付を含め、読み取りビューで表示する場合は、クラスで日付を含む要素を割り当てします `'dateline'` 。</span><span class="sxs-lookup"><span data-stu-id="6d004-133">If you have a date in your article body and would like Reading view to render it, assign the element containing the date with the class `'dateline'`:</span></span>  

```html
<div class="dateline"> Wednesday, September 18, 2013 7:38 AM </div>
```  

<span data-ttu-id="6d004-134">記事の本文に日付が含んでいなのに、読み取りビューで日付をレンダリングする場合は、メタ タグを使用します `name='displaydate'` 。</span><span class="sxs-lookup"><span data-stu-id="6d004-134">If you don't have a date in the article body but would like Reading view to render the date, use the meta tag `name='displaydate'`:</span></span>  

```html
<meta name="displaydate" content=" Wednesday, September 18, 2013 7:38 AM ">
```  

### <span data-ttu-id="6d004-135">発行元</span><span class="sxs-lookup"><span data-stu-id="6d004-135">Publisher</span></span>  

<span data-ttu-id="6d004-136">閲覧ビューは、発行元情報をレンダリングする Open Graph `"og:site_name"` プロトコルを探します。</span><span class="sxs-lookup"><span data-stu-id="6d004-136">Reading view will look for the Open Graph protocol `"og:site_name"` to render the publisher information.</span></span>  <span data-ttu-id="6d004-137">また、ページ上の発行元情報のセカンダリ インジケーターとして、任意の html タグ内の属性 `source_organization` `publisher` を検索します。</span><span class="sxs-lookup"><span data-stu-id="6d004-137">It also looks for `source_organization` and `publisher` attributes in any html tag as a secondary indicator of publisher information on the page.</span></span>  <span data-ttu-id="6d004-138">発行元のテキストは、閲覧ビュー ページのハイパーリンク スタイルを使用して、ページの URL にハイパーリンクされます。</span><span class="sxs-lookup"><span data-stu-id="6d004-138">The publisher text will be hyperlinked to the URL of page using the Reading view page hyperlink style.</span></span>  

```html
<meta content="Name of organization source" property="og:site_name">
```  

### <span data-ttu-id="6d004-139">画像</span><span class="sxs-lookup"><span data-stu-id="6d004-139">Images</span></span>  

<span data-ttu-id="6d004-140">読み取りビューでは、幅 >= 400px、縦横比 >= 1/3、= 3.0 の生の画像<キャプチャします。</span><span class="sxs-lookup"><span data-stu-id="6d004-140">Reading view captures most raw images with width >= 400px and aspect ratio >= 1/3 and =< 3.0.</span></span>  <span data-ttu-id="6d004-141">これらのサイズを満たしていない画像は、幅が 400 ピクセル未満でキャプションが付いた画像など、引き続き抽出できます。</span><span class="sxs-lookup"><span data-stu-id="6d004-141">Images that do not meet these dimensions may still be extracted, such as images that are smaller than 400px in width but have captions.</span></span>  <span data-ttu-id="6d004-142">最初の対象となる画像は、記事の主要なイメージになります。</span><span class="sxs-lookup"><span data-stu-id="6d004-142">The first eligible image becomes the dominant image of the article.</span></span>  <span data-ttu-id="6d004-143">主要な画像は、コンテンツの最初の部分としてレンダリングされ、列全体の幅が指定されます。</span><span class="sxs-lookup"><span data-stu-id="6d004-143">The dominant image is rendered as the first piece of content and given full column width.</span></span>  <span data-ttu-id="6d004-144">次のすべての画像は、記事内でインライン画像としてレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="6d004-144">All following images are rendered as inline images within the article.</span></span>  

### <span data-ttu-id="6d004-145">字幕</span><span class="sxs-lookup"><span data-stu-id="6d004-145">Captions</span></span>  

<span data-ttu-id="6d004-146">ベスト プラクティスは、画像を[](https://developer.mozilla.org/docs/Web/HTML/Element/figure)2 つ以下の入れ子の[figcaption](https://developer.mozilla.org/docs/Web/HTML/Element/figcaption)タグを持つ図タグに配置します。</span><span class="sxs-lookup"><span data-stu-id="6d004-146">Best practice is to place images in [figure](https://developer.mozilla.org/docs/Web/HTML/Element/figure) tags with no more than two nested [figcaption](https://developer.mozilla.org/docs/Web/HTML/Element/figcaption) tags.</span></span>  

### <span data-ttu-id="6d004-147">本文</span><span class="sxs-lookup"><span data-stu-id="6d004-147">Body</span></span>  

<span data-ttu-id="6d004-148">読み取りビューでページのすべての本文テキストを確実にキャプチャするために、ほとんどの記事のテキストを同じフォント サイズと DOM の深さに保つために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6d004-148">To ensure that all the body text of your page is captured by Reading view, it helps to keep most of the article text the same font size and DOM depth.</span></span>  <span data-ttu-id="6d004-149">閲覧表示アルゴリズムを使用すると、このルールからある程度のずれが生じ、パブリッシャーは自由に行や単語を強調することができます。</span><span class="sxs-lookup"><span data-stu-id="6d004-149">The reading view algorithm allows for some deviation from this rule so publishers can have the freedom to add emphasis to lines or words.</span></span>  

### <span data-ttu-id="6d004-150">著作権</span><span class="sxs-lookup"><span data-stu-id="6d004-150">Copyright</span></span>  

<span data-ttu-id="6d004-151">閲覧ビューは、メタ タグで示される著作権情報を抽出して表示します。メタ タグ情報が存在しない場合は、著作権 \( \) 記号を含むテキスト ノード `name = "copyright"` `©` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d004-151">Reading view extracts and displays copyright information denoted by meta tags with `name = "copyright"`, or if no meta tag information exists, a text node that contains the copyright \(`©`\) symbol.</span></span>  <span data-ttu-id="6d004-152">閲覧ビューには、本文の末尾に著作権情報が表示され、本文のテキストよりも小さいフォント サイズでスタイル設定されます。</span><span class="sxs-lookup"><span data-stu-id="6d004-152">Reading view displays copyright information at the end of the article main body, styled using a smaller font size than the main body text.</span></span>  

```html
<meta name="copyright" content="Your copyright information">
```  

## <span data-ttu-id="6d004-153">読み取りビューをオプトアウトする</span><span class="sxs-lookup"><span data-stu-id="6d004-153">Opting out of Reading View</span></span>  

<span data-ttu-id="6d004-154">コンテンツが閲覧ビューに適していないと感じた場合は、次のメタ タグを使用してこの機能をオプトアウトできます。</span><span class="sxs-lookup"><span data-stu-id="6d004-154">If you feel your content is not a good fit for Reading view, you can use the following meta tag to opt out of this feature:</span></span>  

```html
<meta name="IE_RM_OFF" content="true">
```  

<span data-ttu-id="6d004-155">このタグを使用すると、ユーザーがページを表示するときに[閲覧ビュー] ボタンがアドレス バーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="6d004-155">With this tag, the **Reading view** button will not appear in the address bar when your users view your page.</span></span>  
