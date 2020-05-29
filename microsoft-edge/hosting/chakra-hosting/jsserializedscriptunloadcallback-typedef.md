---
description: スクリプトの実行に関連するすべてのリソースが終了したときに、ランタイムによって呼び出されます。 この時点で、呼び出し元は、読み込み、バイトコード、コンテキストを解放する必要があります。
title: JsSerializedScriptUnloadCallback typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d18c392-cca0-411e-9f2b-0d788b16161a
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9555b3fd8c14c9629d17c13592e3c78a78be150e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570388"
---
# <span data-ttu-id="2cdd2-104">JsSerializedScriptUnloadCallback typedef</span><span class="sxs-lookup"><span data-stu-id="2cdd2-104">JsSerializedScriptUnloadCallback typedef</span></span>
<span data-ttu-id="2cdd2-105">スクリプトの実行に関連するすべてのリソースが終了したときに、ランタイムによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2cdd2-105">Called by the runtime when it is finished with all resources related to the script execution.</span></span> <span data-ttu-id="2cdd2-106">この時点で、呼び出し元は、読み込み、バイトコード、コンテキストを解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cdd2-106">The caller should free the source if loaded, the byte code, and the context at this time.</span></span>  
  
## <span data-ttu-id="2cdd2-107">構文</span><span class="sxs-lookup"><span data-stu-id="2cdd2-107">Syntax</span></span>  
  
```cpp  
 typedef void (CALLBACK * JsSerializedScriptUnloadCallback)(  
  _In_ JsSourceContext sourceContext  
);  
```  
  
#### <span data-ttu-id="2cdd2-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2cdd2-108">Parameters</span></span>  
 `sourceContext`  
 <span data-ttu-id="2cdd2-109">またはに渡されたコンテキスト `JsParseSerializedScriptWithCallback` `JsRunSerializedScriptWithCallback` 。</span><span class="sxs-lookup"><span data-stu-id="2cdd2-109">The context passed to `JsParseSerializedScriptWithCallback` or `JsRunSerializedScriptWithCallback`.</span></span>  
  
## <span data-ttu-id="2cdd2-110">注釈</span><span class="sxs-lookup"><span data-stu-id="2cdd2-110">Remarks</span></span>  
  
> [!WARNING]
## <span data-ttu-id="2cdd2-111">要件</span><span class="sxs-lookup"><span data-stu-id="2cdd2-111">Requirements</span></span>  
 <span data-ttu-id="2cdd2-112">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="2cdd2-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="2cdd2-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="2cdd2-113">See Also</span></span>  
 [<span data-ttu-id="2cdd2-114">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="2cdd2-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)