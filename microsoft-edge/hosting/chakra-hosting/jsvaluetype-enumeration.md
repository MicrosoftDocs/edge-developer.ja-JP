---
description: JsValueRef の JavaScript の型。
title: JsValueType 列挙 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsValueType
helpviewer_keywords:
- JsValueType enumeration
ms.assetid: 6645e723-e554-41fc-b622-ab54ee044b3d
caps.latest.revision: 16
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c42231525b55b49f0931a2ace33b373e0d4ae441
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569261"
---
# <span data-ttu-id="50079-103">JsValueType 列挙</span><span class="sxs-lookup"><span data-stu-id="50079-103">JsValueType Enumeration</span></span>
<span data-ttu-id="50079-104">JsValueRef の JavaScript の型。</span><span class="sxs-lookup"><span data-stu-id="50079-104">The JavaScript type of a JsValueRef.</span></span>  
  
## <span data-ttu-id="50079-105">構文</span><span class="sxs-lookup"><span data-stu-id="50079-105">Syntax</span></span>  
  
```cpp  
enum JsValueType {  
    JsUndefined      = 0,  
    JsNull           = 1,  
    JsNumber         = 2,  
    JsString         = 3,  
    JsBoolean        = 4,  
    JsObject         = 5,  
    JsFunction       = 6,  
    JsError          = 7,  
    JsArray          = 8,  
    JsSymbol         = 9,  
    JsArrayBuffer    = 10,  
    JsTypedArray     = 11,  
    JsDataView       = 12,  
};  
```  
  
## <span data-ttu-id="50079-106">Members</span><span class="sxs-lookup"><span data-stu-id="50079-106">Members</span></span>  
  
### <span data-ttu-id="50079-107">値</span><span class="sxs-lookup"><span data-stu-id="50079-107">Values</span></span>  
  
|<span data-ttu-id="50079-108">名前</span><span class="sxs-lookup"><span data-stu-id="50079-108">Name</span></span>|<span data-ttu-id="50079-109">説明</span><span class="sxs-lookup"><span data-stu-id="50079-109">Description</span></span>|  
|----------|-----------------|  
|`JsUndefined`|<span data-ttu-id="50079-110">値が値です `undefined` 。</span><span class="sxs-lookup"><span data-stu-id="50079-110">The value is the `undefined` value.</span></span>|  
|`JsNull`|<span data-ttu-id="50079-111">値が値です `null` 。</span><span class="sxs-lookup"><span data-stu-id="50079-111">The value is the `null` value.</span></span>|  
|`JsNumber`|<span data-ttu-id="50079-112">この値は JavaScript 番号の値です。</span><span class="sxs-lookup"><span data-stu-id="50079-112">The value is a JavaScript number value.</span></span>|  
|`JsString`|<span data-ttu-id="50079-113">この値は JavaScript の文字列値です。</span><span class="sxs-lookup"><span data-stu-id="50079-113">The value is a JavaScript string value.</span></span>|  
|`JsBoolean`|<span data-ttu-id="50079-114">この値は JavaScript のブール値です。</span><span class="sxs-lookup"><span data-stu-id="50079-114">The value is a JavaScript Boolean value.</span></span>|  
|`JsObject`|<span data-ttu-id="50079-115">この値は JavaScript オブジェクトの値です。</span><span class="sxs-lookup"><span data-stu-id="50079-115">The value is a JavaScript object value.</span></span>|  
|`JsFunction`|<span data-ttu-id="50079-116">この値は JavaScript 関数オブジェクトの値です。</span><span class="sxs-lookup"><span data-stu-id="50079-116">The value is a JavaScript function object value.</span></span>|  
|`JsError`|<span data-ttu-id="50079-117">この値は JavaScript のエラーオブジェクトの値です。</span><span class="sxs-lookup"><span data-stu-id="50079-117">The value is a JavaScript error object value.</span></span>|  
|`JsArray`|<span data-ttu-id="50079-118">この値は、JavaScript 配列オブジェクトの値です。</span><span class="sxs-lookup"><span data-stu-id="50079-118">The value is a JavaScript array object value.</span></span>|  
|`JsSymbol`|<span data-ttu-id="50079-119">この値は JavaScript の記号値です。</span><span class="sxs-lookup"><span data-stu-id="50079-119">The value is a JavaScript symbol value.</span></span><br /><br /> <span data-ttu-id="50079-120">この列挙値は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="50079-120">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsArrayBuffer`|<span data-ttu-id="50079-121">この値は JavaScript `ArrayBuffer` オブジェクトの値です。</span><span class="sxs-lookup"><span data-stu-id="50079-121">The value is a JavaScript `ArrayBuffer` object value.</span></span><br /><br /> <span data-ttu-id="50079-122">この列挙値は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="50079-122">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsTypedArray`|<span data-ttu-id="50079-123">この値は、JavaScript 型指定された配列オブジェクトの値です。</span><span class="sxs-lookup"><span data-stu-id="50079-123">The value is a JavaScript typed array object value.</span></span><br /><br /> <span data-ttu-id="50079-124">この列挙値は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="50079-124">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsDataView`|<span data-ttu-id="50079-125">この値は JavaScript `DataView` オブジェクトの値です。</span><span class="sxs-lookup"><span data-stu-id="50079-125">The value is a JavaScript `DataView` object value.</span></span><br /><br /> <span data-ttu-id="50079-126">この列挙値は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="50079-126">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
  
## <span data-ttu-id="50079-127">要件</span><span class="sxs-lookup"><span data-stu-id="50079-127">Requirements</span></span>  
 <span data-ttu-id="50079-128">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="50079-128">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="50079-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="50079-129">See Also</span></span>  
 [<span data-ttu-id="50079-130">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="50079-130">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)