---
description: レンダリング ツールの \"エミュレート CSS メディア機能 prefers-color-scheme\" ドロップダウン リストを使用して、ダーク テーマとライト テーマ (ダーク モードとライト モード) のコントラストの問題を確認します。
title: 暗いテーマと明るいテーマのコントラストの問題を確認する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 052c75b610ec872329f387e46819867f299a8ca9
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597528"
---
# <a name="check-for-contrast-issues-with-dark-theme-and-light-theme"></a><span data-ttu-id="1a40e-104">暗いテーマと明るいテーマのコントラストの問題を確認する</span><span class="sxs-lookup"><span data-stu-id="1a40e-104">Check for contrast issues with dark theme and light theme</span></span>

<!-- Rendering tool: Emulate CSS media feature prefers-color-scheme -->

<span data-ttu-id="1a40e-105">色のアクセシビリティをテストする場合、コントラストの問題をテストする必要があるさまざまな表示色のテーマがある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1a40e-105">When testing color accessibility, there could be different display color themes that you need to test for contrast issues.</span></span>

<span data-ttu-id="1a40e-106">ほとんどのオペレーティング システムには、ダーク モードとライト モードが用意されています。</span><span class="sxs-lookup"><span data-stu-id="1a40e-106">Most operating systems come with a dark mode and a light mode.</span></span>  <span data-ttu-id="1a40e-107">WEB ページは、CSS メディア クエリを使用して、このオペレーティング システム設定に対応できます。</span><span class="sxs-lookup"><span data-stu-id="1a40e-107">Your webpage can react to this operating system setting, by using a CSS media query.</span></span>  <span data-ttu-id="1a40e-108">これらのテーマをテストし、レンダリング ツールの CSS オプションを使用して、オペレーティング システム設定を変更せずに CSS メディア クエリ `prefers-color-scheme` **をテスト** できます。</span><span class="sxs-lookup"><span data-stu-id="1a40e-108">You can test these themes and test your CSS media query without having to change your operating system setting, by using the `prefers-color-scheme` CSS options in the **Rendering** tool.</span></span>

<span data-ttu-id="1a40e-109">例として、アクセシビリティテストのデモ ページには、明るいテーマと暗いテーマが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1a40e-109">As an example, the accessibility-testing demo page includes a light theme and a dark theme.</span></span>  <span data-ttu-id="1a40e-110">デモ ページは、オペレーティング システムから暗いテーマまたは明るいテーマ設定を継承します。</span><span class="sxs-lookup"><span data-stu-id="1a40e-110">The demo page inherits the dark or light theme setting from the operating system.</span></span>  <span data-ttu-id="1a40e-111">DevTools を使用して、ライト スキームに設定されているオペレーティング システムをシミュレートし、デモ Web ページを更新すると **、Issues** ツールには 2 つの代わりに 6 つの色コントラストの問題が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a40e-111">If we use DevTools to simulate the operating system being set to a light scheme and then refresh the demo webpage, the **Issues** tool shows six color-contrast problems instead of two.</span></span>  <span data-ttu-id="1a40e-112">(別の番号が表示される場合があります)。</span><span class="sxs-lookup"><span data-stu-id="1a40e-112">(You might see different numbers.)</span></span>


<span data-ttu-id="1a40e-113">優先する色テーマのユーザーの選択をエミュレートするには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a40e-113">To emulate a user's selection of preferred color theme:</span></span>

1.  <span data-ttu-id="1a40e-114">ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="1a40e-114">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="1a40e-115">**[Esc] を**選択して、DevTools の下部にあるドロワーを開きます。</span><span class="sxs-lookup"><span data-stu-id="1a40e-115">Select **Esc** to open the Drawer at the bottom of DevTools.</span></span>  <span data-ttu-id="1a40e-116">ドロワー **+** の上部にあるアイコンを選択してツールの一覧を表示し、[レンダリング] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="1a40e-116">Select the **+** icon at the top of the Drawer to see the list of tools, and then select **Rendering**.</span></span>  <span data-ttu-id="1a40e-117">レンダリング ツールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a40e-117">The Rendering tool appears.</span></span>

1.  <span data-ttu-id="1a40e-118">[CSS メディア **のエミュレート] 機能の [** 優先する配色] ドロップダウン リストで、[優先する配色: 明るい **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1a40e-118">In the **Emulate CSS media feature prefers-color-scheme** dropdown list, select **prefers-color-scheme: light**.</span></span>      <span data-ttu-id="1a40e-119">Web ページは、 を使用して再レンダリングされます `light-theme.css` 。</span><span class="sxs-lookup"><span data-stu-id="1a40e-119">The webpage is re-rendered using `light-theme.css`.</span></span>


    :::image type="complex" source="../media/a11y-testing-simulating-light-mode.msft.png" alt-text="レンダリング ツールを使用してライト モードをシミュレートし、ドキュメントの他のテーマをトリガーする" lightbox="../media/a11y-testing-simulating-light-mode.msft.png":::
        <span data-ttu-id="1a40e-121">レンダリング ツールを使用してライト モードをシミュレートし、ドキュメントの他のテーマをトリガーする</span><span class="sxs-lookup"><span data-stu-id="1a40e-121">Using the Rendering tool to simulate a light mode and triggering the other theme of the document</span></span>
    :::image-end:::


1.  <span data-ttu-id="1a40e-122">[問題 **] ツールを選択** し、[アクセシビリティ] **セクションを展開** します。</span><span class="sxs-lookup"><span data-stu-id="1a40e-122">Select the **Issues** tool, and then expand the **Accessibility** section.</span></span>  <span data-ttu-id="1a40e-123">さまざまな要因に応じて、警告が `Insufficient color contrast` 表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a40e-123">Depending on various factors, you might get `Insufficient color contrast` warnings.</span></span> <span data-ttu-id="1a40e-124">「影響を **受けるリソース」には** 、色のコントラストが不十分な 6 つの要素があります。</span><span class="sxs-lookup"><span data-stu-id="1a40e-124">Notice in **AFFECTED RESOURCES** there are 6 elements with insufficient color contrast.</span></span>
    
    :::image type="complex" source="../media/a11y-testing-new-contrast-issues-in-light-mode.msft.png" alt-text="光のテーマが変更されたため、新しいコントラストの問題が検出されました" lightbox="../media/a11y-testing-new-contrast-issues-in-light-mode.msft.png":::
        <span data-ttu-id="1a40e-126">光のテーマが変更されたため、新しいコントラストの問題が検出されました</span><span class="sxs-lookup"><span data-stu-id="1a40e-126">New contrast issues detected because of the change to light theme</span></span>
    :::image-end:::
    
    <span data-ttu-id="1a40e-127">デモ ページでは、ページの **[寄** 附状況] セクションはライト モードでは読み取り不能であり、変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a40e-127">On our demo page, the **Donation status** section of the page is unreadable in light mode, and needs to change.</span></span> 
    
    :::image type="complex" source="../media/a11y-testing-donation-state-light-contrast.msft.png" alt-text="[寄附状況] セクションには、光モードでのコントラストの問題があります。" lightbox="../media/a11y-testing-donation-state-light-contrast.msft.png":::
        <span data-ttu-id="1a40e-129">[ **寄附状況]** セクションには、光モードでのコントラストの問題があります。</span><span class="sxs-lookup"><span data-stu-id="1a40e-129">The **Donation Status** section has contrast issues in light mode</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="1a40e-130">DevTools で[要素\*\*\*\*] ツールを選択し\*\*\*\*、macOS の [Windows/Linux] または [Command+ **F]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="1a40e-130">In DevTools, select the **Elements** tool, and then select **Ctrl+F** on Windows/Linux or **Command+F** on macOS.</span></span>  <span data-ttu-id="1a40e-131">HTML \*\*\*\* DOM ツリー内で検索する [検索] テキスト ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a40e-131">The **Find** textbox appears, to search within the HTML DOM tree.</span></span>
 
1.  <span data-ttu-id="1a40e-132">を `scheme` 入力します。</span><span class="sxs-lookup"><span data-stu-id="1a40e-132">Enter `scheme`.</span></span>  <span data-ttu-id="1a40e-133">次の CSS メディア クエリが見つかり、対応する CSS ファイルを更新できます。</span><span class="sxs-lookup"><span data-stu-id="1a40e-133">The following CSS media queries are found, and the corresponding CSS files can now be updated.</span></span>

    ```html
    <link rel="stylesheet" href="css/light-theme.css" media="(prefers-color-scheme: light), (prefers-color-scheme: no-preference)">
    <link rel="stylesheet" href="css/dark-theme.css" media="(prefers-color-scheme: dark)">
    ```


## <a name="see-also"></a><span data-ttu-id="1a40e-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a40e-134">See also</span></span>

*  [<span data-ttu-id="1a40e-135">暗いまたは明るい配色のシミュレーション</span><span class="sxs-lookup"><span data-stu-id="1a40e-135">Dark or light color scheme simulation</span></span>][DevToolsColorSchemeSimulation]
*  [<span data-ttu-id="1a40e-136">DevTools を使用したアクセシビリティ テストの概要</span><span class="sxs-lookup"><span data-stu-id="1a40e-136">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="1a40e-137">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="1a40e-137">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsColorSchemeSimulation]: ./preferred-color-scheme-simulation.md "暗いまたは明るい配色のシミュレーション |Microsoft Docs"
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
