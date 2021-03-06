---
description: スキーマ ドメインの DevTools プロトコル バージョン 0.2 (EdgeHTML) リファレンス。 プロトコル スキーマに関する情報を提供します。
title: スキーマ ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 6844939f452bc96980d6d67d4652adcc7c078c7a
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398148"
---
# <a name="schema-domain---devtools-protocol-version-02-edgehtml"></a><span data-ttu-id="c2af4-104">スキーマ ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="c2af4-104">Schema Domain - DevTools Protocol Version 0.2 (EdgeHTML)</span></span>  

<span data-ttu-id="c2af4-105">プロトコル スキーマに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c2af4-105">Provides information about the protocol schema.</span></span>  

| <span data-ttu-id="c2af4-106">分類</span><span class="sxs-lookup"><span data-stu-id="c2af4-106">Classification</span></span> | <span data-ttu-id="c2af4-107">Members</span><span class="sxs-lookup"><span data-stu-id="c2af4-107">Members</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="c2af4-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="c2af4-108">Methods</span></span>](#methods) | [<span data-ttu-id="c2af4-109">getDomains</span><span class="sxs-lookup"><span data-stu-id="c2af4-109">getDomains</span></span>](#getdomains) |  
| [<span data-ttu-id="c2af4-110">型</span><span class="sxs-lookup"><span data-stu-id="c2af4-110">Types</span></span>](#types) | [<span data-ttu-id="c2af4-111">Domain オブジェクト</span><span class="sxs-lookup"><span data-stu-id="c2af4-111">Domain object</span></span>](#domain) |  

## <a name="methods"></a><span data-ttu-id="c2af4-112">メソッド</span><span class="sxs-lookup"><span data-stu-id="c2af4-112">Methods</span></span>  

### <a name="getdomains"></a><span data-ttu-id="c2af4-113">getDomains</span><span class="sxs-lookup"><span data-stu-id="c2af4-113">getDomains</span></span>  

<span data-ttu-id="c2af4-114">サポートされているドメインを返します。</span><span class="sxs-lookup"><span data-stu-id="c2af4-114">Returns supported domains.</span></span>  

| <span data-ttu-id="c2af4-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="c2af4-115">Returns</span></span> | <span data-ttu-id="c2af4-116">型</span><span class="sxs-lookup"><span data-stu-id="c2af4-116">Type</span></span> | <span data-ttu-id="c2af4-117">詳細</span><span class="sxs-lookup"><span data-stu-id="c2af4-117">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="c2af4-118">ドメイン</span><span class="sxs-lookup"><span data-stu-id="c2af4-118">domains</span></span> | [<span data-ttu-id="c2af4-119">Domain[]</span><span class="sxs-lookup"><span data-stu-id="c2af4-119">Domain[]</span></span>](#domain) | <span data-ttu-id="c2af4-120">サポートされているドメインの一覧。</span><span class="sxs-lookup"><span data-stu-id="c2af4-120">List of supported domains.</span></span> |  

---  

## <a name="types"></a><span data-ttu-id="c2af4-121">型</span><span class="sxs-lookup"><span data-stu-id="c2af4-121">Types</span></span>  

### <a name="domain-object"></a><span data-ttu-id="c2af4-122">Domain オブジェクト</span><span class="sxs-lookup"><span data-stu-id="c2af4-122">Domain object</span></span>  

<a name="domain"></a>  

<span data-ttu-id="c2af4-123">プロトコル ドメインの説明。</span><span class="sxs-lookup"><span data-stu-id="c2af4-123">Description of the protocol domain.</span></span>  

| <span data-ttu-id="c2af4-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c2af4-124">Properties</span></span> | <span data-ttu-id="c2af4-125">型</span><span class="sxs-lookup"><span data-stu-id="c2af4-125">Type</span></span> | <span data-ttu-id="c2af4-126">詳細</span><span class="sxs-lookup"><span data-stu-id="c2af4-126">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="c2af4-127">name</span><span class="sxs-lookup"><span data-stu-id="c2af4-127">name</span></span> | `string` | <span data-ttu-id="c2af4-128">ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="c2af4-128">Domain name.</span></span> |  
| <span data-ttu-id="c2af4-129">version</span><span class="sxs-lookup"><span data-stu-id="c2af4-129">version</span></span> | `string` | <span data-ttu-id="c2af4-130">ドメイン バージョン。</span><span class="sxs-lookup"><span data-stu-id="c2af4-130">Domain version.</span></span> |  

---  
