---
description: シリアル化されたスクリプトを解析し、スクリプトを表す関数を返します。 必要な場合にのみ、スクリプトソースの遅延読み込み機能を提供します。
title: JsParseSerializedScriptWithCallback 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a93ecfb-4b82-4a85-b24c-6816db2332ea
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: ad6d635722f0b3fea8b19f8d16679b402d1fd56e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570414"
---
# <span data-ttu-id="b88d5-104">JsParseSerializedScriptWithCallback 関数</span><span class="sxs-lookup"><span data-stu-id="b88d5-104">JsParseSerializedScriptWithCallback Function</span></span>
<span data-ttu-id="b88d5-105">シリアル化されたスクリプトを解析し、スクリプトを表す関数を返します。</span><span class="sxs-lookup"><span data-stu-id="b88d5-105">Parses a serialized script and returns a function representing the script.</span></span> <span data-ttu-id="b88d5-106">必要な場合にのみ、スクリプトソースの遅延読み込み機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="b88d5-106">Provides the ability to lazy load the script source only if/when it is needed.</span></span>  
  
## <span data-ttu-id="b88d5-107">構文</span><span class="sxs-lookup"><span data-stu-id="b88d5-107">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsParseSerializedScriptWithCallback(  
  _In_ JsSerializedScriptLoadSourceCallback scriptLoadCallback,  
  _In_ JsSerializedScriptUnloadCallback scriptUnloadCallback,  
  _In_ BYTE *buffer,  
  _In_ JsSourceContext sourceContext,  
  _In_z_ const wchar_t *sourceUrl,  
  _Out_ JsValueRef * result  
);  
  
```  
  
#### <span data-ttu-id="b88d5-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b88d5-108">Parameters</span></span>  
 `scriptLoadCallback`  
 <span data-ttu-id="b88d5-109">スクリプトのソースコードを読み込む必要があるときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b88d5-109">Callback called when the source code of the script needs to be loaded.</span></span>  
  
 `scriptUnloadCallback`  
 <span data-ttu-id="b88d5-110">シリアル化されたスクリプトとソースコードが不要になったときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b88d5-110">Callback called when the serialized script and source code are no longer needed.</span></span>  
  
 `buffer`  
 <span data-ttu-id="b88d5-111">シリアル化されたスクリプト。</span><span class="sxs-lookup"><span data-stu-id="b88d5-111">The serialized script.</span></span>  
  
 `sourceContext`  
 <span data-ttu-id="b88d5-112">デバッグ可能なスクリプトコンテキストによって使用できるスクリプトを識別する cookie。</span><span class="sxs-lookup"><span data-stu-id="b88d5-112">A cookie identifying the script that can be used by debuggable script contexts.</span></span>     <span data-ttu-id="b88d5-113">このコンテキストは、scriptLoadCallback と scriptUnloadCallback に渡されます。</span><span class="sxs-lookup"><span data-stu-id="b88d5-113">This context will passed into scriptLoadCallback and scriptUnloadCallback.</span></span>  
  
 `sourceUrl`  
 <span data-ttu-id="b88d5-114">スクリプトの取得元の場所。</span><span class="sxs-lookup"><span data-stu-id="b88d5-114">The location the script came from.</span></span>  
  
 `result`  
 <span data-ttu-id="b88d5-115">スクリプトコードを表す関数。</span><span class="sxs-lookup"><span data-stu-id="b88d5-115">A function representing the script code.</span></span>  
  
## <span data-ttu-id="b88d5-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="b88d5-116">Return Value</span></span>  
 <span data-ttu-id="b88d5-117">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="b88d5-117">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="b88d5-118">注釈</span><span class="sxs-lookup"><span data-stu-id="b88d5-118">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b88d5-119">この API は、ストアアプリではまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="b88d5-119">This API is not yet available for Store apps.</span></span>  
  
 <span data-ttu-id="b88d5-120">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="b88d5-120">Requires an active script context.</span></span>  
  
 <span data-ttu-id="b88d5-121">ランタイムは、バッファーから作成されたすべての関数のすべてのインスタンスがガベージコレクションされるまで、バッファーを保持します。</span><span class="sxs-lookup"><span data-stu-id="b88d5-121">The runtime will hold on to the buffer until all instances of any functions created from     the buffer are garbage collected.</span></span>  <span data-ttu-id="b88d5-122">次に、scriptUnloadCallback を呼び出して、安全に解放できることを呼び出し元に通知します。</span><span class="sxs-lookup"><span data-stu-id="b88d5-122">It will then call scriptUnloadCallback to inform the     caller that it is safe to release.</span></span>  
  
## <span data-ttu-id="b88d5-123">要件</span><span class="sxs-lookup"><span data-stu-id="b88d5-123">Requirements</span></span>  
 <span data-ttu-id="b88d5-124">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="b88d5-124">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="b88d5-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="b88d5-125">See Also</span></span>  
 [<span data-ttu-id="b88d5-126">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="b88d5-126">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)