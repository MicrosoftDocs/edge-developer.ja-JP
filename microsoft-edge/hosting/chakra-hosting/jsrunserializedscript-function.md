---
description: シリアル化されたスクリプトを実行します。
title: JsRunSerializedScript 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsRunSerializedScript
helpviewer_keywords:
- JsRunSerializedScript function
ms.assetid: 3fd3f6f1-eb3e-4751-92a5-c93b1035f3b2
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: bc1e2fb7fdc5df52fde3b7cc59cf9173d658782a
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570403"
---
# <span data-ttu-id="0ab88-103">JsRunSerializedScript 関数</span><span class="sxs-lookup"><span data-stu-id="0ab88-103">JsRunSerializedScript Function</span></span>
<span data-ttu-id="0ab88-104">シリアル化されたスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="0ab88-104">Runs a serialized script.</span></span>  
  
## <span data-ttu-id="0ab88-105">構文</span><span class="sxs-lookup"><span data-stu-id="0ab88-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsRunSerializedScript(  
   _In_z_ const wchar_t *script,  
   _In_ BYTE *buffer,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="0ab88-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0ab88-106">Parameters</span></span>  
 `script`  
 <span data-ttu-id="0ab88-107">シリアル化されたスクリプトのソースコード。</span><span class="sxs-lookup"><span data-stu-id="0ab88-107">The source code of the serialized script.</span></span>  
  
 `buffer`  
 <span data-ttu-id="0ab88-108">シリアル化されたスクリプト。</span><span class="sxs-lookup"><span data-stu-id="0ab88-108">The serialized script.</span></span>  
  
 `sourceContext`  
 <span data-ttu-id="0ab88-109">デバッグ可能なスクリプトコンテキストによって使用できるスクリプトを識別する cookie。</span><span class="sxs-lookup"><span data-stu-id="0ab88-109">A cookie identifying the script that can be used by debuggable script contexts.</span></span>  
  
 `sourceUrl`  
 <span data-ttu-id="0ab88-110">スクリプトの取得元の場所。</span><span class="sxs-lookup"><span data-stu-id="0ab88-110">The location the script came from.</span></span>  
  
 `result`  
 <span data-ttu-id="0ab88-111">スクリプトを実行した結果 (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="0ab88-111">The result of running the script, if any.</span></span> <span data-ttu-id="0ab88-112">このパラメーターは null にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0ab88-112">This parameter can be null.</span></span>  
  
## <span data-ttu-id="0ab88-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="0ab88-113">Return Value</span></span>  
 <span data-ttu-id="0ab88-114">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="0ab88-114">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="0ab88-115">注釈</span><span class="sxs-lookup"><span data-stu-id="0ab88-115">Remarks</span></span>  
 <span data-ttu-id="0ab88-116">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="0ab88-116">Requires an active script context.</span></span>  
  
 <span data-ttu-id="0ab88-117">バッファーはスクリプトエンジンによってメモリ内に保持されないため、スクリプトの実行に使用されている可能性がある限り、コードは有効な状態に維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ab88-117">The buffer is not persisted in memory by the scripting engine, so your code must keep it alive for as long as it might be used to execute scripts.</span></span>  
  
## <span data-ttu-id="0ab88-118">要件</span><span class="sxs-lookup"><span data-stu-id="0ab88-118">Requirements</span></span>  
 <span data-ttu-id="0ab88-119">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="0ab88-119">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="0ab88-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ab88-120">See Also</span></span>  
 [<span data-ttu-id="0ab88-121">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="0ab88-121">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)