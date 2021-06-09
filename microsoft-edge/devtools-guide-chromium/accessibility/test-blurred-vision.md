---
description: Web ページがぼやけたビジョンで使用できると確認するには、[レンダリング] ツールで [エミュレートビジョンの欠陥] ドロップダウン リストを使用します。
title: ページがぼやけたビジョンで使用できると確認する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 2fc1a1cf7746591573fce07946c7fb11abf42705
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597531"
---
# <a name="verify-that-the-page-is-usable-with-blurred-vision"></a><span data-ttu-id="37f43-104">ページがぼやけたビジョンで使用できると確認する</span><span class="sxs-lookup"><span data-stu-id="37f43-104">Verify that the page is usable with blurred vision</span></span>

<!-- Rendering tool: Emulate vision deficiencies: Blurred vision -->

<span data-ttu-id="37f43-105">ぼやけたビジョンをシミュレートするには、[ **レンダリング] ツールの [** ビジョンの不備をエミュレート **する] メニューを使用** します。</span><span class="sxs-lookup"><span data-stu-id="37f43-105">To simulate blurred vision, in the **Rendering** tool, use the **Emulate vision deficiencies** menu.</span></span>  <span data-ttu-id="37f43-106">デモ Web ページでこの機能を使用すると、上部メニューのテキストのドロップ シャドウによって、メニュー項目の読み取りが難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="37f43-106">When you use this feature with the demo webpage, you can see that the drop shadow on the text in the upper menu makes it hard to read the menu items.</span></span>

<span data-ttu-id="37f43-107">ぼやけたビジョンで Web ページが使用できるかどうかを確認するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="37f43-107">To check whether a webpage is usable with blurred vision:</span></span>

1.  <span data-ttu-id="37f43-108">ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="37f43-108">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="37f43-109">**[Esc] を**選択して、DevTools の下部にあるドロワーを開きます。</span><span class="sxs-lookup"><span data-stu-id="37f43-109">Select **Esc** to open the Drawer at the bottom of DevTools.</span></span>  <span data-ttu-id="37f43-110">ドロワー **+** の上部にあるアイコンを選択してツールの一覧を表示し、[レンダリング] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="37f43-110">Select the **+** icon at the top of the Drawer to display the list of tools, and then select **Rendering**.</span></span>  

1.  <span data-ttu-id="37f43-111">[ビジョン **の不備をエミュレートする] ドロップダウン** リストで、[ぼ **やけたビジョン] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="37f43-111">In the **Emulate vision deficiencies** dropdown list, select **Blurred vision**.</span></span>

    :::image type="complex" source="../media/a11y-testing-simulating-blur.msft.png" alt-text="ぼやけたページをシミュレートする" lightbox="../media/a11y-testing-simulating-blur.msft.png":::
        <span data-ttu-id="37f43-113">ぼやけたページをシミュレートする</span><span class="sxs-lookup"><span data-stu-id="37f43-113">Simulating a blurred page</span></span>
    :::image-end:::

    <span data-ttu-id="37f43-114">CSS プロパティ `text-shadow` を使用すると、メニュー項目のテキストが上部メニューで読みにくくなっている点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="37f43-114">Notice that the `text-shadow` CSS property makes the text of the menu items difficult to read on the upper menu.</span></span> <span data-ttu-id="37f43-115">たとえば、「ホーム **」、「Pet**を採用 **する」、** その他のメニュー項目を確認します。</span><span class="sxs-lookup"><span data-stu-id="37f43-115">For example, review the **Home**, **Adopt a Pet**, and other menu items.</span></span>
    
1.  <span data-ttu-id="37f43-116">レンダリング ツール**の [エミュレート**ビジョンの欠陥]\*\*\*\*\*\*で\*\*、[エミュレーションなし] を選択して、ぼやけたビジョン シミュレーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="37f43-116">In the **Rendering** tool, in **Emulate vision deficiencies**, select **No emulation** to remove the blurred vision simulation.</span></span>


## <a name="see-also"></a><span data-ttu-id="37f43-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="37f43-117">See also</span></span>

*  [<span data-ttu-id="37f43-118">視覚欠陥をエミュレートする</span><span class="sxs-lookup"><span data-stu-id="37f43-118">Emulate vision deficiencies</span></span>](emulate-vision-deficiencies.md)
*  [<span data-ttu-id="37f43-119">DevTools を使用したアクセシビリティ テストの概要</span><span class="sxs-lookup"><span data-stu-id="37f43-119">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="37f43-120">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="37f43-120">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
