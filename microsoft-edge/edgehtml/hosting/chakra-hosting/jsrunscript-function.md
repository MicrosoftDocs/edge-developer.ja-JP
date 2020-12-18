---
description: スクリプトを実行します。
title: JsRunScript 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsRunScript
helpviewer_keywords:
- JsRunScript function
ms.assetid: 8d6b8c9a-af3a-4e21-a330-5a6b535423a3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d61771991e1d22a9d71a928d785390b814a992a8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235024"
---
# <span data-ttu-id="b1d07-103">JsRunScript 関数</span><span class="sxs-lookup"><span data-stu-id="b1d07-103">JsRunScript Function</span></span>

<span data-ttu-id="b1d07-104">スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="b1d07-104">Executes a script.</span></span>  
  
## <span data-ttu-id="b1d07-105">構文</span><span class="sxs-lookup"><span data-stu-id="b1d07-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsRunScript(  
   _In_z_ const wchar_t *script,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="b1d07-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b1d07-106">Parameters</span></span>  
 `script`  
 <span data-ttu-id="b1d07-107">実行するスクリプト。</span><span class="sxs-lookup"><span data-stu-id="b1d07-107">The script to run.</span></span>  
  
 `sourceContext`  
 <span data-ttu-id="b1d07-108">デバッグ可能なスクリプト コンテキストで使用できるスクリプトを識別する Cookie。</span><span class="sxs-lookup"><span data-stu-id="b1d07-108">A cookie identifying the script that can be used by debuggable script contexts.</span></span>  
  
 `sourceUrl`  
 <span data-ttu-id="b1d07-109">スクリプトの作成場所。</span><span class="sxs-lookup"><span data-stu-id="b1d07-109">The location the script came from.</span></span>  
  
 `result`  
 <span data-ttu-id="b1d07-110">スクリプトの結果 (スクリプトがある場合)。</span><span class="sxs-lookup"><span data-stu-id="b1d07-110">The result of the script, if any.</span></span> <span data-ttu-id="b1d07-111">このパラメーターは null に設定できます。</span><span class="sxs-lookup"><span data-stu-id="b1d07-111">This parameter can be null.</span></span>  
  
## <span data-ttu-id="b1d07-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="b1d07-112">Return Value</span></span>  
 <span data-ttu-id="b1d07-113">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="b1d07-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="b1d07-114">注釈</span><span class="sxs-lookup"><span data-stu-id="b1d07-114">Remarks</span></span>  
 <span data-ttu-id="b1d07-115">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="b1d07-115">Requires an active script context.</span></span>  
  
## <span data-ttu-id="b1d07-116">要件</span><span class="sxs-lookup"><span data-stu-id="b1d07-116">Requirements</span></span>  
 <span data-ttu-id="b1d07-117">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="b1d07-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="b1d07-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1d07-118">See Also</span></span>  
 [<span data-ttu-id="b1d07-119">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="b1d07-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
