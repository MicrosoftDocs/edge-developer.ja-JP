---
description: WinRT 名前空間をプロジェクトします。
title: JsProjectWinRTNamespace 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 8a23c154-df4b-4ce3-9fef-f41f90acdb87
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c4d63727b3d25bbb346fee7179ae0d942ae37008
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569273"
---
# <span data-ttu-id="6de97-103">JsProjectWinRTNamespace 関数</span><span class="sxs-lookup"><span data-stu-id="6de97-103">JsProjectWinRTNamespace Function</span></span>
<span data-ttu-id="6de97-104">WinRT 名前空間をプロジェクトします。</span><span class="sxs-lookup"><span data-stu-id="6de97-104">Project a WinRT namespace.</span></span>  
  
## <span data-ttu-id="6de97-105">構文</span><span class="sxs-lookup"><span data-stu-id="6de97-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode)  
   JsProjectWinRTNamespace(  
   _In_z_ const wchar_t *namespaceName  
);  
```  
  
#### <span data-ttu-id="6de97-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6de97-106">Parameters</span></span>  
 `namespaceName`  
 <span data-ttu-id="6de97-107">投影される WinRT 名前空間。</span><span class="sxs-lookup"><span data-stu-id="6de97-107">The WinRT namespace to be projected.</span></span>  
  
## <span data-ttu-id="6de97-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="6de97-108">Return Value</span></span>  
 <span data-ttu-id="6de97-109">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="6de97-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="6de97-110">注釈</span><span class="sxs-lookup"><span data-stu-id="6de97-110">Remarks</span></span>  
 <span data-ttu-id="6de97-111">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="6de97-111">Requires an active script context.</span></span>  
  
 <span data-ttu-id="6de97-112">この API は、EdgeHTML モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="6de97-112">This API is supported only in EdgeHTML mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6de97-113">WinRT はユニバーサル Windows プラットフォーム (UWP) の前のプラットフォーム名です。</span><span class="sxs-lookup"><span data-stu-id="6de97-113">WinRT was the platform name before Universal Windows Platform (UWP).</span></span>  
  
## <span data-ttu-id="6de97-114">要件</span><span class="sxs-lookup"><span data-stu-id="6de97-114">Requirements</span></span>  
 <span data-ttu-id="6de97-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="6de97-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="6de97-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6de97-116">See Also</span></span>  
 [<span data-ttu-id="6de97-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="6de97-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)