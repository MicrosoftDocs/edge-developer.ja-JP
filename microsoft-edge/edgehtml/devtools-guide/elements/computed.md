---
description: '[計算] ウィンドウを使用して、CSS がページ要素でカスケードおよび計算される方法を理解する'
title: DevTools - 要素 - 計算
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, 要素, css, 計算値, ボックス モデル
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e88b96a08ac22c56ac6578495311931d265247bb
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234462"
---
# <span data-ttu-id="58d88-104">計算済み</span><span class="sxs-lookup"><span data-stu-id="58d88-104">Computed</span></span>

<span data-ttu-id="58d88-105">選択した要素のボックス モデル図 (幅、パディング、境界線、余白、オフセット値) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58d88-105">See a box model diagram (width, padding, border, margin and offset values) of the selected element.</span></span> <span data-ttu-id="58d88-106">要素の強調表示ツール( ) をオンにした場合、図内の同じ色の領域 (幅、パディングなど) は、レンダリングされた要素をページ上で選択するときにオーバーレイします。 `Ctrl+Shift+L`</span><span class="sxs-lookup"><span data-stu-id="58d88-106">If you turn on the **Element highlighting** tool (`Ctrl+Shift+L`), the same colored regions in the diagram (for width, padding, etc.) that will overlay the rendered element when you select it on the page.</span></span> <span data-ttu-id="58d88-107">ダイアグラム内の任意の値をクリックして編集できます。</span><span class="sxs-lookup"><span data-stu-id="58d88-107">You can edit any value in the diagram by clicking it.</span></span> 

<span data-ttu-id="58d88-108">ボックス モデル図の下には、計算されたスタイル プロパティのフィルター処理可能で編集可能なリストがあります。</span><span class="sxs-lookup"><span data-stu-id="58d88-108">Below the box model diagram is a filterable and editable list of computed style properties.</span></span> <span data-ttu-id="58d88-109">現在アクティブなプロパティをオフにした場合は、カスケード内の次のプロパティがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="58d88-109">Turning off a currently active property activates the next property in the cascade, if one exists.</span></span> <span data-ttu-id="58d88-110">変更は、[変更] ウィンドウで [**確認**](./changes.md) できます。</span><span class="sxs-lookup"><span data-stu-id="58d88-110">You can view your changes in the [**Changes**](./changes.md) pane.</span></span>

<span data-ttu-id="58d88-111">[ **ユーザー スタイルのみを表示]** ボタンは既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="58d88-111">The **Display user styles only** button is on by default.</span></span> <span data-ttu-id="58d88-112">ボタンを押すと、計算されたスタイル リストに Microsoft Edge の既定のスタイルシートのスタイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="58d88-112">Depressing the button will include styles from the *default stylesheet* of Microsoft Edge in the computed styles list.</span></span>

![計算ウィンドウ](../media/elements_computed.png)
