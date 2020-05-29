---
description: ガベージコレクションオブジェクトへの参照を解放します。
title: JsRelease 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsRelease
helpviewer_keywords:
- JsRelease function
ms.assetid: 8714fd0b-5b66-48e0-927e-7b93af6cde7b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 134ba16509b6c2f0c232214d7efba4d8c8915d43
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570406"
---
# <span data-ttu-id="f486f-103">JsRelease 関数</span><span class="sxs-lookup"><span data-stu-id="f486f-103">JsRelease Function</span></span>
<span data-ttu-id="f486f-104">ガベージコレクションオブジェクトへの参照を解放します。</span><span class="sxs-lookup"><span data-stu-id="f486f-104">Releases a reference to a garbage collected object.</span></span>  
  
## <span data-ttu-id="f486f-105">構文</span><span class="sxs-lookup"><span data-stu-id="f486f-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsRelease(  
   _In_ JsRef ref,  
   _Out_opt_ unsigned int *count  
);  
```  
  
#### <span data-ttu-id="f486f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f486f-106">Parameters</span></span>  
 `ref`  
 <span data-ttu-id="f486f-107">参照を追加する対象のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f486f-107">The object to add a reference to.</span></span>  
  
 `count`  
 <span data-ttu-id="f486f-108">オブジェクトの新しい参照カウント (null 値を渡すことができます)。</span><span class="sxs-lookup"><span data-stu-id="f486f-108">The object's new reference count (can pass in null).</span></span>  
  
## <span data-ttu-id="f486f-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="f486f-109">Return Value</span></span>  
 <span data-ttu-id="f486f-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="f486f-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="f486f-111">注釈</span><span class="sxs-lookup"><span data-stu-id="f486f-111">Remarks</span></span>  
 <span data-ttu-id="f486f-112">によって作成されたハンドルへの参照を削除 `JsRef` `JsAddRef` します。</span><span class="sxs-lookup"><span data-stu-id="f486f-112">Removes a reference to a `JsRef` handle that was created by `JsAddRef`.</span></span>  
  
## <span data-ttu-id="f486f-113">要件</span><span class="sxs-lookup"><span data-stu-id="f486f-113">Requirements</span></span>  
 <span data-ttu-id="f486f-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="f486f-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="f486f-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f486f-115">See Also</span></span>  
 [<span data-ttu-id="f486f-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="f486f-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)