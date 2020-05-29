---
description: スキーマドメインの参照。 プロトコルスキーマに関する情報を提供します。
title: スキーマドメイン-DevTools プロトコルバージョン0.1
author: pelavall
ms.author: pelavall
ms.date: 12/15/2017
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 83d7019d18ccce1c81b67aafdcafe1a8566694ea
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569619"
---
# <span data-ttu-id="32d62-104">スキーマ</span><span class="sxs-lookup"><span data-stu-id="32d62-104">Schema</span></span>
<span data-ttu-id="32d62-105">プロトコルスキーマに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="32d62-105">Provides information about the protocol schema.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="32d62-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="32d62-106">Methods</span></span>**](#methods) | [<span data-ttu-id="32d62-107">getDomains</span><span class="sxs-lookup"><span data-stu-id="32d62-107">getDomains</span></span>](#getdomains) |
| [**<span data-ttu-id="32d62-108">型</span><span class="sxs-lookup"><span data-stu-id="32d62-108">Types</span></span>**](#types) | [<span data-ttu-id="32d62-109">ドメイン</span><span class="sxs-lookup"><span data-stu-id="32d62-109">Domain</span></span>](#domain) |
## <span data-ttu-id="32d62-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="32d62-110">Methods</span></span>

### <span data-ttu-id="32d62-111">getDomains</span><span class="sxs-lookup"><span data-stu-id="32d62-111">getDomains</span></span>
<span data-ttu-id="32d62-112">サポートされているドメインを返します。</span><span class="sxs-lookup"><span data-stu-id="32d62-112">Returns supported domains.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="32d62-113">返し</span><span class="sxs-lookup"><span data-stu-id="32d62-113">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="32d62-114">domains</span><span class="sxs-lookup"><span data-stu-id="32d62-114">domains</span></span></td>
            <td><a href="#domain"><code class="flyout">Domain[]</code></a></td>
            <td><span data-ttu-id="32d62-115">サポートされているドメインの一覧。</span><span class="sxs-lookup"><span data-stu-id="32d62-115">List of supported domains.</span></span></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="32d62-116">型</span><span class="sxs-lookup"><span data-stu-id="32d62-116">Types</span></span>

### <a name="domain"></a> <span data-ttu-id="32d62-117">ドメイン</span><span class="sxs-lookup"><span data-stu-id="32d62-117">Domain</span></span> `object`

<span data-ttu-id="32d62-118">プロトコルドメインの説明。</span><span class="sxs-lookup"><span data-stu-id="32d62-118">Description of the protocol domain.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="32d62-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="32d62-119">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="32d62-120">name</span><span class="sxs-lookup"><span data-stu-id="32d62-120">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="32d62-121">ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="32d62-121">Domain name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="32d62-122">version</span><span class="sxs-lookup"><span data-stu-id="32d62-122">version</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="32d62-123">ドメインバージョン。</span><span class="sxs-lookup"><span data-stu-id="32d62-123">Domain version.</span></span></td>
        </tr>
    </tbody>
</table>

---
