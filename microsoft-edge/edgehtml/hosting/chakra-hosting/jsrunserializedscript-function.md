---
description: シリアル化されたスクリプトを実行します。
title: JsRunSerializedScript 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsRunSerializedScript
helpviewer_keywords:
- JsRunSerializedScript function
ms.assetid: 3fd3f6f1-eb3e-4751-92a5-c93b1035f3b2
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 46f293d76bf0944c1cdedae917735c505798f4ad
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235023"
---
# <span data-ttu-id="4ffb7-103">JsRunSerializedScript 関数</span><span class="sxs-lookup"><span data-stu-id="4ffb7-103">JsRunSerializedScript Function</span></span>

<span data-ttu-id="4ffb7-104">シリアル化されたスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="4ffb7-104">Runs a serialized script.</span></span>  
  
## <span data-ttu-id="4ffb7-105">構文</span><span class="sxs-lookup"><span data-stu-id="4ffb7-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsRunSerializedScript(  
   _In_z_ const wchar_t *script,  
   _In_ BYTE *buffer,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="4ffb7-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4ffb7-106">Parameters</span></span>  
 `script`  
 <span data-ttu-id="4ffb7-107">シリアル化されたスクリプトのソース コード。</span><span class="sxs-lookup"><span data-stu-id="4ffb7-107">The source code of the serialized script.</span></span>  
  
 `buffer`  
 <span data-ttu-id="4ffb7-108">シリアル化されたスクリプト。</span><span class="sxs-lookup"><span data-stu-id="4ffb7-108">The serialized script.</span></span>  
  
 `sourceContext`  
 <span data-ttu-id="4ffb7-109">デバッグ可能なスクリプト コンテキストで使用できるスクリプトを識別する Cookie。</span><span class="sxs-lookup"><span data-stu-id="4ffb7-109">A cookie identifying the script that can be used by debuggable script contexts.</span></span>  
  
 `sourceUrl`  
 <span data-ttu-id="4ffb7-110">スクリプトの作成場所。</span><span class="sxs-lookup"><span data-stu-id="4ffb7-110">The location the script came from.</span></span>  
  
 `result`  
 <span data-ttu-id="4ffb7-111">スクリプトを実行した結果 (スクリプトがある場合)。</span><span class="sxs-lookup"><span data-stu-id="4ffb7-111">The result of running the script, if any.</span></span> <span data-ttu-id="4ffb7-112">このパラメーターは null に設定できます。</span><span class="sxs-lookup"><span data-stu-id="4ffb7-112">This parameter can be null.</span></span>  
  
## <span data-ttu-id="4ffb7-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="4ffb7-113">Return Value</span></span>  
 <span data-ttu-id="4ffb7-114">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="4ffb7-114">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="4ffb7-115">注釈</span><span class="sxs-lookup"><span data-stu-id="4ffb7-115">Remarks</span></span>  
 <span data-ttu-id="4ffb7-116">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="4ffb7-116">Requires an active script context.</span></span>  
  
 <span data-ttu-id="4ffb7-117">バッファーはスクリプト エンジンによってメモリ内に保持されないので、スクリプトの実行に使用される可能性がある限り、コードで有効な状態を維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ffb7-117">The buffer is not persisted in memory by the scripting engine, so your code must keep it alive for as long as it might be used to execute scripts.</span></span>  
  
## <span data-ttu-id="4ffb7-118">要件</span><span class="sxs-lookup"><span data-stu-id="4ffb7-118">Requirements</span></span>  
 <span data-ttu-id="4ffb7-119">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="4ffb7-119">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="4ffb7-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ffb7-120">See Also</span></span>  
 [<span data-ttu-id="4ffb7-121">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="4ffb7-121">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
