---
description: スクリプトを解析し、スクリプトを表す関数を返します。
title: Jsparc Sescript 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsParseScript
helpviewer_keywords:
- JsParseScript function
ms.assetid: e9d0e363-7cbe-43eb-9dc0-1f47e586c9ab
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: dd224ef0e800f05e6e07580f545bc4af218b3498
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570418"
---
# <span data-ttu-id="0b76c-103">Jsparc Sescript 関数</span><span class="sxs-lookup"><span data-stu-id="0b76c-103">JsParseScript Function</span></span>
<span data-ttu-id="0b76c-104">スクリプトを解析し、スクリプトを表す関数を返します。</span><span class="sxs-lookup"><span data-stu-id="0b76c-104">Parses a script and returns a function representing the script.</span></span>  
  
## <span data-ttu-id="0b76c-105">構文</span><span class="sxs-lookup"><span data-stu-id="0b76c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsParseScript(  
   _In_z_ const wchar_t *script,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="0b76c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0b76c-106">Parameters</span></span>  
 `script`  
 <span data-ttu-id="0b76c-107">解析するスクリプト。</span><span class="sxs-lookup"><span data-stu-id="0b76c-107">The script to parse.</span></span>  
  
 `sourceContext`  
 <span data-ttu-id="0b76c-108">デバッグ可能なスクリプトコンテキストによって使用できるスクリプトを識別する cookie。</span><span class="sxs-lookup"><span data-stu-id="0b76c-108">A cookie identifying the script that can be used by debuggable script contexts.</span></span>  
  
 `sourceUrl`  
 <span data-ttu-id="0b76c-109">スクリプトの取得元の場所。</span><span class="sxs-lookup"><span data-stu-id="0b76c-109">The location the script came from.</span></span>  
  
 `result`  
 <span data-ttu-id="0b76c-110">スクリプトコードを表す関数。</span><span class="sxs-lookup"><span data-stu-id="0b76c-110">A function representing the script code.</span></span>  
  
## <span data-ttu-id="0b76c-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="0b76c-111">Return Value</span></span>  
 <span data-ttu-id="0b76c-112">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="0b76c-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="0b76c-113">注釈</span><span class="sxs-lookup"><span data-stu-id="0b76c-113">Remarks</span></span>  
 <span data-ttu-id="0b76c-114">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="0b76c-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="0b76c-115">要件</span><span class="sxs-lookup"><span data-stu-id="0b76c-115">Requirements</span></span>  
 <span data-ttu-id="0b76c-116">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="0b76c-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="0b76c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b76c-117">See Also</span></span>  
 [<span data-ttu-id="0b76c-118">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="0b76c-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)