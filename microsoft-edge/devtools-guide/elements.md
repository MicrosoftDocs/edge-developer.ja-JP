---
description: '[要素] パネルを使用して、ページの HTML、CSS、DOM、アクセシビリティを検査します。'
title: DevTools-要素
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、elements、html、css、dom ブレークポイント、イベント、アクセシビリティ
ms.custom: seodec18
ms.openlocfilehash: 8948ddb3291bd122521e0b0800c0113a576d49e4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570494"
---
# <span data-ttu-id="63ba7-104">要素</span><span class="sxs-lookup"><span data-stu-id="63ba7-104">Elements</span></span>

<span data-ttu-id="63ba7-105">[**要素**] パネルでは、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="63ba7-105">The **Elements** panel helps you to:</span></span>

* <span data-ttu-id="63ba7-106">現在のページの[HTML ツリーの要素を識別および編集](#html-tree-view)する</span><span class="sxs-lookup"><span data-stu-id="63ba7-106">[Identify and edit elements in the HTML tree](#html-tree-view) of the current page</span></span>
* <span data-ttu-id="63ba7-107">擬似状態と擬似要素を含むページの[CSS を検査して変更](./elements/styles.md)する</span><span class="sxs-lookup"><span data-stu-id="63ba7-107">[Inspect and modify CSS](./elements/styles.md) on the page, including pseudo-states and pseudo-elements</span></span>
* <span data-ttu-id="63ba7-108">ページ上での[CSS レイアウトとスタイルのカスケードについて理解する](./elements/computed.md)</span><span class="sxs-lookup"><span data-stu-id="63ba7-108">[Understand the CSS layout and style cascade](./elements/computed.md) happening on the page</span></span>
* <span data-ttu-id="63ba7-109">デバッグできるように、[不正なイベントハンドラーを追跡](./elements/events.md)する</span><span class="sxs-lookup"><span data-stu-id="63ba7-109">[Track down rogue event handlers](./elements/events.md) so you can debug them</span></span>
* <span data-ttu-id="63ba7-110">[予期しない視覚的な変更に対してデバッグのブレークポイントを設定して](./elements/dom-breakpoints.md)、それを引き起こしているコードにジャンプします。</span><span class="sxs-lookup"><span data-stu-id="63ba7-110">[Set debugging breakpoints for unexpected visual changes](./elements/dom-breakpoints.md) to jump into the code causing them</span></span>
* <span data-ttu-id="63ba7-111">[ページで使用され](./elements/fonts.md)ているフォントおよびその読み込み元の場所に関する詳細情報を取得する</span><span class="sxs-lookup"><span data-stu-id="63ba7-111">[Get detailed information about the fonts used on the page](./elements/fonts.md) and where they're loading from</span></span>
* <span data-ttu-id="63ba7-112">[スクリーンリーダーの視点からページを表示](./elements/accessibility.md)して、アクセシビリティを確認およびテストする</span><span class="sxs-lookup"><span data-stu-id="63ba7-112">[View your page from a screen reader's point of view](./elements/accessibility.md) to verify and test accessibility</span></span> 
* <span data-ttu-id="63ba7-113">ページの UI をデバッグするときに加えた[CSS の変更の実行結果を確認](./elements/changes.md)する</span><span class="sxs-lookup"><span data-stu-id="63ba7-113">[Review a running diff of the CSS changes](./elements/changes.md) you make as you debug the UI of your page</span></span>

## <span data-ttu-id="63ba7-114">HTML ツリービュー</span><span class="sxs-lookup"><span data-stu-id="63ba7-114">HTML tree view</span></span>

![Microsoft Edge DevTools 要素パネル](./media/elements.png)

1. <span data-ttu-id="63ba7-116">**Select element** () ツールを使用し `Ctrl+B` て、ページ内の要素をクリックし、 **HTML ツリービュー**で要素を見つけます。</span><span class="sxs-lookup"><span data-stu-id="63ba7-116">Use the **Select element** (`Ctrl+B`) tool to locate an element in the **HTML tree view** by clicking on it in the page.</span></span>

2. <span data-ttu-id="63ba7-117">要素の**強調**表示 ( `Ctrl+Shift+L` ) ツールを使って、 **HTML ツリービュー**の要素の上にマウスポインターを置くと、ページ上の要素を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="63ba7-117">Use the **Element highlighting** (`Ctrl+Shift+L`) tool to locate an element on the page by hovering over it in the **HTML tree view**.</span></span>

3. <span data-ttu-id="63ba7-118">[**カラーピッカー** ] ( `Ctrl+K` ) ツールを開いて、現在のページで使用されている色の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="63ba7-118">Open the **Color picker** (`Ctrl+K`) tool to see a list of the colors in use on the current page.</span></span> <span data-ttu-id="63ba7-119">リストの色をクリックすると、さらに詳細 (色相、鮮やかさ、明度、アルファ) が提供されます。</span><span class="sxs-lookup"><span data-stu-id="63ba7-119">Clicking on a color on the list will provide further details (Hue, Saturation, Lightness, Alpha).</span></span> <span data-ttu-id="63ba7-120">また、[**スタイル**] ウィンドウで色の値の横にある色付きの正方形をクリックすると、*カラーピッカー*が開き、ページ要素の色を編集してすぐに結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="63ba7-120">The *Color picker* also opens when you click on the colored square next to a color value in the **Styles** pane, allowing you to edit the color of a page element and immediately see the results.</span></span>

4. <span data-ttu-id="63ba7-121">[ **Accessibility tree** ( `Ctrl+Shift+A` )] ボタンをクリックすると、 [Windows ナレーター](https://support.microsoft.com/help/22798/windows-10-narrator-get-started)スクリーンリーダーなどの支援技術に表示されるページの構造が表示された [[アクセシビリティツリー](./elements/accessibility.md) ] ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="63ba7-121">The **Accessibility tree** (`Ctrl+Shift+A`) button will open the [Accessibility tree](./elements/accessibility.md) pane showing the structure of your page as it would appear to an assistive technology, such as the [Windows Narrator](https://support.microsoft.com/help/22798/windows-10-narrator-get-started) screenreader.</span></span>

5. <span data-ttu-id="63ba7-122">**Find** `Ctrl+F` タグ名、属性、またはテキストの内容を検索することによって、HTML ツリービューで要素を検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="63ba7-122">You can also **Find** (`Ctrl+F`) an element in the HTML tree view by searching for its tag name, attributes, or text content.</span></span>

### <span data-ttu-id="63ba7-123">要素の編集</span><span class="sxs-lookup"><span data-stu-id="63ba7-123">Editing elements</span></span>

<span data-ttu-id="63ba7-124">HTML ツリービュー内で要素を右クリックし、コンテキストメニューから [ **html として編集**] を選択して要素を編集できます。</span><span class="sxs-lookup"><span data-stu-id="63ba7-124">You can edit an element by right-clicking on it within the HTML tree view and selecting **Edit as HTML** from the context menu.</span></span> <span data-ttu-id="63ba7-125">コンテキストメニューには、削除、切り取り、コピー、貼り付け、CSS 擬似クラス (*: active*、 *: focus*、 *: hover*、 *: アクセス*)、属性の追加のオプションも用意されています。</span><span class="sxs-lookup"><span data-stu-id="63ba7-125">The context menu also provides options to delete, cut, copy, paste, set CSS pseudo-classes (*:active*, *:focus*, *:hover*, *:visited*) and add attributes.</span></span> <span data-ttu-id="63ba7-126">属性やその値を編集するもう1つの方法は、HTML ツリービューから属性をダブルクリックすることです。</span><span class="sxs-lookup"><span data-stu-id="63ba7-126">Another way to edit an attribute and/or its value is to double-click it from the HTML tree view.</span></span>

![HTML ツリービューコンテキストメニュー](./media/elements_html_tree_context.png)

> [!NOTE]
> <span data-ttu-id="63ba7-128">HTML ツリーを編集しても、基になるソースマークアップには影響しません。</span><span class="sxs-lookup"><span data-stu-id="63ba7-128">Editing the HTML tree does not affect the underlying source markup.</span></span> <span data-ttu-id="63ba7-129">ページを更新すると、変更が元に戻り、ページソースによって決定されたレイアウトのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63ba7-129">Refreshing the page will revert your changes and render only the layout determined by the page source.</span></span> <span data-ttu-id="63ba7-130">変更した HTML をクリップボードに**コピー**するには、目的の要素 (またはページ全体を表示する場合はグローバル要素) を右クリックして `html` コンテキストメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="63ba7-130">You can **Copy** your modified HTML to the clipboard by right-clicking the desired element (or the global `html` element, if you want the entire page) to open up the context menu.</span></span> <span data-ttu-id="63ba7-131">([**切り取り**] と [**貼り付け**] のオプションも使用できます)。</span><span class="sxs-lookup"><span data-stu-id="63ba7-131">(**Cut** and **Paste** options are also available).</span></span>

<span data-ttu-id="63ba7-132">[[スタイル](./elements/styles.md)] ウィンドウでは、CSS の擬似状態と擬似要素の追加、削除、編集を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="63ba7-132">From the [Styles](./elements/styles.md) pane you can also add/delete/edit CSS pseudo-states and pseudo-elements.</span></span>

## <span data-ttu-id="63ba7-133">ツールウィンドウ</span><span class="sxs-lookup"><span data-stu-id="63ba7-133">Tool Panes</span></span>

<span data-ttu-id="63ba7-134">目的のページ要素を選択した後は、ツールウィンドウを使用して、その他のスタイルとアクセシビリティプロパティの検査、イベントリスナーの表示、DOM 変異ブレークポイントの設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="63ba7-134">Once you have selected a page element of interest, you can use the tool panes to further inspect its different styles and accessibility properties, view its event listeners, and set DOM mutation breakpoints.</span></span>

![[要素] パネルの [ツール] ウィンドウ](./media/elements_toolpanes.png)

1. <span data-ttu-id="63ba7-136">[**スタイル**](./elements/styles.md): 現在、スタイルシートによって整理されたスタイル</span><span class="sxs-lookup"><span data-stu-id="63ba7-136">[**Styles**](./elements/styles.md): Currently applied styles organized by stylesheet</span></span>

2. <span data-ttu-id="63ba7-137">[**計算**](./elements/computed.md)済み: 現在、CSS 属性によって整理されたスタイル</span><span class="sxs-lookup"><span data-stu-id="63ba7-137">[**Computed**](./elements/computed.md): Currently applied styles organized by CSS attributes</span></span>

3. <span data-ttu-id="63ba7-138">[**イベント**](./elements/events.md): 現在の要素と先祖要素に登録されているイベントリスナー</span><span class="sxs-lookup"><span data-stu-id="63ba7-138">[**Events**](./elements/events.md): Event listeners registered on the current element and ancestor elements</span></span>

4. <span data-ttu-id="63ba7-139">[**Dom ブレークポイント**](./elements/dom-breakpoints.md): Dom 変異ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="63ba7-139">[**DOM breakpoints**](./elements/dom-breakpoints.md): DOM Mutation Breakpoints</span></span> 

5. <span data-ttu-id="63ba7-140">[**フォント**](./elements/fonts.md): 選択した要素に対して現在適用されているフォント</span><span class="sxs-lookup"><span data-stu-id="63ba7-140">[**Fonts**](./elements/fonts.md): Currently applied fonts for a selected element</span></span>

6. <span data-ttu-id="63ba7-141">[**アクセシビリティ**](./elements/accessibility.md): アクセシビリティプロパティ</span><span class="sxs-lookup"><span data-stu-id="63ba7-141">[**Accessibility**](./elements/accessibility.md):  Accessibility properties</span></span>

7. <span data-ttu-id="63ba7-142">[**変更**](./elements/changes.md): 診断セッション中に行われた CSS の変更</span><span class="sxs-lookup"><span data-stu-id="63ba7-142">[**Changes**](./elements/changes.md): CSS changes made during diagnostic session</span></span>  

## <span data-ttu-id="63ba7-143">ショートカット</span><span class="sxs-lookup"><span data-stu-id="63ba7-143">Shortcuts</span></span>

| <span data-ttu-id="63ba7-144">操作</span><span class="sxs-lookup"><span data-stu-id="63ba7-144">Action</span></span>               | <span data-ttu-id="63ba7-145">キー</span><span class="sxs-lookup"><span data-stu-id="63ba7-145">Shortcut</span></span>               |
|:---------------------|:-----------------------|
| <span data-ttu-id="63ba7-146">要素パネル</span><span class="sxs-lookup"><span data-stu-id="63ba7-146">Elements panel</span></span>       | `Ctrl` + `1`           |
| <span data-ttu-id="63ba7-147">要素の強調表示</span><span class="sxs-lookup"><span data-stu-id="63ba7-147">Element highlighting</span></span> | `Ctrl` + `Shift` + `L` |
| <span data-ttu-id="63ba7-148">要素を選ぶ</span><span class="sxs-lookup"><span data-stu-id="63ba7-148">Select element</span></span>       | `Ctrl` + `B`           |
| <span data-ttu-id="63ba7-149">カラー ピッカー</span><span class="sxs-lookup"><span data-stu-id="63ba7-149">Color picker</span></span>         | `Ctrl` + `K`           |
| <span data-ttu-id="63ba7-150">アクセシビリティツリー</span><span class="sxs-lookup"><span data-stu-id="63ba7-150">Accessibility tree</span></span>   | `Ctrl` + `Shift` + `A` |
