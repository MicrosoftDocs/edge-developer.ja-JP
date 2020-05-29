---
description: プロパティ記述子から、新しいオブジェクトの独自のプロパティを定義します。
title: JsDefineProperty 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsDefineProperty
helpviewer_keywords:
- JsDefineProperty function
ms.assetid: b2cf48d6-eb40-457c-aa8b-b16a50dc5d6a
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: b3c9641b4d00540670b44d1718a6aa2aca3b02de
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569343"
---
# <span data-ttu-id="129be-103">JsDefineProperty 関数</span><span class="sxs-lookup"><span data-stu-id="129be-103">JsDefineProperty Function</span></span>
<span data-ttu-id="129be-104">プロパティ記述子から、新しいオブジェクトの独自のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="129be-104">Defines a new object's own property from a property descriptor.</span></span>  
  
## <span data-ttu-id="129be-105">構文</span><span class="sxs-lookup"><span data-stu-id="129be-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDefineProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _In_ JsValueRef propertyDescriptor,  
   _Out_ bool *result  
);  
```  
  
#### <span data-ttu-id="129be-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="129be-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="129be-107">プロパティが設定されているオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="129be-107">The object that has the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="129be-108">プロパティの ID です。</span><span class="sxs-lookup"><span data-stu-id="129be-108">The ID of the property.</span></span>  
  
 `propertyDescriptor`  
 <span data-ttu-id="129be-109">プロパティ記述子。</span><span class="sxs-lookup"><span data-stu-id="129be-109">The property descriptor.</span></span>  
  
 `result`  
 <span data-ttu-id="129be-110">プロパティが定義されているかどうか。</span><span class="sxs-lookup"><span data-stu-id="129be-110">Whether the property was defined.</span></span>  
  
## <span data-ttu-id="129be-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="129be-111">Return Value</span></span>  
 <span data-ttu-id="129be-112">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="129be-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="129be-113">注釈</span><span class="sxs-lookup"><span data-stu-id="129be-113">Remarks</span></span>  
 <span data-ttu-id="129be-114">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="129be-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="129be-115">要件</span><span class="sxs-lookup"><span data-stu-id="129be-115">Requirements</span></span>  
 <span data-ttu-id="129be-116">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="129be-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="129be-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="129be-117">See Also</span></span>  
 [<span data-ttu-id="129be-118">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="129be-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)