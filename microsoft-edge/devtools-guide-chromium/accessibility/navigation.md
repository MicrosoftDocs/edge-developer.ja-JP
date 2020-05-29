---
title: Microsoft Edge の DevTools を支援技術でナビゲートする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 5de27e46d20957a1be79f72cf36074291566e6e5
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569112"
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





# <span data-ttu-id="0ad87-103">Microsoft Edge の DevTools を支援技術でナビゲートする</span><span class="sxs-lookup"><span data-stu-id="0ad87-103">Navigate Microsoft Edge DevTools With Assistive Technology</span></span>   



<span data-ttu-id="0ad87-104">このガイドでは、スクリーンリーダーアクセスなどの支援技術に主に依存しているユーザーが、Microsoft Edge DevTools を使用できるようにすることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="0ad87-104">This guide aims to help users who primarily rely on assistive technology like screen readers access and use Microsoft Edge DevTools.</span></span>  <span data-ttu-id="0ad87-105">Microsoft Edge DevTools は、Microsoft Edge ブラウザーに組み込まれた web 開発者ツールのスイートです。</span><span class="sxs-lookup"><span data-stu-id="0ad87-105">Microsoft Edge DevTools is a suite of web developer tools built into the Microsoft Edge browser.</span></span>  <!--See [Accessibility Reference][DevtoolsAccessibilityReference] if you are looking for DevTools features related to improving the accessibility of a web page.  -->

<!--todo: add edge devtools index section when available  -->  
<!--todo: add reference (Accessibility Reference) section when available  -->  

<span data-ttu-id="0ad87-106">DevTools のアクセシビリティは、進行中の作業です。</span><span class="sxs-lookup"><span data-stu-id="0ad87-106">The accessibility of DevTools is a work-in-progress.</span></span>  <span data-ttu-id="0ad87-107">一部のパネルとタブは、他の支援技術よりも機能が向上します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-107">Some panels and tabs work better with assistive technology than others.</span></span>  <span data-ttu-id="0ad87-108">このガイドでは、最もアクセシビリティの高いパネルと、そのような問題が発生する可能性のある特定の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-108">This guide walks you through the panels which are the most accessible and highlights specific issues you may encounter along the way.</span></span>  

## <span data-ttu-id="0ad87-109">概要</span><span class="sxs-lookup"><span data-stu-id="0ad87-109">Overview</span></span>   

<span data-ttu-id="0ad87-110">開始する前に、DevTools UI がどのように構成されるかを、メンタルモデルで把握することができます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-110">Before starting, it helps to have a mental model of how the DevTools UI is structured.</span></span>  <span data-ttu-id="0ad87-111">DevTools は、 [ARIA `tablist` ][W3CWaiAriaTablist]に分類される一連のパネルに分かれています。</span><span class="sxs-lookup"><span data-stu-id="0ad87-111">DevTools is divided into a series of panels which are organized into an [ARIA `tablist`][W3CWaiAriaTablist].</span></span>  

<span data-ttu-id="0ad87-112">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-112">For example:</span></span>  

*   <span data-ttu-id="0ad87-113">[**要素**] パネルでは、DOM ノードの表示と変更、[CSS] [DevtoolsCssIndex] の表示と変更ができます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-113">The **Elements** panel lets you view and change DOM nodes or [CSS][DevtoolsCssIndex].</span></span>  
*   <span data-ttu-id="0ad87-114">[**コンソール**パネル] の [DevtoolsConsoleIndex] では、JavaScript ログとライブ編集オブジェクトを読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-114">The [**Console** panel][DevtoolsConsoleIndex] lets you read JavaScript logs and live edit objects.</span></span>  

<!--todo:  add dom nodes (dom nodes) section when available  -->  

<span data-ttu-id="0ad87-115">各パネルの [コンテンツ] 領域には、さまざまなツールがあります。ドキュメント内のタブまたはウィンドウと呼ばれることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-115">Within the content area of each panel, there are a number of different tools, often referred to as tabs or panes in the documentation.</span></span>  
<span data-ttu-id="0ad87-116">たとえば、[**要素**] パネルには、イベントリスナー、アクセシビリティツリーなどを検査するための追加のタブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0ad87-116">For instance, the **Elements** panel contains additional tabs to inspect event listeners, the accessibility tree, and much more.</span></span>  <span data-ttu-id="0ad87-117">タブとウィンドウの区別は、任意の方法で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-117">The distinction between tabs and panes is somewhat arbitrary.</span></span>  <span data-ttu-id="0ad87-118">1つの用語が表示される唯一の理由は、公式な DevTools のドキュメントの残りの部分との一貫性を維持することです。</span><span class="sxs-lookup"><span data-stu-id="0ad87-118">The only reason you may see one term or the other is to maintain consistency with the rest of the official DevTools documentation.</span></span>  

## <span data-ttu-id="0ad87-119">キーボード ショートカット</span><span class="sxs-lookup"><span data-stu-id="0ad87-119">Keyboard shortcuts</span></span>   

<span data-ttu-id="0ad87-120">[DevTools のショートカットキーリファレンス] [devtools キーボードショートカット] は、役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-120">The [DevTools Keyboard Shortcuts reference][DevtoolsShortcuts] is a helpful cheatsheet.</span></span>  <span data-ttu-id="0ad87-121">ブックマークを作成して、さまざまなパネルを見ながら確認してください。</span><span class="sxs-lookup"><span data-stu-id="0ad87-121">Be sure to bookmark it and refer back to it as you explore the different panels.</span></span>  

## <span data-ttu-id="0ad87-122">DevTools を開く</span><span class="sxs-lookup"><span data-stu-id="0ad87-122">Open DevTools</span></span>   

<span data-ttu-id="0ad87-123">はじめに、[Microsoft Edge DevTools を開く]、[DevTools Open] の順に読みます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-123">To get started, read through [Open Microsoft Edge DevTools][DevtoolsOpen].</span></span>  <span data-ttu-id="0ad87-124">開発ツールを開くには、キーボードショートカットまたはメニュー項目を使用する方法がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-124">There are a number of ways to open DevTools, either through keyboard shortcuts or menu items.</span></span>  

## <span data-ttu-id="0ad87-125">パネル間を移動する</span><span class="sxs-lookup"><span data-stu-id="0ad87-125">Navigate between panels</span></span>   

### <span data-ttu-id="0ad87-126">キーボードを使用して移動する</span><span class="sxs-lookup"><span data-stu-id="0ad87-126">Navigate by keyboard</span></span>   

*   <span data-ttu-id="0ad87-127">Devtools を開いて、 `Control` + `]` 次のパネルにフォーカスするには、\ (Windows \) または `Command` + `]` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-127">With DevTools open, press `Control`+`]` \(Windows\) or `Command`+`]` \(macOS\) to focus the next panel.</span></span>  
*   <span data-ttu-id="0ad87-128">`Control` + `[` 前のパネルにフォーカスするには、\ (Windows \) または `Command` + `[` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-128">Press `Control`+`[` \(Windows\) or `Command`+`[` \(macOS\) to focus the previous panel.</span></span>  
*   <span data-ttu-id="0ad87-129">また、 `Shift` + `Tab` パネルの[ `tablist` ARIA][W3CWaiAriaTablist]にフォーカスを移動したり、方向キーを使ってパネルを変更したりすることもできますが、前に説明したショートカットキーを使う方が速い場合もあります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-129">It is also possible to use `Shift`+`Tab` to move focus into the [ARIA `tablist`][W3CWaiAriaTablist] of a panel and use the arrow keys to change panels, though it may be faster to use the previously mentioned shortcuts.</span></span>  

#### <span data-ttu-id="0ad87-130">既知の問題</span><span class="sxs-lookup"><span data-stu-id="0ad87-130">Known issues</span></span>   

*   <span data-ttu-id="0ad87-131">**コンソール**や**パフォーマンス**パネルなどの一部のパネルでは、アクティブ化されるとすぐに、コンテンツ領域にフォーカスが移動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-131">Some panels, such as the **Console** and **Performance** panels, may move focus into their content area as soon as they are activated.</span></span>  <span data-ttu-id="0ad87-132">これにより、方向キーによる移動が困難になることがあります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-132">This may make navigating by arrow keys difficult.</span></span>  
*   <span data-ttu-id="0ad87-133">選択したパネルの名前はアナウンスされますが、パネル内のフォーカスコンテンツを読み取った後にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-133">The name of the selected panel is announced, but only after it has read the focused content in the panel.</span></span>  <span data-ttu-id="0ad87-134">これにより、簡単に見逃してしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-134">This may make it very easy to miss.</span></span>  

### <span data-ttu-id="0ad87-135">[コマンドによる移動] メニュー</span><span class="sxs-lookup"><span data-stu-id="0ad87-135">Navigate by Command Menu</span></span>   

<span data-ttu-id="0ad87-136">特定のパネルにフォーカスを移動するには、[**コマンドメニュー] [Dev[コマンド] メニュー**インデックス] を使います。</span><span class="sxs-lookup"><span data-stu-id="0ad87-136">To focus a specific panel, use the [**Command Menu**][DevtoolsCommandMenuIndex]:</span></span>  

1.  <span data-ttu-id="0ad87-137">Devtools を開いている状態で、 `Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押して**コマンドメニュー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-137">With DevTools open, press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    <span data-ttu-id="0ad87-138">**コマンドメニュー**は、ファジー検索オートコンプリートのコンボボックスです。</span><span class="sxs-lookup"><span data-stu-id="0ad87-138">The **Command Menu** is a fuzzy search autocomplete combobox.</span></span>  
1.  <span data-ttu-id="0ad87-139">開こうとしているパネルの名前を入力し、キーボードのを使用して `Down Arrow` 適切なオプションに移動します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-139">Type the name of the panel you want to open, then use the `Down Arrow` on the keyboard to navigate to the correct option.</span></span>  
1.  <span data-ttu-id="0ad87-140">キーを押して `Enter` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-140">Press `Enter` to run a command.</span></span>  

<span data-ttu-id="0ad87-141">たとえば、次のように**要素**パネルを開くには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="0ad87-141">For example, to open the **Elements** panel:</span></span>  

1.  <span data-ttu-id="0ad87-142">**コマンドメニュー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-142">Open the **Command Menu**.</span></span>  
1.  <span data-ttu-id="0ad87-143">入力 `E` し `L` ます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-143">Type `E` then `L`.</span></span>  <span data-ttu-id="0ad87-144">[要素の表示] オプションが選択されている**パネル >** ます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-144">The **Panel > Show Elements** option is selected.</span></span>  
1.  <span data-ttu-id="0ad87-145">キーを押して、 `Enter` パネルを開くコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-145">Press `Enter` to run the command that opens the panel.</span></span>  

<span data-ttu-id="0ad87-146">この方法でパネルを開くと、フォーカスはパネルのコンテンツに移動します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-146">Opening a panel this way directs focus to the contents of the panel.</span></span>  <span data-ttu-id="0ad87-147">[**要素**] パネルの場合は、[ **DOM] ツリー**にフォーカスが移動します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-147">In the case of the **Elements** panel, focus moves into the **DOM Tree**.</span></span>  

## <span data-ttu-id="0ad87-148">要素パネル</span><span class="sxs-lookup"><span data-stu-id="0ad87-148">Elements panel</span></span>   

### <span data-ttu-id="0ad87-149">ページ上の要素を検査する</span><span class="sxs-lookup"><span data-stu-id="0ad87-149">Inspect an element on the page</span></span>   

1.  <span data-ttu-id="0ad87-150">スクリーンリーダーでカーソルを使って検査する要素に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-150">Navigate to the element you want to inspect using the cursor in the screen reader.</span></span>  
1.  <span data-ttu-id="0ad87-151">要素を右クリックして、コンテキストメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-151">Simulate a right-mouse click on the element to open the context menu.</span></span>  
1.  <span data-ttu-id="0ad87-152">[**検査**] オプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-152">Choose the **Inspect** option.</span></span>  <span data-ttu-id="0ad87-153">これにより、**要素**パネルが開き、 **DOM ツリー**で要素がフォーカスされます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-153">This opens the **Elements** panel and focuses the element in the **DOM Tree**.</span></span>  

<!--todo:  add dom nodes (elements pane) section when available  -->  

<span data-ttu-id="0ad87-154">**DOM ツリー**は、 [ARIA `tree` ][W3CWaiAriaTree]としてレイアウトされています。</span><span class="sxs-lookup"><span data-stu-id="0ad87-154">The **DOM Tree** is laid out as an [ARIA `tree`][W3CWaiAriaTree].</span></span>  <!--See [Navigate the **DOM Tree** with a keyboard][DevtoolsDomIndexNavigateDomTreeKeyboard] for an example.  -->  

<!--todo: add dom index navigation tree section then available  -->

### <span data-ttu-id="0ad87-155">DOM ツリーの要素のコードをコピーする</span><span class="sxs-lookup"><span data-stu-id="0ad87-155">Copy the code for an element in the DOM Tree</span></span>   

1.  <span data-ttu-id="0ad87-156">**DOM ツリー**のノードにフォーカスがある状態で、右クリックのコンテキストメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-156">With focus on a node in the **DOM Tree**, bring up the right-click context menu.</span></span>  
1.  <span data-ttu-id="0ad87-157">[**コピー** ] オプションを展開します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-157">Expand the **Copy** option.</span></span>  
1.  <span data-ttu-id="0ad87-158">[ **OuterHTML のコピー**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-158">Select **Copy outerHTML**.</span></span>  

#### <span data-ttu-id="0ad87-159">既知の問題</span><span class="sxs-lookup"><span data-stu-id="0ad87-159">Known issues</span></span>   

*   <span data-ttu-id="0ad87-160">**OuterHTML をコピー**すると、現在のノードは選ばれず、親ノードが選択されることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-160">**Copy outerHTML** often does not select the current node but instead selects the parent node.</span></span>  <span data-ttu-id="0ad87-161">ただし、要素の内容は、コピーされた outerHTML にも含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-161">However, the contents of the element should still be in the copied outerHTML.</span></span>  

### <span data-ttu-id="0ad87-162">DOM ツリーの要素の属性を変更する</span><span class="sxs-lookup"><span data-stu-id="0ad87-162">Modify the attributes of an element in the DOM Tree</span></span>   

*   <span data-ttu-id="0ad87-163">**DOM ツリー**のノードにフォーカスがある状態で、を押して、そのノードを `Enter` 編集可能にします。</span><span class="sxs-lookup"><span data-stu-id="0ad87-163">With focus on a node in the **DOM Tree**, press `Enter` to make it editable.</span></span>  
*   <span data-ttu-id="0ad87-164">を押して `Tab` 、属性値の間を移動します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-164">Press `Tab` to move between attribute values.</span></span>  <span data-ttu-id="0ad87-165">"スペース" という音声が空のテキスト入力の中にあり、新しい属性値を入力できます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-165">When you hear "space" you are inside of an empty text input and are able to type a new attribute value.</span></span>  
*   <span data-ttu-id="0ad87-166">`Control` + `Enter` \ (Windows \) または `Command` + `Enter` \ (macOS \) を押すと、変更が反映され、要素の内容全体が読み上げられます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-166">Press `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\) to accept the change and hear the entire contents of the element.</span></span>  

#### <span data-ttu-id="0ad87-167">既知の問題</span><span class="sxs-lookup"><span data-stu-id="0ad87-167">Known issues</span></span>   

*   <span data-ttu-id="0ad87-168">テキスト入力に入力すると、フィードバックは表示されません。</span><span class="sxs-lookup"><span data-stu-id="0ad87-168">When you type into the text input you get no feedback.</span></span>  <span data-ttu-id="0ad87-169">入力ミスをして方向キーを使用して入力を調べると、フィードバックも送信されません。</span><span class="sxs-lookup"><span data-stu-id="0ad87-169">If you make a typo and use the arrow keys to explore your input you also get no feedback.</span></span>  <span data-ttu-id="0ad87-170">作業を確認する最も簡単な方法は、変更を承諾した後、要素全体をリッスンしてアナウンスすることです。</span><span class="sxs-lookup"><span data-stu-id="0ad87-170">The easiest way to check your work is to accept the change, then listen for the entire element to be announced.</span></span>  

### <span data-ttu-id="0ad87-171">DOM ツリーの要素の HTML を編集する</span><span class="sxs-lookup"><span data-stu-id="0ad87-171">Edit the HTML of an element in the DOM Tree</span></span>   

*   <span data-ttu-id="0ad87-172">**DOM ツリー**のノードにフォーカスがある状態で、を押して、そのノードを `Enter` 編集可能にします。</span><span class="sxs-lookup"><span data-stu-id="0ad87-172">With focus on a node in the **DOM Tree**, press `Enter` to make it editable.</span></span>  
*   <span data-ttu-id="0ad87-173">を押して `Tab` 、属性値の間を移動します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-173">Press `Tab` to move between attribute values.</span></span>  <span data-ttu-id="0ad87-174">たとえば、"h2" のように、要素の名前が読み上げられたときに、テキスト入力の内部にあり、要素の型を変更することがあります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-174">When you hear the name of the element, for instance, "h2", you are inside of a text input and may change the type of the element.</span></span>  
*   <span data-ttu-id="0ad87-175">`Control` + `Enter` 変更を反映するには、\ (Windows \) または `Command` + `Enter` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-175">Press `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\) to accept the change.</span></span>  

<span data-ttu-id="0ad87-176">たとえば、「 `h3` `Control` + `Enter` \ (Windows \)」または「\ (macOS \)」と入力すると、 `Command` + `Enter` 要素の開始タグと終了タグが変更され `h3` ます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-176">For example, typing `h3` and pressing `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\) changes the start and end tags of the element to `h3`.</span></span>  

## <span data-ttu-id="0ad87-177">要素パネルのタブ</span><span class="sxs-lookup"><span data-stu-id="0ad87-177">Elements panel tabs</span></span>   

<span data-ttu-id="0ad87-178">[**要素**] パネルには、要素に適用される CSS や、アクセシビリティツリーの関連する場所を調べるための追加のタブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0ad87-178">The **Elements** panel contains additional tabs for inspecting things like the CSS applied to an element or the relevant place in the accessibility tree.</span></span>  

*   <span data-ttu-id="0ad87-179">**DOM ツリー**のノードにフォーカスがある状態で、[ `Tab` **スタイル**] ウィンドウが選択されているという音声が聞こえるまで、キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-179">With focus on a node in the **DOM Tree**, press `Tab` until you hear that the **Styles** pane is selected.</span></span>  
*   <span data-ttu-id="0ad87-180">を使用して、 `Right Arrow` その他の使用できるタブを調べます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-180">Use the `Right Arrow` to explore other available tabs.</span></span>  

<span data-ttu-id="0ad87-181">**DOM ツリー**は、属性を持つ要素をフォーカス可能な `href` リンクに変換するため、[ `Tab` **スタイル**] ウィンドウに到達するために複数回押す必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-181">The **DOM Tree** turns elements with `href` attributes into focusable links, so you may need to press `Tab` more than once to reach the **Styles** pane.</span></span>  

### <span data-ttu-id="0ad87-182">既知の問題</span><span class="sxs-lookup"><span data-stu-id="0ad87-182">Known issues</span></span>   

<span data-ttu-id="0ad87-183">[ **DOM ブレークポイント**] タブと [**プロパティ**] タブは、キーボードからアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="0ad87-183">The **DOM Breakpoints** and **Properties** tabs are not keyboard accessible.</span></span>  

### <span data-ttu-id="0ad87-184">スタイルウィンドウ</span><span class="sxs-lookup"><span data-stu-id="0ad87-184">Styles pane</span></span>   

<span data-ttu-id="0ad87-185">[**スタイル**] ウィンドウでは、フィルター処理のスタイル、要素の状態の切り替え ( [`:active`][MDNActive] および [`:focus`][MDNFocus] \)、クラスの切り替え、新しいクラスの追加などのコントロールを検索します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-185">In the **Styles** pane find controls for filtering styles, toggling element states \(such as [`:active`][MDNActive] and [`:focus`][MDNFocus]\), toggling classes, and adding new classes.</span></span>  <span data-ttu-id="0ad87-186">また、 **DOM ツリー**でフォーカスが置かれている要素に現在適用されているスタイルを調査し、変更するための強力なスタイル検査ツールも用意されています。</span><span class="sxs-lookup"><span data-stu-id="0ad87-186">There is also a powerful style inspection tool to explore and modify styles currently applied to the element that is in focus in the **DOM Tree**.</span></span>  

<span data-ttu-id="0ad87-187">[**スタイル**] ウィンドウについて理解するための重要な概念は、現在選択されているノードのスタイルのみが**DOM ツリー**に表示されることです。</span><span class="sxs-lookup"><span data-stu-id="0ad87-187">The key concept to understand about the **Styles** pane is that it only shows styles for the currently-selected node in the **DOM Tree**.</span></span>  <span data-ttu-id="0ad87-188">たとえば、ノードのスタイルの検査が終了したのに、ノードのスタイルを確認したいとし `<header>` `<footer>` ます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-188">For example, suppose you are done inspecting the styles of a `<header>` node, and now you want to look at the styles for a `<footer>` node.</span></span>  <span data-ttu-id="0ad87-189">そのためには、最初に `<footer>` **DOM ツリー**でノードを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-189">To do that, you first need to select the `<footer>` node in the **DOM Tree**.</span></span>  <span data-ttu-id="0ad87-190">「ワークフロー[検査](#inspect-an-element-on-the-page)」を使用して、ノードの近く (フッター \ などのリンクなど) にあるノードを検査します。これにより、 `footer` **DOM ツリー**がフォーカスされます。次に、キーボードを使用して目的のノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-190">You may find it faster to use the [Inspect](#inspect-an-element-on-the-page) workflow to inspect a node that is in the general vicinity of the `footer` node \(such as a link within the footer\), which focuses the **DOM Tree**, and then use your keyboard to navigate to the exact node in which you are interested.</span></span>  

#### <span data-ttu-id="0ad87-191">[スタイル] ウィンドウ内の移動</span><span class="sxs-lookup"><span data-stu-id="0ad87-191">Navigate the Styles pane</span></span>   

<span data-ttu-id="0ad87-192">すべてのスタイルツールは、1つの方法で、または別**のスタイルのペインに**接続しているため、最初にこのツールをマスターすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0ad87-192">Because all of the style tools connect in one way or another back to the **Styles** pane, it makes sense to master this tool first.</span></span>  

*   <span data-ttu-id="0ad87-193">[**スタイル**] ウィンドウにフォーカスがある状態で、を押してフォーカスを移動し、内容を確認し `Tab` ます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-193">With focus on the **Styles** pane, press `Tab` to move focus inside and explore the contents.</span></span>  
*   <span data-ttu-id="0ad87-194">`Tab`最初のスタイルがアクティブになるまで、キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-194">Press `Tab` until the first style becomes active.</span></span>  <span data-ttu-id="0ad87-195">スクリーンリーダーを使用している場合、この最初のスタイルは "element. style" としてアナウンスされ {} ます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-195">If you are using a screen reader this first style is announced as "element.style {}".</span></span>  
*   <span data-ttu-id="0ad87-196">を押して `Down Arrow` 、スタイルの一覧を目的の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-196">Press `Down Arrow` to navigate the list of styles in order of specificity.</span></span>  <span data-ttu-id="0ad87-197">スクリーンリーダーは、CSS ファイルの名前、スタイルが表示される行番号、スタイルの名前の順に、各スタイルを読み上げます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-197">A screen reader announces each style starting with the name of the CSS file, the line number on which the style appears, and the name of the style.</span></span>  <span data-ttu-id="0ad87-198">例: "main .css: 233. card__img {} "</span><span class="sxs-lookup"><span data-stu-id="0ad87-198">For example: "main.css:233 .card__img {}"</span></span>  
*   <span data-ttu-id="0ad87-199">を押して `Enter` 、スタイルを詳しく調べます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-199">Press `Enter` to inspect a style in more detail.</span></span>  <span data-ttu-id="0ad87-200">スタイル名の編集可能なバージョンからフォーカスを開始します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-200">Focus begins on an editable version of the style name.</span></span>  
*   <span data-ttu-id="0ad87-201">`Tab`各 CSS プロパティの編集可能なバージョンとそれに対応する値の間を移動するには、を押します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-201">Press `Tab` to move between editable versions of each CSS property and their corresponding values.</span></span>  <span data-ttu-id="0ad87-202">各スタイルブロックの末尾には、CSS プロパティを追加するために使用できる空白の編集可能なテキストフィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-202">At the end of each style block is a blank editable text field which you may use to add additional CSS properties.</span></span>  
*   <span data-ttu-id="0ad87-203">キーを押しながら `Tab` スタイルの一覧内を移動するか、またはキーを押して `Escape` このモードを終了し、方向キーを使用して移動することができます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-203">You may continue to press `Tab` to move through the list of styles, or press `Escape` to exit this mode and go back to navigating by arrow keys.</span></span>  

<span data-ttu-id="0ad87-204">その他のショートカットについては、[[スタイル] ウィンドウのキーボードリファレンス] [DevtoolsShortcutsStylesPaneKeyboard] を読んでください。</span><span class="sxs-lookup"><span data-stu-id="0ad87-204">Be sure to read through the [Styles pane keyboard reference][DevtoolsShortcutsStylesPaneKeyboard] for additional shortcuts.</span></span>  

##### <span data-ttu-id="0ad87-205">既知の問題</span><span class="sxs-lookup"><span data-stu-id="0ad87-205">Known Issues</span></span>   

*   <span data-ttu-id="0ad87-206">編集可能テキストフィールド**を使用**すると、スタイルのリスト内を移動することはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-206">If you use the **Filter** editable text field, you are no longer be able to navigate the list of styles.</span></span>  

#### <span data-ttu-id="0ad87-207">要素の状態を切り替える</span><span class="sxs-lookup"><span data-stu-id="0ad87-207">Toggle element state</span></span>   

<span data-ttu-id="0ad87-208">要素の状態を切り替えるには、次のようにし `:active` `:focus` ます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-208">To toggle the state of an element, such as `:active` or `:focus`:</span></span>  

1.  <span data-ttu-id="0ad87-209">[**スタイル**] ウィンドウに移動し `Tab` 、[**要素の状態の切り替え**] ボタンがフォーカスされるまで押します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-209">Navigate to the **Styles** pane and press `Tab` until the **Toggle Element State** button has focus.</span></span>  
1.  <span data-ttu-id="0ad87-210">を押して `Enter` 、要素の状態のコレクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-210">Press `Enter` to expand the collection of element states.</span></span>  <span data-ttu-id="0ad87-211">要素の状態は、チェックボックスのグループとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-211">The element states are presented as a group of checkboxes.</span></span>  
1.  <span data-ttu-id="0ad87-212">`Tab`1 つ目の状態にフォーカスが置かれるまで、キーを押し `:active` ます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-212">Press `Tab` until the first state, `:active`, has focus.</span></span>  
1.  <span data-ttu-id="0ad87-213">を押して `Space` 有効にします。</span><span class="sxs-lookup"><span data-stu-id="0ad87-213">Press `Space` to enable it.</span></span>  <span data-ttu-id="0ad87-214">DOM ツリーで現在選択されている要素にスタイルが設定されている場合 `:active` は、それが適用されます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-214">If the currently-selected element in the DOM Tree has an `:active` style, it is now applied.</span></span>  
1.  <span data-ttu-id="0ad87-215">引き続きキー `Tab` を押して、利用可能なすべての状態を調査します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-215">Continue pressing `Tab` to explore all of the available states.</span></span>  

#### <span data-ttu-id="0ad87-216">既存のクラスを追加する</span><span class="sxs-lookup"><span data-stu-id="0ad87-216">Add an existing class</span></span>   

<span data-ttu-id="0ad87-217">**トグル要素の状態**ボタンの横にあるのは、[**要素クラス**] ボタンです。</span><span class="sxs-lookup"><span data-stu-id="0ad87-217">Adjacent to the **Toggle Element State** button is the **Element Classes** button.</span></span>  <span data-ttu-id="0ad87-218">[次へ] を押してフォーカスを移動し `Tab` `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-218">Move focus to it by pressing `Tab` then `Enter`.</span></span>  <span data-ttu-id="0ad87-219">フォーカスは、[ **Add New Class**] というラベルの編集テキストフィールドに移動します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-219">Focus moves into an edit text field labeled **Add New Class**.</span></span>  

<span data-ttu-id="0ad87-220">[**要素クラス**] ボタンは、主に既存のクラスを要素に追加するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-220">The **Element Classes** button is primarily used for adding existing classes to an element.</span></span>  <span data-ttu-id="0ad87-221">たとえば、スタイルシートに、という名前のヘルパークラスが含まれている場合は、[ `.clearfix` `.` テキストの編集] フィールドの内側を押して候補の一覧を表示し、を使用して `Down Arrow` 候補を検索し `.clearfix` ます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-221">For example, if your stylesheet contained a helper class named `.clearfix` you may press `.` inside of the edit text field to see a suggestion list of classes and use the `Down Arrow` to find the `.clearfix` suggestion.</span></span>  <span data-ttu-id="0ad87-222">または、クラス名を自分で入力して、を押して `Enter` 適用します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-222">Or type the class name out yourself and press `Enter` to apply it.</span></span>  

#### <span data-ttu-id="0ad87-223">新しいスタイルルールを追加する</span><span class="sxs-lookup"><span data-stu-id="0ad87-223">Add a new style rule</span></span>   

<span data-ttu-id="0ad87-224">[**要素クラス**] ボタンの横には、**新しい [スタイルルール**] ボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-224">Adjacent to the **Element Classes** button is the **New Style Rule** button.</span></span>  <span data-ttu-id="0ad87-225">キーを押してフォーカスを移動し `Tab` `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-225">Move focus to it by pressing `Tab` and press `Enter`.</span></span>  <span data-ttu-id="0ad87-226">フォーカスは、スタイル検査内の編集可能なテキストフィールドに移動します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-226">Focus moves into an editable text field inside of the style inspector.</span></span>  <span data-ttu-id="0ad87-227">フィールドの最初のテキストのコンテンツは、 **DOM ツリー**で選択された要素のタグ名です。</span><span class="sxs-lookup"><span data-stu-id="0ad87-227">The initial text content of the field is the tag name of the element that is selected in the **DOM Tree**.</span></span>  
<span data-ttu-id="0ad87-228">このフィールドに任意のクラス名を入力し、を押して `Tab` CSS プロパティを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-228">You may type any class name you want into this field and then press `Tab` to assign CSS properties to it.</span></span>  

### <span data-ttu-id="0ad87-229">[計算] タブ</span><span class="sxs-lookup"><span data-stu-id="0ad87-229">Computed tab</span></span>   

<span data-ttu-id="0ad87-230">[**計算**] タブにフォーカスがある状態で、を押してフォーカスを移動し、内容を確認し `Tab` ます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-230">With focus on the **Computed** tab, press `Tab` to move focus inside and explore the contents.</span></span>  <span data-ttu-id="0ad87-231">[**計算**] タブでは、要素に実際に適用される CSS プロパティを調査するためのコントロールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="0ad87-231">Within the **Computed** tab there are controls for exploring which CSS properties are actually applied to an element in order of specificity.</span></span>  

<!--todo: add computed tab section when available  -->  

#### <span data-ttu-id="0ad87-232">計算されたスタイルをすべて調べる</span><span class="sxs-lookup"><span data-stu-id="0ad87-232">Explore all computed styles</span></span>   

<span data-ttu-id="0ad87-233">`Tab`計算されたスタイルのコレクションに到達するまで、キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-233">Press `Tab` until you reach the collection of computed styles.</span></span>  <span data-ttu-id="0ad87-234">これらは[ARIA `tree` ][W3CWaiAriaTree]として表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-234">These are presented as an [ARIA `tree`][W3CWaiAriaTree].</span></span>  <span data-ttu-id="0ad87-235">Listbox を展開すると、計算されたスタイルを適用している CSS セレクターが示されます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-235">Expanding a listbox reveals which CSS selectors are applying the computed style.</span></span>  <span data-ttu-id="0ad87-236">これらのセレクターは、特異性によって整理されます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-236">These selectors are organized by specificity.</span></span>  <span data-ttu-id="0ad87-237">スクリーンリーダーは、計算値、現在一致している CSS セレクター、セレクターを含むスタイルシートのファイル名、セレクターの行番号を通知します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-237">A screen reader announces the computed value, which CSS selector is currently matching, the filename of the stylesheet that contains the selector, and the line number for the selector.</span></span>  

#### <span data-ttu-id="0ad87-238">既知の問題</span><span class="sxs-lookup"><span data-stu-id="0ad87-238">Known issues</span></span>   

*   <span data-ttu-id="0ad87-239">**フィルター**テキストフィールドを使用する場合、スタイルを検査することはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-239">If you use the **Filter** text field, you are no longer able to inspect styles.</span></span>  

### <span data-ttu-id="0ad87-240">[イベントリスナー] タブ</span><span class="sxs-lookup"><span data-stu-id="0ad87-240">Event listeners tab</span></span>   

<span data-ttu-id="0ad87-241">[**要素**] パネルで、[**イベントリスナー** ] タブを使って、要素に適用されているイベントリスナーを調べることができます。 [**スタイル**] ウィンドウにフォーカスがある状態で、を押して [ `Right Arrow` **イベントリスナー** ] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-241">From within the **Elements** panel you may inspect the event listeners applied to an element using the **Event Listeners** tab.  With focus on the **Styles** pane, press the `Right Arrow` to navigate to the **Event Listeners** tab.</span></span>  

#### <span data-ttu-id="0ad87-242">イベントリスナーを調べる</span><span class="sxs-lookup"><span data-stu-id="0ad87-242">Explore event listeners</span></span>   

<span data-ttu-id="0ad87-243">イベントリスナーは[ARIA `tree` ][W3CWaiAriaTree]として表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-243">Event listeners are presented as an [ARIA `tree`][W3CWaiAriaTree].</span></span>  <span data-ttu-id="0ad87-244">方向キーを使用して移動することができます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-244">You may use the arrow keys to navigate them.</span></span>  <span data-ttu-id="0ad87-245">スクリーンリーダーは、イベントリスナーがアタッチされている DOM オブジェクトの名前に加えて、イベントリスナーが定義されているファイル名と行番号を通知します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-245">A screen reader announces the name of the DOM object that the event listener is attached to, as well as the file name where the event listener is defined and the line number.</span></span>  

### <span data-ttu-id="0ad87-246">アクセシビリティウィンドウ</span><span class="sxs-lookup"><span data-stu-id="0ad87-246">Accessibility pane</span></span>   

<span data-ttu-id="0ad87-247">[**アクセシビリティ**] ウィンドウにフォーカスがある状態で、を押してフォーカスを移動し、内容を確認し `Tab` ます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-247">With focus on the **Accessibility** pane, press `Tab` to move focus inside and explore the contents.</span></span>  <span data-ttu-id="0ad87-248">[**アクセシビリティ**] ウィンドウ内には、アクセシビリティツリー、要素に適用される ARIA 属性、および計算されたアクセシビリティプロパティを調べるためのコントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-248">Within the **Accessibility** pane there are controls for exploring the accessibility tree, the ARIA attributes applied to an element, and the computed accessibility properties.</span></span>  

<!--todo: add reference (Accessibility pane) section when available  -->  

#### <span data-ttu-id="0ad87-249">アクセシビリティツリー</span><span class="sxs-lookup"><span data-stu-id="0ad87-249">Accessibility Tree</span></span>   

<span data-ttu-id="0ad87-250">**アクセシビリティツリー**は[ARIA `tree` ][W3CWaiAriaTree]として表示され、それぞれが `treeitem` DOM 内の要素に対応しています。</span><span class="sxs-lookup"><span data-stu-id="0ad87-250">The **Accessibility Tree** is presented as an [ARIA `tree`][W3CWaiAriaTree] where each `treeitem` corresponds to an element in the DOM.</span></span>  <span data-ttu-id="0ad87-251">ツリーは、選んだノードの計算された役割を通知します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-251">The tree announces the computed role for the selected node.</span></span>  <span data-ttu-id="0ad87-252">などの一般的な要素 `div` `span` は、ツリーの "genericcontainer" としてアナウンスされます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-252">Generic elements like `div` and `span` are announced as "GenericContainer" in the tree.</span></span>  <span data-ttu-id="0ad87-253">方向キーを使用してツリーを走査し、親子関係を調べます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-253">Use the arrow keys to traverse the tree and explore parent-child relationships.</span></span>  

#### <span data-ttu-id="0ad87-254">既知の問題</span><span class="sxs-lookup"><span data-stu-id="0ad87-254">Known issues</span></span>   

*   <span data-ttu-id="0ad87-255">**アクセシビリティ**ウィンドウで使用される[ARIA `tree` ][W3CWaiAriaTree]の種類は、VoiceOver のような macOS のスクリーンリーダーでは Microsoft Edge で適切に公開されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-255">The type of [ARIA `tree`][W3CWaiAriaTree] used by the **Accessibility** pane may not be properly exposed in Microsoft Edge for macOS screen readers like VoiceOver.</span></span>  <span data-ttu-id="0ad87-256">この問題の進捗状況について通知を受け取るには、 [Chromium の問題 #868480][ChromiumIssues868480]をサブスクライブしてください。</span><span class="sxs-lookup"><span data-stu-id="0ad87-256">Subscribe to [Chromium issue #868480][ChromiumIssues868480] to be informed about progress on this issue.</span></span>  
*   <span data-ttu-id="0ad87-257">各**Aria 属性**と計算された**プロパティ**のセクションは[aria `tree` ][W3CWaiAriaTree]としてマークされていますが、現在はフォーカス管理がないため、キーボード操作はできません。</span><span class="sxs-lookup"><span data-stu-id="0ad87-257">Each of the **ARIA Attributes** and **Computed Properties** sections are marked up as an [ARIA `tree`][W3CWaiAriaTree], but each does not currently have focus management and is not keyboard operable.</span></span>  

## <span data-ttu-id="0ad87-258">監査パネル</span><span class="sxs-lookup"><span data-stu-id="0ad87-258">Audits panel</span></span>   

<span data-ttu-id="0ad87-259">**監査**パネルでは、パフォーマンス、アクセシビリティ、SEO、その他のカテゴリの多くに関連する一般的な問題をチェックするために、サイトに対して一連のテストを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-259">The **Audits** panel you should run a series of tests against a site to check for common issues related to performance, accessibility, SEO, and a number of other categories.</span></span>  

### <span data-ttu-id="0ad87-260">監査を構成して実行する</span><span class="sxs-lookup"><span data-stu-id="0ad87-260">Configure and run an audit</span></span>   

1.  <span data-ttu-id="0ad87-261">**監査**パネルを最初に開いたときに、フォームの最後にある [**監査の実行**] ボタンにフォーカスが置かれます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-261">When the **Audits** panel is first opened, focus is placed on the **Run Audit** button at the end of the form.</span></span>  <span data-ttu-id="0ad87-262">既定では、シミュレートされた3G 接続でモバイルエミュレーションを使用して、すべてのカテゴリの監査を実行するようにフォームが構成されています。</span><span class="sxs-lookup"><span data-stu-id="0ad87-262">By default the form is configured to run audits for every category using mobile emulation on a simulated 3G connection.</span></span>  
1.  <span data-ttu-id="0ad87-263">`Shift` + `Tab` 監査設定を変更するには、[参照] モードを使うか、もう一度移動します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-263">Use `Shift`+`Tab` or navigate back in Browse mode to change the audit settings.</span></span>  
1.  <span data-ttu-id="0ad87-264">監査を実行する準備ができたら、[**監査の実行**] ボタンに戻り、enter キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-264">When you are ready to run the audit, navigate back to the **Run Audit** button and press `Enter`.</span></span>  
1.  <span data-ttu-id="0ad87-265">フォーカスが **[キャンセル**] ボタンでモーダルウィンドウに移動し、監査を終了することができます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-265">Focus moves into a modal window with a **Cancel** button which allows you to exit the audit.</span></span>  <span data-ttu-id="0ad87-266">監査が実行され、ページが複数回更新されると、一連の考えが何度も発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-266">You may hear a series of earcons as the audit runs and refreshes the page multiple times.</span></span>  

#### <span data-ttu-id="0ad87-267">既知の問題</span><span class="sxs-lookup"><span data-stu-id="0ad87-267">Known issues</span></span>   

*   <span data-ttu-id="0ad87-268">構成フォームのセクションは、現在、要素でマークアップされていません `fieldset` 。</span><span class="sxs-lookup"><span data-stu-id="0ad87-268">The different sections of the configuration form are not currently marked up with a `fieldset` element.</span></span>  <span data-ttu-id="0ad87-269">各セクションに関連付けられているコントロールを確認するために、参照モードで移動した方が簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-269">It may be easier to navigate them in Browse mode to figure out which controls are associated with each section.</span></span>  
*   <span data-ttu-id="0ad87-270">監査の実行が完了しても、現在のところ、またはライブリージョンのお知らせはありません。</span><span class="sxs-lookup"><span data-stu-id="0ad87-270">There is no earcon or live region announcement when the audit is finished running.</span></span>  <span data-ttu-id="0ad87-271">通常、30秒ほどかかります。その後、結果に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-271">Generally it takes about 30 seconds, after which you should be able to navigate to the results.</span></span>  <span data-ttu-id="0ad87-272">検索結果を表示するには、参照モードを使用する方法が最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="0ad87-272">Using Browse mode may be the easiest way to reach the results.</span></span>  

### <span data-ttu-id="0ad87-273">監査レポート内を移動する</span><span class="sxs-lookup"><span data-stu-id="0ad87-273">Navigate the audit report</span></span>   

<span data-ttu-id="0ad87-274">監査レポートは、各監査カテゴリに対応するセクションに整理されます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-274">The audit report is organized into sections that correspond with each of the audit categories.</span></span>  <span data-ttu-id="0ad87-275">レポートが開き、各カテゴリのスコアの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-275">The report opens with a list of scores for each category.</span></span>  <span data-ttu-id="0ad87-276">これらのスコアは、関連するセクションにスキップするために使用できるリンクでもあります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-276">These scores are also links which are able to be used to skip to the relevant sections.</span></span>  <span data-ttu-id="0ad87-277">各セクション内には `details` 、成功または失敗の監査に関連する情報が含まれている拡張可能な要素があります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-277">Within each section are expandable `details` elements, which contain information relating to passed or failed audits.</span></span>  <span data-ttu-id="0ad87-278">既定では、失敗した監査のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-278">By default, only failing audits are shown.</span></span>  <span data-ttu-id="0ad87-279">各セクションは、 `details` 成功したすべての監査を含む最終要素で終わります。</span><span class="sxs-lookup"><span data-stu-id="0ad87-279">Each section ends with a final `details` element which contains all of the passed audits.</span></span>  

<span data-ttu-id="0ad87-280">新しい監査を実行するには、を使用して `Shift` + `Tab` レポートを終了し、[**監査の実行**] ボタンを探します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-280">To run a new audit, use `Shift`+`Tab` to exit the report and look for the **Perform An Audit** button.</span></span>  

## <span data-ttu-id="0ad87-281">フィードバック</span><span class="sxs-lookup"><span data-stu-id="0ad87-281">Feedback</span></span>   

*   <span data-ttu-id="0ad87-282">DevTools バグレポートまたは[Chromium Issue Tracker][MonorailChromiumIssues]への機能要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-282">Send DevTools bug reports or feature requests to [Chromium Issue Tracker][MonorailChromiumIssues].</span></span>  
*   <span data-ttu-id="0ad87-283">このドキュメントに関連するフィードバックを[GitHub][GithubEdgeDeveloperNewIssue]に送信します。</span><span class="sxs-lookup"><span data-stu-id="0ad87-283">Send any feedback related to this document to [GitHub][GithubEdgeDeveloperNewIssue].</span></span>  

<!-- image links -->  

<!-- links -->  

<!--[DevtoolsAccessibilityReference]: reference.md "Accessibility Reference"  -->  
<!--[DevtoolsAccessibilityReferencePane]: reference.md#the-accessibility-pane "The Accessibility pane - Accessibility Reference"  -->  

<!--[MicrosoftEdgeDevtoolsIndex]: ../index.md "Microsoft Edge DevTools"  -->  
<span data-ttu-id="0ad87-284">[Dev[コマンド] メニューインデックス]:...[コマンドの実行] [Microsoft Edge ツール] のコマンドメニューを使用してコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="0ad87-284">[DevtoolsCommandMenuIndex]: ../command-menu/index.md "Run Commands With The Microsoft Edge DevTools Command Menu"</span></span>  
[Dev| Consoleindex]:...md "コンソールの概要"
[DevtoolsConsoleIndex]: ../console/index.md "Console Overview"  
[DevtoolsCssIndex]:.../css/index.md "CSS の表示と変更の概要"  
<!--[DevtoolsCssReferenceViewAppliedElement]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "CSS Reference - View only the CSS that is actually applied to an element"  -->  
<!--[DevtoolsDomIndex]: ../dom/index.md "Get Started With Viewing And Changing The DOM"  -->  
<!--[DevtoolsDomIndexNavigateDomTreeKeyboard]: ../dom/index.md#navigate-the-dom-tree-with-a-keyboard "Navigate the DOM Tree with a keyboard - Get Started With Viewing And Changing The DOM"  -->
[DevtoolsOpen]:../open.md "Microsoft Edge DevTools を開く"  
<span data-ttu-id="0ad87-288">[Dev[キーボードショートカット]:.../shortcuts.md "Microsoft Edge DevTools のキーボードショートカット"</span><span class="sxs-lookup"><span data-stu-id="0ad87-288">[DevtoolsShortcuts]: ../shortcuts.md "Microsoft Edge DevTools Keyboard Shortcuts"</span></span>  
[DevtoolsShortcutsStylesPaneKeyboard]: ../shortcuts.md # styles-ウィンドウ-キーボードショートカット "[スタイル] ウィンドウのキーボードショートカット-Microsoft Edge DevTools のキーボードショートカット"  

[ChromiumIssues868480]: https://bugs.chromium.org/p/chromium/issues/detail?id=868480 "問題 868480-ARIA ツリーを Mac アクセシビリティの表として公開する"  
[GithubEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Docs%20Feedback%5D "新しい問題-Microsoft のドキュメント/エッジ-開発者 |GitHub"  
[MDNActive]: https://developer.mozilla.org/docs/Web/CSS/:active ": active |MDN"  
[MDNFocus]: https://developer.mozilla.org/docs/Web/CSS/:focus ": フォーカス |MDN"  
[MonorailChromiumIssues]: https://crbug.com "問題-chromium"  
[W3CWaiAriaTablist]: https://www.w3.org/TR/wai-aria-1.1/#tablist "tablist (役割)-アクセシビリティの高いリッチインターネットアプリケーション (WAI-ARIA 使った-ARIA) 1.1 |勧告"  
[W3CWaiAriaTree]: https://www.w3.org/TR/wai-aria-1.1/#tree "tree (役割)-アクセシビリティの高いリッチインターネットアプリケーション (WAI-ARIA 使った-ARIA) 1.1 |勧告"  

> [!NOTE]
> <span data-ttu-id="0ad87-297">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ad87-297">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0ad87-298">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation)にあり、[渡 Dodson][RobDodson]によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="0ad87-298">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation) and is authored by [Rob Dodson][RobDodson] \(Contributor, Google WebFundamentals\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="0ad87-300">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="0ad87-300">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[RobDodson]: https://developers.google.com/web/resources/contributors/robdodson  
