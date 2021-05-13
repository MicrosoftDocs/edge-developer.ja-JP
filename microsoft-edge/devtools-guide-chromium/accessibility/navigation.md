---
description: スクリーン リーダーのような支援テクノロジMicrosoft Edge DevTools のナビゲーションに関するガイド。
title: 支援Microsoft Edge DevTools のナビゲーション
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: cf2742dfb08ee482b26fe43417b7454e5b6ff809
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564582"
---
<!-- Copyright Rob Dodson 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->
# <a name="navigate-microsoft-edge-devtools-with-assistive-technology"></a><span data-ttu-id="39942-104">支援Microsoft Edge DevTools のナビゲーション</span><span class="sxs-lookup"><span data-stu-id="39942-104">Navigate Microsoft Edge DevTools with assistive technology</span></span>  

<span data-ttu-id="39942-105">次の記事は、主にスクリーン リーダーのような支援テクノロジに依存しているユーザーが DevTools にアクセスして使用Microsoft Edge[を目的とします][MicrosoftEdgeDevtoolsMain]。</span><span class="sxs-lookup"><span data-stu-id="39942-105">The following article aims to help users who primarily rely on assistive technology like screen readers access and use [Microsoft Edge DevTools][MicrosoftEdgeDevtoolsMain].</span></span>  <span data-ttu-id="39942-106">[Microsoft Edge DevTools は][MicrosoftEdgeDevtoolsMain]、ブラウザーに組み込Microsoft Edgeです。</span><span class="sxs-lookup"><span data-stu-id="39942-106">[Microsoft Edge DevTools][MicrosoftEdgeDevtoolsMain] is a suite of web developer tools built into the Microsoft Edge browser.</span></span>  <span data-ttu-id="39942-107">Web ページのアクセシビリティの向上に関連する DevTools 機能を探している場合は、[アクセシビリティ リファレンス] [に移動します][DevtoolsAccessibilityReference]。</span><span class="sxs-lookup"><span data-stu-id="39942-107">If you are looking for DevTools features related to improving the accessibility of a web page,  navigate to [Accessibility Reference][DevtoolsAccessibilityReference].</span></span>  

<span data-ttu-id="39942-108">DevTools のアクセシビリティは、進行中の作業です。</span><span class="sxs-lookup"><span data-stu-id="39942-108">The accessibility of DevTools is a work-in-progress.</span></span>  <span data-ttu-id="39942-109">一部のパネルとタブは、他のパネルよりも支援技術に優れた機能を備えます。</span><span class="sxs-lookup"><span data-stu-id="39942-109">Some panels and tabs work better with assistive technology than others.</span></span>  <span data-ttu-id="39942-110">このガイドでは、最もアクセスしやすいパネルについて説明し、途中で発生する可能性のある特定の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="39942-110">This guide walks you through the panels which are the most accessible and highlights specific issues you may encounter along the way.</span></span>  

## <a name="overview"></a><span data-ttu-id="39942-111">概要</span><span class="sxs-lookup"><span data-stu-id="39942-111">Overview</span></span>  

<span data-ttu-id="39942-112">開始する前に、DevTools UI の構造化方法のメンタル モデルを作成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="39942-112">Before starting, it helps to have a mental model of how the DevTools UI is structured.</span></span>  <span data-ttu-id="39942-113">DevTools は、ARIA タブリストに編成された一連の [パネルに分かれています][W3CWaiAriaTablist]。</span><span class="sxs-lookup"><span data-stu-id="39942-113">DevTools is divided into a series of panels which are organized into an [ARIA tablist][W3CWaiAriaTablist].</span></span>  

<span data-ttu-id="39942-114">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="39942-114">For example:</span></span>  

*   <span data-ttu-id="39942-115">要素 **ツール** を使用すると、[DOM ノードの表示と変更][DevtoolsDomIndexNavigateDomTreeKeyboard] または CSS を使用 [できます][DevtoolsCssIndex]。</span><span class="sxs-lookup"><span data-stu-id="39942-115">The **Elements** tool lets you [view and change DOM nodes][DevtoolsDomIndexNavigateDomTreeKeyboard] or [CSS][DevtoolsCssIndex].</span></span>  
*   <span data-ttu-id="39942-116">コンソール [パネルでは、JavaScript][DevtoolsConsoleIndex] ログとライブ編集オブジェクトを読み取りできます。</span><span class="sxs-lookup"><span data-stu-id="39942-116">The [Console panel][DevtoolsConsoleIndex] lets you read JavaScript logs and live edit objects.</span></span>  

<span data-ttu-id="39942-117">各パネルのコンテンツ領域内には、多くの場合、ドキュメント内のタブまたはウィンドウと呼ばれるさまざまなツールがあります。</span><span class="sxs-lookup"><span data-stu-id="39942-117">Within the content area of each panel, there are a number of different tools, often referred to as tabs or panes in the documentation.</span></span>  
<span data-ttu-id="39942-118">たとえば **、Elements** ツールには、イベント リスナー、アクセシビリティ ツリーなど、その他のタブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="39942-118">For instance, the **Elements** tool contains additional tabs to inspect event listeners, the accessibility tree, and much more.</span></span>  <span data-ttu-id="39942-119">タブとウィンドウの違いは、やや任意です。</span><span class="sxs-lookup"><span data-stu-id="39942-119">The distinction between tabs and panes is somewhat arbitrary.</span></span>  <span data-ttu-id="39942-120">1 つの用語または他の用語を確認する唯一の理由は、DevTools の公式ドキュメントの残りの部分との整合性を維持する方法です。</span><span class="sxs-lookup"><span data-stu-id="39942-120">The only reason you may review one term or the other is to maintain consistency with the rest of the official DevTools documentation.</span></span>  

## <a name="keyboard-shortcuts"></a><span data-ttu-id="39942-121">キーボード ショートカット</span><span class="sxs-lookup"><span data-stu-id="39942-121">Keyboard shortcuts</span></span>  

<span data-ttu-id="39942-122">[DevTools キーボード ショートカット リファレンス][DevtoolsShortcuts] は役に立つチートシートです。</span><span class="sxs-lookup"><span data-stu-id="39942-122">The [DevTools Keyboard Shortcuts reference][DevtoolsShortcuts] is a helpful cheatsheet.</span></span>  <span data-ttu-id="39942-123">異なるパネルを探索する場合は、必ずブックマークを作成し、参照してください。</span><span class="sxs-lookup"><span data-stu-id="39942-123">Be sure to bookmark it and refer back to it as you explore the different panels.</span></span>  

## <a name="open-devtools"></a><span data-ttu-id="39942-124">DevTools を開く</span><span class="sxs-lookup"><span data-stu-id="39942-124">Open DevTools</span></span>  

<span data-ttu-id="39942-125">開始するには、[Open Microsoft Edge DevTools][DevtoolsOpen] に移動します。</span><span class="sxs-lookup"><span data-stu-id="39942-125">To get started, navigate to [Open Microsoft Edge DevTools][DevtoolsOpen].</span></span>  <span data-ttu-id="39942-126">キーボード ショートカットまたはメニュー項目を使用して DevTools を開く方法は多数あります。</span><span class="sxs-lookup"><span data-stu-id="39942-126">There are a number of ways to open DevTools, either through keyboard shortcuts or menu items.</span></span>  

## <a name="navigate-between-panels"></a><span data-ttu-id="39942-127">パネル間を移動する</span><span class="sxs-lookup"><span data-stu-id="39942-127">Navigate between panels</span></span>  

### <a name="navigate-by-keyboard"></a><span data-ttu-id="39942-128">キーボードによる移動</span><span class="sxs-lookup"><span data-stu-id="39942-128">Navigate by keyboard</span></span>  

*   <span data-ttu-id="39942-129">DevTools を開いた後 `Control` + `]` 、\(Windows、Linux\) または \(macOS\) を選択して、次のパネル `Command` + `]` にフォーカスを設定します。</span><span class="sxs-lookup"><span data-stu-id="39942-129">With DevTools open, select `Control`+`]` \(Windows, Linux\) or `Command`+`]` \(macOS\) to focus the next panel.</span></span>  
*   <span data-ttu-id="39942-130">`Control` + `[` 前のパネルにフォーカスWindows \(Windows Linux\) または `Command` + `[` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="39942-130">Select `Control`+`[` \(Windows, Linux\) or `Command`+`[` \(macOS\) to focus the previous panel.</span></span>  
*   <span data-ttu-id="39942-131">パネルの `Shift` + `Tab` [ARIA][W3CWaiAriaTablist]タブリストにフォーカスを移動し、矢印キーを使用してパネルを変更することもできますが、前述のショートカットを使用する方が速い場合があります。</span><span class="sxs-lookup"><span data-stu-id="39942-131">It is also possible to use `Shift`+`Tab` to move focus into the [ARIA tablist][W3CWaiAriaTablist] of a panel and use the arrow keys to change panels, though it may be faster to use the previously mentioned shortcuts.</span></span>  

**<span data-ttu-id="39942-132">既知の問題</span><span class="sxs-lookup"><span data-stu-id="39942-132">Known issues</span></span>**  

*   <span data-ttu-id="39942-133">[コンソール] ツールや [ **パフォーマンス]** ツールなどの一部の **パネルでは、** 各パネルがアクティブ化されるとすぐに、パネルコンテンツ領域にフォーカスが移動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="39942-133">Some panels, such as the **Console** and **Performance** tools, may move focus into the panel content area as soon as each panel is activated.</span></span>  <span data-ttu-id="39942-134">これにより、矢印キーによる移動が困難になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="39942-134">This may make navigating by arrow keys difficult.</span></span>  
*   <span data-ttu-id="39942-135">選択したパネルの名前は発表されますが、パネル内のフォーカスされたコンテンツを読み取った後にのみ発表されます。</span><span class="sxs-lookup"><span data-stu-id="39942-135">The name of the selected panel is announced, but only after it has read the focused content in the panel.</span></span>  <span data-ttu-id="39942-136">これにより、見逃しが非常に簡単になります。</span><span class="sxs-lookup"><span data-stu-id="39942-136">This may make it very easy to miss.</span></span>  

### <a name="navigate-by-command-menu"></a><span data-ttu-id="39942-137">[コマンド] メニューで移動する</span><span class="sxs-lookup"><span data-stu-id="39942-137">Navigate by Command Menu</span></span>  

<span data-ttu-id="39942-138">特定のパネルをフォーカスするには、コマンド メニュー [を使用します][DevtoolsCommandMenuIndex]。</span><span class="sxs-lookup"><span data-stu-id="39942-138">To focus a specific panel, use the [Command Menu][DevtoolsCommandMenuIndex]:</span></span>  

1.  <span data-ttu-id="39942-139">DevTools を開いた後 `Control` + `Shift` + `P` 、\(Windows、Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択してコマンド メニューを**開きます**。</span><span class="sxs-lookup"><span data-stu-id="39942-139">With DevTools open, select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    <span data-ttu-id="39942-140">コマンド **メニューは** 、あいまい検索オートコンプリート コンボ ボックスです。</span><span class="sxs-lookup"><span data-stu-id="39942-140">The **Command Menu** is a fuzzy search autocomplete combobox.</span></span>  
1.  <span data-ttu-id="39942-141">開くパネルの名前を入力し、キーボードで正しいオプション `Down Arrow` に移動します。</span><span class="sxs-lookup"><span data-stu-id="39942-141">Type the name of the panel you want to open, then use the `Down Arrow` on the keyboard to navigate to the correct option.</span></span>  
1.  <span data-ttu-id="39942-142">コマンド `Enter` を実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="39942-142">Select `Enter` to run a command.</span></span>  

<span data-ttu-id="39942-143">次のアクションを実行して、[要素] ツール **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="39942-143">Complete the following actions to open the **Elements** tool.</span></span>  

1.  <span data-ttu-id="39942-144">**コマンド メニュー** を開きます。</span><span class="sxs-lookup"><span data-stu-id="39942-144">Open the **Command Menu**.</span></span>  
1.  <span data-ttu-id="39942-145">次に `E` 入力 `L` します。</span><span class="sxs-lookup"><span data-stu-id="39942-145">Type `E` then `L`.</span></span>  <span data-ttu-id="39942-146">[ **パネル] >要素の表示** ] オプションが選択されています。</span><span class="sxs-lookup"><span data-stu-id="39942-146">The **Panel > Show Elements** option is selected.</span></span>  
1.  <span data-ttu-id="39942-147">パネル `Enter` を開くコマンドを実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="39942-147">Select `Enter` to run the command that opens the panel.</span></span>  

<span data-ttu-id="39942-148">この方法でパネルを開き、パネルの内容にフォーカスを当てる。</span><span class="sxs-lookup"><span data-stu-id="39942-148">Open a panel this way directs focus to the contents of the panel.</span></span>  <span data-ttu-id="39942-149">Elements ツールの場合、 **フォーカス** は DOM ツリーに **移動します**。</span><span class="sxs-lookup"><span data-stu-id="39942-149">In the case of the **Elements** tool, focus moves into the **DOM Tree**.</span></span>  

## <a name="elements-panel"></a><span data-ttu-id="39942-150">[要素] パネル</span><span class="sxs-lookup"><span data-stu-id="39942-150">Elements panel</span></span>  

### <a name="inspect-an-element-on-the-page"></a><span data-ttu-id="39942-151">ページ上の要素を検査する</span><span class="sxs-lookup"><span data-stu-id="39942-151">Inspect an element on the page</span></span>  

1.  <span data-ttu-id="39942-152">スクリーン リーダーのカーソルを使用して検査する要素に移動します。</span><span class="sxs-lookup"><span data-stu-id="39942-152">Navigate to the element you want to inspect using the cursor in the screen reader.</span></span>  
1.  <span data-ttu-id="39942-153">要素のマウスを使用して右クリックをシミュレートし、コンテキスト メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="39942-153">Simulate a right-click using a mouse on the element to open the context menu.</span></span>  
1.  <span data-ttu-id="39942-154">[検査] **オプションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="39942-154">Choose the **Inspect** option.</span></span>  <span data-ttu-id="39942-155">この [要素] パネルが開き、DOM ツリー内の要素に焦点を当て、[DevtoolsDomIndexViewDomNodes] になります。</span><span class="sxs-lookup"><span data-stu-id="39942-155">This [opens the Elements panel and focuses the element in the DOM Tree][DevtoolsDomIndexViewDomNodes].</span></span>  

<span data-ttu-id="39942-156">**DOM ツリーは** [ARIA ツリーとしてレイアウトされます][W3CWaiAriaTree]。</span><span class="sxs-lookup"><span data-stu-id="39942-156">The **DOM Tree** is laid out as an [ARIA tree][W3CWaiAriaTree].</span></span>  <span data-ttu-id="39942-157">例については、[キーボードを使用して **DOM ツリー** を移動する][DevtoolsDomIndexNavigateDomTreeKeyboard]に移動します。</span><span class="sxs-lookup"><span data-stu-id="39942-157">For an example, navigate to [Navigate the **DOM Tree** with a keyboard][DevtoolsDomIndexNavigateDomTreeKeyboard].</span></span>  

### <a name="copy-the-code-for-an-element-in-the-dom-tree"></a><span data-ttu-id="39942-158">DOM ツリー内の要素のコードをコピーする</span><span class="sxs-lookup"><span data-stu-id="39942-158">Copy the code for an element in the DOM Tree</span></span>  

1.  <span data-ttu-id="39942-159">**DOM**ツリーのノードにフォーカスを合わせると、ノードにカーソルを合わせると、コンテキスト メニュー \(右クリック\) が開きます。</span><span class="sxs-lookup"><span data-stu-id="39942-159">With focus on a node in the **DOM Tree**, hover on the node and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="39942-160">[コピー] **オプションを展開** します。</span><span class="sxs-lookup"><span data-stu-id="39942-160">Expand the **Copy** option.</span></span>  
1.  <span data-ttu-id="39942-161">[外部 **HTML のコピー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39942-161">Choose **Copy outerHTML**.</span></span>  

**<span data-ttu-id="39942-162">既知の問題</span><span class="sxs-lookup"><span data-stu-id="39942-162">Known issues</span></span>**  

*   <span data-ttu-id="39942-163">**多くの場合、copy outerHTML** は現在のノードを選択するのではなく、親ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="39942-163">**Copy outerHTML** often does not select the current node but instead selects the parent node.</span></span>  <span data-ttu-id="39942-164">ただし、要素の内容はコピーされた outerHTML に残っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="39942-164">However, the contents of the element should still be in the copied outerHTML.</span></span>  

### <a name="modify-the-attributes-of-an-element-in-the-dom-tree"></a><span data-ttu-id="39942-165">DOM ツリー内の要素の属性を変更する</span><span class="sxs-lookup"><span data-stu-id="39942-165">Modify the attributes of an element in the DOM Tree</span></span>  

*   <span data-ttu-id="39942-166">**DOM**ツリーのノードにフォーカスを置き、編集 `Enter` 可能にする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="39942-166">With focus on a node in the **DOM Tree**, select `Enter` to make it editable.</span></span>  
*   <span data-ttu-id="39942-167">属性値 `Tab` 間を移動する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="39942-167">Select `Tab` to move between attribute values.</span></span>  <span data-ttu-id="39942-168">"スペース" と聞くと、空のテキスト入力の内側に新しい属性値を入力できます。</span><span class="sxs-lookup"><span data-stu-id="39942-168">When you hear "space" you are inside of an empty text input and are able to type a new attribute value.</span></span>  
*   <span data-ttu-id="39942-169">`Control` + `Enter` \(Windows、Linux\) または `Command` + \(macOS\) を選択して変更を受け入れ、要素の内容 `Enter` 全体を確認します。</span><span class="sxs-lookup"><span data-stu-id="39942-169">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\) to accept the change and hear the entire contents of the element.</span></span>  

**<span data-ttu-id="39942-170">既知の問題</span><span class="sxs-lookup"><span data-stu-id="39942-170">Known issues</span></span>**  

*   <span data-ttu-id="39942-171">テキスト入力を入力すると、フィードバックは得かねない。</span><span class="sxs-lookup"><span data-stu-id="39942-171">When you type into the text input you get no feedback.</span></span>  <span data-ttu-id="39942-172">入力ミスを行い、矢印キーを使用して入力を確認すると、フィードバックも得かねない。</span><span class="sxs-lookup"><span data-stu-id="39942-172">If you make a typo and use the arrow keys to explore your input you also get no feedback.</span></span>  <span data-ttu-id="39942-173">作業を確認する最も簡単な方法は、変更を受け入れてから、発表される要素全体をリッスンする方法です。</span><span class="sxs-lookup"><span data-stu-id="39942-173">The easiest way to check your work is to accept the change, then listen for the entire element to be announced.</span></span>  

### <a name="edit-the-html-of-an-element-in-the-dom-tree"></a><span data-ttu-id="39942-174">DOM ツリーで要素の HTML を編集する</span><span class="sxs-lookup"><span data-stu-id="39942-174">Edit the HTML of an element in the DOM Tree</span></span>  

*   <span data-ttu-id="39942-175">**DOM**ツリーのノードにフォーカスを置き、編集 `Enter` 可能にする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="39942-175">With focus on a node in the **DOM Tree**, select `Enter` to make it editable.</span></span>  
*   <span data-ttu-id="39942-176">属性値 `Tab` 間を移動する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="39942-176">Select `Tab` to move between attribute values.</span></span>  <span data-ttu-id="39942-177">たとえば、要素の名前が聞こえると、テキスト入力の内部にいて、要素の種類 `h2` が変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="39942-177">When you hear the name of the element, for instance, `h2`, you are inside of a text input and may change the type of the element.</span></span>  
*   <span data-ttu-id="39942-178">`Control` + `Enter` \(Windows Linux\) または `Command` + `Enter` \(macOS\) を選択して変更を受け入れる。</span><span class="sxs-lookup"><span data-stu-id="39942-178">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\) to accept the change.</span></span>  

<span data-ttu-id="39942-179">たとえば `h3` `Control` + `Enter` 、\(Windows、Linux\) または `Command` + `Enter` \(macOS\) を入力して選択すると、要素の開始タグと終了タグが `h3` 変更されます。</span><span class="sxs-lookup"><span data-stu-id="39942-179">For example, when you type `h3` and select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\), the start and end tags of the `h3` element change.</span></span>  

## <a name="elements-tool-panels"></a><span data-ttu-id="39942-180">要素ツール パネル</span><span class="sxs-lookup"><span data-stu-id="39942-180">Elements tool panels</span></span>  

<span data-ttu-id="39942-181">要素 **ツール** には、要素に適用される CSS やアクセシビリティ ツリー内の関連する場所など、その他のタブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="39942-181">The **Elements** tool contains additional tabs for inspecting things like the CSS applied to an element or the relevant place in the accessibility tree.</span></span>  

*   <span data-ttu-id="39942-182">DOM ツリーのノードにフォーカスがある場合 **は、[** スタイル] ウィンドウが選択されているという `Tab` 音 **がするまで** 選択します。</span><span class="sxs-lookup"><span data-stu-id="39942-182">With focus on a node in the **DOM Tree**, select `Tab` until you hear that the **Styles** pane is selected.</span></span>  
*   <span data-ttu-id="39942-183">その他の `Right Arrow` 使用可能なタブを表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="39942-183">Use the `Right Arrow` to explore other available tabs.</span></span>  

<span data-ttu-id="39942-184">**DOM ツリーは**属性を持つ要素をフォーカス可能なリンクに変換します。そのため、[スタイル] ウィンドウに移動するには、複数の要素 `href` を選択 `Tab` する**必要があります**。</span><span class="sxs-lookup"><span data-stu-id="39942-184">The **DOM Tree** turns elements with `href` attributes into focusable links, so you may need to select `Tab` more than once to reach the **Styles** pane.</span></span>  

**<span data-ttu-id="39942-185">既知の問題</span><span class="sxs-lookup"><span data-stu-id="39942-185">Known issues</span></span>**  

<span data-ttu-id="39942-186">**[DOM ブレークポイント] タブと** **[プロパティ] タブ**はキーボードにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="39942-186">The **DOM Breakpoints** and **Properties** tabs are not keyboard accessible.</span></span>  

### <a name="styles-pane"></a><span data-ttu-id="39942-187">[スタイル] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="39942-187">Styles pane</span></span>  

<span data-ttu-id="39942-188">[スタイル **] ウィンドウで**、スタイルのフィルター処理、要素の状態 \(:active、:focus\など) の切り替え、クラスの切り替え、および新しいクラスの追加のコントロールを検索します。 [][MDNActive] [][MDNFocus]</span><span class="sxs-lookup"><span data-stu-id="39942-188">In the **Styles** pane find controls for filtering styles, toggling element states \(such as [:active][MDNActive] and [:focus][MDNFocus]\), toggling classes, and adding new classes.</span></span>  <span data-ttu-id="39942-189">また、DOM ツリーでフォーカスされている要素に現在適用されているスタイルを探索および変更するための強力なスタイル検査ツール **も用意されています**。</span><span class="sxs-lookup"><span data-stu-id="39942-189">There is also a powerful style inspection tool to explore and modify styles currently applied to the element that is in focus in the **DOM Tree**.</span></span>  

<span data-ttu-id="39942-190">[スタイル] ウィンドウについて理解\*\*\*\* する重要な概念は、DOM ツリーで現在選択されているノードのスタイルのみを**表示する点です**。</span><span class="sxs-lookup"><span data-stu-id="39942-190">The key concept to understand about the **Styles** pane is that it only shows styles for the currently-selected node in the **DOM Tree**.</span></span>  <span data-ttu-id="39942-191">たとえば、ノードのスタイルの検査が完了し、ノードのスタイルを確認 `<header>` すると `<footer>` します。</span><span class="sxs-lookup"><span data-stu-id="39942-191">For example, suppose you are done inspecting the styles of a `<header>` node, and now you want to look at the styles for a `<footer>` node.</span></span>  <span data-ttu-id="39942-192">これを行うには、まず DOM ツリーで `<footer>` ノードを選択する **必要があります**。</span><span class="sxs-lookup"><span data-stu-id="39942-192">To do that, you first need to select the `<footer>` node in the **DOM Tree**.</span></span>  <span data-ttu-id="39942-193">Inspect ワークフローを使用して[](#inspect-an-element-on-the-page)、DOM ツリーに焦点を当てたノード `footer` \(フッター\内のリンクなど) の一般的な近傍にあるノードを検査し、\*\*\*\* キーボードを使用して目的の正確なノードに移動する方が速い場合があります。</span><span class="sxs-lookup"><span data-stu-id="39942-193">You may find it faster to use the [Inspect](#inspect-an-element-on-the-page) workflow to inspect a node that is in the general vicinity of the `footer` node \(such as a link within the footer\), which focuses the **DOM Tree**, and then use your keyboard to navigate to the exact node in which you are interested.</span></span>  

#### <a name="navigate-the-styles-pane"></a><span data-ttu-id="39942-194">[スタイル] ウィンドウを移動する</span><span class="sxs-lookup"><span data-stu-id="39942-194">Navigate the Styles pane</span></span>  

<span data-ttu-id="39942-195">すべてのスタイル ツールは、何通りか別の方法で [\*\*\*\* スタイル] ウィンドウに接続されます。このツールの専門家になるのは、まず意味があります。</span><span class="sxs-lookup"><span data-stu-id="39942-195">Because all of the style tools connect in one way or another back to the **Styles** pane, it makes sense to become an expert in this tool first.</span></span>  

*   <span data-ttu-id="39942-196">[スタイル] ウィンドウに **フォーカスを置** いて、フォーカス `Tab` を内側に移動し、コンテンツを確認します。</span><span class="sxs-lookup"><span data-stu-id="39942-196">With focus on the **Styles** pane, select `Tab` to move focus inside and explore the contents.</span></span>  
*   <span data-ttu-id="39942-197">最初 `Tab` のスタイルがアクティブになるまで選択します。</span><span class="sxs-lookup"><span data-stu-id="39942-197">Select `Tab` until the first style becomes active.</span></span>  <span data-ttu-id="39942-198">スクリーン リーダーを使用している場合、この最初のスタイルはとして発表されます `element.style {}` 。</span><span class="sxs-lookup"><span data-stu-id="39942-198">If you are using a screen reader this first style is announced as `element.style {}`.</span></span>  
*   <span data-ttu-id="39942-199">スタイル `Down Arrow` の一覧を特定の順序で移動する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="39942-199">Select `Down Arrow` to navigate the list of styles in order of specificity.</span></span>  <span data-ttu-id="39942-200">スクリーン リーダーは、CSS ファイルの名前、スタイルが表示される行番号、およびスタイルの名前から始まる各スタイルをアナウンスします。</span><span class="sxs-lookup"><span data-stu-id="39942-200">A screen reader announces each style starting with the name of the CSS file, the line number on which the style appears, and the name of the style.</span></span>  <span data-ttu-id="39942-201">例: `main.css:233 .card__img {}`。</span><span class="sxs-lookup"><span data-stu-id="39942-201">For example, `main.css:233 .card__img {}`.</span></span>  
*   <span data-ttu-id="39942-202">スタイル `Enter` の詳細を調べている場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="39942-202">Select `Enter` to inspect a style in more detail.</span></span>  <span data-ttu-id="39942-203">フォーカスは、スタイル名の編集可能なバージョンから始まります。</span><span class="sxs-lookup"><span data-stu-id="39942-203">Focus begins on an editable version of the style name.</span></span>  
*   <span data-ttu-id="39942-204">各 `Tab` CSS プロパティの編集可能なバージョンと対応する値の間を移動する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="39942-204">Select `Tab` to move between editable versions of each CSS property and the corresponding values.</span></span>  <span data-ttu-id="39942-205">各スタイル ブロックの最後には、空白の編集可能なテキスト フィールドが表示され、追加の CSS プロパティを追加するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="39942-205">At the end of each style block is a blank editable text field which you may use to add additional CSS properties.</span></span>  
*   <span data-ttu-id="39942-206">引き続き選択してスタイルの一覧を移動するか、モードを終了して矢印キーによるナビゲーション `Tab` `Escape` に戻ります。</span><span class="sxs-lookup"><span data-stu-id="39942-206">You may continue to select `Tab` to move through the list of styles, or select `Escape` to exit the mode and go back to navigating by arrow keys.</span></span>  

<span data-ttu-id="39942-207">追加のショートカットについては、[スタイル ウィンドウ キーボード リファレンス][DevtoolsShortcutsStylesPaneKeyboard]に移動します。</span><span class="sxs-lookup"><span data-stu-id="39942-207">For additional shortcuts, navigate to [Styles pane keyboard reference][DevtoolsShortcutsStylesPaneKeyboard].</span></span>  

**<span data-ttu-id="39942-208">既知の問題</span><span class="sxs-lookup"><span data-stu-id="39942-208">Known issues</span></span>**  

*   <span data-ttu-id="39942-209">[編集可能なテキストの **フィルター]** フィールドを使用すると、スタイルの一覧を移動できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="39942-209">If you use the **Filter** editable text field, you are no longer be able to navigate the list of styles.</span></span>  

#### <a name="toggle-element-state"></a><span data-ttu-id="39942-210">要素の状態を切り替える</span><span class="sxs-lookup"><span data-stu-id="39942-210">Toggle element state</span></span>  

<span data-ttu-id="39942-211">要素の状態を切り替えるには、次のように `:active` します `:focus` 。</span><span class="sxs-lookup"><span data-stu-id="39942-211">To toggle the state of an element, such as `:active` or `:focus`:</span></span>  

1.  <span data-ttu-id="39942-212">[スタイル] ウィンドウ **に移動** し、[要素 `Tab` の状態の切り替え] ボタンがフォーカスを **持つまで** 選択します。</span><span class="sxs-lookup"><span data-stu-id="39942-212">Navigate to the **Styles** pane and select `Tab` until the **Toggle Element State** button has focus.</span></span>  
1.  <span data-ttu-id="39942-213">要素 `Enter` の状態のコレクションを展開する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="39942-213">Select `Enter` to expand the collection of element states.</span></span>  <span data-ttu-id="39942-214">要素の状態は、チェック ボックスのグループとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="39942-214">The element states are presented as a group of checkboxes.</span></span>  
1.  <span data-ttu-id="39942-215">最初 `Tab` の状態がフォーカスを `:active` 持つまで選択します。</span><span class="sxs-lookup"><span data-stu-id="39942-215">Select `Tab` until the first state, `:active`, has focus.</span></span>  
1.  <span data-ttu-id="39942-216">有効 `Space` にする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="39942-216">Select `Space` to enable it.</span></span>  <span data-ttu-id="39942-217">DOM ツリーで現在選択されている要素にスタイルがある場合は `:active` 、そのスタイルが適用されます。</span><span class="sxs-lookup"><span data-stu-id="39942-217">If the currently-selected element in the DOM Tree has an `:active` style, it is now applied.</span></span>  
1.  <span data-ttu-id="39942-218">ホールド `Tab` して、使用可能なすべての状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="39942-218">Hold `Tab` to explore all of the available states.</span></span>  

#### <a name="add-an-existing-class"></a><span data-ttu-id="39942-219">既存のクラスを追加する</span><span class="sxs-lookup"><span data-stu-id="39942-219">Add an existing class</span></span>  

<span data-ttu-id="39942-220">[要素の状態の **切り替え] ボタン** の隣には、[ **要素クラス] ボタン** があります。</span><span class="sxs-lookup"><span data-stu-id="39942-220">Adjacent to the **Toggle Element State** button is the **Element Classes** button.</span></span>  <span data-ttu-id="39942-221">フォーカスを移動するには、を選択して `Tab` 選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="39942-221">To move the focus to it, select `Tab` and select `Enter`.</span></span>  <span data-ttu-id="39942-222">[新しいクラスの追加] というラベルの付いた編集テキスト フィールド **にフォーカスが移動します**。</span><span class="sxs-lookup"><span data-stu-id="39942-222">Focus moves into an edit text field labeled **Add New Class**.</span></span>  

<span data-ttu-id="39942-223">[ **要素クラス]** ボタンは、主に要素に既存のクラスを追加するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="39942-223">The **Element Classes** button is primarily used for adding existing classes to an element.</span></span>  <span data-ttu-id="39942-224">たとえば、スタイルシートにという名前のヘルパー クラスが含まれている場合は、編集テキスト フィールドの内側を選択して、クラスの候補リストを表示し、 を使用して候補を `.clearfix` `.` `Down Arrow` 検索 `.clearfix` できます。</span><span class="sxs-lookup"><span data-stu-id="39942-224">For example, if your stylesheet contained a helper class named `.clearfix` you may select `.` inside of the edit text field to display a suggestion list of classes and use the `Down Arrow` to find the `.clearfix` suggestion.</span></span>  <span data-ttu-id="39942-225">または、自分でクラス名を入力し、適用 `Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="39942-225">Or type the class name out yourself and select `Enter` to apply it.</span></span>  

#### <a name="add-a-new-style-rule"></a><span data-ttu-id="39942-226">新しいスタイル ルールを追加する</span><span class="sxs-lookup"><span data-stu-id="39942-226">Add a new style rule</span></span>  

<span data-ttu-id="39942-227">[要素クラス] **ボタンの隣** には、[新しいスタイル **ルール] ボタン** があります。</span><span class="sxs-lookup"><span data-stu-id="39942-227">Adjacent to the **Element Classes** button is the **New Style Rule** button.</span></span>  <span data-ttu-id="39942-228">フォーカスを移動するには、を選択して `Tab` 選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="39942-228">To move the focus to it, select `Tab` and select `Enter`.</span></span>  <span data-ttu-id="39942-229">フォーカスは、スタイル インスペクター内の編集可能なテキスト フィールドに移動します。</span><span class="sxs-lookup"><span data-stu-id="39942-229">Focus moves into an editable text field inside of the style inspector.</span></span>  <span data-ttu-id="39942-230">フィールドの最初のテキストコンテンツは **、DOM**ツリーで選択されている要素のタグ名です。</span><span class="sxs-lookup"><span data-stu-id="39942-230">The initial text content of the field is the tag name of the element that is selected in the **DOM Tree**.</span></span>  
<span data-ttu-id="39942-231">このフィールドに任意のクラス名を入力し、CSS プロパティを割り当 `Tab` てる場合に選択できます。</span><span class="sxs-lookup"><span data-stu-id="39942-231">You may type any class name you want into this field and then select `Tab` to assign CSS properties to it.</span></span>  

### <a name="computed-tab"></a><span data-ttu-id="39942-232">[計算] タブ</span><span class="sxs-lookup"><span data-stu-id="39942-232">Computed tab</span></span>  

<span data-ttu-id="39942-233">[計算] タブに **フォーカスを置** いて、フォーカス `Tab` を内部に移動し、コンテンツを探索する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="39942-233">With focus on the **Computed** tab, select `Tab` to move focus inside and explore the contents.</span></span>  <span data-ttu-id="39942-234">[計算 **] タブ** には、特定の順序で要素に実際に適用される CSS プロパティを確認するコントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="39942-234">Within the **Computed** tab there are controls for exploring which CSS properties are actually applied to an element in order of specificity.</span></span>  

<!--todo: add computed tab section when available  -->  

#### <a name="explore-all-computed-styles"></a><span data-ttu-id="39942-235">すべての計算スタイルを見る</span><span class="sxs-lookup"><span data-stu-id="39942-235">Explore all computed styles</span></span>  

<span data-ttu-id="39942-236">計算 `Tab` されたスタイルのコレクションに到達するまで選択します。</span><span class="sxs-lookup"><span data-stu-id="39942-236">Select `Tab` until you reach the collection of computed styles.</span></span>  <span data-ttu-id="39942-237">これらは ARIA ツリー [として表示されます][W3CWaiAriaTree]。</span><span class="sxs-lookup"><span data-stu-id="39942-237">These are presented as an [ARIA tree][W3CWaiAriaTree].</span></span>  <span data-ttu-id="39942-238">リスト ボックスを展開すると、計算されたスタイルを適用している CSS セレクターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39942-238">Expanding a listbox reveals which CSS selectors are applying the computed style.</span></span>  <span data-ttu-id="39942-239">これらのセレクターは、固有の構成で構成されます。</span><span class="sxs-lookup"><span data-stu-id="39942-239">These selectors are organized by specificity.</span></span>  <span data-ttu-id="39942-240">スクリーン リーダーは、計算された値、現在一致している CSS セレクター、セレクターを含むスタイルシートのファイル名、およびセレクターの行番号をアナウンスします。</span><span class="sxs-lookup"><span data-stu-id="39942-240">A screen reader announces the computed value, which CSS selector is currently matching, the filename of the stylesheet that contains the selector, and the line number for the selector.</span></span>  

**<span data-ttu-id="39942-241">既知の問題</span><span class="sxs-lookup"><span data-stu-id="39942-241">Known issues</span></span>**  

*   <span data-ttu-id="39942-242">[フィルター] テキスト **フィールドを** 使用すると、スタイルを検査できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="39942-242">If you use the **Filter** text field, you are no longer able to inspect styles.</span></span>  

### <a name="event-listeners-tab"></a><span data-ttu-id="39942-243">[イベント リスナー] タブ</span><span class="sxs-lookup"><span data-stu-id="39942-243">Event listeners tab</span></span>  

<span data-ttu-id="39942-244">要素ツール **内から** 、[イベント リスナー] タブを使用して、要素に適用されるイベント **リスナーを検査** できます。 [スタイル] パネルに **フォーカスを置** き、[イベント リスナー] `Right Arrow` パネル **に移動します** 。</span><span class="sxs-lookup"><span data-stu-id="39942-244">From within the **Elements** tool you may inspect the event listeners applied to an element using the **Event Listeners** tab.  With focus on the **Styles** panel, select the `Right Arrow` to navigate to the **Event Listeners** panel.</span></span>  

#### <a name="explore-event-listeners"></a><span data-ttu-id="39942-245">イベント リスナーの探索</span><span class="sxs-lookup"><span data-stu-id="39942-245">Explore event listeners</span></span>  

<span data-ttu-id="39942-246">イベント リスナーは [ARIA ツリーとして表示されます][W3CWaiAriaTree]。</span><span class="sxs-lookup"><span data-stu-id="39942-246">Event listeners are presented as an [ARIA tree][W3CWaiAriaTree].</span></span>  <span data-ttu-id="39942-247">矢印キーを使用して移動できます。</span><span class="sxs-lookup"><span data-stu-id="39942-247">You may use the arrow keys to navigate them.</span></span>  <span data-ttu-id="39942-248">スクリーン リーダーは、イベント リスナーが接続されている DOM オブジェクトの名前と、イベント リスナーが定義されているファイル名と行番号をアナウンスします。</span><span class="sxs-lookup"><span data-stu-id="39942-248">A screen reader announces the name of the DOM object that the event listener is attached to, as well as the file name where the event listener is defined and the line number.</span></span>  

### <a name="accessibility-pane"></a><span data-ttu-id="39942-249">アクセシビリティ ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="39942-249">Accessibility pane</span></span>  

<span data-ttu-id="39942-250">[アクセシビリティ] ウィンドウに **フォーカスを置いて** 、フォーカス `Tab` を内部に移動し、コンテンツを探索する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="39942-250">With focus on the **Accessibility** pane, select `Tab` to move focus inside and explore the contents.</span></span>  <span data-ttu-id="39942-251">[アクセシビリティ [] ウィンドウには][DevtoolsAccessibilityReference] 、アクセシビリティ ツリー、要素に適用される ARIA 属性、および計算されたアクセシビリティ プロパティを探索するコントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="39942-251">On the [Accessibility pane][DevtoolsAccessibilityReference] there are controls for exploring the accessibility tree, the ARIA attributes applied to an element, and the computed accessibility properties.</span></span>  

#### <a name="accessibility-tree"></a><span data-ttu-id="39942-252">アクセシビリティ ツリー</span><span class="sxs-lookup"><span data-stu-id="39942-252">Accessibility Tree</span></span>  

<span data-ttu-id="39942-253">アクセシビリティ **ツリーは ARIA** ツリーとして表示され、 [各][W3CWaiAriaTree] ツリーは DOM 内の `treeitem` 要素に対応します。</span><span class="sxs-lookup"><span data-stu-id="39942-253">The **Accessibility Tree** is presented as an [ARIA tree][W3CWaiAriaTree] where each `treeitem` corresponds to an element in the DOM.</span></span>  <span data-ttu-id="39942-254">ツリーは、選択したノードの計算された役割をアナウンスします。</span><span class="sxs-lookup"><span data-stu-id="39942-254">The tree announces the computed role for the selected node.</span></span>  <span data-ttu-id="39942-255">ツリー内の `div` `span` "GenericContainer" のような汎用的な要素が発表されます。</span><span class="sxs-lookup"><span data-stu-id="39942-255">Generic elements like `div` and `span` are announced as "GenericContainer" in the tree.</span></span>  <span data-ttu-id="39942-256">矢印キーを使用してツリーを走査し、親子関係を探索します。</span><span class="sxs-lookup"><span data-stu-id="39942-256">Use the arrow keys to traverse the tree and explore parent-child relationships.</span></span>  

**<span data-ttu-id="39942-257">既知の問題</span><span class="sxs-lookup"><span data-stu-id="39942-257">Known issues</span></span>**  

*   <span data-ttu-id="39942-258">アクセシビリティ ウィンドウ[で使用される ARIA][W3CWaiAriaTree]ツリーの種類は、VoiceOver のような macOS スクリーン リーダー Microsoft Edgeで適切に公開されない場合があります。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="39942-258">The type of [ARIA tree][W3CWaiAriaTree] used by the **Accessibility** pane may not be properly exposed in Microsoft Edge for macOS screen readers like VoiceOver.</span></span>  <span data-ttu-id="39942-259">この問題[Chromium進捗#868480][ChromiumIssues868480]通知を受け取る場合は、この問題を購読してください。</span><span class="sxs-lookup"><span data-stu-id="39942-259">Subscribe to [Chromium issue #868480][ChromiumIssues868480] to be informed about progress on this issue.</span></span>  
*   <span data-ttu-id="39942-260">**[ARIA 属性**]\*\*\*\* セクションと [計算されたプロパティ] セクションのそれぞれは[ARIA][W3CWaiAriaTree]ツリーとしてマークされますが、それぞれが現在フォーカス管理を行っているのではなく、キーボード操作可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="39942-260">Each of the **ARIA Attributes** and **Computed Properties** sections are marked up as an [ARIA tree][W3CWaiAriaTree], but each does not currently have focus management and is not keyboard operable.</span></span>  

## <a name="audits-panel"></a><span data-ttu-id="39942-261">[監査] パネル</span><span class="sxs-lookup"><span data-stu-id="39942-261">Audits panel</span></span>  

<span data-ttu-id="39942-262">監査 **ツールでは** 、サイトに対して一連のテストを実行して、パフォーマンス、アクセシビリティ、SEO、その他の多くのカテゴリに関連する一般的な問題を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39942-262">The **Audits** tool you should run a series of tests against a site to check for common issues related to performance, accessibility, SEO, and a number of other categories.</span></span>  

### <a name="configure-and-run-an-audit"></a><span data-ttu-id="39942-263">監査の構成と実行</span><span class="sxs-lookup"><span data-stu-id="39942-263">Configure and run an audit</span></span>  

1.  <span data-ttu-id="39942-264">監査ツール**が最初**に開かれると、フォームの最後にある [\*\*\*\* 監査の実行] ボタンにフォーカスが移動します。</span><span class="sxs-lookup"><span data-stu-id="39942-264">When the **Audits** tool is first opened, focus is placed on the **Run Audit** button at the end of the form.</span></span>  <span data-ttu-id="39942-265">既定では、フォームは、シミュレートされた 3G 接続でモバイル エミュレーションを使用してすべてのカテゴリの監査を実行するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="39942-265">By default the form is configured to run audits for every category using mobile emulation on a simulated 3G connection.</span></span>  
1.  <span data-ttu-id="39942-266">監査 `Shift` + `Tab` 設定を変更するには、参照モードで使用または移動します。</span><span class="sxs-lookup"><span data-stu-id="39942-266">Use `Shift`+`Tab` or navigate back in Browse mode to change the audit settings.</span></span>  
1.  <span data-ttu-id="39942-267">監査を実行する準備ができたら、[監査の実行] ボタンに戻 **り、** を選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="39942-267">When you are ready to run the audit, navigate back to the **Run Audit** button and select `Enter`.</span></span>  
1.  <span data-ttu-id="39942-268">フォーカスは、監査を終了できる **[キャンセル** ] ボタンを使用してモーダル ウィンドウに移動します。</span><span class="sxs-lookup"><span data-stu-id="39942-268">Focus moves into a modal window with a **Cancel** button which allows you to exit the audit.</span></span>  <span data-ttu-id="39942-269">監査が実行され、ページが複数回更新されると、一連の耳鳴り音が聞こえる場合があります。</span><span class="sxs-lookup"><span data-stu-id="39942-269">You may hear a series of earcons as the audit runs and refreshes the page multiple times.</span></span>  

**<span data-ttu-id="39942-270">既知の問題</span><span class="sxs-lookup"><span data-stu-id="39942-270">Known issues</span></span>**  

*   <span data-ttu-id="39942-271">構成フォームの異なるセクションは、現在要素でマーク `fieldset` 付けされていない。</span><span class="sxs-lookup"><span data-stu-id="39942-271">The different sections of the configuration form are not currently marked up with a `fieldset` element.</span></span>  <span data-ttu-id="39942-272">参照モードで移動して、各セクションに関連付けられているコントロールを把握する方が簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="39942-272">It may be easier to navigate them in Browse mode to figure out which controls are associated with each section.</span></span>  
*   <span data-ttu-id="39942-273">監査の実行が完了すると、耳コンやライブ領域のアナウンスはありません。</span><span class="sxs-lookup"><span data-stu-id="39942-273">There is no earcon or live region announcement when the audit is finished running.</span></span>  <span data-ttu-id="39942-274">通常、所要時間は約 30 秒で、その後、結果に移動できます。</span><span class="sxs-lookup"><span data-stu-id="39942-274">Generally it takes about 30 seconds, after which you should be able to navigate to the results.</span></span>  <span data-ttu-id="39942-275">ブラウズ モードを使用すると、結果に最も簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="39942-275">Using Browse mode may be the easiest way to reach the results.</span></span>  

### <a name="navigate-the-audit-report"></a><span data-ttu-id="39942-276">監査レポートを移動する</span><span class="sxs-lookup"><span data-stu-id="39942-276">Navigate the audit report</span></span>  

<span data-ttu-id="39942-277">監査レポートは、各監査カテゴリに対応するセクションに編成されます。</span><span class="sxs-lookup"><span data-stu-id="39942-277">The audit report is organized into sections that correspond with each of the audit categories.</span></span>  <span data-ttu-id="39942-278">レポートが開き、各カテゴリのスコアの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39942-278">The report opens with a list of scores for each category.</span></span>  <span data-ttu-id="39942-279">これらのスコアは、関連するセクションにスキップするために使用できるリンクです。</span><span class="sxs-lookup"><span data-stu-id="39942-279">These scores are also links which are able to be used to skip to the relevant sections.</span></span>  <span data-ttu-id="39942-280">各セクション内には、渡された監査または失敗した監査に関連する情報を含む拡張可能 `details` な要素があります。</span><span class="sxs-lookup"><span data-stu-id="39942-280">Within each section are expandable `details` elements, which contain information relating to passed or failed audits.</span></span>  <span data-ttu-id="39942-281">既定では、失敗した監査だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39942-281">By default, only failing audits are shown.</span></span>  <span data-ttu-id="39942-282">各セクションは、渡された `details` 監査のすべてが含まれる最終的な要素で終わります。</span><span class="sxs-lookup"><span data-stu-id="39942-282">Each section ends with a final `details` element which contains all of the passed audits.</span></span>  

<span data-ttu-id="39942-283">新しい監査を実行するには、レポートを終了し、[監査の実行] `Shift` + `Tab` **ボタンを探します**。</span><span class="sxs-lookup"><span data-stu-id="39942-283">To run a new audit, use `Shift`+`Tab` to exit the report and look for the **Perform An Audit** button.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="39942-284">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="39942-284">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsAccessibilityReference]: ./reference.md "アクセシビリティ|Microsoft Docs"  
[DevtoolsAccessibilityReferencePane]: reference.md#the-accessibility-pane "[アクセシビリティ] ウィンドウ - [アクセシビリティ リファレンス] |Microsoft Docs"  
[MicrosoftEdgeDevtoolsMain]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsCommandMenuIndex]: ../command-menu/index.md "[DevTools コマンド メニュー] Microsoft Edgeを使用してコマンドを実行|Microsoft Docs"  
[DevtoolsConsoleIndex]: ../console/index.md "コンソールの概要 | Microsoft Docs"  
[DevtoolsCssIndex]: ../css/index.md "はじめにCSS の表示と変更を使用|Microsoft Docs"  
<!--[DevtoolsCssReferenceViewAppliedElement]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "CSS Reference - View only the CSS that is actually applied to an element | Microsoft Docs"  -->  
<!--[DevtoolsDomIndex]: ../dom/index.md "Get started with viewing and changing the DOM | Microsoft Docs"  -->  
[DevtoolsDomIndexViewDomNodes]: ../dom/index.md#view-dom-nodes "View DOM ノード - DOM ノードの表示と変更の|Microsoft Docs"  
[DevtoolsDomIndexNavigateDomTreeKeyboard]: ../dom/index.md#navigate-the-dom-tree-with-a-keyboard "キーボードを使用して DOM ツリーを移動する - DOM ツリーの表示と変更の|Microsoft Docs"  
[DevtoolsOpen]: ../open/index.md "Open Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsShortcuts]: ../shortcuts/index.md "Microsoft Edge DevTools キーボード ショートカット |Microsoft Docs"  
[DevtoolsShortcutsStylesPaneKeyboard]: ../shortcuts/index.md#styles-panel-keyboard-shortcuts "Styles panel keyboard shortcuts - Microsoft Edge DevTools キーボード ショートカット |Microsoft Docs"  

[ChromiumIssues868480]: https://bugs.chromium.org/p/chromium/issues/detail?id=868480 "問題 868480 - Mac アクセシビリティで ARIA ツリーをテーブルとして公開する"  

[GithubEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Docs%20Feedback%5D "新しい問題 - MicrosoftDocs/edge-developer |GitHub"  

[MDNActive]: https://developer.mozilla.org/docs/Web/CSS/:active ":active |MDN"  
[MDNFocus]: https://developer.mozilla.org/docs/Web/CSS/:focus ":focus |MDN"  

[MonorailChromiumIssues]: https://crbug.com "問題 - クロム - モノレール"  

[W3CWaiAriaTablist]: https://www.w3.org/TR/wai-aria-1.1/#tablist "tablist (role) - アクセス可能なリッチ インターネット アプリケーション (WAI-ARIA) 1.1 |W3C"  
[W3CWaiAriaTree]: https://www.w3.org/TR/wai-aria-1.1/#tree "tree (role) - アクセス可能なリッチ インターネット アプリケーション (WAI-ARIA) 1.1 |W3C"  

> [!NOTE]
> <span data-ttu-id="39942-303">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="39942-303">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="39942-304">元のページ [はここで見](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation) つかり [、Rob Dodson][RobDodson] \(Contributor, Google WebFundamentals\) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="39942-304">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation) and is authored by [Rob Dodson][RobDodson] \(Contributor, Google WebFundamentals\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="39942-306">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="39942-306">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[RobDodson]: https://developers.google.com/web/resources/contributors#rob-dodson  
