---
description: 指定したオブジェクトのインデックス位置の値を削除します。
title: JsDeleteIndexedProperty 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsDeleteIndexedProperty
helpviewer_keywords:
- JsDeleteIndexedProperty function
ms.assetid: cc876839-2ecd-41a8-82d0-c19b3de944e3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 6148a9c59105749a78ece73578d4b840501c6ecc
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569340"
---
# <span data-ttu-id="4b0e6-103">JsDeleteIndexedProperty 関数</span><span class="sxs-lookup"><span data-stu-id="4b0e6-103">JsDeleteIndexedProperty Function</span></span>
<span data-ttu-id="4b0e6-104">指定したオブジェクトのインデックス位置の値を削除します。</span><span class="sxs-lookup"><span data-stu-id="4b0e6-104">Delete the value at the specified index of an object.</span></span>  
  
## <span data-ttu-id="4b0e6-105">構文</span><span class="sxs-lookup"><span data-stu-id="4b0e6-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDeleteIndexedProperty(  
   _In_ JsValueRef object,  
   _In_ JsValueRef index  
);  
```  
  
#### <span data-ttu-id="4b0e6-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4b0e6-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="4b0e6-107">操作対象のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4b0e6-107">The object to operate on.</span></span>  
  
 `index`  
 <span data-ttu-id="4b0e6-108">削除するインデックス。</span><span class="sxs-lookup"><span data-stu-id="4b0e6-108">The index to delete.</span></span>  
  
## <span data-ttu-id="4b0e6-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="4b0e6-109">Return Value</span></span>  
 <span data-ttu-id="4b0e6-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="4b0e6-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="4b0e6-111">注釈</span><span class="sxs-lookup"><span data-stu-id="4b0e6-111">Remarks</span></span>  
 <span data-ttu-id="4b0e6-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="4b0e6-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="4b0e6-113">要件</span><span class="sxs-lookup"><span data-stu-id="4b0e6-113">Requirements</span></span>  
 <span data-ttu-id="4b0e6-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="4b0e6-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="4b0e6-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b0e6-115">See Also</span></span>  
 [<span data-ttu-id="4b0e6-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="4b0e6-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)