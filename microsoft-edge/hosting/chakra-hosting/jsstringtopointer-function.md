---
description: 文字列値の文字列ポインターを取得します。
title: JsStringToPointer 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsStringToPointer
helpviewer_keywords:
- JsStringToPointer function
ms.assetid: c7aa7a09-489d-4435-8f8a-aeb62f8875ae
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1f5997894c4ea479378a323b230492dde28ab177
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570271"
---
# <span data-ttu-id="f0a73-103">JsStringToPointer 関数</span><span class="sxs-lookup"><span data-stu-id="f0a73-103">JsStringToPointer Function</span></span>
<span data-ttu-id="f0a73-104">文字列値の文字列ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="f0a73-104">Retrieves the string pointer of a string value.</span></span>  
  
## <span data-ttu-id="f0a73-105">構文</span><span class="sxs-lookup"><span data-stu-id="f0a73-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsStringToPointer(  
   _In_ JsValueRef value,  
   _Outptr_result_buffer_(*stringLength) const wchar_t **stringValue,  
   _Out_ size_t *stringLength  
);  
```  
  
#### <span data-ttu-id="f0a73-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f0a73-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="f0a73-107">文字列ポインターに変換する文字列値。</span><span class="sxs-lookup"><span data-stu-id="f0a73-107">The string value to convert to a string pointer.</span></span>  
  
 `stringValue`  
 <span data-ttu-id="f0a73-108">文字列ポインター。</span><span class="sxs-lookup"><span data-stu-id="f0a73-108">The string pointer.</span></span>  
  
 `stringLength`  
 <span data-ttu-id="f0a73-109">文字列の長さ。</span><span class="sxs-lookup"><span data-stu-id="f0a73-109">The length of the string.</span></span>  
  
## <span data-ttu-id="f0a73-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="f0a73-110">Return Value</span></span>  
 <span data-ttu-id="f0a73-111">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="f0a73-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="f0a73-112">注釈</span><span class="sxs-lookup"><span data-stu-id="f0a73-112">Remarks</span></span>  
 <span data-ttu-id="f0a73-113">この関数は、文字列値の文字列ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="f0a73-113">This function retrieves the string pointer of a string value.</span></span> <span data-ttu-id="f0a73-114">`JsErrorInvalidArgument`値の型が文字列でない場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="f0a73-114">It will fail with `JsErrorInvalidArgument` if the type of the value is not string.</span></span> <span data-ttu-id="f0a73-115">返される文字列の有効期間は、元の値の有効期間と同じになりますが、文字列ポインターは値への参照と見なされません (そのため、その値が収集されることはありません)。</span><span class="sxs-lookup"><span data-stu-id="f0a73-115">The lifetime of the string returned will be the same as the lifetime of the value it came from, however the string pointer is not considered a reference to the value (and so will not keep it from being collected).</span></span>  
  
 <span data-ttu-id="f0a73-116">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="f0a73-116">Requires an active script context.</span></span>  
  
## <span data-ttu-id="f0a73-117">要件</span><span class="sxs-lookup"><span data-stu-id="f0a73-117">Requirements</span></span>  
 <span data-ttu-id="f0a73-118">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="f0a73-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="f0a73-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0a73-119">See Also</span></span>  
 [<span data-ttu-id="f0a73-120">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="f0a73-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)