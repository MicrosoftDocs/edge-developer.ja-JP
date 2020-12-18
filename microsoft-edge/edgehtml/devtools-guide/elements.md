---
description: '[要素] パネルを使用して、ページの HTML、CSS、DOM、およびアクセシビリティを検査します。'
title: DevTools - 要素
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, 要素, html, css, dom ブレークポイント, イベント, アクセシビリティ
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 14052bc40b9f94e628f0b575ede6c1ca8ccf179a
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234461"
---
# <span data-ttu-id="91627-104">要素</span><span class="sxs-lookup"><span data-stu-id="91627-104">Elements</span></span>

<span data-ttu-id="91627-105">要素 **パネルは** 、次の操作を行うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="91627-105">The **Elements** panel helps you to:</span></span>

* <span data-ttu-id="91627-106">[現在のページの HTML ツリー内の要素を](#html-tree-view) 識別および編集する</span><span class="sxs-lookup"><span data-stu-id="91627-106">[Identify and edit elements in the HTML tree](#html-tree-view) of the current page</span></span>
* <span data-ttu-id="91627-107">[ページ上の CSS (擬似](./elements/styles.md) 状態と擬似要素を含む) を検査および変更する</span><span class="sxs-lookup"><span data-stu-id="91627-107">[Inspect and modify CSS](./elements/styles.md) on the page, including pseudo-states and pseudo-elements</span></span>
* <span data-ttu-id="91627-108">[ページ上で発生する CSS レイアウトとスタイルカスケード](./elements/computed.md) について理解する</span><span class="sxs-lookup"><span data-stu-id="91627-108">[Understand the CSS layout and style cascade](./elements/computed.md) happening on the page</span></span>
* <span data-ttu-id="91627-109">[悪意のあるイベント ハンドラーを追跡して](./elements/events.md) デバッグできる</span><span class="sxs-lookup"><span data-stu-id="91627-109">[Track down rogue event handlers](./elements/events.md) so you can debug them</span></span>
* <span data-ttu-id="91627-110">[予期しない視覚的な変更が原因のコードに](./elements/dom-breakpoints.md) ジャンプするためにデバッグブレークポイントを設定する</span><span class="sxs-lookup"><span data-stu-id="91627-110">[Set debugging breakpoints for unexpected visual changes](./elements/dom-breakpoints.md) to jump into the code causing them</span></span>
* <span data-ttu-id="91627-111">[ページで使用されるフォントと、](./elements/fonts.md) そのフォントの読み込み場所に関する詳細情報を取得する</span><span class="sxs-lookup"><span data-stu-id="91627-111">[Get detailed information about the fonts used on the page](./elements/fonts.md) and where they're loading from</span></span>
* <span data-ttu-id="91627-112">[スクリーン リーダーの視点から](./elements/accessibility.md) ページを表示し、アクセシビリティを確認してテストする</span><span class="sxs-lookup"><span data-stu-id="91627-112">[View your page from a screen reader's point of view](./elements/accessibility.md) to verify and test accessibility</span></span> 
* <span data-ttu-id="91627-113">[ページの UI をデバッグする場合に加](./elements/changes.md) える CSS の変更の実行中の違いを確認する</span><span class="sxs-lookup"><span data-stu-id="91627-113">[Review a running diff of the CSS changes](./elements/changes.md) you make as you debug the UI of your page</span></span>

## <span data-ttu-id="91627-114">HTML ツリー ビュー</span><span class="sxs-lookup"><span data-stu-id="91627-114">HTML tree view</span></span>

![Microsoft Edge DevTools 要素パネル](./media/elements.png)

1. <span data-ttu-id="91627-116">Select**要素**( ) ツールを使用して、ページ内で要素をクリックして HTML ツリー ビュー `Ctrl+B` で要素を見つける。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="91627-116">Use the **Select element** (`Ctrl+B`) tool to locate an element in the **HTML tree view** by clicking on it in the page.</span></span>

2. <span data-ttu-id="91627-117">要素の **強調表示** ( ) ツールを使用して、HTML ツリー ビューで要素をポイントして、ページ `Ctrl+Shift+L` **上の要素を検索します**。</span><span class="sxs-lookup"><span data-stu-id="91627-117">Use the **Element highlighting** (`Ctrl+Shift+L`) tool to locate an element on the page by hovering over it in the **HTML tree view**.</span></span>

3. <span data-ttu-id="91627-118">色の **選択 ()** ツールを開き、現在のページで使用されている色 `Ctrl+K` の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="91627-118">Open the **Color picker** (`Ctrl+K`) tool to see a list of the colors in use on the current page.</span></span> <span data-ttu-id="91627-119">一覧の色をクリックすると、詳細 (色相、彩度、明度、アルファ) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="91627-119">Clicking on a color on the list will provide further details (Hue, Saturation, Lightness, Alpha).</span></span> <span data-ttu-id="91627-120">[*スタイル*] ウィンドウで色の値の横にある色付き正方形をクリックすると、色\*\*\*\* の選択も開き、ページ要素の色を編集してすぐに結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="91627-120">The *Color picker* also opens when you click on the colored square next to a color value in the **Styles** pane, allowing you to edit the color of a page element and immediately see the results.</span></span>

4. <span data-ttu-id="91627-121">アクセシビリティ**ツリー** ( ) ボタンをクリックすると、[アクセシビリティ ツリー] ウィンドウが開き `Ctrl+Shift+A` [、Windows](https://support.microsoft.com/help/22798/windows-10-narrator-get-started)ナレーター スクリーンリーダーなどの支援技術に表示されるページの構造が表示されます。 [](./elements/accessibility.md)</span><span class="sxs-lookup"><span data-stu-id="91627-121">The **Accessibility tree** (`Ctrl+Shift+A`) button will open the [Accessibility tree](./elements/accessibility.md) pane showing the structure of your page as it would appear to an assistive technology, such as the [Windows Narrator](https://support.microsoft.com/help/22798/windows-10-narrator-get-started) screenreader.</span></span>

5. <span data-ttu-id="91627-122">また、HTML **ツリー** ビューで要素のタグ名、属性、またはテキスト コンテンツを検索して、要素 `Ctrl+F` を検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="91627-122">You can also **Find** (`Ctrl+F`) an element in the HTML tree view by searching for its tag name, attributes, or text content.</span></span>

### <span data-ttu-id="91627-123">要素の編集</span><span class="sxs-lookup"><span data-stu-id="91627-123">Editing elements</span></span>

<span data-ttu-id="91627-124">HTML ツリー ビュー内で要素を右クリックし、コンテキスト メニューから **[HTML** として編集] を選択すると、要素を編集できます。</span><span class="sxs-lookup"><span data-stu-id="91627-124">You can edit an element by right-clicking on it within the HTML tree view and selecting **Edit as HTML** from the context menu.</span></span> <span data-ttu-id="91627-125">コンテキスト メニューには、削除、切り取り、コピー、貼り付け、CSS 擬似クラス *(:active* *、:focus 、:hover* *、:visited)* の設定、属性の追加を行うオプションも用意されています。 \*\*</span><span class="sxs-lookup"><span data-stu-id="91627-125">The context menu also provides options to delete, cut, copy, paste, set CSS pseudo-classes (*:active*, *:focus*, *:hover*, *:visited*) and add attributes.</span></span> <span data-ttu-id="91627-126">属性や値を編集するもう 1 つの方法は、HTML ツリー ビューからダブルクリックする方法です。</span><span class="sxs-lookup"><span data-stu-id="91627-126">Another way to edit an attribute and/or its value is to double-click it from the HTML tree view.</span></span>

![HTML ツリー ビューのコンテキスト メニュー](./media/elements_html_tree_context.png)

> [!NOTE]
> <span data-ttu-id="91627-128">HTML ツリーを編集しても、基になるソース マークアップには影響を与え得ない。</span><span class="sxs-lookup"><span data-stu-id="91627-128">Editing the HTML tree does not affect the underlying source markup.</span></span> <span data-ttu-id="91627-129">ページを更新すると、変更が元に戻り、ページ ソースによって決定されたレイアウトだけがレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="91627-129">Refreshing the page will revert your changes and render only the layout determined by the page source.</span></span> <span data-ttu-id="91627-130">変更した\*\*\*\* HTML をクリップボードにコピーするには、目的の要素 (またはページ全体が必要な場合はグローバル要素) を右クリックして、コンテキスト メニューを `html` 開きます。</span><span class="sxs-lookup"><span data-stu-id="91627-130">You can **Copy** your modified HTML to the clipboard by right-clicking the desired element (or the global `html` element, if you want the entire page) to open up the context menu.</span></span> <span data-ttu-id="91627-131">(**切り取** り **および貼り付** けオプションも使用できます)。</span><span class="sxs-lookup"><span data-stu-id="91627-131">(**Cut** and **Paste** options are also available).</span></span>

<span data-ttu-id="91627-132">[スタイル [] ウィンドウから](./elements/styles.md) 、CSS 擬似状態と擬似要素を追加/削除/編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="91627-132">From the [Styles](./elements/styles.md) pane you can also add/delete/edit CSS pseudo-states and pseudo-elements.</span></span>

## <span data-ttu-id="91627-133">ツール ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="91627-133">Tool Panes</span></span>

<span data-ttu-id="91627-134">目的のページ要素を選択したら、ツール ウィンドウを使用して、さまざまなスタイルとアクセシビリティ プロパティをさらに調査し、そのイベント リスナーを表示し、DOM のブレークポイントを設定できます。</span><span class="sxs-lookup"><span data-stu-id="91627-134">Once you have selected a page element of interest, you can use the tool panes to further inspect its different styles and accessibility properties, view its event listeners, and set DOM mutation breakpoints.</span></span>

![[要素] パネルの [ツール] ウィンドウ](./media/elements_toolpanes.png)

1. <span data-ttu-id="91627-136">[**スタイル**](./elements/styles.md): 現在適用されているスタイルをスタイルシート別に整理</span><span class="sxs-lookup"><span data-stu-id="91627-136">[**Styles**](./elements/styles.md): Currently applied styles organized by stylesheet</span></span>

2. <span data-ttu-id="91627-137">[**計算:**](./elements/computed.md)現在適用されているスタイルを CSS 属性別に整理</span><span class="sxs-lookup"><span data-stu-id="91627-137">[**Computed**](./elements/computed.md): Currently applied styles organized by CSS attributes</span></span>

3. <span data-ttu-id="91627-138">[**イベント**](./elements/events.md): 現在の要素と先祖要素に登録されているイベント リスナー</span><span class="sxs-lookup"><span data-stu-id="91627-138">[**Events**](./elements/events.md): Event listeners registered on the current element and ancestor elements</span></span>

4. <span data-ttu-id="91627-139">[**DOM ブレークポイント**](./elements/dom-breakpoints.md): DOM のブレークポイント</span><span class="sxs-lookup"><span data-stu-id="91627-139">[**DOM breakpoints**](./elements/dom-breakpoints.md): DOM Mutation Breakpoints</span></span> 

5. <span data-ttu-id="91627-140">[**フォント**](./elements/fonts.md): 選択した要素に現在適用されているフォント</span><span class="sxs-lookup"><span data-stu-id="91627-140">[**Fonts**](./elements/fonts.md): Currently applied fonts for a selected element</span></span>

6. <span data-ttu-id="91627-141">[**アクセシビリティ**](./elements/accessibility.md): アクセシビリティ プロパティ</span><span class="sxs-lookup"><span data-stu-id="91627-141">[**Accessibility**](./elements/accessibility.md):  Accessibility properties</span></span>

7. <span data-ttu-id="91627-142">[**変更**](./elements/changes.md): 診断セッション中に行われた CSS の変更</span><span class="sxs-lookup"><span data-stu-id="91627-142">[**Changes**](./elements/changes.md): CSS changes made during diagnostic session</span></span>  

## <span data-ttu-id="91627-143">ショートカット</span><span class="sxs-lookup"><span data-stu-id="91627-143">Shortcuts</span></span>

| <span data-ttu-id="91627-144">操作</span><span class="sxs-lookup"><span data-stu-id="91627-144">Action</span></span>               | <span data-ttu-id="91627-145">ショートカット</span><span class="sxs-lookup"><span data-stu-id="91627-145">Shortcut</span></span>               |
|:---------------------|:-----------------------|
| <span data-ttu-id="91627-146">要素パネル</span><span class="sxs-lookup"><span data-stu-id="91627-146">Elements panel</span></span>       | `Ctrl` + `1`           |
| <span data-ttu-id="91627-147">要素の強調表示</span><span class="sxs-lookup"><span data-stu-id="91627-147">Element highlighting</span></span> | `Ctrl` + `Shift` + `L` |
| <span data-ttu-id="91627-148">Select 要素</span><span class="sxs-lookup"><span data-stu-id="91627-148">Select element</span></span>       | `Ctrl` + `B`           |
| <span data-ttu-id="91627-149">カラー ピッカー</span><span class="sxs-lookup"><span data-stu-id="91627-149">Color picker</span></span>         | `Ctrl` + `K`           |
| <span data-ttu-id="91627-150">アクセシビリティ ツリー</span><span class="sxs-lookup"><span data-stu-id="91627-150">Accessibility tree</span></span>   | `Ctrl` + `Shift` + `A` |
