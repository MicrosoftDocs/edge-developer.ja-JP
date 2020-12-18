---
description: アクセシビリティ ツールを使用してページのアクセシビリティの確認とテストを行う
title: アクセシビリティ - DevTools (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, 要素, アクセシビリティ
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5fd5f072f602cb8fa344df8124ee174f2a20aa5d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234603"
---
# <span data-ttu-id="d11a1-104">アクセシビリティ - DevTools (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="d11a1-104">Accessibility - DevTools (EdgeHTML)</span></span>  

<span data-ttu-id="d11a1-105">選択した要素に割り当てられているアクセス可能なプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="d11a1-105">View the accessible properties assigned to the selected element.</span></span> <span data-ttu-id="d11a1-106">支援技術による使い方の説明については、プロパティ名の上にカーソルを合わせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d11a1-106">Hover over any of the property names for a description of how it's used by assistive technologies.</span></span> <span data-ttu-id="d11a1-107">また、任意のプロパティを右クリックして、その値をクリップボードにコピーすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d11a1-107">You can also right-click any property to copy its value to the clipboard.</span></span>

![[アクセシビリティ] ウィンドウ](../media/elements_accessibility.png)

<span data-ttu-id="d11a1-109">アクセシビリティ ツリーを開いて、[](#accessibility-tree)スクリーン リーダーと同じ方法でページ内を移動し、[アクセシビリティ] ウィンドウ\*\*\*\* を使用して、関心のあるアクセシビリティ プロパティに関する詳細を確認すると便利です。</span><span class="sxs-lookup"><span data-stu-id="d11a1-109">It's useful to open the [Accessibility tree](#accessibility-tree) to navigate around your page as a screen reader would, and then use the **Accessibility** pane to inspect details about accessibility properties of interest.</span></span>

## <span data-ttu-id="d11a1-110">アクセシビリティ ツリー</span><span class="sxs-lookup"><span data-stu-id="d11a1-110">Accessibility tree</span></span>  

<span data-ttu-id="d11a1-111">[ **アクセシビリティ] ツリー** ウィンドウには [、Windows](https://support.microsoft.com/help/22798/windows-10-narrator-get-started) ナレーター スクリーン リーダーなどの支援技術のように表示されるページの構造が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d11a1-111">The **Accessibility tree** pane shows the structure of your page as it would appear to an assistive technology, such as the [Windows Narrator](https://support.microsoft.com/help/22798/windows-10-narrator-get-started) screen reader.</span></span>

<span data-ttu-id="d11a1-112">ツリー ビューでノードをクリックすると [**、HTML**](../elements.md#html-tree-view)ツリーでもノードが選択され、その逆も選択されます。</span><span class="sxs-lookup"><span data-stu-id="d11a1-112">Clicking on a node in the tree view will also select it in the [**HTML tree**](../elements.md#html-tree-view), and vice versa.</span></span> <span data-ttu-id="d11a1-113">*HTML*ビューまたはアクセシビリティ ツリー ビューからアクセシビリティ\*\* 対応の要素を選択すると、アクセシビリティ ツール ウィンドウにアクセシビリティ プロパティの詳細**が**表示されます。</span><span class="sxs-lookup"><span data-stu-id="d11a1-113">Selecting an accessible element from either the *HTML* or *Accessibility* tree views will also populate further accessibility property details in the **Accessibility** tool pane.</span></span> 

![アクセシビリティ ツリー ビュー](../media/elements_accessibility_tree.png)

<!--  Here are further resources on [Accessibility with Microsoft Edge](../../accessibility.md).  -->  
