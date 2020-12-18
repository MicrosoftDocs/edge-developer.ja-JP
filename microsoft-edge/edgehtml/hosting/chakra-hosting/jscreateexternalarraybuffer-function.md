---
description: 外部メモリにアクセスする Javascript `ArrayBuffer` オブジェクトを作成します。
title: JsCreateExternalArrayBuffer 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: article
ms.assetid: 4a02aaec-0f67-4bf9-b37c-71cdb1410ca4
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 78c0d3c8b298876358f247c86a488b6f10e52c6d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234917"
---
# <span data-ttu-id="ebcfd-103">JsCreateExternalArrayBuffer 関数</span><span class="sxs-lookup"><span data-stu-id="ebcfd-103">JsCreateExternalArrayBuffer Function</span></span>

<span data-ttu-id="ebcfd-104">外部メモリにアクセスする Javascript `ArrayBuffer` オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-104">Creates a Javascript `ArrayBuffer` object to access external memory.</span></span>
  
## <span data-ttu-id="ebcfd-105">構文</span><span class="sxs-lookup"><span data-stu-id="ebcfd-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateExternalArrayBuffer(  
  _Pre_maybenull_ _Pre_writable_byte_size_(byteLength) void *data,  
  _In_ unsigned int byteLength,  
  _In_opt_ JsFinalizeCallback finalizeCallback,  
  _In_opt_ void *callbackState,  
  _Out_ JsValueRef *result  
);  
  
```  
  
#### <span data-ttu-id="ebcfd-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ebcfd-106">Parameters</span></span>  
 `data`  
 <span data-ttu-id="ebcfd-107">外部メモリへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-107">A pointer to the external memory.</span></span>  
  
 `byteLength`  
 <span data-ttu-id="ebcfd-108">外部メモリ内のバイト数。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-108">The number of bytes in the external memory.</span></span>  
  
 `finalizeCallback`  
 <span data-ttu-id="ebcfd-109">オブジェクトが最終処理される場合のコールバック。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-109">A callback for when the object is finalized.</span></span> <span data-ttu-id="ebcfd-110">null の場合があります。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-110">May be null.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="ebcfd-111">finalizeCallback に戻されるユーザー指定の状態。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-111">User provided state that will be passed back to finalizeCallback.</span></span>  
  
 `result`  
 <span data-ttu-id="ebcfd-112">新しい `ArrayBuffer` オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-112">The new `ArrayBuffer` object.</span></span>  
  
## <span data-ttu-id="ebcfd-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="ebcfd-113">Return Value</span></span>  
 <span data-ttu-id="ebcfd-114">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-114">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ebcfd-115">注釈</span><span class="sxs-lookup"><span data-stu-id="ebcfd-115">Remarks</span></span>  
 <span data-ttu-id="ebcfd-116">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-116">Requires an active script context.</span></span>  
  
## <span data-ttu-id="ebcfd-117">要件</span><span class="sxs-lookup"><span data-stu-id="ebcfd-117">Requirements</span></span>  
 <span data-ttu-id="ebcfd-118">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="ebcfd-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ebcfd-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="ebcfd-119">See Also</span></span>  
 [<span data-ttu-id="ebcfd-120">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="ebcfd-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
