---
description: DevTools を使用したアクセシビリティの問題のテストの開始
title: DevTools を使用したアクセシビリティ テストの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 50661f68c7b3269d003bdc25f6a8098ae0e3ec89
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597562"
---
# <a name="overview-of-accessibility-testing-using-devtools"></a><span data-ttu-id="4da66-104">DevTools を使用したアクセシビリティ テストの概要</span><span class="sxs-lookup"><span data-stu-id="4da66-104">Overview of accessibility testing using DevTools</span></span>

<span data-ttu-id="4da66-105">この記事では、DevTools でアクセシビリティの問題をテストするために使用できる機能の一部について取り上げ、取り上げを行います。</span><span class="sxs-lookup"><span data-stu-id="4da66-105">In this article, we cover some of the features you can use in DevTools to test for accessibility problems.</span></span>  <span data-ttu-id="4da66-106">DevTools のさまざまな機能を使用してデモ ページのアクセシビリティの問題を検出し、それらを修正する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4da66-106">We go through using different features of DevTools to detect the accessibility problems in a demo page, and we discuss how to fix them.</span></span>  <span data-ttu-id="4da66-107">新しい [タブでデモ ページ][DevToolsA11yErrorsDemopage] を開き、自分で試し、一緒にテストできます。</span><span class="sxs-lookup"><span data-stu-id="4da66-107">Open the [demo page][DevToolsA11yErrorsDemopage] in a new tab to try it out yourself and you can test along.</span></span>

:::image type="complex" source="../media/a11y-testing-basics-demopage.msft.png" alt-text="この記事で使用されるデモ ページには、アクセシビリティに関する問題がいくつか含まれる" lightbox="../media/a11y-testing-basics-demopage.msft.png":::
    <span data-ttu-id="4da66-109">この記事で使用されるデモ ページには、アクセシビリティに関する問題がいくつか含まれる</span><span class="sxs-lookup"><span data-stu-id="4da66-109">The demo page used in this article with a few accessibility issues</span></span>
:::image-end:::


## <a name="automated-testing-by-using-the-issues-tool"></a><span data-ttu-id="4da66-110">問題ツールを使用した自動テスト</span><span class="sxs-lookup"><span data-stu-id="4da66-110">Automated testing by using the Issues tool</span></span>

<span data-ttu-id="4da66-111">ブラウザーでデモ ページを開き、DevTools を開いた場合は、問題カウンターで一部の問題が自動的に **検出されます**。</span><span class="sxs-lookup"><span data-stu-id="4da66-111">When you open the demo page in the browser and open DevTools, notice that some issues are automatically detected in the **Issues counter**.</span></span>  <span data-ttu-id="4da66-112">[問題 **] カウンター** \( Issues counter \) を選択して[問題] ツールを開き、問題と ![ ](../media/issues-counter-icon.msft.png) 詳細を表示します。 [][DevToolsIssuesTool]</span><span class="sxs-lookup"><span data-stu-id="4da66-112">Select the **Issues counter** \(![Issues counter](../media/issues-counter-icon.msft.png)\) to open the [Issues tool][DevToolsIssuesTool] to view the issues and more information.</span></span>

:::image type="complex" source="../media/a11y-testing-issues-tracker.msft.png" alt-text="[問題] カウンターは、現在の Web ページに発生している問題の数を示し、[問題] ツールを開きます。" lightbox="../media/a11y-testing-issues-tracker.msft.png":::
    <span data-ttu-id="4da66-114">[問題] カウンターは、現在の Web ページに発生している問題の数を示し、[問題] ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="4da66-114">The Issues counter shows how many problems there are in the current webpage, and opens the Issues tool</span></span>
:::image-end:::

<span data-ttu-id="4da66-115">この記事では、問題ツールの **[アクセシビリティ** ] セクション **に注目** します。</span><span class="sxs-lookup"><span data-stu-id="4da66-115">For this article, we'll focus on the **Accessibility** section of the **Issues** tool.</span></span>

:::image type="complex" source="../media/a11y-testing-accessibility-issues.msft.png" alt-text="[問題] ツールに表示されるアクセシビリティの警告" lightbox="../media/a11y-testing-accessibility-issues.msft.png":::
    <span data-ttu-id="4da66-117">[問題] ツールに表示されるアクセシビリティの警告</span><span class="sxs-lookup"><span data-stu-id="4da66-117">Accessibility warnings displayed in the Issues tool</span></span>
:::image-end:::

<span data-ttu-id="4da66-118">チュートリアルの詳細な手順については、[問題] ツールの [ [アクセシビリティの表示] セクションに移動します][DevToolsAccessibilityTestIssuesToolViewAccSection]。</span><span class="sxs-lookup"><span data-stu-id="4da66-118">For detailed walkthrough steps, navigate to [View the Accessibility section of the Issues tool][DevToolsAccessibilityTestIssuesToolViewAccSection].</span></span>


### <a name="automatically-checking-that-input-fields-have-labels"></a><span data-ttu-id="4da66-119">入力フィールドにラベルが含まれていますを自動的に確認する</span><span class="sxs-lookup"><span data-stu-id="4da66-119">Automatically checking that input fields have labels</span></span>

<span data-ttu-id="4da66-120">最初に表示される警告はです `Form elements must have labels: Element has no title attribute. Element has no placeholder attribute` 。</span><span class="sxs-lookup"><span data-stu-id="4da66-120">The first warning displayed is `Form elements must have labels: Element has no title attribute. Element has no placeholder attribute`.</span></span>  <span data-ttu-id="4da66-121">このセクションを展開し、[要素で開\*\*\*\* く] リンクを選択\*\*\*\* すると、[要素] ツールが開き、DOM ツリーで要素が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-121">When you expand this section and then select the **Open in Elements** link, the **Elements** tool opens, with the element highlighted in the DOM tree.</span></span>  <span data-ttu-id="4da66-122">[ **スタイル]** タブには、要素に適用される CSS が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-122">The **Styles** tab shows the CSS that's applied to the element.</span></span>

<span data-ttu-id="4da66-123">チュートリアルの詳細な手順については、「入力フィールドにラベル [が付い確認する」に移動します][DevtoolsAccessibilityTestIssuesToolCheckFieldsLabels]。</span><span class="sxs-lookup"><span data-stu-id="4da66-123">For detailed walkthrough steps, navigate to [Verify that input fields have labels][DevtoolsAccessibilityTestIssuesToolCheckFieldsLabels].</span></span>

:::image type="complex" source="../media/a11y-testing-inspect-problematic-element.msft.png" alt-text="[問題] ツールでリンクを選択した後に問題のある HTML を表示する要素ツール" lightbox="../media/a11y-testing-inspect-problematic-element.msft.png":::
    <span data-ttu-id="4da66-125">[問題] ツールでリンクを選択した後に問題のある HTML を表示する要素ツール</span><span class="sxs-lookup"><span data-stu-id="4da66-125">Elements tool showing the problematic HTML after selecting the link in the Issues tool</span></span>
:::image-end:::

<span data-ttu-id="4da66-126">この場合、HTML には機能 `label` しない要素があります。</span><span class="sxs-lookup"><span data-stu-id="4da66-126">In this case, the HTML has a `label` element that doesn't work.</span></span>

```html
<label>Search</label>
<input type="search">
<input type="submit" value="go">
```

<span data-ttu-id="4da66-127">要素と要素の間に接続しないので、ここでの要素の使用 `label` は間違 `label` `input` っています。</span><span class="sxs-lookup"><span data-stu-id="4da66-127">The use of the `label` element here is wrong, because there's no connection between the `label` element and the `input` element.</span></span>  <span data-ttu-id="4da66-128">検索ラベルを選択すると、有効な HTML ラベルが検索入力テキスト ボックスに **フォーカスを置** く場合があります。</span><span class="sxs-lookup"><span data-stu-id="4da66-128">A valid HTML label would put focus on the search input textbox when you select the **Search** label.</span></span> 

<span data-ttu-id="4da66-129">この問題は、要素に要素をネストするか、要素の属性をポイントする属性を追加 `input` `label` `for` `id` することで解決 `input` できます。</span><span class="sxs-lookup"><span data-stu-id="4da66-129">You can solve this problem by either nesting the `input` element in a `label` element, or adding a `for` attribute that points to an `id` attribute of the `input` element.</span></span>  <span data-ttu-id="4da66-130">正しい接続を表示するには、寄付フォームの **[その** 他] ラベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="4da66-130">To view a correct connection, select the **Other** label on the donation form.</span></span>

<span data-ttu-id="4da66-131">[問題] ツールで説明リンクを選択 **して、この** 情報を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="4da66-131">You can also select the explanatory links in the **Issues** tool to get this information.</span></span>

:::image type="complex" source="../media/a11y-testing-more-information-links.msft.png" alt-text="問題に関する詳細な情報を示す Issues ツール内のリンク" lightbox="../media/a11y-testing-more-information-links.msft.png":::
    <span data-ttu-id="4da66-133">問題に関 **する詳細** な情報を示す Issues ツール内のリンク</span><span class="sxs-lookup"><span data-stu-id="4da66-133">Links in the **Issues** tool pointing to more in-depth information about the issue</span></span>
:::image-end:::


### <a name="automatically-checking-that-images-have-alt-text"></a><span data-ttu-id="4da66-134">画像に代替テキストが含まれていますを自動的に確認する</span><span class="sxs-lookup"><span data-stu-id="4da66-134">Automatically checking that images have alt text</span></span>

<span data-ttu-id="4da66-135">もう 1 つの自動的に検出された問題は、ページ内の画像の多くに代替テキストが含めなかった場合です。</span><span class="sxs-lookup"><span data-stu-id="4da66-135">The other automatically detected problem is that many of the images in the page don't have any alternative text.</span></span>  <span data-ttu-id="4da66-136">警告を展開すると `Images must have alternate text: Element has no title attribute` 、その問題を抱える 4 つのイメージ インスタンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-136">If you expand the `Images must have alternate text: Element has no title attribute` warning, you get four instances of images with that problem.</span></span>

:::image type="complex" source="../media/a11y-testing-images-without-alt.msft.png" alt-text="代替テキストが見つからない画像を報告する問題ツール" lightbox="../media/a11y-testing-images-without-alt.msft.png":::
    <span data-ttu-id="4da66-138">代替 **テキストが見** つからない画像を報告する問題ツール</span><span class="sxs-lookup"><span data-stu-id="4da66-138">The **Issues** tool, reporting images with missing alternative text</span></span>
:::image-end:::

<span data-ttu-id="4da66-139">チュートリアルの詳細な手順については、「イメージに代替テキストが含まれています。」 [に移動します][DevtoolsAccessibilityTestIssuesToolCheckAltText]。</span><span class="sxs-lookup"><span data-stu-id="4da66-139">For detailed walkthrough steps, navigate to [Verify that images have alt text][DevtoolsAccessibilityTestIssuesToolCheckAltText].</span></span>


### <a name="automatically-checking-that-text-colors-have-enough-contrast"></a><span data-ttu-id="4da66-140">テキストの色に十分なコントラストを自動的に確認する</span><span class="sxs-lookup"><span data-stu-id="4da66-140">Automatically checking that text colors have enough contrast</span></span>

<span data-ttu-id="4da66-141">問題 **ツールは** 、ページ上の 2 つの要素のコントラストが十分ではない場合にも報告します。</span><span class="sxs-lookup"><span data-stu-id="4da66-141">The **Issues** tool also reports when two elements on the page don't have enough contrast.</span></span>

:::image type="complex" source="../media/a11y-testing-contrast-issues.msft.png" alt-text="[問題] ツールで報告されたコントラストの問題" lightbox="../media/a11y-testing-contrast-issues.msft.png":::
    <span data-ttu-id="4da66-143">[問題] ツールで報告された **コントラストの** 問題</span><span class="sxs-lookup"><span data-stu-id="4da66-143">Contrast problems reported in the **Issues** tool</span></span>
:::image-end:::

<span data-ttu-id="4da66-144">[ **問題]** ツールは、警告の詳細な説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="4da66-144">The **Issues** tool provides detailed explanations of the warning.</span></span>  <span data-ttu-id="4da66-145">ドリルダウンすると、この問題がある要素の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-145">When you drill down, you get a list of the elements that have this issue.</span></span>  <span data-ttu-id="4da66-146">[問題 **] ツール** で、要素をポイントするリンクを選択すると、レンダリングされたページ上のその要素が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-146">In the **Issues** tool, selecting a link that points to an element will highlight that element on the rendered page.</span></span>

:::image type="complex" source="../media/a11y-testing-element-with-contrast-issues.msft.png" alt-text="ページへのリンクを選択した後に強調表示されたページ内の要素" lightbox="../media/a11y-testing-element-with-contrast-issues.msft.png":::
    <span data-ttu-id="4da66-148">ページへのリンクを選択した後に強調表示されたページ内の要素</span><span class="sxs-lookup"><span data-stu-id="4da66-148">Element in the page highlighted after selecting the link to it</span></span>
:::image-end:::

<span data-ttu-id="4da66-149">チュートリアルの詳細な手順については、「テキストの色に [十分なコントラストが含まれます。」に移動します][DevtoolsAccessibilityTestIssuesToolCheckContrast]。</span><span class="sxs-lookup"><span data-stu-id="4da66-149">For detailed walkthrough steps, navigate to [Verify that text colors have enough contrast][DevtoolsAccessibilityTestIssuesToolCheckContrast].</span></span>


### <a name="verify-that-the-webpage-layout-is-usable-when-narrow"></a><span data-ttu-id="4da66-150">狭い場合に Web ページ レイアウトが使用可能な場合を確認する</span><span class="sxs-lookup"><span data-stu-id="4da66-150">Verify that the webpage layout is usable when narrow</span></span>

<!-- by design, this section doesn't have a corresponding how-to article -->

<span data-ttu-id="4da66-151">アクセシビリティの重要な部分は、狭いビューポートで Web 製品が正しく動作することが重要です。</span><span class="sxs-lookup"><span data-stu-id="4da66-151">An important part of accessibility is to make sure that your web products work well on a narrow viewport.</span></span> <span data-ttu-id="4da66-152">多くのユーザーは、ページを使用するためにページをズームする必要があります。つまり、スペースがあまり残っていないという意味です。</span><span class="sxs-lookup"><span data-stu-id="4da66-152">Many users need to zoom the page to be able to use it, and this means that there is not much space left.</span></span> <span data-ttu-id="4da66-153">スペースが足りない場合は、複数列のレイアウトを 1 列のレイアウトに変換し、コンテンツを理解できる順序で配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4da66-153">When there is not enough space, your multi-column layout should turn into a single-column layout, with content placed in an understandable order.</span></span> <span data-ttu-id="4da66-154">つまり、最も重要なコンテンツをページの上部に配置し、追加のコンテンツをページの下に配置します。</span><span class="sxs-lookup"><span data-stu-id="4da66-154">This means placing the most important content at the top of the page, and placing additional content further down the page.</span></span>

<span data-ttu-id="4da66-155">ブラウザー ウィンドウを狭くし、矢印キーを使用してページをスクロールすると、デモ ページの上部のナビゲーション バーにアクセシビリティの問題があるのが分かっています。</span><span class="sxs-lookup"><span data-stu-id="4da66-155">By making the browser window narrow and using the arrow keys to scroll the page, you can see that the top navigation bar of the demo page has some accessibility issues.</span></span>  <span data-ttu-id="4da66-156">上のナビゲーション バーは、 **前の画像** に示すように[検索] フォームと重なり、その問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4da66-156">The top navigation bar overlaps the **Search** form, as shown in the previous image, and that issue needs to be fixed.</span></span>

<span data-ttu-id="4da66-157">狭いビューポートをシミュレートするには、ブラウザー ウィンドウのサイズを変更しますが、デザインの応答性をテストするには **、Device エミュレーション ツールを使用する方が良い方法** です。</span><span class="sxs-lookup"><span data-stu-id="4da66-157">You can simulate a narrow viewport by resizing the browser window, but a better way to test the responsiveness of your design is to use the **Device Emulation** tool.</span></span>  <span data-ttu-id="4da66-158">任意の Web サイトのアクセシビリティの問題 **を** 見つけるのに役立つデバイス エミュレーション ツールの機能を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4da66-158">Here are some features of the **Device Emulation** tool that help you find accessibility issues of any website:</span></span>

*  <span data-ttu-id="4da66-159">ブラウザー ウィンドウのサイズを変更せずに、ページのサイズを変更し [、CSS][DevToolsMediaQueries] メディア クエリがレイアウトの変更をトリガーするかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="4da66-159">Without resizing the browser window, resize the page and test whether your [CSS media queries][DevToolsMediaQueries] trigger a change in layout.</span></span>
*  <span data-ttu-id="4da66-160">マウスを使用する依存関係を確認します。</span><span class="sxs-lookup"><span data-stu-id="4da66-160">Check for dependencies that use a mouse.</span></span> <span data-ttu-id="4da66-161">既定では、デバイス エミュレーションはタッチ デバイスを前提とします。</span><span class="sxs-lookup"><span data-stu-id="4da66-161">By default, device emulation assumes a touch device.</span></span> <span data-ttu-id="4da66-162">つまり、ホバー操作に依存する製品の機能は機能しません。</span><span class="sxs-lookup"><span data-stu-id="4da66-162">This means that any functionality of your product that relies on hover interaction will not work.</span></span> 
*  <span data-ttu-id="4da66-163">さまざまなデバイス、ズーム レベル、ピクセル比をシミュレートして視覚的なテストを行います。</span><span class="sxs-lookup"><span data-stu-id="4da66-163">Do visual testing by simulating different devices, zoom levels, and pixel ratios.</span></span>
*  <span data-ttu-id="4da66-164">製品が不当な接続でどのように動作するか、またはユーザーがオフラインである場合にテストします。</span><span class="sxs-lookup"><span data-stu-id="4da66-164">Test how your product behaves on unreliable connections or when the user is offline.</span></span>  <span data-ttu-id="4da66-165">低速の接続でユーザーに最も重要な操作を表示する方法も、アクセシビリティに関する考慮事項です。</span><span class="sxs-lookup"><span data-stu-id="4da66-165">Showing the most important interactions to a user on a slow connection is also an accessibility consideration.</span></span>

<span data-ttu-id="4da66-166">デバイス エミュレーション ツールの詳細**については、「デバイス**の DevTools でモバイル デバイスをエミュレート[するMicrosoft Edge移動します][DevToolsDeviceModeIndex]。</span><span class="sxs-lookup"><span data-stu-id="4da66-166">To learn more about the **Device Emulation** tool, navigate to [Emulate mobile devices in Microsoft Edge DevTools][DevToolsDeviceModeIndex].</span></span>


### <a name="wavy-underlines-in-the-dom-tree-indicate-automatically-detected-issues"></a><span data-ttu-id="4da66-167">DOM ツリーの波の下線は、自動的に検出された問題を示します</span><span class="sxs-lookup"><span data-stu-id="4da66-167">Wavy underlines in the DOM tree indicate automatically detected issues</span></span>

<span data-ttu-id="4da66-168">要素ツールの DOM ツリー **は** 、波状の下線を追加することで、HTML 内の問題に直接フラグを自動的に設定します。</span><span class="sxs-lookup"><span data-stu-id="4da66-168">The DOM tree in the **Elements** tool automatically flags issues directly in the HTML by adding a wavy underline.</span></span>  <span data-ttu-id="4da66-169">波線 `Shift` + `click` が付く要素がある場合は、[問題] ツール**が**開きます。</span><span class="sxs-lookup"><span data-stu-id="4da66-169">If you `Shift`+`click` any element that has a wavy underline, the **Issues** tool opens.</span></span>

:::image type="complex" source="../media/a11y-testing-wavy-underlines.msft.png" alt-text="DOM ツリーに波線付き下線が表示されている要素には問題があります。  Shift キーを押しながら要素をクリックすると、問題に直接アクセスできます。" lightbox="../media/a11y-testing-wavy-underlines.msft.png":::
    <span data-ttu-id="4da66-172">DOM ツリーに波線付き下線が表示されている要素には問題があります。</span><span class="sxs-lookup"><span data-stu-id="4da66-172">An element that is shown with wavy underlining in the DOM tree has issues.</span></span>  `Shift`<span data-ttu-id="4da66-173">+`click` 問題に直接アクセスする要素。</span><span class="sxs-lookup"><span data-stu-id="4da66-173">+`click` the element to get directly to the issue.</span></span>
:::image-end:::

<span data-ttu-id="4da66-174">Issues ツールで見つかったこれらの\*\*\*\* 問題は、回避できる比較的明白なアクセシビリティの問題です。</span><span class="sxs-lookup"><span data-stu-id="4da66-174">These issues that were found by the **Issues** tool are some relatively obvious accessibility problems that can be avoided.</span></span>  <span data-ttu-id="4da66-175">Issues **ツールとその** ガイド付き説明を使用して修正すると、アクセス可能な製品に向かう途中で設定されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-175">Using the **Issues** tool and its guided explanations to fix them sets you on the way towards an accessible product.</span></span>


## <a name="limits-of-automated-testing"></a><span data-ttu-id="4da66-176">自動テストの制限</span><span class="sxs-lookup"><span data-stu-id="4da66-176">Limits of automated testing</span></span>

<span data-ttu-id="4da66-177">Issues[ツール、][DevToolsIssuesTool][アクセシビリティ インサイト][AccessibilityInsights]、[およびライト][Lighthouse]ハウスは、Web ページのアクセシビリティ レポートを自動的に生成するツールです。</span><span class="sxs-lookup"><span data-stu-id="4da66-177">The [Issues tool][DevToolsIssuesTool], [Accessibility Insights][AccessibilityInsights], and [Lighthouse][Lighthouse] are tools that automatically generate an accessibility report for a webpage.</span></span>  <span data-ttu-id="4da66-178">このようなツールから自動レポートを取得できるのは、アクセシビリティ テストの開始にすぎない。</span><span class="sxs-lookup"><span data-stu-id="4da66-178">Getting an automated report from such tools is only the beginning of your accessibility-testing journey.</span></span>

<span data-ttu-id="4da66-179">アクセシビリティとは、さまざまな技術的な環境で製品を使用するさまざまなニーズを持つユーザーとの対話に関する情報です。</span><span class="sxs-lookup"><span data-stu-id="4da66-179">Accessibility is about human interaction—people with different needs using your products within various technical environments.</span></span>  <span data-ttu-id="4da66-180">このテストは完全に自動化できないが、製品をナビゲートする人間による検証が必要です。</span><span class="sxs-lookup"><span data-stu-id="4da66-180">This testing can't be fully automated, but needs verification by a human navigating the product.</span></span>  <span data-ttu-id="4da66-181">最適なシナリオでは、アクセシビリティのニーズが異なるテスターや、さまざまな環境を使用するテスターにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4da66-181">In the best scenario, you'd have access to testers with different accessibility needs, and testers using various environments.</span></span>  <span data-ttu-id="4da66-182">しかし、キーボードを使用してナビゲーションを行い、ページの異なる部分を検査することで、自分で多くのことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4da66-182">But you can already do a lot yourself by using the keyboard to navigate and by inspecting different parts of the page.</span></span>

<span data-ttu-id="4da66-183">デモ ページには、自動テストで検出できない追加の問題があります。</span><span class="sxs-lookup"><span data-stu-id="4da66-183">On the demo page, there are additional issues that automated testing can't detect including:</span></span> 

*  <span data-ttu-id="4da66-184">ページを操作した後に発生する問題。</span><span class="sxs-lookup"><span data-stu-id="4da66-184">Issues that arise after you interact with the page.</span></span> 
*  <span data-ttu-id="4da66-185">ウィンドウを狭くするなどの表示の変更に関連する問題。</span><span class="sxs-lookup"><span data-stu-id="4da66-185">Issues related to changes in display, such as making the window narrow.</span></span>

<span data-ttu-id="4da66-186">これらの問題の 1 つは、寄付フォームです。</span><span class="sxs-lookup"><span data-stu-id="4da66-186">One of those issues is the donation form.</span></span>  <span data-ttu-id="4da66-187">マウスを使用する場合は、さまざまなオプションをクリックして寄付することができます。</span><span class="sxs-lookup"><span data-stu-id="4da66-187">When you use a mouse, you can click the different options to donate money.</span></span>  <span data-ttu-id="4da66-188">しかし、キーボードを使用して寄付フォームにアクセスしようとすると、何も起こりません。</span><span class="sxs-lookup"><span data-stu-id="4da66-188">But when you try to use the keyboard to access the donation form, nothing happens.</span></span> <span data-ttu-id="4da66-189">この問題を解決するには、検査ツールを使用する **必要** があります。</span><span class="sxs-lookup"><span data-stu-id="4da66-189">To solve this issue, you need to use the **Inspect** tool.</span></span>

:::image type="complex" source="../media/a11y-testing-basics-donation-form-issue.msft.png" alt-text="デモ ページの寄附フォームが強調表示されます" lightbox="../media/a11y-testing-basics-donation-form-issue.msft.png":::
    <span data-ttu-id="4da66-191">デモ ページの寄附フォームが強調表示されます</span><span class="sxs-lookup"><span data-stu-id="4da66-191">Donation form on the demo page is highlighted</span></span>
:::image-end:::


## <a name="using-the-inspect-tool-to-detect-accessibility-issues"></a><span data-ttu-id="4da66-192">[検査] ツールを使用してアクセシビリティの問題を検出する</span><span class="sxs-lookup"><span data-stu-id="4da66-192">Using the Inspect tool to detect accessibility issues</span></span>

<span data-ttu-id="4da66-193">[検査 **] ツール** を使用して、Web ページの一部にカーソルを合わせると、アクセシビリティの問題を検出できます。</span><span class="sxs-lookup"><span data-stu-id="4da66-193">Use the **Inspect** tool to detect accessibility issues by hovering over parts of the webpage.</span></span>  <span data-ttu-id="4da66-194">Inspect \*\*\*\* \( ![ Inspect ](../media/inspect-icon.msft.png) \) ツールは、DevTools の左上隅にあります。</span><span class="sxs-lookup"><span data-stu-id="4da66-194">The **Inspect** \(![Inspect](../media/inspect-icon.msft.png)\) tool is in the top-left corner of DevTools.</span></span>  <span data-ttu-id="4da66-195">[検査] ツール ボタンを選択して、[検査] **ツールを** オンにします。</span><span class="sxs-lookup"><span data-stu-id="4da66-195">Turn on the Inspect tool by selecting the **Inspect** tool button.</span></span>

:::image type="complex" source="../media/a11y-testing-basics-inspector.msft.png" alt-text="[検査] ツール ボタンを選択して[検査] ツールをオンにする" lightbox="../media/a11y-testing-basics-inspector.msft.png":::
    <span data-ttu-id="4da66-197">[ **検査]** ツール ボタンを選択して[検査] **ツールを** オンにする</span><span class="sxs-lookup"><span data-stu-id="4da66-197">Turn on the **Inspect** tool by selecting the **Inspect** tool button</span></span>
:::image-end:::

<span data-ttu-id="4da66-198">[ツールの検査] **ボタンを** 選択した後、レンダリングされたページの任意の要素の上にポインターを移動できます。</span><span class="sxs-lookup"><span data-stu-id="4da66-198">After you select the **Inspect** tool button, you can move your pointer over any element on the rendered page.</span></span>  <span data-ttu-id="4da66-199">[検査] ツールは、要素のレイアウトを多色のフレックスボックス オーバーレイとして表示し、要素の詳細をヒントに似た情報オーバーレイとして表示します。</span><span class="sxs-lookup"><span data-stu-id="4da66-199">The Inspect tool shows the element's layout as a multicolored flexbox overlay, and shows element details as an information overlay similar to a tooltip.</span></span>

:::image type="complex" source="../media/inspect-tool-flexbox-overlay.msft.png" alt-text="検査ツールを使用する場合のマルチカラー フレックスボックス オーバーレイと情報オーバーレイ" lightbox="../media/inspect-tool-flexbox-overlay.msft.png":::
    <span data-ttu-id="4da66-201">検査ツールを使用する場合のマルチカラー フレックスボックス オーバーレイと情報**オーバーレイ**</span><span class="sxs-lookup"><span data-stu-id="4da66-201">Multicolor flexbox overlay and information overlay when using the **Inspect** tool</span></span>
:::image-end:::

<span data-ttu-id="4da66-202">[検査] ツールの [ **アクセシビリティ] セクション** には、該当する **場合はコントラスト** 線が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4da66-202">The Inspect tool's **Accessibility** section includes a **Contrast** line, when applicable.</span></span>

:::image type="complex" source="../media/a11y-testing-basics-inspector-overlay.msft.png" alt-text="[検査] ツールの [アクセシビリティ] セクションには、該当する場合はコントラスト線が含まれます。" lightbox="../media/a11y-testing-basics-inspector-overlay.msft.png":::
    <span data-ttu-id="4da66-204">[検査] ツールの **[アクセシビリティ] セクション** には、 **該当する場合はコントラスト** 線が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4da66-204">The Inspect tool's **Accessibility** section includes a **Contrast** line, when applicable</span></span>
:::image-end:::

<span data-ttu-id="4da66-205">詳細なチュートリアル手順については、「色の強調表示を [使用して入れ子になった領域を識別する」に移動します][DevtoolsAccessibilityTestInspectToolColorHighlighting]。</span><span class="sxs-lookup"><span data-stu-id="4da66-205">For detailed walkthrough steps, navigate to [Identify nested regions using color highlighting][DevtoolsAccessibilityTestInspectToolColorHighlighting].</span></span>
<!-- = test-inspect-tool.md##identify-nested-regions-using-color-highlighting -->

<span data-ttu-id="4da66-206">検査ツールの **情報オーバーレイの** 上部には、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-206">The upper section of the **Inspect** tool's information overlay displays the following information:</span></span>

* <span data-ttu-id="4da66-207">レイアウトの種類。要素がフレックスボックスまたはグリッドを使用して配置されている場合は、適切なアイコン \(</span><span class="sxs-lookup"><span data-stu-id="4da66-207">Layout type; if the element is positioned using a flexbox or grid, you see an appropriate icon \(</span></span>![グリッド レイアウト アイコン](../media/grid-icon.msft.png)<span data-ttu-id="4da66-209">\).</span><span class="sxs-lookup"><span data-stu-id="4da66-209">\).</span></span>
* <span data-ttu-id="4da66-210">要素の名前 **(a、h1、div\*\*\*\*など)。** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4da66-210">The name of the element, such as **a**, **h1**, or **div**.</span></span>
* <span data-ttu-id="4da66-211">要素のサイズ (ピクセル単位)。</span><span class="sxs-lookup"><span data-stu-id="4da66-211">The dimensions of the element, in pixels.</span></span>
* <span data-ttu-id="4da66-212">色は、色見本 (小さい色付き四角形) として、書式設定された値 (など) として表示されます `#336699` 。</span><span class="sxs-lookup"><span data-stu-id="4da66-212">The color, as a color swatch (a small, colored square) and as a formatted value (such as `#336699`).</span></span>
* <span data-ttu-id="4da66-213">フォント情報 (サイズとフォント ファミリ)。</span><span class="sxs-lookup"><span data-stu-id="4da66-213">Font information (size and font families).</span></span>
* <span data-ttu-id="4da66-214">余白とパディング (ピクセル単位)。</span><span class="sxs-lookup"><span data-stu-id="4da66-214">Margin and padding, in pixels.</span></span>

<span data-ttu-id="4da66-215">Inspect **オーバーレイの** アクセシビリティ **部分** については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="4da66-215">The **Accessibility** part of the **Inspect** overlay is described in the following section.</span></span>


### <a name="checking-individual-elements-for-text-contrast-screen-reader-text-and-keyboard-support"></a><span data-ttu-id="4da66-216">個々の要素でテキストのコントラスト、スクリーン リーダー テキスト、キーボードのサポートを確認する</span><span class="sxs-lookup"><span data-stu-id="4da66-216">Checking individual elements for text contrast, screen reader text, and keyboard support</span></span>

<span data-ttu-id="4da66-217">[ **検査] オーバーレイの** [アクセシビリティ] **セクション** には、次の行が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4da66-217">The **Accessibility** section of the **Inspect** overlay contains the following rows:</span></span>

*   <span data-ttu-id="4da66-218">**コントラスト** は、視覚障害を持つユーザーが要素を理解できるかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="4da66-218">**Contrast** defines whether an element can be understood by people with impaired vision.</span></span>
    *   <span data-ttu-id="4da66-219">[WCAG][WCAG] [ガイドラインで定義][W3CContrastRatio]されているコントラスト比は、テキストと背景色の間に十分なコントラストが含されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4da66-219">The [contrast ratio][W3CContrastRatio] as defined by the [WCAG Guidelines][WCAG] indicates whether there is enough contrast between text and background colors.</span></span>  <span data-ttu-id="4da66-220">緑色のチェック マーク アイコンは十分なコントラストを示し、オレンジ色の感嘆符アイコンは十分なコントラストが見えない状態を示します。</span><span class="sxs-lookup"><span data-stu-id="4da66-220">A green check mark icon indicates there's enough contrast, and an orange exclamation-point icon indicates there's not enough contrast.</span></span>

*   <span data-ttu-id="4da66-221">**名前** と **役割は** 、スクリーン リーダーなどの情報支援テクノロジが要素について報告する情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4da66-221">**Name** and **Role** indicate what information assistive technology, such as screen readers, will report about the element.</span></span>
    *   <span data-ttu-id="4da66-222">Name **は** 、要素のテキスト コンテンツ `a` です。</span><span class="sxs-lookup"><span data-stu-id="4da66-222">The **Name** is the text content of an `a` element.</span></span>  <span data-ttu-id="4da66-223">要素の場合 `<a href="/">About Us</a>` 、 **検査ツールに** 表示される名前は "About Us" です。</span><span class="sxs-lookup"><span data-stu-id="4da66-223">For the element `<a href="/">About Us</a>`, the **Name** shown in the Inspect tool is "About Us".</span></span>
    *   <span data-ttu-id="4da66-224">要素**の Role。**</span><span class="sxs-lookup"><span data-stu-id="4da66-224">The **Role** of the element.</span></span>  <span data-ttu-id="4da66-225">Role **は** 、通常、要素名 `article` (、 `img` `link` `heading` など) です。</span><span class="sxs-lookup"><span data-stu-id="4da66-225">The **Role** is usually the element name, such as `article`, `img` , `link`, or `heading`.</span></span>  <span data-ttu-id="4da66-226">と `div` 要素 `span` はとして表されます `generic` 。</span><span class="sxs-lookup"><span data-stu-id="4da66-226">The `div` and `span` elements are represented as `generic`.</span></span>

*   <span data-ttu-id="4da66-227">**キーボードフォーカス可能は** 、ユーザーがマウス以外の入力デバイスを使用して要素に到達できるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4da66-227">**Keyboard-focusable** indicates whether users can reach the element using input devices other than a mouse.</span></span>
    *   <span data-ttu-id="4da66-228">緑色のチェック マーク アイコンは、要素がキーボードフォーカス可能な状態を示します。</span><span class="sxs-lookup"><span data-stu-id="4da66-228">A green check mark icon indicates that the element is keyboard-focusable.</span></span>
    *   <span data-ttu-id="4da66-229">斜めの線が付く灰色の円は、要素がキーボードフォーカス可能でなかったかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4da66-229">A gray circle with diagonal line indicates that the element isn't keyboard-focusable.</span></span>

<span data-ttu-id="4da66-230">チュートリアルの詳細な手順については、「テキストのコントラスト、スクリーン リーダー テキスト、キーボードのサポートについて個々の要素を確認する」 [に移動します][DevtoolsAccessibilityTestInspectToolIndivElems]。</span><span class="sxs-lookup"><span data-stu-id="4da66-230">For detailed walkthrough steps, navigate to [Check individual elements for text contrast, screen reader text, and keyboard support][DevtoolsAccessibilityTestInspectToolIndivElems].</span></span>
<!-- = test-inspect-tool.md#check-individual-elements-for-text-contrast-screen-reader-text-and-keyboard-support -->


### <a name="using-the-inspect-tool-to-hover-over-the-webpage-to-highlight-the-dom-and-css"></a><span data-ttu-id="4da66-231">[検査] ツールを使用して Web ページにカーソルを合わせると、DOM と CSS が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-231">Using the Inspect tool to hover over the webpage to highlight the DOM and CSS</span></span>

<span data-ttu-id="4da66-232">[検査] **ツールを使用** する場合、レンダリングされたページで要素を選択すると、[要素] ツール **が開** きます。</span><span class="sxs-lookup"><span data-stu-id="4da66-232">When using the **Inspect** tool, selecting an element on the rendered page opens the **Elements** tool.</span></span>  <span data-ttu-id="4da66-233">DOM ツリーには要素の HTML が表示され **、Styles** には要素に適用される CSS プロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-233">The DOM tree shows the HTML of the element, and **Styles** shows the CSS properties that are applied to the element.</span></span>

:::image type="complex" source="../media/a11y-testing-basics-inspector-selected-element.msft.png" alt-text="要素ツールに表示される選択した要素の詳細" lightbox="../media/a11y-testing-basics-inspector-selected-element.msft.png":::
    <span data-ttu-id="4da66-235">要素ツールに表示される選択した要素の詳細</span><span class="sxs-lookup"><span data-stu-id="4da66-235">Details about the selected element displayed in the Elements tool</span></span>
:::image-end:::

<span data-ttu-id="4da66-236">[検査] **ツールを** 使用する場合、レンダリングされたページの異なる部分にカーソルを合わせると、 **要素** が開いていると、DOM ツリーが自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-236">When using the **Inspect** tool, as you hover over different parts of the rendered page with **Elements** open, you'll notice that the DOM tree automatically refreshes.</span></span>

<span data-ttu-id="4da66-237">チュートリアルの詳細な手順については、「検査ツールを使用して Web ページにカーソルを合わせる」に移動して、DOM と [CSS を強調表示します][DevtoolsAccessibilityTestInspectToolDomCss]。</span><span class="sxs-lookup"><span data-stu-id="4da66-237">For detailed walkthrough steps, navigate to [Use the Inspect tool to hover over the webpage to highlight the DOM and CSS][DevtoolsAccessibilityTestInspectToolDomCss].</span></span>
<!-- = test-inspect-tool.md#use-the-inspect-tool-to-hover-over-the-webpage-to-highlight-the-dom-and-css -->


## <a name="verify-keyboard-support-by-using-the-tab-and-enter-keys"></a><span data-ttu-id="4da66-238">Tab キーと Enter キーを使用してキーボードのサポートを確認する</span><span class="sxs-lookup"><span data-stu-id="4da66-238">Verify keyboard support by using the Tab and Enter keys</span></span>

<span data-ttu-id="4da66-239">すべてのユーザーがポインターデバイスやタッチ デバイスを使用する場合や、低視力の人もいます。</span><span class="sxs-lookup"><span data-stu-id="4da66-239">Not all people use pointer or touch devices, and some people may have low vision.</span></span> <span data-ttu-id="4da66-240">これらのシナリオに対応するには、UIs がキーボードで動作します。</span><span class="sxs-lookup"><span data-stu-id="4da66-240">To cater for these scenarios, ensure that UIs work with keyboards.</span></span>

<span data-ttu-id="4da66-241">キーボードを使用して、要素から要素へのジャンプを使用して、ページを `Tab` `Shift+Tab` 移動するテストを行います。</span><span class="sxs-lookup"><span data-stu-id="4da66-241">You can test using a keyboard to navigate the page, by using `Tab` or `Shift+Tab` to jump from element to element.</span></span>  <span data-ttu-id="4da66-242">デモ ページを押すと、最初にフォーカスを受け取ったのは、ページ ヘッダーの `Tab` **[検索** ] フォームです。</span><span class="sxs-lookup"><span data-stu-id="4da66-242">If you press `Tab` on the demo page, the first thing that receives focus is the **Search** form in the page header.</span></span>  <span data-ttu-id="4da66-243">[ `Enter` 問題] ツールを使用するときに以前に発見したラベルの問題にもかかわらず、フォームを送信することもできます。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4da66-243">Pressing `Enter` even allows you to submit the form, so that works, despite the label issue we discovered earlier when using the **Issues** tool.</span></span>

<span data-ttu-id="4da66-244">詳細なチュートリアル手順については、「Tab キーと Enter キーを使用してキーボードサポートを確認 [する」に移動します](test-tab-enter-keys.md)。</span><span class="sxs-lookup"><span data-stu-id="4da66-244">For detailed walkthrough steps, navigate to [Check for keyboard support by using the Tab and Enter keys](test-tab-enter-keys.md).</span></span>

<span data-ttu-id="4da66-245">代わりに押すと、フォーカスを取得する次の要素は、アウトラインで示されているページのコンテンツ セクションの最初の [その他] `Tab` `Enter` リンクです。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4da66-245">When you press `Tab` instead of `Enter`, the next element that gets focus is the first **More** link in the content section of the page, as indicated by an outline.</span></span>

:::image type="complex" source="../media/a11y-testing-keyboard-focus-on-element.msft.png" alt-text="Tab キーを使用してページを移動します。  ページの [その他] リンクにフォーカスが表示されます。" lightbox="../media/a11y-testing-keyboard-focus-on-element.msft.png":::
    <span data-ttu-id="4da66-248">キーを使用してページを移動 `Tab` します。</span><span class="sxs-lookup"><span data-stu-id="4da66-248">Navigating the page by using the `Tab` key.</span></span>  <span data-ttu-id="4da66-249">ページの [その他] **リンクに** フォーカスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-249">Focus is shown on a **More** link in the page.</span></span>
:::image-end:::

<span data-ttu-id="4da66-250">最後の [その他] **リンクを** 過ぎた後、ページが上にスクロールし、フォーカスがある要素が不明です。</span><span class="sxs-lookup"><span data-stu-id="4da66-250">After you go past the last **More** link, the page scrolls up, and it's unclear which element has focus.</span></span>

<span data-ttu-id="4da66-251">画面の左下を見た場合、またはスクリーン リーダーを使用する場合は、ブラウザーに URL が表示されるので、サイドバー ナビゲーション メニューの青い**Cats**リンクにフォーカスが設定されている場合があります。 `#cats`</span><span class="sxs-lookup"><span data-stu-id="4da66-251">If you look to the bottom left of the screen or if you use a screen reader, you can tell that the blue **Cats** link in the sidebar navigation menu has focus, because the browser shows the URL `#cats`.</span></span>

:::image type="complex" source="../media/a11y-testing-lack-of-focus-style.msft.png" alt-text="フォーカスのスタイルが不足すると、ページの現在の場所を知ることは不可能です。  唯一のヒントは、ウィンドウの左下にリンク ターゲットが表示されます。" lightbox="../media/a11y-testing-lack-of-focus-style.msft.png":::
    <span data-ttu-id="4da66-254">フォーカスのスタイルが不足すると、ページの現在の場所を知ることは不可能です。</span><span class="sxs-lookup"><span data-stu-id="4da66-254">A lack of focus styling makes it impossible to know where you currently are in the page.</span></span>  <span data-ttu-id="4da66-255">唯一のヒントは、ウィンドウの左下にリンク ターゲットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-255">The only hint is the display of the link target in the bottom left of the window.</span></span>
:::image-end:::

<span data-ttu-id="4da66-256">もう一 `Tab` 度選択すると、寄付フォームの入力テキスト ボックスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4da66-256">Selecting `Tab` again takes you to the input textbox of the donation form.</span></span>  <span data-ttu-id="4da66-257">ただし、入力テキスト ボックスの **上にある 50**ボタン **、100** ボタン、 **または 200** ボタンには到達できない。</span><span class="sxs-lookup"><span data-stu-id="4da66-257">However, you can't reach the **50**, **100** or **200** buttons above the input textbox.</span></span>  <span data-ttu-id="4da66-258">また、その入力テキスト ボックスにフォーカスがある場合、選択 `Enter` してもフォームは送信されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-258">Also, when focus is on that input textbox, selecting `Enter` doesn't submit the form.</span></span>

:::image type="complex" source="../media/a11y-testing-form-field-with-outline.msft.png" alt-text="寄附フォームのキーボードアクセス可能な要素は、入力テキスト フィールドのみです。" lightbox="../media/a11y-testing-form-field-with-outline.msft.png":::
    <span data-ttu-id="4da66-260">寄附フォームのキーボードアクセス可能な要素は、テキスト フィールドのみです。</span><span class="sxs-lookup"><span data-stu-id="4da66-260">The only keyboard-accessible element in the donation form is the text field</span></span>
:::image-end:::

<span data-ttu-id="4da66-261">もう一度選択すると、トップ ナビゲーション バーにフォーカスが置き、ページの別のセクションまたはサイトの別のページに `Tab` `Enter` 移動できます。</span><span class="sxs-lookup"><span data-stu-id="4da66-261">Selecting `Tab` again puts focus on the top navigation bar, where you can select `Enter` to go to a different section of the page or a different page of the site.</span></span>  <span data-ttu-id="4da66-262">フォーカスアウトラインがあるから、どの要素をオンにしているのか分かっている。</span><span class="sxs-lookup"><span data-stu-id="4da66-262">You know which element you are on, because there's a focus outline.</span></span>  <span data-ttu-id="4da66-263">トップ ナビゲーション バーでリンクを選択するには、リンクにフォーカスを設定するか、を選択 `Tab` `Shift+Tab` します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="4da66-263">To select a link in the top navigation bar, use `Tab` or `Shift+Tab` to put focus on a link, and then select `Enter`.</span></span>

:::image type="complex" source="../media/a11y-testing-menu-with-outline.msft.png" alt-text="上部のナビゲーション バーには強調表示とフォーカスのアウトラインが表示され、キーボードにアクセスできます。" lightbox="../media/a11y-testing-menu-with-outline.msft.png":::
    <span data-ttu-id="4da66-265">上部のナビゲーション バーには強調表示とフォーカスのアウトラインが表示され、キーボードにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4da66-265">The top navigation bar has a highlight and a focus outline, and thus is keyboard-accessible</span></span>
:::image-end:::

<span data-ttu-id="4da66-266">ここで修正する問題がいくつか見つかりました。</span><span class="sxs-lookup"><span data-stu-id="4da66-266">We found some issues here to fix:</span></span>

* <span data-ttu-id="4da66-267">キーボードを使用してページ上を移動する場合、サイドバーのナビゲーション メニューにフォーカスがあるユーザー `Tab` は表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-267">The sidebar navigation menu doesn't show users where the `Tab` focus is, when using keyboards to move around on the page.</span></span>
* <span data-ttu-id="4da66-268">寄附フォームでは、キーボードを使用する場合、**50、100、**、 **および 200** のボタンとフォーム送信機能は機能しません。</span><span class="sxs-lookup"><span data-stu-id="4da66-268">On the donation form, the \*\*50, 100, \*\* and **200** buttons and form submit functionality doesn't work when using the keyboard.</span></span>
* <span data-ttu-id="4da66-269">キーボードのタブの順序が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="4da66-269">The keyboard tab order is incorrect.</span></span> <span data-ttu-id="4da66-270">キー `Tab` は、サイドバー ナビゲーション\*\*\*\* メニューの前のページ上のすべての [その他] リンクを移動します。</span><span class="sxs-lookup"><span data-stu-id="4da66-270">The `Tab` key navigates through all the **More** links on the page before the sidebar navigation menu.</span></span>  <span data-ttu-id="4da66-271">この順序は、そのページの別のセクションに移動することを目的としたサイドバー ナビゲーションなので `Tab` 役に立つとは限らない。</span><span class="sxs-lookup"><span data-stu-id="4da66-271">This `Tab` order isn't helpful because the sidebar navigation is intended to take you to the different sections of that page.</span></span> 

<span data-ttu-id="4da66-272">DevTools を使用してこれらの問題を分析しましょう。</span><span class="sxs-lookup"><span data-stu-id="4da66-272">Let's analyze these problems using DevTools.</span></span>


## <a name="analyze-keyboard-accessibility-issues-using-devtools"></a><span data-ttu-id="4da66-273">DevTools を使用してキーボードアクセシビリティの問題を分析する</span><span class="sxs-lookup"><span data-stu-id="4da66-273">Analyze keyboard accessibility issues using DevTools</span></span>


### <a name="analyzing-the-lack-of-indication-of-keyboard-focus-in-the-sidebar-menu"></a><span data-ttu-id="4da66-274">サイドバー メニューでのキーボード フォーカスの表示の不足を分析する</span><span class="sxs-lookup"><span data-stu-id="4da66-274">Analyzing the lack of indication of keyboard focus in the sidebar menu</span></span>

<span data-ttu-id="4da66-275">キーボードで使用するためにサイドバー ナビゲーションが期待通り最適化されていない理由を確認するには、まず[検査] ツール\*\*\*\* を使用してサイドバー ナビゲーション メニューのリンクを強調表示してから、DOM ツリーで要素にドリルダウンします。 `a`</span><span class="sxs-lookup"><span data-stu-id="4da66-275">To find out why the sidebar navigation isn't optimized as expected for use with keyboards, start by using the **Inspect** tool to highlight a link in the sidebar navigation menu, and then drill down in the DOM tree to the `a` element.</span></span> 

:::image type="complex" source="../media/a11y-testing-menu-link.msft.png" alt-text="サイドバーのナビゲーション メニューでリンクのソース コードと適用されたスタイルを確認する" lightbox="../media/a11y-testing-menu-link.msft.png":::
    <span data-ttu-id="4da66-277">サイドバーのナビゲーション メニューでリンクのソース コードと適用されたスタイルを確認する</span><span class="sxs-lookup"><span data-stu-id="4da66-277">Inspecting the source code and the applied styles of a link in the sidebar navigation menu</span></span>
:::image-end:::

<span data-ttu-id="4da66-278">[スタイル **] タブ** で、リンクに適用される CSS を確認できます。リンク先を選択すると、[ソース] ツールでファイル `styles.css` **が開** きます。</span><span class="sxs-lookup"><span data-stu-id="4da66-278">In the **Styles** tab, you can see the CSS that's applied to the link, and if you select the link to `styles.css`, the file opens in the **Sources** tool.</span></span>

:::image type="complex" source="../media/a11y-testing-menu-link-styles.msft.png" alt-text="リンクに適用されるスタイル (ソース ツールに表示)" lightbox="../media/a11y-testing-menu-link-styles.msft.png":::
    <span data-ttu-id="4da66-280">リンクに適用されるスタイル (ソース ツールに表示)</span><span class="sxs-lookup"><span data-stu-id="4da66-280">The styles that are applied to the link, shown in the Sources tool</span></span>
:::image-end:::

<span data-ttu-id="4da66-281">上記の例では、マウスを使用する場合、ページのスタイルにはメニュー項目の状態が含まれますが、キーボード ユーザーの CSS には `hover` `focus` 状態はありません。</span><span class="sxs-lookup"><span data-stu-id="4da66-281">In the above example, the styles of the page include a `hover` state on the menu item when you use a mouse, but there's no `focus` state in the CSS for keyboard users.</span></span>  

<span data-ttu-id="4da66-282">また、この例では、リンクはを使用します `outline: none` 。</span><span class="sxs-lookup"><span data-stu-id="4da66-282">Also, in this example, the links use `outline: none`.</span></span> <span data-ttu-id="4da66-283">このスタイルは、フォーカスとキーボードが使用されている場合に、ブラウザーによって要素に自動的に追加されるアウトラインを削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-283">This style is used to remove the outline that's automatically added by browsers to elements when they have focus and keyboards are used.</span></span>  <span data-ttu-id="4da66-284">この問題を回避するには、使用しないようにします `outline: none` 。</span><span class="sxs-lookup"><span data-stu-id="4da66-284">To avoid this problem, don't use `outline: none`.</span></span>

<span data-ttu-id="4da66-285">チュートリアルの詳細な手順については、「サイドバー メニューのキーボード フォーカスの不足を分析 [する」に移動します](test-analyze-no-focus-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="4da66-285">For detailed walkthrough steps, navigate to [Analyze the lack of indication of keyboard focus in a sidebar menu](test-analyze-no-focus-indicator.md).</span></span>


### <a name="analyzing-the-lack-of-keyboard-support-in-the-donation-form"></a><span data-ttu-id="4da66-286">寄附フォームでのキーボード サポートの不足の分析</span><span class="sxs-lookup"><span data-stu-id="4da66-286">Analyzing the lack of keyboard support in the donation form</span></span>

<span data-ttu-id="4da66-287">寄付フォームのボタンは、フォームのコントロールとして自動テスト ツールでは認識されない要素を使用 `div` して実装されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-287">The buttons on the donation form are implemented using the `div` element, which is not recognized by automated testing tools as a control on a form.</span></span>

<span data-ttu-id="4da66-288">これを調査するには、[検査] ツール\*\*\*\* を使用して、寄付フォームのボタンの上にマウス ポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="4da66-288">To investigate this, you can use the **Inspect** tool to hover over the donation form's buttons.</span></span>  <span data-ttu-id="4da66-289">その結果、情報オーバーレイのキーボードフォーカス可能な行の灰色のリングで示されている、キーボードにアクセス\*\*\*\* できる値はありません。</span><span class="sxs-lookup"><span data-stu-id="4da66-289">The result is that none of them are keyboard-accessible, as indicated by the gray ring on the **Keyboard-focusable** line of the information overlay.</span></span>  <span data-ttu-id="4da66-290">情報オーバーレイの **[名前**] 行と [役割] 行に示すように、寄附フォームのボタンには名前も含め、(要素を表す) 役割があります。つまり、支援テクノロジにはアクセスできないという意味です。 \*\*\*\* `generic` `div` `span`</span><span class="sxs-lookup"><span data-stu-id="4da66-290">As shown in the **Name** and **Role** lines of the information overlay, the buttons of the donation form also have no name, and have a role of `generic` (representing `div` or `span` elements), which means they aren't accessible to assistive technology.</span></span>

:::image type="complex" source="../media/a11y-testing-donation-button-info.msft.png" alt-text="フォームのボタンを調すと、キーボードにアクセスできないという結果が表示されます。" lightbox="../media/a11y-testing-donation-button-info.msft.png":::
    <span data-ttu-id="4da66-292">フォームのボタンを調すと、キーボードにアクセスできないという結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-292">Inspecting the buttons of the form shows that they aren't keyboard-accessible</span></span>
:::image-end:::

<span data-ttu-id="4da66-293">チュートリアルの詳細な手順については、「フォーム内のキーボード サポートの不足を [分析する」に移動します](test-analyze-no-keyboard-support.md)。</span><span class="sxs-lookup"><span data-stu-id="4da66-293">For detailed walkthrough steps, navigate to [Analyze the lack of keyboard support in a form](test-analyze-no-keyboard-support.md).</span></span>

<span data-ttu-id="4da66-294">**[Donate] ボタンを選択**すると、[**検査**] ツールが\*\*\*\*[要素] ツールに移動し、フォームの HTML を表示します。</span><span class="sxs-lookup"><span data-stu-id="4da66-294">If you select the **Donate** button, the **Inspect** tool takes you to the **Elements** tool and shows you the form's HTML.</span></span>

```HTML
<div class="donationrow">
    <div class="donationbutton">50</div>
    <div class="donationbutton">100</div>
    <div class="donationbutton">200</div>
</div>
<div class="donationrow">
    <label for="freedonation">Other</label>
    <input id="freedonation" class="smallinput">
</div>
<div class="donationrow">
    <div class="submitbutton">Donate</div>
</div>
```

<span data-ttu-id="4da66-295">and 要素の使用は有効であり、ラベルは意図した通り動作し、テキスト ボックスは `label` `input` `input` キーボードでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4da66-295">The use of the `label` and `input` elements are valid, which result in the label working as intended and the `input` textbox is keyboard-accessible.</span></span>  <span data-ttu-id="4da66-296">フォームの残りの部分では要素が使用されますが、スタイルは簡単ですが `div` 、意味的な意味はありません。</span><span class="sxs-lookup"><span data-stu-id="4da66-296">The rest of the form uses `div` elements, which are easy to style but have no semantic meaning.</span></span>

<span data-ttu-id="4da66-297">次に、フォームの JavaScript 機能を分析します。</span><span class="sxs-lookup"><span data-stu-id="4da66-297">Next, let's analyze the form's JavaScript functionality.</span></span> <span data-ttu-id="4da66-298">[ **要素]** で、[ **イベント リスナー] タブを選択** して、フォームの JavaScript を分析します。</span><span class="sxs-lookup"><span data-stu-id="4da66-298">In **Elements**, select the **Event Listeners** tab to analyze the form's JavaScript.</span></span>

:::image type="complex" source="../media/a11y-testing-event-handlers-on-button.msft.png" alt-text="フォームの JavaScript へのリンクを含む [イベント リスナー] タブ" lightbox="../media/a11y-testing-event-handlers-on-button.msft.png":::
    <span data-ttu-id="4da66-300">フォーム **の JavaScript** へのリンクを含む [イベント リスナー] タブ</span><span class="sxs-lookup"><span data-stu-id="4da66-300">The **Event Listeners** tab, with a link to the JavaScript for the form</span></span>
:::image-end:::

<span data-ttu-id="4da66-301">[イベント**リスナー] タブ**で、リンクを選択して [ソース] ツールを開き、フォームの機能を担当する `buttons.js:18` JavaScript を調えます。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4da66-301">On the **Event Listeners** tab, select the `buttons.js:18` link to open the **Sources** tool, and then inspect the JavaScript that's responsible for the form's functionality.</span></span>

:::image type="complex" source="../media/a11y-testing-form-handling-javascript.msft.png" alt-text="[ソース] ツールに表示される、寄付フォームの機能を担当する JavaScript" lightbox="../media/a11y-testing-form-handling-javascript.msft.png":::
    <span data-ttu-id="4da66-303">[ソース] ツールに表示される、寄付フォームの機能を担当する**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="4da66-303">The JavaScript that's responsible for the donation form's functionality, shown in the **Sources** tool</span></span>
:::image-end:::

<span data-ttu-id="4da66-304">イベントはマウス ポインターとキーボードの両方で動作しますので、ボタンでイベントを使用 `click` `click` する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4da66-304">Using `click` events with buttons is recommended because `click` events work with both mouse pointers and keyboards.</span></span>  <span data-ttu-id="4da66-305">ただし、要素はキーボードでアクセスできないので、Donate ボタンは要素として実装されます。この JavaScript はマウスを使用する場合 `div` \*\*\*\* `div` にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-305">However, because a `div` element isn't keyboard-accessible, and the **Donate** button is implemented as a `div` element, this JavaScript only runs when a mouse is used.</span></span>

<span data-ttu-id="4da66-306">ボタンとしての使用は、要素が提供する機能を作成するために追加の JavaScript が必要な `div` 従来の `button` 例です。</span><span class="sxs-lookup"><span data-stu-id="4da66-306">Using a `div` as a button is a classic example where extra JavaScript is needed to create functionality that `button` elements provide.</span></span> <span data-ttu-id="4da66-307">その結果、アクセスできないエクスペリエンスが発生します。</span><span class="sxs-lookup"><span data-stu-id="4da66-307">As a result, this leads to an experience that is inaccessible.</span></span>


### <a name="checking-the-accessibility-tree-for-keyboard-and-screen-reader-support"></a><span data-ttu-id="4da66-308">アクセシビリティ ツリーでキーボードとスクリーン リーダーのサポートを確認する</span><span class="sxs-lookup"><span data-stu-id="4da66-308">Checking the Accessibility Tree for keyboard and screen reader support</span></span>

<span data-ttu-id="4da66-309">[検査 **] ツール** を使用してページ上の各要素を個別に確認するには、時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="4da66-309">Using the **Inspect** tool to individually check each element on the page is time-consuming.</span></span>  <span data-ttu-id="4da66-310">代わりに、[アクセシビリティ] **タブを使用** して、ページの **アクセシビリティ ツリーを移動します**。</span><span class="sxs-lookup"><span data-stu-id="4da66-310">Instead, use the **Accessibility** tab to navigate the page's **Accessibility Tree**.</span></span>  <span data-ttu-id="4da66-311">アクセシビリティ ツリーは、ページがスクリーン リーダーなどの支援テクノロジに提供する情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4da66-311">The Accessibility Tree indicates what information the page provides to assistive technology such as screen readers.</span></span>

:::image type="complex" source="../media/a11y-testing-accessibility-tree.msft.png" alt-text="アクセシビリティ ツリーの [寄附フォーム] ボタン" lightbox="../media/a11y-testing-accessibility-tree.msft.png":::
    <span data-ttu-id="4da66-313">アクセシビリティ ツリーの **[寄附フォーム] ボタン**</span><span class="sxs-lookup"><span data-stu-id="4da66-313">Donation form button in the **Accessibility Tree**</span></span>
:::image-end:::

<span data-ttu-id="4da66-314">名前を持たなかったり、役割を持つツリー内の要素は、キーボード ユーザーや支援技術を使用しているユーザーが使用できないので、問題です `generic` 。</span><span class="sxs-lookup"><span data-stu-id="4da66-314">Any element in the tree that doesn't have a name, or that has a role of `generic`, is a problem, because that element won't be available to keyboard users or to people using assistive technology.</span></span>

<span data-ttu-id="4da66-315">チュートリアルの詳細な手順については、「アクセシビリティ ツリーでキーボードとスクリーン リーダーのサポートを確認 [する」に移動します](test-accessibility-tree.md)。</span><span class="sxs-lookup"><span data-stu-id="4da66-315">For detailed walkthrough steps, navigate to [Check the Accessibility Tree for keyboard and screen reader support](test-accessibility-tree.md).</span></span>


### <a name="analyzing-the-order-of-keyboard-access-to-sections-of-the-page"></a><span data-ttu-id="4da66-316">ページのセクションへのキーボード アクセスの順序を分析する</span><span class="sxs-lookup"><span data-stu-id="4da66-316">Analyzing the order of keyboard access to sections of the page</span></span>

<span data-ttu-id="4da66-317">もう 1 つの問題は、ページの不明瞭なタブオーダーです。</span><span class="sxs-lookup"><span data-stu-id="4da66-317">Another issue is the unclear tab order on the page.</span></span>  <span data-ttu-id="4da66-318">キーボード ユーザーは、ページ全体のすべての [その他] リンクをタブ移動した **後にのみ、** サイドバー ナビゲーション メニューに移動します。</span><span class="sxs-lookup"><span data-stu-id="4da66-318">Keyboard users reach the sidebar navigation menu only after tabbing through all the **More** links throughout the entire page.</span></span>  <span data-ttu-id="4da66-319">この例では、サイドバーのナビゲーション メニューは、そのページの別のセクションへのショートカットを意図しています。</span><span class="sxs-lookup"><span data-stu-id="4da66-319">In this example, the sidebar navigation menu is intended to be a shortcut to different sections of that page.</span></span>  <span data-ttu-id="4da66-320">このタブオーダーは、ユーザー エクスペリエンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="4da66-320">This tab order leads to a poor user experience.</span></span> 

<span data-ttu-id="4da66-321">わかりにくい順序の理由は、ドキュメントのソースの `Tab` 順序によって決まるからです。</span><span class="sxs-lookup"><span data-stu-id="4da66-321">The reason for the confusing `Tab` order is that it is determined by the source order of the document.</span></span>  <span data-ttu-id="4da66-322">タブオーダーは、既定のソース順序からその要素を取り出す要素の属性を使用して `tabindex` 変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="4da66-322">The tab order can also be modified by using the `tabindex` attribute on an element which takes that element out of the default source order.</span></span>

<span data-ttu-id="4da66-323">ドキュメントのソース コードでは、ページのメイン コンテンツの後にサイドバー ナビゲーション メニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-323">In the source code of the document, the sidebar navigation menu appears after the main content of the page.</span></span>  <span data-ttu-id="4da66-324">サイドバーナビゲーション メニューは、CSS を使用してサイドバー ナビゲーション メニューが配置されている場合にのみ、ページのメイン コンテンツの上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-324">The sidebar navigation menu appears above the main content of the page only because the sidebar navigation menu has been positioned using CSS.</span></span>

<span data-ttu-id="4da66-325">ドキュメントのソースの順序は、支援テクノロジにとって重要であり、レンダリングされたページに要素が表示される順序とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4da66-325">The source order of a document is important for assistive technology, and can be different than the order in which elements appear on the rendered page.</span></span>  <span data-ttu-id="4da66-326">CSS を使用すると、視覚的な方法でページ要素の順序を変更できますが、スクリーン リーダーなどの支援テクノロジは、その CSS と同じ順序でページ要素を表すという意味ではありません。</span><span class="sxs-lookup"><span data-stu-id="4da66-326">Using CSS, you can re-order page elements in a visual way, but that doesn't mean that assistive technology such as screen readers would represent page elements in the same order as that CSS.</span></span>

<span data-ttu-id="4da66-327">ページ要素の順序をテストするには、[アクセシビリティ] タブの **[ソース** オーダー ビューアー **] を使用** します。 下にスクロールして、[ソースの順序を **表示] チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="4da66-327">You can test the order of page elements by using the **Source Order Viewer** in the **Accessibility** tab.  Scroll down all the way and select the **Show Source Order** checkbox.</span></span>  <span data-ttu-id="4da66-328">要素の選択など、 **要素** ツールで DOM ツリーを移動すると、ソースの順序を表すレンダリングされたページのセクションに数値オーバーレイ `header` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-328">Now, when you navigate the DOM tree in the **Elements** tool, such as selecting the `header` element, numeric overlays are displayed on sections of the rendered page which represent the source order.</span></span> 

:::image type="complex" source="../media/a11y-testing-source-order-viewer.msft.png" alt-text="ソース オーダー ビューアーをオンにすると、ページ上の数値オーバーレイとしてソース コード内の要素の順序が表示されます。" lightbox="../media/a11y-testing-source-order-viewer.msft.png":::
    <span data-ttu-id="4da66-330">ソース オーダー ビューアー **をオンに** すると、ページ上の数値オーバーレイとしてソース コード内の要素の順序が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-330">Turning on the **Source Order Viewer** shows the order of the elements in the source code as numeric overlays on the page</span></span>
:::image-end:::

<span data-ttu-id="4da66-331">チュートリアルの詳細な手順については、「ソース オーダー ビューアーを [使用してキーボード サポートをテストする」に移動します](test-tab-key-source-order-viewer.md)。</span><span class="sxs-lookup"><span data-stu-id="4da66-331">For detailed walkthrough steps, navigate to [Test keyboard support using the Source Order Viewer](test-tab-key-source-order-viewer.md).</span></span>


## <a name="testing-contrast-of-text-colors-in-various-states"></a><span data-ttu-id="4da66-332">さまざまな状態でのテキストの色のコントラストのテスト</span><span class="sxs-lookup"><span data-stu-id="4da66-332">Testing contrast of text colors in various states</span></span>

<span data-ttu-id="4da66-333">検査 **ツールは** 、一度に 1 つの状態のアクセシビリティの問題を報告します。</span><span class="sxs-lookup"><span data-stu-id="4da66-333">The **Inspect** tool reports accessibility issues for one state at a time.</span></span>  <span data-ttu-id="4da66-334">まず、検査ツールを使用してページ要素の静的な状態のみを表示する制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="4da66-334">First, we'll describe the limitation of using the Inspect tool to view only the static state of a page element.</span></span>  <span data-ttu-id="4da66-335">次に、[スタイル] タブで **\:hov (Toggle Element State)** を選択して、ページ要素の他の状態を検査する方法 **について説明** します。</span><span class="sxs-lookup"><span data-stu-id="4da66-335">Then we'll explain how to inspect other states of a page element, by selecting **\:hov (Toggle Element State)** on the **Styles** tab.</span></span>

### <a name="checking-text-color-contrast-in-the-default-state"></a><span data-ttu-id="4da66-336">既定の状態でテキストの色のコントラストを確認する</span><span class="sxs-lookup"><span data-stu-id="4da66-336">Checking text color contrast in the default state</span></span>

<span data-ttu-id="4da66-337">[問題] ツールの色コントラストの自動テスト\*\*\*\* に加えて、[検査] ツールを\*\*\*\* 使用して、個々のページ要素のコントラストが十分かどうかを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="4da66-337">In addition to the automatic color-contrast tests in the **Issues** tool, you can also use the **Inspect** tool to check whether individual page elements have enough contrast.</span></span>  <span data-ttu-id="4da66-338">コントラスト情報を使用できる場合は、[ **検査** ] オーバーレイにコントラスト比とチェック ボックス項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-338">If contrast information is available, the **Inspect** overlay shows the contrast ratio and a checkbox item.</span></span>  <span data-ttu-id="4da66-339">緑色のチェック マーク アイコンは十分なコントラストを示し、黄色の警告アイコンは十分なコントラストを示します。</span><span class="sxs-lookup"><span data-stu-id="4da66-339">A green check mark icon indicates there's enough contrast, and a yellow alert icon indicates not enough contrast.</span></span>

<span data-ttu-id="4da66-340">たとえば、サイドバーのナビゲーション メニューのリンクには十分なコントラストがありますが、[寄附金の状態] セクションの緑色の **犬** リスト **アイテムは** 表示されません。</span><span class="sxs-lookup"><span data-stu-id="4da66-340">For example, the links in the sidebar navigation menu have enough contrast, but the green **Dogs** list item in the **Donation status** section doesn't.</span></span>  <span data-ttu-id="4da66-341">十分なコントラストを持つ要素は、Inspect オーバーレイの警告によって **フラグが設定** されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-341">An element that doesn't have enough contrast is flagged by a warning in the **Inspect** overlay.</span></span>

:::row:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-enough-contrast.msft.png" alt-text="[検査] オーバーレイに示すように、サイドバー ナビゲーション メニューのリンクには十分なコントラストがあります。" lightbox="../media/a11y-testing-enough-contrast.msft.png":::
            <span data-ttu-id="4da66-343">[検査] オーバーレイに示すように、サイドバー ナビゲーション メニューのリンクには十分なコントラスト **があります** 。</span><span class="sxs-lookup"><span data-stu-id="4da66-343">The links in the sidebar navigation menu have enough contrast, as shown in the **Inspect** overlay</span></span> :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-not-enough-contrast.msft.png" alt-text="十分なコントラストを持つ要素は、Inspect オーバーレイの警告によってフラグが設定されます。" lightbox="../media/a11y-testing-not-enough-contrast.msft.png":::
            <span data-ttu-id="4da66-345">十分なコントラストを持つ要素は、Inspect オーバーレイの警告によって **フラグが設定** されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-345">An element that doesn't have enough contrast is flagged by a warning in the **Inspect** overlay</span></span> :::image-end:::
    :::column-end:::
:::row-end:::

<span data-ttu-id="4da66-346">この方法 **で検査** ツールを使用しても、要素を完全にテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4da66-346">Using the **Inspect** tool in this way doesn't fully test your elements.</span></span> <span data-ttu-id="4da66-347">ページ上の要素の状態が異なる場合があります。そのすべてがテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4da66-347">Elements on the page may have different states, all of which need to be tested.</span></span> <span data-ttu-id="4da66-348">たとえば、サイドバーのナビゲーション メニューの上にマウス ポインターを置くと、リンクの色を変更するアニメーションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-348">For example, if you hover the mouse over the sidebar navigation menu, notice the animation which changes the color of the links.</span></span>

:::image type="complex" source="../media/a11y-testing-hover.msft.png" alt-text="マウス ポインターがマウス ポインターの上にあるとき、異なる色を示すメニュー項目" lightbox="../media/a11y-testing-hover.msft.png":::
    <span data-ttu-id="4da66-350">マウス ポインターがマウス ポインターの上にあるとき、異なる色を示すメニュー項目</span><span class="sxs-lookup"><span data-stu-id="4da66-350">The menu item showing different colors when the mouse pointer is over it</span></span>
:::image-end:::

### <a name="verify-accessibility-of-all-states-of-elements-such-as-the-contrast-on-hover"></a><span data-ttu-id="4da66-351">ホバーのコントラストなど、要素のすべての状態のアクセシビリティを確認する</span><span class="sxs-lookup"><span data-stu-id="4da66-351">Verify accessibility of all states of elements, such as the contrast on hover</span></span>

<span data-ttu-id="4da66-352">DevTools を使用する場合は、検査ツールがすべての状態の情報を同時に表示し\*\*\*\* ないので、要素のすべての状態をシミュレートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4da66-352">When using the DevTools, you'll need to simulate all states of your element, because the **Inspect** tool doesn't display information for all states at the same time.</span></span> <span data-ttu-id="4da66-353">この例では、[検査]\*\*\*\* ツールを使用している場合、スタイルの状態がトリガーされないので、サイドバー ナビゲーション メニューの [Cats] リンクの状態に到達して、状態のコントラスト比を分析できます。 `hover` \*\*\*\* `hover` `hover`</span><span class="sxs-lookup"><span data-stu-id="4da66-353">In this example, when using the **Inspect** tool, you can't reach the `hover` state of the **Cats** link on the sidebar navigation menu to analyze the contrast ratio in a `hover` state, because the `hover` state in your styles isn't triggered.</span></span>  <span data-ttu-id="4da66-354">代わりに、[スタイル] タブの状態シミュレーションを使用して **、Cats** メニュー項目の状態を **シミュレートする必要** があります。</span><span class="sxs-lookup"><span data-stu-id="4da66-354">Instead, you need to simulate the state of the **Cats** menu item, by using the state simulation in the **Styles** tab.</span></span>

<span data-ttu-id="4da66-355">詳細なチュートリアル手順については、「要素のすべての状態 [のアクセシビリティを確認する」に移動します](test-inspect-states.md)。</span><span class="sxs-lookup"><span data-stu-id="4da66-355">For detailed walkthrough steps, navigate to [Verify accessibility of all states of elements](test-inspect-states.md).</span></span>

<span data-ttu-id="4da66-356">[検査] **ツールを** オンにし、レンダリングされたページで、サイドバーのナビゲーション メニューで青い **Cats** リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="4da66-356">Turn on the **Inspect** tool and then in the rendered page, select the blue **Cats** link in the sidebar navigation menu.</span></span>  <span data-ttu-id="4da66-357">要素 **ツールが** 開き `a` 、DOM ツリーで要素が選択されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-357">The **Elements** tool opens, with the `a` element selected in the DOM tree.</span></span>  <span data-ttu-id="4da66-358">必要に応じて、DOM ツリーで、CSS の状態を持つ `hover` 要素に移動します。</span><span class="sxs-lookup"><span data-stu-id="4da66-358">If needed, in the DOM tree, navigate to the element that has a `hover` state in the CSS.</span></span>  <span data-ttu-id="4da66-359">この場合、要素 `a` には状態 `hover` があります。</span><span class="sxs-lookup"><span data-stu-id="4da66-359">In this case, the `a` element has a `hover` state.</span></span>

:::image type="complex" source="../media/a11y-testing-inspecting-link-to-hover.msft.png" alt-text="要素ツールでホバー状態を持つ要素を検査する" lightbox="../media/a11y-testing-inspecting-link-to-hover.msft.png":::
    <span data-ttu-id="4da66-361">要素ツールでホバー状態を持つ要素を検査する</span><span class="sxs-lookup"><span data-stu-id="4da66-361">Inspecting the element that has a hover state in the Elements tool</span></span>
:::image-end:::

<span data-ttu-id="4da66-362">[スタイル] **タブ** で **、\:hov (要素の状態の切り替え) ボタンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="4da66-362">On the **Styles** tab, select the **\:hov (Toggle Element State)** button.</span></span>  <span data-ttu-id="4da66-363">次に **、[Force 要素の状態] チェック** ボックスを使用して、シミュレートする状態を選択します。</span><span class="sxs-lookup"><span data-stu-id="4da66-363">Then use the **Force element state** checkboxes to choose which state to simulate.</span></span>

:::image type="complex" source="../media/a11y-testing-state-simulation.msft.png" alt-text="すべてのオプションを示す状態シミュレーション機能" lightbox="../media/a11y-testing-state-simulation.msft.png":::
    <span data-ttu-id="4da66-365">すべてのオプションを示す状態シミュレーション機能</span><span class="sxs-lookup"><span data-stu-id="4da66-365">The state simulation feature showing all the options</span></span>
:::image-end:::

<span data-ttu-id="4da66-366">**[\:hover] チェック ボックスを**オンにします。</span><span class="sxs-lookup"><span data-stu-id="4da66-366">Select the **\:hover** checkbox.</span></span>  <span data-ttu-id="4da66-367">DOM 要素の横に黄色のドットが表示され、DOM 要素にシミュレートされた状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-367">A yellow dot now appears next to the DOM element, indicating that the DOM element has a simulated state.</span></span>  <span data-ttu-id="4da66-368">また、サイドバーナビゲーション メニューの **[Cats]** リンクが、マウス ポインターがカーソルを置いた場合と同様に、ページ内で強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-368">Also, the **Cats** link in the sidebar navigation menu is now highlighted in the page, as if the mouse pointer were hovering over it.</span></span>

:::image type="complex" source="../media/a11y-testing-hover-simulated.msft.png" alt-text="ホバー状態をシミュレートする DevTools" lightbox="../media/a11y-testing-hover-simulated.msft.png":::
    <span data-ttu-id="4da66-370">ホバー状態をシミュレートする DevTools</span><span class="sxs-lookup"><span data-stu-id="4da66-370">DevTools simulating a hover state</span></span>
:::image-end:::

<span data-ttu-id="4da66-371">シミュレートされた状態を適用した後、もう一度\*\*\*\*[検査] ツールを使用して、ユーザーが上にカーソルを置いたときに要素のコントラストを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4da66-371">After the simulated state is applied, you can use the **Inspect** tool again to check the contrast of the element when the user hovers over it.</span></span>  <span data-ttu-id="4da66-372">この場合、コントラストが十分に高くはない。</span><span class="sxs-lookup"><span data-stu-id="4da66-372">In this case, the contrast isn't high enough.</span></span>

:::image type="complex" source="../media/a11y-testing-hover-contrast-testing.msft.png" alt-text="シミュレートされたホバー状態の要素のコントラストをテストする" lightbox="../media/a11y-testing-hover-contrast-testing.msft.png":::
    <span data-ttu-id="4da66-374">シミュレートされたホバー状態の要素のコントラストをテストする</span><span class="sxs-lookup"><span data-stu-id="4da66-374">Testing the contrast of an element in a simulated hover state</span></span>
:::image-end:::

<span data-ttu-id="4da66-375">状態シミュレーションは、ユーザーのニーズが異なっているかどうかを確認する良い方法です。</span><span class="sxs-lookup"><span data-stu-id="4da66-375">State simulation is also a good way to check whether you considered different user needs.</span></span>  <span data-ttu-id="4da66-376">サイドバーのナビゲーション メニューでは、状態にコントラストの `:focus` 問題が発生しているのを検出できます。</span><span class="sxs-lookup"><span data-stu-id="4da66-376">For the sidebar navigation menu, you can detect that the `:focus` state has a contrast issue.</span></span>


## <a name="use-the-rendering-tool-to-test-accessibility-for-visual-impairment"></a><span data-ttu-id="4da66-377">レンダリング ツールを使用して視覚障害のアクセシビリティをテストする</span><span class="sxs-lookup"><span data-stu-id="4da66-377">Use the Rendering tool to test accessibility for visual impairment</span></span>

### <a name="check-contrast-issues-with-dark-theme-and-light-themes"></a><span data-ttu-id="4da66-378">暗いテーマと明るいテーマのコントラストの問題を確認する</span><span class="sxs-lookup"><span data-stu-id="4da66-378">Check contrast issues with dark theme and light themes</span></span>

<span data-ttu-id="4da66-379">色のアクセシビリティに関するもう 1 つの考慮事項は、コントラストの問題をテストする必要があるテーマが異なる可能性がある点です。</span><span class="sxs-lookup"><span data-stu-id="4da66-379">Another consideration when it comes to color accessibility is that there could be different themes that you need to test for contrast issues.</span></span>  <span data-ttu-id="4da66-380">ほとんどのオペレーティング システムには、暗いモードとライト モードがあります。</span><span class="sxs-lookup"><span data-stu-id="4da66-380">Most operating systems have a dark mode and a light mode.</span></span>  <span data-ttu-id="4da66-381">Web ページでは、CSS メディア クエリを使用して、これらの異なる設定に対応できます。</span><span class="sxs-lookup"><span data-stu-id="4da66-381">Your webpage can react to these different settings using CSS media queries.</span></span>

<span data-ttu-id="4da66-382">このデモ ページには、明るいテーマと暗いテーマがあります。</span><span class="sxs-lookup"><span data-stu-id="4da66-382">This demo page has a light and a dark theme.</span></span>  <span data-ttu-id="4da66-383">両方のテーマをオペレーティング システムを変更せずにテストするには、レンダリング ツールで [濃][DevToolsColorSchemeSimulation] 色または明るい配色のシミュレーションを **使用** します。</span><span class="sxs-lookup"><span data-stu-id="4da66-383">You can test both themes without changing your operating system, by using [Dark or light color scheme simulation][DevToolsColorSchemeSimulation] in the **Rendering** tool.</span></span>  <span data-ttu-id="4da66-384">これまでのところ、この記事では、暗いテーマ設定を使用したオペレーティング システムを使用したデモ ページについて説明しました。</span><span class="sxs-lookup"><span data-stu-id="4da66-384">So far, this article looked at the demo page with an operating system using a dark theme setting.</span></span>  <span data-ttu-id="4da66-385">代わりにライト スキームをシミュレートし、ページを更新すると、[ **問題** ] ツールに 2 つの代わりに 6 つの色のコントラストの問題が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-385">If we instead simulate a light scheme and then refresh the page, the **Issues** tool shows six color contrast problems instead of two.</span></span>

<span data-ttu-id="4da66-386">チュートリアルの詳細な手順については、「濃いテーマと明るいテーマのコントラストの問題を確認 [する」に移動します](test-dark-mode.md)。</span><span class="sxs-lookup"><span data-stu-id="4da66-386">For detailed walkthrough steps, navigate to [Check for contrast issues with dark theme and light theme](test-dark-mode.md).</span></span>


<span data-ttu-id="4da66-387">レンダリング ツールでライト テーマに切り替える **場合** は、次の項目に注意してください。</span><span class="sxs-lookup"><span data-stu-id="4da66-387">When switching to a light theme in the **Rendering** tool, notice the following items.</span></span>

*  <span data-ttu-id="4da66-388">光のテーマが変更されたため、新しいコントラストの問題が検出されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-388">New contrast issues are detected because of the change to light theme.</span></span>
*  <span data-ttu-id="4da66-389">ページの **[寄附状況** ] セクション全体は、ライト モードでは読み取りできません。</span><span class="sxs-lookup"><span data-stu-id="4da66-389">The entire **Donation Status** section of the page is unreadable in light mode.</span></span>

:::row:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-new-contrast-issues-in-light-mode.msft.png" alt-text="光のテーマが変更されたため、新しいコントラストの問題が検出されました" lightbox="../media/a11y-testing-new-contrast-issues-in-light-mode.msft.png":::
            <span data-ttu-id="4da66-391">光のテーマが変更されたため、新しいコントラストの問題が検出されました</span><span class="sxs-lookup"><span data-stu-id="4da66-391">New contrast issues detected because of the change to light theme</span></span> :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-donation-state-light-contrast.msft.png" alt-text="光モードの場合にコントラストの問題としてフラグが設定された寄附状況アイテム" lightbox="../media/a11y-testing-donation-state-light-contrast.msft.png":::
            <span data-ttu-id="4da66-393">光モードの場合にコントラストの問題としてフラグが設定された寄附状況アイテム</span><span class="sxs-lookup"><span data-stu-id="4da66-393">The donation status items flagged as contrast issues when in light mode</span></span> :::image-end:::
    :::column-end:::
:::row-end:::


### <a name="verify-that-the-webpage-is-usable-by-people-with-color-blindness"></a><span data-ttu-id="4da66-394">色覚を持つユーザーが Web ページを使用できると確認する</span><span class="sxs-lookup"><span data-stu-id="4da66-394">Verify that the webpage is usable by people with color blindness</span></span>

<span data-ttu-id="4da66-395">異なる寄付の状態では、資金の状態を区別する唯一の手段として、色 (赤、緑、黄色) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-395">The different donation states use color (red, green, yellow) as the only means to differentiate between the states of funding.</span></span>  <span data-ttu-id="4da66-396">しかし、すべてのユーザーが意図した色でこれらの色を体験できるとは限らない。</span><span class="sxs-lookup"><span data-stu-id="4da66-396">You can't expect all of your users to experience these colors as intended, though.</span></span>  <span data-ttu-id="4da66-397">DevTools の [ビジョン][DevToolsVisionDeficiencies] 不足エミュレーション機能を使用すると、異なるビジョンを持つユーザーがデザインをどのように認識するのかシミュレーションすることで、これが十分ではないと分かっています。</span><span class="sxs-lookup"><span data-stu-id="4da66-397">If you use the [vision deficiencies emulation][DevToolsVisionDeficiencies] feature of DevTools, you can find out that this is not good enough, by simulating how people with different vision would perceive your design.</span></span>
<span data-ttu-id="4da66-398">詳細なチュートリアル手順については、「ページが色覚を持つユーザーが使用できるページを確認する [」に移動します](test-color-blindness.md)。</span><span class="sxs-lookup"><span data-stu-id="4da66-398">For detailed walkthrough steps, navigate to [Verify that the page is usable by people with color blindness](test-color-blindness.md).</span></span>
:::image type="complex" source="../media/a11y-testing-simulating-protanopia.msft.png" alt-text="ページを protanopia (赤い色の失明) を持つユーザーとして表示すると、ページが表示されます" lightbox="../media/a11y-testing-simulating-protanopia.msft.png":::
    <span data-ttu-id="4da66-400">protanopia (赤い色の失明) を持つユーザーがページを表示する</span><span class="sxs-lookup"><span data-stu-id="4da66-400">Showing the page as if someone with protanopia (red color blindness) would see it</span></span>
:::image-end:::



### <a name="verify-that-the-webpage-is-usable-with-blurred-vision"></a><span data-ttu-id="4da66-401">Web ページがぼやけたビジョンで使用できるのを確認する</span><span class="sxs-lookup"><span data-stu-id="4da66-401">Verify that the webpage is usable with blurred vision</span></span>

<span data-ttu-id="4da66-402">レンダリング ツールのもう **1 つの興味深い** 機能は、ぼやけたビジョンをシミュレートできる点です。</span><span class="sxs-lookup"><span data-stu-id="4da66-402">Another interesting feature of the **Rendering** tool is that you can simulate blurred vision.</span></span>  <span data-ttu-id="4da66-403">[ビジョンの不\*\*\*\* 備をエミュレートする]\*\*\*\* ドロップダウン リストから [ぼやけたビジョン] オプションを選択すると、上部メニューのテキストのドロップ シャドウがメニュー項目を読みにくいのが分かっています。</span><span class="sxs-lookup"><span data-stu-id="4da66-403">If we choose the **Blurred vision** option from the **Emulate vision deficiencies** dropdown list, we can see that the drop shadow on the text in the upper menu makes it hard to read the menu items.</span></span>
<span data-ttu-id="4da66-404">詳細なチュートリアル手順については、「ページがぼやけたビジョンで使用できる」 [に移動します](test-blurred-vision.md)。</span><span class="sxs-lookup"><span data-stu-id="4da66-404">For detailed walkthrough steps, navigate to [Verify that the page is usable with blurred vision](test-blurred-vision.md).</span></span>

:::image type="complex" source="../media/a11y-testing-simulating-blur.msft.png" alt-text="ぼやけたページをシミュレートすると、アクセシビリティの問題が発生する可能性があります" lightbox="../media/a11y-testing-simulating-blur.msft.png":::
    <span data-ttu-id="4da66-406">ぼやけたページをシミュレートすると、アクセシビリティの問題が発生する可能性があります</span><span class="sxs-lookup"><span data-stu-id="4da66-406">Simulating a blurred page can reveal accessibility issues</span></span>
:::image-end:::


### <a name="verify-that-the-page-is-usable-with-ui-animation-turned-off-reduced-motion"></a><span data-ttu-id="4da66-407">ページが UI アニメーションをオフにした状態で使用できる (モーションの減少) を確認する</span><span class="sxs-lookup"><span data-stu-id="4da66-407">Verify that the page is usable with UI animation turned off (reduced motion)</span></span>

<span data-ttu-id="4da66-408">これらの日にオペレーティング システムが使用するもう 1 つの設定は、アニメーションをオフにする方法です。</span><span class="sxs-lookup"><span data-stu-id="4da66-408">Another setting that operating systems come with these days are a way to turn off animations.</span></span>  <span data-ttu-id="4da66-409">アニメーションは、製品の使いやすさに役立ちますが、混乱から吐き気に至るまで、多くの問題を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4da66-409">Animations can help the usability of a product, but they can also cause a lot of problems, ranging from confusion to nausea.</span></span> <span data-ttu-id="4da66-410">これは、オペレーティング システムでオフにしたユーザーに対して、製品がアニメーションを表示しない理由です。</span><span class="sxs-lookup"><span data-stu-id="4da66-410">That's why your products should not show animations to users who turned them off in the operating system.</span></span>  <span data-ttu-id="4da66-411">CSS メディア クエリを使用すると、ユーザーがアニメーションを表示するかどうかを確認し、必要に応じてオフにできます。</span><span class="sxs-lookup"><span data-stu-id="4da66-411">By using a CSS media query, you can check whether the user wants to see animations, and turn them off accordingly.</span></span>  <span data-ttu-id="4da66-412">また、暗いモードや明るいモードと同様に、DevTools を使用して縮小モーションを [シミュレートする方法があります][DevToolsReducedMotion]。</span><span class="sxs-lookup"><span data-stu-id="4da66-412">And, much like with dark and light mode, there is a way to [simulate reduced motion using DevTools][DevToolsReducedMotion].</span></span>

<span data-ttu-id="4da66-413">ここでのデモ ページでは、アニメーションをオフにすると、サイドバー ナビゲーション メニューの別の部分を選択すると、ページのスムーズなスクロールが停止します。</span><span class="sxs-lookup"><span data-stu-id="4da66-413">In the demo page here, turning off animations will stop the smooth scrolling of the page when you select different parts of the sidebar navigation menu.</span></span>  <span data-ttu-id="4da66-414">これは、メディア クエリで CSS でスムーズなスクロール設定をラップすることで実現されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-414">This is achieved by wrapping the smooth scrolling setting in CSS in a media query:</span></span>

:::image type="complex" source="../media/a11y-testing-simulating-reduced-motion.msft.png" alt-text="縮小されたモーションと、ユーザーが必要なときにのみスムーズなスクロールが実行される CSS をシミュレートする" lightbox="../media/a11y-testing-simulating-reduced-motion.msft.png":::
    <span data-ttu-id="4da66-416">縮小されたモーションと、ユーザーが必要なときにのみスムーズなスクロールが実行される CSS をシミュレートする</span><span class="sxs-lookup"><span data-stu-id="4da66-416">Simulating reduced motion and the CSS that makes sure that smooth scrolling only happens when the user wants it</span></span>
:::image-end:::

```css
@media (prefers-reduced-motion: no-preference) {
  html {
    scroll-behavior: smooth;
  }
}
```

<span data-ttu-id="4da66-417">この CSS メディア クエリは、条件付きで "スムーズスクロール" アニメーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="4da66-417">This CSS media query conditionally runs the "smooth scrolling" animation.</span></span>  <span data-ttu-id="4da66-418">ただし、トップ ナビゲーション バー、サイドバー ナビゲーション メニュー、\*\*\*\* その他のリンクのアニメーションは、ユーザーがアニメーションを表示したくない場合でも実行されます。</span><span class="sxs-lookup"><span data-stu-id="4da66-418">But the animation of the top navigation bar, sidebar navigation menu, and **More** links still run, even when the user doesn't want to see animations.</span></span> <span data-ttu-id="4da66-419">これらの他のアニメーションは、追加のメディア クエリを追加するなどの条件付きで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4da66-419">Those other animations need to be conditionally run, such as by adding additional media queries.</span></span>

<span data-ttu-id="4da66-420">チュートリアルの詳細な手順については、「ページが UI アニメーションをオフにした状態で使用できる状態になっていることを確認 [する」に移動します](test-reduced-ui-motion.md)。</span><span class="sxs-lookup"><span data-stu-id="4da66-420">For detailed walkthrough steps, navigate to [Verify that the page is usable with UI animation turned off](test-reduced-ui-motion.md).</span></span>


## <a name="what-to-do-next"></a><span data-ttu-id="4da66-421">次に何をしますか?</span><span class="sxs-lookup"><span data-stu-id="4da66-421">What to do next?</span></span>

<span data-ttu-id="4da66-422">製品のアクセシビリティの問題を確実にキャッチするために使用できるツールは、かなり多く取り上がっています。</span><span class="sxs-lookup"><span data-stu-id="4da66-422">We've covered quite a few tools you can use to make sure that you catch accessibility problems in your products.</span></span>  <span data-ttu-id="4da66-423">このようなツールは、自動チェックや手動による詳細チェックから、さまざまな状態や環境のシミュレーションにまで及びます。</span><span class="sxs-lookup"><span data-stu-id="4da66-423">Such tools range from automated checks and manual detail checks to simulation of different states and environments.</span></span>  <span data-ttu-id="4da66-424">これらのツールは [、DevTools のアクセシビリティテスト機能に要約されています](reference.md)。</span><span class="sxs-lookup"><span data-stu-id="4da66-424">These tools are summarized in [Accessibility-testing features in DevTools](reference.md).</span></span>  <span data-ttu-id="4da66-425">ユーザー補助の障壁の多くは対話型の使用中にのみ表示されるので、自動化されたツールは製品内のすべての問題を見つけ出すことはありません。</span><span class="sxs-lookup"><span data-stu-id="4da66-425">Automated tools can't find all the problems in a product, because many of the accessibility barriers show up only during interactive use.</span></span>

<span data-ttu-id="4da66-426">これらのツールはいずれも、製品の適切なテストラウンドを支援技術を使用するユーザーに置き換え、必要なすべてのテストを確認する計画に従う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4da66-426">None of these tools can replace a proper round of testing your products with people that use assistive technologies and following a plan to check for all the required tests.</span></span> <span data-ttu-id="4da66-427">アクセシビリティインサイトの [評価][AccessibilityInsightsAssessment] 機能 [も使用できます][AccessibilityInsights]。</span><span class="sxs-lookup"><span data-stu-id="4da66-427">You can also use the [Assessments][AccessibilityInsightsAssessment] feature of [Accessibility Insights][AccessibilityInsights].</span></span>  <span data-ttu-id="4da66-428">次のような追加のチェックを実行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="4da66-428">You may need to perform additional checks such as:</span></span>

* <span data-ttu-id="4da66-429">ズームイン時のテスト。</span><span class="sxs-lookup"><span data-stu-id="4da66-429">Testing when zoomed-in.</span></span>
* <span data-ttu-id="4da66-430">スクリーン リーダーによるテスト。</span><span class="sxs-lookup"><span data-stu-id="4da66-430">Testing with screen readers.</span></span>
* <span data-ttu-id="4da66-431">音声認識によるテスト。</span><span class="sxs-lookup"><span data-stu-id="4da66-431">Testing with voice recognition.</span></span>
* <span data-ttu-id="4da66-432">ハイ コントラスト モードでのテスト。</span><span class="sxs-lookup"><span data-stu-id="4da66-432">Testing in high-contrast mode.</span></span>

<span data-ttu-id="4da66-433">Web 製品を改善するために何を行うのかを確認するもう 1 つの方法は、webhint 拡張機能を使用して[webhint][WebhintForCode]拡張機能を使用Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="4da66-433">Another way to find out what to do to improve your web product is to use the [webhint extension for Visual Studio Code][WebhintForCode].</span></span>  <span data-ttu-id="4da66-434">この拡張機能は、ソース コードで容易に検出できるアクセシビリティの問題にフラグを設定し、それらを修正する方法に関する分析情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="4da66-434">This extension flags the readily detectable accessibility problems in your source code and gives insights on how to fix them.</span></span>

:::image type="complex" source="../media/a11y-testing-webhint-in-vs-code.msft.png" alt-text="Webhint Visual Studio Code HTML 要素の下線を引き、問題の説明を表示してアクセシビリティの問題を表示する" lightbox="../media/a11y-testing-webhint-in-vs-code.msft.png":::
    <span data-ttu-id="4da66-436">Webhint Visual Studio Code HTML 要素の下線を引き、問題の説明を表示してアクセシビリティの問題を表示する</span><span class="sxs-lookup"><span data-stu-id="4da66-436">Webhint in Visual Studio Code, showing an accessibility issue by underlining the HTML element and showing an explanation of the problem</span></span>
:::image-end:::

<span data-ttu-id="4da66-437">DevTools の新しいアクセシビリティ機能に常に取り組み続け中です。</span><span class="sxs-lookup"><span data-stu-id="4da66-437">We're constantly working on new accessibility features for DevTools.</span></span>  <span data-ttu-id="4da66-438">不足している何かがある場合は、メッセージを送信し、何が可能かを教えて下さい。</span><span class="sxs-lookup"><span data-stu-id="4da66-438">If there is anything you are missing, send us a message and tell us what we can do.</span></span>


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="4da66-439">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="4da66-439">Getting in touch with the Microsoft Edge DevTools team</span></span>

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]


<!-- links -->
[DevToolsMediaQueries]: ../device-mode/index.md#show-media-queries "メディア クエリの表示 - DevTools アプリケーションでモバイル Microsoft Edgeをエミュレート|Microsoft Docs"
[DevToolsDeviceModeIndex]: ../device-mode/index.md "Microsoft Edge DevTools でモバイル デバイスをエミュレートする | Microsoft Docs"
[DevtoolsAccessibilityReference]: reference.md "DevTools |Microsoft Docs"
[DevToolsColorSchemeSimulation]: ./preferred-color-scheme-simulation.md "暗いまたは明るい配色のシミュレーション |Microsoft Docs"
[DevToolsIssuesTool]: ../issues/index.md "Microsoft Edge DevTools の問題を見つけて解決するツール | Microsoft Docs"
[DevToolsReducedMotion]: ./reduced-motion-simulation.md "モーション シミュレーションの|Microsoft Docs"
[DevToolsVisionDeficiencies]: ./emulate-vision-deficiencies.md "ビジョンの欠陥をエミュレート|Microsoft Docs"
<!-- links into test-issues-tool.md -->
[DevToolsAccessibilityTestIssuesToolViewAccSection]: test-issues-tool.md#view-the-accessibility-section-of-the-issues-tool "[問題] ツールの [アクセシビリティ] セクションを表示する - Web ページでアクセシビリティの問題を自動的にテスト|Microsoft Docs"
[DevtoolsAccessibilityTestIssuesToolCheckFieldsLabels]: test-issues-tool.md#verify-that-input-fields-have-labels "入力フィールドにラベルが含まれていますを確認する - ユーザー補助の問題について Web ページを自動的にテスト|Microsoft Docs" 
[DevtoolsAccessibilityTestIssuesToolCheckAltText]: test-issues-tool.md#verify-that-images-have-alt-text "画像に代替テキストが含まれています - Web ページでアクセシビリティの問題を自動的にテスト|Microsoft Docs "
[DevtoolsAccessibilityTestIssuesToolCheckContrast]: test-issues-tool.md#verify-that-text-colors-have-enough-contrast "テキストの色のコントラストが十分に高い - Web ページでアクセシビリティの問題が自動的にテスト|Microsoft Docs"
<!-- links into test-inspect-tool.md -->
[DevtoolsAccessibilityTestInspectToolColorHighlighting]: test-inspect-tool.md#identify-nested-regions-using-color-highlighting "色の強調表示を使用して入れ子になった領域を特定する - [検査] ツールを使用して、Web ページの上にマウス ポインターを置いてアクセシビリティの問題を検出|Microsoft Docs"
[DevtoolsAccessibilityTestInspectToolIndivElems]: test-inspect-tool.md#check-individual-elements-for-text-contrast-screen-reader-text-and-keyboard-support "個々の要素でテキストのコントラスト、スクリーン リーダー テキスト、キーボードのサポートを確認する - [検査] ツールを使用して、Web ページの上にマウス ポインターを置いてアクセシビリティの問題を検出|Microsoft Docs"
[DevtoolsAccessibilityTestInspectToolDomCss]: test-inspect-tool.md#use-the-inspect-tool-to-hover-over-the-webpage-to-highlight-the-dom-and-css "[検査] ツールを使用して Web ページにカーソルを合わせると、DOM と CSS が強調表示されます 。 [検査] ツールを使用して、Web ページの上にマウス ポインターを置いてアクセシビリティの問題を検出|Microsoft Docs"
<!-- external links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
[W3CContrastRatio]: https://www.w3.org/TR/WCAG21/#dfn-contrast-ratio "コントラスト比|W3C"
[WCAG]: https://www.w3.org/TR/WCAG21/ "Web コンテンツ アクセシビリティ ガイドライン |W3C"
[AccessibilityInsightsAssessment]: https://accessibilityinsights.io/docs/en/web/getstarted/assessment/ "Web サービスのアクセシビリティインサイトの評価|アクセシビリティインサイト"
[AccessibilityInsights]: https://accessibilityinsights.io "アクセシビリティインサイト"
[Lighthouse]: https://developers.google.com/web/tools/lighthouse/ "ライトハウス |Google"
[WebhintForCode]:https://aka.ms/webhint4code "webhint |Visual StudioMarketplace"
