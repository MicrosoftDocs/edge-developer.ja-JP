---
ms.assetid: c4544a19-de78-4c69-a042-c0415726548f
description: ライトとダークモードの両方で拡張機能のアイコンが表示されるようにするには、アクセシビリティガイドに従います。
title: アクセシビリティ-拡張子 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: 60e794467c6d054e390ce61c40559afa3a110c21
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882794"
---
# <span data-ttu-id="afa23-104">アクセシビリティ-拡張子 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="afa23-104">Accessibility - Extensions (EdgeHTML)</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

## <span data-ttu-id="afa23-105">Microsoft Edge のアクセシビリティ対応の拡張機能アイコンの作成</span><span class="sxs-lookup"><span data-stu-id="afa23-105">Creating accessible extension icons for Microsoft Edge</span></span>

<span data-ttu-id="afa23-106">サードパーティの拡張機能の開発者は、Microsoft の厳格なアクセシビリティ要件を満たしている画像アセットを使用することをお勧めします。これにより、淡色テーマと濃色テーマの両方でアイコンが明確に表示されます。</span><span class="sxs-lookup"><span data-stu-id="afa23-106">Third-party extension developers are encouraged to use image assets that meet Microsoft’s strict accessibility requirements so that icons are clearly visible for both light and dark themes.</span></span> <span data-ttu-id="afa23-107">すべての拡張アイコンには、アイコンの背景色とアイコン自体の主要色との比率を14:1 にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="afa23-107">We recommend that all extension icons have a 14:1 ratio between the icon’s background color and the dominant color of the icon itself.</span></span>


<span data-ttu-id="afa23-108">Microsoft が開発した初回パーティの拡張機能は、これらの要件を満たすために "stickering" の視覚的な処理を適用します。</span><span class="sxs-lookup"><span data-stu-id="afa23-108">First-party extensions developed by Microsoft apply a “stickering” visual treatment to satisfy these requirements.</span></span>

### <span data-ttu-id="afa23-109">"Stickering" の例</span><span class="sxs-lookup"><span data-stu-id="afa23-109">Examples of the "stickering"</span></span>

<span data-ttu-id="afa23-110">"Stickering" の主な目標は、アイコンを背景色で視覚的にアクセスできるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="afa23-110">The main goal of “stickering” is to make the icon visually accessible on any background color.</span></span> <span data-ttu-id="afa23-111">白の外側のストロークとアイコンの間の推奨色の比率は、ハイコントラストの要件をサポートするために、14:1 である必要があります。</span><span class="sxs-lookup"><span data-stu-id="afa23-111">The recommended color ratio between the white outer stroke and your icon should be 14:1 to support the high contrast requirements.</span></span>

#### <span data-ttu-id="afa23-112">適切なアイコン</span><span class="sxs-lookup"><span data-stu-id="afa23-112">Good icon</span></span>
<span data-ttu-id="afa23-113">Stickering では、基本的に暗いアイコンが背景色に表示されたままになります。</span><span class="sxs-lookup"><span data-stu-id="afa23-113">With stickering, a primarily dark icon will remain visible on any background color.</span></span>


![背景色に表示されているアイコンの画像](./../media/accessibility-light-to-dark-good.png)

#### <span data-ttu-id="afa23-115">不正なアイコン</span><span class="sxs-lookup"><span data-stu-id="afa23-115">Bad icon</span></span>
<span data-ttu-id="afa23-116">Stickering を使わないと、アイコンが背景とブレンドされ、見えなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="afa23-116">Without stickering, an icon could blend in with the background and become impossible to see.</span></span>


![黒の背景にブレンドされるアイコンの画像](./../media/accessibility-light-to-dark-bad.png)

### <span data-ttu-id="afa23-118">"Stickering" の拡張機能アイコン</span><span class="sxs-lookup"><span data-stu-id="afa23-118">"Stickering" your extension icon</span></span>

<span data-ttu-id="afa23-119">次の5つの手順では、Microsoft のアクセシビリティ要件を満たす拡張機能アイコンの作成方法の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="afa23-119">The following five steps outline the suggested method of creating an extension icon that meets Microsoft’s accessibility requirements:</span></span>


| <span data-ttu-id="afa23-120">ステップ 1</span><span class="sxs-lookup"><span data-stu-id="afa23-120">Step 1</span></span>                                       | <span data-ttu-id="afa23-121">ステップ 2</span><span class="sxs-lookup"><span data-stu-id="afa23-121">Step 2</span></span>                                       | <span data-ttu-id="afa23-122">ステップ 3</span><span class="sxs-lookup"><span data-stu-id="afa23-122">Step 3</span></span>                                                                                 | <span data-ttu-id="afa23-123">ステップ 4</span><span class="sxs-lookup"><span data-stu-id="afa23-123">Step 4</span></span>                                                                          | <span data-ttu-id="afa23-124">ステップ 5</span><span class="sxs-lookup"><span data-stu-id="afa23-124">Step 5</span></span>                                                       |
|:---------------------------------------------|:---------------------------------------------|:---------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------|:-------------------------------------------------------------|
| <span data-ttu-id="afa23-125">指定した grid 内にアイコンを設定します。</span><span class="sxs-lookup"><span data-stu-id="afa23-125">Set your icon within your specified grid.</span></span>    | <span data-ttu-id="afa23-126">アイコンのサイズを2ピクセル小さくします。</span><span class="sxs-lookup"><span data-stu-id="afa23-126">Reduce your icon size by 2 pixels.</span></span>           | <span data-ttu-id="afa23-127">アイコンをコピーして、適切な場所に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="afa23-127">Copy your icon and paste in place.</span></span> <span data-ttu-id="afa23-128">角が丸い2ピクセルの外側のストロークを作成します。</span><span class="sxs-lookup"><span data-stu-id="afa23-128">Create a 2 pixel outer stroke with rounded corners.</span></span> | <span data-ttu-id="afa23-129">ストロークのアウトラインを作成し、複合パスを解放し、残りの図形を結合します。</span><span class="sxs-lookup"><span data-stu-id="afa23-129">Outline your stroke, release the compound path, and merge the remaining shapes.</span></span> | <span data-ttu-id="afa23-130">目的に応じて、外側のストロークの白と内側のアイコンの色を設定します。</span><span class="sxs-lookup"><span data-stu-id="afa23-130">Color the outer stroke white and the inner icon as you wish.</span></span> |
| ![手順1](./../media/accessibility-step1.png) | ![手順2](./../media/accessibility-step2.png) | ![step3](./../media/accessibility-step3.png)                                           | ![step4](./../media/accessibility-step4.png)                                    | ![step5](./../media/accessibility-step5.png)                 |

