---
description: シリアル化されたスクリプトを実行します。 必要な場合にのみ、スクリプトソースの遅延読み込み機能を提供します。
title: JsRunSerializedScriptWithCallback 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 0608d778-f65b-4dc5-a745-364aac57ef59
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 84a74d3c1aa68469dfe2fe42fdee685faa4c358c
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752221"
---
# <span data-ttu-id="be7c4-104">JsRunSerializedScriptWithCallback 関数</span><span class="sxs-lookup"><span data-stu-id="be7c4-104">JsRunSerializedScriptWithCallback Function</span></span>
<span data-ttu-id="be7c4-105">シリアル化されたスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="be7c4-105">Runs a serialized script.</span></span> <span data-ttu-id="be7c4-106">必要な場合にのみ、スクリプトソースの遅延読み込み機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="be7c4-106">Provides the ability to lazy load the script source only if/when it is needed.</span></span>  
  
## <span data-ttu-id="be7c4-107">構文</span><span class="sxs-lookup"><span data-stu-id="be7c4-107">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsRunSerializedScriptWithCallback(  
  _In_ JsSerializedScriptLoadSourceCallback scriptLoadCallback,  
  _In_ JsSerializedScriptUnloadCallback scriptUnloadCallback,  
  _In_ BYTE *buffer,  
  _In_ JsSourceContext sourceContext,  
  _In_z_ const wchar_t *sourceUrl,  
  _Out_opt_ JsValueRef *result  
);  
  
```  
  
#### <span data-ttu-id="be7c4-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="be7c4-108">Parameters</span></span>  
 `scriptLoadCallback`  
 <span data-ttu-id="be7c4-109">スクリプトのソースコードを読み込む必要があるときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="be7c4-109">Callback called when the source code of the script needs to be loaded.</span></span>  
  
 `scriptUnloadCallback`  
 <span data-ttu-id="be7c4-110">シリアル化されたスクリプトとソースコードが不要になったときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="be7c4-110">Callback called when the serialized script and source code are no longer needed.</span></span>  
  
 `buffer`  
 <span data-ttu-id="be7c4-111">シリアル化されたスクリプト。</span><span class="sxs-lookup"><span data-stu-id="be7c4-111">The serialized script.</span></span>  
  
 `sourceContext`  
 <span data-ttu-id="be7c4-112">デバッグ可能なスクリプトコンテキストによって使用できるスクリプトを識別する cookie。</span><span class="sxs-lookup"><span data-stu-id="be7c4-112">A cookie identifying the script that can be used by debuggable script contexts.</span></span>     <span data-ttu-id="be7c4-113">このコンテキストは、scriptLoadCallback と scriptUnloadCallback に渡されます。</span><span class="sxs-lookup"><span data-stu-id="be7c4-113">This context will passed into scriptLoadCallback and scriptUnloadCallback.</span></span>  
  
 `sourceUrl`  
 <span data-ttu-id="be7c4-114">スクリプトの取得元の場所。</span><span class="sxs-lookup"><span data-stu-id="be7c4-114">The location the script came from.</span></span>  
  
 `result`  
 <span data-ttu-id="be7c4-115">スクリプトを実行した結果 (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="be7c4-115">The result of running the script, if any.</span></span> <span data-ttu-id="be7c4-116">このパラメーターは null にすることができます。</span><span class="sxs-lookup"><span data-stu-id="be7c4-116">This parameter can be null.</span></span>  
  
## <span data-ttu-id="be7c4-117">戻り値</span><span class="sxs-lookup"><span data-stu-id="be7c4-117">Return Value</span></span>  
 <span data-ttu-id="be7c4-118">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="be7c4-118">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="be7c4-119">注釈</span><span class="sxs-lookup"><span data-stu-id="be7c4-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be7c4-120">この API は、ストアアプリではまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="be7c4-120">This API is not yet available for Store apps.</span></span>  
  
 <span data-ttu-id="be7c4-121">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="be7c4-121">Requires an active script context.</span></span>  
  
 <span data-ttu-id="be7c4-122">ランタイムは、バッファーから作成されたすべての関数のすべてのインスタンスがガベージコレクションされるまで、バッファーを保持します。</span><span class="sxs-lookup"><span data-stu-id="be7c4-122">The runtime will hold on to the buffer until all instances of any functions created from     the buffer are garbage collected.</span></span>  <span data-ttu-id="be7c4-123">次に、scriptUnloadCallback を呼び出して、安全に解放できることを呼び出し元に通知します。</span><span class="sxs-lookup"><span data-stu-id="be7c4-123">It will then call scriptUnloadCallback to inform the     caller that it is safe to release.</span></span>  
  
## <span data-ttu-id="be7c4-124">要件</span><span class="sxs-lookup"><span data-stu-id="be7c4-124">Requirements</span></span>  
 <span data-ttu-id="be7c4-125">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="be7c4-125">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="be7c4-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="be7c4-126">See Also</span></span>  
 [<span data-ttu-id="be7c4-127">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="be7c4-127">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)