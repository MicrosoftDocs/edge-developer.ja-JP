---
description: ページのセクションのタブオーダーをすばやく表示するには、[ユーザー補助] ツールの [スタイル] タブの右側にある [ソースオーダー ビューアー] を使用します。
title: ソース オーダー ビューアーを使用したキーボード サポートのテスト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 7e90221b581280a6eb63cee4d073622a80871903
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597492"
---
# <a name="test-keyboard-support-using-the-source-order-viewer"></a><span data-ttu-id="e669f-104">ソース オーダー ビューアーを使用したキーボード サポートのテスト</span><span class="sxs-lookup"><span data-stu-id="e669f-104">Test keyboard support using the Source Order Viewer</span></span>

<span data-ttu-id="e669f-105">ドキュメントのソースの順序は、支援テクノロジにとって重要であり、レンダリングされたページに要素が表示される順序とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e669f-105">The source order of a document is important for assistive technology, and can be different than the order in which elements appear on the rendered page.</span></span>  <span data-ttu-id="e669f-106">CSS を使用すると、視覚的な方法でページ要素の順序を変更できますが、スクリーン リーダーなどの支援テクノロジがページ要素を同じ順序で表すという意味ではありません。</span><span class="sxs-lookup"><span data-stu-id="e669f-106">Using CSS, you can re-order page elements in a visual way, but that doesn't mean that assistive technology such as screen readers would represent page elements in the same order.</span></span>  

<span data-ttu-id="e669f-107">ドキュメントに論理的な順序を設定するには、ソース オーダー ビューアー\*\*\*\* を使用して、ドキュメントのソース コード内の順序を指定する番号で異なるページ要素にラベルを付けできます。</span><span class="sxs-lookup"><span data-stu-id="e669f-107">To ensure that the document has a logical order, you can use the **Source Order Viewer** to label different page elements with numbers that specify the order in the source code of the document.</span></span>  <span data-ttu-id="e669f-108">ソース**オーダー ビューアーは 、[** アクセシビリティ] タブ ([スタイル] タブの近く) にあります。 \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e669f-108">The **Source Order Viewer** is in the **Accessibility** tab (near the **Styles** tab).</span></span>


## <a name="analyzing-the-order-of-keyboard-access-through-sections-of-the-page"></a><span data-ttu-id="e669f-109">ページのセクションを通じてキーボード アクセスの順序を分析する</span><span class="sxs-lookup"><span data-stu-id="e669f-109">Analyzing the order of keyboard access through sections of the page</span></span>

<span data-ttu-id="e669f-110">アクセシビリティ[テストのデモ][DevToolsA11yErrorsDemopage]Web ページには、他のすべてのリンクをタブ化した後にのみキーボード ユーザーがサイドバー ナビゲーション メニューにアクセスする、直感に反するタブ**順序があります。**</span><span class="sxs-lookup"><span data-stu-id="e669f-110">The [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] has a counterintuitive tabbing order, where keyboard users access the sidebar navigation menu only after tabbing through all the **More** links.</span></span>  <span data-ttu-id="e669f-111">サイドバーのナビゲーション メニューは、ページ コンテンツの深部に到達するショートカットを意味します。</span><span class="sxs-lookup"><span data-stu-id="e669f-111">The sidebar navigation menu is meant to be a shortcut to reach deep into the page content.</span></span>  <span data-ttu-id="e669f-112">ただし、サイドバー ナビゲーション メニューに移動する前にページ全体を移動する必要がある場合、そのナビゲーション メニューはキーボード ユーザーには無効です。</span><span class="sxs-lookup"><span data-stu-id="e669f-112">But because you need to go through the entire page before you reach the sidebar navigation menu, that navigation menu is ineffective for keyboard users.</span></span>

<span data-ttu-id="e669f-113">デモ `Tab` ページの主な順序は次の場合です。</span><span class="sxs-lookup"><span data-stu-id="e669f-113">The `Tab` key order on the demo page is:</span></span>
1. <span data-ttu-id="e669f-114">[ **検索** ] フィールド、次に [ **検索** ] フィールドの [移動] **ボタンをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="e669f-114">The **Search** field, then the **go** button for the **Search** field.</span></span>
1. <span data-ttu-id="e669f-115">[ **猫]** セクションの **[その** 他] ボタンをクリックして、"Cats" Web ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e669f-115">The **More** button in the **Cats** section, to navigate to a "Cats" webpage.</span></span>  <span data-ttu-id="e669f-116">次に、 **その他の [** その他] ボタン (犬、羊、馬、そしてアルパカスの場合)。</span><span class="sxs-lookup"><span data-stu-id="e669f-116">Then the other **More** buttons, for Dogs, Sheep, Horses, and then Alpacas.</span></span>
1. <span data-ttu-id="e669f-117">サイドバー ナビゲーション メニューの青いリンク: **Cats**、 **Dogs**、 **Sheep**、 **Horses**、 then **Alpacas**。</span><span class="sxs-lookup"><span data-stu-id="e669f-117">The blue links of the sidebar navigation menu: **Cats**, **Dogs**, **Sheep**, **Horses**, and then **Alpacas**.</span></span>
1. <span data-ttu-id="e669f-118">[寄付] フォームの [寄付] テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="e669f-118">The donation textbox in the donation form.</span></span>
1. <span data-ttu-id="e669f-119">トップ ナビゲーション バーのボタン: **[ホーム**] **、[** ペットの採用] **、[寄付**] **、[** ジョブ] 、および [ユーザー情報] **の順に選択します**。</span><span class="sxs-lookup"><span data-stu-id="e669f-119">The buttons in the top navigation bar: **Home**, **Adopt a pet**, **Donate**, **Jobs**, and then **About Us**.</span></span>
1. <span data-ttu-id="e669f-120">ブラウザーのトップ オブ ウィンドウ インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="e669f-120">The browser's top-of-window interface.</span></span>

<span data-ttu-id="e669f-121">キーの順序がわかりにくいのは、キーボードを使用するときに発生する順序がドキュメントのソースの順序 `Tab` によって決まるという理由です。</span><span class="sxs-lookup"><span data-stu-id="e669f-121">The reason for the confusing `Tab` key order is that the order experienced when using a keyboard is determined by the source order of the document.</span></span>  <span data-ttu-id="e669f-122">キーボードを使用して経験した順序は、要素の属性を使用して変更できます。これは、その要素をソースの順序から `tabindex` 取り出します。</span><span class="sxs-lookup"><span data-stu-id="e669f-122">The order experienced using a keyboard can be modified using the `tabindex` attribute on elements, which takes that element out of the source order.</span></span>

<span data-ttu-id="e669f-123">ドキュメントのソース コードでは、Web ページのメイン コンテンツの後にサイドバー ナビゲーション メニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e669f-123">In the source code of the document, the sidebar navigation menu appears after the main content of the webpage.</span></span>  <span data-ttu-id="e669f-124">CSS は、Web ページのメイン コンテンツの大部分の上にサイドバー ナビゲーション メニューを配置するために使用しました。</span><span class="sxs-lookup"><span data-stu-id="e669f-124">CSS was used to position the sidebar navigation menu above most of the main content of the webpage.</span></span> 

<span data-ttu-id="e669f-125">ページ要素の順序をテストするには、[アクセシビリティ] タブの **[ソース** オーダー ビューアー **] を使用** します。 ソース **オーダー ビューアーは実験的** な機能です。</span><span class="sxs-lookup"><span data-stu-id="e669f-125">You can test the order of page elements by using the **Source Order Viewer** in the **Accessibility** tab.  The **Source Order Viewer** is an experimental feature.</span></span> <span data-ttu-id="e669f-126">詳細については、「Source [Order Viewer」に移動します](../experimental-features/index.md#source-order-viewer)。</span><span class="sxs-lookup"><span data-stu-id="e669f-126">For more information, navigate to [Source Order Viewer](../experimental-features/index.md#source-order-viewer).</span></span>


<span data-ttu-id="e669f-127">ソース オーダー ビューアーを有効にする方法:</span><span class="sxs-lookup"><span data-stu-id="e669f-127">To turn on the Source Order Viewer:</span></span>

1.  <span data-ttu-id="e669f-128">DevTools の右上にある [\( 設定**\)** ![ 設定 ](../media/settings-button-icon.msft.png) を選択します。</span><span class="sxs-lookup"><span data-stu-id="e669f-128">In DevTools, in the upper right, select the **Settings** \(![Settings button](../media/settings-button-icon.msft.png)\) button.</span></span>  

1.  <span data-ttu-id="e669f-129">[テスト**設定]** で、[実験]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e669f-129">Below **Settings**, select **Experiments**.</span></span>  

1.  <span data-ttu-id="e669f-130">[ソース注文 **ビューアー] チェック ボックスを** オンにします。</span><span class="sxs-lookup"><span data-stu-id="e669f-130">Select the **Source Order Viewer** checkbox.</span></span>

1.  <span data-ttu-id="e669f-131">[ページ] ページの右上隅にある **[設定]** を選択\*\*\*\* して、ページを閉設定します。</span><span class="sxs-lookup"><span data-stu-id="e669f-131">In the upper-right corner of the **Settings** page, select **X** to close the Settings page.</span></span>  <span data-ttu-id="e669f-132">DevTools の上部にあるメッセージ 1 つ以上の設定が変更され、再読み込みを有効 **にする必要があります。**</span><span class="sxs-lookup"><span data-stu-id="e669f-132">At the top of DevTools, the message **One or more settings have changed which require a reload to take effect.**</span></span> <span data-ttu-id="e669f-133">が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e669f-133">is displayed.</span></span>  <span data-ttu-id="e669f-134">**[DevTools の再読み込み] ボタンを選択**します。</span><span class="sxs-lookup"><span data-stu-id="e669f-134">Select the **Reload DevTools** button.</span></span>



<span data-ttu-id="e669f-135">ソース オーダー ビューアーをアクティブ化して使用するには、デモ ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="e669f-135">To activate and use the Source Order Viewer, with the demo page:</span></span>

1.  <span data-ttu-id="e669f-136">アクセシビリティ テスト [のデモ Web ページを新しい][DevToolsA11yErrorsDemopage] タブで開きます。 次に **、[F12] を** 選択して DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="e669f-136">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab.  Then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="e669f-137">[要素 **]** ツールの [スタイル] タブの **右側にある** [アクセシビリティ] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="e669f-137">In the **Elements** tool, to the right of the **Styles** tab, select the **Accessibility** tab.</span></span>

1.  <span data-ttu-id="e669f-138">[ソース注文 **ビューアー] セクションで** 、[ソースの順序を **表示する] チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="e669f-138">In the **Source Order Viewer** section, select the **Show source order** checkbox.</span></span>  <span data-ttu-id="e669f-139">レンダリングされた Web ページには、ソース ファイル内のコード行の順序によって制御される順序を示す数値 `Tab` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e669f-139">In the rendered webpage, numbers appear, indicating the `Tab` order as controlled by the order of lines of code in the source file.</span></span>

1.  <span data-ttu-id="e669f-140">要素ツールの DOM ツリー **で** 、要素などの主要なレイアウト要素を選択 `header` します。</span><span class="sxs-lookup"><span data-stu-id="e669f-140">In the DOM tree in the **Elements** tool, select a major layout element, such as the `header` element.</span></span>  <span data-ttu-id="e669f-141">レンダリングされたページのセクションに数値オーバーレイが表示され、さまざまな要素のソースの順序が示されます。</span><span class="sxs-lookup"><span data-stu-id="e669f-141">Numeric overlays are now displayed on sections of the rendered page, which indicate the source order of the different elements.</span></span> 

    :::image type="complex" source="../media/a11y-testing-source-order-viewer.msft.png" alt-text="ソース オーダー ビューアーをアクティブ化すると、ページ上のオーバーレイとしてソース内の要素の順序が表示されます。" lightbox="../media/a11y-testing-source-order-viewer.msft.png":::
        <span data-ttu-id="e669f-143">ソース オーダー ビューアー **をアクティブ化すると** 、ページ上のオーバーレイとしてソース内の要素の順序が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e669f-143">Activating the **Source Order Viewer** shows the order of the elements in the source as overlays on the page</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="e669f-144">ページをスクロールすると、ページ フッター セクションを含むすべての数値オーバーレイが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e669f-144">Scroll the page to see all of the numeric overlays, including on the page footer section.</span></span>


## <a name="see-also"></a><span data-ttu-id="e669f-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="e669f-145">See also</span></span>

*  [<span data-ttu-id="e669f-146">DevTools を使用したアクセシビリティ テストの概要</span><span class="sxs-lookup"><span data-stu-id="e669f-146">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="e669f-147">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="e669f-147">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
