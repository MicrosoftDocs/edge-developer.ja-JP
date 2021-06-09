---
description: Tab キーと Enter キーを使用してキーボードのサポートを確認します。
title: Tab キーと Enter キーを使用してキーボードのサポートを確認する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 48151e16a9059b5ebaadca36f29447d4ad3be8c7
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597491"
---
# <a name="check-for-keyboard-support-by-using-the-tab-and-enter-keys"></a><span data-ttu-id="41250-104">Tab キーと Enter キーを使用してキーボードのサポートを確認する</span><span class="sxs-lookup"><span data-stu-id="41250-104">Check for keyboard support by using the Tab and Enter keys</span></span>


<span data-ttu-id="41250-105">すべてのユーザーがポインターまたはタッチ デバイスを持っている必要があります。また、すべてのユーザーが作成した Web プロジェクトを表示できる場合ではありません。</span><span class="sxs-lookup"><span data-stu-id="41250-105">Not all users have a pointer or touch device, and not all users can see the web projects we create.</span></span>  <span data-ttu-id="41250-106">これは、ユーザー インターフェイスが少なくともキーボードで動作することが重要な理由です。</span><span class="sxs-lookup"><span data-stu-id="41250-106">This is why it is important that the user interface works at least with a keyboard.</span></span>  <span data-ttu-id="41250-107">キーを使用して、Web ページ上の各フォーム コントロールにフォーカスを移動し、キーを使用してフォームを `Tab` `Enter` 送信できます。</span><span class="sxs-lookup"><span data-stu-id="41250-107">Ensure you can use the `Tab` key to move the focus to each form control on a webpage, and ensure you can use the `Enter` key to submit forms.</span></span>

<span data-ttu-id="41250-108">キーボード ユーザーの Web ページの使いやすさは、次の方法でテストできます。</span><span class="sxs-lookup"><span data-stu-id="41250-108">You can test the usability of a webpage for keyboard users in several ways:</span></span>
*  <span data-ttu-id="41250-109">キーボード、特に 、、 `Tab` および `Shift` + `Tab` キーを使用 `Enter` します。</span><span class="sxs-lookup"><span data-stu-id="41250-109">By using the keyboard, particularly the `Tab`, `Shift`+`Tab`, and `Enter` keys.</span></span>  <span data-ttu-id="41250-110">この方法については、この記事で説明します。</span><span class="sxs-lookup"><span data-stu-id="41250-110">This approach is described in this article.</span></span>
*  <span data-ttu-id="41250-111">[検査] ツールを使用して、個々の要素のキーボードサポートを **確認** します。</span><span class="sxs-lookup"><span data-stu-id="41250-111">Check for keyboard support for an individual element by using the **Inspect** tool.</span></span>  <span data-ttu-id="41250-112">[検査] ツールの情報オーバーレイには、 **キーボード** フォーカス可能な行を含むアクセシビリティ **セクションが含** まれます。</span><span class="sxs-lookup"><span data-stu-id="41250-112">The Inspect tool's information overlay includes an **Accessibility** section that includes a **Keyboard-focusable** row.</span></span>  
*  <span data-ttu-id="41250-113">キーボード サポート **の問題** については、[問題] レポート **の [アクセシビリティ** ] セクションを確認します。</span><span class="sxs-lookup"><span data-stu-id="41250-113">Check the **Issues** report's **Accessibility** section for keyboard support issues.</span></span>

<span data-ttu-id="41250-114">マウスではなくキーボードを使用してデモ ページでアクセシビリティの問題を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="41250-114">To check the demo page for accessibility issues by using a keyboard rather than a mouse, perform the following steps:</span></span>

1.  <span data-ttu-id="41250-115">ブラウザーの [新しいタブで][DevToolsA11yErrorsDemopage] アクセシビリティ テストデモ Web ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="41250-115">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser.</span></span>

1.  <span data-ttu-id="41250-116">キーボードを使用してデモ ドキュメントを移動し、キーを使用して要素から `Tab` `Shift` + `Tab` 要素に移動します。</span><span class="sxs-lookup"><span data-stu-id="41250-116">Use a keyboard to navigate the demo document, using the `Tab` and `Shift`+`Tab` keys to jump from element to element.</span></span>  <span data-ttu-id="41250-117">デモ Web ページで、キー `Tab` が最初にセクション内の検索フォームにフォーカスを移動 `header` します。</span><span class="sxs-lookup"><span data-stu-id="41250-117">On the demo webpage, the `Tab` key first moves focus to the search form in the `header` section.</span></span>

1.  <span data-ttu-id="41250-118">ボタン `Tab` にフォーカスを置く場合は選択し、フォーカス `Enter` されたボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="41250-118">Select `Tab` to put focus on a button, and then select `Enter` to click the focused button.</span></span>  <span data-ttu-id="41250-119">たとえば、デモ ページで[検索] フィールドにフォーカスを置くを選択し、検索を送信 `Tab` \*\*\*\* `Enter` するを選択します。</span><span class="sxs-lookup"><span data-stu-id="41250-119">For example, in the demo page, select `Tab` to put focus on the **Search** field, and then select `Enter` to submit the search.</span></span>  <span data-ttu-id="41250-120">この方法では、移動ボタンを選択した場合と同じ結果 **が得** られます。</span><span class="sxs-lookup"><span data-stu-id="41250-120">This approach produces the same result as selecting the **go** button.</span></span>  <span data-ttu-id="41250-121">[検索 `Enter` ] フォームの送信を **選択すると** 、正しく動作します。</span><span class="sxs-lookup"><span data-stu-id="41250-121">Selecting `Enter` to send the **Search** form works correctly.</span></span>

1.  <span data-ttu-id="41250-122">もう一 `Tab` 度選択します。</span><span class="sxs-lookup"><span data-stu-id="41250-122">Select `Tab` again.</span></span>  <span data-ttu-id="41250-123">フォーカスを置く次の要素は、アウトライン\*\*\*\* で示されている Web ページのセクションの最初の [その他] `content` リンクです。</span><span class="sxs-lookup"><span data-stu-id="41250-123">The next element you put focus on is the first **More** link in the `content` section of the webpage, as indicated by an outline.</span></span>
    
    :::image type="complex" source="../media/a11y-testing-keyboard-focus-on-element.msft.png" alt-text="キーボードと 'Tab' キーを使用してドキュメントを移動します。 ドキュメント内のリンクにフォーカスが表示されます。" lightbox="../media/a11y-testing-keyboard-focus-on-element.msft.png":::
        <span data-ttu-id="41250-126">キーボードとタブ キーを使用してドキュメントを移動する。</span><span class="sxs-lookup"><span data-stu-id="41250-126">Navigating the document using the keyboard and the tab key.</span></span> <span data-ttu-id="41250-127">ドキュメント内のリンクにフォーカスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41250-127">Focus is shown on a link in the document.</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="41250-128">最後 `Tab` の [その他] リンクを渡すまで、さらに数回 **選択** します。</span><span class="sxs-lookup"><span data-stu-id="41250-128">Select `Tab` several more times until you pass the last **More** link.</span></span>  <span data-ttu-id="41250-129">ページが上にスクロールし、ページの要素に表示されているように見えるが、どの要素かを知る方法はありません。</span><span class="sxs-lookup"><span data-stu-id="41250-129">The page scrolls up and you seem to be on an element of the page, but there's no way to tell which element it is.</span></span>

1.  <span data-ttu-id="41250-130">左下の URL に注意してください。</span><span class="sxs-lookup"><span data-stu-id="41250-130">Notice the URL in the bottom left.</span></span>  <span data-ttu-id="41250-131">画面の左下を見た場合 (またはスクリーン リーダーを使用する場合) は、ブラウザーに Cats リンクがポイントする URL \*\*\*\* `#cats` () が表示されるので、青いリンクを含むサイドバー ナビゲーション メニューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="41250-131">If you look to the bottom left of the screen (or if you use a screen reader), you realize that you are on the sidebar navigation menu with blue links, because the browser shows the URL that the **Cats** link points to (`#cats`).</span></span>

    :::image type="complex" source="../media/a11y-testing-lack-of-focus-style.msft.png" alt-text="フォーカス スタイルが不足すると、現在ドキュメントのどこにいるかはわかりません。 唯一のヒントは、画面の左下隅にリンク ターゲットが表示される場合です。" lightbox="../media/a11y-testing-lack-of-focus-style.msft.png":::
        <span data-ttu-id="41250-134">フォーカス スタイルが不足すると、現在ドキュメントのどこにいるかはわかりません。</span><span class="sxs-lookup"><span data-stu-id="41250-134">A lack of focus style makes it impossible to know where you currently are in the document.</span></span> <span data-ttu-id="41250-135">唯一のヒントは、画面の左下隅にリンク ターゲットを表示します。</span><span class="sxs-lookup"><span data-stu-id="41250-135">The only hint is the display of the link target in the bottom left corner of the screen.</span></span>
    :::image-end:::

1.  <span data-ttu-id="41250-136">もう `Tab` 一度選択して、寄付フォームの入力フィールドにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="41250-136">Select `Tab` again, to get to the entry field in the donation form.</span></span>  <span data-ttu-id="41250-137">ただし、 を選択すると、テキスト ボックスの上のボタンにアクセスできない `Tab` 。</span><span class="sxs-lookup"><span data-stu-id="41250-137">However, you can't reach the buttons above the textbox by selecting `Tab`.</span></span> <span data-ttu-id="41250-138">キーボードを使用して **、50、100、または** \*\*\*\* **200**のボタンにフォーカスを置いて選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="41250-138">You can't use the keyboard to put focus on the **50**, **100**, or **200** buttons and then select them.</span></span>  <span data-ttu-id="41250-139">また、選択 `Enter` しても、寄付フォームは送信されます。</span><span class="sxs-lookup"><span data-stu-id="41250-139">Also, selecting `Enter` doesn't submit the donation form.</span></span>

    :::image type="complex" source="../media/a11y-testing-form-field-with-outline.msft.png" alt-text="寄附フォームのキーボードアクセス可能な要素は、テキスト入力フィールドのみです。" lightbox="../media/a11y-testing-form-field-with-outline.msft.png":::
        <span data-ttu-id="41250-141">寄附フォームのキーボードアクセス可能な要素は、テキスト入力フィールドのみです。</span><span class="sxs-lookup"><span data-stu-id="41250-141">The only keyboard-accessible element in the donation form is the text entry field</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="41250-142">もう一度選択すると、ページの上部のナビゲーション バーにフォーカスが置き、ホーム 、Adopt `Tab` a \*\*\*\* **Pet、Donate、Jobs、** および About Us\*\*\*\* のメニュー ボタンが**表示されます**。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="41250-142">Selecting `Tab` again puts focus on the top navigation bar of the page, with menu buttons for **Home**, **Adopt a Pet**, **Donate**, **Jobs**, and **About Us**.</span></span>  <span data-ttu-id="41250-143">フォーカス `Tab` の `Shift` + アウトラインで示されているメニュー ボタンにフォーカスを置くまたは `Tab` 選択します。</span><span class="sxs-lookup"><span data-stu-id="41250-143">Select `Tab` or `Shift`+`Tab` to put focus on a menu button, as indicated by a focus outline.</span></span>  <span data-ttu-id="41250-144">次に `Enter` 、Web ページのそのセクションにアクセスする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="41250-144">Then select `Enter` to access that section of the webpage.</span></span>

    :::image type="complex" source="../media/a11y-testing-menu-with-outline.msft.png" alt-text="メイン メニューには強調表示とフォーカスアウトラインが表示され、キーボードにアクセスできます。" lightbox="../media/a11y-testing-menu-with-outline.msft.png":::
        <span data-ttu-id="41250-146">メイン メニューには強調表示とフォーカスアウトラインが表示され、キーボードにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="41250-146">The main menu has a highlight and a focus outline, and thus is keyboard-accessible</span></span>
    :::image-end:::
    
<span data-ttu-id="41250-147">上記のチュートリアルに基づいて、修正が必要な次の問題が見つかりました。</span><span class="sxs-lookup"><span data-stu-id="41250-147">Based on the above walkthrough, we found the following issues that need to be fixed.</span></span>

*  <span data-ttu-id="41250-148">キーボードを使用する場合、サイドバーナビゲーション メニューの青いリンクは、フォーカスがあるリンクを視覚的に示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="41250-148">When using a keyboard, the blue links of the sidebar navigation menu don't visually indicate which link has focus.</span></span>  <span data-ttu-id="41250-149">詳細については、「サイドバー メニューのキーボード フォーカスの表示不足を分析 [する」に移動します](test-analyze-no-focus-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="41250-149">For more information, navigate to [Analyze the lack of indication of keyboard focus in a sidebar menu](test-analyze-no-focus-indicator.md).</span></span>

*  <span data-ttu-id="41250-150">寄付フォームでは、金額ボタンと [寄付] **ボタンは** キーボードでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="41250-150">In the donation form, the amount buttons and the **Donate** button don't work with a keyboard.</span></span>  <span data-ttu-id="41250-151">詳細については、「フォームでのキーボードサポートの不足 [を分析する」に移動します](test-analyze-no-keyboard-support.md)。</span><span class="sxs-lookup"><span data-stu-id="41250-151">For more information, navigate to [Analyze the lack of keyboard support in a form](test-analyze-no-keyboard-support.md).</span></span>

*  <span data-ttu-id="41250-152">ページのセクションを通じたキーボード アクセスの順序が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="41250-152">The order of the keyboard access through sections of the page is not correct.</span></span>  <span data-ttu-id="41250-153">サイドバーのナビゲーション メニュー **に移動する** 前に、ドキュメント内のすべての [その他] リンクを移動します。</span><span class="sxs-lookup"><span data-stu-id="41250-153">You navigate through all the **More** links in the document before you reach the sidebar navigation menu.</span></span>  <span data-ttu-id="41250-154">キーがサイドバーのナビゲーション メニューにフォーカスを置くまでには、すべてのページ コンテンツ `Tab` が既に走査されています。</span><span class="sxs-lookup"><span data-stu-id="41250-154">By the time the `Tab` key puts focus on the sidebar navigation menu, you have already traversed all the page content.</span></span> <span data-ttu-id="41250-155">サイドバーのナビゲーション メニューは、ページ コンテンツに簡単にアクセスできるように意図されています。</span><span class="sxs-lookup"><span data-stu-id="41250-155">The sidebar navigation menu was intended to provide easy access to the page content.</span></span>  <span data-ttu-id="41250-156">この問題を解決する方法の詳細については、「ソース オーダー ビューアーを使用してキーボード [サポートをテストする」に移動します](test-tab-key-source-order-viewer.md)。</span><span class="sxs-lookup"><span data-stu-id="41250-156">For more information on how to solve this issue, navigate to [Test keyboard support using the Source Order Viewer](test-tab-key-source-order-viewer.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="41250-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="41250-157">See also</span></span>

*  [<span data-ttu-id="41250-158">DevTools を使用したアクセシビリティ テストの概要</span><span class="sxs-lookup"><span data-stu-id="41250-158">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="41250-159">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="41250-159">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
