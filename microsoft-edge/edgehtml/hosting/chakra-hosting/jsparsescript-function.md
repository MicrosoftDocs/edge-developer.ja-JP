---
description: スクリプトを解析し、スクリプトを表す関数を返します。
title: JsParseScript 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsParseScript
helpviewer_keywords:
- JsParseScript function
ms.assetid: e9d0e363-7cbe-43eb-9dc0-1f47e586c9ab
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 656d9a992868a3cb892808775f160092b8eaf069
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234861"
---
# <span data-ttu-id="48704-103">JsParseScript 関数</span><span class="sxs-lookup"><span data-stu-id="48704-103">JsParseScript Function</span></span>

<span data-ttu-id="48704-104">スクリプトを解析し、スクリプトを表す関数を返します。</span><span class="sxs-lookup"><span data-stu-id="48704-104">Parses a script and returns a function representing the script.</span></span>  
  
## <span data-ttu-id="48704-105">構文</span><span class="sxs-lookup"><span data-stu-id="48704-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsParseScript(  
   _In_z_ const wchar_t *script,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="48704-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="48704-106">Parameters</span></span>  
 `script`  
 <span data-ttu-id="48704-107">解析するスクリプト。</span><span class="sxs-lookup"><span data-stu-id="48704-107">The script to parse.</span></span>  
  
 `sourceContext`  
 <span data-ttu-id="48704-108">デバッグ可能なスクリプト コンテキストで使用できるスクリプトを識別する Cookie。</span><span class="sxs-lookup"><span data-stu-id="48704-108">A cookie identifying the script that can be used by debuggable script contexts.</span></span>  
  
 `sourceUrl`  
 <span data-ttu-id="48704-109">スクリプトの作成場所。</span><span class="sxs-lookup"><span data-stu-id="48704-109">The location the script came from.</span></span>  
  
 `result`  
 <span data-ttu-id="48704-110">スクリプト コードを表す関数。</span><span class="sxs-lookup"><span data-stu-id="48704-110">A function representing the script code.</span></span>  
  
## <span data-ttu-id="48704-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="48704-111">Return Value</span></span>  
 <span data-ttu-id="48704-112">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="48704-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="48704-113">注釈</span><span class="sxs-lookup"><span data-stu-id="48704-113">Remarks</span></span>  
 <span data-ttu-id="48704-114">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="48704-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="48704-115">要件</span><span class="sxs-lookup"><span data-stu-id="48704-115">Requirements</span></span>  
 <span data-ttu-id="48704-116">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="48704-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="48704-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="48704-117">See Also</span></span>  
 [<span data-ttu-id="48704-118">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="48704-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
