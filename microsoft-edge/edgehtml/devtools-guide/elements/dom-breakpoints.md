---
description: DOM ブレークポイントを使用してページ上のレイアウトの不具合を視覚的にデバッグする
title: DevTools - 要素 - DOM のブレークポイント
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, 要素, dom ブレークポイント, dom の変更
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cb60fa0497c98c152ca2c5adf28e9dee5d7c9f98
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234626"
---
# <span data-ttu-id="efde6-104">DOM ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="efde6-104">DOM breakpoints</span></span>

<span data-ttu-id="efde6-105">DOM のブレークポイントを無効、削除、再バインドなど、このウィンドウから管理します。</span><span class="sxs-lookup"><span data-stu-id="efde6-105">Manage your DOM mutation breakpoints from this pane, including disabling, deleting and rebinding them.</span></span>

<span data-ttu-id="efde6-106">DOM のブレークポイントを使用すると、選択した要素ノードが変更されるたびにデバッガーにブレークポイントを割り込みます。</span><span class="sxs-lookup"><span data-stu-id="efde6-106">You can use DOM mutation breakpoints to break into the debugger whenever a selected element node changes.</span></span> <span data-ttu-id="efde6-107">これは、このような変更をトリガーできる *EdgeHTML* の 450+ DOM API それぞれに個別のブレークポイントを設定することなく、UI で視覚的な不具合を引き起こす原因となるコードを追跡する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="efde6-107">This is helpful for tracking down the code responsible for causing visual glitches with your UI without having to set individual breakpoints on each of the 450+ DOM APIs in *EdgeHTML* that can trigger such changes.</span></span> 

<span data-ttu-id="efde6-108">DOM のブレークポイントを設定するには、[要素] パネルの\*\*\*\*\*HTML\*ツリー ビューで任意の要素を右クリックしてコンテキスト メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="efde6-108">To set a DOM breakpoint, right-click on any element in the **Elements** panel *HTML tree view* to open the context menu.</span></span>

![DOM ブレークポイントのコンテキスト メニュー](../media/elements_dom_breakpoints_contextmenu.png)

<span data-ttu-id="efde6-110">次のブレークポイントを設定できます。</span><span class="sxs-lookup"><span data-stu-id="efde6-110">You can set any of the following breakpoints:</span></span>

 - <span data-ttu-id="efde6-111">**削除されたノードで**ブレーク : 選択した要素がドキュメント (DOM ツリー) から削除されると、デバッガーに割り込みます。</span><span class="sxs-lookup"><span data-stu-id="efde6-111">**Break on Node removed**: Break into the debugger when the selected element is removed from the document (DOM tree).</span></span>

 - <span data-ttu-id="efde6-112">**変更されたサブツリー**でのブレーク : 選択した要素の子孫が変更された場合 (追加、削除、またはサブツリーが変更された場合) にデバッガーに割り込みます。</span><span class="sxs-lookup"><span data-stu-id="efde6-112">**Break on Subtree modified**: Break into the debugger when any of the descendants of the selected element are changed (added, removed, or their subtrees are modified).</span></span> <span data-ttu-id="efde6-113">これは、属性が変更された場合に壊れる可能性はありません (その次のオプションを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="efde6-113">This will not break when attributes are modified (see the next option for that).</span></span>

 - <span data-ttu-id="efde6-114">**Break on Attribute modified:** Break into the debugger when an attribute of the selected element is added, removed or changed in value.</span><span class="sxs-lookup"><span data-stu-id="efde6-114">**Break on Attribute modified**: Break into the debugger when an attribute of the selected element is added, removed or changed in value.</span></span>

<span data-ttu-id="efde6-115">**DOM**のブレークポイント ウィンドウには、選択した要素 (DOM 内での位置を示すセレクターを生成) と、設定したブレークポイントの種類 (ノードの削除、サブツリーの変更、*属性*の変更) が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="efde6-115">The **DOM breakpoints** pane will then list the selected element (by generating a selector describing its location in the DOM) and the types of breakpoints you have set (*Node removed, Subtree modified, Attribute modified*).</span></span> <span data-ttu-id="efde6-116">ここから、ブレークポイントを個別に**(rt-click コンテキスト** メニューから) 再バインド、無効化、または削除したり、または一度にすべて (ボタンを使用) することもできます。 \*\*</span><span class="sxs-lookup"><span data-stu-id="efde6-116">From here, you can also *rebind*, *disable*, or *delete* your breakpoints, individually (from the rt-click context menu) or all at once (using the buttons).</span></span>

![[DOM ブレークポイント] ウィンドウ](../media/elements_dom_breakpoints.png)

## <span data-ttu-id="efde6-118">ブレークポイントの永続性</span><span class="sxs-lookup"><span data-stu-id="efde6-118">Breakpoint persistence</span></span>

<span data-ttu-id="efde6-119">ブレークポイントは、DevTools の設定の一部として格納されます (また、ブレークポイントが設定されているページの URL にスコープが設定されます)。</span><span class="sxs-lookup"><span data-stu-id="efde6-119">Breakpoints are stored (and scoped to the URL of the page they're set within) as part of your DevTools settings.</span></span> <span data-ttu-id="efde6-120">ページを再読み込みするか、ツールを閉じてから再度開くと、DevTools はブレークポイントを関連する要素に再バインドします。</span><span class="sxs-lookup"><span data-stu-id="efde6-120">When the page is reloaded or the tools are closed and reopened, DevTools will attempt to rebind your breakpoints to their associated elements.</span></span>

<span data-ttu-id="efde6-121">自動的に再バインドできなかったブレークポイントは、ブレークポイント の円に警告アイコンで示されます。</span><span class="sxs-lookup"><span data-stu-id="efde6-121">Breakpoints that couldn't be automatically rebinded are indicated with a warning icon on the breakpoint circle.</span></span> <span data-ttu-id="efde6-122">このため、DOM に対応する要素が表示されたら ([再バインド\*\*\*\* されたブレークポイント] ボタンやコンテキスト メニュー オプションを使用して) 要素を手動で再バインドするのを待つ (ブレークポイント アイコンに警告インジケーターが\*\*\*\* 表示されなくなった) か、ブレークポイントを完全に削除することができます。</span><span class="sxs-lookup"><span data-stu-id="efde6-122">For these, you can wait to rebind the element manually (using the **Rebind breakpoint** button and/or context menu option) once a corresponding element appears in the DOM (and the breakpoint icon no longer shows the warning indicator), or **Delete** the breakpoint altogether.</span></span>

![非受信ブレークポイント インジケーター](../media/elements_dom_breakpoint_unbound.png)

<span data-ttu-id="efde6-124">この DOM のブレークポイント ウィンドウに *加* えて、デバッガー内から [DOM](../debugger.md#dom-breakpoints) のブレークポイントを管理 **することもできます**。</span><span class="sxs-lookup"><span data-stu-id="efde6-124">In addition to this *DOM breakpoints* pane, you can also manage your [DOM breakpoints](../debugger.md#dom-breakpoints) from within the **Debugger**.</span></span>

## <span data-ttu-id="efde6-125">現在の制限事項</span><span class="sxs-lookup"><span data-stu-id="efde6-125">Current limitations</span></span>

<span data-ttu-id="efde6-126">Edge DevTools での DOM ブレークポイント デバッグの次の制限事項に注意してください。</span><span class="sxs-lookup"><span data-stu-id="efde6-126">Please be aware of the following limitations of DOM breakpoint debugging in Edge DevTools:</span></span>

- <span data-ttu-id="efde6-127">Edge DevTools では、現在、ブレークポイント内のブレークポイントの再バインドはサポート[ `<iframe>` されていません](https://developer.mozilla.org/docs/Web/HTML/Element/iframe)。</span><span class="sxs-lookup"><span data-stu-id="efde6-127">Edge DevTools don't currently support rebinding breakpoints inside of [`<iframe>`s](https://developer.mozilla.org/docs/Web/HTML/Element/iframe).</span></span> <span data-ttu-id="efde6-128">iframe にブレークポイントを設定して Edge DevTools を閉じるか、ページを更新すると、ブレークポイントは失われます。</span><span class="sxs-lookup"><span data-stu-id="efde6-128">If you set a breakpoint in an iframe and close Edge DevTools or refresh the page, the breakpoint will be lost.</span></span>

- <span data-ttu-id="efde6-129">DOM が完了する前に同期的に実行されたブレークポイントがスクリプトで検出された場合、デバッガーが一時停止している間は DOM のブレークポイントを [`readyState`](https://developer.mozilla.org/docs/Web/API/Document/readyState) 設定できません。</span><span class="sxs-lookup"><span data-stu-id="efde6-129">If your script encounters a synchronously-executed breakpoint before the DOM [`readyState`](https://developer.mozilla.org/docs/Web/API/Document/readyState) is completed, you won't be able to set a DOM breakpoint while the debugger is paused.</span></span> <span data-ttu-id="efde6-130">通常、この状況を解決するには、スクリプト属性 [`defer`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) またはスクリプト属性 [`async`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) を設定します。</span><span class="sxs-lookup"><span data-stu-id="efde6-130">You can typically remedy this situation by setting the [`defer`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) or [`async`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) script attributes.</span></span>

- <span data-ttu-id="efde6-131">同期スクリプトの場合、イベントが呼び出されるとブレークポイントの自動再バインド [`window.onload`](https://developer.mozilla.org/docs/Web/API/GlobalEventHandlers/onload) がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="efde6-131">For synchronous scripts, we trigger automatic rebinding of breakpoints when the [`window.onload`](https://developer.mozilla.org/docs/Web/API/GlobalEventHandlers/onload) event is called.</span></span> <span data-ttu-id="efde6-132">この場合、DOM のスクリプト駆動型の初期ビルド時にトリガーされるバインド ブレークポイントが見つからない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="efde6-132">In this case, we may miss binding breakpoints that would trigger during initial script-driven build-up of the DOM.</span></span> <span data-ttu-id="efde6-133">非同期スクリプトの場合、最初のスクリプトが実行される前に再バインドの試行がトリガーされます。そのため、ブレークポイントが再バインドされ、必要に応じてトリガーされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="efde6-133">For asynchronous scripts, we trigger a rebind attempt before the first script executes, so your breakpoints may rebind and trigger as desired.</span></span>
