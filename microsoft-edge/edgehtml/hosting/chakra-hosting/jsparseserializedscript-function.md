---
description: シリアル化されたスクリプトを解析し、スクリプトを表す関数を返します。
title: JsParseSerializedScript 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsParseSerializedScript
helpviewer_keywords:
- JsParseSerializedScript function
ms.assetid: 40d0c7c4-fd5b-46ed-9e65-38c2db2fc859
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 66ecabb9d96c3f339625f93858444f55d25fd4d7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234860"
---
# <span data-ttu-id="010fa-103">JsParseSerializedScript 関数</span><span class="sxs-lookup"><span data-stu-id="010fa-103">JsParseSerializedScript Function</span></span>

<span data-ttu-id="010fa-104">シリアル化されたスクリプトを解析し、スクリプトを表す関数を返します。</span><span class="sxs-lookup"><span data-stu-id="010fa-104">Parses a serialized script and returns a function representing the script.</span></span>  
  
## <span data-ttu-id="010fa-105">構文</span><span class="sxs-lookup"><span data-stu-id="010fa-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsParseSerializedScript(  
   _In_z_ const wchar_t *script,  
   _In_ BYTE *buffer,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="010fa-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="010fa-106">Parameters</span></span>  
 `script`  
 <span data-ttu-id="010fa-107">解析するスクリプト。</span><span class="sxs-lookup"><span data-stu-id="010fa-107">The script to parse.</span></span>  
  
 `buffer`  
 <span data-ttu-id="010fa-108">シリアル化されたスクリプト。</span><span class="sxs-lookup"><span data-stu-id="010fa-108">The serialized script.</span></span>  
  
 `sourceContext`  
 <span data-ttu-id="010fa-109">デバッグ可能なスクリプト コンテキストで使用できるスクリプトを識別する Cookie。</span><span class="sxs-lookup"><span data-stu-id="010fa-109">A cookie identifying the script that can be used by debuggable script contexts.</span></span>  
  
 `sourceUrl`  
 <span data-ttu-id="010fa-110">スクリプトの作成場所。</span><span class="sxs-lookup"><span data-stu-id="010fa-110">The location the script came from.</span></span>  
  
 `result`  
 <span data-ttu-id="010fa-111">スクリプト コードを表す関数。</span><span class="sxs-lookup"><span data-stu-id="010fa-111">A function representing the script code.</span></span>  
  
## <span data-ttu-id="010fa-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="010fa-112">Return Value</span></span>  
 <span data-ttu-id="010fa-113">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="010fa-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="010fa-114">注釈</span><span class="sxs-lookup"><span data-stu-id="010fa-114">Remarks</span></span>  
 <span data-ttu-id="010fa-115">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="010fa-115">Requires an active script context.</span></span>  
  
 <span data-ttu-id="010fa-116">バッファーはスクリプト エンジンによってメモリ内に保持されないので、スクリプトの実行に使用される可能性がある限り、コードで有効な状態を維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="010fa-116">The buffer is not persisted in memory by the scripting engine, so your code must keep it alive for as long as it might be used to execute scripts.</span></span>  
  
## <span data-ttu-id="010fa-117">要件</span><span class="sxs-lookup"><span data-stu-id="010fa-117">Requirements</span></span>  
 <span data-ttu-id="010fa-118">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="010fa-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="010fa-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="010fa-119">See Also</span></span>  
 [<span data-ttu-id="010fa-120">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="010fa-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
