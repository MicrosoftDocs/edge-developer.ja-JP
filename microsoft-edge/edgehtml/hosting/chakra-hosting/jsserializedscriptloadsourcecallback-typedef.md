---
description: シリアル化されたスクリプトのソース コードを読み込むランタイムによって呼び出されます。 呼び出し元は、スクリプト バッファーを有効な状態に保つ必要があります `JsSerializedScriptUnloadCallback` 。
title: JsSerializedScriptLoadSourceCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 9406c488-76ac-49e5-b305-39751f3412ea
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2bb30befc61003d20cdeaa293fd1fdfdc95b36f7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235087"
---
# <span data-ttu-id="e6bc6-104">JsSerializedScriptLoadSourceCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="e6bc6-104">JsSerializedScriptLoadSourceCallback Typedef</span></span>

<span data-ttu-id="e6bc6-105">シリアル化されたスクリプトのソース コードを読み込むランタイムによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e6bc6-105">Called by the runtime to load the source code of the serialized script.</span></span> <span data-ttu-id="e6bc6-106">呼び出し元は、スクリプト バッファーを有効な状態に保つ必要があります `JsSerializedScriptUnloadCallback` 。</span><span class="sxs-lookup"><span data-stu-id="e6bc6-106">The caller must keep the script buffer valid until the `JsSerializedScriptUnloadCallback`.</span></span>  
  
## <span data-ttu-id="e6bc6-107">構文</span><span class="sxs-lookup"><span data-stu-id="e6bc6-107">Syntax</span></span>  
  
```cpp  
typedef bool (CALLBACK * JsSerializedScriptLoadSourceCallback)(  
  _In_ JsSourceContextsourceContext,  
  _Outptr_result_z_ const wchar_t** scriptBuffer  
);  
```  
  
#### <span data-ttu-id="e6bc6-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e6bc6-108">Parameters</span></span>  
 `sourceContext`  
 <span data-ttu-id="e6bc6-109">渡されるコンテキスト。または `JsParseSerializedScriptWithCallback` `JsRunSerializedScriptWithCallback` .</span><span class="sxs-lookup"><span data-stu-id="e6bc6-109">The context passed to `JsParseSerializedScriptWithCallback` or `JsRunSerializedScriptWithCallback`.</span></span>  
  
 `scriptBuffer`  
 <span data-ttu-id="e6bc6-110">返されたスクリプト。</span><span class="sxs-lookup"><span data-stu-id="e6bc6-110">The script returned.</span></span>  
  
## <span data-ttu-id="e6bc6-111">注釈</span><span class="sxs-lookup"><span data-stu-id="e6bc6-111">Remarks</span></span>  
  
> [!WARNING]
## <span data-ttu-id="e6bc6-112">要件</span><span class="sxs-lookup"><span data-stu-id="e6bc6-112">Requirements</span></span>  
 <span data-ttu-id="e6bc6-113">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="e6bc6-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="e6bc6-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6bc6-114">See Also</span></span>  
 [<span data-ttu-id="e6bc6-115">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="e6bc6-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
