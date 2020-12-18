---
description: スキーマ ドメインの DevTools プロトコル バージョン 0.2 (EdgeHTML) リファレンス。 プロトコル スキーマに関する情報を提供します。
title: スキーマ ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 12/16/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 53038a02844fafc9550a6ac26303620a1a0183f8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234406"
---
# <span data-ttu-id="8b450-104">スキーマ ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="8b450-104">Schema Domain - DevTools Protocol Version 0.2 (EdgeHTML)</span></span>  

<span data-ttu-id="8b450-105">プロトコル スキーマに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="8b450-105">Provides information about the protocol schema.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="8b450-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="8b450-106">Methods</span></span>**](#methods) | [<span data-ttu-id="8b450-107">getDomains</span><span class="sxs-lookup"><span data-stu-id="8b450-107">getDomains</span></span>](#getdomains) |
| [**<span data-ttu-id="8b450-108">型</span><span class="sxs-lookup"><span data-stu-id="8b450-108">Types</span></span>**](#types) | [<span data-ttu-id="8b450-109">ドメイン</span><span class="sxs-lookup"><span data-stu-id="8b450-109">Domain</span></span>](#domain) |
## <span data-ttu-id="8b450-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="8b450-110">Methods</span></span>

### <span data-ttu-id="8b450-111">getDomains</span><span class="sxs-lookup"><span data-stu-id="8b450-111">getDomains</span></span>
<span data-ttu-id="8b450-112">サポートされているドメインを返します。</span><span class="sxs-lookup"><span data-stu-id="8b450-112">Returns supported domains.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="8b450-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="8b450-113">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="8b450-114">domains</span><span class="sxs-lookup"><span data-stu-id="8b450-114">domains</span></span></td>
            <td><a href="#domain"><code class="flyout">Domain[]</code></a></td>
            <td><span data-ttu-id="8b450-115">サポートされているドメインの一覧。</span><span class="sxs-lookup"><span data-stu-id="8b450-115">List of supported domains.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="8b450-116">型</span><span class="sxs-lookup"><span data-stu-id="8b450-116">Types</span></span>

### <a name="domain"></a> <span data-ttu-id="8b450-117">ドメイン</span><span class="sxs-lookup"><span data-stu-id="8b450-117">Domain</span></span> `object`

<span data-ttu-id="8b450-118">プロトコル ドメインの説明。</span><span class="sxs-lookup"><span data-stu-id="8b450-118">Description of the protocol domain.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="8b450-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8b450-119">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="8b450-120">name</span><span class="sxs-lookup"><span data-stu-id="8b450-120">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="8b450-121">ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="8b450-121">Domain name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="8b450-122">version</span><span class="sxs-lookup"><span data-stu-id="8b450-122">version</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="8b450-123">ドメインのバージョン。</span><span class="sxs-lookup"><span data-stu-id="8b450-123">Domain version.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---
