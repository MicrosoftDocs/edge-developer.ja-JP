---
description: '`ArrayBuffer`外部メモリにアクセスする Javascript オブジェクトを作成します。'
title: JsCreateExternalArrayBuffer 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a02aaec-0f67-4bf9-b37c-71cdb1410ca4
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 376eedda18393436d9dce340753586bf32599b21
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569367"
---
# <span data-ttu-id="cbf10-103">JsCreateExternalArrayBuffer 関数</span><span class="sxs-lookup"><span data-stu-id="cbf10-103">JsCreateExternalArrayBuffer Function</span></span>
<span data-ttu-id="cbf10-104">`ArrayBuffer`外部メモリにアクセスする Javascript オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="cbf10-104">Creates a Javascript `ArrayBuffer` object to access external memory.</span></span>
  
## <span data-ttu-id="cbf10-105">構文</span><span class="sxs-lookup"><span data-stu-id="cbf10-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateExternalArrayBuffer(  
  _Pre_maybenull_ _Pre_writable_byte_size_(byteLength) void *data,  
  _In_ unsigned int byteLength,  
  _In_opt_ JsFinalizeCallback finalizeCallback,  
  _In_opt_ void *callbackState,  
  _Out_ JsValueRef *result  
);  
  
```  
  
#### <span data-ttu-id="cbf10-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cbf10-106">Parameters</span></span>  
 `data`  
 <span data-ttu-id="cbf10-107">外部メモリへのポインター。</span><span class="sxs-lookup"><span data-stu-id="cbf10-107">A pointer to the external memory.</span></span>  
  
 `byteLength`  
 <span data-ttu-id="cbf10-108">外部メモリのバイト数。</span><span class="sxs-lookup"><span data-stu-id="cbf10-108">The number of bytes in the external memory.</span></span>  
  
 `finalizeCallback`  
 <span data-ttu-id="cbf10-109">オブジェクトが完了するときのためのコールバック。</span><span class="sxs-lookup"><span data-stu-id="cbf10-109">A callback for when the object is finalized.</span></span> <span data-ttu-id="cbf10-110">は null でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="cbf10-110">May be null.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="cbf10-111">FinalizeCallback に戻される、ユーザーによって指定された状態。</span><span class="sxs-lookup"><span data-stu-id="cbf10-111">User provided state that will be passed back to finalizeCallback.</span></span>  
  
 `result`  
 <span data-ttu-id="cbf10-112">新しい `ArrayBuffer` オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="cbf10-112">The new `ArrayBuffer` object.</span></span>  
  
## <span data-ttu-id="cbf10-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="cbf10-113">Return Value</span></span>  
 <span data-ttu-id="cbf10-114">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="cbf10-114">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="cbf10-115">注釈</span><span class="sxs-lookup"><span data-stu-id="cbf10-115">Remarks</span></span>  
 <span data-ttu-id="cbf10-116">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="cbf10-116">Requires an active script context.</span></span>  
  
## <span data-ttu-id="cbf10-117">要件</span><span class="sxs-lookup"><span data-stu-id="cbf10-117">Requirements</span></span>  
 <span data-ttu-id="cbf10-118">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="cbf10-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="cbf10-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbf10-119">See Also</span></span>  
 [<span data-ttu-id="cbf10-120">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="cbf10-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)