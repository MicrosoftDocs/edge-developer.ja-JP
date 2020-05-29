---
description: 解析されたスクリプトを再利用可能なバッファーにシリアル化します。
title: JsSerializeScript 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSerializeScript
helpviewer_keywords:
- JsSerializeScript function
ms.assetid: ca42c194-e1c1-407d-b542-b9d494e3ac4e
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1b45067fddb7ea4dff02e527e460db1270011c61
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570386"
---
# <span data-ttu-id="6c908-103">JsSerializeScript 関数</span><span class="sxs-lookup"><span data-stu-id="6c908-103">JsSerializeScript Function</span></span>
<span data-ttu-id="6c908-104">解析されたスクリプトを再利用可能なバッファーにシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="6c908-104">Serializes a parsed script to a buffer than can be reused.</span></span>  
  
## <span data-ttu-id="6c908-105">構文</span><span class="sxs-lookup"><span data-stu-id="6c908-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSerializeScript(  
   _In_z_ const wchar_t *script,  
   _Out_writes_to_opt_(*bufferSize,  
   *bufferSize) BYTE *buffer,  
   _Inout_ unsigned long *bufferSize  
);  
```  
  
#### <span data-ttu-id="6c908-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6c908-106">Parameters</span></span>  
 `script`  
 <span data-ttu-id="6c908-107">シリアル化するスクリプト。</span><span class="sxs-lookup"><span data-stu-id="6c908-107">The script to serialize.</span></span>  
  
 `buffer`  
 <span data-ttu-id="6c908-108">シリアル化されたスクリプトを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="6c908-108">The buffer to put the serialized script into.</span></span> <span data-ttu-id="6c908-109">Null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6c908-109">Can be null.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="6c908-110">エントリの場合は、バッファーのサイズ (バイト単位)。終了時に、シリアル化されたスクリプトを保持するために必要なバッファーのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="6c908-110">On entry, the size of the buffer, in bytes; on exit, the size of the buffer, in bytes, required to hold the serialized script.</span></span>  
  
## <span data-ttu-id="6c908-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="6c908-111">Return Value</span></span>  
 <span data-ttu-id="6c908-112">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="6c908-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="6c908-113">注釈</span><span class="sxs-lookup"><span data-stu-id="6c908-113">Remarks</span></span>  
 `JsSerializeScript` <span data-ttu-id="6c908-114">スクリプトを解析し、実行時に依存しない形式でスクリプトの解析された形式を保存します。</span><span class="sxs-lookup"><span data-stu-id="6c908-114">parses a script and then stores the parsed form of the script in a runtime-independent format.</span></span> <span data-ttu-id="6c908-115">シリアル化されたスクリプトは、スクリプトを再解析する必要なく、任意のランタイムで逆シリアル化することができます。</span><span class="sxs-lookup"><span data-stu-id="6c908-115">The serialized script then can be deserialized in any runtime without requiring the script to be re-parsed.</span></span>  
  
 <span data-ttu-id="6c908-116">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="6c908-116">Requires an active script context.</span></span>  
  
## <span data-ttu-id="6c908-117">要件</span><span class="sxs-lookup"><span data-stu-id="6c908-117">Requirements</span></span>  
 <span data-ttu-id="6c908-118">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="6c908-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="6c908-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c908-119">See Also</span></span>  
 [<span data-ttu-id="6c908-120">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="6c908-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)