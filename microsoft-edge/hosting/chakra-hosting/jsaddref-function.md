---
description: ガベージコレクションオブジェクトへの参照を追加します。
title: JsAddRef 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsAddRef
helpviewer_keywords:
- JsAddRef function
ms.assetid: a7f3ed49-6a86-489a-abdf-c99428e79cae
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: bd02dded6dc2877228f22b4d2800e41a78163467
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569404"
---
# <span data-ttu-id="1e80c-103">JsAddRef 関数</span><span class="sxs-lookup"><span data-stu-id="1e80c-103">JsAddRef Function</span></span>
<span data-ttu-id="1e80c-104">ガベージコレクションオブジェクトへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="1e80c-104">Adds a reference to a garbage collected object.</span></span>  
  
## <span data-ttu-id="1e80c-105">構文</span><span class="sxs-lookup"><span data-stu-id="1e80c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsAddRef(  
   _In_ JsRef ref,  
   _Out_opt_ unsigned int *count  
);  
```  
  
#### <span data-ttu-id="1e80c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e80c-106">Parameters</span></span>  
 `ref`  
 <span data-ttu-id="1e80c-107">参照を追加する対象のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1e80c-107">The object to add a reference to.</span></span>  
  
 `count`  
 <span data-ttu-id="1e80c-108">オブジェクトの新しい参照カウント (null 値を渡すことができます)。</span><span class="sxs-lookup"><span data-stu-id="1e80c-108">The object's new reference count (can pass in null).</span></span>  
  
## <span data-ttu-id="1e80c-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="1e80c-109">Return Value</span></span>  
 <span data-ttu-id="1e80c-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="1e80c-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="1e80c-111">注釈</span><span class="sxs-lookup"><span data-stu-id="1e80c-111">Remarks</span></span>  
 <span data-ttu-id="1e80c-112">これは `JsRef` 、スタックのどこかに保存されないハンドルでのみ呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e80c-112">This only needs to be called on `JsRef` handles that are not going to be stored somewhere on the stack.</span></span> <span data-ttu-id="1e80c-113">呼び出し `JsAddRef` によって、 `JsRef` が呼び出されるまで、参照先のオブジェクトは解放されません `JsRelease` 。</span><span class="sxs-lookup"><span data-stu-id="1e80c-113">Calling `JsAddRef` ensures that the object the `JsRef` refers to will not be freed until `JsRelease` is called.</span></span>  
  
## <span data-ttu-id="1e80c-114">要件</span><span class="sxs-lookup"><span data-stu-id="1e80c-114">Requirements</span></span>  
 <span data-ttu-id="1e80c-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="1e80c-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="1e80c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e80c-116">See Also</span></span>  
 [<span data-ttu-id="1e80c-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="1e80c-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)