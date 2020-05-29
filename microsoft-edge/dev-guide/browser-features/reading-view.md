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
# <span data-ttu-id="dd98b-104">読み取りビュー</span><span class="sxs-lookup"><span data-stu-id="dd98b-104">Reading view</span></span>

<span data-ttu-id="dd98b-105">Microsoft Edge には、ページ上の関連性のない、または他の二次的なコンテンツを気にせずに、web ページをより効率的に使用できるようにするための*閲覧表示*が用意されています。</span><span class="sxs-lookup"><span data-stu-id="dd98b-105">Microsoft Edge provides a *reading view* for a more streamlined, book-like reading experience of webpages without the distraction of unrelated or other secondary content on the page.</span></span> <span data-ttu-id="dd98b-106">閲覧表示は、**アドレスバー**の (または Ctrl キーを**押し**ながら R を押しながら)**閲覧表示**(ブックアイコン) ボタンでオンまたはオフにすることができ  +  **Shift**  +  **R**ます。</span><span class="sxs-lookup"><span data-stu-id="dd98b-106">Reading view can be toggled on or off from the **Reading view** (book icon) button on the **address bar** (or with **Ctrl** + **Shift** + **R**).</span></span> <span data-ttu-id="dd98b-107">閲覧表示では、次のメタデータがページから抽出されます。</span><span class="sxs-lookup"><span data-stu-id="dd98b-107">Reading view extracts the following metadata from a page:</span></span>

* <span data-ttu-id="dd98b-108">タイトル</span><span class="sxs-lookup"><span data-stu-id="dd98b-108">Title</span></span>
* <span data-ttu-id="dd98b-109">著者</span><span class="sxs-lookup"><span data-stu-id="dd98b-109">Author</span></span>
* <span data-ttu-id="dd98b-110">日付</span><span class="sxs-lookup"><span data-stu-id="dd98b-110">Date</span></span>
* <span data-ttu-id="dd98b-111">発行元</span><span class="sxs-lookup"><span data-stu-id="dd98b-111">Publisher</span></span>
* <span data-ttu-id="dd98b-112">主要イメージ</span><span class="sxs-lookup"><span data-stu-id="dd98b-112">Dominant image(s)</span></span>
* <span data-ttu-id="dd98b-113">主要な画像のキャプション</span><span class="sxs-lookup"><span data-stu-id="dd98b-113">Captions of dominant image(s)</span></span>
* <span data-ttu-id="dd98b-114">セカンダリイメージ</span><span class="sxs-lookup"><span data-stu-id="dd98b-114">Secondary images</span></span>
* <span data-ttu-id="dd98b-115">ページのメインテキストコンテンツ</span><span class="sxs-lookup"><span data-stu-id="dd98b-115">Main text content of the page</span></span>
* <span data-ttu-id="dd98b-116">著作権</span><span class="sxs-lookup"><span data-stu-id="dd98b-116">Copyright</span></span>

<span data-ttu-id="dd98b-117">ユーザーは、Microsoft Edge の [**設定**] パネルでページのコントラストとフォントサイズを調整することができます。</span><span class="sxs-lookup"><span data-stu-id="dd98b-117">Users can then adjust the page contrast and font size from the Microsoft Edge **Settings** panel.</span></span>

## <span data-ttu-id="dd98b-118">メタデータの抽出</span><span class="sxs-lookup"><span data-stu-id="dd98b-118">Metadata extraction</span></span>


<span data-ttu-id="dd98b-119">ここでは、閲覧表示によってレンダリングされるページメタデータの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd98b-119">Here are details of the page metadata rendered by reading view.</span></span>

### <span data-ttu-id="dd98b-120">タイトル</span><span class="sxs-lookup"><span data-stu-id="dd98b-120">Title</span></span>

<span data-ttu-id="dd98b-121">閲覧表示で記事のタイトルをレンダリングするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dd98b-121">To ensure Reading view renders your article's title:</span></span>

* <span data-ttu-id="dd98b-122">ヘッダーに**タイトル**要素を含める</span><span class="sxs-lookup"><span data-stu-id="dd98b-122">Include a **title** element in your header</span></span>
* <span data-ttu-id="dd98b-123">次のメタタグを含める</span><span class="sxs-lookup"><span data-stu-id="dd98b-123">Include a meta tag with</span></span> `name="title"`
* <span data-ttu-id="dd98b-124">記事本文のタイトルテキストと、メタタグのコンテンツ文字列を一致させます。</span><span class="sxs-lookup"><span data-stu-id="dd98b-124">Match the title text in your article body with the content string of your meta tag.</span></span> <span data-ttu-id="dd98b-125">`|`コンテンツ文字列のパイプリーダービューがアクティブにならないように、代わりに hypens を使用してみてください `-` 。</span><span class="sxs-lookup"><span data-stu-id="dd98b-125">Pipes `|` in your content string prevent the reader view from becoming active, try using hypens `-` instead.</span></span>

### <span data-ttu-id="dd98b-126">著者</span><span class="sxs-lookup"><span data-stu-id="dd98b-126">Author</span></span>

<span data-ttu-id="dd98b-127">閲覧表示では、要素を検索 `class = "byline-name"` します。</span><span class="sxs-lookup"><span data-stu-id="dd98b-127">Reading View will look for an element with `class = "byline-name"`.</span></span> <span data-ttu-id="dd98b-128">ベストプラクティスとして、タイトルの後と記事本文の前に作成者の名前を配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dd98b-128">Best practice is to place the author name after the title and before the article body.</span></span>

```html
<div class="byline-name">Author name</div>
```

### <span data-ttu-id="dd98b-129">日付</span><span class="sxs-lookup"><span data-stu-id="dd98b-129">Date</span></span>

<span data-ttu-id="dd98b-130">閲覧表示では、publisher と日付の情報が同じ行にまとめて表示され、この情報を強調するためのスタイルが追加されます。</span><span class="sxs-lookup"><span data-stu-id="dd98b-130">Reading view will render the publisher and date information together on the same line, with additional styling to highlight this information.</span></span> <span data-ttu-id="dd98b-131">記事の発行日は、文字列に表示されるとおりに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd98b-131">The article's publishing date will render exactly as it appears in the string.</span></span> <span data-ttu-id="dd98b-132">閲覧表示は特定の日付形式に変換されません。</span><span class="sxs-lookup"><span data-stu-id="dd98b-132">Reading view does not convert to a specific date format.</span></span>

<span data-ttu-id="dd98b-133">記事の本文に日付があり、閲覧表示で表示する必要がある場合は、次のように、日付を含む要素をクラスに割り当て `'dateline'` ます。</span><span class="sxs-lookup"><span data-stu-id="dd98b-133">If you have a date in your article body and would like Reading view to render it, assign the element containing the date with the class `'dateline'`:</span></span>

```html
<div class="dateline"> Wednesday, September 18, 2013 7:38 AM </div>
```

<span data-ttu-id="dd98b-134">記事の本文に日付が表示されておらず、閲覧表示で日付を表示したい場合は、meta タグを使用し `name='displaydate'` ます。</span><span class="sxs-lookup"><span data-stu-id="dd98b-134">If you don't have a date in the article body but would like Reading view to render the date, use the meta tag `name='displaydate'`:</span></span>

```html
<meta name="displaydate" content=" Wednesday, September 18, 2013 7:38 AM ">
```

### <span data-ttu-id="dd98b-135">発行元</span><span class="sxs-lookup"><span data-stu-id="dd98b-135">Publisher</span></span>

<span data-ttu-id="dd98b-136">閲覧表示では、publisher の情報を表示するために、 *Open Graph*プロトコルが検索され `"og:site_name"` ます。</span><span class="sxs-lookup"><span data-stu-id="dd98b-136">Reading view will look for the *Open Graph* protocol `"og:site_name"` to render the publisher information.</span></span> <span data-ttu-id="dd98b-137">また、 `source_organization` `publisher` どの html タグでも、ページ上の publisher 情報のセカンダリインジケーターとして属性を検索し、属性を探します。</span><span class="sxs-lookup"><span data-stu-id="dd98b-137">It also looks for `source_organization` and `publisher` attributes in any html tag as a secondary indicator of publisher information on the page.</span></span> <span data-ttu-id="dd98b-138">Publisher のテキストは、[閲覧表示] ページのハイパーリンクスタイルを使用して、ページの URL にハイパーリンクされます。</span><span class="sxs-lookup"><span data-stu-id="dd98b-138">The publisher text will be hyperlinked to the URL of page using the Reading view page hyperlink style.</span></span>

```html
<meta content="Name of organization source" property="og:site_name">
```

### <span data-ttu-id="dd98b-139">画像</span><span class="sxs-lookup"><span data-stu-id="dd98b-139">Images</span></span>

<span data-ttu-id="dd98b-140">閲覧表示では、幅 >= 400px、縦横比 >= 1/3 and =< 3.0 のほとんどの raw 画像がキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="dd98b-140">Reading view captures most raw images with width >= 400px and aspect ratio >= 1/3 and =< 3.0.</span></span> <span data-ttu-id="dd98b-141">これらの寸法を満たしていない画像はまだ抽出されている可能性があります。たとえば、幅が400px より小さく、キャプションがある画像などです。</span><span class="sxs-lookup"><span data-stu-id="dd98b-141">Images that do not meet these dimensions may still be extracted, such as images that are smaller than 400px in width but have captions.</span></span> <span data-ttu-id="dd98b-142">最初の対象となる画像は、記事の主要な画像になります。</span><span class="sxs-lookup"><span data-stu-id="dd98b-142">The first eligible image becomes the dominant image of the article.</span></span> <span data-ttu-id="dd98b-143">主要な画像は、コンテンツの最初の部分と、すべての列の幅としてレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="dd98b-143">The dominant image is rendered as the first piece of content and given full column width.</span></span> <span data-ttu-id="dd98b-144">次の画像はすべて、記事内のインライン画像としてレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="dd98b-144">All following images are rendered as inline images within the article.</span></span>

### <span data-ttu-id="dd98b-145">字幕</span><span class="sxs-lookup"><span data-stu-id="dd98b-145">Captions</span></span>

<span data-ttu-id="dd98b-146">ベストプラクティスとして、3つの入れ子になった[figcaption](https://msdn.microsoft.com/library/gg593037(v=vs.85).aspx)タグを持たない[図](https://msdn.microsoft.com/library/gg593038(v=vs.85).aspx)のタグに画像を配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dd98b-146">Best practice is to place images in [figure](https://msdn.microsoft.com/library/gg593038(v=vs.85).aspx) tags with no more than two nested [figcaption](https://msdn.microsoft.com/library/gg593037(v=vs.85).aspx) tags.</span></span>

### <span data-ttu-id="dd98b-147">本文</span><span class="sxs-lookup"><span data-stu-id="dd98b-147">Body</span></span>

<span data-ttu-id="dd98b-148">ページのすべての本文のテキストを閲覧表示で確実にキャプチャするために、ほとんどの記事のテキストを同じフォントサイズと DOM 深度にしておくことができます。</span><span class="sxs-lookup"><span data-stu-id="dd98b-148">To ensure that all the body text of your page is captured by Reading view, it helps to keep most of the article text the same font size and DOM depth.</span></span> <span data-ttu-id="dd98b-149">閲覧表示アルゴリズムでは、publishers が行または単語に自由に追加できるように、このルールによって一定の誤差を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="dd98b-149">The reading view algorithm allows for some deviation from this rule so publishers can have the freedom to add emphasis to lines or words.</span></span>

### <span data-ttu-id="dd98b-150">著作権</span><span class="sxs-lookup"><span data-stu-id="dd98b-150">Copyright</span></span>

<span data-ttu-id="dd98b-151">閲覧表示では、meta タグで示されている著作権情報が抽出され `name = "copyright"` 、メタタグ情報が存在しない場合は、著作権 (**©**) 記号を含むテキストノードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd98b-151">Reading view extracts and displays copyright information denoted by meta tags with `name = "copyright"`, or if no meta tag information exists, a text node that contains the copyright (**©**) symbol.</span></span> <span data-ttu-id="dd98b-152">[閲覧表示] は、本文の本文より小さいフォントサイズでスタイルが適用された、記事の本文の最後に著作権情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="dd98b-152">Reading view displays copyright information at the end of the article main body, styled using a smaller font size than the main body text.</span></span>

```html
<meta name="copyright" content="Your copyright information">
```

## <span data-ttu-id="dd98b-153">閲覧表示を終了する</span><span class="sxs-lookup"><span data-stu-id="dd98b-153">Opting out of Reading View</span></span>


<span data-ttu-id="dd98b-154">閲覧表示に適していないコンテンツの場合は、次の meta タグを使用してこの機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="dd98b-154">If you feel your content is not a good fit for Reading view, you can use the following meta tag to opt out of this feature:</span></span>

```html
<meta name="IE_RM_OFF" content="true">
```

<span data-ttu-id="dd98b-155">このタグを使用すると、ユーザーがページを表示したときに、[**閲覧表示**] ボタンがアドレスバーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="dd98b-155">With this tag, the **Reading view** button will not appear in the address bar when your users view your page.</span></span>
