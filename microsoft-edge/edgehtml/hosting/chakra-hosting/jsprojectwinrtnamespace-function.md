---
description: WinRT 名前空間を投影します。
title: JsProjectWinRTNamespace 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 8a23c154-df4b-4ce3-9fef-f41f90acdb87
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f781cf90aaec68b2bd305bf34c453fc663ad0187
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235093"
---
# <span data-ttu-id="c1674-103">JsProjectWinRTNamespace 関数</span><span class="sxs-lookup"><span data-stu-id="c1674-103">JsProjectWinRTNamespace Function</span></span>

<span data-ttu-id="c1674-104">WinRT 名前空間を投影します。</span><span class="sxs-lookup"><span data-stu-id="c1674-104">Project a WinRT namespace.</span></span>  
  
## <span data-ttu-id="c1674-105">構文</span><span class="sxs-lookup"><span data-stu-id="c1674-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode)  
   JsProjectWinRTNamespace(  
   _In_z_ const wchar_t *namespaceName  
);  
```  
  
#### <span data-ttu-id="c1674-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c1674-106">Parameters</span></span>  
 `namespaceName`  
 <span data-ttu-id="c1674-107">投影する WinRT 名前空間。</span><span class="sxs-lookup"><span data-stu-id="c1674-107">The WinRT namespace to be projected.</span></span>  
  
## <span data-ttu-id="c1674-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="c1674-108">Return Value</span></span>  
 <span data-ttu-id="c1674-109">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="c1674-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="c1674-110">注釈</span><span class="sxs-lookup"><span data-stu-id="c1674-110">Remarks</span></span>  
 <span data-ttu-id="c1674-111">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="c1674-111">Requires an active script context.</span></span>  
  
 <span data-ttu-id="c1674-112">この API は EdgeHTML モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c1674-112">This API is supported only in EdgeHTML mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1674-113">WinRT は、ユニバーサル Windows プラットフォーム (UWP) より前のプラットフォーム名でした。</span><span class="sxs-lookup"><span data-stu-id="c1674-113">WinRT was the platform name before Universal Windows Platform (UWP).</span></span>  
  
## <span data-ttu-id="c1674-114">要件</span><span class="sxs-lookup"><span data-stu-id="c1674-114">Requirements</span></span>  
 <span data-ttu-id="c1674-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="c1674-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="c1674-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1674-116">See Also</span></span>  
 [<span data-ttu-id="c1674-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="c1674-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
