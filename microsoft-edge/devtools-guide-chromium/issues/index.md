---
description: 現在の Web ページの問題を特定して修正するには、[問題] ツールを使用します。
title: 問題ツールを使用して問題を見つけて修正する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/24/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 86277c509aa4b67635661ba3a316fb5b1e3b9d14
ms.sourcegitcommit: e150d798161277fd3fc610838ef2611dc08f5cf6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2021
ms.locfileid: "11624711"
---
<!-- Copyright Sam Dutton

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# <a name="find-and-fix-problems-using-the-issues-tool"></a><span data-ttu-id="def22-104">問題ツールを使用して問題を見つけて修正する</span><span class="sxs-lookup"><span data-stu-id="def22-104">Find and fix problems using the Issues tool</span></span>

<span data-ttu-id="def22-105">DevTools Microsoft Edge、Issues ツール\*\*\*\* は現在の Web ページを自動的に分析し、種類別にグループ化された問題を報告し、問題の説明と解決に役立つドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="def22-105">In Microsoft Edge DevTools, the **Issues** tool automatically analyzes the current webpage, reports issues grouped by type, and provides documentation to help explain and resolve the issues.</span></span>

<span data-ttu-id="def22-106">Issues **ツールは** 、次のカテゴリでフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="def22-106">The **Issues** tool provides feedback in the following categories:</span></span>
*  <span data-ttu-id="def22-107">アクセシビリティ。</span><span class="sxs-lookup"><span data-stu-id="def22-107">Accessibility.</span></span>
*  <span data-ttu-id="def22-108">ブラウザー間の互換性。</span><span class="sxs-lookup"><span data-stu-id="def22-108">Compatibility across browsers.</span></span>
*  <span data-ttu-id="def22-109">パフォーマンス。</span><span class="sxs-lookup"><span data-stu-id="def22-109">Performance.</span></span>
*  <span data-ttu-id="def22-110">プログレッシブ Web アプリ。</span><span class="sxs-lookup"><span data-stu-id="def22-110">Progressive Web Apps.</span></span>
*  <span data-ttu-id="def22-111">セキュリティ。</span><span class="sxs-lookup"><span data-stu-id="def22-111">Security.</span></span>
*  <span data-ttu-id="def22-112">その他。</span><span class="sxs-lookup"><span data-stu-id="def22-112">Other.</span></span>

<span data-ttu-id="def22-113">問題ツールの**フィードバック**は、Chromium プラットフォーム、Deque axe、MDN ブラウザー互換性データ、webhint など、いくつかのソースによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="def22-113">Feedback in the **Issues** tool is provided by several sources, including the Chromium platform, Deque axe, MDN browser compatibility data, and webhint.</span></span>  <span data-ttu-id="def22-114">[問題] ツールを設定するフィードバックのこれらのソースの詳細 **については、次** の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="def22-114">For information about these sources of feedback that populate the **Issues** tool, navigate to:</span></span>
*  [<span data-ttu-id="def22-115">axe Tools の概要</span><span class="sxs-lookup"><span data-stu-id="def22-115">axe Tools Overview</span></span>][DequeAxe]
*  [<span data-ttu-id="def22-116">browser-compat-data repo</span><span class="sxs-lookup"><span data-stu-id="def22-116">browser-compat-data repo</span></span>][MDNCompat]
*  [<span data-ttu-id="def22-117">Webhint</span><span class="sxs-lookup"><span data-stu-id="def22-117">webhint</span></span>][webhintIo]


## <a name="open-the-issues-tool"></a><span data-ttu-id="def22-118">[問題] ツールを開く</span><span class="sxs-lookup"><span data-stu-id="def22-118">Open the Issues tool</span></span>

<span data-ttu-id="def22-119">次の手順を実行して、デモ ページ **を使用して Issues** ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="def22-119">Perform the following steps to open the **Issues** tool using a demo page.</span></span>


1.  <span data-ttu-id="def22-120">修正する問題を含む Web ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="def22-120">Navigate to a webpage that contains issues to fix.</span></span>  <span data-ttu-id="def22-121">たとえば、新しいタブ [またはウィンドウでアクセシビリティ テストの][A11ytestingPagewitherrors] デモ ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="def22-121">For example, open the [accessibility-testing demo page][A11ytestingPagewitherrors] in a new tab or window.</span></span>

1.  <span data-ttu-id="def22-122">DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="def22-122">Open DevTools.</span></span>  <span data-ttu-id="def22-123">数秒後、DevTools の右上隅に **Issues** カウンター ![ ](../media/issues-counter-icon.msft.png) \( Issues counter \) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="def22-123">After a few seconds, the **Issues counter** \(![Issues counter](../media/issues-counter-icon.msft.png)\) appears, in the upper right corner of DevTools.</span></span>  <span data-ttu-id="def22-124">[問題] カウンターの問題の数が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="def22-124">The number of issues in your Issues counter might be different.</span></span>

1.  <span data-ttu-id="def22-125">[問題 **] カウンターを選択します**。</span><span class="sxs-lookup"><span data-stu-id="def22-125">Select the **Issues counter**.</span></span>  <span data-ttu-id="def22-126">[ **問題] ツールが** 開き、さまざまなカテゴリにグループ化された問題が表示されます。</span><span class="sxs-lookup"><span data-stu-id="def22-126">The **Issues** tool opens with issues grouped into different categories.</span></span>

    :::image type="complex" source="../media/issues-tool-categories.msft.png" alt-text="デモ ページの [問題] ツールの問題のカテゴリ" lightbox="../media/issues-tool-categories.msft.png":::
       <span data-ttu-id="def22-128">デモ ページの [問題] ツールの問題のカテゴリ</span><span class="sxs-lookup"><span data-stu-id="def22-128">Categories of issues in the Issues tool on the demo page</span></span>
    :::image-end:::

### <a name="other-ways-to-open-the-issues-tool"></a><span data-ttu-id="def22-129">問題ツールを開くその他の方法</span><span class="sxs-lookup"><span data-stu-id="def22-129">Other ways to open the Issues tool</span></span>

<span data-ttu-id="def22-130">問題ツールを開く方法は **次のとおりです** 。</span><span class="sxs-lookup"><span data-stu-id="def22-130">There are several additional ways to open the **Issues** tool:</span></span>
*  <span data-ttu-id="def22-131">メイン パネル**またはドロワーで**[その他のツール ] ( ) メニューを選択し、[ **+** 問題]**を選択します**。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="def22-131">Select the **More Tools** (**+**) menu in the main panel or the **Drawer**, and then select **Issues**.</span></span>
*  <span data-ttu-id="def22-132">**[DevTools のカスタマイズと制御] [** その  >  **他のツールの問題**  >  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="def22-132">Select **Customize and control DevTools** > **More tools** > **Issues**.</span></span>
*  <span data-ttu-id="def22-133">要素ツールの DOM ツリー **で** 、波線付き下線付き要素名を `Shift` 選択してクリックします。</span><span class="sxs-lookup"><span data-stu-id="def22-133">In the DOM tree in the **Elements** tool, select `Shift` and then click a wavy-underlined element name.</span></span>  <span data-ttu-id="def22-134">または、波線付き下線付き要素のコンテキスト メニューを開き、[問題の表示 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="def22-134">Or, open the context menu on a wavy-underlined element and then select **View issues**.</span></span>

### <a name="issues-are-automatically-ordered-by-severity"></a><span data-ttu-id="def22-135">問題は重大度によって自動的に順序付けされます。</span><span class="sxs-lookup"><span data-stu-id="def22-135">Issues are automatically ordered by severity</span></span>

<span data-ttu-id="def22-136">問題の各カテゴリ内で、最初にエラーが一覧表示され、次に警告が表示され、次にヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="def22-136">Within each category of issues, first the errors are listed, then warnings, and then tips.</span></span>

:::image type="complex" source="../media/issues-ordered-by-severity.msft.png" alt-text="[問題] ツールには、重大度別に並べ替えたパフォーマンスの問題が表示されます。" lightbox="../media/issues-ordered-by-severity.msft.png":::
   <span data-ttu-id="def22-138">[ **問題] ツールには** 、重大度別に並べ替えたパフォーマンスの問題が表示されます。</span><span class="sxs-lookup"><span data-stu-id="def22-138">The **Issues** tool displays Performance issues sorted by severity</span></span>
:::image-end:::

### <a name="include-third-party-issues"></a><span data-ttu-id="def22-139">サードパーティの問題を含める</span><span class="sxs-lookup"><span data-stu-id="def22-139">Include third-party issues</span></span>

<span data-ttu-id="def22-140">サード パーティのサイトによって発生する問題を含めるには、[問題] ツールの\*\*\*\* 上部にある [サードパーティの問題を含める] チェック ボックス**をオン**にします。</span><span class="sxs-lookup"><span data-stu-id="def22-140">To include issues that are caused by third-party sites, at the top of the **Issues** tool, select the **Include third-party issues** checkbox.</span></span>


## <a name="expand-entries-in-the-issues-tool"></a><span data-ttu-id="def22-141">[問題] ツールのエントリを展開する</span><span class="sxs-lookup"><span data-stu-id="def22-141">Expand entries in the Issues tool</span></span>

<span data-ttu-id="def22-142">Issues **ツールには** 、各問題に適用する追加のドキュメントと推奨される修正プログラムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="def22-142">The **Issues** tool presents additional documentation and recommended fixes to apply to each issue.</span></span>  <span data-ttu-id="def22-143">この追加情報を取得するために問題を展開するには、次のように問題を選択します。</span><span class="sxs-lookup"><span data-stu-id="def22-143">To expand an issue to get this additional information, select an issue, as follows.</span></span>

1.  <span data-ttu-id="def22-144">新しい [ウィンドウまたはタブで][A11ytestingPagewitherrors] デモ ページを開き、DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="def22-144">Open the [demo page][A11ytestingPagewitherrors] in a new window or tab, and then open DevTools.</span></span>

1.  <span data-ttu-id="def22-145">[問題 **] カウンター** \( **Issues counter** \) を選択して ![ 、[問題] ツールを ](../media/issues-counter-icon.msft.png) 開きます。</span><span class="sxs-lookup"><span data-stu-id="def22-145">Open the **Issues** tool by selecting the **Issues counter** \(![Issues counter](../media/issues-counter-icon.msft.png)\).</span></span>

1.  <span data-ttu-id="def22-146">問題を選択して、問題を展開します。</span><span class="sxs-lookup"><span data-stu-id="def22-146">Select an issue to expand the issue.</span></span>

    :::image type="complex" source="../media/issues-tool-initial-view-accessibility-page.msft.png" alt-text="問題の修正方法に関する追加情報を表示する Issues ツール" lightbox="../media/issues-tool-initial-view-accessibility-page.msft.png":::
       <span data-ttu-id="def22-148">問題 **の修正** 方法に関する追加情報を表示する Issues ツール</span><span class="sxs-lookup"><span data-stu-id="def22-148">The **Issues** tool displaying additional information on how to fix the issue</span></span>
    :::image-end:::

<span data-ttu-id="def22-149">表示される各問題には、次のコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="def22-149">Each displayed issue has the following components:</span></span>
*   <span data-ttu-id="def22-150">問題を説明する見出し。</span><span class="sxs-lookup"><span data-stu-id="def22-150">A headline describing the issue.</span></span>
*   <span data-ttu-id="def22-151">より多くのコンテキストと提案されたソリューションを提供する説明。</span><span class="sxs-lookup"><span data-stu-id="def22-151">A description providing more context and proposed solutions.</span></span>
*   <span data-ttu-id="def22-152">要素 **、ソース**、ネットワーク ツールなどの DevTools のリソースにリンク\*\*\*\* する、\*\*\*\* 影響を受けるリソース**セクション**。</span><span class="sxs-lookup"><span data-stu-id="def22-152">An **AFFECTED RESOURCES** section that links to resources in DevTools, such as the **Elements**, **Sources**, or **Network** tool.</span></span>
*   <span data-ttu-id="def22-153">その他のドキュメントへのリンク。</span><span class="sxs-lookup"><span data-stu-id="def22-153">Links to further documentation.</span></span>


## <a name="view-issues-in-context-of-an-associated-tool"></a><span data-ttu-id="def22-154">関連付けられたツールのコンテキストで問題を表示する</span><span class="sxs-lookup"><span data-stu-id="def22-154">View issues in context of an associated tool</span></span>

<span data-ttu-id="def22-155">問題ツールの問題**には**、要素、ソース、ネットワーク ツールなど、さまざまなツールを開く\*\*\*\* 1\*\*\*\* つ以上のリンクが**含まれる場合**があります。</span><span class="sxs-lookup"><span data-stu-id="def22-155">An issue in the **Issues** tool may include one or more links that open different tools, such as the **Elements**, **Sources**, or **Network** tool.</span></span> <span data-ttu-id="def22-156">これらのツールのいずれかを開き、追加のトラブルシューティング手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="def22-156">You can open one of these tools to perform additional troubleshooting steps.</span></span> <span data-ttu-id="def22-157">[問題] ツールからリンク ツール **を開く場合** は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="def22-157">To open a linked tool from the **Issues** tool, perform the following steps.</span></span>

1.  <span data-ttu-id="def22-158">前のセクションで説明したように、デモ ページを開き、[問題] ツールで問題 **を展開** します。</span><span class="sxs-lookup"><span data-stu-id="def22-158">As described in the previous section, open the demo page and then expand an issue in the **Issues** tool.</span></span>

1.  <span data-ttu-id="def22-159">[**影響を受けるリソース**  >  **] で、** ツール名を選択します。</span><span class="sxs-lookup"><span data-stu-id="def22-159">In **AFFECTED RESOURCES** > **Open in**, select the tool name.</span></span>  <span data-ttu-id="def22-160">影響を受けるリソースが選択したツールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="def22-160">The affected resource is displayed in the selected tool.</span></span>

    :::image type="complex" source="../media/issues-tool-affected-resource-opens-elements-tool.msft.png" alt-text="問題ツール内から影響を受けるリソースを開くツールを選択する" lightbox="../media/issues-tool-affected-resource-opens-elements-tool.msft.png":::
       <span data-ttu-id="def22-162">問題ツール内から影響を受けるリソースを開くツールを選択する</span><span class="sxs-lookup"><span data-stu-id="def22-162">Select a tool to open an affected resource from within the Issues tool</span></span>
    :::image-end:::

    <span data-ttu-id="def22-163">展開された問題には、 **影響を受** けるリソースをネットワーク ツールに表示するネットワーク リンクがある **場合** があります。</span><span class="sxs-lookup"><span data-stu-id="def22-163">An expanded issue may have a **Network** link, to display the affected resource in the **Network** tool.</span></span>

    :::image type="complex" source="../media/issues-tab-view-issue.msft.png" alt-text="ネットワーク リソース リンクを選択すると、[ネットワーク] ツールが開きます。" lightbox="../media/issues-tab-view-issue.msft.png":::
    <span data-ttu-id="def22-165">ネットワーク **リソース リンク** を選択すると、[ネットワーク] **ツールが** 開きます。</span><span class="sxs-lookup"><span data-stu-id="def22-165">The **Network** tool opens when you select a **Network** resource link</span></span>
    :::image-end:::


## <a name="open-issues-from-the-dom-tree"></a><span data-ttu-id="def22-166">DOM ツリーから問題を開く</span><span class="sxs-lookup"><span data-stu-id="def22-166">Open issues from the DOM tree</span></span>

<span data-ttu-id="def22-167">要素に関連する問題がある場合、要素ツールの DOM\*\*\*\* ツリーには、要素名の下線が波線で表示されます。</span><span class="sxs-lookup"><span data-stu-id="def22-167">If an element has an associated issue, the DOM tree in the **Elements** tool shows a wavy underline under the element name.</span></span>  <span data-ttu-id="def22-168">要素のコンテキスト メニュー (右クリック) を開き、[問題の\*\*\*\* 表示] を選択するか、下線が波状の要素を選択して `Shift` 左クリックします。</span><span class="sxs-lookup"><span data-stu-id="def22-168">You can open the context menu (right-click) on the element and then select **View issues**, or select `Shift` and left-click the element with the wavy underline.</span></span>

<span data-ttu-id="def22-169">DOM ツリーに波線が付く要素の問題を表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="def22-169">To display an issue for elements with wavy underlines in the DOM tree, perform the following steps.</span></span>

1.  <span data-ttu-id="def22-170">デモ ページなどのページを新しいタブ [または][A11ytestingPagewitherrors]ウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="def22-170">Open a page, such as the [demo page][A11ytestingPagewitherrors], in a new tab or window.</span></span>

1.  <span data-ttu-id="def22-171">DevTools を開き、[要素] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="def22-171">Open DevTools and then select the **Elements** tab.</span></span>

1.  <span data-ttu-id="def22-172">DOM ツリーで、 を展開します `<body>`  >  `<header>`  >  `<form>` 。</span><span class="sxs-lookup"><span data-stu-id="def22-172">In the DOM tree, expand `<body>` > `<header>` > `<form>`.</span></span>  <span data-ttu-id="def22-173">要素に波 `<input>` の下線が付い注意してください。</span><span class="sxs-lookup"><span data-stu-id="def22-173">Notice that the `<input>` element has a wavy underline.</span></span>

    :::image type="complex" source="../media/issues-wavy-underlines-dom-tree.msft.png" alt-text="要素ツールの DOM ツリー内のウェーブ下線付き問題" lightbox="../media/issues-wavy-underlines-dom-tree.msft.png":::
       <span data-ttu-id="def22-175">要素ツールの**DOM**ツリー内のウェーブ下線**付き問題**</span><span class="sxs-lookup"><span data-stu-id="def22-175">Wavy-underlined issues in the **DOM tree** in the **Elements** tool</span></span>
    :::image-end:::

1.  <span data-ttu-id="def22-176">要素にカーソルを合 `<input>` わせる。</span><span class="sxs-lookup"><span data-stu-id="def22-176">Hover over the `<input>` element.</span></span>  <span data-ttu-id="def22-177">ヒントには、問題に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="def22-177">A tooltip displays information about the issue.</span></span>

1.  <span data-ttu-id="def22-178">下線が波打つ要素のコンテキスト メニューを開き、[問題の表示] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="def22-178">Open the context menu on the element with the wavy underline, and then select **View issues**.</span></span>  <span data-ttu-id="def22-179">[ **問題] ツール** が開き、その要素に関連付けられている問題が表示されます。</span><span class="sxs-lookup"><span data-stu-id="def22-179">The **Issues** tool opens and displays the issue that's associated with that element.</span></span>

    :::image type="complex" source="../media/issues-opened-from-dom-tree-wavy-underline.msft.png" alt-text="DOM ツリー内の波線付き下線付き要素の問題の詳細" lightbox="../media/issues-opened-from-dom-tree-wavy-underline.msft.png":::
       <span data-ttu-id="def22-181">DOM ツリー内の波線付き下線付き要素の問題の **詳細**</span><span class="sxs-lookup"><span data-stu-id="def22-181">Details about issues on a wavy-underlined element in the **DOM tree**</span></span>
    :::image-end:::


## <a name="see-also"></a><span data-ttu-id="def22-182">関連項目</span><span class="sxs-lookup"><span data-stu-id="def22-182">See also</span></span>

* [<span data-ttu-id="def22-183">アクセシビリティの問題のための Web ページを自動的にテストする</span><span class="sxs-lookup"><span data-stu-id="def22-183">Automatically test a webpage for accessibility issues</span></span>](../accessibility/test-issues-tool.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="def22-184">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="def22-184">Getting in touch with the Microsoft Edge DevTools team</span></span>

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]

<!-- links -->
[DevtoolsOpenIndex]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"
<!-- external links -->
[A11ytestingPagewitherrors]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティ テストのデモ ページ |Microsoft Docs"
[DequeAxe]: https://www.deque.com/axe "axe Tools の概要 |Deque"
[MDNCompat]: https://github.com/mdn/browser-compat-data "MDN ブラウザー互換性データ |GitHub"
[webhintIo]: https://webhint.io "webhint.io"

> [!NOTE]
> <span data-ttu-id="def22-190">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="def22-190">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>
> <span data-ttu-id="def22-191">元のページはここで [見](https://developers.google.com/web/tools/chrome-devtools/issues/index) つかり [、Sam Dutton][SamDutton] \(Developer Advocate\) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="def22-191">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/issues/index) and is authored by [Sam Dutton][SamDutton] \(Developer Advocate\).</span></span>
<span data-ttu-id="def22-192">[ ![ クリエイティブ コモンズ ライセンス この][CCby4Image]][CCA4IL]作品は、クリエイティブ コモンズ アトリビューション[4.0 インターナショナル ライセンスの下でライセンスされています][CCA4IL]。</span><span class="sxs-lookup"><span data-stu-id="def22-192">[![Creative Commons License][CCby4Image]][CCA4IL] This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>

[CCA4IL]: https://creativecommons.org/licenses/by/4.0
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques
[SamDutton]: https://developers.google.com/web/resources/contributors#sam-dutton
