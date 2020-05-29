---
description: '[スタイル] ウィンドウを使って、現在適用されているスタイルと擬似要素を表示および編集する'
title: DevTools-要素-スタイル
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/10/2017
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、elements、スタイル、擬似状態、擬似 classe、擬似要素
ms.custom: seodec18
ms.openlocfilehash: f517595a61dda8a802cbc368d84c1036c26e1ee0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569708"
---
# <span data-ttu-id="f1b7f-104">スタイル</span><span class="sxs-lookup"><span data-stu-id="f1b7f-104">Styles</span></span>
<span data-ttu-id="f1b7f-105">現在適用されているスタイルを、スタイルシート別に表示して編集します。</span><span class="sxs-lookup"><span data-stu-id="f1b7f-105">View and edit the currently applied styles, organized by stylesheet.</span></span>  <span data-ttu-id="f1b7f-106">プロパティを変更すると、変更された (黄色)、追加された (緑)、および削除された (赤) プロパティについては、色付きのインジケーターバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1b7f-106">As you make changes to your properties, a colored indicator bar will appear for changed (yellow), added (green), and deleted (red) properties.</span></span>

![スタイルウィンドウ](../media/elements_styles.png)

<span data-ttu-id="f1b7f-108">「**A:**」ボタンをクリックすると、擬似状態パネルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f1b7f-108">You can display the pseudo states panel by clicking the "**a:**" button.</span></span> <span data-ttu-id="f1b7f-109">新しいスタイルルールを定義するには、[] ボタンをクリック **+** するか、[**スタイル**] ウィンドウの任意の場所を右クリックしてコンテキストメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="f1b7f-109">Define a new style rule by clicking the "**+**" button or right-clicking anywhere in the **Styles** pane to open the context menu.</span></span>

![[スタイル] ウィンドウのボタンとコンテキストメニュー](../media/elements_styles_buttons.png)

## <span data-ttu-id="f1b7f-111">疑似要素の編集</span><span class="sxs-lookup"><span data-stu-id="f1b7f-111">Editing pseudo elements</span></span>

<span data-ttu-id="f1b7f-112">[スタイル] ウィンドウを使って、擬似要素と擬似状態の追加、編集、削除を行います。</span><span class="sxs-lookup"><span data-stu-id="f1b7f-112">Use the Styles pane to add, edit, and delete pseudo elements and pseudo states.</span></span> <span data-ttu-id="f1b7f-113">選択した要素に CSS 擬似状態を適用するには、[*擬似状態] パネル*(**a:** button) を開いて、目的のクラスを選びます。</span><span class="sxs-lookup"><span data-stu-id="f1b7f-113">To apply a CSS pseudo state to the selected element, open the *Pseudo states panel* (**a:** button) and tick the desired class.</span></span>

![[スタイル] ウィンドウの擬似クラス](../media/elements_styles_pseudo_states.png)

<span data-ttu-id="f1b7f-115">擬似要素を追加するには、[ **+** (*新しいスタイルルール*)] ボタンをクリックして、通常のスタイルシートと同様に編集します。</span><span class="sxs-lookup"><span data-stu-id="f1b7f-115">To add a pseudo element, click the **+** (*New style rule*) button and edit as you would a regular stylesheet.</span></span>

![[スタイル] ウィンドウでの擬似要素の追加](../media/elements_styles_pseudo_element.png)

<span data-ttu-id="f1b7f-117">[*スタイル*] ウィンドウでは、擬似要素は独自の見出しの下にグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="f1b7f-117">Pseudo elements are grouped under their own headings in the *Styles* pane.</span></span>