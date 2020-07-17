---
description: スキーマドメインの参照。 プロトコルスキーマに関する情報を提供します。
title: スキーマドメイン-DevTools プロトコルバージョン 0.2 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: d0fbe9cde742d255797a2460b940732ffa5b8f27
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882878"
---
# <span data-ttu-id="44c9a-104">スキーマドメイン-DevTools プロトコルバージョン 0.2 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="44c9a-104">Schema Domain - DevTools Protocol Version 0.2 (EdgeHTML)</span></span>  

<span data-ttu-id="44c9a-105">プロトコルスキーマに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="44c9a-105">Provides information about the protocol schema.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="44c9a-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="44c9a-106">Methods</span></span>**](#methods) | [<span data-ttu-id="44c9a-107">getDomains</span><span class="sxs-lookup"><span data-stu-id="44c9a-107">getDomains</span></span>](#getdomains) |
| [**<span data-ttu-id="44c9a-108">型</span><span class="sxs-lookup"><span data-stu-id="44c9a-108">Types</span></span>**](#types) | [<span data-ttu-id="44c9a-109">ドメイン</span><span class="sxs-lookup"><span data-stu-id="44c9a-109">Domain</span></span>](#domain) |
## <span data-ttu-id="44c9a-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="44c9a-110">Methods</span></span>

### <span data-ttu-id="44c9a-111">getDomains</span><span class="sxs-lookup"><span data-stu-id="44c9a-111">getDomains</span></span>
<span data-ttu-id="44c9a-112">サポートされているドメインを返します。</span><span class="sxs-lookup"><span data-stu-id="44c9a-112">Returns supported domains.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="44c9a-113">返し</span><span class="sxs-lookup"><span data-stu-id="44c9a-113">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="44c9a-114">domains</span><span class="sxs-lookup"><span data-stu-id="44c9a-114">domains</span></span></td>
            <td><a href="#domain"><code class="flyout">Domain[]</code></a></td>
            <td><span data-ttu-id="44c9a-115">サポートされているドメインの一覧。</span><span class="sxs-lookup"><span data-stu-id="44c9a-115">List of supported domains.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="44c9a-116">型</span><span class="sxs-lookup"><span data-stu-id="44c9a-116">Types</span></span>

### <a name="domain"></a> <span data-ttu-id="44c9a-117">ドメイン</span><span class="sxs-lookup"><span data-stu-id="44c9a-117">Domain</span></span> `object`

<span data-ttu-id="44c9a-118">プロトコルドメインの説明。</span><span class="sxs-lookup"><span data-stu-id="44c9a-118">Description of the protocol domain.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="44c9a-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="44c9a-119">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="44c9a-120">name</span><span class="sxs-lookup"><span data-stu-id="44c9a-120">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="44c9a-121">ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="44c9a-121">Domain name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="44c9a-122">version</span><span class="sxs-lookup"><span data-stu-id="44c9a-122">version</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="44c9a-123">ドメインバージョン。</span><span class="sxs-lookup"><span data-stu-id="44c9a-123">Domain version.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---
