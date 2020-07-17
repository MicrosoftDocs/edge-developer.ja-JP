---
description: スキーマドメインの参照。 プロトコルスキーマに関する情報を提供します。
title: スキーマドメイン-DevTools プロトコルバージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: a2f679f6f4bf8e82dc7298d96f798507b1338062
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882927"
---
# <span data-ttu-id="d2edb-104">スキーマドメイン-DevTools プロトコルバージョン 0.1 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="d2edb-104">Schema Domain - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  

<span data-ttu-id="d2edb-105">プロトコルスキーマに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d2edb-105">Provides information about the protocol schema.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="d2edb-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="d2edb-106">Methods</span></span>**](#methods) | [<span data-ttu-id="d2edb-107">getDomains</span><span class="sxs-lookup"><span data-stu-id="d2edb-107">getDomains</span></span>](#getdomains) |
| [**<span data-ttu-id="d2edb-108">型</span><span class="sxs-lookup"><span data-stu-id="d2edb-108">Types</span></span>**](#types) | [<span data-ttu-id="d2edb-109">ドメイン</span><span class="sxs-lookup"><span data-stu-id="d2edb-109">Domain</span></span>](#domain) |
## <span data-ttu-id="d2edb-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="d2edb-110">Methods</span></span>

### <span data-ttu-id="d2edb-111">getDomains</span><span class="sxs-lookup"><span data-stu-id="d2edb-111">getDomains</span></span>
<span data-ttu-id="d2edb-112">サポートされているドメインを返します。</span><span class="sxs-lookup"><span data-stu-id="d2edb-112">Returns supported domains.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="d2edb-113">返し</span><span class="sxs-lookup"><span data-stu-id="d2edb-113">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="d2edb-114">domains</span><span class="sxs-lookup"><span data-stu-id="d2edb-114">domains</span></span></td>
            <td><a href="#domain"><code class="flyout">Domain[]</code></a></td>
            <td><span data-ttu-id="d2edb-115">サポートされているドメインの一覧。</span><span class="sxs-lookup"><span data-stu-id="d2edb-115">List of supported domains.</span></span></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="d2edb-116">型</span><span class="sxs-lookup"><span data-stu-id="d2edb-116">Types</span></span>

### <a name="domain"></a> <span data-ttu-id="d2edb-117">ドメイン</span><span class="sxs-lookup"><span data-stu-id="d2edb-117">Domain</span></span> `object`

<span data-ttu-id="d2edb-118">プロトコルドメインの説明。</span><span class="sxs-lookup"><span data-stu-id="d2edb-118">Description of the protocol domain.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="d2edb-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d2edb-119">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="d2edb-120">name</span><span class="sxs-lookup"><span data-stu-id="d2edb-120">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="d2edb-121">ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="d2edb-121">Domain name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="d2edb-122">version</span><span class="sxs-lookup"><span data-stu-id="d2edb-122">version</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="d2edb-123">ドメインバージョン。</span><span class="sxs-lookup"><span data-stu-id="d2edb-123">Domain version.</span></span></td>
        </tr>
    </tbody>
</table>

---
