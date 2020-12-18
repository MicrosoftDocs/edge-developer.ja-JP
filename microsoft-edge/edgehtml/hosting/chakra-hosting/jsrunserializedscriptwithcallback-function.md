---
description: シリアル化されたスクリプトを実行します。 必要な場合にのみスクリプト ソースを遅延読み込む機能を提供します。
title: JsRunSerializedScriptWithCallback 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 0608d778-f65b-4dc5-a745-364aac57ef59
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: ac9ac08357cd479f78e3500bc5eef151fb8e4e6c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235022"
---
# <span data-ttu-id="bb764-104">JsRunSerializedScriptWithCallback 関数</span><span class="sxs-lookup"><span data-stu-id="bb764-104">JsRunSerializedScriptWithCallback Function</span></span>

<span data-ttu-id="bb764-105">シリアル化されたスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="bb764-105">Runs a serialized script.</span></span> <span data-ttu-id="bb764-106">必要な場合にのみスクリプト ソースを遅延読み込む機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="bb764-106">Provides the ability to lazy load the script source only if/when it is needed.</span></span>  
  
## <span data-ttu-id="bb764-107">構文</span><span class="sxs-lookup"><span data-stu-id="bb764-107">Syntax</span></span>  
  
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
  
#### <span data-ttu-id="bb764-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bb764-108">Parameters</span></span>  
 `scriptLoadCallback`  
 <span data-ttu-id="bb764-109">スクリプトのソース コードを読み込む必要があるときに呼び出されるコールバック。</span><span class="sxs-lookup"><span data-stu-id="bb764-109">Callback called when the source code of the script needs to be loaded.</span></span>  
  
 `scriptUnloadCallback`  
 <span data-ttu-id="bb764-110">シリアル化されたスクリプトとソース コードが不要になったときに呼び出されるコールバック。</span><span class="sxs-lookup"><span data-stu-id="bb764-110">Callback called when the serialized script and source code are no longer needed.</span></span>  
  
 `buffer`  
 <span data-ttu-id="bb764-111">シリアル化されたスクリプト。</span><span class="sxs-lookup"><span data-stu-id="bb764-111">The serialized script.</span></span>  
  
 `sourceContext`  
 <span data-ttu-id="bb764-112">デバッグ可能なスクリプト コンテキストで使用できるスクリプトを識別する Cookie。</span><span class="sxs-lookup"><span data-stu-id="bb764-112">A cookie identifying the script that can be used by debuggable script contexts.</span></span>     <span data-ttu-id="bb764-113">このコンテキストは、scriptLoadCallback と scriptUnloadCallback に渡されます。</span><span class="sxs-lookup"><span data-stu-id="bb764-113">This context will passed into scriptLoadCallback and scriptUnloadCallback.</span></span>  
  
 `sourceUrl`  
 <span data-ttu-id="bb764-114">スクリプトの作成場所。</span><span class="sxs-lookup"><span data-stu-id="bb764-114">The location the script came from.</span></span>  
  
 `result`  
 <span data-ttu-id="bb764-115">スクリプトを実行した結果 (スクリプトがある場合)。</span><span class="sxs-lookup"><span data-stu-id="bb764-115">The result of running the script, if any.</span></span> <span data-ttu-id="bb764-116">このパラメーターは null に設定できます。</span><span class="sxs-lookup"><span data-stu-id="bb764-116">This parameter can be null.</span></span>  
  
## <span data-ttu-id="bb764-117">戻り値</span><span class="sxs-lookup"><span data-stu-id="bb764-117">Return Value</span></span>  
 <span data-ttu-id="bb764-118">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="bb764-118">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="bb764-119">注釈</span><span class="sxs-lookup"><span data-stu-id="bb764-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb764-120">この API は、ストア アプリではまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="bb764-120">This API is not yet available for Store apps.</span></span>  
  
 <span data-ttu-id="bb764-121">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="bb764-121">Requires an active script context.</span></span>  
  
 <span data-ttu-id="bb764-122">バッファーから作成された関数のすべてのインスタンスがガベージ コレクションされるまで、ランタイムはバッファーを保持します。</span><span class="sxs-lookup"><span data-stu-id="bb764-122">The runtime will hold on to the buffer until all instances of any functions created from     the buffer are garbage collected.</span></span>  <span data-ttu-id="bb764-123">その後、scriptUnloadCallback を呼び出して、解放しても安全だと呼び出し元に通知します。</span><span class="sxs-lookup"><span data-stu-id="bb764-123">It will then call scriptUnloadCallback to inform the     caller that it is safe to release.</span></span>  
  
## <span data-ttu-id="bb764-124">要件</span><span class="sxs-lookup"><span data-stu-id="bb764-124">Requirements</span></span>  
 <span data-ttu-id="bb764-125">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="bb764-125">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="bb764-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb764-126">See Also</span></span>  
 [<span data-ttu-id="bb764-127">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="bb764-127">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
