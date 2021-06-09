---
description: '[問題] ツールの [アクセシビリティ] セクションを使用して、アクセシビリティの問題について Web ページを自動的にテストします。'
title: アクセシビリティの問題について Web ページを自動的にテストする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 986a021d2fd390cd45bd53dcfc37a83d58ed2338
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597496"
---
# <a name="automatically-test-a-webpage-for-accessibility-issues"></a><span data-ttu-id="d209a-104">アクセシビリティの問題について Web ページを自動的にテストする</span><span class="sxs-lookup"><span data-stu-id="d209a-104">Automatically test a webpage for accessibility issues</span></span>

<span data-ttu-id="d209a-105">[**問題]** ツールには\*\*\*\*、[アクセシビリティ] セクションが含まれています。画像に代替テキストが見つからない、フォーム フィールドのラベルが見つからない、テキストの色のコントラストが不十分ななどの問題を自動的に報告します。</span><span class="sxs-lookup"><span data-stu-id="d209a-105">The **Issues** tool includes an **Accessibility** section that automatically reports issues such as missing alternative text on images, missing labels on form fields, and insufficient contrast of text colors.</span></span>  <span data-ttu-id="d209a-106">Issues **ツール** は **、DevTools** の下部にあるドロワー内にあります。</span><span class="sxs-lookup"><span data-stu-id="d209a-106">The **Issues** tool is within the **Drawer** at the bottom of DevTools.</span></span>  <span data-ttu-id="d209a-107">この記事では、アクセシビリティ テストのデモ Web ページを使用して、問題ツールの **[アクセシビリティ** ] セクションを **使用** します。</span><span class="sxs-lookup"><span data-stu-id="d209a-107">This article uses the accessibility-testing demo webpage to step through using the **Accessibility** section of the **Issues** tool.</span></span>

<span data-ttu-id="d209a-108">Issues ツールを開く方法は **次** のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d209a-108">There are several ways to open the **Issues** tool, such as:</span></span>
*  <span data-ttu-id="d209a-109">DevTools **の右上にある** [問題] カウンター ![ \( Issues counter ](../media/issues-counter-icon.msft.png) \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="d209a-109">Select the **Issues counter** \(![Issues counter](../media/issues-counter-icon.msft.png)\) in the upper right of DevTools.</span></span>
*  <span data-ttu-id="d209a-110">要素ツール **の DOM** ツリーで **、Shift キー** を押しながら要素の波線下線をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d209a-110">In the **Elements** tool, in the DOM tree, **Shift+click** a wavy underline on an element.</span></span>
*  <span data-ttu-id="d209a-111">[コマンド] **メニューで、** と `issues` 入力し、[問題の表示 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d209a-111">In the **Command Menu**, type `issues`, and then select **Show Issues**.</span></span>


## <a name="view-the-accessibility-section-of-the-issues-tool"></a><span data-ttu-id="d209a-112">[問題] ツールの [アクセシビリティ] セクションを表示する</span><span class="sxs-lookup"><span data-stu-id="d209a-112">View the Accessibility section of the Issues tool</span></span>

1.  <span data-ttu-id="d209a-113">ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="d209a-113">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>  <span data-ttu-id="d209a-114">右上には、自動的に検出された問題の数と共に、問題カウンター \( **Issues** counter \) が音声バブル アイコンとして ![ ](../media/issues-counter-icon.msft.png) 表示されます。</span><span class="sxs-lookup"><span data-stu-id="d209a-114">In the upper right, the **Issues counter** \(![Issues counter](../media/issues-counter-icon.msft.png)\) appears, as a speech-bubble icon along with the number of automatically detected issues.</span></span>  <span data-ttu-id="d209a-115">ブラウザーに別の番号が表示され、DevTools を使用すると番号が更新される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d209a-115">A different number might appear in your browser, and the number might update as you use DevTools.</span></span>

    :::image type="complex" source="../media/a11y-testing-issues-tracker.msft.png" alt-text="現在のドキュメントに存在する問題の数を示す DevTools の Issues カウンター" lightbox="../media/a11y-testing-issues-tracker.msft.png":::
        <span data-ttu-id="d209a-117">現在 **のドキュメントに** 存在する問題の数を示す DevTools の Issues カウンター</span><span class="sxs-lookup"><span data-stu-id="d209a-117">The **Issues counter** in DevTools, indicating how many problems there are in the current document</span></span>
    :::image-end:::

1.  <span data-ttu-id="d209a-118">[問題 **] カウンターを選択します**。</span><span class="sxs-lookup"><span data-stu-id="d209a-118">Select the **Issues counter**.</span></span>  <span data-ttu-id="d209a-119">Issues **ツール** が開き **、DevTools** の下部にあるドロワーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d209a-119">The **Issues** tool opens, in the **Drawer** at the bottom of DevTools.</span></span>

    :::image type="complex" source="../media/a11y-testing-accessibility-issues.msft.png" alt-text="[問題] ツールに表示されるアクセシビリティの警告" lightbox="../media/a11y-testing-accessibility-issues.msft.png":::
        <span data-ttu-id="d209a-121">[問題] ツールに表示されるアクセシビリティの警告</span><span class="sxs-lookup"><span data-stu-id="d209a-121">Accessibility warnings displayed in the Issues tool</span></span>
    :::image-end:::

1.  <span data-ttu-id="d209a-122">[問題 **] タブで** 、[アクセシビリティ] **セクションを展開** します。</span><span class="sxs-lookup"><span data-stu-id="d209a-122">On the **Issues** tab, expand the **Accessibility** section.</span></span>


## <a name="verify-that-input-fields-have-labels"></a><span data-ttu-id="d209a-123">入力フィールドにラベルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d209a-123">Verify that input fields have labels</span></span>

<span data-ttu-id="d209a-124">入力フィールドにラベルが接続されているかどうかを確認するには、[問題] ツール\*\*\*\* を使用して、Web ページ全体を自動的にチェックし、[アクセシビリティ] セクションでこの問題**を報告**します。</span><span class="sxs-lookup"><span data-stu-id="d209a-124">To check whether input fields have labels connected to them, use the **Issues** tool, which automatically checks the entire webpage and reports this issue in the **Accessibility** section.</span></span>

1.  <span data-ttu-id="d209a-125">ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="d209a-125">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="d209a-126">右上の [問題]\*\*\*\* カウンター \( ![ Issues counter ](../media/issues-counter-icon.msft.png) \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="d209a-126">In the upper right, select the **Issues counter** \(![Issues counter](../media/issues-counter-icon.msft.png)\).</span></span>  <span data-ttu-id="d209a-127">Issues **ツール** が開き **、DevTools** の下部にあるドロワーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d209a-127">The **Issues** tool opens, in the **Drawer** at the bottom of DevTools.</span></span>

1.  <span data-ttu-id="d209a-128">[問題 **] タブで** 、[アクセシビリティ] **セクションを展開** します。</span><span class="sxs-lookup"><span data-stu-id="d209a-128">On the **Issues** tab, expand the **Accessibility** section.</span></span>

1.  <span data-ttu-id="d209a-129">[警告] を **展開します** `Form elements must have labels: Element has no title attribute Element has no placeholder attribute` 。</span><span class="sxs-lookup"><span data-stu-id="d209a-129">Expand the **Warning** `Form elements must have labels: Element has no title attribute Element has no placeholder attribute`.</span></span>

1. <span data-ttu-id="d209a-130">[要素で **開く] リンクを選択** します。</span><span class="sxs-lookup"><span data-stu-id="d209a-130">Select the **Open in Elements** link.</span></span>

    :::image type="complex" source="../media/a11y-testing-inspect-problematic-element.msft.png" alt-text="[問題] ツールでリンクを選択した後に問題のある HTML を表示する要素ツール" lightbox="../media/a11y-testing-inspect-problematic-element.msft.png":::
        <span data-ttu-id="d209a-132">[問題] ツールでリンクを選択した後に問題のある HTML を **表示する要素** ツール</span><span class="sxs-lookup"><span data-stu-id="d209a-132">Elements tool showing the problematic HTML after selecting the link in the **Issues** tool</span></span> :::image-end:::

    <span data-ttu-id="d209a-133">要素 **ツールが** 開き、DOM ツリーで要素が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="d209a-133">The **Elements** tool opens, with the element highlighted in the DOM tree.</span></span>  <span data-ttu-id="d209a-134">[ **スタイル]** ウィンドウには、要素に適用された CSS ルールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d209a-134">The **Styles** pane displays the applied CSS rules for the element.</span></span>  <span data-ttu-id="d209a-135">次のコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d209a-135">The following code is now displayed.</span></span>

    ```html
    <label>Search</label>
    <input type="search">
    <input type="submit" value="go">
    ```

    <span data-ttu-id="d209a-136">上記のコードでは、要素と特定の要素との間に接続が行われるため、要素が正 `label` `label` しく使用 `input` されません。</span><span class="sxs-lookup"><span data-stu-id="d209a-136">In the above code, the `label` element is used incorrectly, because there is no connection between the `label` element and a particular `input` element.</span></span>  <span data-ttu-id="d209a-137">要素を特定 `label` の要素に接続 `input` するには、次のオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="d209a-137">To connect the `label` element to a specific `input` element, use any of the following options.</span></span>
    *   <span data-ttu-id="d209a-138">要素内で `input` 要素をネスト `label` します。</span><span class="sxs-lookup"><span data-stu-id="d209a-138">Nest the `input` element within the `label` element.</span></span>
    *   <span data-ttu-id="d209a-139">要素に `label` 、要素の `for` 属性に一致する `id` 属性を追加 `input` します。</span><span class="sxs-lookup"><span data-stu-id="d209a-139">In the `label` element, add a `for` attribute that matches an `id` attribute of the `input` element.</span></span>

    <span data-ttu-id="d209a-140">要素間の接続の不足をテストする別の方法があります。</span><span class="sxs-lookup"><span data-stu-id="d209a-140">There's also another way to test for lack of connections between elements.</span></span> <span data-ttu-id="d209a-141">[要素 **] ツール** で `<label>Search</label>` 、DOM ツリーで要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="d209a-141">In the **Elements** tool, select the `<label>Search</label>` element in the DOM tree.</span></span>  <span data-ttu-id="d209a-142">Web ページで、フォーカスは検索ラベルにのみ表示され\*\*\*\*、入力テキスト ボックスには表示されません。</span><span class="sxs-lookup"><span data-stu-id="d209a-142">On the webpage, notice that focus only appears on the **Search** label, and not the input textbox.</span></span>  <span data-ttu-id="d209a-143">正しい実装では、入力テキスト ボックスと `search` 検索ラベルに **フォーカスが置** かされます。</span><span class="sxs-lookup"><span data-stu-id="d209a-143">The correct implementation would put focus on the `search` input textbox and the **Search** label.</span></span>

1.  <span data-ttu-id="d209a-144">正しい接続の例として、寄付フォームの **[その** 他] ラベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d209a-144">As an example of a correct connection, select the **Other** label on the donation form.</span></span>  <span data-ttu-id="d209a-145">一致する値と属性値があるため、フォーカス インジケーター ボックスが\*\*\*\*[その他] ラベルの横の入力テキスト ボックス `for` に正しく `id` 表示されます。</span><span class="sxs-lookup"><span data-stu-id="d209a-145">A focus-indicator box correctly appears on the input textbox next to the **Other** label, because there are matching `for` and `id` attribute values.</span></span>

1.  <span data-ttu-id="d209a-146">[問題 **] ツールで、[** さらに読 **む** ] を選択して、問題の詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="d209a-146">In the **Issues tool**, select **Further reading** to learn more about the issue.</span></span>  <span data-ttu-id="d209a-147">新しいタブでリンクを開く場合は **、Ctrl**キーを押しながら Windows/Linux のリンクをクリックするか、コマンドで macOS のリンク + \*\*\*\*\*\*\*\* + \*\*\*\* をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d209a-147">To open the link in a new tab, **Ctrl**+**click** the link on Windows/Linux, or **Command**+**click** the link on macOS.</span></span>

    :::image type="complex" source="../media/a11y-testing-more-information-links.msft.png" alt-text="問題に関する詳細な情報を示す [問題] タブのリンク" lightbox="../media/a11y-testing-more-information-links.msft.png":::
        <span data-ttu-id="d209a-149">問題に関 **する詳細** な情報を示す [問題] タブのリンク</span><span class="sxs-lookup"><span data-stu-id="d209a-149">Link on the **Issues** tab pointing to more in-depth information about the issue</span></span>
    :::image-end:::


## <a name="verify-that-images-have-alt-text"></a><span data-ttu-id="d209a-150">イメージに代替テキストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d209a-150">Verify that images have alt text</span></span>

<span data-ttu-id="d209a-151">基本的なアクセシビリティテストでは、画像に代替テキスト (alt _テキストとも呼_ばれる) が用意されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d209a-151">Basic accessibility testing requires making sure alternative text (also called _alt text_) is provided for images.</span></span>

<span data-ttu-id="d209a-152">画像に対して代替テキストが提供されているかどうかを自動的に確認するには、[\*\*\*\* アクセシビリティ] セクションがある [問題]**ツールを使用**します。</span><span class="sxs-lookup"><span data-stu-id="d209a-152">To automatically check whether alt text is provided for images, use the **Issues** tool, which has an **Accessibility** section.</span></span>  <span data-ttu-id="d209a-153">Issues **ツール** は、DevTools **の下部** にあるドロワーにあります。</span><span class="sxs-lookup"><span data-stu-id="d209a-153">The **Issues** tool is located in the **Drawer** at the bottom of DevTools.</span></span>

1.  <span data-ttu-id="d209a-154">ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="d209a-154">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="d209a-155">[問題] **ツールを開** くには **、DevTools** の右上にある [問題] カウンターを選択します。</span><span class="sxs-lookup"><span data-stu-id="d209a-155">To open the **Issues** tool, select the **Issues** counter in the upper right of DevTools.</span></span>

1.  <span data-ttu-id="d209a-156">[問題 **] タブで** 、警告を展開します `Images must have alternate text: Element has no title attribute` 。</span><span class="sxs-lookup"><span data-stu-id="d209a-156">On the **Issues** tab, expand the warning `Images must have alternate text: Element has no title attribute`.</span></span>  <span data-ttu-id="d209a-157">代替テキストがないイメージのインスタンスは 4 種類です。</span><span class="sxs-lookup"><span data-stu-id="d209a-157">There are four instances of images that lack alt text.</span></span>

    :::image type="complex" source="../media/a11y-testing-images-without-alt.msft.png" alt-text="代替テキストが見つからない問題ツールレポート画像" lightbox="../media/a11y-testing-images-without-alt.msft.png":::
        <span data-ttu-id="d209a-159">代替テキストが見つからない問題ツールレポート画像</span><span class="sxs-lookup"><span data-stu-id="d209a-159">The Issues tool reporting images that are missing alternative text</span></span>
    :::image-end:::

<span data-ttu-id="d209a-160">詳細については、[イメージ] に移動 [するには、代替テキストが必要です](https://dequeuniversity.com/rules/axe/4.1/image-alt)。</span><span class="sxs-lookup"><span data-stu-id="d209a-160">For more information, navigate to [Images must have alternate text](https://dequeuniversity.com/rules/axe/4.1/image-alt).</span></span>


## <a name="verify-that-text-colors-have-enough-contrast"></a><span data-ttu-id="d209a-161">テキストの色に十分なコントラストが設定されているのを確認する</span><span class="sxs-lookup"><span data-stu-id="d209a-161">Verify that text colors have enough contrast</span></span>

<span data-ttu-id="d209a-162">テキストの色のコントラストが十分かどうかを自動的に確認するには\*\*\*\*、[アクセシビリティ] セクションがある [問題]**ツールを使用**します。</span><span class="sxs-lookup"><span data-stu-id="d209a-162">To automatically check whether text colors have enough contrast, use the **Issues** tool, which has an **Accessibility** section.</span></span>  <span data-ttu-id="d209a-163">Issues **ツール** は、DevTools **の下部** にあるドロワーにあります。</span><span class="sxs-lookup"><span data-stu-id="d209a-163">The **Issues** tool is located in the **Drawer** at the bottom of DevTools.</span></span>

1.  <span data-ttu-id="d209a-164">ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="d209a-164">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="d209a-165">[問題] **ツールを開** くには **、DevTools** の右上にある [問題] カウンターを選択します。</span><span class="sxs-lookup"><span data-stu-id="d209a-165">To open the **Issues** tool, select the **Issues** counter in the upper right of DevTools.</span></span>  <span data-ttu-id="d209a-166">デモ Web ページの 2 つの要素のコントラストが十分ではないという警告が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d209a-166">You may receive warnings that two elements on the demo webpage don't have enough contrast.</span></span>

    :::image type="complex" source="../media/a11y-testing-contrast-issues.msft.png" alt-text="[問題] ツールで報告されたコントラストの問題" lightbox="../media/a11y-testing-contrast-issues.msft.png":::
        <span data-ttu-id="d209a-168">[問題] ツールで報告されたコントラストの問題</span><span class="sxs-lookup"><span data-stu-id="d209a-168">Contrast problems reported in the Issues tool</span></span>
    :::image-end:::

1.  <span data-ttu-id="d209a-169">設定によっては、[問題] タブ\*\*\*\* に、色のコントラストが不十分でテキスト コンテンツの読み取りが困難になる可能性があるという警告**が表示される場合があります**。</span><span class="sxs-lookup"><span data-stu-id="d209a-169">Depending on your settings, the **Issues** tab might have a warning like **Users may have difficulties reading text content due to insufficient color contrast**.</span></span>   <span data-ttu-id="d209a-170">この警告を展開し、[影響を受けるリソース **] を展開できます**。</span><span class="sxs-lookup"><span data-stu-id="d209a-170">You can expand that warning, and then expand **Affected resources**.</span></span>  <span data-ttu-id="d209a-171">要素の一覧が表示され、十分なコントラストを持つ要素の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d209a-171">A list of elements appears with a list of elements that don't have enough contrast.</span></span>


1.  <span data-ttu-id="d209a-172">要素を選択 `li.high` します。</span><span class="sxs-lookup"><span data-stu-id="d209a-172">Select the `li.high` element.</span></span>  <span data-ttu-id="d209a-173">レンダリングされた Web ページでは **、[Donate]** セクションの **[犬** ] リンクが強調表示され、小さな情報オーバーレイが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d209a-173">In the rendered webpage, the **Dogs** link in the **Donate** section is highlighted, displaying a small information overlay.</span></span>  <span data-ttu-id="d209a-174">これは、要素ツールの DOM ツリー内の要素にカーソルを合わせると表示されるオーバーレイと **同** じです。</span><span class="sxs-lookup"><span data-stu-id="d209a-174">This is the same overlay that appears when you hover over an element in the DOM tree in the **Elements** tool.</span></span>

    :::image type="complex" source="../media/a11y-testing-element-with-contrast-issues.msft.png" alt-text="[影響を受けるリソース] セクションでリンクを選択した後に強調表示された Web ページ内の要素" lightbox="../media/a11y-testing-element-with-contrast-issues.msft.png":::
        <span data-ttu-id="d209a-176">[影響を受けるリソース] セクションでリンクを選択した後に強調表示された Web**ページ内の要素**</span><span class="sxs-lookup"><span data-stu-id="d209a-176">Element in the webpage highlighted after selecting a link in the **Affected Resources** section</span></span>
    :::image-end:::


### <a name="wavy-underlines-in-the-dom-tree-indicate-automatically-detected-issues"></a><span data-ttu-id="d209a-177">DOM ツリーの波の下線は、自動的に検出された問題を示します</span><span class="sxs-lookup"><span data-stu-id="d209a-177">Wavy underlines in the DOM tree indicate automatically detected issues</span></span> 

<span data-ttu-id="d209a-178">要素ツールの DOM ツリー **は、HTML** 内で直接問題に波線を付け、下線を付けフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="d209a-178">The DOM tree in the **Elements** tool flags issues directly in the HTML with wavy underlines.</span></span>  <span data-ttu-id="d209a-179">これらの問題は、問題ツール **によって報告** されます。</span><span class="sxs-lookup"><span data-stu-id="d209a-179">These issues are reported by the **Issues** tool.</span></span>  <span data-ttu-id="d209a-180">下線 **が波打つ** 要素を Shift キーを押しながらクリックすると、[問題] **ツールが** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="d209a-180">When you **Shift+click** any element with a wavy underline, the **Issues tool** is displayed.</span></span>

1.  <span data-ttu-id="d209a-181">要素ツール **の DOM** ツリーで **、Shift キー** を押しながら要素をクリックします。この要素の下に波 `<input type="search">` 線が表示されます `input` 。</span><span class="sxs-lookup"><span data-stu-id="d209a-181">In the **Elements** tool, in the DOM tree, **Shift+click** the element `<input type="search">`, which has a wavy line under `input`.</span></span>  <span data-ttu-id="d209a-182">[ **問題] ツールが** 表示され、その要素の問題が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d209a-182">The **Issues tool** is displayed, and shows the issue for that element.</span></span>

    :::image type="complex" source="../media/a11y-testing-wavy-underlines.msft.png" alt-text="DOM ビューに波の下線がある要素に問題がある" lightbox="../media/a11y-testing-wavy-underlines.msft.png":::
        <span data-ttu-id="d209a-184">DOM ビューに波の下線がある要素に問題がある</span><span class="sxs-lookup"><span data-stu-id="d209a-184">An element that has a wavy underline in the DOM view has an issue</span></span>
    :::image-end:::


## <a name="see-also"></a><span data-ttu-id="d209a-185">関連項目</span><span class="sxs-lookup"><span data-stu-id="d209a-185">See also</span></span>

*  [<span data-ttu-id="d209a-186">DevTools の問題ツールの問題Microsoft Edge見つけて修正する</span><span class="sxs-lookup"><span data-stu-id="d209a-186">Find and fix problems with the Microsoft Edge DevTools Issues tool</span></span>][DevToolsIssuesTool]
*  [<span data-ttu-id="d209a-187">DevTools を使用したアクセシビリティ テストの概要</span><span class="sxs-lookup"><span data-stu-id="d209a-187">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="d209a-188">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="d209a-188">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsIssuesTool]: ../issues/index.md "Microsoft Edge DevTools の問題を見つけて解決するツール | Microsoft Docs"
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
