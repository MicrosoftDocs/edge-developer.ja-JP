---
description: '[イベント] ウィンドウを使用して、ページ上の登録済みイベント リスナーを検査する'
title: DevTools - 要素 - イベント
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, 要素, イベント リスナー, イベント ハンドラー
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 76696946e7dad93712144a0d3b78e0b1ee6d1eb1
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234749"
---
# <span data-ttu-id="05361-104">イベント</span><span class="sxs-lookup"><span data-stu-id="05361-104">Events</span></span> 

<span data-ttu-id="05361-105">選択した要素に登録されているイベント リスナーを表示し、(オプションで、チェックボックスの切り替えを使用して) その先祖を表示します。</span><span class="sxs-lookup"><span data-stu-id="05361-105">View the event listeners registered on the selected element and (optionally, using the checkbox toggle) its ancestors.</span></span> <span data-ttu-id="05361-106">これは、悪意のあるイベント リスナーを追跡する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="05361-106">This is useful for tracking down rogue event listeners.</span></span> 

<span data-ttu-id="05361-107">イベント リスナーは、Event または **Element** でグループ化 **できます**。</span><span class="sxs-lookup"><span data-stu-id="05361-107">You can group the event listeners by either **Event** or **Element**.</span></span> <span data-ttu-id="05361-108">イベント ハンドラー名の横にある青いハイパーリンクをクリックすると、その関数の場所へのデバッガーが開きます。</span><span class="sxs-lookup"><span data-stu-id="05361-108">Clicking the blue hyperlink next to the event handler name will open the debugger to the location of that function.</span></span>

![[イベント] ウィンドウ](../media/elements_events.png)
