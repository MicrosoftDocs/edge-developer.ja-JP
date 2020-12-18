---
ms.assetid: c4544a19-de78-4c69-a042-c0415726548f
description: Light モードと Dark モードの両方で拡張機能のアイコンが表示されるのを確認するには、アクセシビリティ ガイドに従います。
title: アクセシビリティ - 拡張機能 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e6e7dbd2ee66ac785be31eec7189b87e6a6bd91f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234982"
---
# <span data-ttu-id="000af-104">アクセシビリティ - 拡張機能 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="000af-104">Accessibility - Extensions (EdgeHTML)</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

## <span data-ttu-id="000af-105">Microsoft Edge のアクセス可能な拡張機能アイコンの作成</span><span class="sxs-lookup"><span data-stu-id="000af-105">Creating accessible extension icons for Microsoft Edge</span></span>

<span data-ttu-id="000af-106">サード パーティ拡張機能の開発者は、淡色テーマと濃色テーマの両方でアイコンを明確に表示するために、Microsoft の厳密なアクセシビリティ要件を満たす画像アセットを使用するようにお勧めしています。</span><span class="sxs-lookup"><span data-stu-id="000af-106">Third-party extension developers are encouraged to use image assets that meet Microsoft’s strict accessibility requirements so that icons are clearly visible for both light and dark themes.</span></span> <span data-ttu-id="000af-107">すべての拡張アイコンは、アイコンの背景色とアイコン自体の主要な色との比率が 14:1 にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="000af-107">We recommend that all extension icons have a 14:1 ratio between the icon’s background color and the dominant color of the icon itself.</span></span>


<span data-ttu-id="000af-108">Microsoft が開発したファースト パーティ拡張機能では、これらの要件を満たすために "ステッカー" による視覚的な処理が適用されます。</span><span class="sxs-lookup"><span data-stu-id="000af-108">First-party extensions developed by Microsoft apply a “stickering” visual treatment to satisfy these requirements.</span></span>

### <span data-ttu-id="000af-109">"ステッカー" の例</span><span class="sxs-lookup"><span data-stu-id="000af-109">Examples of the "stickering"</span></span>

<span data-ttu-id="000af-110">"ステッカー" の主な目的は、任意の背景色でアイコンに視覚的にアクセス可能に設定します。</span><span class="sxs-lookup"><span data-stu-id="000af-110">The main goal of “stickering” is to make the icon visually accessible on any background color.</span></span> <span data-ttu-id="000af-111">ハイ コントラスト要件をサポートするには、白の外側のストロークとアイコンの推奨される色の比率を 14:1 に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="000af-111">The recommended color ratio between the white outer stroke and your icon should be 14:1 to support the high contrast requirements.</span></span>

#### <span data-ttu-id="000af-112">良いアイコン</span><span class="sxs-lookup"><span data-stu-id="000af-112">Good icon</span></span>
<span data-ttu-id="000af-113">ステッカーを使用すると、主に暗いアイコンが任意の背景色で表示されたままになります。</span><span class="sxs-lookup"><span data-stu-id="000af-113">With stickering, a primarily dark icon will remain visible on any background color.</span></span>


![任意の背景色で表示されているアイコンの画像](./../media/accessibility-light-to-dark-good.png)

#### <span data-ttu-id="000af-115">悪いアイコン</span><span class="sxs-lookup"><span data-stu-id="000af-115">Bad icon</span></span>
<span data-ttu-id="000af-116">ステッカーを使用しない場合、アイコンが背景と混じり合って見えなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="000af-116">Without stickering, an icon could blend in with the background and become impossible to see.</span></span>


![黒の背景にブレンドされたアイコンの画像](./../media/accessibility-light-to-dark-bad.png)

### <span data-ttu-id="000af-118">拡張機能アイコンを "ステッカー" する</span><span class="sxs-lookup"><span data-stu-id="000af-118">"Stickering" your extension icon</span></span>

<span data-ttu-id="000af-119">次の 5 つの手順では、Microsoft のアクセシビリティ要件を満たす拡張アイコンを作成する推奨される方法の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="000af-119">The following five steps outline the suggested method of creating an extension icon that meets Microsoft’s accessibility requirements:</span></span>


| <span data-ttu-id="000af-120">ステップ 1</span><span class="sxs-lookup"><span data-stu-id="000af-120">Step 1</span></span>                                       | <span data-ttu-id="000af-121">ステップ 2</span><span class="sxs-lookup"><span data-stu-id="000af-121">Step 2</span></span>                                       | <span data-ttu-id="000af-122">ステップ 3</span><span class="sxs-lookup"><span data-stu-id="000af-122">Step 3</span></span>                                                                                 | <span data-ttu-id="000af-123">ステップ 4</span><span class="sxs-lookup"><span data-stu-id="000af-123">Step 4</span></span>                                                                          | <span data-ttu-id="000af-124">ステップ 5</span><span class="sxs-lookup"><span data-stu-id="000af-124">Step 5</span></span>                                                       |
|:---------------------------------------------|:---------------------------------------------|:---------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------|:-------------------------------------------------------------|
| <span data-ttu-id="000af-125">指定したグリッド内にアイコンを設定します。</span><span class="sxs-lookup"><span data-stu-id="000af-125">Set your icon within your specified grid.</span></span>    | <span data-ttu-id="000af-126">アイコンのサイズを 2 ピクセル小さくします。</span><span class="sxs-lookup"><span data-stu-id="000af-126">Reduce your icon size by 2 pixels.</span></span>           | <span data-ttu-id="000af-127">アイコンをコピーして、その場所に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="000af-127">Copy your icon and paste in place.</span></span> <span data-ttu-id="000af-128">角が丸い 2 ピクセルの外側のストロークを作成します。</span><span class="sxs-lookup"><span data-stu-id="000af-128">Create a 2 pixel outer stroke with rounded corners.</span></span> | <span data-ttu-id="000af-129">ストロークの輪郭を設定し、複合パスを離して、残りの図形を結合します。</span><span class="sxs-lookup"><span data-stu-id="000af-129">Outline your stroke, release the compound path, and merge the remaining shapes.</span></span> | <span data-ttu-id="000af-130">外側のストロークを白、内側のアイコンを必要に合った色に設定します。</span><span class="sxs-lookup"><span data-stu-id="000af-130">Color the outer stroke white and the inner icon as you wish.</span></span> |
| ![step1](./../media/accessibility-step1.png) | ![step2](./../media/accessibility-step2.png) | ![step3](./../media/accessibility-step3.png)                                           | ![step4](./../media/accessibility-step4.png)                                    | ![step5](./../media/accessibility-step5.png)                 |

