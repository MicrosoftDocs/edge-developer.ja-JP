---
description: ガベージ コレクション オブジェクトへの参照を追加します。
title: JsAddRef 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsAddRef
helpviewer_keywords:
- JsAddRef function
ms.assetid: a7f3ed49-6a86-489a-abdf-c99428e79cae
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: fd397dbfeacafdf12728ef0ca2a98d97405f6592
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234560"
---
# <span data-ttu-id="90b3e-103">JsAddRef 関数</span><span class="sxs-lookup"><span data-stu-id="90b3e-103">JsAddRef Function</span></span>

<span data-ttu-id="90b3e-104">ガベージ コレクション オブジェクトへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="90b3e-104">Adds a reference to a garbage collected object.</span></span>  
  
## <span data-ttu-id="90b3e-105">構文</span><span class="sxs-lookup"><span data-stu-id="90b3e-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsAddRef(  
   _In_ JsRef ref,  
   _Out_opt_ unsigned int *count  
);  
```  
  
#### <span data-ttu-id="90b3e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="90b3e-106">Parameters</span></span>  
 `ref`  
 <span data-ttu-id="90b3e-107">参照を追加するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="90b3e-107">The object to add a reference to.</span></span>  
  
 `count`  
 <span data-ttu-id="90b3e-108">オブジェクトの新しい参照カウント (null を渡す場合があります)。</span><span class="sxs-lookup"><span data-stu-id="90b3e-108">The object's new reference count (can pass in null).</span></span>  
  
## <span data-ttu-id="90b3e-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="90b3e-109">Return Value</span></span>  
 <span data-ttu-id="90b3e-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="90b3e-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="90b3e-111">注釈</span><span class="sxs-lookup"><span data-stu-id="90b3e-111">Remarks</span></span>  
 <span data-ttu-id="90b3e-112">これは、スタック上のどこかに格納されないハンドルでのみ呼び出 `JsRef` す必要があります。</span><span class="sxs-lookup"><span data-stu-id="90b3e-112">This only needs to be called on `JsRef` handles that are not going to be stored somewhere on the stack.</span></span> <span data-ttu-id="90b3e-113">呼 `JsAddRef` び出しは、参照元のオブジェクトが呼び出されるまで解放 `JsRef` `JsRelease` されません。</span><span class="sxs-lookup"><span data-stu-id="90b3e-113">Calling `JsAddRef` ensures that the object the `JsRef` refers to will not be freed until `JsRelease` is called.</span></span>  
  
## <span data-ttu-id="90b3e-114">要件</span><span class="sxs-lookup"><span data-stu-id="90b3e-114">Requirements</span></span>  
 <span data-ttu-id="90b3e-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="90b3e-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="90b3e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="90b3e-116">See Also</span></span>  
 [<span data-ttu-id="90b3e-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="90b3e-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
