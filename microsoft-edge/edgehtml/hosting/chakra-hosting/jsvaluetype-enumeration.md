---
description: JsValueRef の JavaScript 型。
title: JsValueType 列挙 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsValueType
helpviewer_keywords:
- JsValueType enumeration
ms.assetid: 6645e723-e554-41fc-b622-ab54ee044b3d
caps.latest.revision: 16
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 840afcde86d4df80490d463921a74c73e42ddfc2
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234676"
---
# <span data-ttu-id="ca163-103">JsValueType 列挙</span><span class="sxs-lookup"><span data-stu-id="ca163-103">JsValueType Enumeration</span></span>

<span data-ttu-id="ca163-104">JsValueRef の JavaScript 型。</span><span class="sxs-lookup"><span data-stu-id="ca163-104">The JavaScript type of a JsValueRef.</span></span>  
  
## <span data-ttu-id="ca163-105">構文</span><span class="sxs-lookup"><span data-stu-id="ca163-105">Syntax</span></span>  
  
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
  
## <span data-ttu-id="ca163-106">Members</span><span class="sxs-lookup"><span data-stu-id="ca163-106">Members</span></span>  
  
### <span data-ttu-id="ca163-107">値</span><span class="sxs-lookup"><span data-stu-id="ca163-107">Values</span></span>  
  
|<span data-ttu-id="ca163-108">名前</span><span class="sxs-lookup"><span data-stu-id="ca163-108">Name</span></span>|<span data-ttu-id="ca163-109">説明</span><span class="sxs-lookup"><span data-stu-id="ca163-109">Description</span></span>|  
|----------|-----------------|  
|`JsUndefined`|<span data-ttu-id="ca163-110">値は値 `undefined` です。</span><span class="sxs-lookup"><span data-stu-id="ca163-110">The value is the `undefined` value.</span></span>|  
|`JsNull`|<span data-ttu-id="ca163-111">値は値 `null` です。</span><span class="sxs-lookup"><span data-stu-id="ca163-111">The value is the `null` value.</span></span>|  
|`JsNumber`|<span data-ttu-id="ca163-112">値は JavaScript 番号の値です。</span><span class="sxs-lookup"><span data-stu-id="ca163-112">The value is a JavaScript number value.</span></span>|  
|`JsString`|<span data-ttu-id="ca163-113">値は JavaScript 文字列値です。</span><span class="sxs-lookup"><span data-stu-id="ca163-113">The value is a JavaScript string value.</span></span>|  
|`JsBoolean`|<span data-ttu-id="ca163-114">値は JavaScript ブール値です。</span><span class="sxs-lookup"><span data-stu-id="ca163-114">The value is a JavaScript Boolean value.</span></span>|  
|`JsObject`|<span data-ttu-id="ca163-115">値は JavaScript オブジェクト値です。</span><span class="sxs-lookup"><span data-stu-id="ca163-115">The value is a JavaScript object value.</span></span>|  
|`JsFunction`|<span data-ttu-id="ca163-116">値は JavaScript 関数オブジェクト値です。</span><span class="sxs-lookup"><span data-stu-id="ca163-116">The value is a JavaScript function object value.</span></span>|  
|`JsError`|<span data-ttu-id="ca163-117">値は JavaScript エラー オブジェクト値です。</span><span class="sxs-lookup"><span data-stu-id="ca163-117">The value is a JavaScript error object value.</span></span>|  
|`JsArray`|<span data-ttu-id="ca163-118">値は JavaScript 配列オブジェクト値です。</span><span class="sxs-lookup"><span data-stu-id="ca163-118">The value is a JavaScript array object value.</span></span>|  
|`JsSymbol`|<span data-ttu-id="ca163-119">値は JavaScript シンボル値です。</span><span class="sxs-lookup"><span data-stu-id="ca163-119">The value is a JavaScript symbol value.</span></span><br /><br /> <span data-ttu-id="ca163-120">この列挙値は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ca163-120">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsArrayBuffer`|<span data-ttu-id="ca163-121">値は JavaScript オブジェクト `ArrayBuffer` の値です。</span><span class="sxs-lookup"><span data-stu-id="ca163-121">The value is a JavaScript `ArrayBuffer` object value.</span></span><br /><br /> <span data-ttu-id="ca163-122">この列挙値は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ca163-122">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsTypedArray`|<span data-ttu-id="ca163-123">値は、JavaScript 型指定された配列オブジェクト値です。</span><span class="sxs-lookup"><span data-stu-id="ca163-123">The value is a JavaScript typed array object value.</span></span><br /><br /> <span data-ttu-id="ca163-124">この列挙値は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ca163-124">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsDataView`|<span data-ttu-id="ca163-125">値は JavaScript オブジェクト `DataView` 値です。</span><span class="sxs-lookup"><span data-stu-id="ca163-125">The value is a JavaScript `DataView` object value.</span></span><br /><br /> <span data-ttu-id="ca163-126">この列挙値は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ca163-126">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
  
## <span data-ttu-id="ca163-127">要件</span><span class="sxs-lookup"><span data-stu-id="ca163-127">Requirements</span></span>  
 <span data-ttu-id="ca163-128">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="ca163-128">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ca163-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca163-129">See Also</span></span>  
 [<span data-ttu-id="ca163-130">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="ca163-130">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
