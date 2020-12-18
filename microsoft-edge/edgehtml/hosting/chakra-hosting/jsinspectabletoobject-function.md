---
description: 渡されたポインターのプロジェクションである JavaScript 値を作成 `IInspectable` します。
title: JsInspectableToObject 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: dd0ad567-2ba8-4a63-bee4-2c6ff5ce9fa9
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a5d3d91b38c9db5de2eb8fb02526f6072f0f5147
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234910"
---
# <span data-ttu-id="10c71-103">JsInspectableToObject 関数</span><span class="sxs-lookup"><span data-stu-id="10c71-103">JsInspectableToObject Function</span></span>

<span data-ttu-id="10c71-104">渡されたポインターのプロジェクションである JavaScript 値を作成 `IInspectable` します。</span><span class="sxs-lookup"><span data-stu-id="10c71-104">Creates a JavaScript value that is a projection of the passed in `IInspectable` pointer.</span></span>  
  
## <span data-ttu-id="10c71-105">構文</span><span class="sxs-lookup"><span data-stu-id="10c71-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsInspectableToObject(  
        _In_ IInspectable  *inspectable,  
        _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="10c71-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="10c71-106">Parameters</span></span>  
 `inspectable`  
 <span data-ttu-id="10c71-107">投影 `IInspectable` される A。</span><span class="sxs-lookup"><span data-stu-id="10c71-107">A `IInspectable` to be projected.</span></span>  
  
 `value`  
 <span data-ttu-id="10c71-108">のプロジェクションである JavaScript 値 `IInspectable` 。</span><span class="sxs-lookup"><span data-stu-id="10c71-108">A JavaScript value that is a projection of the `IInspectable`.</span></span>  
  
## <span data-ttu-id="10c71-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="10c71-109">Return Value</span></span>  
 <span data-ttu-id="10c71-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="10c71-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="10c71-111">注釈</span><span class="sxs-lookup"><span data-stu-id="10c71-111">Remarks</span></span>  
 <span data-ttu-id="10c71-112">投影された値は、スクリプトで WinRT オブジェクトを呼び出す場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="10c71-112">The projected value can be used by script to call a WinRT object.</span></span> <span data-ttu-id="10c71-113">ホストは COM スレッド ルールを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10c71-113">Hosts are responsible for enforcing COM threading rules.</span></span>  
  
 <span data-ttu-id="10c71-114">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="10c71-114">Requires an active script context.</span></span>  
  
 <span data-ttu-id="10c71-115">この API は EdgeHTML モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="10c71-115">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="10c71-116">要件</span><span class="sxs-lookup"><span data-stu-id="10c71-116">Requirements</span></span>  
 <span data-ttu-id="10c71-117">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="10c71-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="10c71-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="10c71-118">See Also</span></span>  
 [<span data-ttu-id="10c71-119">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="10c71-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
