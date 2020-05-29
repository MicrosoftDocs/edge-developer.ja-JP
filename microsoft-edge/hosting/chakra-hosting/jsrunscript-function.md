---
description: スクリプトを実行します。
title: JsRunScript 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsRunScript
helpviewer_keywords:
- JsRunScript function
ms.assetid: 8d6b8c9a-af3a-4e21-a330-5a6b535423a3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 49a06e4e6ad0c04e124b76f31d38b2e362e03f99
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570404"
---
# <span data-ttu-id="5de01-103">JsRunScript 関数</span><span class="sxs-lookup"><span data-stu-id="5de01-103">JsRunScript Function</span></span>
<span data-ttu-id="5de01-104">スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="5de01-104">Executes a script.</span></span>  
  
## <span data-ttu-id="5de01-105">構文</span><span class="sxs-lookup"><span data-stu-id="5de01-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsRunScript(  
   _In_z_ const wchar_t *script,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="5de01-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5de01-106">Parameters</span></span>  
 `script`  
 <span data-ttu-id="5de01-107">実行するスクリプト。</span><span class="sxs-lookup"><span data-stu-id="5de01-107">The script to run.</span></span>  
  
 `sourceContext`  
 <span data-ttu-id="5de01-108">デバッグ可能なスクリプトコンテキストによって使用できるスクリプトを識別する cookie。</span><span class="sxs-lookup"><span data-stu-id="5de01-108">A cookie identifying the script that can be used by debuggable script contexts.</span></span>  
  
 `sourceUrl`  
 <span data-ttu-id="5de01-109">スクリプトの取得元の場所。</span><span class="sxs-lookup"><span data-stu-id="5de01-109">The location the script came from.</span></span>  
  
 `result`  
 <span data-ttu-id="5de01-110">スクリプトの結果 (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="5de01-110">The result of the script, if any.</span></span> <span data-ttu-id="5de01-111">このパラメーターは null にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5de01-111">This parameter can be null.</span></span>  
  
## <span data-ttu-id="5de01-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="5de01-112">Return Value</span></span>  
 <span data-ttu-id="5de01-113">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="5de01-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="5de01-114">注釈</span><span class="sxs-lookup"><span data-stu-id="5de01-114">Remarks</span></span>  
 <span data-ttu-id="5de01-115">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="5de01-115">Requires an active script context.</span></span>  
  
## <span data-ttu-id="5de01-116">要件</span><span class="sxs-lookup"><span data-stu-id="5de01-116">Requirements</span></span>  
 <span data-ttu-id="5de01-117">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="5de01-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="5de01-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5de01-118">See Also</span></span>  
 [<span data-ttu-id="5de01-119">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="5de01-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)