---
description: ナビゲーションの理由と場所を含むフォーカスイベントからのディスパッチされたオブジェクト
title: FocusNavigationEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: b988bcd7ff252b9972bef9a31339a34b4b58d9ee
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569244"
---
# <span data-ttu-id="6d17c-104">FocusNavigationEvent オブジェクト</span><span class="sxs-lookup"><span data-stu-id="6d17c-104">FocusNavigationEvent object</span></span>

<span data-ttu-id="6d17c-105">[**NavigateFocus**](../webview.md#navigatefocus) / [**Navigationreason**](#navigationreason)と location を含む NavigateFocus[**DepartingFocus**](../webview.md#departingfocus)のディスパッチされたオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6d17c-105">The dispatched object from [**NavigateFocus**](../webview.md#navigatefocus)/[**DepartingFocus**](../webview.md#departingfocus) containing the [**NavigationReason**](#navigationreason) and location.</span></span> 

## <span data-ttu-id="6d17c-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="6d17c-106">Methods</span></span>

### <span data-ttu-id="6d17c-107">requestFocus</span><span class="sxs-lookup"><span data-stu-id="6d17c-107">requestFocus</span></span>

<span data-ttu-id="6d17c-108">アプリから webview にフォーカスを移動するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6d17c-108">Called to move focus from the app to the webview.</span></span>

### <span data-ttu-id="6d17c-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6d17c-109">Parameters</span></span>

<span data-ttu-id="6d17c-110">このメソッドにはパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="6d17c-110">This method does not have parameters.</span></span>

### <span data-ttu-id="6d17c-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="6d17c-111">Return value</span></span>

<span data-ttu-id="6d17c-112">このメソッドに戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="6d17c-112">This method does not return a value.</span></span>

## <span data-ttu-id="6d17c-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6d17c-113">Properties</span></span>
    
### <span data-ttu-id="6d17c-114">ナビゲーションの理由</span><span class="sxs-lookup"><span data-stu-id="6d17c-114">navigationReason</span></span>

<span data-ttu-id="6d17c-115">"左"、"上"、"右"、または "下" のいずれかの列挙型の**Navigationreason**。</span><span class="sxs-lookup"><span data-stu-id="6d17c-115">Enumerated type **NavigationReason**, either "left", "up", "right", or "down".</span></span> 

<span data-ttu-id="6d17c-116">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="6d17c-116">This property is read-only.</span></span>

```js
var navigationReason = FocusNavigationEvent.navigationReason;
```

#### <span data-ttu-id="6d17c-117">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="6d17c-117">Property value</span></span>
<span data-ttu-id="6d17c-118">種類: **Navigationreason**</span><span class="sxs-lookup"><span data-stu-id="6d17c-118">Type: **NavigationReason**</span></span>

### <span data-ttu-id="6d17c-119">原点の高さ</span><span class="sxs-lookup"><span data-stu-id="6d17c-119">originHeight</span></span>

<span data-ttu-id="6d17c-120">フォーカスを与える要素の元の高さの場所。</span><span class="sxs-lookup"><span data-stu-id="6d17c-120">The origin height location of the element to be given focus.</span></span>

<span data-ttu-id="6d17c-121">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="6d17c-121">This property is read-only.</span></span>

```js
var originWoriginHeightidth = FocusNavigationEvent.originHeight;
```

#### <span data-ttu-id="6d17c-122">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="6d17c-122">Property value</span></span>
<span data-ttu-id="6d17c-123">種類: **float**</span><span class="sxs-lookup"><span data-stu-id="6d17c-123">Type: **float**</span></span>

### <span data-ttu-id="6d17c-124">残りの原点</span><span class="sxs-lookup"><span data-stu-id="6d17c-124">originLeft</span></span>

<span data-ttu-id="6d17c-125">フォーカスを与える要素の左辺の位置。</span><span class="sxs-lookup"><span data-stu-id="6d17c-125">The origin left location of the element to be given focus.</span></span>

<span data-ttu-id="6d17c-126">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="6d17c-126">This property is read-only.</span></span>

```js
var originLeft = FocusNavigationEvent.originLeft;
```

#### <span data-ttu-id="6d17c-127">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="6d17c-127">Property value</span></span>
<span data-ttu-id="6d17c-128">種類: **float**</span><span class="sxs-lookup"><span data-stu-id="6d17c-128">Type: **float**</span></span>

### <span data-ttu-id="6d17c-129">原点の先頭へ</span><span class="sxs-lookup"><span data-stu-id="6d17c-129">originTop</span></span>

<span data-ttu-id="6d17c-130">フォーカスを与える要素の起点の上位の位置。</span><span class="sxs-lookup"><span data-stu-id="6d17c-130">The origin top location of the element to be given focus.</span></span>

<span data-ttu-id="6d17c-131">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="6d17c-131">This property is read-only.</span></span>

```js
var originTop = FocusNavigationEvent.originTop;
```

#### <span data-ttu-id="6d17c-132">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="6d17c-132">Property value</span></span>
<span data-ttu-id="6d17c-133">種類: **float**</span><span class="sxs-lookup"><span data-stu-id="6d17c-133">Type: **float**</span></span>

### <span data-ttu-id="6d17c-134">原点の幅</span><span class="sxs-lookup"><span data-stu-id="6d17c-134">originWidth</span></span>

<span data-ttu-id="6d17c-135">フォーカスを与える要素の元の幅。</span><span class="sxs-lookup"><span data-stu-id="6d17c-135">The origin width location of the element to be given focus.</span></span>

<span data-ttu-id="6d17c-136">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="6d17c-136">This property is read-only.</span></span>

```js
var originWidth = FocusNavigationEvent.originWidth;
```

#### <span data-ttu-id="6d17c-137">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="6d17c-137">Property value</span></span>
<span data-ttu-id="6d17c-138">種類: **float**</span><span class="sxs-lookup"><span data-stu-id="6d17c-138">Type: **float**</span></span>

