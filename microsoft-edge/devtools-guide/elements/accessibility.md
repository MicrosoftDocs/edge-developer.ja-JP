---
description: アクセシビリティツールを使用して、ページのアクセシビリティの確認とテストを行う
title: アクセシビリティ-DevTools (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、elements、アクセシビリティ
ms.custom: seodec18
ms.openlocfilehash: 82f0fb505d88da6c5ee6318e787ed12ad05d1b0f
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882885"
---
# <span data-ttu-id="3b63e-104">アクセシビリティ-DevTools (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="3b63e-104">Accessibility - DevTools (EdgeHTML)</span></span>  

<span data-ttu-id="3b63e-105">選択した要素に割り当てられているアクセシビリティ対応のプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="3b63e-105">View the accessible properties assigned to the selected element.</span></span> <span data-ttu-id="3b63e-106">プロパティ名の上にマウスポインターを置くと、支援技術によってどのように使用されるかが説明されます。</span><span class="sxs-lookup"><span data-stu-id="3b63e-106">Hover over any of the property names for a description of how it's used by assistive technologies.</span></span> <span data-ttu-id="3b63e-107">任意のプロパティを右クリックして、その値をクリップボードにコピーすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3b63e-107">You can also right-click any property to copy its value to the clipboard.</span></span>

![アクセシビリティウィンドウ](../media/elements_accessibility.png)

<span data-ttu-id="3b63e-109">スクリーンリーダーとしてページ内を移動するには、[アクセシビリティツリー](#accessibility-tree)を開くと便利です。次に、[**アクセシビリティ**] ウィンドウを使って、関心のあるアクセシビリティプロパティの詳細を調べます。</span><span class="sxs-lookup"><span data-stu-id="3b63e-109">It's useful to open the [Accessibility tree](#accessibility-tree) to navigate around your page as a screen reader would, and then use the **Accessibility** pane to inspect details about accessibility properties of interest.</span></span>

## <span data-ttu-id="3b63e-110">アクセシビリティツリー</span><span class="sxs-lookup"><span data-stu-id="3b63e-110">Accessibility tree</span></span>  

<span data-ttu-id="3b63e-111">[**アクセシビリティツリー** ] ウィンドウには、 [Windows ナレーター](https://support.microsoft.com/help/22798/windows-10-narrator-get-started)のスクリーンリーダーなどの支援技術に表示されるページの構造が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b63e-111">The **Accessibility tree** pane shows the structure of your page as it would appear to an assistive technology, such as the [Windows Narrator](https://support.microsoft.com/help/22798/windows-10-narrator-get-started) screen reader.</span></span>

<span data-ttu-id="3b63e-112">ツリービュー内のノードをクリックすると、[ [**HTML] ツリー**](../elements.md#html-tree-view)でもそのノードが選択され、その逆もできます。</span><span class="sxs-lookup"><span data-stu-id="3b63e-112">Clicking on a node in the tree view will also select it in the [**HTML tree**](../elements.md#html-tree-view), and vice versa.</span></span> <span data-ttu-id="3b63e-113">[ *HTML* ] または [*アクセシビリティ*] ツリービューからアクセス可能な要素を選ぶと、[**アクセシビリティ**ツール] ウィンドウにさらにアクセシビリティプロパティの詳細情報が追加されます。</span><span class="sxs-lookup"><span data-stu-id="3b63e-113">Selecting an accessible element from either the *HTML* or *Accessibility* tree views will also populate further accessibility property details in the **Accessibility** tool pane.</span></span> 

![アクセシビリティツリービュー](../media/elements_accessibility_tree.png)

<span data-ttu-id="3b63e-115">[Microsoft Edge でのアクセシビリティ](../../accessibility.md)に関するその他のリソースを次に示します。</span><span class="sxs-lookup"><span data-stu-id="3b63e-115">Here are further resources on [Accessibility with Microsoft Edge](../../accessibility.md).</span></span>
