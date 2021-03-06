---
description: ページ ドメインの DevTools プロトコル バージョン 0.1 (EdgeHTML) リファレンス。 検査されたページに関連するアクションとイベントは、ページ ドメインに属します。
title: ページ ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b04b0685a6b465d40e999a2a48d370573a3058d8
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399149"
---
# <a name="page-domain---devtools-protocol-version-01-edgehtml"></a><span data-ttu-id="f2fa8-104">ページ ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="f2fa8-104">Page Domain - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  

<span data-ttu-id="f2fa8-105">検査されたページに関連するアクションとイベントは、ページ ドメインに属します。</span><span class="sxs-lookup"><span data-stu-id="f2fa8-105">Actions and events related to the inspected page belong to the page domain.</span></span>  

| <span data-ttu-id="f2fa8-106">分類</span><span class="sxs-lookup"><span data-stu-id="f2fa8-106">Classification</span></span> | <span data-ttu-id="f2fa8-107">Members</span><span class="sxs-lookup"><span data-stu-id="f2fa8-107">Members</span></span> |  
|:--- |:--- |  
| [**<span data-ttu-id="f2fa8-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="f2fa8-108">Methods</span></span>**](#methods) | <span data-ttu-id="f2fa8-109">[有効にする](#enable)、[無効にする、](#disable)[移動する](#navigate)</span><span class="sxs-lookup"><span data-stu-id="f2fa8-109">[enable](#enable), [disable](#disable), [navigate](#navigate)</span></span> |  
| [**<span data-ttu-id="f2fa8-110">型</span><span class="sxs-lookup"><span data-stu-id="f2fa8-110">Types</span></span>**](#types) | [<span data-ttu-id="f2fa8-111">FrameId</span><span class="sxs-lookup"><span data-stu-id="f2fa8-111">FrameId</span></span>](#frameid) |  

## <a name="methods"></a><span data-ttu-id="f2fa8-112">メソッド</span><span class="sxs-lookup"><span data-stu-id="f2fa8-112">Methods</span></span>  

### <a name="enable"></a><span data-ttu-id="f2fa8-113">[有効]</span><span class="sxs-lookup"><span data-stu-id="f2fa8-113">enable</span></span>  

<span data-ttu-id="f2fa8-114">ページ ドメイン通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f2fa8-114">Enables page domain notifications.</span></span>  

&nbsp;  

---  

### <a name="disable"></a><span data-ttu-id="f2fa8-115">[無効]</span><span class="sxs-lookup"><span data-stu-id="f2fa8-115">disable</span></span>  

<span data-ttu-id="f2fa8-116">ページ ドメイン通知を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f2fa8-116">Disables page domain notifications.</span></span>  

&nbsp;  

---  

### <a name="navigate"></a><span data-ttu-id="f2fa8-117">ナビゲート</span><span class="sxs-lookup"><span data-stu-id="f2fa8-117">navigate</span></span>  

<span data-ttu-id="f2fa8-118">現在のページを特定の URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="f2fa8-118">Navigates current page to the given URL.</span></span>  

| <span data-ttu-id="f2fa8-119">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f2fa8-119">Parameters</span></span> | <span data-ttu-id="f2fa8-120">型</span><span class="sxs-lookup"><span data-stu-id="f2fa8-120">Type</span></span> | <span data-ttu-id="f2fa8-121">詳細</span><span class="sxs-lookup"><span data-stu-id="f2fa8-121">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f2fa8-122">url</span><span class="sxs-lookup"><span data-stu-id="f2fa8-122">url</span></span> | `string` | <span data-ttu-id="f2fa8-123">ページを移動する URL。</span><span class="sxs-lookup"><span data-stu-id="f2fa8-123">URL to navigate the page to.</span></span> |  

| <span data-ttu-id="f2fa8-124">戻り値</span><span class="sxs-lookup"><span data-stu-id="f2fa8-124">Returns</span></span> | <span data-ttu-id="f2fa8-125">型</span><span class="sxs-lookup"><span data-stu-id="f2fa8-125">Type</span></span> | <span data-ttu-id="f2fa8-126">詳細</span><span class="sxs-lookup"><span data-stu-id="f2fa8-126">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="f2fa8-127">frameId</span><span class="sxs-lookup"><span data-stu-id="f2fa8-127">frameId</span></span> | [<span data-ttu-id="f2fa8-128">FrameId</span><span class="sxs-lookup"><span data-stu-id="f2fa8-128">FrameId</span></span>](#frameid) | <span data-ttu-id="f2fa8-129">**実験的な**.</span><span class="sxs-lookup"><span data-stu-id="f2fa8-129">**Experimental**.</span></span>  <span data-ttu-id="f2fa8-130">移動するフレーム ID。</span><span class="sxs-lookup"><span data-stu-id="f2fa8-130">Frame ID that will be navigated.</span></span> |  

---  

## <a name="types"></a><span data-ttu-id="f2fa8-131">型</span><span class="sxs-lookup"><span data-stu-id="f2fa8-131">Types</span></span>  

### <a name="frameid-string"></a><span data-ttu-id="f2fa8-132">FrameId 文字列</span><span class="sxs-lookup"><span data-stu-id="f2fa8-132">FrameId string</span></span>  

<a name="frameid"></a>  

<span data-ttu-id="f2fa8-133">一意のフレーム識別子。</span><span class="sxs-lookup"><span data-stu-id="f2fa8-133">Unique frame identifier.</span></span>  

&nbsp;  

---  
