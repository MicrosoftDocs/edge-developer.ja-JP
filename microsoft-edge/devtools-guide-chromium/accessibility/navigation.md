---
description: スクリーンリーダーなどの支援技術を利用して、Microsoft Edge の DevTools に移動するためのガイドです。
title: Microsoft Edge の DevTools を支援技術でナビゲートする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: f4ec63a0d432925b7db99ce695db66dd61f8bcf1
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125294"
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

# <span data-ttu-id="865aa-104">Microsoft Edge の DevTools を支援技術でナビゲートする</span><span class="sxs-lookup"><span data-stu-id="865aa-104">Navigate Microsoft Edge DevTools with assistive technology</span></span>  

<span data-ttu-id="865aa-105">次の記事では、スクリーンリーダーアクセスなどの支援技術に主に依存しているユーザーを対象として、 [Microsoft Edge DevTools][MicrosoftEdgeDevtoolsMain]を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="865aa-105">The following article aims to help users who primarily rely on assistive technology like screen readers access and use [Microsoft Edge DevTools][MicrosoftEdgeDevtoolsMain].</span></span>  <span data-ttu-id="865aa-106">[Microsoft Edge devtools][MicrosoftEdgeDevtoolsMain] は、microsoft edge ブラウザーに組み込まれた web 開発者ツールのスイートです。</span><span class="sxs-lookup"><span data-stu-id="865aa-106">[Microsoft Edge DevTools][MicrosoftEdgeDevtoolsMain] is a suite of web developer tools built into the Microsoft Edge browser.</span></span>  <span data-ttu-id="865aa-107">Web ページのアクセシビリティを向上させるための DevTools 機能を探している場合は、「アクセシビリティに関する [リファレンス][DevtoolsAccessibilityReference]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="865aa-107">If you are looking for DevTools features related to improving the accessibility of a web page,  see [Accessibility Reference][DevtoolsAccessibilityReference].</span></span>  

<span data-ttu-id="865aa-108">DevTools のアクセシビリティは、進行中の作業です。</span><span class="sxs-lookup"><span data-stu-id="865aa-108">The accessibility of DevTools is a work-in-progress.</span></span>  <span data-ttu-id="865aa-109">一部のパネルとタブは、他の支援技術よりも機能が向上します。</span><span class="sxs-lookup"><span data-stu-id="865aa-109">Some panels and tabs work better with assistive technology than others.</span></span>  <span data-ttu-id="865aa-110">このガイドでは、最もアクセシビリティの高いパネルと、そのような問題が発生する可能性のある特定の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="865aa-110">This guide walks you through the panels which are the most accessible and highlights specific issues you may encounter along the way.</span></span>  

## <span data-ttu-id="865aa-111">概要</span><span class="sxs-lookup"><span data-stu-id="865aa-111">Overview</span></span>  

<span data-ttu-id="865aa-112">開始する前に、DevTools UI がどのように構成されるかを、メンタルモデルで把握することができます。</span><span class="sxs-lookup"><span data-stu-id="865aa-112">Before starting, it helps to have a mental model of how the DevTools UI is structured.</span></span>  <span data-ttu-id="865aa-113">DevTools は、 [ARIA のタブリスト][W3CWaiAriaTablist]に整理された一連のパネルに分かれています。</span><span class="sxs-lookup"><span data-stu-id="865aa-113">DevTools is divided into a series of panels which are organized into an [ARIA tablist][W3CWaiAriaTablist].</span></span>  

<span data-ttu-id="865aa-114">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="865aa-114">For example:</span></span>  

*   <span data-ttu-id="865aa-115">[ **要素** ] パネルでは、[DOM ノードの表示と変更]、[DevtoolsDomIndexNavigateDomTreeKeyboard]、または [ [CSS][DevtoolsCssIndex]] を使用できます。</span><span class="sxs-lookup"><span data-stu-id="865aa-115">The **Elements** panel lets you [view and change DOM nodes][DevtoolsDomIndexNavigateDomTreeKeyboard] or [CSS][DevtoolsCssIndex].</span></span>  
*   <span data-ttu-id="865aa-116">[コンソールパネル][DevtoolsConsoleIndex]では、JavaScript ログとライブ編集オブジェクトを読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="865aa-116">The [Console panel][DevtoolsConsoleIndex] lets you read JavaScript logs and live edit objects.</span></span>  

<span data-ttu-id="865aa-117">各パネルの [コンテンツ] 領域には、さまざまなツールがあります。ドキュメント内のタブまたはウィンドウと呼ばれることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="865aa-117">Within the content area of each panel, there are a number of different tools, often referred to as tabs or panes in the documentation.</span></span>  
<span data-ttu-id="865aa-118">たとえば、[ **要素** ] パネルには、イベントリスナー、アクセシビリティツリーなどを検査するための追加のタブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="865aa-118">For instance, the **Elements** panel contains additional tabs to inspect event listeners, the accessibility tree, and much more.</span></span>  <span data-ttu-id="865aa-119">タブとウィンドウの区別は、任意の方法で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="865aa-119">The distinction between tabs and panes is somewhat arbitrary.</span></span>  <span data-ttu-id="865aa-120">1つの用語が表示される唯一の理由は、公式な DevTools のドキュメントの残りの部分との一貫性を維持することです。</span><span class="sxs-lookup"><span data-stu-id="865aa-120">The only reason you may see one term or the other is to maintain consistency with the rest of the official DevTools documentation.</span></span>  

## <span data-ttu-id="865aa-121">キーボード ショートカット</span><span class="sxs-lookup"><span data-stu-id="865aa-121">Keyboard shortcuts</span></span>  

<span data-ttu-id="865aa-122">[DevTools のショートカットキーリファレンス] [devtools キーボードショートカット] は、役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="865aa-122">The [DevTools Keyboard Shortcuts reference][DevtoolsShortcuts] is a helpful cheatsheet.</span></span>  <span data-ttu-id="865aa-123">ブックマークを作成して、さまざまなパネルを見ながら確認してください。</span><span class="sxs-lookup"><span data-stu-id="865aa-123">Be sure to bookmark it and refer back to it as you explore the different panels.</span></span>  

## <span data-ttu-id="865aa-124">DevTools を開く</span><span class="sxs-lookup"><span data-stu-id="865aa-124">Open DevTools</span></span>  

<span data-ttu-id="865aa-125">始めるには、[Microsoft Edge DevTools を開く] に移動し、[DevTools Open] を選びます。</span><span class="sxs-lookup"><span data-stu-id="865aa-125">To get started, navigate to [Open Microsoft Edge DevTools][DevtoolsOpen].</span></span>  <span data-ttu-id="865aa-126">開発ツールを開くには、キーボードショートカットまたはメニュー項目を使用する方法がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="865aa-126">There are a number of ways to open DevTools, either through keyboard shortcuts or menu items.</span></span>  

## <span data-ttu-id="865aa-127">パネル間を移動する</span><span class="sxs-lookup"><span data-stu-id="865aa-127">Navigate between panels</span></span>  

### <span data-ttu-id="865aa-128">キーボードを使用して移動する</span><span class="sxs-lookup"><span data-stu-id="865aa-128">Navigate by keyboard</span></span>  

*   <span data-ttu-id="865aa-129">Devtools が開いている状態で、[ `Control` + `]` \ (Windows、Linux \)] または [ `Command` + `]` \ (macOS \)] を選択して、次のパネルにフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="865aa-129">With DevTools open, select `Control`+`]` \(Windows, Linux\) or `Command`+`]` \(macOS\) to focus the next panel.</span></span>  
*   <span data-ttu-id="865aa-130">`Control` + `[` 前のパネルにフォーカスするには、[\ (Windows, Linux \]) または `Command` + `[` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="865aa-130">Select `Control`+`[` \(Windows, Linux\) or `Command`+`[` \(macOS\) to focus the previous panel.</span></span>  
*   <span data-ttu-id="865aa-131">また、 `Shift` + `Tab` パネルの[ARIA タブリスト][W3CWaiAriaTablist]にフォーカスを移動したり、方向キーを使ってパネルを変更したりすることもできますが、前に説明したショートカットキーを使用する方が高速である場合もあります。</span><span class="sxs-lookup"><span data-stu-id="865aa-131">It is also possible to use `Shift`+`Tab` to move focus into the [ARIA tablist][W3CWaiAriaTablist] of a panel and use the arrow keys to change panels, though it may be faster to use the previously mentioned shortcuts.</span></span>  

**<span data-ttu-id="865aa-132">既知の問題</span><span class="sxs-lookup"><span data-stu-id="865aa-132">Known issues</span></span>**  

*   <span data-ttu-id="865aa-133">**コンソール**や**パフォーマンス**パネルなどの一部のパネルでは、各パネルがアクティブになるとすぐに、パネルのコンテンツ領域にフォーカスが移動されることがあります。</span><span class="sxs-lookup"><span data-stu-id="865aa-133">Some panels, such as the **Console** and **Performance** panels, may move focus into the panel content area as soon as each panel is activated.</span></span>  <span data-ttu-id="865aa-134">これにより、方向キーによる移動が困難になることがあります。</span><span class="sxs-lookup"><span data-stu-id="865aa-134">This may make navigating by arrow keys difficult.</span></span>  
*   <span data-ttu-id="865aa-135">選択したパネルの名前はアナウンスされますが、パネル内のフォーカスコンテンツを読み取った後にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="865aa-135">The name of the selected panel is announced, but only after it has read the focused content in the panel.</span></span>  <span data-ttu-id="865aa-136">これにより、簡単に見逃してしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="865aa-136">This may make it very easy to miss.</span></span>  

### <span data-ttu-id="865aa-137">[コマンドによる移動] メニュー</span><span class="sxs-lookup"><span data-stu-id="865aa-137">Navigate by Command Menu</span></span>  

<span data-ttu-id="865aa-138">特定のパネルにフォーカスを移動するには、 [コマンドメニュー][DevtoolsCommandMenuIndex]を使用します。</span><span class="sxs-lookup"><span data-stu-id="865aa-138">To focus a specific panel, use the [Command Menu][DevtoolsCommandMenuIndex]:</span></span>  

1.  <span data-ttu-id="865aa-139">Devtools を開いて、[ `Control` + `Shift` + `P` \ (Windows, Linux \)] または [ `Command` + `Shift` + `P` \ (macOS \ **Command Menu**)] を選択してコマンドメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="865aa-139">With DevTools open, select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    <span data-ttu-id="865aa-140">**コマンドメニュー**は、ファジー検索オートコンプリートのコンボボックスです。</span><span class="sxs-lookup"><span data-stu-id="865aa-140">The **Command Menu** is a fuzzy search autocomplete combobox.</span></span>  
1.  <span data-ttu-id="865aa-141">開こうとしているパネルの名前を入力し、キーボードのを使用して `Down Arrow` 適切なオプションに移動します。</span><span class="sxs-lookup"><span data-stu-id="865aa-141">Type the name of the panel you want to open, then use the `Down Arrow` on the keyboard to navigate to the correct option.</span></span>  
1.  <span data-ttu-id="865aa-142">`Enter`コマンドを実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="865aa-142">Select `Enter` to run a command.</span></span>  

<span data-ttu-id="865aa-143">次の操作を実行して、[ **要素** ] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="865aa-143">Complete the following actions to open the **Elements** panel.</span></span>  

1.  <span data-ttu-id="865aa-144">**コマンドメニュー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="865aa-144">Open the **Command Menu**.</span></span>  
1.  <span data-ttu-id="865aa-145">入力 `E` し `L` ます。</span><span class="sxs-lookup"><span data-stu-id="865aa-145">Type `E` then `L`.</span></span>  <span data-ttu-id="865aa-146">[要素の表示] オプションが選択されている **パネル >** ます。</span><span class="sxs-lookup"><span data-stu-id="865aa-146">The **Panel > Show Elements** option is selected.</span></span>  
1.  <span data-ttu-id="865aa-147">パネルを開くコマンドを選択して `Enter` 実行します。</span><span class="sxs-lookup"><span data-stu-id="865aa-147">Select `Enter` to run the command that opens the panel.</span></span>  

<span data-ttu-id="865aa-148">この方法でパネルを開くと、フォーカスはパネルのコンテンツに移動します。</span><span class="sxs-lookup"><span data-stu-id="865aa-148">Open a panel this way directs focus to the contents of the panel.</span></span>  <span data-ttu-id="865aa-149">[ **要素** ] パネルの場合は、[ **DOM] ツリー**にフォーカスが移動します。</span><span class="sxs-lookup"><span data-stu-id="865aa-149">In the case of the **Elements** panel, focus moves into the **DOM Tree**.</span></span>  

## <span data-ttu-id="865aa-150">要素パネル</span><span class="sxs-lookup"><span data-stu-id="865aa-150">Elements panel</span></span>  

### <span data-ttu-id="865aa-151">ページ上の要素を検査する</span><span class="sxs-lookup"><span data-stu-id="865aa-151">Inspect an element on the page</span></span>  

1.  <span data-ttu-id="865aa-152">スクリーンリーダーでカーソルを使って検査する要素に移動します。</span><span class="sxs-lookup"><span data-stu-id="865aa-152">Navigate to the element you want to inspect using the cursor in the screen reader.</span></span>  
1.  <span data-ttu-id="865aa-153">要素のマウスを使って右クリックをシミュレートし、コンテキストメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="865aa-153">Simulate a right-click using a mouse on the element to open the context menu.</span></span>  
1.  <span data-ttu-id="865aa-154">[ **検査** ] オプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="865aa-154">Choose the **Inspect** option.</span></span>  <span data-ttu-id="865aa-155">これにより、[要素] パネルが開き、DOM ツリーの要素がフォーカスされます ([DevtoolsDomIndexViewDomNodes])。</span><span class="sxs-lookup"><span data-stu-id="865aa-155">This [opens the Elements panel and focuses the element in the DOM Tree][DevtoolsDomIndexViewDomNodes].</span></span>  

<span data-ttu-id="865aa-156">**DOM ツリー**は、 [ARIA ツリー][W3CWaiAriaTree]としてレイアウトされています。</span><span class="sxs-lookup"><span data-stu-id="865aa-156">The **DOM Tree** is laid out as an [ARIA tree][W3CWaiAriaTree].</span></span>  <span data-ttu-id="865aa-157">例については、[[DevtoolsDomIndexNavigateDomTreeKeyboard] に移動して、[ **DOM Tree** を移動] を選びます。</span><span class="sxs-lookup"><span data-stu-id="865aa-157">For an example, navigate to [Navigate the **DOM Tree** with a keyboard][DevtoolsDomIndexNavigateDomTreeKeyboard].</span></span>  

### <span data-ttu-id="865aa-158">DOM ツリーの要素のコードをコピーする</span><span class="sxs-lookup"><span data-stu-id="865aa-158">Copy the code for an element in the DOM Tree</span></span>  

1.  <span data-ttu-id="865aa-159">**DOM ツリー**のノードにフォーカスがある状態で、ノードをポイントし、コンテキストメニューを開きます (\ を右クリックします)。</span><span class="sxs-lookup"><span data-stu-id="865aa-159">With focus on a node in the **DOM Tree**, hover on the node and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="865aa-160">[ **コピー** ] オプションを展開します。</span><span class="sxs-lookup"><span data-stu-id="865aa-160">Expand the **Copy** option.</span></span>  
1.  <span data-ttu-id="865aa-161">[ **OuterHTML のコピー**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="865aa-161">Choose **Copy outerHTML**.</span></span>  

**<span data-ttu-id="865aa-162">既知の問題</span><span class="sxs-lookup"><span data-stu-id="865aa-162">Known issues</span></span>**  

*   <span data-ttu-id="865aa-163">**OuterHTML をコピー** すると、現在のノードは選ばれず、親ノードが選択されることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="865aa-163">**Copy outerHTML** often does not select the current node but instead selects the parent node.</span></span>  <span data-ttu-id="865aa-164">ただし、要素の内容は、コピーされた outerHTML にも含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="865aa-164">However, the contents of the element should still be in the copied outerHTML.</span></span>  

### <span data-ttu-id="865aa-165">DOM ツリーの要素の属性を変更する</span><span class="sxs-lookup"><span data-stu-id="865aa-165">Modify the attributes of an element in the DOM Tree</span></span>  

*   <span data-ttu-id="865aa-166">**DOM ツリー**のノードにフォーカスがある状態で、それを選択し `Enter` て編集できるようにします。</span><span class="sxs-lookup"><span data-stu-id="865aa-166">With focus on a node in the **DOM Tree**, select `Enter` to make it editable.</span></span>  
*   <span data-ttu-id="865aa-167">`Tab`属性値の間を移動する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="865aa-167">Select `Tab` to move between attribute values.</span></span>  <span data-ttu-id="865aa-168">"スペース" という音声が空のテキスト入力の中にあり、新しい属性値を入力できます。</span><span class="sxs-lookup"><span data-stu-id="865aa-168">When you hear "space" you are inside of an empty text input and are able to type a new attribute value.</span></span>  
*   <span data-ttu-id="865aa-169">`Control` + `Enter` `Command` + `Enter` 変更を承諾して要素の内容全体を読み上げるには、[\ (Windows, Linux \)] または [\ (macOS \)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="865aa-169">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\) to accept the change and hear the entire contents of the element.</span></span>  

**<span data-ttu-id="865aa-170">既知の問題</span><span class="sxs-lookup"><span data-stu-id="865aa-170">Known issues</span></span>**  

*   <span data-ttu-id="865aa-171">テキスト入力に入力すると、フィードバックは表示されません。</span><span class="sxs-lookup"><span data-stu-id="865aa-171">When you type into the text input you get no feedback.</span></span>  <span data-ttu-id="865aa-172">入力ミスをして方向キーを使用して入力を調べると、フィードバックも送信されません。</span><span class="sxs-lookup"><span data-stu-id="865aa-172">If you make a typo and use the arrow keys to explore your input you also get no feedback.</span></span>  <span data-ttu-id="865aa-173">作業を確認する最も簡単な方法は、変更を承諾した後、要素全体をリッスンしてアナウンスすることです。</span><span class="sxs-lookup"><span data-stu-id="865aa-173">The easiest way to check your work is to accept the change, then listen for the entire element to be announced.</span></span>  

### <span data-ttu-id="865aa-174">DOM ツリーの要素の HTML を編集する</span><span class="sxs-lookup"><span data-stu-id="865aa-174">Edit the HTML of an element in the DOM Tree</span></span>  

*   <span data-ttu-id="865aa-175">**DOM ツリー**のノードにフォーカスがある状態で、それを選択し `Enter` て編集できるようにします。</span><span class="sxs-lookup"><span data-stu-id="865aa-175">With focus on a node in the **DOM Tree**, select `Enter` to make it editable.</span></span>  
*   <span data-ttu-id="865aa-176">`Tab`属性値の間を移動する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="865aa-176">Select `Tab` to move between attribute values.</span></span>  <span data-ttu-id="865aa-177">たとえば、要素の名前が読み上げられた場合 `h2` は、テキスト入力の内部にあり、要素の型を変更することがあります。</span><span class="sxs-lookup"><span data-stu-id="865aa-177">When you hear the name of the element, for instance, `h2`, you are inside of a text input and may change the type of the element.</span></span>  
*   <span data-ttu-id="865aa-178">`Control` + `Enter` 変更を受け入れるには、\ (Windows、Linux \) または `Command` + `Enter` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="865aa-178">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\) to accept the change.</span></span>  

<span data-ttu-id="865aa-179">たとえば、「 `h3` `Control` + `Enter` \ (Windows、Linux \)」または「\ (macOS \)」と入力すると、 `Command` + `Enter` 要素の開始タグと終了タグが `h3` 変わります。</span><span class="sxs-lookup"><span data-stu-id="865aa-179">For example, when you type `h3` and select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\), the start and end tags of the `h3` element change.</span></span>  

## <span data-ttu-id="865aa-180">要素パネルのタブ</span><span class="sxs-lookup"><span data-stu-id="865aa-180">Elements panel tabs</span></span>  

<span data-ttu-id="865aa-181">[ **要素** ] パネルには、要素に適用される CSS や、アクセシビリティツリーの関連する場所を調べるための追加のタブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="865aa-181">The **Elements** panel contains additional tabs for inspecting things like the CSS applied to an element or the relevant place in the accessibility tree.</span></span>  

*   <span data-ttu-id="865aa-182">**DOM ツリー**のノードにフォーカスがある状態で、[ `Tab` **スタイル**] ウィンドウが選択されているという音声が聞こえるまで選択します。</span><span class="sxs-lookup"><span data-stu-id="865aa-182">With focus on a node in the **DOM Tree**, select `Tab` until you hear that the **Styles** pane is selected.</span></span>  
*   <span data-ttu-id="865aa-183">を使用して、 `Right Arrow` その他の使用できるタブを調べます。</span><span class="sxs-lookup"><span data-stu-id="865aa-183">Use the `Right Arrow` to explore other available tabs.</span></span>  

<span data-ttu-id="865aa-184">**DOM ツリー**は、属性を持つ要素をフォーカス可能な `href` リンクに変換するため、[ `Tab` **スタイル**] ウィンドウに移動するには、複数回選択する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="865aa-184">The **DOM Tree** turns elements with `href` attributes into focusable links, so you may need to select `Tab` more than once to reach the **Styles** pane.</span></span>  

**<span data-ttu-id="865aa-185">既知の問題</span><span class="sxs-lookup"><span data-stu-id="865aa-185">Known issues</span></span>**  

<span data-ttu-id="865aa-186">[ **DOM ブレークポイント** ] タブと [ **プロパティ** ] タブは、キーボードからアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="865aa-186">The **DOM Breakpoints** and **Properties** tabs are not keyboard accessible.</span></span>  

### <span data-ttu-id="865aa-187">スタイルウィンドウ</span><span class="sxs-lookup"><span data-stu-id="865aa-187">Styles pane</span></span>  

<span data-ttu-id="865aa-188">[ **スタイル** ] ウィンドウでは、フィルター処理のスタイルのコントロール、要素の状態の切り替え ([ [アクティブ][MDNActive] ] と [ [フォーカス][MDNFocus]] など)、[クラスの切り替え]、[新しいクラスの追加] を参照します。</span><span class="sxs-lookup"><span data-stu-id="865aa-188">In the **Styles** pane find controls for filtering styles, toggling element states \(such as [:active][MDNActive] and [:focus][MDNFocus]\), toggling classes, and adding new classes.</span></span>  <span data-ttu-id="865aa-189">また、 **DOM ツリー**でフォーカスが置かれている要素に現在適用されているスタイルを調査し、変更するための強力なスタイル検査ツールも用意されています。</span><span class="sxs-lookup"><span data-stu-id="865aa-189">There is also a powerful style inspection tool to explore and modify styles currently applied to the element that is in focus in the **DOM Tree**.</span></span>  

<span data-ttu-id="865aa-190">[ **スタイル** ] ウィンドウについて理解するための重要な概念は、現在選択されているノードのスタイルのみが **DOM ツリー**に表示されることです。</span><span class="sxs-lookup"><span data-stu-id="865aa-190">The key concept to understand about the **Styles** pane is that it only shows styles for the currently-selected node in the **DOM Tree**.</span></span>  <span data-ttu-id="865aa-191">たとえば、ノードのスタイルの検査が終了したのに、ノードのスタイルを確認したいとし `<header>` `<footer>` ます。</span><span class="sxs-lookup"><span data-stu-id="865aa-191">For example, suppose you are done inspecting the styles of a `<header>` node, and now you want to look at the styles for a `<footer>` node.</span></span>  <span data-ttu-id="865aa-192">そのためには、最初に `<footer>` **DOM ツリー**でノードを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="865aa-192">To do that, you first need to select the `<footer>` node in the **DOM Tree**.</span></span>  <span data-ttu-id="865aa-193">「ワークフロー [検査](#inspect-an-element-on-the-page) 」を使用して、ノードの近く (フッター \ などのリンクなど) にあるノードを検査します。これにより、 `footer` **DOM ツリー**がフォーカスされます。次に、キーボードを使用して目的のノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="865aa-193">You may find it faster to use the [Inspect](#inspect-an-element-on-the-page) workflow to inspect a node that is in the general vicinity of the `footer` node \(such as a link within the footer\), which focuses the **DOM Tree**, and then use your keyboard to navigate to the exact node in which you are interested.</span></span>  

#### <span data-ttu-id="865aa-194">[スタイル] ウィンドウ内の移動</span><span class="sxs-lookup"><span data-stu-id="865aa-194">Navigate the Styles pane</span></span>  

<span data-ttu-id="865aa-195">すべてのスタイルツールは、1つの方法で、または別の方法で [ **スタイル** ] ウィンドウに戻るため、最初にこのツールの専門家になることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="865aa-195">Because all of the style tools connect in one way or another back to the **Styles** pane, it makes sense to become an expert in this tool first.</span></span>  

*   <span data-ttu-id="865aa-196">[ **スタイル** ] ウィンドウにフォーカスがある状態で、 `Tab` フォーカスを移動してコンテンツを検索するには、を選択します。</span><span class="sxs-lookup"><span data-stu-id="865aa-196">With focus on the **Styles** pane, select `Tab` to move focus inside and explore the contents.</span></span>  
*   <span data-ttu-id="865aa-197">`Tab`最初のスタイルがアクティブになるまで選択します。</span><span class="sxs-lookup"><span data-stu-id="865aa-197">Select `Tab` until the first style becomes active.</span></span>  <span data-ttu-id="865aa-198">スクリーンリーダーを使用している場合、この最初のスタイルはとしてアナウンスされ `element.style {}` ます。</span><span class="sxs-lookup"><span data-stu-id="865aa-198">If you are using a screen reader this first style is announced as `element.style {}`.</span></span>  
*   <span data-ttu-id="865aa-199">選択 `Down Arrow` すると、スタイルの一覧が目的の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="865aa-199">Select `Down Arrow` to navigate the list of styles in order of specificity.</span></span>  <span data-ttu-id="865aa-200">スクリーンリーダーは、CSS ファイルの名前、スタイルが表示される行番号、スタイルの名前の順に、各スタイルを読み上げます。</span><span class="sxs-lookup"><span data-stu-id="865aa-200">A screen reader announces each style starting with the name of the CSS file, the line number on which the style appears, and the name of the style.</span></span>  <span data-ttu-id="865aa-201">たとえば、`main.css:233 .card__img {}` と記述します。</span><span class="sxs-lookup"><span data-stu-id="865aa-201">For example, `main.css:233 .card__img {}`.</span></span>  
*   <span data-ttu-id="865aa-202">`Enter`スタイルを詳しく調べるには、を選択します。</span><span class="sxs-lookup"><span data-stu-id="865aa-202">Select `Enter` to inspect a style in more detail.</span></span>  <span data-ttu-id="865aa-203">スタイル名の編集可能なバージョンからフォーカスを開始します。</span><span class="sxs-lookup"><span data-stu-id="865aa-203">Focus begins on an editable version of the style name.</span></span>  
*   <span data-ttu-id="865aa-204">`Tab`各 CSS プロパティの編集可能なバージョンと対応する値の間を移動する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="865aa-204">Select `Tab` to move between editable versions of each CSS property and the corresponding values.</span></span>  <span data-ttu-id="865aa-205">各スタイルブロックの末尾には、CSS プロパティを追加するために使用できる空白の編集可能なテキストフィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="865aa-205">At the end of each style block is a blank editable text field which you may use to add additional CSS properties.</span></span>  
*   <span data-ttu-id="865aa-206">引き続き選択し `Tab` てスタイルの一覧を移動するか、を選択して `Escape` モードを終了し、方向キーを使用して移動することができます。</span><span class="sxs-lookup"><span data-stu-id="865aa-206">You may continue to select `Tab` to move through the list of styles, or select `Escape` to exit the mode and go back to navigating by arrow keys.</span></span>  

<span data-ttu-id="865aa-207">その他のショートカットについては、[[スタイル] ウィンドウのキーボードリファレンス] [DevtoolsShortcutsStylesPaneKeyboard] に移動します。</span><span class="sxs-lookup"><span data-stu-id="865aa-207">For additional shortcuts, navigate to [Styles pane keyboard reference][DevtoolsShortcutsStylesPaneKeyboard].</span></span>  

**<span data-ttu-id="865aa-208">既知の問題</span><span class="sxs-lookup"><span data-stu-id="865aa-208">Known issues</span></span>**  

*   <span data-ttu-id="865aa-209">編集可能テキストフィールド **を使用** すると、スタイルのリスト内を移動することはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="865aa-209">If you use the **Filter** editable text field, you are no longer be able to navigate the list of styles.</span></span>  

#### <span data-ttu-id="865aa-210">要素の状態を切り替える</span><span class="sxs-lookup"><span data-stu-id="865aa-210">Toggle element state</span></span>  

<span data-ttu-id="865aa-211">要素の状態を切り替えるには、次のようにし `:active` `:focus` ます。</span><span class="sxs-lookup"><span data-stu-id="865aa-211">To toggle the state of an element, such as `:active` or `:focus`:</span></span>  

1.  <span data-ttu-id="865aa-212">[ **スタイル** ] ウィンドウに移動し `Tab` 、[ **要素の状態の切り替え** ] ボタンにフォーカスが移動するまで選択します。</span><span class="sxs-lookup"><span data-stu-id="865aa-212">Navigate to the **Styles** pane and select `Tab` until the **Toggle Element State** button has focus.</span></span>  
1.  <span data-ttu-id="865aa-213">`Enter`要素の状態のコレクションを展開する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="865aa-213">Select `Enter` to expand the collection of element states.</span></span>  <span data-ttu-id="865aa-214">要素の状態は、チェックボックスのグループとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="865aa-214">The element states are presented as a group of checkboxes.</span></span>  
1.  <span data-ttu-id="865aa-215">`Tab`最初の状態にフォーカスが置かれるまで選択し `:active` ます。</span><span class="sxs-lookup"><span data-stu-id="865aa-215">Select `Tab` until the first state, `:active`, has focus.</span></span>  
1.  <span data-ttu-id="865aa-216">`Space`有効にする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="865aa-216">Select `Space` to enable it.</span></span>  <span data-ttu-id="865aa-217">DOM ツリーで現在選択されている要素にスタイルが設定されている場合 `:active` は、それが適用されます。</span><span class="sxs-lookup"><span data-stu-id="865aa-217">If the currently-selected element in the DOM Tree has an `:active` style, it is now applied.</span></span>  
1.  <span data-ttu-id="865aa-218">保留 `Tab` にして、利用可能なすべての状態を調べます。</span><span class="sxs-lookup"><span data-stu-id="865aa-218">Hold `Tab` to explore all of the available states.</span></span>  

#### <span data-ttu-id="865aa-219">既存のクラスを追加する</span><span class="sxs-lookup"><span data-stu-id="865aa-219">Add an existing class</span></span>  

<span data-ttu-id="865aa-220">**トグル要素の状態**ボタンの横にあるのは、[**要素クラス**] ボタンです。</span><span class="sxs-lookup"><span data-stu-id="865aa-220">Adjacent to the **Toggle Element State** button is the **Element Classes** button.</span></span>  <span data-ttu-id="865aa-221">フォーカスを移動するには、を選択し `Tab` て選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="865aa-221">To move the focus to it, select `Tab` and select `Enter`.</span></span>  <span data-ttu-id="865aa-222">フォーカスは、[ **Add New Class**] というラベルの編集テキストフィールドに移動します。</span><span class="sxs-lookup"><span data-stu-id="865aa-222">Focus moves into an edit text field labeled **Add New Class**.</span></span>  

<span data-ttu-id="865aa-223">[ **要素クラス** ] ボタンは、主に既存のクラスを要素に追加するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="865aa-223">The **Element Classes** button is primarily used for adding existing classes to an element.</span></span>  <span data-ttu-id="865aa-224">たとえば、スタイルシートに、という名前のヘルパークラスが含まれている場合、[ `.clearfix` `.` テキストの編集] フィールドの内側を選択して候補の一覧を表示し、を使用して候補を検索することができ `Down Arrow` `.clearfix` ます。</span><span class="sxs-lookup"><span data-stu-id="865aa-224">For example, if your stylesheet contained a helper class named `.clearfix` you may select `.` inside of the edit text field to see a suggestion list of classes and use the `Down Arrow` to find the `.clearfix` suggestion.</span></span>  <span data-ttu-id="865aa-225">または、クラス名を自分で入力し、それを選択し `Enter` て適用します。</span><span class="sxs-lookup"><span data-stu-id="865aa-225">Or type the class name out yourself and select `Enter` to apply it.</span></span>  

#### <span data-ttu-id="865aa-226">新しいスタイルルールを追加する</span><span class="sxs-lookup"><span data-stu-id="865aa-226">Add a new style rule</span></span>  

<span data-ttu-id="865aa-227">[ **要素クラス** ] ボタンの横には、 **新しい [スタイルルール** ] ボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="865aa-227">Adjacent to the **Element Classes** button is the **New Style Rule** button.</span></span>  <span data-ttu-id="865aa-228">フォーカスを移動するには、を選択し `Tab` て選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="865aa-228">To move the focus to it, select `Tab` and select `Enter`.</span></span>  <span data-ttu-id="865aa-229">フォーカスは、スタイル検査内の編集可能なテキストフィールドに移動します。</span><span class="sxs-lookup"><span data-stu-id="865aa-229">Focus moves into an editable text field inside of the style inspector.</span></span>  <span data-ttu-id="865aa-230">フィールドの最初のテキストのコンテンツは、 **DOM ツリー**で選択された要素のタグ名です。</span><span class="sxs-lookup"><span data-stu-id="865aa-230">The initial text content of the field is the tag name of the element that is selected in the **DOM Tree**.</span></span>  
<span data-ttu-id="865aa-231">このフィールドに任意のクラス名を入力して、CSS プロパティを割り当てることができ `Tab` ます。</span><span class="sxs-lookup"><span data-stu-id="865aa-231">You may type any class name you want into this field and then select `Tab` to assign CSS properties to it.</span></span>  

### <span data-ttu-id="865aa-232">[計算] タブ</span><span class="sxs-lookup"><span data-stu-id="865aa-232">Computed tab</span></span>  

<span data-ttu-id="865aa-233">[ **計算** ] タブにフォーカスがある状態で、 `Tab` フォーカスを移動してコンテンツを検索するには、を選択します。</span><span class="sxs-lookup"><span data-stu-id="865aa-233">With focus on the **Computed** tab, select `Tab` to move focus inside and explore the contents.</span></span>  <span data-ttu-id="865aa-234">[ **計算** ] タブでは、要素に実際に適用される CSS プロパティを調査するためのコントロールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="865aa-234">Within the **Computed** tab there are controls for exploring which CSS properties are actually applied to an element in order of specificity.</span></span>  

<!--todo: add computed tab section when available  -->  

#### <span data-ttu-id="865aa-235">計算されたスタイルをすべて調べる</span><span class="sxs-lookup"><span data-stu-id="865aa-235">Explore all computed styles</span></span>  

<span data-ttu-id="865aa-236">`Tab`計算されたスタイルのコレクションに到達するまで選択します。</span><span class="sxs-lookup"><span data-stu-id="865aa-236">Select `Tab` until you reach the collection of computed styles.</span></span>  <span data-ttu-id="865aa-237">これらは [ARIA ツリー][W3CWaiAriaTree]として表示されます。</span><span class="sxs-lookup"><span data-stu-id="865aa-237">These are presented as an [ARIA tree][W3CWaiAriaTree].</span></span>  <span data-ttu-id="865aa-238">Listbox を展開すると、計算されたスタイルを適用している CSS セレクターが示されます。</span><span class="sxs-lookup"><span data-stu-id="865aa-238">Expanding a listbox reveals which CSS selectors are applying the computed style.</span></span>  <span data-ttu-id="865aa-239">これらのセレクターは、特異性によって整理されます。</span><span class="sxs-lookup"><span data-stu-id="865aa-239">These selectors are organized by specificity.</span></span>  <span data-ttu-id="865aa-240">スクリーンリーダーは、計算値、現在一致している CSS セレクター、セレクターを含むスタイルシートのファイル名、セレクターの行番号を通知します。</span><span class="sxs-lookup"><span data-stu-id="865aa-240">A screen reader announces the computed value, which CSS selector is currently matching, the filename of the stylesheet that contains the selector, and the line number for the selector.</span></span>  

**<span data-ttu-id="865aa-241">既知の問題</span><span class="sxs-lookup"><span data-stu-id="865aa-241">Known issues</span></span>**  

*   <span data-ttu-id="865aa-242">**フィルター**テキストフィールドを使用する場合、スタイルを検査することはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="865aa-242">If you use the **Filter** text field, you are no longer able to inspect styles.</span></span>  

### <span data-ttu-id="865aa-243">[イベントリスナー] タブ</span><span class="sxs-lookup"><span data-stu-id="865aa-243">Event listeners tab</span></span>  

<span data-ttu-id="865aa-244">[ **要素** ] パネルで、[ **イベントリスナー** ] タブを使って、要素に適用されているイベントリスナーを調べることができます。 [ **スタイル** ] ウィンドウにフォーカスがある状態で、を選択して [ `Right Arrow` **イベントリスナー** ] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="865aa-244">From within the **Elements** panel you may inspect the event listeners applied to an element using the **Event Listeners** tab.  With focus on the **Styles** pane, select the `Right Arrow` to navigate to the **Event Listeners** tab.</span></span>  

#### <span data-ttu-id="865aa-245">イベントリスナーを調べる</span><span class="sxs-lookup"><span data-stu-id="865aa-245">Explore event listeners</span></span>  

<span data-ttu-id="865aa-246">イベントリスナーは、 [ARIA ツリー][W3CWaiAriaTree]として表示されます。</span><span class="sxs-lookup"><span data-stu-id="865aa-246">Event listeners are presented as an [ARIA tree][W3CWaiAriaTree].</span></span>  <span data-ttu-id="865aa-247">方向キーを使用して移動することができます。</span><span class="sxs-lookup"><span data-stu-id="865aa-247">You may use the arrow keys to navigate them.</span></span>  <span data-ttu-id="865aa-248">スクリーンリーダーは、イベントリスナーがアタッチされている DOM オブジェクトの名前に加えて、イベントリスナーが定義されているファイル名と行番号を通知します。</span><span class="sxs-lookup"><span data-stu-id="865aa-248">A screen reader announces the name of the DOM object that the event listener is attached to, as well as the file name where the event listener is defined and the line number.</span></span>  

### <span data-ttu-id="865aa-249">アクセシビリティウィンドウ</span><span class="sxs-lookup"><span data-stu-id="865aa-249">Accessibility pane</span></span>  

<span data-ttu-id="865aa-250">[ **アクセシビリティ** ] ウィンドウにフォーカスがある状態で、 `Tab` フォーカスを移動してコンテンツを検索するには、を選択します。</span><span class="sxs-lookup"><span data-stu-id="865aa-250">With focus on the **Accessibility** pane, select `Tab` to move focus inside and explore the contents.</span></span>  <span data-ttu-id="865aa-251">[ [アクセシビリティ] ウィンドウ][DevtoolsAccessibilityReference] には、アクセシビリティツリー、要素に適用される ARIA 属性、計算されたアクセシビリティプロパティを調べるためのコントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="865aa-251">On the [Accessibility pane][DevtoolsAccessibilityReference] there are controls for exploring the accessibility tree, the ARIA attributes applied to an element, and the computed accessibility properties.</span></span>  

#### <span data-ttu-id="865aa-252">アクセシビリティツリー</span><span class="sxs-lookup"><span data-stu-id="865aa-252">Accessibility Tree</span></span>  

<span data-ttu-id="865aa-253">**アクセシビリティツリー**は、それぞれが DOM の要素に対応する[ARIA ツリー][W3CWaiAriaTree]として表示され `treeitem` ます。</span><span class="sxs-lookup"><span data-stu-id="865aa-253">The **Accessibility Tree** is presented as an [ARIA tree][W3CWaiAriaTree] where each `treeitem` corresponds to an element in the DOM.</span></span>  <span data-ttu-id="865aa-254">ツリーは、選んだノードの計算された役割を通知します。</span><span class="sxs-lookup"><span data-stu-id="865aa-254">The tree announces the computed role for the selected node.</span></span>  <span data-ttu-id="865aa-255">などの一般的な要素 `div` `span` は、ツリーの "genericcontainer" としてアナウンスされます。</span><span class="sxs-lookup"><span data-stu-id="865aa-255">Generic elements like `div` and `span` are announced as "GenericContainer" in the tree.</span></span>  <span data-ttu-id="865aa-256">方向キーを使用してツリーを走査し、親子関係を調べます。</span><span class="sxs-lookup"><span data-stu-id="865aa-256">Use the arrow keys to traverse the tree and explore parent-child relationships.</span></span>  

**<span data-ttu-id="865aa-257">既知の問題</span><span class="sxs-lookup"><span data-stu-id="865aa-257">Known issues</span></span>**  

*   <span data-ttu-id="865aa-258">**アクセシビリティ**ウィンドウで使用される[ARIA ツリー][W3CWaiAriaTree]の種類は、VoiceOver のような macOS のスクリーンリーダーでは Microsoft Edge で適切に公開されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="865aa-258">The type of [ARIA tree][W3CWaiAriaTree] used by the **Accessibility** pane may not be properly exposed in Microsoft Edge for macOS screen readers like VoiceOver.</span></span>  <span data-ttu-id="865aa-259">この問題の進捗状況について通知を受け取るには、 [Chromium の問題 #868480][ChromiumIssues868480] をサブスクライブしてください。</span><span class="sxs-lookup"><span data-stu-id="865aa-259">Subscribe to [Chromium issue #868480][ChromiumIssues868480] to be informed about progress on this issue.</span></span>  
*   <span data-ttu-id="865aa-260">Aria の各 **属性** と計算された **プロパティ** のセクションは [aria ツリー][W3CWaiAriaTree]としてマークされますが、現在はフォーカス管理がなく、キーボード操作ができません。</span><span class="sxs-lookup"><span data-stu-id="865aa-260">Each of the **ARIA Attributes** and **Computed Properties** sections are marked up as an [ARIA tree][W3CWaiAriaTree], but each does not currently have focus management and is not keyboard operable.</span></span>  

## <span data-ttu-id="865aa-261">監査パネル</span><span class="sxs-lookup"><span data-stu-id="865aa-261">Audits panel</span></span>  

<span data-ttu-id="865aa-262">**監査**パネルでは、パフォーマンス、アクセシビリティ、SEO、その他のカテゴリの多くに関連する一般的な問題をチェックするために、サイトに対して一連のテストを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="865aa-262">The **Audits** panel you should run a series of tests against a site to check for common issues related to performance, accessibility, SEO, and a number of other categories.</span></span>  

### <span data-ttu-id="865aa-263">監査を構成して実行する</span><span class="sxs-lookup"><span data-stu-id="865aa-263">Configure and run an audit</span></span>  

1.  <span data-ttu-id="865aa-264">**監査**パネルを最初に開いたときに、フォームの最後にある [**監査の実行**] ボタンにフォーカスが置かれます。</span><span class="sxs-lookup"><span data-stu-id="865aa-264">When the **Audits** panel is first opened, focus is placed on the **Run Audit** button at the end of the form.</span></span>  <span data-ttu-id="865aa-265">既定では、シミュレートされた3G 接続でモバイルエミュレーションを使用して、すべてのカテゴリの監査を実行するようにフォームが構成されています。</span><span class="sxs-lookup"><span data-stu-id="865aa-265">By default the form is configured to run audits for every category using mobile emulation on a simulated 3G connection.</span></span>  
1.  <span data-ttu-id="865aa-266">`Shift` + `Tab` 監査設定を変更するには、[参照] モードを使うか、もう一度移動します。</span><span class="sxs-lookup"><span data-stu-id="865aa-266">Use `Shift`+`Tab` or navigate back in Browse mode to change the audit settings.</span></span>  
1.  <span data-ttu-id="865aa-267">監査を実行する準備ができたら、[ **監査の実行** ] ボタンに戻り、を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="865aa-267">When you are ready to run the audit, navigate back to the **Run Audit** button and select `Enter`.</span></span>  
1.  <span data-ttu-id="865aa-268">フォーカスが **[キャンセル** ] ボタンでモーダルウィンドウに移動し、監査を終了することができます。</span><span class="sxs-lookup"><span data-stu-id="865aa-268">Focus moves into a modal window with a **Cancel** button which allows you to exit the audit.</span></span>  <span data-ttu-id="865aa-269">監査が実行され、ページが複数回更新されると、一連の考えが何度も発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="865aa-269">You may hear a series of earcons as the audit runs and refreshes the page multiple times.</span></span>  

**<span data-ttu-id="865aa-270">既知の問題</span><span class="sxs-lookup"><span data-stu-id="865aa-270">Known issues</span></span>**  

*   <span data-ttu-id="865aa-271">構成フォームのセクションは、現在、要素でマークアップされていません `fieldset` 。</span><span class="sxs-lookup"><span data-stu-id="865aa-271">The different sections of the configuration form are not currently marked up with a `fieldset` element.</span></span>  <span data-ttu-id="865aa-272">各セクションに関連付けられているコントロールを確認するために、参照モードで移動した方が簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="865aa-272">It may be easier to navigate them in Browse mode to figure out which controls are associated with each section.</span></span>  
*   <span data-ttu-id="865aa-273">監査の実行が完了しても、現在のところ、またはライブリージョンのお知らせはありません。</span><span class="sxs-lookup"><span data-stu-id="865aa-273">There is no earcon or live region announcement when the audit is finished running.</span></span>  <span data-ttu-id="865aa-274">通常、30秒ほどかかります。その後、結果に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="865aa-274">Generally it takes about 30 seconds, after which you should be able to navigate to the results.</span></span>  <span data-ttu-id="865aa-275">検索結果を表示するには、参照モードを使用する方法が最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="865aa-275">Using Browse mode may be the easiest way to reach the results.</span></span>  

### <span data-ttu-id="865aa-276">監査レポート内を移動する</span><span class="sxs-lookup"><span data-stu-id="865aa-276">Navigate the audit report</span></span>  

<span data-ttu-id="865aa-277">監査レポートは、各監査カテゴリに対応するセクションに整理されます。</span><span class="sxs-lookup"><span data-stu-id="865aa-277">The audit report is organized into sections that correspond with each of the audit categories.</span></span>  <span data-ttu-id="865aa-278">レポートが開き、各カテゴリのスコアの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="865aa-278">The report opens with a list of scores for each category.</span></span>  <span data-ttu-id="865aa-279">これらのスコアは、関連するセクションにスキップするために使用できるリンクでもあります。</span><span class="sxs-lookup"><span data-stu-id="865aa-279">These scores are also links which are able to be used to skip to the relevant sections.</span></span>  <span data-ttu-id="865aa-280">各セクション内には `details` 、成功または失敗の監査に関連する情報が含まれている拡張可能な要素があります。</span><span class="sxs-lookup"><span data-stu-id="865aa-280">Within each section are expandable `details` elements, which contain information relating to passed or failed audits.</span></span>  <span data-ttu-id="865aa-281">既定では、失敗した監査のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="865aa-281">By default, only failing audits are shown.</span></span>  <span data-ttu-id="865aa-282">各セクションは、 `details` 成功したすべての監査を含む最終要素で終わります。</span><span class="sxs-lookup"><span data-stu-id="865aa-282">Each section ends with a final `details` element which contains all of the passed audits.</span></span>  

<span data-ttu-id="865aa-283">新しい監査を実行するには、を使用して `Shift` + `Tab` レポートを終了し、[**監査の実行**] ボタンを探します。</span><span class="sxs-lookup"><span data-stu-id="865aa-283">To run a new audit, use `Shift`+`Tab` to exit the report and look for the **Perform An Audit** button.</span></span>  

## <span data-ttu-id="865aa-284">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="865aa-284">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsAccessibilityReference]: ./reference.md "アクセシビリティリファレンス |Microsoft ドキュメント"  
[DevtoolsAccessibilityReferencePane]: reference.md#the-accessibility-pane "アクセシビリティウィンドウ-アクセシビリティリファレンス |Microsoft ドキュメント"  
[MicrosoftEdgeDevtoolsMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevtoolsCommandMenuIndex]: ../command-menu/index.md "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する |Microsoft ドキュメント"  
[DevtoolsConsoleIndex]: ../console/index.md "本体の概要 |Microsoft ドキュメント"  
[DevtoolsCssIndex]: ../css/index.md "CSS の表示と変更の概要 |Microsoft ドキュメント"  
<!--[DevtoolsCssReferenceViewAppliedElement]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "CSS Reference - View only the CSS that is actually applied to an element | Microsoft Docs"  -->  
<!--[DevtoolsDomIndex]: ../dom/index.md "Get started with viewing and changing the DOM | Microsoft Docs"  -->  
[DevtoolsDomIndexViewDomNodes]: ..[dom/index¥ md # view-dom-ノードの表示]: DOM ノードの表示と変更を開始します。Microsoft ドキュメント "  
[DevtoolsDomIndexNavigateDomTreeKeyboard]: ../dom# md #-------------------------------------------------------------Microsoft ドキュメント "  
[DevtoolsOpen]:../open.md "Microsoft Edge DevTools を開く |Microsoft ドキュメント "  
<span data-ttu-id="865aa-294">[Dev[キーボードショートカット]:.../shortcuts.md "Microsoft Edge DevTools のショートカットキー |Microsoft ドキュメント "</span><span class="sxs-lookup"><span data-stu-id="865aa-294">[DevtoolsShortcuts]: ../shortcuts.md "Microsoft Edge DevTools Keyboard Shortcuts | Microsoft Docs"</span></span>  
[DevtoolsShortcutsStylesPaneKeyboard]: ../shortcuts.md # styles-ウィンドウ-キーボードショートカット "[スタイル] ウィンドウのキーボードショートカット-Microsoft Edge DevTools のキーボードショートカット |Microsoft ドキュメント "  

[ChromiumIssues868480]: https://bugs.chromium.org/p/chromium/issues/detail?id=868480 "問題 868480-ARIA ツリーを Mac アクセシビリティの表として公開する"  

[GithubEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Docs%20Feedback%5D "新しい問題-Microsoft のドキュメント/エッジ-開発者 |GitHub"  

[MDNActive]: https://developer.mozilla.org/docs/Web/CSS/:active ": active |MDN"  
[MDNFocus]: https://developer.mozilla.org/docs/Web/CSS/:focus ": フォーカス |MDN"  

[MonorailChromiumIssues]: https://crbug.com "問題-chromium"  

[W3CWaiAriaTablist]: https://www.w3.org/TR/wai-aria-1.1/#tablist "tablist (役割)-アクセシビリティの高いリッチインターネットアプリケーション (WAI-ARIA 使った-ARIA) 1.1 |勧告"  
[W3CWaiAriaTree]: https://www.w3.org/TR/wai-aria-1.1/#tree "tree (役割)-アクセシビリティの高いリッチインターネットアプリケーション (WAI-ARIA 使った-ARIA) 1.1 |勧告"  

> [!NOTE]
> <span data-ttu-id="865aa-303">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="865aa-303">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="865aa-304">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation) にあり、 [渡 Dodson][RobDodson] によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="865aa-304">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation) and is authored by [Rob Dodson][RobDodson] \(Contributor, Google WebFundamentals\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="865aa-306">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="865aa-306">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[RobDodson]: https://developers.google.com/web/resources/contributors/robdodson  
