---
description: '[検査] ツールと [イベント リスナー] タブで div 要素を使用するフォームでのキーボードサポートの不足を分析します。'
title: DevTools を使用してフォームのキーボードサポートを分析する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 16ec030ed433fc24d3b2b88bfb423a2479996dfe
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597534"
---
# <a name="analyze-keyboard-support-on-forms-using-the-devtools"></a><span data-ttu-id="b2f20-104">DevTools を使用してフォームのキーボードサポートを分析する</span><span class="sxs-lookup"><span data-stu-id="b2f20-104">Analyze keyboard support on forms using the DevTools</span></span>

<span data-ttu-id="b2f20-105">この記事では、[ **検査** ] ツールと [ **イベント** リスナー] タブを使用して、要素を使用するボタンがあるデモ ページでのキーボード サポートの不足を分析 `div` します。</span><span class="sxs-lookup"><span data-stu-id="b2f20-105">This article uses the **Inspect** tool and **Event Listeners** tab to analyze the lack of keyboard support on a demo page which has buttons that use the `div` element.</span></span>

<span data-ttu-id="b2f20-106">**[Donate] フォーム**では、金額ボタンと **[Donate]** ボタンはキーボードでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="b2f20-106">On the **Donate** form, the amount buttons and **Donate** button doesn't work with a keyboard.</span></span>  <span data-ttu-id="b2f20-107">寄付フォームをデバッグするには、フォーカススタイルの欠如が、問題ツールなどの自動テスト ツールの問題としてフラグ付けされていない理由 **を理解する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="b2f20-107">Debugging the donation form requires understanding why the lack of focus styling isn't flagged as a problem with automatic testing tools like the **Issues** tool.</span></span>  <span data-ttu-id="b2f20-108">この例では、ボタンは、フォーム上のコントロールとしてこれらのツールでは認識されない要素を使用 `div` して実装されます。</span><span class="sxs-lookup"><span data-stu-id="b2f20-108">In this example, the buttons are implemented using `div` elements, which are not recognized by these tools as a control on a form.</span></span>

<span data-ttu-id="b2f20-109">[検査] ツールと [イベント リスナー] タブを使用して、デモ ページでのキーボード サポートの不足を分析するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b2f20-109">To use the Inspect tool and Event Listeners tab to analyze the lack of keyboard support on the demo page:</span></span>

<!-- 1. Inspect tool: Accessibility section: keyboard-focusable row -->

1.  <span data-ttu-id="b2f20-110">ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="b2f20-110">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>
    
1.  <span data-ttu-id="b2f20-111">DevTools **の左上隅** にある [検査] アイコン \( Inspect icon \) ボタンを選択して、ボタンが強調表示 ![ ](../media/inspect-icon.msft.png) (青) にします。</span><span class="sxs-lookup"><span data-stu-id="b2f20-111">Select the **Inspect** \(![Inspect icon](../media/inspect-icon.msft.png)\) button in the top-left corner of DevTools so that the button is highlighted (blue).</span></span>

1.  <span data-ttu-id="b2f20-112">**50、100、** および**200**の寄付ボタンにカーソルを合わせる。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b2f20-112">Hover over the **50**, **100**, and **200** donation buttons.</span></span>  <span data-ttu-id="b2f20-113">[検査] ツールは、オーバーレイとして Web ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2f20-113">The Inspect tool appears on the webpage, as an overlay.</span></span>  <span data-ttu-id="b2f20-114">[ **検査] オーバーレイ** のキーボードフォーカス可能な行は、斜線が付いた灰色の円で示すように、寄付金額ボタンのいずれもキーボードにアクセスできない状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="b2f20-114">The **keyboard-focusable** row of the Inspect overlay shows that none of the donation amount buttons are keyboard-accessible, as indicated by a gray circle with diagonal line.</span></span>  <span data-ttu-id="b2f20-115">ボタンには名前が付かないので、要素なので、支援テクノロジではボタンに `generic` `div` アクセスできないという役割があります。</span><span class="sxs-lookup"><span data-stu-id="b2f20-115">The buttons have no name, and have a role of `generic` because they are `div` elements, which means that the buttons aren't accessible to assistive technology.</span></span>

    :::image type="complex" source="../media/a11y-testing-donation-button-info.msft.png" alt-text="フォームのボタンを調すと、キーボードにアクセスできないという結果が表示されます。" lightbox="../media/a11y-testing-donation-button-info.msft.png":::
        <span data-ttu-id="b2f20-117">フォームのボタンを調すと、キーボードにアクセスできないという結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2f20-117">Inspecting the buttons of the form shows that they aren't keyboard-accessible</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="b2f20-118">[検査]**ツール**がアクティブな場合は、Web\*\*\*\* ページで、[Donate] ボタンの上にある [その他の入力]**テキスト ボックスを選択**します。</span><span class="sxs-lookup"><span data-stu-id="b2f20-118">When the **Inspect** tool is active, on the webpage, select the **Other** input textbox, above the **Donate** button.</span></span>  <span data-ttu-id="b2f20-119">[ **要素]** ツールが開き、Web ページの DOM ツリーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2f20-119">The **Elements** tool opens, showing the DOM tree for the webpage.</span></span>  <span data-ttu-id="b2f20-120">要素 `<input id="freedonation" class="smallinput">` が選択されています。</span><span class="sxs-lookup"><span data-stu-id="b2f20-120">The element `<input id="freedonation" class="smallinput">` is selected.</span></span>

    ```html
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

    <span data-ttu-id="b2f20-121">Other テキスト ボックスの and 要素の使用は有効です。つまり、Other ラベルは入力テキスト ボックスに正 `label` `input` しくリンクされています。 \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b2f20-121">The use of the `label` and `input` elements on the **Other** textbox is valid, which means that the **Other** label is correctly linked with the input textbox.</span></span>  <span data-ttu-id="b2f20-122">テキスト `input` ボックスはキーボードでアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b2f20-122">The `input` textbox is also keyboard-accessible.</span></span>  <span data-ttu-id="b2f20-123">フォームの残りのマークアップは要素で、スタイルは簡単ですが、意味 `div` 的な意味はありません。</span><span class="sxs-lookup"><span data-stu-id="b2f20-123">The rest of the form's markup are `div` elements, which are easy to style, but have no semantic meaning.</span></span>

    <!-- 2. Elements tool: Event Listeners tab -->

    <span data-ttu-id="b2f20-124">フォームの機能は JavaScript で作成され、次のように [イベント リスナー] タブを **確認してこれを** テストできます。</span><span class="sxs-lookup"><span data-stu-id="b2f20-124">The form's functionality is created with JavaScript, and you can test this by checking the **Event Listeners** tab, as follows.</span></span>

1.  <span data-ttu-id="b2f20-125">DOM ツリーで要素がまだ選択されている場合は、[スタイル] タブの右側にある [イベント リスナー] タブを選択し、イベント リスナー `<input id="freedonation" class="smallinput">` を\*\*\*\*\*\*\*\* `click` 展開します。</span><span class="sxs-lookup"><span data-stu-id="b2f20-125">With the element `<input id="freedonation" class="smallinput">` still selected in the DOM tree, select the **Event Listeners** tab to the right of the **Styles** tab, and then expand the `click` event listener.</span></span>

    :::image type="complex" source="../media/a11y-testing-event-handlers-on-button.msft.png" alt-text="フォームが動作する JavaScript の場所を示すイベント リスナー ツール" lightbox="../media/a11y-testing-event-handlers-on-button.msft.png":::
        <span data-ttu-id="b2f20-127">フォームが動作する JavaScript の場所を示すイベント リスナー ツール</span><span class="sxs-lookup"><span data-stu-id="b2f20-127">The Event listeners tool showing you where the JavaScript is that makes the form work</span></span>
    :::image-end:::

1.  <span data-ttu-id="b2f20-128">リンクを選択 `buttons.js:18` します。</span><span class="sxs-lookup"><span data-stu-id="b2f20-128">Select the `buttons.js:18` link.</span></span>  <span data-ttu-id="b2f20-129">ソース **ツールが開** き、適用された JavaScript が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2f20-129">The **Sources** tool opens, showing the applied JavaScript.</span></span>

    :::image type="complex" source="../media/a11y-testing-form-handling-javascript.msft.png" alt-text="[ソース] ツールに表示される、寄付フォームの機能を担当する JavaScript" lightbox="../media/a11y-testing-form-handling-javascript.msft.png":::
        <span data-ttu-id="b2f20-131">[ソース] ツールに表示される、寄付フォームの機能を担当する JavaScript</span><span class="sxs-lookup"><span data-stu-id="b2f20-131">The JavaScript responsible for the donation form's functionality, shown in the Sources tool</span></span>
    :::image-end:::

```javascript
donations.addEventListener('click', e => {
  let t = e.target;
  if (t.classList.contains('donationbutton')) {
    if (currentbutton) { currentbutton.classList.remove('current'); }
    t.classList.add('current');
    currentbutton = t;
    e.preventDefault();
  }
  if (t.classList.contains('submitbutton')) {
    alert('Thanks for your donation!')
  } 
})
```

<span data-ttu-id="b2f20-132">イベントを `click` 使用してボタンを読み取る方法は、マウス ポインターとキーボード操作の両方でイベントが発生する場合に便利 `click` です。</span><span class="sxs-lookup"><span data-stu-id="b2f20-132">Using a `click` event to read the buttons is good practice, because a `click` event fires both on mouse pointer and keyboard interaction.</span></span>  <span data-ttu-id="b2f20-133">ただし、要素はキーボードでアクセスできないので、この Donate ボタンは要素 ( ) として実装されます。一部のキーボードで使用できる特別なボタンなど、マウスやイベントの別のソースを使用しない限り、この `div` \*\*\*\* `div` `<div class="submitbutton">Donate</div>` JavaScript 機能は実行されません。 `click`</span><span class="sxs-lookup"><span data-stu-id="b2f20-133">However, because a `div` element isn't keyboard-accessible, and this **Donate** button is implemented as a `div` element (`<div class="submitbutton">Donate</div>`), this JavaScript functionality never runs unless you use a mouse or another source of a `click` event, such as a special button available on some keyboards.</span></span>

<span data-ttu-id="b2f20-134">これは、要素がネイティブに提供する機能を作成するために JavaScript が追加された `button` 従来の例です。</span><span class="sxs-lookup"><span data-stu-id="b2f20-134">This is a classic example where JavaScript was added to create functionality that `button` elements provide natively.</span></span>  <span data-ttu-id="b2f20-135">要素を使用してボタンの機能をシミュレートすると、アクセスできない `div` エクスペリエンスが生まれます。</span><span class="sxs-lookup"><span data-stu-id="b2f20-135">Simulating the functionality of buttons with `div` elements ended up producing an inaccessible experience.</span></span>


## <a name="see-also"></a><span data-ttu-id="b2f20-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2f20-136">See also</span></span>

*  [<span data-ttu-id="b2f20-137">DevTools を使用したアクセシビリティ テストの概要</span><span class="sxs-lookup"><span data-stu-id="b2f20-137">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="b2f20-138">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="b2f20-138">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
