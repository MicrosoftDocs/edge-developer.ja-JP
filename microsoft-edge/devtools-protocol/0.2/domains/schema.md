---
description: スキーマドメインの参照。 プロトコルスキーマに関する情報を提供します。
title: スキーマドメイン-DevTools プロトコルバージョン0.2
author: pelavall
ms.author: pelavall
ms.date: 8/17/2018
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: df86e6669956c14b7c905514fc44376f71eaa993
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569594"
---
# <span data-ttu-id="0fcac-104">スキーマ</span><span class="sxs-lookup"><span data-stu-id="0fcac-104">Schema</span></span>
<span data-ttu-id="0fcac-105">プロトコルスキーマに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="0fcac-105">Provides information about the protocol schema.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="0fcac-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="0fcac-106">Methods</span></span>**](#methods) | [<span data-ttu-id="0fcac-107">getDomains</span><span class="sxs-lookup"><span data-stu-id="0fcac-107">getDomains</span></span>](#getdomains) |
| [**<span data-ttu-id="0fcac-108">型</span><span class="sxs-lookup"><span data-stu-id="0fcac-108">Types</span></span>**](#types) | [<span data-ttu-id="0fcac-109">ドメイン</span><span class="sxs-lookup"><span data-stu-id="0fcac-109">Domain</span></span>](#domain) |
## <span data-ttu-id="0fcac-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="0fcac-110">Methods</span></span>

### <span data-ttu-id="0fcac-111">getDomains</span><span class="sxs-lookup"><span data-stu-id="0fcac-111">getDomains</span></span>
<span data-ttu-id="0fcac-112">サポートされているドメインを返します。</span><span class="sxs-lookup"><span data-stu-id="0fcac-112">Returns supported domains.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="0fcac-113">返し</span><span class="sxs-lookup"><span data-stu-id="0fcac-113">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="0fcac-114">domains</span><span class="sxs-lookup"><span data-stu-id="0fcac-114">domains</span></span></td>
            <td><a href="#domain"><code class="flyout">Domain[]</code></a></td>
            <td><span data-ttu-id="0fcac-115">サポートされているドメインの一覧。</span><span class="sxs-lookup"><span data-stu-id="0fcac-115">List of supported domains.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="0fcac-116">型</span><span class="sxs-lookup"><span data-stu-id="0fcac-116">Types</span></span>

### <a name="domain"></a> <span data-ttu-id="0fcac-117">ドメイン</span><span class="sxs-lookup"><span data-stu-id="0fcac-117">Domain</span></span> `object`

<span data-ttu-id="0fcac-118">プロトコルドメインの説明。</span><span class="sxs-lookup"><span data-stu-id="0fcac-118">Description of the protocol domain.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="0fcac-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0fcac-119">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="0fcac-120">name</span><span class="sxs-lookup"><span data-stu-id="0fcac-120">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="0fcac-121">ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="0fcac-121">Domain name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="0fcac-122">version</span><span class="sxs-lookup"><span data-stu-id="0fcac-122">version</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="0fcac-123">ドメインバージョン。</span><span class="sxs-lookup"><span data-stu-id="0fcac-123">Domain version.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---
