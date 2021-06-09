---
description: スクリーン リーダーのような支援テクノロジMicrosoft Edge DevTools のナビゲーションに関するガイド。
title: 支援Microsoft Edge DevTools のナビゲーション
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 2cb57a8ea1ea34506b4698d80ae0981d8716f3d2
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597101"
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
# <a name="navigate-microsoft-edge-devtools-with-assistive-technology"></a><span data-ttu-id="e7451-104">支援Microsoft Edge DevTools のナビゲーション</span><span class="sxs-lookup"><span data-stu-id="e7451-104">Navigate Microsoft Edge DevTools with assistive technology</span></span>  

<span data-ttu-id="e7451-105">この記事では、主にスクリーン リーダーなどの支援テクノロジに依存しているユーザーが[DevTools][MicrosoftEdgeDevtoolsMain]を使用Microsoft Edge役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e7451-105">This article helps users who primarily rely on assistive technology such as screen readers use [Microsoft Edge DevTools][MicrosoftEdgeDevtoolsMain].</span></span>  <span data-ttu-id="e7451-106">DevTools は、ブラウザーに組み込Microsoft Edgeです。</span><span class="sxs-lookup"><span data-stu-id="e7451-106">DevTools is a suite of web developer tools built into the Microsoft Edge browser.</span></span>  

<span data-ttu-id="e7451-107">Web ページのアクセシビリティの向上に関連する [DevTools 機能については、「DevTools][DevtoolsAccessibilityReference] のアクセシビリティ テスト機能」および [「DevTools](accessibility-testing-in-devtools.md)を使用したアクセシビリティ テストの概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7451-107">For DevTools features related to improving the accessibility of a web page, see [Accessibility-testing features in DevTools][DevtoolsAccessibilityReference] and [Overview of accessibility testing using DevTools](accessibility-testing-in-devtools.md).</span></span>

<span data-ttu-id="e7451-108">DevTools のアクセシビリティは、進行中の作業です。</span><span class="sxs-lookup"><span data-stu-id="e7451-108">The accessibility of DevTools is a work-in-progress.</span></span>  <span data-ttu-id="e7451-109">一部のツールとタブは、他のツールよりも支援テクノロジの方が優れた機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="e7451-109">Some tools and tabs work better with assistive technology than others.</span></span>  <span data-ttu-id="e7451-110">このガイドでは、最もアクセスしやすいツールとタブについて説明し、途中で発生する可能性のある特定の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="e7451-110">This guide walks you through the tools and tabs which are the most accessible, and highlights specific issues you may encounter along the way.</span></span>  

## <a name="overview"></a><span data-ttu-id="e7451-111">概要</span><span class="sxs-lookup"><span data-stu-id="e7451-111">Overview</span></span>  

<span data-ttu-id="e7451-112">DevTools は、一連のツールに分かれています。</span><span class="sxs-lookup"><span data-stu-id="e7451-112">DevTools is divided into a series of tools.</span></span>  <span data-ttu-id="e7451-113">(コマンド メニュー **内では**、ツールはパネルと _呼ばれます_。) ツールは、メイン ツールバーと引き出しツール バーの [ARIA][W3CWaiAriaTablist] タブリストに整理されています。</span><span class="sxs-lookup"><span data-stu-id="e7451-113">(Within the **Command Menu**, tools are referred to as _panels_.)  Tools are organized into an [ARIA tablist][W3CWaiAriaTablist] on the main toolbar and on the drawer toolbar.</span></span>

<span data-ttu-id="e7451-114">ツールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e7451-114">The following are examples of tools:</span></span>

*   <span data-ttu-id="e7451-115">要素 **ツール** を使用すると、[DOM ノードの表示と変更][DevtoolsDomIndexNavigateDomTreeKeyboard] または CSS を使用 [できます][DevtoolsCssIndex]。</span><span class="sxs-lookup"><span data-stu-id="e7451-115">The **Elements** tool lets you [view and change DOM nodes][DevtoolsDomIndexNavigateDomTreeKeyboard] or [CSS][DevtoolsCssIndex].</span></span>  
*   <span data-ttu-id="e7451-116">コンソール **ツールを** 使用すると、JavaScript ログとライブ編集オブジェクトを読み取りできます。</span><span class="sxs-lookup"><span data-stu-id="e7451-116">The **Console** tool lets you read JavaScript logs and live-edit objects.</span></span>  <span data-ttu-id="e7451-117">詳細については、「コンソールを使用 [する」に移動します][DevtoolsConsoleIndex]。</span><span class="sxs-lookup"><span data-stu-id="e7451-117">For more information, navigate to [Use the Console][DevtoolsConsoleIndex].</span></span>

<span data-ttu-id="e7451-118">各ツールには、1 つ以上のタブセットがあります。</span><span class="sxs-lookup"><span data-stu-id="e7451-118">Within each tool, there are one or more sets of tabs.</span></span>  <span data-ttu-id="e7451-119">たとえば、要素ツール**には**、スタイル、イベント リスナー、アクセシビリティ**などの**一\*\*\*\* 連のタブ**が含まれています**。</span><span class="sxs-lookup"><span data-stu-id="e7451-119">For example, the **Elements** tool contains a set of tabs including **Styles**, **Event Listeners**, and **Accessibility**.</span></span>

## <a name="keyboard-shortcuts"></a><span data-ttu-id="e7451-120">キーボード ショートカット</span><span class="sxs-lookup"><span data-stu-id="e7451-120">Keyboard shortcuts</span></span>  

<span data-ttu-id="e7451-121">[DevTools キーボード ショートカット リファレンス][DevtoolsShortcuts] は便利なチートシートです。</span><span class="sxs-lookup"><span data-stu-id="e7451-121">The [DevTools Keyboard Shortcuts reference][DevtoolsShortcuts] is a helpful cheat sheet.</span></span>  <span data-ttu-id="e7451-122">異なるツールを探索する場合は、必ずブックマークを作成して参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7451-122">Be sure to bookmark it and refer back to it as you explore the different tools.</span></span>

## <a name="open-devtools"></a><span data-ttu-id="e7451-123">DevTools を開く</span><span class="sxs-lookup"><span data-stu-id="e7451-123">Open DevTools</span></span>  

<span data-ttu-id="e7451-124">開始するには、[Open Microsoft Edge DevTools][DevtoolsOpen] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7451-124">To get started, navigate to [Open Microsoft Edge DevTools][DevtoolsOpen].</span></span>  <span data-ttu-id="e7451-125">キーボード ショートカットまたはメニュー項目を使用して DevTools を開く方法は多数あります。</span><span class="sxs-lookup"><span data-stu-id="e7451-125">There are a number of ways to open DevTools, either through keyboard shortcuts or menu items.</span></span>  

## <a name="navigate-between-tools"></a><span data-ttu-id="e7451-126">ツール間の移動</span><span class="sxs-lookup"><span data-stu-id="e7451-126">Navigate between tools</span></span>

### <a name="navigate-by-keyboard"></a><span data-ttu-id="e7451-127">キーボードによる移動</span><span class="sxs-lookup"><span data-stu-id="e7451-127">Navigate by keyboard</span></span>  

*   <span data-ttu-id="e7451-128">DevTools を開いた `Control` + `]` 後、\(Windows、Linux\) または `Command` + \(macOS\) を選択して、メイン ツールバーの次のツールに `]` フォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="e7451-128">With DevTools open, select `Control`+`]` \(Windows, Linux\) or `Command`+`]` \(macOS\) to move focus to the next tool on the main toolbar.</span></span>
*   <span data-ttu-id="e7451-129">`Control` + `[` \(Windows、Linux\) または `Command` + \(macOS\) を選択して、メイン ツールバーの前の `[` ツールにフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="e7451-129">Select `Control`+`[` \(Windows, Linux\) or `Command`+`[` \(macOS\) to move focus to the previous tool on the main toolbar.</span></span>
*   <span data-ttu-id="e7451-130">メイン ツールバーまたはドロワー ツールバーのタブにフォーカスが移動するまで、または繰り返し選択してから、矢印キーを使用してツール `Tab` `Shift` + `Tab` 間を移動します。</span><span class="sxs-lookup"><span data-stu-id="e7451-130">Select `Tab` or `Shift`+`Tab` repeatedly until focus moves to the tabs of the main toolbar or drawer toolbar, and then use the arrow keys to move among the tools.</span></span>

**<span data-ttu-id="e7451-131">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e7451-131">Known issues</span></span>**  

*   <span data-ttu-id="e7451-132">[コンソール] ツールや\*\*\*\*[\*\*\*\* パフォーマンス] ツールなどの一部のツールは、ツールが選択された時点でツールのコンテンツ領域にフォーカスを移動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="e7451-132">Some tools, such as the **Console** and **Performance** tools, may move focus into the tool's content area as soon as the tool is selected.</span></span>  <span data-ttu-id="e7451-133">これにより、矢印キーによる移動が困難になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e7451-133">This may make navigating by arrow keys difficult.</span></span>  
*   <span data-ttu-id="e7451-134">選択したツールの名前は発表されますが、ツールでフォーカスされたコンテンツを発表した後にのみ発表されます。</span><span class="sxs-lookup"><span data-stu-id="e7451-134">The name of the selected tool is announced, but only after announcing the focused content in the tool.</span></span>  <span data-ttu-id="e7451-135">この一連のアナウンスにより、ツールの名前を簡単に見逃す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e7451-135">This sequence of announcements may make it easy to miss the name of the tool.</span></span>

### <a name="navigate-by-command-menu"></a><span data-ttu-id="e7451-136">[コマンド] メニューで移動する</span><span class="sxs-lookup"><span data-stu-id="e7451-136">Navigate by Command Menu</span></span>  

<span data-ttu-id="e7451-137">特定のツールを選択するには、コマンド メニュー [を使用します][DevtoolsCommandMenuIndex]。</span><span class="sxs-lookup"><span data-stu-id="e7451-137">To select a specific tool, use the [Command Menu][DevtoolsCommandMenuIndex].</span></span>  <span data-ttu-id="e7451-138">コマンド メニューでは、ツールをパネルと呼 _びます_。</span><span class="sxs-lookup"><span data-stu-id="e7451-138">In the Command Menu, a tool is called a _panel_.</span></span>

1.  <span data-ttu-id="e7451-139">DevTools を開いた後 `Control` + `Shift` + `P` 、\(Windows、Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択してコマンド メニューを**開きます**。</span><span class="sxs-lookup"><span data-stu-id="e7451-139">With DevTools open, select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    <span data-ttu-id="e7451-140">コマンド **メニューは** 、ファジー検索オートコンプリート コンボボックスです。</span><span class="sxs-lookup"><span data-stu-id="e7451-140">The **Command Menu** is a fuzzy-search autocomplete combobox.</span></span>  
1.  <span data-ttu-id="e7451-141">パネル (ツール) の名前を入力し、キーボードで正しいオプション `Down Arrow` に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7451-141">Type the name of a panel (tool), and then use the `Down Arrow` on the keyboard to navigate to the correct option.</span></span>  
1.  <span data-ttu-id="e7451-142">コマンド `Enter` を実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="e7451-142">Select `Enter` to run a command.</span></span>  

<span data-ttu-id="e7451-143">要素ツールを **開く** 方法:</span><span class="sxs-lookup"><span data-stu-id="e7451-143">To open the **Elements** tool:</span></span>

1.  <span data-ttu-id="e7451-144">**コマンド メニュー** を開きます。</span><span class="sxs-lookup"><span data-stu-id="e7451-144">Open the **Command Menu**.</span></span>  
1.  <span data-ttu-id="e7451-145">次に `E` 入力 `L` します。</span><span class="sxs-lookup"><span data-stu-id="e7451-145">Type `E` then `L`.</span></span>  <span data-ttu-id="e7451-146">[ **パネル] >要素の表示** ] オプションが選択されています。</span><span class="sxs-lookup"><span data-stu-id="e7451-146">The **Panel > Show Elements** option is selected.</span></span>  
1.  <span data-ttu-id="e7451-147">`Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7451-147">Select `Enter`.</span></span>  

<span data-ttu-id="e7451-148">ツールを開く方法は、ツールのコンテンツ領域にフォーカスを置きます。</span><span class="sxs-lookup"><span data-stu-id="e7451-148">Opening a tool this way puts focus in the content area of the tool.</span></span>  <span data-ttu-id="e7451-149">Elements ツールの場合、 **フォーカス** は DOM ツリーに **移動します**。</span><span class="sxs-lookup"><span data-stu-id="e7451-149">In the case of the **Elements** tool, focus moves into the **DOM Tree**.</span></span>

## <a name="elements-tool"></a><span data-ttu-id="e7451-150">要素ツール</span><span class="sxs-lookup"><span data-stu-id="e7451-150">Elements tool</span></span>

### <a name="inspect-an-element-on-the-page"></a><span data-ttu-id="e7451-151">ページ上の要素を検査する</span><span class="sxs-lookup"><span data-stu-id="e7451-151">Inspect an element on the page</span></span>  

1.  <span data-ttu-id="e7451-152">スクリーン リーダーのカーソルを使用して、検査する要素に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7451-152">Navigate to the element you want to inspect, using the cursor in the screen reader.</span></span>  
1.  <span data-ttu-id="e7451-153">要素を右クリックして、コンテキスト メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="e7451-153">Simulate a right-click on the element, to open the context menu.</span></span>  
1.  <span data-ttu-id="e7451-154">[検査] **オプションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="e7451-154">Choose the **Inspect** option.</span></span>  <span data-ttu-id="e7451-155">この [要素] ツールを開き、DOM ツリー内の要素に焦点を当て、[DevtoolsDomIndexViewDomNodes] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7451-155">This [opens the Elements tool and focuses the element in the DOM Tree][DevtoolsDomIndexViewDomNodes].</span></span>  

<span data-ttu-id="e7451-156">**DOM ツリーは** [ARIA ツリーとしてレイアウトされます][W3CWaiAriaTree]。</span><span class="sxs-lookup"><span data-stu-id="e7451-156">The **DOM Tree** is laid out as an [ARIA tree][W3CWaiAriaTree].</span></span>  <span data-ttu-id="e7451-157">例については、[キーボードを使用して **DOM ツリー** を移動する][DevtoolsDomIndexNavigateDomTreeKeyboard]に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7451-157">For an example, navigate to [Navigate the **DOM Tree** with a keyboard][DevtoolsDomIndexNavigateDomTreeKeyboard].</span></span>  

### <a name="copy-the-code-for-an-element-in-the-dom-tree"></a><span data-ttu-id="e7451-158">DOM ツリー内の要素のコードをコピーする</span><span class="sxs-lookup"><span data-stu-id="e7451-158">Copy the code for an element in the DOM Tree</span></span>  

1.  <span data-ttu-id="e7451-159">**DOM**ツリーのノードにフォーカスを合わせると、ノードにカーソルを合わせると、コンテキスト メニュー \(右クリック\) が開きます。</span><span class="sxs-lookup"><span data-stu-id="e7451-159">With focus on a node in the **DOM Tree**, hover on the node and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="e7451-160">[コピー] **オプションを展開** します。</span><span class="sxs-lookup"><span data-stu-id="e7451-160">Expand the **Copy** option.</span></span>  
1.  <span data-ttu-id="e7451-161">[外部 **HTML のコピー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7451-161">Choose **Copy outerHTML**.</span></span>  

**<span data-ttu-id="e7451-162">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e7451-162">Known issues</span></span>**  

*   <span data-ttu-id="e7451-163">**多くの場合、copy outerHTML** は現在のノードを選択するのではなく、親ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7451-163">**Copy outerHTML** often does not select the current node but instead selects the parent node.</span></span>  <span data-ttu-id="e7451-164">ただし、要素の内容はコピーされた outerHTML に残っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7451-164">However, the contents of the element should still be in the copied outerHTML.</span></span>  

### <a name="modify-the-attributes-of-an-element-in-the-dom-tree"></a><span data-ttu-id="e7451-165">DOM ツリー内の要素の属性を変更する</span><span class="sxs-lookup"><span data-stu-id="e7451-165">Modify the attributes of an element in the DOM Tree</span></span>  

*   <span data-ttu-id="e7451-166">**DOM**ツリーのノードにフォーカスを置き、編集 `Enter` 可能にする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="e7451-166">With focus on a node in the **DOM Tree**, select `Enter` to make it editable.</span></span>  
*   <span data-ttu-id="e7451-167">属性値 `Tab` 間を移動する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="e7451-167">Select `Tab` to move between attribute values.</span></span>  <span data-ttu-id="e7451-168">"スペース" と聞くと、空のテキスト入力の内側に新しい属性値を入力できます。</span><span class="sxs-lookup"><span data-stu-id="e7451-168">When you hear "space" you are inside of an empty text input and are able to type a new attribute value.</span></span>  
*   <span data-ttu-id="e7451-169">`Control` + `Enter` \(Windows、Linux\) または `Command` + \(macOS\) を選択して変更を受け入れ、要素の内容 `Enter` 全体を確認します。</span><span class="sxs-lookup"><span data-stu-id="e7451-169">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\) to accept the change and hear the entire contents of the element.</span></span>  

**<span data-ttu-id="e7451-170">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e7451-170">Known issues</span></span>**  

*   <span data-ttu-id="e7451-171">テキスト入力を入力すると、フィードバックは得かねない。</span><span class="sxs-lookup"><span data-stu-id="e7451-171">When you type into the text input, you get no feedback.</span></span>  <span data-ttu-id="e7451-172">入力ミスを行い、矢印キーを使用して入力を確認すると、フィードバックも得かねない。</span><span class="sxs-lookup"><span data-stu-id="e7451-172">If you make a typo and use the arrow keys to explore your input, you also get no feedback.</span></span>  <span data-ttu-id="e7451-173">作業を確認する最も簡単な方法は、変更を受け入れてから、発表される要素全体をリッスンする方法です。</span><span class="sxs-lookup"><span data-stu-id="e7451-173">The easiest way to check your work is to accept the change, then listen for the entire element to be announced.</span></span>  

### <a name="edit-the-html-of-an-element-in-the-dom-tree"></a><span data-ttu-id="e7451-174">DOM ツリーで要素の HTML を編集する</span><span class="sxs-lookup"><span data-stu-id="e7451-174">Edit the HTML of an element in the DOM Tree</span></span>  

*   <span data-ttu-id="e7451-175">**DOM**ツリーのノードにフォーカスを置き、編集 `Enter` 可能にする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="e7451-175">With focus on a node in the **DOM Tree**, select `Enter` to make it editable.</span></span>  
*   <span data-ttu-id="e7451-176">属性値 `Tab` 間を移動する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="e7451-176">Select `Tab` to move between attribute values.</span></span>  <span data-ttu-id="e7451-177">たとえば、要素の名前が聞こえると、テキスト入力の内部にいて、要素の種類 `h2` が変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e7451-177">When you hear the name of the element, for instance, `h2`, you are inside of a text input and may change the type of the element.</span></span>  
*   <span data-ttu-id="e7451-178">`Control` + `Enter` \(Windows Linux\) または `Command` + `Enter` \(macOS\) を選択して変更を受け入れる。</span><span class="sxs-lookup"><span data-stu-id="e7451-178">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\) to accept the change.</span></span>  

<span data-ttu-id="e7451-179">たとえば `h3` `Control` + `Enter` 、\(Windows、Linux\) または `Command` + `Enter` \(macOS\) を入力して選択すると、要素の開始タグと終了タグが `h3` 変更されます。</span><span class="sxs-lookup"><span data-stu-id="e7451-179">For example, when you type `h3` and select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\), the start and end tags of the `h3` element change.</span></span>  

## <a name="tabs-in-the-elements-tool"></a><span data-ttu-id="e7451-180">[要素] ツールのタブ</span><span class="sxs-lookup"><span data-stu-id="e7451-180">Tabs in the Elements tool</span></span>

<span data-ttu-id="e7451-181">要素 **ツール** には、要素に適用される CSS やアクセシビリティ ツリー内の関連する場所など、その他のタブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7451-181">The **Elements** tool contains additional tabs for inspecting things like the CSS applied to an element or the relevant place in the accessibility tree.</span></span>  

*   <span data-ttu-id="e7451-182">DOM ツリーのノードにフォーカスがある場合 **は、[** スタイル] タブが選択されているという声 `Tab` **が聞こえる** まで選択します。</span><span class="sxs-lookup"><span data-stu-id="e7451-182">With focus on a node in the **DOM Tree**, select `Tab` until you hear that the **Styles** tab is selected.</span></span>  
*   <span data-ttu-id="e7451-183">その他の `Right Arrow` 使用可能なタブを表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e7451-183">Use the `Right Arrow` to explore other available tabs.</span></span>

<span data-ttu-id="e7451-184">**DOM ツリーは**属性を持つ要素をフォーカス可能なリンクに変換します。そのため、[スタイル] ウィンドウに移動するには、複数の要素 `href` を選択 `Tab` する**必要があります**。</span><span class="sxs-lookup"><span data-stu-id="e7451-184">The **DOM Tree** turns elements with `href` attributes into focusable links, so you may need to select `Tab` more than once to reach the **Styles** pane.</span></span>  

**<span data-ttu-id="e7451-185">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e7451-185">Known issues</span></span>**  

<span data-ttu-id="e7451-186">**[DOM ブレークポイント] タブと** **[プロパティ] タブ**はキーボードアクセス可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="e7451-186">The **DOM Breakpoints** and **Properties** tabs are not keyboard-accessible.</span></span>  

### <a name="styles-pane"></a><span data-ttu-id="e7451-187">[スタイル] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="e7451-187">Styles pane</span></span>  

<span data-ttu-id="e7451-188">[スタイル **] ウィンドウで**、スタイルのフィルター処理、要素の状態 \(:active、:focus\など) の切り替え、クラスの切り替え、および新しいクラスの追加のコントロールを検索します。 [][MDNActive] [][MDNFocus]</span><span class="sxs-lookup"><span data-stu-id="e7451-188">In the **Styles** pane find controls for filtering styles, toggling element states \(such as [:active][MDNActive] and [:focus][MDNFocus]\), toggling classes, and adding new classes.</span></span>  <span data-ttu-id="e7451-189">また、DOM ツリーでフォーカスされている要素に現在適用されているスタイルを探索および変更するための強力なスタイル検査ツール **も用意されています**。</span><span class="sxs-lookup"><span data-stu-id="e7451-189">There is also a powerful style inspection tool to explore and modify styles currently applied to the element that is in focus in the **DOM Tree**.</span></span>  

<span data-ttu-id="e7451-190">[スタイル] ウィンドウについて理解\*\*\*\* する重要な概念は、DOM ツリーで現在選択されているノードのスタイルのみを**表示する点です**。</span><span class="sxs-lookup"><span data-stu-id="e7451-190">The key concept to understand about the **Styles** pane is that it only shows styles for the currently-selected node in the **DOM Tree**.</span></span>  <span data-ttu-id="e7451-191">たとえば、ノードのスタイルの検査が完了し、ノードのスタイルを確認 `<header>` すると `<footer>` します。</span><span class="sxs-lookup"><span data-stu-id="e7451-191">For example, suppose you are done inspecting the styles of a `<header>` node, and now you want to look at the styles for a `<footer>` node.</span></span>  <span data-ttu-id="e7451-192">これを行うには、まず DOM ツリーで `<footer>` ノードを選択する **必要があります**。</span><span class="sxs-lookup"><span data-stu-id="e7451-192">To do that, you first need to select the `<footer>` node in the **DOM Tree**.</span></span>  <span data-ttu-id="e7451-193">Inspect ワークフローを使用して[](#inspect-an-element-on-the-page)、DOM ツリーに焦点を当てたノード `footer` \(フッター\内のリンクなど) の一般的な近傍にあるノードを検査し、\*\*\*\* キーボードを使用して目的の正確なノードに移動する方が速い場合があります。</span><span class="sxs-lookup"><span data-stu-id="e7451-193">You may find it faster to use the [Inspect](#inspect-an-element-on-the-page) workflow to inspect a node that is in the general vicinity of the `footer` node \(such as a link within the footer\), which focuses the **DOM Tree**, and then use your keyboard to navigate to the exact node in which you are interested.</span></span>  

#### <a name="navigate-the-styles-pane"></a><span data-ttu-id="e7451-194">[スタイル] ウィンドウを移動する</span><span class="sxs-lookup"><span data-stu-id="e7451-194">Navigate the Styles pane</span></span>  

<span data-ttu-id="e7451-195">すべてのスタイル ツールは、何通りか別の方法で [\*\*\*\* スタイル] ウィンドウに接続されます。このツールの専門家になるのは、まず意味があります。</span><span class="sxs-lookup"><span data-stu-id="e7451-195">Because all of the style tools connect in one way or another back to the **Styles** pane, it makes sense to become an expert in this tool first.</span></span>  

*   <span data-ttu-id="e7451-196">[スタイル] ウィンドウに **フォーカスを置** いて、フォーカス `Tab` を内側に移動し、コンテンツを確認します。</span><span class="sxs-lookup"><span data-stu-id="e7451-196">With focus on the **Styles** pane, select `Tab` to move focus inside and explore the contents.</span></span>  
*   <span data-ttu-id="e7451-197">最初 `Tab` のスタイルがアクティブになるまで選択します。</span><span class="sxs-lookup"><span data-stu-id="e7451-197">Select `Tab` until the first style becomes active.</span></span>  <span data-ttu-id="e7451-198">スクリーン リーダーを使用している場合、この最初のスタイルはとして発表されます `element.style {}` 。</span><span class="sxs-lookup"><span data-stu-id="e7451-198">If you are using a screen reader this first style is announced as `element.style {}`.</span></span>  
*   <span data-ttu-id="e7451-199">スタイル `Down Arrow` の一覧を特定の順序で移動する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="e7451-199">Select `Down Arrow` to navigate the list of styles in order of specificity.</span></span>  <span data-ttu-id="e7451-200">スクリーン リーダーは、CSS ファイルの名前、スタイルが表示される行番号、およびスタイルの名前から始まる各スタイルをアナウンスします。</span><span class="sxs-lookup"><span data-stu-id="e7451-200">A screen reader announces each style starting with the name of the CSS file, the line number on which the style appears, and the name of the style.</span></span>  <span data-ttu-id="e7451-201">例: `main.css:233 .card__img {}`。</span><span class="sxs-lookup"><span data-stu-id="e7451-201">For example, `main.css:233 .card__img {}`.</span></span>  
*   <span data-ttu-id="e7451-202">スタイル `Enter` の詳細を調べている場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="e7451-202">Select `Enter` to inspect a style in more detail.</span></span>  <span data-ttu-id="e7451-203">フォーカスは、スタイル名の編集可能なバージョンから始まります。</span><span class="sxs-lookup"><span data-stu-id="e7451-203">Focus begins on an editable version of the style name.</span></span>  
*   <span data-ttu-id="e7451-204">各 `Tab` CSS プロパティの編集可能なバージョンと対応する値の間を移動する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="e7451-204">Select `Tab` to move between editable versions of each CSS property and the corresponding values.</span></span>  <span data-ttu-id="e7451-205">各スタイル ブロックの末尾には、空白の編集可能なテキスト フィールドが表示され、追加の CSS プロパティを追加できます。</span><span class="sxs-lookup"><span data-stu-id="e7451-205">At the end of each style block is a blank editable text field which you can use to add additional CSS properties.</span></span>  
*   <span data-ttu-id="e7451-206">引き続き選択してスタイルの一覧を移動するか、モードを終了して矢印キーでナビゲーション `Tab` `Escape` に戻ります。</span><span class="sxs-lookup"><span data-stu-id="e7451-206">You can continue to select `Tab` to move through the list of styles, or select `Escape` to exit the mode and go back to navigating by arrow keys.</span></span>  

<span data-ttu-id="e7451-207">追加のショートカットについては、[スタイル ウィンドウ キーボード リファレンス][DevtoolsShortcutsStylesPaneKeyboard]に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7451-207">For additional shortcuts, navigate to [Styles pane keyboard reference][DevtoolsShortcutsStylesPaneKeyboard].</span></span>  

**<span data-ttu-id="e7451-208">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e7451-208">Known issues</span></span>**  

*   <span data-ttu-id="e7451-209">[編集可能なテキストの **フィルター]** フィールドを使用すると、スタイルの一覧を移動できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e7451-209">If you use the **Filter** editable text field, you are no longer be able to navigate the list of styles.</span></span>  

#### <a name="toggle-element-state"></a><span data-ttu-id="e7451-210">要素の状態を切り替える</span><span class="sxs-lookup"><span data-stu-id="e7451-210">Toggle element state</span></span>  

<span data-ttu-id="e7451-211">要素の状態を切り替えるには、次のように `:active` します `:focus` 。</span><span class="sxs-lookup"><span data-stu-id="e7451-211">To toggle the state of an element, such as `:active` or `:focus`:</span></span>  

1.  <span data-ttu-id="e7451-212">[スタイル] ウィンドウ **に移動** し、[要素 `Tab` の状態の切り替え] ボタンがフォーカスを **持つまで** 選択します。</span><span class="sxs-lookup"><span data-stu-id="e7451-212">Navigate to the **Styles** pane and select `Tab` until the **Toggle Element State** button has focus.</span></span>  
1.  <span data-ttu-id="e7451-213">要素 `Enter` の状態のコレクションを展開する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="e7451-213">Select `Enter` to expand the collection of element states.</span></span>  <span data-ttu-id="e7451-214">要素の状態は、チェック ボックスのグループとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7451-214">The element states are presented as a group of checkboxes.</span></span>  
1.  <span data-ttu-id="e7451-215">最初 `Tab` の状態がフォーカスを `:active` 持つまで選択します。</span><span class="sxs-lookup"><span data-stu-id="e7451-215">Select `Tab` until the first state, `:active`, has focus.</span></span>  
1.  <span data-ttu-id="e7451-216">有効 `Space` にする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="e7451-216">Select `Space` to enable it.</span></span>  <span data-ttu-id="e7451-217">DOM ツリーで現在選択されている要素にスタイルがある場合は `:active` 、そのスタイルが適用されます。</span><span class="sxs-lookup"><span data-stu-id="e7451-217">If the currently-selected element in the DOM Tree has an `:active` style, it is now applied.</span></span>  
1.  <span data-ttu-id="e7451-218">ホールド `Tab` して、使用可能なすべての状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="e7451-218">Hold `Tab` to explore all of the available states.</span></span>  

#### <a name="add-an-existing-class"></a><span data-ttu-id="e7451-219">既存のクラスを追加する</span><span class="sxs-lookup"><span data-stu-id="e7451-219">Add an existing class</span></span>  

<span data-ttu-id="e7451-220">[要素の状態の **切り替え] ボタン** の隣には、[ **要素クラス] ボタン** があります。</span><span class="sxs-lookup"><span data-stu-id="e7451-220">Adjacent to the **Toggle Element State** button is the **Element Classes** button.</span></span>  <span data-ttu-id="e7451-221">フォーカスを移動するには、を選択 `Tab` して選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="e7451-221">To move the focus to it, select `Tab` and then select `Enter`.</span></span>  <span data-ttu-id="e7451-222">[新しいクラスの追加] というラベルの付いた編集テキスト フィールド **にフォーカスが移動します**。</span><span class="sxs-lookup"><span data-stu-id="e7451-222">Focus moves into an edit text field labeled **Add new class**.</span></span>  

<span data-ttu-id="e7451-223">[ **要素クラス]** ボタンは、主に要素に既存のクラスを追加するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7451-223">The **Element Classes** button is primarily used for adding existing classes to an element.</span></span>  <span data-ttu-id="e7451-224">たとえば、スタイルシートにヘルパー クラスという名前のヘルパー クラスが含まれている場合は、編集テキスト フィールドの内部を選択して、クラスの候補リストを表示し、 を使用して候補を `.clearfix` `.` `Down Arrow` 検索 `.clearfix` できます。</span><span class="sxs-lookup"><span data-stu-id="e7451-224">For example, if your stylesheet contained a helper class named `.clearfix`, you can select `.` inside of the edit text field to display a suggestion list of classes and use the `Down Arrow` to find the `.clearfix` suggestion.</span></span>  <span data-ttu-id="e7451-225">または、自分でクラス名を入力し、適用 `Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7451-225">Or type the class name out yourself and select `Enter` to apply it.</span></span>  

#### <a name="add-a-new-style-rule"></a><span data-ttu-id="e7451-226">新しいスタイル ルールを追加する</span><span class="sxs-lookup"><span data-stu-id="e7451-226">Add a new style rule</span></span>  

<span data-ttu-id="e7451-227">[要素クラス] **ボタンの隣** には、[新しいスタイル **ルール] ボタン** があります。</span><span class="sxs-lookup"><span data-stu-id="e7451-227">Adjacent to the **Element Classes** button is the **New Style Rule** button.</span></span>  <span data-ttu-id="e7451-228">フォーカスを移動するには、を選択 `Tab` して選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="e7451-228">To move the focus to it, select `Tab` and then select `Enter`.</span></span>  <span data-ttu-id="e7451-229">フォーカスは、スタイル インスペクター内の編集可能なテキスト フィールドに移動します。</span><span class="sxs-lookup"><span data-stu-id="e7451-229">Focus moves into an editable text field inside of the style inspector.</span></span>  <span data-ttu-id="e7451-230">フィールドの最初のテキストコンテンツは **、DOM**ツリーで選択されている要素のタグ名です。</span><span class="sxs-lookup"><span data-stu-id="e7451-230">The initial text content of the field is the tag name of the element that is selected in the **DOM Tree**.</span></span>  
<span data-ttu-id="e7451-231">このフィールドに任意のクラス名を入力し、CSS プロパティを割り当 `Tab` てる場合に選択できます。</span><span class="sxs-lookup"><span data-stu-id="e7451-231">You can type any class name you want into this field and then select `Tab` to assign CSS properties to it.</span></span>  

### <a name="computed-tab"></a><span data-ttu-id="e7451-232">[計算] タブ</span><span class="sxs-lookup"><span data-stu-id="e7451-232">Computed tab</span></span>  

<span data-ttu-id="e7451-233">[計算] タブに **フォーカスを置** いて、フォーカス `Tab` を内部に移動し、コンテンツを探索する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="e7451-233">With focus on the **Computed** tab, select `Tab` to move focus inside and explore the contents.</span></span>  <span data-ttu-id="e7451-234">[計算 **] タブ** には、特定の順序で要素に実際に適用される CSS プロパティを確認するコントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="e7451-234">Within the **Computed** tab there are controls for exploring which CSS properties are actually applied to an element in order of specificity.</span></span>  

<!--todo: add Computed tab section when available  -->  

#### <a name="explore-all-computed-styles"></a><span data-ttu-id="e7451-235">すべての計算スタイルを見る</span><span class="sxs-lookup"><span data-stu-id="e7451-235">Explore all computed styles</span></span>  

<span data-ttu-id="e7451-236">計算 `Tab` されたスタイルのコレクションに到達するまで選択します。</span><span class="sxs-lookup"><span data-stu-id="e7451-236">Select `Tab` until you reach the collection of computed styles.</span></span>  <span data-ttu-id="e7451-237">これらは ARIA ツリー [として表示されます][W3CWaiAriaTree]。</span><span class="sxs-lookup"><span data-stu-id="e7451-237">These are presented as an [ARIA tree][W3CWaiAriaTree].</span></span>  <span data-ttu-id="e7451-238">リスト ボックスを展開すると、計算されたスタイルを適用している CSS セレクターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7451-238">Expanding a listbox reveals which CSS selectors are applying the computed style.</span></span>  <span data-ttu-id="e7451-239">これらのセレクターは、固有の構成で構成されます。</span><span class="sxs-lookup"><span data-stu-id="e7451-239">These selectors are organized by specificity.</span></span>  <span data-ttu-id="e7451-240">スクリーン リーダーは、計算された値、現在一致している CSS セレクター、セレクターを含むスタイルシートのファイル名、およびセレクターの行番号をアナウンスします。</span><span class="sxs-lookup"><span data-stu-id="e7451-240">A screen reader announces the computed value, which CSS selector is currently matching, the filename of the stylesheet that contains the selector, and the line number for the selector.</span></span>  

**<span data-ttu-id="e7451-241">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e7451-241">Known issues</span></span>**  

*   <span data-ttu-id="e7451-242">[フィルター] テキスト **フィールドを** 使用すると、スタイルを検査できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e7451-242">If you use the **Filter** text field, you are no longer able to inspect styles.</span></span>  

### <a name="event-listeners-tab"></a><span data-ttu-id="e7451-243">[イベント リスナー] タブ</span><span class="sxs-lookup"><span data-stu-id="e7451-243">Event Listeners tab</span></span>  

<span data-ttu-id="e7451-244">要素に適用されるイベント リスナーを調べたい場合は、[要素\*\*\*\*] ツールを選択し\*\*\*\*、[イベント リスナー] タブ ([スタイル] タブでグループ化)**を選択**します。</span><span class="sxs-lookup"><span data-stu-id="e7451-244">To inspect the event listeners that are applied to an element, select the **Elements** tool and then select the **Event Listeners** tab (grouped with the **Styles** tab).</span></span>

#### <a name="explore-event-listeners"></a><span data-ttu-id="e7451-245">イベント リスナーの探索</span><span class="sxs-lookup"><span data-stu-id="e7451-245">Explore event listeners</span></span>  

<span data-ttu-id="e7451-246">イベント リスナーは [ARIA ツリーとして表示されます][W3CWaiAriaTree]。</span><span class="sxs-lookup"><span data-stu-id="e7451-246">Event listeners are presented as an [ARIA tree][W3CWaiAriaTree].</span></span>  <span data-ttu-id="e7451-247">矢印キーを使用して移動できます。</span><span class="sxs-lookup"><span data-stu-id="e7451-247">You can use the arrow keys to navigate them.</span></span>  <span data-ttu-id="e7451-248">スクリーン リーダーは、イベント リスナーが接続されている DOM オブジェクトの名前と、イベント リスナーが定義されているファイル名と行番号をアナウンスします。</span><span class="sxs-lookup"><span data-stu-id="e7451-248">A screen reader announces the name of the DOM object that the event listener is attached to, as well as the file name where the event listener is defined and the line number.</span></span>  

### <a name="accessibility-tab"></a><span data-ttu-id="e7451-249">[アクセシビリティ] タブ</span><span class="sxs-lookup"><span data-stu-id="e7451-249">Accessibility tab</span></span>

<span data-ttu-id="e7451-250">要素ツール `Tab` の [アクセシビリティ]\*\*\*\* タブ内で移動するキーを**選択**します。</span><span class="sxs-lookup"><span data-stu-id="e7451-250">Select the `Tab` key to move around within the **Accessibility** tab in the **Elements** tool.</span></span>

<span data-ttu-id="e7451-251">[ **アクセシビリティ] タブ** は、[スタイル] タブ **の近** くに表示されます。[アクセシビリティ] タブには、アクセシビリティ ツリー、要素に適用される ARIA 属性、および計算されたアクセシビリティ プロパティを探索するコントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="e7451-251">The **Accessibility** tab is near the **Styles** tab. On the Accessibility tab, there are controls for exploring the accessibility tree, the ARIA attributes applied to an element, and the computed accessibility properties.</span></span>  <span data-ttu-id="e7451-252">詳細については、[アクセシビリティ] タブを [使用してアクセシビリティをテストするに移動します][DevtoolsAccessibilityTab]。</span><span class="sxs-lookup"><span data-stu-id="e7451-252">For more information, navigate to [Test accessibility using the Accessibility tab][DevtoolsAccessibilityTab].</span></span>

#### <a name="accessibility-tree"></a><span data-ttu-id="e7451-253">アクセシビリティ ツリー</span><span class="sxs-lookup"><span data-stu-id="e7451-253">Accessibility Tree</span></span>  

<span data-ttu-id="e7451-254">アクセシビリティ **ツリーは ARIA** ツリーとして表示され、 [各][W3CWaiAriaTree] ツリーは DOM 内の `treeitem` 要素に対応します。</span><span class="sxs-lookup"><span data-stu-id="e7451-254">The **Accessibility Tree** is presented as an [ARIA tree][W3CWaiAriaTree] where each `treeitem` corresponds to an element in the DOM.</span></span>  <span data-ttu-id="e7451-255">ツリーは、選択したノードの計算された役割をアナウンスします。</span><span class="sxs-lookup"><span data-stu-id="e7451-255">The tree announces the computed role for the selected node.</span></span>  <span data-ttu-id="e7451-256">ツリー内の `div` `span` "GenericContainer" のような汎用的な要素が発表されます。</span><span class="sxs-lookup"><span data-stu-id="e7451-256">Generic elements like `div` and `span` are announced as "GenericContainer" in the tree.</span></span>  <span data-ttu-id="e7451-257">矢印キーを使用してツリーを走査し、親子関係を探索します。</span><span class="sxs-lookup"><span data-stu-id="e7451-257">Use the arrow keys to traverse the tree and explore parent-child relationships.</span></span>  

**<span data-ttu-id="e7451-258">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e7451-258">Known issues</span></span>**  

*   <span data-ttu-id="e7451-259">[アクセシビリティ][タブで使用][W3CWaiAriaTree]される\*\*\*\* ARIA ツリーの種類は、VoiceOver のような macOS スクリーン リーダー Microsoft Edgeで適切に公開されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e7451-259">The type of [ARIA tree][W3CWaiAriaTree] used by the **Accessibility** tab may not be properly exposed in Microsoft Edge for macOS screen readers like VoiceOver.</span></span>  <span data-ttu-id="e7451-260">この問題[Chromium進捗#868480][ChromiumIssues868480]通知を受け取る場合は、この問題を購読してください。</span><span class="sxs-lookup"><span data-stu-id="e7451-260">Subscribe to [Chromium issue #868480][ChromiumIssues868480] to be informed about progress on this issue.</span></span>  
*   <span data-ttu-id="e7451-261">**[ARIA 属性**]\*\*\*\* セクションと [計算されたプロパティ] セクションのそれぞれは[ARIA][W3CWaiAriaTree]ツリーとしてマークされますが、それぞれが現在フォーカス管理を行っているのではなく、キーボード操作可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="e7451-261">Each of the **ARIA Attributes** and **Computed Properties** sections are marked up as an [ARIA tree][W3CWaiAriaTree], but each does not currently have focus management and is not keyboard operable.</span></span>  

## <a name="lighthouse-tool"></a><span data-ttu-id="e7451-262">ライトハウス ツール</span><span class="sxs-lookup"><span data-stu-id="e7451-262">Lighthouse tool</span></span>

<span data-ttu-id="e7451-263">**ライト** ハウスはサイトに対して一連のテストを実行し、パフォーマンス、アクセシビリティ、SEO、その他の多くのカテゴリに関連する一般的な問題を確認します。</span><span class="sxs-lookup"><span data-stu-id="e7451-263">**Lighthouse** runs a series of tests against a site to check for common issues related to performance, accessibility, SEO, and a number of other categories.</span></span>  

### <a name="configure-and-generate-a-report"></a><span data-ttu-id="e7451-264">レポートの構成と生成</span><span class="sxs-lookup"><span data-stu-id="e7451-264">Configure and generate a report</span></span>

1.  <span data-ttu-id="e7451-265">DevTools **で** ライトハウス ツールが最初に開かれると、[レポートの生成] ボタンにフォーカス **が置** きます。</span><span class="sxs-lookup"><span data-stu-id="e7451-265">When the **Lighthouse** tool is first opened in DevTools, focus is placed on the **Generate report** button.</span></span>  <span data-ttu-id="e7451-266">既定では、フォームは、シミュレートされた 3G 接続でモバイル エミュレーションを使用してすべてのカテゴリのレポートを実行するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="e7451-266">By default, the form is configured to run reports for every category using mobile emulation on a simulated 3G connection.</span></span>  
1.  <span data-ttu-id="e7451-267">レポートの設定を変更するには、ライトハウスの設定にフォーカスを当てたり、ブラウズ `Shift` + `Tab` モードで戻って移動したりします。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e7451-267">To change the report settings, use `Shift`+`Tab` to put focus on **Lighthouse settings**, or navigate back in Browse mode.</span></span>  
1.  <span data-ttu-id="e7451-268">レポートを実行する準備ができたら、[レポートの生成] ボタンに戻 **り、** を選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="e7451-268">When you are ready to run the report, navigate back to the **Generate report** button and select `Enter`.</span></span>  
1.  <span data-ttu-id="e7451-269">フォーカスは、監査を終了できる **[キャンセル** ] ボタンを使用してモーダル ウィンドウに移動します。</span><span class="sxs-lookup"><span data-stu-id="e7451-269">Focus moves into a modal window with a **Cancel** button which allows you to exit the audit.</span></span>  <span data-ttu-id="e7451-270">監査が実行され、ページが複数回更新されると、一連の耳鳴り音が聞こえる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e7451-270">You may hear a series of earcons as the audit runs and refreshes the page multiple times.</span></span>  

**<span data-ttu-id="e7451-271">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e7451-271">Known issues</span></span>**  

*   <span data-ttu-id="e7451-272">構成フォームの異なるセクションは、現在要素でマーク `fieldset` 付けされていない。</span><span class="sxs-lookup"><span data-stu-id="e7451-272">The different sections of the configuration form are not currently marked up with a `fieldset` element.</span></span>  <span data-ttu-id="e7451-273">参照モードで移動して、各セクションに関連付けられているコントロールを把握する方が簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="e7451-273">It may be easier to navigate them in Browse mode to figure out which controls are associated with each section.</span></span>  
*   <span data-ttu-id="e7451-274">監査の実行が完了すると、耳コンやライブ領域のアナウンスはありません。</span><span class="sxs-lookup"><span data-stu-id="e7451-274">There is no earcon or live region announcement when the audit is finished running.</span></span>  <span data-ttu-id="e7451-275">通常、監査には約 30 秒かかっています。その後、結果に移動できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7451-275">Generally the audit takes about 30 seconds, after which you should be able to navigate to the results.</span></span>  <span data-ttu-id="e7451-276">ブラウズ モードを使用すると、結果に最も簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e7451-276">Using Browse mode may be the easiest way to reach the results.</span></span>  

### <a name="navigate-the-lighthouse-report"></a><span data-ttu-id="e7451-277">ライトハウス レポートを移動する</span><span class="sxs-lookup"><span data-stu-id="e7451-277">Navigate the Lighthouse report</span></span>  

<span data-ttu-id="e7451-278">ライトハウス レポートは、各監査カテゴリに対応するセクションに編成されます。</span><span class="sxs-lookup"><span data-stu-id="e7451-278">The Lighthouse report is organized into sections that correspond with each of the audit categories.</span></span>  <span data-ttu-id="e7451-279">レポートが開き、各カテゴリのスコアの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7451-279">The report opens with a list of scores for each category.</span></span>  <span data-ttu-id="e7451-280">これらのスコアは、関連するセクションにスキップするために使用できるリンクです。</span><span class="sxs-lookup"><span data-stu-id="e7451-280">These scores are also links which you can use to skip to the relevant sections.</span></span>  <span data-ttu-id="e7451-281">各セクション内には、渡された監査または失敗した監査に関連する情報を含む拡張可能 `details` な要素があります。</span><span class="sxs-lookup"><span data-stu-id="e7451-281">Within each section are expandable `details` elements, which contain information relating to passed or failed audits.</span></span>  <span data-ttu-id="e7451-282">既定では、失敗した監査だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7451-282">By default, only failing audits are shown.</span></span>  <span data-ttu-id="e7451-283">各セクションは、渡された `details` 監査のすべてが含まれる最終的な要素で終わります。</span><span class="sxs-lookup"><span data-stu-id="e7451-283">Each section ends with a final `details` element which contains all of the passed audits.</span></span>  

<span data-ttu-id="e7451-284">新しい監査を実行するには、レポート `Shift` + `Tab` を終了し、[レポートの生成] ボタン**を選択**します。</span><span class="sxs-lookup"><span data-stu-id="e7451-284">To run a new audit, use `Shift`+`Tab` to exit the report and select the **Generate report** button.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="e7451-285">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="e7451-285">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  
[DevtoolsAccessibilityReference]: reference.md "DevTools |Microsoft Docs"  
[DevtoolsAccessibilityTab]: accessibility-tab.md "[アクセシビリティ] タブを使用してアクセシビリティをテスト|Microsoft Docs"  
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
> <span data-ttu-id="e7451-304">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="e7451-304">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="e7451-305">元のページ [はここで見](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation) つかり [、Rob Dodson][RobDodson] \(Contributor, Google WebFundamentals\) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="e7451-305">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation) and is authored by [Rob Dodson][RobDodson] \(Contributor, Google WebFundamentals\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="e7451-307">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="e7451-307">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[RobDodson]: https://developers.google.com/web/resources/contributors#rob-dodson  
