---
description: オブジェクトのインデックス付きプロパティの外部データ情報を取得します。
title: JsGetIndexedPropertiesExternalData 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 2c313163-3462-42fd-8dee-3dfb3ac7f43f
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 96fdcd4b6fe29ffc20a796983cc1de692c80a3f1
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569320"
---
# <span data-ttu-id="59263-103">JsGetIndexedPropertiesExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="59263-103">JsGetIndexedPropertiesExternalData Function</span></span>
<span data-ttu-id="59263-104">オブジェクトのインデックス付きプロパティの外部データ情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="59263-104">Retrieves an object's indexed properties external data information.</span></span>  
  
## <span data-ttu-id="59263-105">構文</span><span class="sxs-lookup"><span data-stu-id="59263-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetIndexedPropertiesExternalData(  
   _In_ JsValueRef object,  
   _Out_ void** data,  
   _Out_ JsTypedArrayType* arrayType,  
   _Out_ unsigned int* elementLength  
);  
```  
  
#### <span data-ttu-id="59263-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="59263-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="59263-107">オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="59263-107">The object.</span></span>  
  
 `data`  
 <span data-ttu-id="59263-108">オブジェクトのインデックスが作成されたプロパティの外部データバックストア。</span><span class="sxs-lookup"><span data-stu-id="59263-108">The external data back store for the object's indexed properties.</span></span>  
  
 `arrayType`  
 <span data-ttu-id="59263-109">外部データの配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="59263-109">The array element type in external data.</span></span>  
  
 `elementLength`  
 <span data-ttu-id="59263-110">外部データの配列要素の数です。</span><span class="sxs-lookup"><span data-stu-id="59263-110">The number of array elements in external data.</span></span>  
  
## <span data-ttu-id="59263-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="59263-111">Return Value</span></span>  
 <span data-ttu-id="59263-112">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="59263-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="59263-113">注釈</span><span class="sxs-lookup"><span data-stu-id="59263-113">Remarks</span></span>  
 <span data-ttu-id="59263-114">この API は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="59263-114">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="59263-115">要件</span><span class="sxs-lookup"><span data-stu-id="59263-115">Requirements</span></span>  
 <span data-ttu-id="59263-116">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="59263-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="59263-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="59263-117">See Also</span></span>  
 [<span data-ttu-id="59263-118">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="59263-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)