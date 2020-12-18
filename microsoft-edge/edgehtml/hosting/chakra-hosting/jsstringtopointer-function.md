---
description: 文字列値の文字列ポインターを取得します。
title: JsStringToPointer 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsStringToPointer
helpviewer_keywords:
- JsStringToPointer function
ms.assetid: c7aa7a09-489d-4435-8f8a-aeb62f8875ae
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 77b8e16be41d8b5541129b50fa200b947f566342
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234682"
---
# <span data-ttu-id="c2d1a-103">JsStringToPointer 関数</span><span class="sxs-lookup"><span data-stu-id="c2d1a-103">JsStringToPointer Function</span></span>

<span data-ttu-id="c2d1a-104">文字列値の文字列ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="c2d1a-104">Retrieves the string pointer of a string value.</span></span>  
  
## <span data-ttu-id="c2d1a-105">構文</span><span class="sxs-lookup"><span data-stu-id="c2d1a-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsStringToPointer(  
   _In_ JsValueRef value,  
   _Outptr_result_buffer_(*stringLength) const wchar_t **stringValue,  
   _Out_ size_t *stringLength  
);  
```  
  
#### <span data-ttu-id="c2d1a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c2d1a-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="c2d1a-107">文字列ポインターに変換する文字列値。</span><span class="sxs-lookup"><span data-stu-id="c2d1a-107">The string value to convert to a string pointer.</span></span>  
  
 `stringValue`  
 <span data-ttu-id="c2d1a-108">文字列ポインター。</span><span class="sxs-lookup"><span data-stu-id="c2d1a-108">The string pointer.</span></span>  
  
 `stringLength`  
 <span data-ttu-id="c2d1a-109">文字列の長さ。</span><span class="sxs-lookup"><span data-stu-id="c2d1a-109">The length of the string.</span></span>  
  
## <span data-ttu-id="c2d1a-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="c2d1a-110">Return Value</span></span>  
 <span data-ttu-id="c2d1a-111">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="c2d1a-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="c2d1a-112">注釈</span><span class="sxs-lookup"><span data-stu-id="c2d1a-112">Remarks</span></span>  
 <span data-ttu-id="c2d1a-113">この関数は、文字列値の文字列ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="c2d1a-113">This function retrieves the string pointer of a string value.</span></span> <span data-ttu-id="c2d1a-114">値の型が `JsErrorInvalidArgument` 文字列ではない場合は失敗します。</span><span class="sxs-lookup"><span data-stu-id="c2d1a-114">It will fail with `JsErrorInvalidArgument` if the type of the value is not string.</span></span> <span data-ttu-id="c2d1a-115">返される文字列の有効期間は、取得元の値の有効期間と同じですが、文字列ポインターは値への参照とは見なされません (したがって、収集されません)。</span><span class="sxs-lookup"><span data-stu-id="c2d1a-115">The lifetime of the string returned will be the same as the lifetime of the value it came from, however the string pointer is not considered a reference to the value (and so will not keep it from being collected).</span></span>  
  
 <span data-ttu-id="c2d1a-116">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="c2d1a-116">Requires an active script context.</span></span>  
  
## <span data-ttu-id="c2d1a-117">要件</span><span class="sxs-lookup"><span data-stu-id="c2d1a-117">Requirements</span></span>  
 <span data-ttu-id="c2d1a-118">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="c2d1a-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="c2d1a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2d1a-119">See Also</span></span>  
 [<span data-ttu-id="c2d1a-120">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="c2d1a-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
