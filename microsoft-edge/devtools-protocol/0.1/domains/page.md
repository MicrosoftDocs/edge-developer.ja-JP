---
description: ページドメインの参照。 検査されたページに関連するアクションとイベントは、ページドメインに属しています。
title: ページドメイン-DevTools プロトコルバージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 1602673eae1c04f60046a898dbadeab1b59f9ce5
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882941"
---
# <span data-ttu-id="290d2-104">ページドメイン-DevTools プロトコルバージョン 0.1 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="290d2-104">Page Domain - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  

<span data-ttu-id="290d2-105">検査されたページに関連するアクションとイベントは、ページドメインに属しています。</span><span class="sxs-lookup"><span data-stu-id="290d2-105">Actions and events related to the inspected page belong to the page domain.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="290d2-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="290d2-106">Methods</span></span>**](#methods) | <span data-ttu-id="290d2-107">[有効化](#enable)、[無効化](#disable)、[移動](#navigate)</span><span class="sxs-lookup"><span data-stu-id="290d2-107">[enable](#enable), [disable](#disable), [navigate](#navigate)</span></span> |
| [**<span data-ttu-id="290d2-108">型</span><span class="sxs-lookup"><span data-stu-id="290d2-108">Types</span></span>**](#types) | [<span data-ttu-id="290d2-109">フレーム Id</span><span class="sxs-lookup"><span data-stu-id="290d2-109">FrameId</span></span>](#frameid) |
## <span data-ttu-id="290d2-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="290d2-110">Methods</span></span>

### <span data-ttu-id="290d2-111">[有効]</span><span class="sxs-lookup"><span data-stu-id="290d2-111">enable</span></span>
<span data-ttu-id="290d2-112">ページドメインの通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="290d2-112">Enables page domain notifications.</span></span>


---

### <span data-ttu-id="290d2-113">[無効]</span><span class="sxs-lookup"><span data-stu-id="290d2-113">disable</span></span>
<span data-ttu-id="290d2-114">ページドメインの通知を無効にします。</span><span class="sxs-lookup"><span data-stu-id="290d2-114">Disables page domain notifications.</span></span>


---

### <span data-ttu-id="290d2-115">ナビゲート</span><span class="sxs-lookup"><span data-stu-id="290d2-115">navigate</span></span>
<span data-ttu-id="290d2-116">指定した URL に現在のページを移動します。</span><span class="sxs-lookup"><span data-stu-id="290d2-116">Navigates current page to the given URL.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="290d2-117">パラメーター</span><span class="sxs-lookup"><span data-stu-id="290d2-117">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="290d2-118">url</span><span class="sxs-lookup"><span data-stu-id="290d2-118">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="290d2-119">ページの移動先の URL。</span><span class="sxs-lookup"><span data-stu-id="290d2-119">URL to navigate the page to.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="290d2-120">返し</span><span class="sxs-lookup"><span data-stu-id="290d2-120">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="290d2-121">フレーム Id</span><span class="sxs-lookup"><span data-stu-id="290d2-121">frameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span><b><span data-ttu-id="290d2-122">的.</span><span class="sxs-lookup"><span data-stu-id="290d2-122">Experimental.</span></span> </b></span><span data-ttu-id="290d2-123">移動されるフレーム id。</span><span class="sxs-lookup"><span data-stu-id="290d2-123">Frame id that will be navigated.</span></span></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="290d2-124">型</span><span class="sxs-lookup"><span data-stu-id="290d2-124">Types</span></span>

### <a name="frameid"></a> <span data-ttu-id="290d2-125">フレーム Id</span><span class="sxs-lookup"><span data-stu-id="290d2-125">FrameId</span></span> `string`

<span data-ttu-id="290d2-126">一意のフレーム識別子。</span><span class="sxs-lookup"><span data-stu-id="290d2-126">Unique frame identifier.</span></span>


---
