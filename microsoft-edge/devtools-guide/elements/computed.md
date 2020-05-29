---
description: 計算されたウィンドウを使って、CSS がページ要素にどのように重ね合わせて計算されるかを理解する
title: DevTools-要素-計算
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/10/2017
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、elements、css、計算値、ボックスモデル
ms.custom: seodec18
ms.openlocfilehash: c7b1b7c86f30e6947442c9b3d0e8856074ce4c8e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570482"
---
# <span data-ttu-id="ac173-104">引い</span><span class="sxs-lookup"><span data-stu-id="ac173-104">Computed</span></span>

<span data-ttu-id="ac173-105">選択した要素のボックスモデル図 (幅、パディング、境界、余白、オフセット値) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac173-105">See a box model diagram (width, padding, border, margin and offset values) of the selected element.</span></span> <span data-ttu-id="ac173-106">[**要素の強調表示**] ツール () をオンにすると `Ctrl+Shift+L` 、ページで選択したときに、レンダリングされた要素をオーバーレイする、同じ色の領域 (幅、パディングなど) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac173-106">If you turn on the **Element highlighting** tool (`Ctrl+Shift+L`), the same colored regions in the diagram (for width, padding, etc.) that will overlay the rendered element when you select it on the page.</span></span> <span data-ttu-id="ac173-107">図面で任意の値を編集するには、それをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac173-107">You can edit any value in the diagram by clicking it.</span></span> 

<span data-ttu-id="ac173-108">ボックスモデル図の下には、計算されたスタイルプロパティのフィルター処理および編集可能なリストがあります。</span><span class="sxs-lookup"><span data-stu-id="ac173-108">Below the box model diagram is a filterable and editable list of computed style properties.</span></span> <span data-ttu-id="ac173-109">現在アクティブなプロパティをオフにすると、cascade で次のプロパティが存在する場合にアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="ac173-109">Turning off a currently active property activates the next property in the cascade, if one exists.</span></span> <span data-ttu-id="ac173-110">[[**変更箇所**](./changes.md)] ウィンドウで変更内容を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ac173-110">You can view your changes in the [**Changes**](./changes.md) pane.</span></span>

<span data-ttu-id="ac173-111">[**ユーザースタイルのみ表示**] ボタンは、既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="ac173-111">The **Display user styles only** button is on by default.</span></span> <span data-ttu-id="ac173-112">[戻る] ボタンでは、Microsoft Edge の*既定のスタイルシート*のスタイルが [計算されたスタイル] の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac173-112">Depressing the button will include styles from the *default stylesheet* of Microsoft Edge in the computed styles list.</span></span>

![計算されたウィンドウ](../media/elements_computed.png)