---
description: ガベージ コレクション オブジェクトへの参照を解放します。
title: JsRelease 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsRelease
helpviewer_keywords:
- JsRelease function
ms.assetid: 8714fd0b-5b66-48e0-927e-7b93af6cde7b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 46552a03dc56a10b1d258d8c33da1c533f38464a
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234508"
---
# <span data-ttu-id="6734e-103">JsRelease 関数</span><span class="sxs-lookup"><span data-stu-id="6734e-103">JsRelease Function</span></span>

<span data-ttu-id="6734e-104">ガベージ コレクション オブジェクトへの参照を解放します。</span><span class="sxs-lookup"><span data-stu-id="6734e-104">Releases a reference to a garbage collected object.</span></span>  
  
## <span data-ttu-id="6734e-105">構文</span><span class="sxs-lookup"><span data-stu-id="6734e-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsRelease(  
   _In_ JsRef ref,  
   _Out_opt_ unsigned int *count  
);  
```  
  
#### <span data-ttu-id="6734e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6734e-106">Parameters</span></span>  
 `ref`  
 <span data-ttu-id="6734e-107">参照を追加するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="6734e-107">The object to add a reference to.</span></span>  
  
 `count`  
 <span data-ttu-id="6734e-108">オブジェクトの新しい参照カウント (null を渡す場合があります)。</span><span class="sxs-lookup"><span data-stu-id="6734e-108">The object's new reference count (can pass in null).</span></span>  
  
## <span data-ttu-id="6734e-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="6734e-109">Return Value</span></span>  
 <span data-ttu-id="6734e-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="6734e-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="6734e-111">注釈</span><span class="sxs-lookup"><span data-stu-id="6734e-111">Remarks</span></span>  
 <span data-ttu-id="6734e-112">によって作成されたハンドル `JsRef` への参照を削除します `JsAddRef` 。</span><span class="sxs-lookup"><span data-stu-id="6734e-112">Removes a reference to a `JsRef` handle that was created by `JsAddRef`.</span></span>  
  
## <span data-ttu-id="6734e-113">要件</span><span class="sxs-lookup"><span data-stu-id="6734e-113">Requirements</span></span>  
 <span data-ttu-id="6734e-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="6734e-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="6734e-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="6734e-115">See Also</span></span>  
 [<span data-ttu-id="6734e-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="6734e-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
