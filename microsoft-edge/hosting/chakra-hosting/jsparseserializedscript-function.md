---
description: シリアル化されたスクリプトを解析し、スクリプトを表す関数を返します。
title: JsParseSerializedScript 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsParseSerializedScript
helpviewer_keywords:
- JsParseSerializedScript function
ms.assetid: 40d0c7c4-fd5b-46ed-9e65-38c2db2fc859
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: a778a007e69f15063d23cc55f999144ab55a306c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570417"
---
# <span data-ttu-id="05a88-103">JsParseSerializedScript 関数</span><span class="sxs-lookup"><span data-stu-id="05a88-103">JsParseSerializedScript Function</span></span>
<span data-ttu-id="05a88-104">シリアル化されたスクリプトを解析し、スクリプトを表す関数を返します。</span><span class="sxs-lookup"><span data-stu-id="05a88-104">Parses a serialized script and returns a function representing the script.</span></span>  
  
## <span data-ttu-id="05a88-105">構文</span><span class="sxs-lookup"><span data-stu-id="05a88-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsParseSerializedScript(  
   _In_z_ const wchar_t *script,  
   _In_ BYTE *buffer,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="05a88-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="05a88-106">Parameters</span></span>  
 `script`  
 <span data-ttu-id="05a88-107">解析するスクリプト。</span><span class="sxs-lookup"><span data-stu-id="05a88-107">The script to parse.</span></span>  
  
 `buffer`  
 <span data-ttu-id="05a88-108">シリアル化されたスクリプト。</span><span class="sxs-lookup"><span data-stu-id="05a88-108">The serialized script.</span></span>  
  
 `sourceContext`  
 <span data-ttu-id="05a88-109">デバッグ可能なスクリプトコンテキストによって使用できるスクリプトを識別する cookie。</span><span class="sxs-lookup"><span data-stu-id="05a88-109">A cookie identifying the script that can be used by debuggable script contexts.</span></span>  
  
 `sourceUrl`  
 <span data-ttu-id="05a88-110">スクリプトの取得元の場所。</span><span class="sxs-lookup"><span data-stu-id="05a88-110">The location the script came from.</span></span>  
  
 `result`  
 <span data-ttu-id="05a88-111">スクリプトコードを表す関数。</span><span class="sxs-lookup"><span data-stu-id="05a88-111">A function representing the script code.</span></span>  
  
## <span data-ttu-id="05a88-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="05a88-112">Return Value</span></span>  
 <span data-ttu-id="05a88-113">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="05a88-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="05a88-114">注釈</span><span class="sxs-lookup"><span data-stu-id="05a88-114">Remarks</span></span>  
 <span data-ttu-id="05a88-115">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="05a88-115">Requires an active script context.</span></span>  
  
 <span data-ttu-id="05a88-116">バッファーはスクリプトエンジンによってメモリ内に保持されないため、スクリプトの実行に使用されている可能性がある限り、コードは有効な状態に維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05a88-116">The buffer is not persisted in memory by the scripting engine, so your code must keep it alive for as long as it might be used to execute scripts.</span></span>  
  
## <span data-ttu-id="05a88-117">要件</span><span class="sxs-lookup"><span data-stu-id="05a88-117">Requirements</span></span>  
 <span data-ttu-id="05a88-118">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="05a88-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="05a88-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="05a88-119">See Also</span></span>  
 [<span data-ttu-id="05a88-120">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="05a88-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)