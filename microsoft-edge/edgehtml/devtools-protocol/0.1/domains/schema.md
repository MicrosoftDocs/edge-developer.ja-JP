---
description: スキーマ ドメインの DevTools プロトコル バージョン 0.1 (EdgeHTML) リファレンス。 プロトコル スキーマに関する情報を提供します。
title: スキーマ ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e89f4269b4984ee49e83a23fcab9679485c49040
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398862"
---
# <a name="schema-domain---devtools-protocol-version-01-edgehtml"></a><span data-ttu-id="8e065-104">スキーマ ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="8e065-104">Schema Domain - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  

<span data-ttu-id="8e065-105">プロトコル スキーマに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="8e065-105">Provides information about the protocol schema.</span></span>  

| <span data-ttu-id="8e065-106">分類</span><span class="sxs-lookup"><span data-stu-id="8e065-106">Classification</span></span> | <span data-ttu-id="8e065-107">Members</span><span class="sxs-lookup"><span data-stu-id="8e065-107">Members</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="8e065-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="8e065-108">Methods</span></span>](#methods) | [<span data-ttu-id="8e065-109">getDomains</span><span class="sxs-lookup"><span data-stu-id="8e065-109">getDomains</span></span>](#getdomains) |  
| [<span data-ttu-id="8e065-110">型</span><span class="sxs-lookup"><span data-stu-id="8e065-110">Types</span></span>](#types) | [<span data-ttu-id="8e065-111">ドメイン</span><span class="sxs-lookup"><span data-stu-id="8e065-111">Domain</span></span>](#domain) |  

## <a name="methods"></a><span data-ttu-id="8e065-112">メソッド</span><span class="sxs-lookup"><span data-stu-id="8e065-112">Methods</span></span>  

### <a name="getdomains"></a><span data-ttu-id="8e065-113">getDomains</span><span class="sxs-lookup"><span data-stu-id="8e065-113">getDomains</span></span>  

<span data-ttu-id="8e065-114">サポートされているドメインを返します。</span><span class="sxs-lookup"><span data-stu-id="8e065-114">Returns supported domains.</span></span>  

| <span data-ttu-id="8e065-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="8e065-115">Returns</span></span> | <span data-ttu-id="8e065-116">型</span><span class="sxs-lookup"><span data-stu-id="8e065-116">Type</span></span> | <span data-ttu-id="8e065-117">詳細</span><span class="sxs-lookup"><span data-stu-id="8e065-117">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="8e065-118">ドメイン</span><span class="sxs-lookup"><span data-stu-id="8e065-118">domains</span></span> | [<span data-ttu-id="8e065-119">Domain[]</span><span class="sxs-lookup"><span data-stu-id="8e065-119">Domain[]</span></span>](#domain) | <span data-ttu-id="8e065-120">サポートされているドメインの一覧。</span><span class="sxs-lookup"><span data-stu-id="8e065-120">List of supported domains.</span></span> |  

---  

## <a name="types"></a><span data-ttu-id="8e065-121">型</span><span class="sxs-lookup"><span data-stu-id="8e065-121">Types</span></span>  

### <a name="domain-object"></a><span data-ttu-id="8e065-122">Domain オブジェクト</span><span class="sxs-lookup"><span data-stu-id="8e065-122">Domain object</span></span>  

<a name="domain"></a>  

<span data-ttu-id="8e065-123">プロトコル ドメインの説明。</span><span class="sxs-lookup"><span data-stu-id="8e065-123">Description of the protocol domain.</span></span>  

| <span data-ttu-id="8e065-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8e065-124">Properties</span></span> | <span data-ttu-id="8e065-125">型</span><span class="sxs-lookup"><span data-stu-id="8e065-125">Type</span></span> | <span data-ttu-id="8e065-126">詳細</span><span class="sxs-lookup"><span data-stu-id="8e065-126">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="8e065-127">name</span><span class="sxs-lookup"><span data-stu-id="8e065-127">name</span></span> | `string` | <span data-ttu-id="8e065-128">ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="8e065-128">Domain name.</span></span> |  
| <span data-ttu-id="8e065-129">version</span><span class="sxs-lookup"><span data-stu-id="8e065-129">version</span></span> | `string` | <span data-ttu-id="8e065-130">ドメイン バージョン。</span><span class="sxs-lookup"><span data-stu-id="8e065-130">Domain version.</span></span> |  

---  
