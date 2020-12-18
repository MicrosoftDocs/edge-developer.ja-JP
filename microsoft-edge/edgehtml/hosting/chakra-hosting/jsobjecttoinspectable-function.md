---
description: JavaScript オブジェクトのポインターの折り返しを `IInspectable` 解除します。
title: JsObjectToInspectable 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 1d15b0b8-516f-4fc6-95aa-2ddd65f8ab75
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 0d818f798805e2afad4dc87b308258464d31bf92
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234857"
---
# <span data-ttu-id="8479b-103">JsObjectToInspectable 関数</span><span class="sxs-lookup"><span data-stu-id="8479b-103">JsObjectToInspectable Function</span></span>

<span data-ttu-id="8479b-104">JavaScript オブジェクトのポインターの折り返しを `IInspectable` 解除します。</span><span class="sxs-lookup"><span data-stu-id="8479b-104">Unwraps a JavaScript object to an `IInspectable` pointer.</span></span>  
  
## <span data-ttu-id="8479b-105">構文</span><span class="sxs-lookup"><span data-stu-id="8479b-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsObjectToInspectable(  
   _In_ JsValueRef value,  
   _Out_ IInspectable  **inspectable  
);  
```  
  
#### <span data-ttu-id="8479b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8479b-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="8479b-107">投影する必要がある JavaScript 値 `IInspectable` 。</span><span class="sxs-lookup"><span data-stu-id="8479b-107">A JavaScript value that should be projected to `IInspectable`.</span></span>  
  
 `inspectable`  
 <span data-ttu-id="8479b-108">オブジェクト `IInspectable` の値。</span><span class="sxs-lookup"><span data-stu-id="8479b-108">An `IInspectable` value of the object.</span></span>  
  
## <span data-ttu-id="8479b-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="8479b-109">Return Value</span></span>  
 <span data-ttu-id="8479b-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="8479b-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="8479b-111">注釈</span><span class="sxs-lookup"><span data-stu-id="8479b-111">Remarks</span></span>  
 <span data-ttu-id="8479b-112">ホストは COM スレッド ルールを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8479b-112">Hosts are responsible for enforcing COM threading rules.</span></span>  
  
 <span data-ttu-id="8479b-113">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="8479b-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="8479b-114">この API は EdgeHTML モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8479b-114">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="8479b-115">要件</span><span class="sxs-lookup"><span data-stu-id="8479b-115">Requirements</span></span>  
 <span data-ttu-id="8479b-116">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="8479b-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="8479b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="8479b-117">See Also</span></span>  
 [<span data-ttu-id="8479b-118">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="8479b-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
