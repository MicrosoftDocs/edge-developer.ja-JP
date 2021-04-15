---
description: コンソール メッセージをフィルター処理する方法について説明します。
title: コンソールでのメッセージのフィルター処理の開始
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: b493bb790b48bc1c4dca0e6802d2f638099b7644
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483553"
---
# <a name="filter-console-messages"></a><span data-ttu-id="6f7d5-104">コンソール メッセージのフィルター</span><span class="sxs-lookup"><span data-stu-id="6f7d5-104">Filter Console messages</span></span>  

<span data-ttu-id="6f7d5-105">Web をサーフィンすると、コンソール **にあらゆる種類** の情報が殺到している場合があります。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-105">When you surf the web, you may find the **Console** is flooded with all kinds of information.</span></span>  <span data-ttu-id="6f7d5-106">多くの場合、情報はユーザーに関係ありません。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-106">Often the information isn't relevant to you.</span></span>  <span data-ttu-id="6f7d5-107">デバッグ中に別の開発者がログに記録したライブ プロジェクトに関する情報など。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-107">Such as information about the live project that another developer logged while you debug.</span></span>  <span data-ttu-id="6f7d5-108">または、変更できない現在のサイトのパフォーマンスに関する違反と警告に関する詳細。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-108">Or more information about violations and warnings about the performance of the current site that you aren't able to change.</span></span>  <span data-ttu-id="6f7d5-109">コンソールのフィルター オプションを使用してノイズを **低減するの** も理にかなっています。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-109">It makes sense to use the filter options of **Console** to reduce the noise.</span></span>  

## <a name="filter-by-log-level"></a><span data-ttu-id="6f7d5-110">ログ レベルでフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="6f7d5-110">Filter by log level</span></span>  

<span data-ttu-id="6f7d5-111">オブジェクトの各メソッド `console` には、重大度レベルが関連付けされています。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-111">Each method of the `console` object has a severity level attached to it.</span></span>  <span data-ttu-id="6f7d5-112">重大度レベルは `Verbose` `Info` `Warning` 、、またはです `Error` 。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-112">The severity levels are `Verbose`, `Info`, `Warning`, or `Error`.</span></span>  <span data-ttu-id="6f7d5-113">API ドキュメントに重大度レベルを [表示します][DevtoolsConsoleApi]。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-113">Display the severity levels in the [API documentation][DevtoolsConsoleApi].</span></span>  <span data-ttu-id="6f7d5-114">たとえば `console.log()` 、-level `Info` メッセージですが `console.error()` `Error` 、-level メッセージです。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-114">For example, `console.log()` is an `Info`-level message, but `console.error()` is an `Error`-level message.</span></span>  

<span data-ttu-id="6f7d5-115">コンソールでメッセージをフィルター処理 **するには**、[ログ レベル **] ドロップダウン メニューを** 使用します。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-115">To filter messages in the **Console**, use the **Log Level** dropdown menu.</span></span>  <span data-ttu-id="6f7d5-116">各レベルの状態を切り替えできます。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-116">You may toggle the state of each level.</span></span>  <span data-ttu-id="6f7d5-117">各レベルをオフにするには、各レベルの横にあるチェックマークを削除します。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-117">To turn off each level, remove the checkmark next to each.</span></span>  

:::image type="complex" source="../media/console-filter-dropdown.msft.png" alt-text="ドロップダウン メニューは、ログ レベルを使用してコンソール メッセージをフィルター処理します。" lightbox="../media/console-filter-dropdown.msft.png":::
    <span data-ttu-id="6f7d5-119">ドロップダウン メニューは、ログ **レベルを使用** してコンソール メッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-119">The dropdown menu filters **Console** messages using the log level</span></span>  
:::image-end:::  

<span data-ttu-id="6f7d5-120">フィルターは適用されませんので、次の図は数十のメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-120">Since no filter is applied, the following figure displays dozens of messages.</span></span>  <span data-ttu-id="6f7d5-121">次に、メッセージの数を減らして管理します。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-121">Next, reduce and manage the number of messages.</span></span>  

:::image type="complex" source="../media/console-filter-displays-all.msft.png" alt-text="フィルター セットがない場合は、多くのコンソール メッセージが表示される可能性があります。" lightbox="../media/console-filter-displays-all.msft.png":::
    <span data-ttu-id="6f7d5-123">フィルター セットがない場合は、多くのコンソール メッセージが表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-123">No filter set means you may display many console messages</span></span>  
:::image-end:::  

<span data-ttu-id="6f7d5-124">すべての警告レベルのメッセージを非表示にし、ノイズを減らします。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-124">Choose to hide all the Warning-level messages to cut down on the noise.</span></span>  <span data-ttu-id="6f7d5-125">[ログ レベル] **ドロップダウンに移動** し、レベルのチェックを外 `Warnings` します。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-125">Navigate to the **Log Levels** dropdown and uncheck the `Warnings` level.</span></span>  

:::image type="complex" source="../media/console-filter-hide-warning.msft.png" alt-text="コンソール内のすべての警告レベルメッセージを非表示にし、ノイズの多くをフィルター処理する" lightbox="../media/console-filter-hide-warning.msft.png":::
    <span data-ttu-id="6f7d5-127">コンソール内のすべての警告レベルメッセージを非表示 **にし** 、ノイズの多くをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="6f7d5-127">Hide all the warning level messages in the **Console** to filter much of the noise</span></span>  
:::image-end:::  

## <a name="filter-by-text"></a><span data-ttu-id="6f7d5-128">テキストによるフィルター</span><span class="sxs-lookup"><span data-stu-id="6f7d5-128">Filter by text</span></span>  

<span data-ttu-id="6f7d5-129">詳細を確認する場合は、テキストを使用してメッセージをフィルター処理するには、[フィルター] テキスト ボックスに文字列 **を** 入力します。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-129">If you want to review more detail, to filter messages using text, type a string into the **Filter** textbox.</span></span>  <span data-ttu-id="6f7d5-130">たとえば、リソースの読み込みをブロックしているブラウザーに関するメッセージのみを表示するには、ボックス `block` に入力します。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-130">For example, type `block` into the box to only display your messages about the browser blocking resources from loading.</span></span>

:::image type="complex" source="../media/console-filter-text.msft.png" alt-text="単語ブロックを含むメッセージを表示します。" lightbox="../media/console-filter-text.msft.png":::
    <span data-ttu-id="6f7d5-132">単語を含むメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-132">Displays the messages that contain the word</span></span> `block`  
:::image-end:::  

## <a name="filter-by-regular-expression"></a><span data-ttu-id="6f7d5-133">正規表現によるフィルター</span><span class="sxs-lookup"><span data-stu-id="6f7d5-133">Filter by regular expression</span></span>

<span data-ttu-id="6f7d5-134">[正規表現は、][MdnDocsWebJavascriptGuideRegularExpressions] メッセージをフィルター処理する強力な方法です。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-134">[Regular expressions][MdnDocsWebJavascriptGuideRegularExpressions] are a powerful way to filter messages.</span></span>  <span data-ttu-id="6f7d5-135">たとえば、[フィルター] `/^Tracking/` テキスト ボックス **に** 入力して、用語で始まるメッセージのみを表示します `Tracking` 。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-135">For example, type `/^Tracking/` into the **Filter** textbox to only displays messages that start with the term `Tracking`.</span></span>  <span data-ttu-id="6f7d5-136">正規表現に慣れていない場合 [、RegExr][|::ref1::|Main] は正規表現の使用について学ぶのに最適なリソースです。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-136">If you're unfamiliar with regular expressions, [RegExr][|::ref1::|Main] is a great resource to learn about using regular expressions.</span></span>

:::image type="complex" source="../media/console-filter-regex.msft.png" alt-text="[フィルター] テキスト ボックスの正規表現を使用して、単語フィルターで始まるメッセージを表示します。" lightbox="../media/console-filter-regex.msft.png":::
    <span data-ttu-id="6f7d5-138">[フィルター] テキスト ボックスに正規表現を使用 `filter` して単語で始まるメッセージ **を** 表示します。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-138">Displays the messages that start with the word `filter` using a regular expression in the **Filter** textbox</span></span>  
:::image-end:::  

## <a name="filter-by-message-source"></a><span data-ttu-id="6f7d5-139">メッセージ ソースによるフィルター</span><span class="sxs-lookup"><span data-stu-id="6f7d5-139">Filter by message source</span></span>  

<span data-ttu-id="6f7d5-140">また、表示するメッセージの種類と、コンソールのサイドバーを使用してそれぞれの発信 **元を** 定義 **することもできます**。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-140">You may also define what kind of messages you want to display and where each originated using the **Sidebar** of the **Console**.</span></span>  <span data-ttu-id="6f7d5-141">これを行うには、[コンソールサイドバーの **表示] ボタンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-141">To do it, choose the **Show console sidebar** button.</span></span>  

:::image type="complex" source="../media/console-filter-sidebar-icon.msft.png" alt-text="サイドバーを開く場合は、サイドバーアイコン" lightbox="../media/console-filter-sidebar-icon.msft.png":::
    <span data-ttu-id="6f7d5-143">サイドバーを開 **く場合は**、[コンソールサイドバーの **表示] ボタンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-143">To open the **Sidebar**, choose the **Show console sidebar** button</span></span>  
:::image-end:::  

<span data-ttu-id="6f7d5-144">サイドバーが **開いている** ときに、メッセージの全体の数と、それぞれの発信元を表示できます。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-144">When the **Sidebar** is open, you may display the overall number of messages and where each originated.</span></span>  <span data-ttu-id="6f7d5-145">オプションは `All messages` `User Messages` 、、、、、 `Errors` `Warnings` `Info` です `Verbose` 。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-145">The options are `All messages`, `User Messages`, `Errors`, `Warnings`, `Info`, and `Verbose`.</span></span>  

:::image type="complex" source="../media/console-filter-sidebar-open.msft.png" alt-text="コンソール サイドバーには、発信元の異なるソース メッセージが表示されます。" lightbox="../media/console-filter-sidebar-open.msft.png":::
    <span data-ttu-id="6f7d5-147">コンソール **サイドバーには、** 発信元の異なるソース メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-147">The **Console Sidebar** displays the different sources messages originated from</span></span>  
:::image-end:::  

<span data-ttu-id="6f7d5-148">任意のオプションを選択して、その種類のメッセージのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-148">Choose any of the options to display only the messages of that type.</span></span>  <span data-ttu-id="6f7d5-149">たとえば、ユーザー メッセージを表示するには、[ユーザー メッセージ] オプションを選択して、ノイズを少なく表示します。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-149">For example, to display user messages, choose the user messages option to display less noise.</span></span>

:::image type="complex" source="../media/console-filter-select-user-messages.msft.png" alt-text="サイドバーのフィルターを使用してコンソールにユーザー メッセージのみを表示する場合を選択します。" lightbox="../media/console-filter-select-user-messages.msft.png":::
    <span data-ttu-id="6f7d5-151">サイドバーのフィルターを使用してコンソールにユーザー **メッセージのみを** 表示する場合を選択 **します。**</span><span class="sxs-lookup"><span data-stu-id="6f7d5-151">Choose to display only user messages in the **Console** using the filter in the **Sidebar**</span></span>  
:::image-end:::  

<span data-ttu-id="6f7d5-152">さらにフィルターを適用して選択肢を展開するには、その横にある三角形のアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-152">To filter more and expand the choice, choose the triangle icon next to it.</span></span>  <span data-ttu-id="6f7d5-153">この方法では、特定のソースから発信されたメッセージのみを表示するための選択肢が多く表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f7d5-153">That way you get more choices to display only messages that originate from a specific source.</span></span>  

:::image type="complex" source="../media/console-filter-sidebar-open-arrow.msft.png" alt-text="矢印アイコンを選択すると、各セクションが展開されます" lightbox="../media/console-filter-sidebar-open-arrow.msft.png":::
    <span data-ttu-id="6f7d5-155">矢印アイコンを選択すると、各セクションが展開されます</span><span class="sxs-lookup"><span data-stu-id="6f7d5-155">Choose the arrow icon expands each of the sections</span></span>  
:::image-end:::  

:::image type="complex" source="../media/console-filter-user-message-by-source.msft.png" alt-text="種類とソースを使用してフィルター処理する新しいオプションを選択する" lightbox="../media/console-filter-user-message-by-source.msft.png":::
    <span data-ttu-id="6f7d5-157">種類とソースを使用してフィルター処理する新しいオプションを選択する</span><span class="sxs-lookup"><span data-stu-id="6f7d5-157">Choose any of the new options to filter using type and source</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="6f7d5-158">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="6f7d5-158">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleApi]: ./api.md "コンソール API リファレンス |Microsoft Docs"  

[MdnDocsWebJavascriptGuideRegularExpressions]: https://developer.mozilla.org/docs/Web/JavaScript/Guide/Regular_Expressions "正規表現|MDN"  

[RegExrMain]: https://regexr.com "RegExr"  
