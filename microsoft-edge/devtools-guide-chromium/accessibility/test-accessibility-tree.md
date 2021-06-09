---
description: アクセシビリティ ツリーでキーボードとスクリーン リーダーのサポートを確認します。
title: キーボードとスクリーン リーダーのサポートについては、アクセシビリティ ツリーを確認してください。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0ab5e5609485505d1ad5fa6e2fffced9af25edcb
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597543"
---
# <a name="check-the-accessibility-tree-for-keyboard-and-screen-reader-support"></a><span data-ttu-id="c4191-104">キーボードとスクリーン リーダーのサポートについては、アクセシビリティ ツリーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c4191-104">Check the Accessibility Tree for keyboard and screen reader support</span></span>

<!-- Accessibility tab: Accessibility Tree -->

<span data-ttu-id="c4191-105">いくつかの DevTools 機能は、キーボードとスクリーン リーダーのサポートをチェックします。</span><span class="sxs-lookup"><span data-stu-id="c4191-105">Several DevTools features check for keyboard and screen reader support.</span></span>  <span data-ttu-id="c4191-106">検査ツール **を使用** して各ページ要素のアクセシビリティを個別に確認すると、かなり時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c4191-106">Using the **Inspect** tool to check the accessibility of each page element individually can become pretty time-consuming.</span></span>  <span data-ttu-id="c4191-107">Web ページを確認する別の方法は、アクセシビリティ ツリー **を使用する方法です**。</span><span class="sxs-lookup"><span data-stu-id="c4191-107">An alternative way to check a webpage is to use the **Accessibility Tree**.</span></span>  <span data-ttu-id="c4191-108">アクセシビリティ **ツリーは、** ページがスクリーン リーダーなどの支援テクノロジに提供する情報を示します。</span><span class="sxs-lookup"><span data-stu-id="c4191-108">The **Accessibility Tree** indicates what information the page provides to assistive technology such as screen readers.</span></span>

<span data-ttu-id="c4191-109">アクセシビリティ **ツリーは** DOM ツリーのサブセットであり、スクリーン リーダーにページの内容を表示する場合に役立つ DOM ツリーの要素を含む。</span><span class="sxs-lookup"><span data-stu-id="c4191-109">The **Accessibility Tree** is a subset of the DOM tree, which contains elements from the DOM tree that are relevant and useful for displaying the contents of a page in a screen reader.</span></span>  <span data-ttu-id="c4191-110">アクセシビリティ**ツリーは、[** 要素]**ツールの**[\*\*\*\* アクセシビリティ] タブ ([スタイル] タブの近く)**にあります**。</span><span class="sxs-lookup"><span data-stu-id="c4191-110">The **Accessibility Tree** is in the **Accessibility** tab of the **Elements** tool (near the **Styles** tab).</span></span>


<span data-ttu-id="c4191-111">デモ ページでアクセシビリティ ツリーを使用して確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c4191-111">To explore using the Accessibility Tree with the demo page:</span></span>

1.  <span data-ttu-id="c4191-112">アクセシビリティ テスト [のデモ Web ページを新しい][DevToolsA11yErrorsDemopage] タブで開きます。 次に **、[F12] を** 選択して DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="c4191-112">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab.  Then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="c4191-113">DevTools **の左上隅** にある [検査] アイコン \( [検査] アイコン \) ボタンを選択して、ボタンが強調表示 ![ (青) ](../media/inspect-icon.msft.png) にします。</span><span class="sxs-lookup"><span data-stu-id="c4191-113">Select the **Inspect** \(![the Inspect icon](../media/inspect-icon.msft.png)\) button in the top-left corner of DevTools so that the button is highlighted (blue).</span></span>

1.  <span data-ttu-id="c4191-114">レンダリングされた Web ページの [寄付]**セクションで\*\*\*\*、[100] ボタンにカーソルを合**わせる。</span><span class="sxs-lookup"><span data-stu-id="c4191-114">In the rendered webpage, in the **Donation** section, hover over the **100** button.</span></span>  <span data-ttu-id="c4191-115">[ **検査]** ツール オーバーレイが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4191-115">The **Inspect** tool overlay appears.</span></span>

1.  <span data-ttu-id="c4191-116">レンダリングされた Web ページで **、[100] ボタンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="c4191-116">In the rendered webpage, select the **100** button.</span></span>  <span data-ttu-id="c4191-117">DevTools では、[ **要素] ツール** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4191-117">In DevTools, the **Elements** tool is displayed.</span></span>  <span data-ttu-id="c4191-118">DOM ツリーには `div` **、100 ボタンの要素が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="c4191-118">The DOM tree shows the `div` element for the **100** button.</span></span>  <span data-ttu-id="c4191-119">[ **スタイル]** ウィンドウには、要素の CSS 設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4191-119">The **Styles** pane shows the CSS settings for the element.</span></span>

1.  <span data-ttu-id="c4191-120">[スタイル] タブの **右側にある** [アクセシビリティ] **タブを選択** します。 要素 **のアクセシビリティ ツリー** が表示され、展開されます。</span><span class="sxs-lookup"><span data-stu-id="c4191-120">To the right of the **Styles** tab, select the **Accessibility** tab.  The **Accessibility Tree** for the element is displayed, and is expanded.</span></span>

:::image type="complex" source="../media/a11y-testing-accessibility-tree.msft.png" alt-text="アクセシビリティ ツリー ツールの [寄附フォーム] ボタン" lightbox="../media/a11y-testing-accessibility-tree.msft.png":::
    <span data-ttu-id="c4191-122">アクセシビリティ ツリー ツールの [寄附フォーム] ボタン</span><span class="sxs-lookup"><span data-stu-id="c4191-122">Donation form button in the Accessibility Tree tool</span></span>
:::image-end:::

<span data-ttu-id="c4191-123">名前を持たなかったり、(要素など) の役割を持つツリー内の要素は、キーボード ユーザーや支援テクノロジを使用しているユーザーが使用できないので、問題になります。 `generic` `div`</span><span class="sxs-lookup"><span data-stu-id="c4191-123">Any element in the tree that doesn't have a name, or has a role of `generic` (such as the `div` element) is a problem, because that element won't be available to keyboard users, or to users who are using assistive technology.</span></span>


## <a name="see-also"></a><span data-ttu-id="c4191-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4191-124">See also</span></span>

*  [<span data-ttu-id="c4191-125">アクセシビリティ ツリーで要素の位置を表示する</span><span class="sxs-lookup"><span data-stu-id="c4191-125">View the position of an element in the Accessibility Tree</span></span>][DevtoolsAccessibilityAccessibilityTabViewTree]
*  [<span data-ttu-id="c4191-126">DevTools を使用したアクセシビリティ テストの概要</span><span class="sxs-lookup"><span data-stu-id="c4191-126">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="c4191-127">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="c4191-127">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevtoolsAccessibilityAccessibilityTabViewTree]: accessibility-tab.md#view-the-position-of-an-element-in-the-accessibility-tree "アクセシビリティ ツリーの要素の位置を表示する - [アクセシビリティ] タブを使用してアクセシビリティをテスト|Microsoft Docs"
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
