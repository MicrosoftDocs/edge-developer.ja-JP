---
description: '[レンダリング] ツールの [CSS メディアのエミュレート] 機能を使用して、UI アニメーションがオフ (縮小モーション) で Web ページが使用可能になっていることを確認します。'
title: ページが UI アニメーションをオフにした状態で使用できる状態になっていることを確認する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: ec30925b706b4b1c6dfaaa6ce66a38fab8759ac2
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597495"
---
# <a name="verify-that-the-page-is-usable-with-ui-animation-turned-off"></a><span data-ttu-id="91b11-104">ページが UI アニメーションをオフにした状態で使用できる状態になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="91b11-104">Verify that the page is usable with UI animation turned off</span></span>

<span data-ttu-id="91b11-105">Web ページは、オペレーティング システムでアニメーションをオフにしたユーザーにアニメーションを表示しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="91b11-105">A webpage should not show animations to a user who turned off animations in the operating system.</span></span>  <span data-ttu-id="91b11-106">アニメーションは、製品の使いやすさに役立ちますが、気晴らし、混乱、または吐き気を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="91b11-106">Animations can help the usability of a product, but they can also cause distraction, confusion, or nausea.</span></span>

<span data-ttu-id="91b11-107">Web ページが UI アニメーションをオフ (縮小モーション) で使用できる\*\*\*\* 状態にすることを確認するには、レンダリング ツールで **、[CSS**メディアのエミュレート] 機能を使用して、低モーションを優先するドロップダウン リストを使用します。</span><span class="sxs-lookup"><span data-stu-id="91b11-107">To check that a webpage is usable with UI animation turned off (reduced motion), in the **Rendering** tool, use the **Emulate CSS media feature prefers-reduced-motion** dropdown list.</span></span>

<span data-ttu-id="91b11-108">アクセシビリティ テストのデモ Web ページで、オペレーティング システムでアニメーションをオフにしたり、DevTools を使用してその設定をエミュレートしたりすると、サイドバー ナビゲーション メニューのリンクを選択しても、Web ページはスムーズなスクロールを使用しない。</span><span class="sxs-lookup"><span data-stu-id="91b11-108">In the accessibility-testing demo webpage, when you turn off animations in the operating system, or emulate that settings by using DevTools, the webpage doesn't use smooth scrolling when you select the links of the sidebar navigation menu.</span></span>  <span data-ttu-id="91b11-109">これは、メディア クエリで CSS の滑らかなスクロール設定をラップし、レンダリング ツールを使用\*\*\*\* して縮小されたアニメーションのオペレーティング システム設定をエミュレートすることによって実現されます。</span><span class="sxs-lookup"><span data-stu-id="91b11-109">This is achieved by wrapping the smooth-scrolling setting in CSS in a media query, and then using the **Rendering** tool to emulate the operating system setting for reduced animation.</span></span>

<span data-ttu-id="91b11-110">アニメーションをオフにした状態でページが使用できるかどうかを確認するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="91b11-110">To check whether the page is usable with animations turned off:</span></span>

1.  <span data-ttu-id="91b11-111">ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="91b11-111">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="91b11-112">DevTools の上部で [ソース\*\*\*\*] ツールを選択し、左側\*\*\*\* の [ナビゲーション] ウィンドウで [ `styles.css` .</span><span class="sxs-lookup"><span data-stu-id="91b11-112">At the top of DevTools, select the **Sources** tool, and then in the **Navigation** pane on the left, select `styles.css`.</span></span>  <span data-ttu-id="91b11-113">CSS ファイルが [エディター] ウィンドウ **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="91b11-113">The CSS file appears in the **Editor** pane.</span></span>

1.  <span data-ttu-id="91b11-114">macOS**で Ctrl + F** Windows/Linux または Command + **F**を選択し、 と入力します `@media` 。</span><span class="sxs-lookup"><span data-stu-id="91b11-114">Select **Ctrl+F** on Windows/Linux or **Command+F** on macOS, and then enter `@media`.</span></span>  <span data-ttu-id="91b11-115">次の CSS メディア クエリが表示され、Web ページで使用されます。</span><span class="sxs-lookup"><span data-stu-id="91b11-115">The following CSS media query is displayed, which confirms that it is used on the webpage.</span></span>

    ```css
    @media (prefers-reduced-motion: no-preference) {
      html {
        scroll-behavior: smooth;
      }
    }
    ```

    <span data-ttu-id="91b11-116">次に、次のように、オペレーティング システム設定をエミュレートしてアニメーションを削減します。</span><span class="sxs-lookup"><span data-stu-id="91b11-116">Next, emulate the operating system setting to reduce animation, as follows.</span></span>

1.  <span data-ttu-id="91b11-117">**[Esc] を**選択して、DevTools の下部にあるドロワーを開きます。</span><span class="sxs-lookup"><span data-stu-id="91b11-117">Select **Esc** to open the Drawer at the bottom of DevTools.</span></span>  <span data-ttu-id="91b11-118">ドロワー **の上部にある** [その他のツール ( )] ボタンを選択してツールの一覧を表示し、[レンダリング **+** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="91b11-118">Select the **More tools** (**+**) button at the top of the Drawer to see the list of tools, and then select **Rendering**.</span></span>  

1.  <span data-ttu-id="91b11-119">[CSS メディア **のエミュレート] 機能で、[** 縮小モーションを優先する] ドロップダウン リストで、[優先する縮小モーション: 縮小] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="91b11-119">In the **Emulate CSS media feature prefers-reduced-motion** dropdown list, select **prefers-reduced-motion: reduced**.</span></span>

    :::image type="complex" source="../media/a11y-testing-simulating-reduced-motion.msft.png" alt-text="縮小されたモーションと、ユーザーが必要なときにのみスムーズなスクロールが実行される CSS をシミュレートする" lightbox="../media/a11y-testing-simulating-reduced-motion.msft.png":::
        <span data-ttu-id="91b11-121">縮小されたモーションと、ユーザーが必要なときにのみスムーズなスクロールが実行される CSS をシミュレートする</span><span class="sxs-lookup"><span data-stu-id="91b11-121">Simulating reduced motion and the CSS that makes sure that smooth scrolling only happens when the user wants it</span></span>
    :::image-end:::

1.  <span data-ttu-id="91b11-122">Web ページで、馬やアルパカスなどの青**いメニュー\*\*\*\*項目を選択します**。</span><span class="sxs-lookup"><span data-stu-id="91b11-122">In the webpage, select the blue menu items, such as **Horses** or **Alpacas**.</span></span>  <span data-ttu-id="91b11-123">これで、スムーズスクロールアニメーションを使用するのではなく、選択したセクションまで Web ページが即座にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="91b11-123">Now the webpage instantly scrolls to the selected section, rather than using the smooth-scrolling animation.</span></span>

1.  <span data-ttu-id="91b11-124">[レンダリング]**ツールの**[CSS メディア機能の**エミュレート優先**縮小]\*\*\*\* の下で、[エミュレーションなし] を選択してこの設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="91b11-124">In the **Rendering** tool, below **Emulate CSS media feature prefers-reduced-motion**, select **No emulation** to remove this setting.</span></span>
   
<span data-ttu-id="91b11-125">デモ Web ページでは、上記のメディア クエリとエミュレーション設定を使用しても、次のアニメーションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="91b11-125">Notice that the demo webpage still runs the following animations, even with the above media query and emulation settings.</span></span> <span data-ttu-id="91b11-126">Web 製品を構築する場合は、同様のすべてのアニメーションを修正してください。</span><span class="sxs-lookup"><span data-stu-id="91b11-126">When building your web product, ensure you fix all similar animations.</span></span>  
*  <span data-ttu-id="91b11-127">青いメニュー項目の上にマウス ポインターを置くと、その項目のアニメーションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="91b11-127">Animation of the blue menu items when you hover over them.</span></span>
*  <span data-ttu-id="91b11-128">その上にマウス ポインターを置くと、 **その他** のリンク上の円のアニメーションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="91b11-128">Animation of the circles on the **More** links when you hover over them.</span></span>



## <a name="see-also"></a><span data-ttu-id="91b11-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="91b11-129">See also</span></span>

*  [<span data-ttu-id="91b11-130">モーション シミュレーションの削減</span><span class="sxs-lookup"><span data-stu-id="91b11-130">Reduced motion simulation</span></span>](reduced-motion-simulation.md)
*  [<span data-ttu-id="91b11-131">DevTools を使用したアクセシビリティ テストの概要</span><span class="sxs-lookup"><span data-stu-id="91b11-131">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="91b11-132">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="91b11-132">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
