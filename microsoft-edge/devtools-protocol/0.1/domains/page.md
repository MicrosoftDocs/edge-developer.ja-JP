---
description: ページドメインの参照。 検査されたページに関連するアクションとイベントは、ページドメインに属しています。
title: ページドメイン-DevTools プロトコルバージョン0.1
author: pelavall
ms.author: pelavall
ms.date: 12/15/2017
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: a1cd094baef4571240881a86ecccfdb319fef61b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569625"
---
# <span data-ttu-id="41400-104">Page</span><span class="sxs-lookup"><span data-stu-id="41400-104">Page</span></span>
<span data-ttu-id="41400-105">検査されたページに関連するアクションとイベントは、ページドメインに属しています。</span><span class="sxs-lookup"><span data-stu-id="41400-105">Actions and events related to the inspected page belong to the page domain.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="41400-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="41400-106">Methods</span></span>**](#methods) | <span data-ttu-id="41400-107">[有効化](#enable)、[無効化](#disable)、[移動](#navigate)</span><span class="sxs-lookup"><span data-stu-id="41400-107">[enable](#enable), [disable](#disable), [navigate](#navigate)</span></span> |
| [**<span data-ttu-id="41400-108">型</span><span class="sxs-lookup"><span data-stu-id="41400-108">Types</span></span>**](#types) | [<span data-ttu-id="41400-109">フレーム Id</span><span class="sxs-lookup"><span data-stu-id="41400-109">FrameId</span></span>](#frameid) |
## <span data-ttu-id="41400-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="41400-110">Methods</span></span>

### <span data-ttu-id="41400-111">[有効]</span><span class="sxs-lookup"><span data-stu-id="41400-111">enable</span></span>
<span data-ttu-id="41400-112">ページドメインの通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="41400-112">Enables page domain notifications.</span></span>


---

### <span data-ttu-id="41400-113">[無効]</span><span class="sxs-lookup"><span data-stu-id="41400-113">disable</span></span>
<span data-ttu-id="41400-114">ページドメインの通知を無効にします。</span><span class="sxs-lookup"><span data-stu-id="41400-114">Disables page domain notifications.</span></span>


---

### <span data-ttu-id="41400-115">ナビゲート</span><span class="sxs-lookup"><span data-stu-id="41400-115">navigate</span></span>
<span data-ttu-id="41400-116">指定した URL に現在のページを移動します。</span><span class="sxs-lookup"><span data-stu-id="41400-116">Navigates current page to the given URL.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="41400-117">パラメーター</span><span class="sxs-lookup"><span data-stu-id="41400-117">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="41400-118">url</span><span class="sxs-lookup"><span data-stu-id="41400-118">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="41400-119">ページの移動先の URL。</span><span class="sxs-lookup"><span data-stu-id="41400-119">URL to navigate the page to.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="41400-120">返し</span><span class="sxs-lookup"><span data-stu-id="41400-120">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="41400-121">フレーム Id</span><span class="sxs-lookup"><span data-stu-id="41400-121">frameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span><b><span data-ttu-id="41400-122">的.</span><span class="sxs-lookup"><span data-stu-id="41400-122">Experimental.</span></span> </b></span><span data-ttu-id="41400-123">移動されるフレーム id。</span><span class="sxs-lookup"><span data-stu-id="41400-123">Frame id that will be navigated.</span></span></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="41400-124">型</span><span class="sxs-lookup"><span data-stu-id="41400-124">Types</span></span>

### <a name="frameid"></a> <span data-ttu-id="41400-125">フレーム Id</span><span class="sxs-lookup"><span data-stu-id="41400-125">FrameId</span></span> `string`

<span data-ttu-id="41400-126">一意のフレーム識別子。</span><span class="sxs-lookup"><span data-stu-id="41400-126">Unique frame identifier.</span></span>


---
