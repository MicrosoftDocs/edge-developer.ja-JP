---
description: 渡されたポインターによって投影された JavaScript 値を作成し `IInspectable` ます。
title: JsInspectableToObject 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: dd0ad567-2ba8-4a63-bee4-2c6ff5ce9fa9
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 26ce17eb3abcefcf9a1f0cc773e9fe4c3aaf05cd
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569300"
---
# <span data-ttu-id="db8e5-103">JsInspectableToObject 関数</span><span class="sxs-lookup"><span data-stu-id="db8e5-103">JsInspectableToObject Function</span></span>
<span data-ttu-id="db8e5-104">渡されたポインターによって投影された JavaScript 値を作成し `IInspectable` ます。</span><span class="sxs-lookup"><span data-stu-id="db8e5-104">Creates a JavaScript value that is a projection of the passed in `IInspectable` pointer.</span></span>  
  
## <span data-ttu-id="db8e5-105">構文</span><span class="sxs-lookup"><span data-stu-id="db8e5-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsInspectableToObject(  
        _In_ IInspectable  *inspectable,  
        _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="db8e5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="db8e5-106">Parameters</span></span>  
 `inspectable`  
 <span data-ttu-id="db8e5-107">`IInspectable`を投影します。</span><span class="sxs-lookup"><span data-stu-id="db8e5-107">A `IInspectable` to be projected.</span></span>  
  
 `value`  
 <span data-ttu-id="db8e5-108">のプロジェクションである JavaScript 値 `IInspectable` 。</span><span class="sxs-lookup"><span data-stu-id="db8e5-108">A JavaScript value that is a projection of the `IInspectable`.</span></span>  
  
## <span data-ttu-id="db8e5-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="db8e5-109">Return Value</span></span>  
 <span data-ttu-id="db8e5-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="db8e5-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="db8e5-111">注釈</span><span class="sxs-lookup"><span data-stu-id="db8e5-111">Remarks</span></span>  
 <span data-ttu-id="db8e5-112">射影された値は、スクリプトで WinRT オブジェクトを呼び出すために使うことができます。</span><span class="sxs-lookup"><span data-stu-id="db8e5-112">The projected value can be used by script to call a WinRT object.</span></span> <span data-ttu-id="db8e5-113">ホストは、COM スレッドルールの強制を行います。</span><span class="sxs-lookup"><span data-stu-id="db8e5-113">Hosts are responsible for enforcing COM threading rules.</span></span>  
  
 <span data-ttu-id="db8e5-114">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="db8e5-114">Requires an active script context.</span></span>  
  
 <span data-ttu-id="db8e5-115">この API は、EdgeHTML モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="db8e5-115">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="db8e5-116">要件</span><span class="sxs-lookup"><span data-stu-id="db8e5-116">Requirements</span></span>  
 <span data-ttu-id="db8e5-117">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="db8e5-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="db8e5-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="db8e5-118">See Also</span></span>  
 [<span data-ttu-id="db8e5-119">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="db8e5-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)