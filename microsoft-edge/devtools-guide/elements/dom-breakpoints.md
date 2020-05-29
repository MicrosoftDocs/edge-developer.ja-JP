---
description: DOM ブレークポイントを使用して、ページのレイアウトに関するエラーを視覚的にデバッグする
title: DevTools-Elements-DOM ブレークポイント
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、elements、dom ブレークポイント、dom 変異
ms.custom: seodec18
ms.openlocfilehash: 4e9eab4727cf1c3ef74b69495dd972838985e589
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570481"
---
# <span data-ttu-id="93bc6-104">DOM ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="93bc6-104">DOM breakpoints</span></span>

<span data-ttu-id="93bc6-105">このウィンドウから DOM 変異のブレークポイントを管理します。これには、無効化、削除、再バインドなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="93bc6-105">Manage your DOM mutation breakpoints from this pane, including disabling, deleting and rebinding them.</span></span>

<span data-ttu-id="93bc6-106">DOM 変異ブレークポイントを使用して、選択した要素ノードが変更されるたびにデバッガーを中断することができます。</span><span class="sxs-lookup"><span data-stu-id="93bc6-106">You can use DOM mutation breakpoints to break into the debugger whenever a selected element node changes.</span></span> <span data-ttu-id="93bc6-107">これは、 *EdgeHTML*の各 450 + DOM api に個別のブレークポイントを設定しなくても、このような変更をトリガーできるコードを追跡するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="93bc6-107">This is helpful for tracking down the code responsible for causing visual glitches with your UI without having to set individual breakpoints on each of the 450+ DOM APIs in *EdgeHTML* that can trigger such changes.</span></span> 

<span data-ttu-id="93bc6-108">DOM ブレークポイントを設定するには、**要素**パネルの*HTML ツリービュー*で任意の要素を右クリックしてコンテキストメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="93bc6-108">To set a DOM breakpoint, right-click on any element in the **Elements** panel *HTML tree view* to open the context menu.</span></span>

![DOM ブレークポイントコンテキストメニュー](../media/elements_dom_breakpoints_contextmenu.png)

<span data-ttu-id="93bc6-110">次のいずれかのブレークポイントを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="93bc6-110">You can set any of the following breakpoints:</span></span>

 - <span data-ttu-id="93bc6-111">**ノードが削除されたときの中断**: 選択した要素がドキュメント (DOM ツリー) から削除されたときにデバッガーを中断します。</span><span class="sxs-lookup"><span data-stu-id="93bc6-111">**Break on Node removed**: Break into the debugger when the selected element is removed from the document (DOM tree).</span></span>

 - <span data-ttu-id="93bc6-112">**サブツリーの中断**: 選択した要素の子孫 (追加、削除、またはサブツリーの変更) が変更されたときにデバッガーを中断します。</span><span class="sxs-lookup"><span data-stu-id="93bc6-112">**Break on Subtree modified**: Break into the debugger when any of the descendants of the selected element are changed (added, removed, or their subtrees are modified).</span></span> <span data-ttu-id="93bc6-113">属性が変更された場合、この操作は中断されません (次のオプションを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="93bc6-113">This will not break when attributes are modified (see the next option for that).</span></span>

 - <span data-ttu-id="93bc6-114">**属性でのブレークの変更**: 選択した要素の属性が追加、削除、または値で変更されたときにデバッガーに中断します。</span><span class="sxs-lookup"><span data-stu-id="93bc6-114">**Break on Attribute modified**: Break into the debugger when an attribute of the selected element is added, removed or changed in value.</span></span>

<span data-ttu-id="93bc6-115">次に、[ **dom ブレークポイント**] ウィンドウに、選択した要素 (dom での場所を説明するセレクターを生成) と、設定したブレークポイントの種類 (*ノードの削除、サブツリー、変更*された属性) を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="93bc6-115">The **DOM breakpoints** pane will then list the selected element (by generating a selector describing its location in the DOM) and the types of breakpoints you have set (*Node removed, Subtree modified, Attribute modified*).</span></span> <span data-ttu-id="93bc6-116">ここでは、ブレークポイントを個別に再*バインド*、*無効化*、または削除することもできます ([rt] のコンテキストメニューから)。または、ボタンを使ってすべて一度に*削除*することもできます。</span><span class="sxs-lookup"><span data-stu-id="93bc6-116">From here, you can also *rebind*, *disable*, or *delete* your breakpoints, individually (from the rt-click context menu) or all at once (using the buttons).</span></span>

![DOM のブレークポイントウィンドウ](../media/elements_dom_breakpoints.png)

## <span data-ttu-id="93bc6-118">ブレークポイントの永続性</span><span class="sxs-lookup"><span data-stu-id="93bc6-118">Breakpoint persistence</span></span>

<span data-ttu-id="93bc6-119">ブレークポイントは、DevTools の設定の一部として格納されます (範囲内に設定されているページの URL が対象となります)。</span><span class="sxs-lookup"><span data-stu-id="93bc6-119">Breakpoints are stored (and scoped to the URL of the page they're set within) as part of your DevTools settings.</span></span> <span data-ttu-id="93bc6-120">ページを再読み込みしたとき、またはツールを閉じて再び開いたときに、DevTools はブレークポイントを関連付けられた要素にバインドします。</span><span class="sxs-lookup"><span data-stu-id="93bc6-120">When the page is reloaded or the tools are closed and reopened, DevTools will attempt to rebind your breakpoints to their associated elements.</span></span>

<span data-ttu-id="93bc6-121">自動的に rebinded できないブレークポイントは、ブレークポイントの円に警告アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="93bc6-121">Breakpoints that couldn't be automatically rebinded are indicated with a warning icon on the breakpoint circle.</span></span> <span data-ttu-id="93bc6-122">そのためには、対応する要素が DOM に表示されるまで ([ブレークポイントの再**バインド**] ボタンとコンテキストメニューオプションを使用して)、要素を手動で再バインドするか、ブレークポイントを**削除**します。</span><span class="sxs-lookup"><span data-stu-id="93bc6-122">For these, you can wait to rebind the element manually (using the **Rebind breakpoint** button and/or context menu option) once a corresponding element appears in the DOM (and the breakpoint icon no longer shows the warning indicator), or **Delete** the breakpoint altogether.</span></span>

![非連結ブレークポイントインジケーター](../media/elements_dom_breakpoint_unbound.png)

<span data-ttu-id="93bc6-124">この*dom ブレークポイント*ウィンドウに加えて、**デバッガー**内から[dom ブレークポイント](../debugger.md#dom-breakpoints)を管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="93bc6-124">In addition to this *DOM breakpoints* pane, you can also manage your [DOM breakpoints](../debugger.md#dom-breakpoints) from within the **Debugger**.</span></span>

## <span data-ttu-id="93bc6-125">現在の制限事項</span><span class="sxs-lookup"><span data-stu-id="93bc6-125">Current limitations</span></span>

<span data-ttu-id="93bc6-126">Edge の DevTools での DOM ブレークポイントのデバッグに関する次の制限事項に注意してください。</span><span class="sxs-lookup"><span data-stu-id="93bc6-126">Please be aware of the following limitations of DOM breakpoint debugging in Edge DevTools:</span></span>

- <span data-ttu-id="93bc6-127">エッジ DevTools では、現在、 [ `<iframe>` s](https://developer.mozilla.org/docs/Web/HTML/Element/iframe)内の再バインドブレークポイントがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="93bc6-127">Edge DevTools don't currently support rebinding breakpoints inside of [`<iframe>`s](https://developer.mozilla.org/docs/Web/HTML/Element/iframe).</span></span> <span data-ttu-id="93bc6-128">Iframe にブレークポイントを設定し、その後 Edge ツールを終了するか、ページを更新すると、ブレークポイントは失われます。</span><span class="sxs-lookup"><span data-stu-id="93bc6-128">If you set a breakpoint in an iframe and close Edge DevTools or refresh the page, the breakpoint will be lost.</span></span>

- <span data-ttu-id="93bc6-129">DOM が完了する前に、スクリプトが同期的に実行されたブレークポイントを検出した場合 [`readyState`](https://developer.mozilla.org/docs/Web/API/Document/readyState) 、デバッガーが一時停止されている間は dom ブレークポイントを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="93bc6-129">If your script encounters a synchronously-executed breakpoint before the DOM [`readyState`](https://developer.mozilla.org/docs/Web/API/Document/readyState) is completed, you won't be able to set a DOM breakpoint while the debugger is paused.</span></span> <span data-ttu-id="93bc6-130">通常 [`defer`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) は、またはスクリプト属性を設定することで、このような状況を解決でき [`async`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) ます。</span><span class="sxs-lookup"><span data-stu-id="93bc6-130">You can typically remedy this situation by setting the [`defer`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) or [`async`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) script attributes.</span></span>

- <span data-ttu-id="93bc6-131">同期スクリプトの場合、イベントが呼び出されたときにブレークポイントの自動再バインドをトリガーし [`window.onload`](https://developer.mozilla.org/docs/Web/API/GlobalEventHandlers/onload) ます。</span><span class="sxs-lookup"><span data-stu-id="93bc6-131">For synchronous scripts, we trigger automatic rebinding of breakpoints when the [`window.onload`](https://developer.mozilla.org/docs/Web/API/GlobalEventHandlers/onload) event is called.</span></span> <span data-ttu-id="93bc6-132">この場合、DOM の最初のスクリプト駆動のビルド時にトリガーされるバインドブレークポイントを見逃してしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="93bc6-132">In this case, we may miss binding breakpoints that would trigger during initial script-driven build-up of the DOM.</span></span> <span data-ttu-id="93bc6-133">非同期スクリプトの場合、最初のスクリプトが実行される前に再バインドが行われ、必要に応じてブレークポイントが再バインドされ、トリガーされることがあります。</span><span class="sxs-lookup"><span data-stu-id="93bc6-133">For asynchronous scripts, we trigger a rebind attempt before the first script executes, so your breakpoints may rebind and trigger as desired.</span></span>
