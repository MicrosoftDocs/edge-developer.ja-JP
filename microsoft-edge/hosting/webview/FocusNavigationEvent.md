---
description: ナビゲーションの理由と場所を含むフォーカスイベントからのディスパッチされたオブジェクト
title: FocusNavigationEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 88f0a4ef8834c6e851f81ee10bf4202a0429f969
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752165"
---
# <span data-ttu-id="574c5-104">FocusNavigationEvent オブジェクト</span><span class="sxs-lookup"><span data-stu-id="574c5-104">FocusNavigationEvent object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="574c5-105">[**NavigateFocus**](../webview.md#navigatefocus) / [**Navigationreason**](#navigationreason)と location を含む NavigateFocus[**DepartingFocus**](../webview.md#departingfocus)のディスパッチされたオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="574c5-105">The dispatched object from [**NavigateFocus**](../webview.md#navigatefocus)/[**DepartingFocus**](../webview.md#departingfocus) containing the [**NavigationReason**](#navigationreason) and location.</span></span>  

## <span data-ttu-id="574c5-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="574c5-106">Methods</span></span>  

### <span data-ttu-id="574c5-107">requestFocus</span><span class="sxs-lookup"><span data-stu-id="574c5-107">requestFocus</span></span>  

<span data-ttu-id="574c5-108">アプリから webview にフォーカスを移動するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="574c5-108">Called to move focus from the app to the webview.</span></span>  

### <span data-ttu-id="574c5-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="574c5-109">Parameters</span></span>  

<span data-ttu-id="574c5-110">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="574c5-110">This method does not have parameters.</span></span>  

### <span data-ttu-id="574c5-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="574c5-111">Return value</span></span>  

<span data-ttu-id="574c5-112">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="574c5-112">This method does not return a value.</span></span>  

## <span data-ttu-id="574c5-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="574c5-113">Properties</span></span>  

### <span data-ttu-id="574c5-114">ナビゲーションの理由</span><span class="sxs-lookup"><span data-stu-id="574c5-114">navigationReason</span></span>  

<span data-ttu-id="574c5-115">"左"、"上"、"右"、または "下" のいずれかの列挙型の**Navigationreason**。</span><span class="sxs-lookup"><span data-stu-id="574c5-115">Enumerated type **NavigationReason**, either "left", "up", "right", or "down".</span></span>  

<span data-ttu-id="574c5-116">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="574c5-116">This property is read-only.</span></span>  

```javascript
var navigationReason = FocusNavigationEvent.navigationReason;
```  

#### <span data-ttu-id="574c5-117">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="574c5-117">Property value</span></span>  

<span data-ttu-id="574c5-118">種類: **Navigationreason**</span><span class="sxs-lookup"><span data-stu-id="574c5-118">Type: **NavigationReason**</span></span>  

### <span data-ttu-id="574c5-119">原点の高さ</span><span class="sxs-lookup"><span data-stu-id="574c5-119">originHeight</span></span>  

<span data-ttu-id="574c5-120">フォーカスを与える要素の元の高さの場所。</span><span class="sxs-lookup"><span data-stu-id="574c5-120">The origin height location of the element to be given focus.</span></span>  

<span data-ttu-id="574c5-121">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="574c5-121">This property is read-only.</span></span>  

```javascript
var originWoriginHeightidth = FocusNavigationEvent.originHeight;
```  

#### <span data-ttu-id="574c5-122">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="574c5-122">Property value</span></span>  

<span data-ttu-id="574c5-123">種類: **float**</span><span class="sxs-lookup"><span data-stu-id="574c5-123">Type: **float**</span></span>  

### <span data-ttu-id="574c5-124">残りの原点</span><span class="sxs-lookup"><span data-stu-id="574c5-124">originLeft</span></span>  

<span data-ttu-id="574c5-125">フォーカスを与える要素の左辺の位置。</span><span class="sxs-lookup"><span data-stu-id="574c5-125">The origin left location of the element to be given focus.</span></span>  

<span data-ttu-id="574c5-126">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="574c5-126">This property is read-only.</span></span>  

```javascript
var originLeft = FocusNavigationEvent.originLeft;
```  

#### <span data-ttu-id="574c5-127">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="574c5-127">Property value</span></span>  

<span data-ttu-id="574c5-128">種類: **float**</span><span class="sxs-lookup"><span data-stu-id="574c5-128">Type: **float**</span></span>  

### <span data-ttu-id="574c5-129">原点の先頭へ</span><span class="sxs-lookup"><span data-stu-id="574c5-129">originTop</span></span>  

<span data-ttu-id="574c5-130">フォーカスを与える要素の起点の上位の位置。</span><span class="sxs-lookup"><span data-stu-id="574c5-130">The origin top location of the element to be given focus.</span></span>  

<span data-ttu-id="574c5-131">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="574c5-131">This property is read-only.</span></span>  

```javascript
var originTop = FocusNavigationEvent.originTop;
```  

#### <span data-ttu-id="574c5-132">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="574c5-132">Property value</span></span>  

<span data-ttu-id="574c5-133">種類: **float**</span><span class="sxs-lookup"><span data-stu-id="574c5-133">Type: **float**</span></span>  

### <span data-ttu-id="574c5-134">原点の幅</span><span class="sxs-lookup"><span data-stu-id="574c5-134">originWidth</span></span>  

<span data-ttu-id="574c5-135">フォーカスを与える要素の元の幅。</span><span class="sxs-lookup"><span data-stu-id="574c5-135">The origin width location of the element to be given focus.</span></span>  

<span data-ttu-id="574c5-136">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="574c5-136">This property is read-only.</span></span>  

```javascript
var originWidth = FocusNavigationEvent.originWidth;
```  

#### <span data-ttu-id="574c5-137">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="574c5-137">Property value</span></span>  

<span data-ttu-id="574c5-138">種類: **float**</span><span class="sxs-lookup"><span data-stu-id="574c5-138">Type: **float**</span></span>  
