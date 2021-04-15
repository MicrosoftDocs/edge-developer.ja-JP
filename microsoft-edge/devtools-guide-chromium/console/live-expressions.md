---
description: コンソールに同じ JavaScript 式を繰り返し入力する場合は、代わりに Live 式を試してください。
title: Live 式を使用して JavaScript 式の値をリアルタイムで確認する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 51b7aa5119775f43861a84c1055ac9149a626d8a
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483143"
---
# <a name="monitor-changes-in-javascript-using-live-expressions"></a><span data-ttu-id="b73d1-104">Live 式を使用して JavaScript の変更を監視する</span><span class="sxs-lookup"><span data-stu-id="b73d1-104">Monitor changes in JavaScript using Live Expressions</span></span>  

<span data-ttu-id="b73d1-105">**Live 式は** 、多くの変更を行う JavaScript 式を監視する優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="b73d1-105">**Live Expressions** are an excellent way to monitor JavaScript expressions that change a lot.</span></span>    <span data-ttu-id="b73d1-106">読み取りおよび移動する多くのコンソール メッセージを持つ代わりに、特定の JavaScript 式をコンソールの上部にピン留め **することもできます**。</span><span class="sxs-lookup"><span data-stu-id="b73d1-106">Instead of having many Console messages to read and navigate, you may pin your specific JavaScript expressions to the top of the **Console**.</span></span>  

## <a name="add-a-new-live-expression"></a><span data-ttu-id="b73d1-107">新しいライブ式を追加する</span><span class="sxs-lookup"><span data-stu-id="b73d1-107">Add a new live expression</span></span>  

<span data-ttu-id="b73d1-108">開始するには、[フィルター] **テキスト ボックスの** 横にある [ライブ式の作成] \(eye\) **ボタンを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="b73d1-108">To start, choose the **Create live expression** \(eye\) button next to the **Filter** textbox.</span></span>  <span data-ttu-id="b73d1-109">選択すると、新しい式を入力するテキスト ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b73d1-109">After you choose it, a textbox is displayed for you to enter your new expression in it.</span></span>  

:::image type="complex" source="../media/console-live-expressions-new.msft.png" alt-text="[新しいライブ式] ボタンを選択してテキスト ボックスを開き、式を入力します。" lightbox="../media/console-live-expressions-new.msft.png":::
    <span data-ttu-id="b73d1-111">式を `New live expression` 入力するテキスト ボックスを開くボタンを選択する</span><span class="sxs-lookup"><span data-stu-id="b73d1-111">Choose the `New live expression` button to open a textbox to type an expression</span></span>  
:::image-end:::  

<span data-ttu-id="b73d1-112">**Live 式には** 、任意の有効な JavaScript 式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b73d1-112">**Live Expressions** may be any valid JavaScript expression.</span></span>  <span data-ttu-id="b73d1-113">これを試す場合は、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="b73d1-113">To try it, complete the following actions.</span></span>  

1.  <span data-ttu-id="b73d1-114">[Live **式] テキスト ボックスを** 開きます。</span><span class="sxs-lookup"><span data-stu-id="b73d1-114">Open the **Live Expression** textbox.</span></span>  
1.  <span data-ttu-id="b73d1-115">「`document.activeElement`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="b73d1-115">Type `document.activeElement`.</span></span>  
1.  <span data-ttu-id="b73d1-116">式を保存するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b73d1-116">To save the expression, complete one of the following actions.</span></span>  
    *   <span data-ttu-id="b73d1-117">`Control` + `Enter` \(Windows, Linux\) または `Command` + `Enter` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="b73d1-117">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\).</span></span>  
    *   <span data-ttu-id="b73d1-118">[Live 式] **テキスト ボックスの外側を** 選択します。</span><span class="sxs-lookup"><span data-stu-id="b73d1-118">Choose outside the **Live Expression** textbox.</span></span>  
        
<span data-ttu-id="b73d1-119">式がライブで表示され、 `body` 結果として表示されます。</span><span class="sxs-lookup"><span data-stu-id="b73d1-119">The expression is now live and displays `body` as the result.</span></span>  

:::image type="complex" source="../media/console-live-expressions-document-active-element.msft.png" alt-text="document.activeElement の Live 式は、結果として本文を表示します。" lightbox="../media/console-live-expressions-document-active-element.msft.png":::
    <span data-ttu-id="b73d1-121">結果として本文 `document.activeElement` を表示するライブ式</span><span class="sxs-lookup"><span data-stu-id="b73d1-121">Live expression for `document.activeElement` displays body as the result</span></span>  
:::image-end:::  

<span data-ttu-id="b73d1-122">Web ページを移動すると、値が変更されます。</span><span class="sxs-lookup"><span data-stu-id="b73d1-122">If you navigate around the webpage, the value changes.</span></span>  <span data-ttu-id="b73d1-123">たとえば、次の図では、Web ページで検索メニューを開き、式が値 `button.nav-bar-button.focus-visible` として表示されます。</span><span class="sxs-lookup"><span data-stu-id="b73d1-123">For example, in the following figure you open the search menu in the webpage and the expression now displays `button.nav-bar-button.focus-visible` as the value.</span></span>  

:::image type="complex" source="../media/console-live-expressions-document-active-element-nav-button.msft.png" alt-text="Live 式の値を変更するには、Web ページ上の異なる要素を操作します。" lightbox="../media/console-live-expressions-document-active-element-nav-button.msft.png":::
    <span data-ttu-id="b73d1-125">Live 式の値を **変更するには、Web**ページ上の異なる要素を操作します。</span><span class="sxs-lookup"><span data-stu-id="b73d1-125">To change the value of the **Live Expression**, interact with different elements on the webpage</span></span>  
:::image-end:::  

<span data-ttu-id="b73d1-126">値を再度変更するには、Web ページの [検索] テキスト ボックスを開いて選択します。</span><span class="sxs-lookup"><span data-stu-id="b73d1-126">To change the value again, open and choose the Search textbox on the webpage.</span></span>  

:::image type="complex" source="../media/console-live-expressions-document-active-element-search.msft.png" alt-text="Web ページ内の別の要素に移動して Live 式を更新する" lightbox="../media/console-live-expressions-document-active-element-search.msft.png":::
    <span data-ttu-id="b73d1-128">Web ページ内の別の要素に移動して Live **式を更新する**</span><span class="sxs-lookup"><span data-stu-id="b73d1-128">Navigate to a different element in the webpage to update the **Live Expression**</span></span>  
:::image-end:::  

## <a name="remove-live-expressions"></a><span data-ttu-id="b73d1-129">ライブ式の削除</span><span class="sxs-lookup"><span data-stu-id="b73d1-129">Remove Live Expressions</span></span>  

<span data-ttu-id="b73d1-130">Live **式は** 、アクティブにしている限り使用できます。</span><span class="sxs-lookup"><span data-stu-id="b73d1-130">A **Live Expression** is available as long as you keep it active.</span></span>  <span data-ttu-id="b73d1-131">Live 式を削除 **するには**、その横 `x` にある式を選択します。</span><span class="sxs-lookup"><span data-stu-id="b73d1-131">To get rid of a **Live Expression**, choose the `x` next to it.</span></span>  

:::image type="complex" source="../media/console-live-expressions-remove.msft.png" alt-text="Live 式を削除するには、その横にある x を選択します。" lightbox="../media/console-live-expressions-remove.msft.png":::
    <span data-ttu-id="b73d1-133">Live 式 **を削除するには**、その横 `x` にある式を選択します。</span><span class="sxs-lookup"><span data-stu-id="b73d1-133">To remove **Live Expressions**, choose the `x` next to it</span></span>  
:::image-end:::  

## <a name="replace-console-logging-with-live-expressions"></a><span data-ttu-id="b73d1-134">コンソール ログを Live 式に置き換える</span><span class="sxs-lookup"><span data-stu-id="b73d1-134">Replace Console logging with Live Expressions</span></span>  

<span data-ttu-id="b73d1-135">必要な数の式を作成し、ブラウザー セッションとウィンドウ間で各式を保持できます。</span><span class="sxs-lookup"><span data-stu-id="b73d1-135">You may create as many expressions as you want and persist each across browser sessions and windows.</span></span>  <span data-ttu-id="b73d1-136">**Live 式** は、デバッグ ワークフローのノイズを削減する方法です。</span><span class="sxs-lookup"><span data-stu-id="b73d1-136">**Live Expressions** are a way to cut down on noise in your debugging workflow.</span></span>  

<span data-ttu-id="b73d1-137">たとえば、現在の Web ページでマウスの動きを監視します。</span><span class="sxs-lookup"><span data-stu-id="b73d1-137">For example, you want to monitor the mouse movement in the current webpage.</span></span>  <span data-ttu-id="b73d1-138">[ログ マウス [の移動] デモに][GithubMicrosoftedgeDevtoolssamplesConsoleMousemoveHtml]移動し、 **コンソール**を開き、マウスを動かして、多くの情報を含むログを表示します。</span><span class="sxs-lookup"><span data-stu-id="b73d1-138">Navigate to [Logging Mouse Movement demo][GithubMicrosoftedgeDevtoolssamplesConsoleMousemoveHtml], open the **Console**, and move your mouse around to display the logs with a lot of information.</span></span>  

:::image type="complex" source="../media/console-live-expression-mouse-logging.msft.png" alt-text="コンソールはマウスの位置に関する多くの情報を表示します" lightbox="../media/console-live-expression-mouse-logging.msft.png":::
    <span data-ttu-id="b73d1-140">**コンソールは** マウスの位置に関する多くの情報を表示します</span><span class="sxs-lookup"><span data-stu-id="b73d1-140">**Console** displays much information on mouse position</span></span>  
:::image-end:::  

<span data-ttu-id="b73d1-141">大量の情報はデバッグ プロセスを遅くするだけでなく、確認する変更を見逃しがちです。</span><span class="sxs-lookup"><span data-stu-id="b73d1-141">The large amount of information not only slows your debug process, but also makes it easy to miss the changes you want to review.</span></span>  <span data-ttu-id="b73d1-142">コンソールにより **多くの** メッセージが表示され、マウスを移動すると、確認する値が画面をスクロールオフします。</span><span class="sxs-lookup"><span data-stu-id="b73d1-142">As the **Console** displays more messages and you move your mouse, the values you want to review scroll off the screen.</span></span>  

<span data-ttu-id="b73d1-143">別の **方法として Live 式** を試す場合は、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="b73d1-143">To try **Live Expressions** as an alternative, complete the following actions.</span></span>  

1.  <span data-ttu-id="b73d1-144">ログデモなしで [マウスの動きに移動します][GithubMicrosoftedgeDevtoolssamplesConsoleMouseNoLogHtml]。</span><span class="sxs-lookup"><span data-stu-id="b73d1-144">Navigate to the [Mouse movement without logging demo][GithubMicrosoftedgeDevtoolssamplesConsoleMouseNoLogHtml].</span></span>  
1.  <span data-ttu-id="b73d1-145">の **Live 式を作成** `x` します `y` 。</span><span class="sxs-lookup"><span data-stu-id="b73d1-145">Create **Live Expressions** for `x` and `y`.</span></span>  
    
<span data-ttu-id="b73d1-146">Live Expressions を**使用する場合**は、常に画面の同じ部分に情報を\*\*\*\* 取得し、あまり変更しない値のコンソール ログを保持します。</span><span class="sxs-lookup"><span data-stu-id="b73d1-146">When you use **Live Expressions**, you always get the information on the same part of your screen and keep **Console** logs for values that don't change as much.</span></span>

:::image type="complex" source="../media/console-live-expressions-x-and-y.msft.png" alt-text="マウスの x 位置と y 位置を Live 式として表示する" lightbox="../media/console-live-expressions-x-and-y.msft.png":::
    <span data-ttu-id="b73d1-148">マウスの位置を Live 式 `x` `y` **として表示する**</span><span class="sxs-lookup"><span data-stu-id="b73d1-148">Display the `x` and `y` position of the mouse as **Live Expressions**</span></span>  
:::image-end:::  

<span data-ttu-id="b73d1-149">**Live Expressions** はコンピューター上で排他的に実行され、表示するコード内で何も変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b73d1-149">**Live Expressions** run exclusively on your computer and you don't need to change anything in your code to display.</span></span>  <span data-ttu-id="b73d1-150">**Live 式** は、デバッグする情報のみを表示するための最適な方法です。</span><span class="sxs-lookup"><span data-stu-id="b73d1-150">**Live Expressions** are a great way to ensure that you only display the information you want to debug.</span></span>  <span data-ttu-id="b73d1-151">また **、Live Expressions を使用** すると、ユーザーのコンピューターのノイズを制限できます。</span><span class="sxs-lookup"><span data-stu-id="b73d1-151">Also, **Live Expressions** help you limit the noise on your users' computers.</span></span>

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="b73d1-152">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="b73d1-152">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[GithubMicrosoftedgeDevtoolssamplesConsoleMousemoveHtml]: https://microsoftedge.github.io/DevToolsSamples/console/mousemove.html "コンソール メッセージの例: テーブル の使用|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleMouseNoLogHtml]: https://microsoftedge.github.io/DevToolsSamples/console/mousemove-no-log.html "ログを記録せずにマウス|GitHub"  
