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
# <a name="analyze-keyboard-support-on-forms-using-the-devtools"></a>DevTools を使用してフォームのキーボードサポートを分析する

この記事では、[ **検査** ] ツールと [ **イベント** リスナー] タブを使用して、要素を使用するボタンがあるデモ ページでのキーボード サポートの不足を分析 `div` します。

**[Donate] フォーム**では、金額ボタンと **[Donate]** ボタンはキーボードでは機能しません。  寄付フォームをデバッグするには、フォーカススタイルの欠如が、問題ツールなどの自動テスト ツールの問題としてフラグ付けされていない理由 **を理解する必要** があります。  この例では、ボタンは、フォーム上のコントロールとしてこれらのツールでは認識されない要素を使用 `div` して実装されます。

[検査] ツールと [イベント リスナー] タブを使用して、デモ ページでのキーボード サポートの不足を分析するには、次の操作を行います。

<!-- 1. Inspect tool: Accessibility section: keyboard-focusable row -->

1.  ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。
    
1.  DevTools **の左上隅** にある [検査] アイコン \( Inspect icon \) ボタンを選択して、ボタンが強調表示 ![ ](../media/inspect-icon.msft.png) (青) にします。

1.  **50、100、** および**200**の寄付ボタンにカーソルを合わせる。 ****  [検査] ツールは、オーバーレイとして Web ページに表示されます。  [ **検査] オーバーレイ** のキーボードフォーカス可能な行は、斜線が付いた灰色の円で示すように、寄付金額ボタンのいずれもキーボードにアクセスできない状態を示しています。  ボタンには名前が付かないので、要素なので、支援テクノロジではボタンに `generic` `div` アクセスできないという役割があります。

    :::image type="complex" source="../media/a11y-testing-donation-button-info.msft.png" alt-text="フォームのボタンを調すと、キーボードにアクセスできないという結果が表示されます。" lightbox="../media/a11y-testing-donation-button-info.msft.png":::
        フォームのボタンを調すと、キーボードにアクセスできないという結果が表示されます。
    :::image-end:::
    
1.  [検査]**ツール**がアクティブな場合は、Web**** ページで、[Donate] ボタンの上にある [その他の入力]**テキスト ボックスを選択**します。  [ **要素]** ツールが開き、Web ページの DOM ツリーが表示されます。  要素 `<input id="freedonation" class="smallinput">` が選択されています。

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

    Other テキスト ボックスの and 要素の使用は有効です。つまり、Other ラベルは入力テキスト ボックスに正 `label` `input` しくリンクされています。 **** ****  テキスト `input` ボックスはキーボードでアクセスすることもできます。  フォームの残りのマークアップは要素で、スタイルは簡単ですが、意味 `div` 的な意味はありません。

    <!-- 2. Elements tool: Event Listeners tab -->

    フォームの機能は JavaScript で作成され、次のように [イベント リスナー] タブを **確認してこれを** テストできます。

1.  DOM ツリーで要素がまだ選択されている場合は、[スタイル] タブの右側にある [イベント リスナー] タブを選択し、イベント リスナー `<input id="freedonation" class="smallinput">` を******** `click` 展開します。

    :::image type="complex" source="../media/a11y-testing-event-handlers-on-button.msft.png" alt-text="フォームが動作する JavaScript の場所を示すイベント リスナー ツール" lightbox="../media/a11y-testing-event-handlers-on-button.msft.png":::
        フォームが動作する JavaScript の場所を示すイベント リスナー ツール
    :::image-end:::

1.  リンクを選択 `buttons.js:18` します。  ソース **ツールが開** き、適用された JavaScript が表示されます。

    :::image type="complex" source="../media/a11y-testing-form-handling-javascript.msft.png" alt-text="[ソース] ツールに表示される、寄付フォームの機能を担当する JavaScript" lightbox="../media/a11y-testing-form-handling-javascript.msft.png":::
        [ソース] ツールに表示される、寄付フォームの機能を担当する JavaScript
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

イベントを `click` 使用してボタンを読み取る方法は、マウス ポインターとキーボード操作の両方でイベントが発生する場合に便利 `click` です。  ただし、要素はキーボードでアクセスできないので、この Donate ボタンは要素 ( ) として実装されます。一部のキーボードで使用できる特別なボタンなど、マウスやイベントの別のソースを使用しない限り、この `div` **** `div` `<div class="submitbutton">Donate</div>` JavaScript 機能は実行されません。 `click`

これは、要素がネイティブに提供する機能を作成するために JavaScript が追加された `button` 従来の例です。  要素を使用してボタンの機能をシミュレートすると、アクセスできない `div` エクスペリエンスが生まれます。


## <a name="see-also"></a>関連項目

*  [DevTools を使用したアクセシビリティ テストの概要](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
