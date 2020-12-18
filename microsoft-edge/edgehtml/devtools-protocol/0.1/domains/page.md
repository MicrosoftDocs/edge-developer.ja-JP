---
description: ページ ドメインの DevTools プロトコル バージョン 0.1 (EdgeHTML) リファレンス。 検査されたページに関連するアクションとイベントは、ページ ドメインに属しています。
title: ページ ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 55575e54b9125d7ff544c23c81da4b15d3b56fb1
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234801"
---
# <span data-ttu-id="3c78d-104">ページ ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="3c78d-104">Page Domain - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  

<span data-ttu-id="3c78d-105">検査されたページに関連するアクションとイベントは、ページ ドメインに属しています。</span><span class="sxs-lookup"><span data-stu-id="3c78d-105">Actions and events related to the inspected page belong to the page domain.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="3c78d-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="3c78d-106">Methods</span></span>**](#methods) | <span data-ttu-id="3c78d-107">[有効、](#enable)[無効、](#disable)[移動](#navigate)</span><span class="sxs-lookup"><span data-stu-id="3c78d-107">[enable](#enable), [disable](#disable), [navigate](#navigate)</span></span> |
| [**<span data-ttu-id="3c78d-108">型</span><span class="sxs-lookup"><span data-stu-id="3c78d-108">Types</span></span>**](#types) | [<span data-ttu-id="3c78d-109">FrameId</span><span class="sxs-lookup"><span data-stu-id="3c78d-109">FrameId</span></span>](#frameid) |
## <span data-ttu-id="3c78d-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="3c78d-110">Methods</span></span>

### <span data-ttu-id="3c78d-111">[有効]</span><span class="sxs-lookup"><span data-stu-id="3c78d-111">enable</span></span>
<span data-ttu-id="3c78d-112">ページ ドメイン通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3c78d-112">Enables page domain notifications.</span></span>


---

### <span data-ttu-id="3c78d-113">[無効]</span><span class="sxs-lookup"><span data-stu-id="3c78d-113">disable</span></span>
<span data-ttu-id="3c78d-114">ページ ドメイン通知を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3c78d-114">Disables page domain notifications.</span></span>


---

### <span data-ttu-id="3c78d-115">ナビゲート</span><span class="sxs-lookup"><span data-stu-id="3c78d-115">navigate</span></span>
<span data-ttu-id="3c78d-116">現在のページを特定の URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="3c78d-116">Navigates current page to the given URL.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="3c78d-117">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3c78d-117">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="3c78d-118">url</span><span class="sxs-lookup"><span data-stu-id="3c78d-118">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="3c78d-119">ページの移動先の URL。</span><span class="sxs-lookup"><span data-stu-id="3c78d-119">URL to navigate the page to.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="3c78d-120">戻り値</span><span class="sxs-lookup"><span data-stu-id="3c78d-120">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="3c78d-121">frameId</span><span class="sxs-lookup"><span data-stu-id="3c78d-121">frameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span><b><span data-ttu-id="3c78d-122">試験的。</span><span class="sxs-lookup"><span data-stu-id="3c78d-122">Experimental.</span></span> </b></span><span data-ttu-id="3c78d-123">移動するフレーム ID です。</span><span class="sxs-lookup"><span data-stu-id="3c78d-123">Frame id that will be navigated.</span></span></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="3c78d-124">型</span><span class="sxs-lookup"><span data-stu-id="3c78d-124">Types</span></span>

### <a name="frameid"></a> <span data-ttu-id="3c78d-125">FrameId</span><span class="sxs-lookup"><span data-stu-id="3c78d-125">FrameId</span></span> `string`

<span data-ttu-id="3c78d-126">一意のフレーム識別子。</span><span class="sxs-lookup"><span data-stu-id="3c78d-126">Unique frame identifier.</span></span>


---
