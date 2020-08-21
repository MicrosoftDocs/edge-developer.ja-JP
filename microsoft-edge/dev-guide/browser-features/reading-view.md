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
# <span data-ttu-id="30601-104">読み取りビュー</span><span class="sxs-lookup"><span data-stu-id="30601-104">Reading view</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="30601-105">Microsoft Edge では、ページ上の関連しないコンテンツや他の第 2 のコンテンツに気がついていることなく、より効率的で、より効率的に Web ページの閲覧表示機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="30601-105">Microsoft Edge provides a reading view for a more streamlined, book-like reading experience of webpages without the distraction of unrelated or other secondary content on the page.</span></span>  <span data-ttu-id="30601-106">閲覧表示は、アドレス バーの閲覧**表示の**\(書籍アイコン\) ボタンまたは使用してオンまたはオフに切り替えることができます `Ctrl` + `Shift` + `R` 。</span><span class="sxs-lookup"><span data-stu-id="30601-106">Reading view can be toggled on or off from the **Reading view** \(book icon\) button on the address bar or with `Ctrl`+`Shift`+`R`.</span></span>  <span data-ttu-id="30601-107">読み取りビューでは、次のメタデータがページから取り込みられます。</span><span class="sxs-lookup"><span data-stu-id="30601-107">Reading view extracts the following metadata from a page:</span></span>  

*   <span data-ttu-id="30601-108">タイトル</span><span class="sxs-lookup"><span data-stu-id="30601-108">Title</span></span>
*   <span data-ttu-id="30601-109">著者</span><span class="sxs-lookup"><span data-stu-id="30601-109">Author</span></span>
*   <span data-ttu-id="30601-110">日付</span><span class="sxs-lookup"><span data-stu-id="30601-110">Date</span></span>
*   <span data-ttu-id="30601-111">発行元</span><span class="sxs-lookup"><span data-stu-id="30601-111">Publisher</span></span>
*   <span data-ttu-id="30601-112">Dominant image\(s\)</span><span class="sxs-lookup"><span data-stu-id="30601-112">Dominant image\(s\)</span></span>
*   <span data-ttu-id="30601-113">ドマニア語画像\(s\) のキャプション</span><span class="sxs-lookup"><span data-stu-id="30601-113">Captions of dominant image\(s\)</span></span>
*   <span data-ttu-id="30601-114">セカンダリ画像</span><span class="sxs-lookup"><span data-stu-id="30601-114">Secondary images</span></span>
*   <span data-ttu-id="30601-115">ページのメイン テキスト コンテンツ</span><span class="sxs-lookup"><span data-stu-id="30601-115">Main text content of the page</span></span>
*   <span data-ttu-id="30601-116">著作権</span><span class="sxs-lookup"><span data-stu-id="30601-116">Copyright</span></span>

<span data-ttu-id="30601-117">ユーザーは、Microsoft Edge の [設定] パネルからページのコントラストとフォント サイズ **を調整** できます。</span><span class="sxs-lookup"><span data-stu-id="30601-117">Users can then adjust the page contrast and font size from the Microsoft Edge **Settings** panel.</span></span>  

## <span data-ttu-id="30601-118">メタデータの追加</span><span class="sxs-lookup"><span data-stu-id="30601-118">Metadata extraction</span></span>  

<span data-ttu-id="30601-119">閲覧表示によってレンダリングされるページのメタデータの詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="30601-119">Here are details of the page metadata rendered by reading view.</span></span>  

### <span data-ttu-id="30601-120">タイトル</span><span class="sxs-lookup"><span data-stu-id="30601-120">Title</span></span>  

<span data-ttu-id="30601-121">閲覧表示で、記事のタイトルが表示されるようにするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="30601-121">To ensure Reading view renders your article's title:</span></span>  

*   <span data-ttu-id="30601-122">ヘッダーに `title` 要素を含める</span><span class="sxs-lookup"><span data-stu-id="30601-122">Include a `title` element in your header</span></span>  
*   <span data-ttu-id="30601-123">メタ タグを追加する</span><span class="sxs-lookup"><span data-stu-id="30601-123">Include a meta tag with</span></span> `name="title"`  
*   <span data-ttu-id="30601-124">記事本文のタイトル テキストとメタ タグのコンテンツ文字列と一致します。</span><span class="sxs-lookup"><span data-stu-id="30601-124">Match the title text in your article body with the content string of your meta tag.</span></span>  <span data-ttu-id="30601-125">コンテンツ文字列に含めた \(\) を使用すると、閲覧者ビューがアクティブになるのを防 `|` げます。代わりにハイフン \( `-` \) を使用してみてください。</span><span class="sxs-lookup"><span data-stu-id="30601-125">Pipes \(`|`\) in your content string prevent the reader view from becoming active, try using hyphens \(`-`\) instead.</span></span>  

### <span data-ttu-id="30601-126">著者</span><span class="sxs-lookup"><span data-stu-id="30601-126">Author</span></span>  

<span data-ttu-id="30601-127">閲覧表示で要素が検索されます `class = "byline-name"` 。</span><span class="sxs-lookup"><span data-stu-id="30601-127">Reading View will look for an element with `class = "byline-name"`.</span></span>  <span data-ttu-id="30601-128">ベスト プラクティスは、タイトルの後と記事本文の前に作成者名を配置する方法です。</span><span class="sxs-lookup"><span data-stu-id="30601-128">Best practice is to place the author name after the title and before the article body.</span></span>  

```html
<div class="byline-name">Author name</div>
```  

### <span data-ttu-id="30601-129">日付</span><span class="sxs-lookup"><span data-stu-id="30601-129">Date</span></span>  

<span data-ttu-id="30601-130">閲覧表示では、パブリッシャーと日付の情報を同じ行にまとめて表示し、この情報を強調表示するスタイルが追加されます。</span><span class="sxs-lookup"><span data-stu-id="30601-130">Reading view will render the publisher and date information together on the same line, with additional styling to highlight this information.</span></span>  <span data-ttu-id="30601-131">記事の公開日は、文字列に含まれる場合とまる正しく表示されます。</span><span class="sxs-lookup"><span data-stu-id="30601-131">The article's publishing date will render exactly as it appears in the string.</span></span>  <span data-ttu-id="30601-132">閲覧表示では特定の日付形式に変換されません。</span><span class="sxs-lookup"><span data-stu-id="30601-132">Reading view does not convert to a specific date format.</span></span>  

<span data-ttu-id="30601-133">記事の本文に日付があり、閲覧ビューでそれを表示する場合は、次のクラスの日付を含む要素を割り当てます `'dateline'` 。</span><span class="sxs-lookup"><span data-stu-id="30601-133">If you have a date in your article body and would like Reading view to render it, assign the element containing the date with the class `'dateline'`:</span></span>  

```html
<div class="dateline"> Wednesday, September 18, 2013 7:38 AM </div>
```  

<span data-ttu-id="30601-134">記事本文に日付がなく、閲覧表示に同じ日付を表示する場合は、メタグを使用します `name='displaydate'` 。</span><span class="sxs-lookup"><span data-stu-id="30601-134">If you don't have a date in the article body but would like Reading view to render the date, use the meta tag `name='displaydate'`:</span></span>  

```html
<meta name="displaydate" content=" Wednesday, September 18, 2013 7:38 AM ">
```  

### <span data-ttu-id="30601-135">発行元</span><span class="sxs-lookup"><span data-stu-id="30601-135">Publisher</span></span>  

<span data-ttu-id="30601-136">閲覧表示では、Open Graph プロトコルを探して `"og:site_name"` 、発行元情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="30601-136">Reading view will look for the Open Graph protocol `"og:site_name"` to render the publisher information.</span></span>  <span data-ttu-id="30601-137">また、ページ上の発行元情報のセカンダリ インジケーターとして、html タグで、必要な html タグ `source_organization` `publisher` を探して属性を探して属性を探します。</span><span class="sxs-lookup"><span data-stu-id="30601-137">It also looks for `source_organization` and `publisher` attributes in any html tag as a secondary indicator of publisher information on the page.</span></span>  <span data-ttu-id="30601-138">発行元のテキストは、読み取りビュー ページのハイパーリンク スタイルを使用してページの URL にハイパーリンクされます。</span><span class="sxs-lookup"><span data-stu-id="30601-138">The publisher text will be hyperlinked to the URL of page using the Reading view page hyperlink style.</span></span>  

```html
<meta content="Name of organization source" property="og:site_name">
```  

### <span data-ttu-id="30601-139">画像</span><span class="sxs-lookup"><span data-stu-id="30601-139">Images</span></span>  

<span data-ttu-id="30601-140">閲覧表示では、幅 >= 400px と縦比率 >= 1/3、=< 3.0 を使用したほとんどの生画像が取り出されます。</span><span class="sxs-lookup"><span data-stu-id="30601-140">Reading view captures most raw images with width >= 400px and aspect ratio >= 1/3 and =< 3.0.</span></span>  <span data-ttu-id="30601-141">サイズが 400px より小さい画像など、図は引き続き取り出す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="30601-141">Images that do not meet these dimensions may still be extracted, such as images that are smaller than 400px in width but have captions.</span></span>  <span data-ttu-id="30601-142">最初の対象となる画像が記事のイメージになりました。</span><span class="sxs-lookup"><span data-stu-id="30601-142">The first eligible image becomes the dominant image of the article.</span></span>  <span data-ttu-id="30601-143">ドマン画像は、最初のコンテンツと全列幅が指定されたコンテンツの一部として表示されます。</span><span class="sxs-lookup"><span data-stu-id="30601-143">The dominant image is rendered as the first piece of content and given full column width.</span></span>  <span data-ttu-id="30601-144">以下の画像はすべて、記事内でインライン 画像として表示されます。</span><span class="sxs-lookup"><span data-stu-id="30601-144">All following images are rendered as inline images within the article.</span></span>  

### <span data-ttu-id="30601-145">字幕</span><span class="sxs-lookup"><span data-stu-id="30601-145">Captions</span></span>  

<span data-ttu-id="30601-146">ベスト プラクティスは、画像を図タ[figure](https://developer.mozilla.org/docs/Web/HTML/Element/figure)グに、ネストされた 3 つ以上の図表番号タグがない[図タグに配置](https://developer.mozilla.org/docs/Web/HTML/Element/figcaption)する方法です。</span><span class="sxs-lookup"><span data-stu-id="30601-146">Best practice is to place images in [figure](https://developer.mozilla.org/docs/Web/HTML/Element/figure) tags with no more than two nested [figcaption](https://developer.mozilla.org/docs/Web/HTML/Element/figcaption) tags.</span></span>  

### <span data-ttu-id="30601-147">本文</span><span class="sxs-lookup"><span data-stu-id="30601-147">Body</span></span>  

<span data-ttu-id="30601-148">ページの本文のすべての本文が閲覧表示でキャプチャされるように、記事のテキストをすべて同じフォント サイズと DOM の詳細を常に保持するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="30601-148">To ensure that all the body text of your page is captured by Reading view, it helps to keep most of the article text the same font size and DOM depth.</span></span>  <span data-ttu-id="30601-149">読み取りビュー アルゴリズムでは、このルールからいくつかの考えに使用できるため、パブリッシャーが線や単語に表や単語を追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="30601-149">The reading view algorithm allows for some deviation from this rule so publishers can have the freedom to add emphasis to lines or words.</span></span>  

### <span data-ttu-id="30601-150">著作権</span><span class="sxs-lookup"><span data-stu-id="30601-150">Copyright</span></span>  

<span data-ttu-id="30601-151">閲覧表示では、メタ タグによって示される著作権情報が取り出され、メタタタ グ情報が `name = "copyright"` 存在しない場合は、著作権 \( \( \) 記号を含むテキスト ノー `©` ドです。</span><span class="sxs-lookup"><span data-stu-id="30601-151">Reading view extracts and displays copyright information denoted by meta tags with `name = "copyright"`, or if no meta tag information exists, a text node that contains the copyright \(`©`\) symbol.</span></span>  <span data-ttu-id="30601-152">閲覧表示では、記事の本文の最後に著作権の情報が表示されます。このサイズは、メインの本文よりも小さいフォント サイズで表示されます。</span><span class="sxs-lookup"><span data-stu-id="30601-152">Reading view displays copyright information at the end of the article main body, styled using a smaller font size than the main body text.</span></span>  

```html
<meta name="copyright" content="Your copyright information">
```  

## <span data-ttu-id="30601-153">閲覧表示からオプトアウトする</span><span class="sxs-lookup"><span data-stu-id="30601-153">Opting out of Reading View</span></span>  

<span data-ttu-id="30601-154">閲覧表示にとってうまくいかないコンテンツが見つからない場合は、次のメタグを使用してこの機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="30601-154">If you feel your content is not a good fit for Reading view, you can use the following meta tag to opt out of this feature:</span></span>  

```html
<meta name="IE_RM_OFF" content="true">
```  

<span data-ttu-id="30601-155">このタグを使用すると、ユーザー **がページ** を表示したときに、閲覧ビュー ボタンはアドレス バーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="30601-155">With this tag, the **Reading view** button will not appear in the address bar when your users view your page.</span></span>  
