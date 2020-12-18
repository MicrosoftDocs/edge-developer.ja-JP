---
description: スキーマ ドメインの DevTools プロトコル バージョン 0.1 (EdgeHTML) リファレンス。 プロトコル スキーマに関する情報を提供します。
title: スキーマ ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7b4ec71b7799ae099c673bd81fa5b15a8ddd5d27
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234794"
---
# <span data-ttu-id="9c080-104">スキーマ ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="9c080-104">Schema Domain - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  

<span data-ttu-id="9c080-105">プロトコル スキーマに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="9c080-105">Provides information about the protocol schema.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="9c080-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="9c080-106">Methods</span></span>**](#methods) | [<span data-ttu-id="9c080-107">getDomains</span><span class="sxs-lookup"><span data-stu-id="9c080-107">getDomains</span></span>](#getdomains) |
| [**<span data-ttu-id="9c080-108">型</span><span class="sxs-lookup"><span data-stu-id="9c080-108">Types</span></span>**](#types) | [<span data-ttu-id="9c080-109">ドメイン</span><span class="sxs-lookup"><span data-stu-id="9c080-109">Domain</span></span>](#domain) |
## <span data-ttu-id="9c080-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="9c080-110">Methods</span></span>

### <span data-ttu-id="9c080-111">getDomains</span><span class="sxs-lookup"><span data-stu-id="9c080-111">getDomains</span></span>
<span data-ttu-id="9c080-112">サポートされているドメインを返します。</span><span class="sxs-lookup"><span data-stu-id="9c080-112">Returns supported domains.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="9c080-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="9c080-113">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="9c080-114">domains</span><span class="sxs-lookup"><span data-stu-id="9c080-114">domains</span></span></td>
            <td><a href="#domain"><code class="flyout">Domain[]</code></a></td>
            <td><span data-ttu-id="9c080-115">サポートされているドメインの一覧。</span><span class="sxs-lookup"><span data-stu-id="9c080-115">List of supported domains.</span></span></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="9c080-116">型</span><span class="sxs-lookup"><span data-stu-id="9c080-116">Types</span></span>

### <a name="domain"></a> <span data-ttu-id="9c080-117">ドメイン</span><span class="sxs-lookup"><span data-stu-id="9c080-117">Domain</span></span> `object`

<span data-ttu-id="9c080-118">プロトコル ドメインの説明。</span><span class="sxs-lookup"><span data-stu-id="9c080-118">Description of the protocol domain.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="9c080-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9c080-119">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="9c080-120">name</span><span class="sxs-lookup"><span data-stu-id="9c080-120">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="9c080-121">ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="9c080-121">Domain name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="9c080-122">version</span><span class="sxs-lookup"><span data-stu-id="9c080-122">version</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="9c080-123">ドメインのバージョン。</span><span class="sxs-lookup"><span data-stu-id="9c080-123">Domain version.</span></span></td>
        </tr>
    </tbody>
</table>

---
