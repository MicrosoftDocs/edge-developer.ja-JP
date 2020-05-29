---
description: ファイナライザーのコールバック。
title: JsFinalizeCallback Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: aa7a0269-b9d4-4717-97ac-8da7eb6ced15
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: d2ee2c2c11e85094010cd15be59aa7ac587b614f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570466"
---
# <span data-ttu-id="7008e-103">JsFinalizeCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="7008e-103">JsFinalizeCallback Typedef</span></span>
<span data-ttu-id="7008e-104">ファイナライザーのコールバック。</span><span class="sxs-lookup"><span data-stu-id="7008e-104">A finalizer callback.</span></span>  
  
## <span data-ttu-id="7008e-105">構文</span><span class="sxs-lookup"><span data-stu-id="7008e-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsFinalizeCallback)(  
   _In_opt_ void *data  
);  
```  
  
#### <span data-ttu-id="7008e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7008e-106">Parameters</span></span>  
 <span data-ttu-id="7008e-107">data</span><span class="sxs-lookup"><span data-stu-id="7008e-107">data</span></span>  
 <span data-ttu-id="7008e-108">完了するオブジェクトの作成時に渡された外部データ。</span><span class="sxs-lookup"><span data-stu-id="7008e-108">The external data that was passed in when creating the object being finalized.</span></span>  
  
## <span data-ttu-id="7008e-109">要件</span><span class="sxs-lookup"><span data-stu-id="7008e-109">Requirements</span></span>  
 <span data-ttu-id="7008e-110">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="7008e-110">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="7008e-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="7008e-111">See Also</span></span>  
 [<span data-ttu-id="7008e-112">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="7008e-112">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)