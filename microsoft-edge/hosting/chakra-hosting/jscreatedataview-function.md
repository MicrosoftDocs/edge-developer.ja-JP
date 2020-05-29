---
description: Javascript オブジェクトを作成 `DataView` します。
title: JsCreateDataView 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 161e59eb-d429-46f7-9a38-bbf2149ccf44
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1bf237458e8561b7070e4f3f0d4a14050f028375
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569373"
---
# <span data-ttu-id="0318b-103">JsCreateDataView 関数</span><span class="sxs-lookup"><span data-stu-id="0318b-103">JsCreateDataView Function</span></span>
<span data-ttu-id="0318b-104">Javascript オブジェクトを作成 `DataView` します。</span><span class="sxs-lookup"><span data-stu-id="0318b-104">Creates a Javascript `DataView` object.</span></span>  
  
## <span data-ttu-id="0318b-105">構文</span><span class="sxs-lookup"><span data-stu-id="0318b-105">Syntax</span></span>  
  
```cpp  
JsErrorCode  JsCreateDataView(  
   _In_ JsValueRef arrayBuffer,  
   _In_ unsigned int byteOffset,  
   _In_ unsigned int byteLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="0318b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0318b-106">Parameters</span></span>  
 `arrayBuffer`  
 <span data-ttu-id="0318b-107">`ArrayBuffer`Result オブジェクトの記憶域として使用する既存のオブジェクト `DataView` 。</span><span class="sxs-lookup"><span data-stu-id="0318b-107">An existing `ArrayBuffer` object to use as the storage for the result `DataView` object.</span></span>  
  
 `byteOffset`  
 <span data-ttu-id="0318b-108">結果を参照するための先頭からのバイト単位のオフセット `arrayBuffer` `DataView` 。</span><span class="sxs-lookup"><span data-stu-id="0318b-108">The offset in bytes from the start of `arrayBuffer` for result `DataView` to reference.</span></span>  
  
 `byteLength`  
 <span data-ttu-id="0318b-109">Result DataView が参照する配列バッファーのバイト数。</span><span class="sxs-lookup"><span data-stu-id="0318b-109">The number of bytes in the ArrayBuffer for result DataView to reference.</span></span>  
  
 `result`  
 <span data-ttu-id="0318b-110">新しい DataView オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0318b-110">The new DataView object.</span></span>  
  
## <span data-ttu-id="0318b-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="0318b-111">Return Value</span></span>  
 <span data-ttu-id="0318b-112">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="0318b-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="0318b-113">注釈</span><span class="sxs-lookup"><span data-stu-id="0318b-113">Remarks</span></span>  
 <span data-ttu-id="0318b-114">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="0318b-114">Requires an active script context.</span></span>  
  
 <span data-ttu-id="0318b-115">この API は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="0318b-115">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="0318b-116">要件</span><span class="sxs-lookup"><span data-stu-id="0318b-116">Requirements</span></span>  
 <span data-ttu-id="0318b-117">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="0318b-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="0318b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="0318b-118">See Also</span></span>  
 [<span data-ttu-id="0318b-119">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="0318b-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)