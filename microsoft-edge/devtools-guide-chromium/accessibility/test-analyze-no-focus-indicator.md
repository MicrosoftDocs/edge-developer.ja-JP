---
description: リンク上のフォーカス状態に対する CSS 擬似クラス ルールが欠けているので、サイドバー メニューでキーボード フォーカスが表示されなかっているのを分析し、リンクにアウトライン設定がないリンクを組み合わせたもの。
title: サイドバー メニューのキーボード フォーカスの表示不足を分析する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 3626de9bdc2cce266efafe4b1b2e8fff501a74f7
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597542"
---
# <a name="analyze-the-lack-of-indication-of-keyboard-focus-in-a-sidebar-menu"></a><span data-ttu-id="67009-104">サイドバー メニューのキーボード フォーカスの表示不足を分析する</span><span class="sxs-lookup"><span data-stu-id="67009-104">Analyze the lack of indication of keyboard focus in a sidebar menu</span></span>

<!-- Inspect tool, and CSS rules: pseudo-classes for states -->

<span data-ttu-id="67009-105">アクセシビリティ テストのデモ ページでは、キーボードを使用する場合、青いリンクを含むサイドバー ナビゲーション メニューは、フォーカスのあるリンクを視覚的に示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="67009-105">In the accessibility-testing demo page, the sidebar navigation menu with blue links doesn't visually indicate which link has focus, when using a keyboard.</span></span>  <span data-ttu-id="67009-106">サイドバー メニューがキーボード ユーザーにとってわかりにくい理由を確認するために、リンクアウトラインの CSS プロパティと共に、CSS 擬似クラスのルールを検索します `hover` `focus` 。</span><span class="sxs-lookup"><span data-stu-id="67009-106">To find out why the sidebar menu is confusing to keyboard users, we'll look for CSS pseudo-class rules for the `hover` and `focus` states, along with the CSS property for link outlines.</span></span>  

<span data-ttu-id="67009-107">この分析では、サイドバー ナビゲーション メニューのリンクにキーボード フォーカスが表示されるのが不十分な理由が分かっています。</span><span class="sxs-lookup"><span data-stu-id="67009-107">This analysis finds that the lack of indication of keyboard focus in the links of the sidebar navigation menu is because:</span></span>
*  <span data-ttu-id="67009-108">リンク `a` には、 の CSS プロパティ設定 `outline: none` があります。</span><span class="sxs-lookup"><span data-stu-id="67009-108">The `a` links have a CSS property setting of `outline: none`.</span></span>
*  <span data-ttu-id="67009-109">リンク `a` には、状態に対する CSS 擬似クラス ルール `:focus` が欠けている。</span><span class="sxs-lookup"><span data-stu-id="67009-109">The `a` links lack a CSS pseudo-class rule for the `:focus` state.</span></span>

<span data-ttu-id="67009-110">CSS に移動するには、[検査] ツールを\*\*\*\* 使用してサイドバー のナビゲーション メニューで青いリンクを強調表示し、そのリンクを定義する要素の DOM ツリーと CSS を `a` 表示します。</span><span class="sxs-lookup"><span data-stu-id="67009-110">To navigate to the CSS, we'll use the **Inspect** tool to highlight a blue link on the sidebar navigation menu, and then view the DOM tree and CSS for the `a` element that defines that link.</span></span>

1.  <span data-ttu-id="67009-111">ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="67009-111">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="67009-112">DevTools **の左上隅** にある [検査] アイコン \( Inspect icon \) ボタンを選択して、ボタンが強調表示 ![ ](../media/inspect-icon.msft.png) (青) にします。</span><span class="sxs-lookup"><span data-stu-id="67009-112">Select the **Inspect** \(![Inspect icon](../media/inspect-icon.msft.png)\) button in the top-left corner of DevTools so that the button is highlighted (blue).</span></span>

1.  <span data-ttu-id="67009-113">サイドバーのナビゲーション メニューの青 **い Cats** リンクの上にカーソルを合わせる。</span><span class="sxs-lookup"><span data-stu-id="67009-113">Hover over the blue **Cats** link in the sidebar navigation menu.</span></span>  <span data-ttu-id="67009-114">[検査] オーバーレイが表示され、要素が `a` キーボードフォーカス可能な状態を示します。</span><span class="sxs-lookup"><span data-stu-id="67009-114">The Inspect overlay appears, showing that the `a` element is keyboard-focusable.</span></span>  <span data-ttu-id="67009-115">ただし、オーバーレイでは、リンクにフォーカスがある場合に視覚的な表示が表示されるというメッセージは表示されます。</span><span class="sxs-lookup"><span data-stu-id="67009-115">But the overlay doesn't show that there's no visual indication when the link has focus.</span></span>

    <span data-ttu-id="67009-116">次に、このリンクの CSS スタイルを調します。</span><span class="sxs-lookup"><span data-stu-id="67009-116">Next, we'll inspect the CSS styling of this link.</span></span>
 
1.  <span data-ttu-id="67009-117">サイドバーの **ナビゲーション メニュー** で [Cats] リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="67009-117">Select the **Cats** link in the sidebar navigation menu.</span></span>  <span data-ttu-id="67009-118">[ **検査** ] ツールがオフにされ、[ **要素** ] ツールが開き、DOM ツリー内の `a` ノードが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="67009-118">The **Inspect** tool turns off, and the **Elements** tool opens, highlighting the `a` node in the DOM tree.</span></span>

1.  <span data-ttu-id="67009-119">[スタイル] **タブを選択** します。 CSS ルールが `#sidebar nav li a` 表示され、行番号へのリンクが表示されます `styles.css` 。</span><span class="sxs-lookup"><span data-stu-id="67009-119">Select the **Styles** tab.  The CSS rule `#sidebar nav li a` appears, along with a link to a line number in `styles.css`.</span></span>

    :::image type="complex" source="../media/a11y-testing-menu-link.msft.png" alt-text="メニュー内のリンクのソース コードと適用されたスタイルの検査" lightbox="../media/a11y-testing-menu-link.msft.png":::
        <span data-ttu-id="67009-121">メニュー内のリンクのソース コードと適用されたスタイルの検査</span><span class="sxs-lookup"><span data-stu-id="67009-121">Inspecting the source code and the applied styles of a link in the menu</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="67009-122">CSS ファイルへのリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="67009-122">Select the link to the CSS file.</span></span>  <span data-ttu-id="67009-123">CSS ファイルがソース ツール **内で開** きます。</span><span class="sxs-lookup"><span data-stu-id="67009-123">The CSS file opens within the **Sources** tool.</span></span>

    :::image type="complex" source="../media/a11y-testing-menu-link-styles.msft.png" alt-text="ソース ツールのリンクに適用されるスタイル" lightbox="../media/a11y-testing-menu-link-styles.msft.png":::
        <span data-ttu-id="67009-125">ソース ツールのリンクに適用されるスタイル</span><span class="sxs-lookup"><span data-stu-id="67009-125">The styles applied to the link in the Sources tool</span></span>
    :::image-end:::
    
<span data-ttu-id="67009-126">ページのスタイルには、マウスを使用するときにどのメニュー項目をオンにしているかを示す状態の CSS 擬似クラス ルール `hover` があります `#sidebar nav li a:hover` 。</span><span class="sxs-lookup"><span data-stu-id="67009-126">The styles of the page have a CSS pseudo-class rule for the `hover` state that indicates which menu item you are on when you use a mouse: `#sidebar nav li a:hover`.</span></span>  <span data-ttu-id="67009-127">ただし、キーボードを使用するときにどのメニュー項目を表示する状態の CSS 擬似クラス ルール `focus` はありません `#sidebar nav li a:focus` 。など。</span><span class="sxs-lookup"><span data-stu-id="67009-127">However, there is no CSS pseudo-class rule for the `focus` state to visually indicate which menu item you are on when you use a keyboard, such as `#sidebar nav li a:focus`.</span></span>

<span data-ttu-id="67009-128">また、リンクには CSS プロパティ設定 `outline: none` が .</span><span class="sxs-lookup"><span data-stu-id="67009-128">Also, notice that the links have a CSS property setting of `outline: none`.</span></span>  <span data-ttu-id="67009-129">これは、キーボードを使用して要素にフォーカスを当てるときに、ブラウザーが自動的に要素に追加するアウトラインを削除する一般的な方法です。</span><span class="sxs-lookup"><span data-stu-id="67009-129">This is a common practice, to remove the outline which browsers automatically add to elements when you focus on them using a keyboard.</span></span>  <span data-ttu-id="67009-130">スタイルを `focus` 使用しない場合は、ユーザーに混乱が生じます。</span><span class="sxs-lookup"><span data-stu-id="67009-130">Not using `focus` styling causes confusion for your users.</span></span>


## <a name="see-also"></a><span data-ttu-id="67009-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="67009-131">See also</span></span> 

*  [<span data-ttu-id="67009-132">フォーカスされている要素を追跡する</span><span class="sxs-lookup"><span data-stu-id="67009-132">Track which element has focus</span></span>](focus.md)
*  [<span data-ttu-id="67009-133">DevTools を使用したアクセシビリティ テストの概要</span><span class="sxs-lookup"><span data-stu-id="67009-133">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="67009-134">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="67009-134">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
