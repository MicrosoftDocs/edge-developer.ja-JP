---
description: スクリプトの実行に関連するリソースが完了すると、ランタイムによって呼び出されます。 呼び出し元は、読み込まれた場合はソース、バイト コード、コンテキストを解放する必要があります。
title: JsSerializedScriptUnloadCallback typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 8d18c392-cca0-411e-9f2b-0d788b16161a
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5c63f2ff3faf21a19e31f2f6fd1692e21d59fc0b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235037"
---
# <span data-ttu-id="f1fa2-104">JsSerializedScriptUnloadCallback typedef</span><span class="sxs-lookup"><span data-stu-id="f1fa2-104">JsSerializedScriptUnloadCallback typedef</span></span>

<span data-ttu-id="f1fa2-105">スクリプトの実行に関連するリソースが完了すると、ランタイムによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f1fa2-105">Called by the runtime when it is finished with all resources related to the script execution.</span></span> <span data-ttu-id="f1fa2-106">呼び出し元は、読み込まれた場合はソース、バイト コード、コンテキストを解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1fa2-106">The caller should free the source if loaded, the byte code, and the context at this time.</span></span>  
  
## <span data-ttu-id="f1fa2-107">構文</span><span class="sxs-lookup"><span data-stu-id="f1fa2-107">Syntax</span></span>  
  
```cpp  
 typedef void (CALLBACK * JsSerializedScriptUnloadCallback)(  
  _In_ JsSourceContext sourceContext  
);  
```  
  
#### <span data-ttu-id="f1fa2-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1fa2-108">Parameters</span></span>  
 `sourceContext`  
 <span data-ttu-id="f1fa2-109">渡されるコンテキスト。または `JsParseSerializedScriptWithCallback` `JsRunSerializedScriptWithCallback` .</span><span class="sxs-lookup"><span data-stu-id="f1fa2-109">The context passed to `JsParseSerializedScriptWithCallback` or `JsRunSerializedScriptWithCallback`.</span></span>  
  
## <span data-ttu-id="f1fa2-110">注釈</span><span class="sxs-lookup"><span data-stu-id="f1fa2-110">Remarks</span></span>  
  
> [!WARNING]
## <span data-ttu-id="f1fa2-111">要件</span><span class="sxs-lookup"><span data-stu-id="f1fa2-111">Requirements</span></span>  
 <span data-ttu-id="f1fa2-112">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="f1fa2-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="f1fa2-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1fa2-113">See Also</span></span>  
 [<span data-ttu-id="f1fa2-114">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="f1fa2-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
