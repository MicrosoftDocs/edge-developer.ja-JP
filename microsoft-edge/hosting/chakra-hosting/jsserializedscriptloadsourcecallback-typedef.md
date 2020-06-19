---
description: シリアル化されたスクリプトのソースコードを読み込むために、ランタイムによって呼び出されます。 呼び出し元は、の前に、スクリプトバッファーを有効な状態に維持する必要があり `JsSerializedScriptUnloadCallback` ます。
title: JsSerializedScriptLoadSourceCallback Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 9406c488-76ac-49e5-b305-39751f3412ea
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 571314145cc19513f04174a9a1c93822a5795b29
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752200"
---
# <span data-ttu-id="aa2da-104">JsSerializedScriptLoadSourceCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="aa2da-104">JsSerializedScriptLoadSourceCallback Typedef</span></span>
<span data-ttu-id="aa2da-105">シリアル化されたスクリプトのソースコードを読み込むために、ランタイムによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="aa2da-105">Called by the runtime to load the source code of the serialized script.</span></span> <span data-ttu-id="aa2da-106">呼び出し元は、の前に、スクリプトバッファーを有効な状態に維持する必要があり `JsSerializedScriptUnloadCallback` ます。</span><span class="sxs-lookup"><span data-stu-id="aa2da-106">The caller must keep the script buffer valid until the `JsSerializedScriptUnloadCallback`.</span></span>  
  
## <span data-ttu-id="aa2da-107">構文</span><span class="sxs-lookup"><span data-stu-id="aa2da-107">Syntax</span></span>  
  
```cpp  
typedef bool (CALLBACK * JsSerializedScriptLoadSourceCallback)(  
  _In_ JsSourceContextsourceContext,  
  _Outptr_result_z_ const wchar_t** scriptBuffer  
);  
```  
  
#### <span data-ttu-id="aa2da-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aa2da-108">Parameters</span></span>  
 `sourceContext`  
 <span data-ttu-id="aa2da-109">またはに渡されたコンテキスト `JsParseSerializedScriptWithCallback` `JsRunSerializedScriptWithCallback` 。</span><span class="sxs-lookup"><span data-stu-id="aa2da-109">The context passed to `JsParseSerializedScriptWithCallback` or `JsRunSerializedScriptWithCallback`.</span></span>  
  
 `scriptBuffer`  
 <span data-ttu-id="aa2da-110">スクリプトが返されました。</span><span class="sxs-lookup"><span data-stu-id="aa2da-110">The script returned.</span></span>  
  
## <span data-ttu-id="aa2da-111">注釈</span><span class="sxs-lookup"><span data-stu-id="aa2da-111">Remarks</span></span>  
  
> [!WARNING]
## <span data-ttu-id="aa2da-112">要件</span><span class="sxs-lookup"><span data-stu-id="aa2da-112">Requirements</span></span>  
 <span data-ttu-id="aa2da-113">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="aa2da-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="aa2da-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa2da-114">See Also</span></span>  
 [<span data-ttu-id="aa2da-115">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="aa2da-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)