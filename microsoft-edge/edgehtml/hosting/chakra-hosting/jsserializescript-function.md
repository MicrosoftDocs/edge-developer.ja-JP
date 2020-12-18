---
description: 解析されたスクリプトを、再利用できるよりもバッファーにシリアル化します。
title: JsSerializeScript 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSerializeScript
helpviewer_keywords:
- JsSerializeScript function
ms.assetid: ca42c194-e1c1-407d-b542-b9d494e3ac4e
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 236cf40c91256e999d5390acd395b1e97fe538ad
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235036"
---
# <span data-ttu-id="bc229-103">JsSerializeScript 関数</span><span class="sxs-lookup"><span data-stu-id="bc229-103">JsSerializeScript Function</span></span>

<span data-ttu-id="bc229-104">解析されたスクリプトを、再利用できるよりもバッファーにシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="bc229-104">Serializes a parsed script to a buffer than can be reused.</span></span>  
  
## <span data-ttu-id="bc229-105">構文</span><span class="sxs-lookup"><span data-stu-id="bc229-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSerializeScript(  
   _In_z_ const wchar_t *script,  
   _Out_writes_to_opt_(*bufferSize,  
   *bufferSize) BYTE *buffer,  
   _Inout_ unsigned long *bufferSize  
);  
```  
  
#### <span data-ttu-id="bc229-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bc229-106">Parameters</span></span>  
 `script`  
 <span data-ttu-id="bc229-107">シリアル化するスクリプト。</span><span class="sxs-lookup"><span data-stu-id="bc229-107">The script to serialize.</span></span>  
  
 `buffer`  
 <span data-ttu-id="bc229-108">シリアル化されたスクリプトを置くバッファー。</span><span class="sxs-lookup"><span data-stu-id="bc229-108">The buffer to put the serialized script into.</span></span> <span data-ttu-id="bc229-109">null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bc229-109">Can be null.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="bc229-110">入力時のバッファーのサイズ (バイト単位)。が終了すると、シリアル化されたスクリプトを保持するために必要なバッファーのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="bc229-110">On entry, the size of the buffer, in bytes; on exit, the size of the buffer, in bytes, required to hold the serialized script.</span></span>  
  
## <span data-ttu-id="bc229-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="bc229-111">Return Value</span></span>  
 <span data-ttu-id="bc229-112">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="bc229-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="bc229-113">注釈</span><span class="sxs-lookup"><span data-stu-id="bc229-113">Remarks</span></span>  
 `JsSerializeScript` <span data-ttu-id="bc229-114">スクリプトを解析し、解析された形式のスクリプトをランタイムに依存しない形式で格納します。</span><span class="sxs-lookup"><span data-stu-id="bc229-114">parses a script and then stores the parsed form of the script in a runtime-independent format.</span></span> <span data-ttu-id="bc229-115">シリアル化されたスクリプトは、スクリプトを再解析することなく、任意の実行時に逆シリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="bc229-115">The serialized script then can be deserialized in any runtime without requiring the script to be re-parsed.</span></span>  
  
 <span data-ttu-id="bc229-116">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="bc229-116">Requires an active script context.</span></span>  
  
## <span data-ttu-id="bc229-117">要件</span><span class="sxs-lookup"><span data-stu-id="bc229-117">Requirements</span></span>  
 <span data-ttu-id="bc229-118">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="bc229-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="bc229-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc229-119">See Also</span></span>  
 [<span data-ttu-id="bc229-120">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="bc229-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
