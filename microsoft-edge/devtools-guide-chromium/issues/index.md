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

# <a name="find-and-fix-problems-using-the-issues-tool"></a>問題ツールを使用して問題を見つけて修正する

DevTools Microsoft Edge、Issues ツール**** は現在の Web ページを自動的に分析し、種類別にグループ化された問題を報告し、問題の説明と解決に役立つドキュメントを提供します。

Issues **ツールは** 、次のカテゴリでフィードバックを提供します。
*  アクセシビリティ。
*  ブラウザー間の互換性。
*  パフォーマンス。
*  プログレッシブ Web アプリ。
*  セキュリティ。
*  その他。

問題ツールの**フィードバック**は、Chromium プラットフォーム、Deque axe、MDN ブラウザー互換性データ、webhint など、いくつかのソースによって提供されます。  [問題] ツールを設定するフィードバックのこれらのソースの詳細 **については、次** の場所に移動します。
*  [axe Tools の概要][DequeAxe]
*  [browser-compat-data repo][MDNCompat]
*  [Webhint][webhintIo]


## <a name="open-the-issues-tool"></a>[問題] ツールを開く

次の手順を実行して、デモ ページ **を使用して Issues** ツールを開きます。


1.  修正する問題を含む Web ページに移動します。  たとえば、新しいタブ [またはウィンドウでアクセシビリティ テストの][A11ytestingPagewitherrors] デモ ページを開きます。

1.  DevTools を開きます。  数秒後、DevTools の右上隅に **Issues** カウンター ![ ](../media/issues-counter-icon.msft.png) \( Issues counter \) が表示されます。  [問題] カウンターの問題の数が異なる場合があります。

1.  [問題 **] カウンターを選択します**。  [ **問題] ツールが** 開き、さまざまなカテゴリにグループ化された問題が表示されます。

    :::image type="complex" source="../media/issues-tool-categories.msft.png" alt-text="デモ ページの [問題] ツールの問題のカテゴリ" lightbox="../media/issues-tool-categories.msft.png":::
       デモ ページの [問題] ツールの問題のカテゴリ
    :::image-end:::

### <a name="other-ways-to-open-the-issues-tool"></a>問題ツールを開くその他の方法

問題ツールを開く方法は **次のとおりです** 。
*  メイン パネル**またはドロワーで**[その他のツール ] ( ) メニューを選択し、[ **+** 問題]**を選択します**。 ****
*  **[DevTools のカスタマイズと制御] [** その  >  **他のツールの問題**  >  **] を選択します**。
*  要素ツールの DOM ツリー **で** 、波線付き下線付き要素名を `Shift` 選択してクリックします。  または、波線付き下線付き要素のコンテキスト メニューを開き、[問題の表示 **] を選択します**。

### <a name="issues-are-automatically-ordered-by-severity"></a>問題は重大度によって自動的に順序付けされます。

問題の各カテゴリ内で、最初にエラーが一覧表示され、次に警告が表示され、次にヒントが表示されます。

:::image type="complex" source="../media/issues-ordered-by-severity.msft.png" alt-text="[問題] ツールには、重大度別に並べ替えたパフォーマンスの問題が表示されます。" lightbox="../media/issues-ordered-by-severity.msft.png":::
   [ **問題] ツールには** 、重大度別に並べ替えたパフォーマンスの問題が表示されます。
:::image-end:::

### <a name="include-third-party-issues"></a>サードパーティの問題を含める

サード パーティのサイトによって発生する問題を含めるには、[問題] ツールの**** 上部にある [サードパーティの問題を含める] チェック ボックス**をオン**にします。


## <a name="expand-entries-in-the-issues-tool"></a>[問題] ツールのエントリを展開する

Issues **ツールには** 、各問題に適用する追加のドキュメントと推奨される修正プログラムが表示されます。  この追加情報を取得するために問題を展開するには、次のように問題を選択します。

1.  新しい [ウィンドウまたはタブで][A11ytestingPagewitherrors] デモ ページを開き、DevTools を開きます。

1.  [問題 **] カウンター** \( **Issues counter** \) を選択して ![ 、[問題] ツールを ](../media/issues-counter-icon.msft.png) 開きます。

1.  問題を選択して、問題を展開します。

    :::image type="complex" source="../media/issues-tool-initial-view-accessibility-page.msft.png" alt-text="問題の修正方法に関する追加情報を表示する Issues ツール" lightbox="../media/issues-tool-initial-view-accessibility-page.msft.png":::
       問題 **の修正** 方法に関する追加情報を表示する Issues ツール
    :::image-end:::

表示される各問題には、次のコンポーネントがあります。
*   問題を説明する見出し。
*   より多くのコンテキストと提案されたソリューションを提供する説明。
*   要素 **、ソース**、ネットワーク ツールなどの DevTools のリソースにリンク**** する、**** 影響を受けるリソース**セクション**。
*   その他のドキュメントへのリンク。


## <a name="view-issues-in-context-of-an-associated-tool"></a>関連付けられたツールのコンテキストで問題を表示する

問題ツールの問題**には**、要素、ソース、ネットワーク ツールなど、さまざまなツールを開く**** 1**** つ以上のリンクが**含まれる場合**があります。 これらのツールのいずれかを開き、追加のトラブルシューティング手順を実行できます。 [問題] ツールからリンク ツール **を開く場合** は、次の手順を実行します。

1.  前のセクションで説明したように、デモ ページを開き、[問題] ツールで問題 **を展開** します。

1.  [**影響を受けるリソース**  >  **] で、** ツール名を選択します。  影響を受けるリソースが選択したツールに表示されます。

    :::image type="complex" source="../media/issues-tool-affected-resource-opens-elements-tool.msft.png" alt-text="問題ツール内から影響を受けるリソースを開くツールを選択する" lightbox="../media/issues-tool-affected-resource-opens-elements-tool.msft.png":::
       問題ツール内から影響を受けるリソースを開くツールを選択する
    :::image-end:::

    展開された問題には、 **影響を受** けるリソースをネットワーク ツールに表示するネットワーク リンクがある **場合** があります。

    :::image type="complex" source="../media/issues-tab-view-issue.msft.png" alt-text="ネットワーク リソース リンクを選択すると、[ネットワーク] ツールが開きます。" lightbox="../media/issues-tab-view-issue.msft.png":::
    ネットワーク **リソース リンク** を選択すると、[ネットワーク] **ツールが** 開きます。
    :::image-end:::


## <a name="open-issues-from-the-dom-tree"></a>DOM ツリーから問題を開く

要素に関連する問題がある場合、要素ツールの DOM**** ツリーには、要素名の下線が波線で表示されます。  要素のコンテキスト メニュー (右クリック) を開き、[問題の**** 表示] を選択するか、下線が波状の要素を選択して `Shift` 左クリックします。

DOM ツリーに波線が付く要素の問題を表示するには、次の手順を実行します。

1.  デモ ページなどのページを新しいタブ [または][A11ytestingPagewitherrors]ウィンドウで開きます。

1.  DevTools を開き、[要素] タブ **を選択** します。

1.  DOM ツリーで、 を展開します `<body>`  >  `<header>`  >  `<form>` 。  要素に波 `<input>` の下線が付い注意してください。

    :::image type="complex" source="../media/issues-wavy-underlines-dom-tree.msft.png" alt-text="要素ツールの DOM ツリー内のウェーブ下線付き問題" lightbox="../media/issues-wavy-underlines-dom-tree.msft.png":::
       要素ツールの**DOM**ツリー内のウェーブ下線**付き問題**
    :::image-end:::

1.  要素にカーソルを合 `<input>` わせる。  ヒントには、問題に関する情報が表示されます。

1.  下線が波打つ要素のコンテキスト メニューを開き、[問題の表示] **を選択します**。  [ **問題] ツール** が開き、その要素に関連付けられている問題が表示されます。

    :::image type="complex" source="../media/issues-opened-from-dom-tree-wavy-underline.msft.png" alt-text="DOM ツリー内の波線付き下線付き要素の問題の詳細" lightbox="../media/issues-opened-from-dom-tree-wavy-underline.msft.png":::
       DOM ツリー内の波線付き下線付き要素の問題の **詳細**
    :::image-end:::


## <a name="see-also"></a>関連項目

* [アクセシビリティの問題のための Web ページを自動的にテストする](../accessibility/test-issues-tool.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]

<!-- links -->
[DevtoolsOpenIndex]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"
<!-- external links -->
[A11ytestingPagewitherrors]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティ テストのデモ ページ |Microsoft Docs"
[DequeAxe]: https://www.deque.com/axe "axe Tools の概要 |Deque"
[MDNCompat]: https://github.com/mdn/browser-compat-data "MDN ブラウザー互換性データ |GitHub"
[webhintIo]: https://webhint.io "webhint.io"

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。
> 元のページはここで [見](https://developers.google.com/web/tools/chrome-devtools/issues/index) つかり [、Sam Dutton][SamDutton] \(Developer Advocate\) によって作成されています。
[ ![ クリエイティブ コモンズ ライセンス この][CCby4Image]][CCA4IL]作品は、クリエイティブ コモンズ アトリビューション[4.0 インターナショナル ライセンスの下でライセンスされています][CCA4IL]。

[CCA4IL]: https://creativecommons.org/licenses/by/4.0
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques
[SamDutton]: https://developers.google.com/web/resources/contributors#sam-dutton
