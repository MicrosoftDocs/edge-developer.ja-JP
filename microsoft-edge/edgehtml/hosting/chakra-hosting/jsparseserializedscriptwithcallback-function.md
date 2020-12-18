---
description: シリアル化されたスクリプトを解析し、スクリプトを表す関数を返します。 必要な場合にのみスクリプト ソースを遅延読み込む機能を提供します。
title: JsParseSerializedScriptWithCallback 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 0a93ecfb-4b82-4a85-b24c-6816db2332ea
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b145f01a5c3459100d8402beae63b7cff55db7b8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234854"
---
# <span data-ttu-id="d24d1-104">JsParseSerializedScriptWithCallback 関数</span><span class="sxs-lookup"><span data-stu-id="d24d1-104">JsParseSerializedScriptWithCallback Function</span></span>

<span data-ttu-id="d24d1-105">シリアル化されたスクリプトを解析し、スクリプトを表す関数を返します。</span><span class="sxs-lookup"><span data-stu-id="d24d1-105">Parses a serialized script and returns a function representing the script.</span></span> <span data-ttu-id="d24d1-106">必要な場合にのみスクリプト ソースを遅延読み込む機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="d24d1-106">Provides the ability to lazy load the script source only if/when it is needed.</span></span>  
  
## <span data-ttu-id="d24d1-107">構文</span><span class="sxs-lookup"><span data-stu-id="d24d1-107">Syntax</span></span>  
  
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
  
#### <span data-ttu-id="d24d1-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d24d1-108">Parameters</span></span>  
 `scriptLoadCallback`  
 <span data-ttu-id="d24d1-109">スクリプトのソース コードを読み込む必要があるときに呼び出されるコールバック。</span><span class="sxs-lookup"><span data-stu-id="d24d1-109">Callback called when the source code of the script needs to be loaded.</span></span>  
  
 `scriptUnloadCallback`  
 <span data-ttu-id="d24d1-110">シリアル化されたスクリプトとソース コードが不要になったときに呼び出されるコールバック。</span><span class="sxs-lookup"><span data-stu-id="d24d1-110">Callback called when the serialized script and source code are no longer needed.</span></span>  
  
 `buffer`  
 <span data-ttu-id="d24d1-111">シリアル化されたスクリプト。</span><span class="sxs-lookup"><span data-stu-id="d24d1-111">The serialized script.</span></span>  
  
 `sourceContext`  
 <span data-ttu-id="d24d1-112">デバッグ可能なスクリプト コンテキストで使用できるスクリプトを識別する Cookie。</span><span class="sxs-lookup"><span data-stu-id="d24d1-112">A cookie identifying the script that can be used by debuggable script contexts.</span></span>     <span data-ttu-id="d24d1-113">このコンテキストは、scriptLoadCallback と scriptUnloadCallback に渡されます。</span><span class="sxs-lookup"><span data-stu-id="d24d1-113">This context will passed into scriptLoadCallback and scriptUnloadCallback.</span></span>  
  
 `sourceUrl`  
 <span data-ttu-id="d24d1-114">スクリプトの作成場所。</span><span class="sxs-lookup"><span data-stu-id="d24d1-114">The location the script came from.</span></span>  
  
 `result`  
 <span data-ttu-id="d24d1-115">スクリプト コードを表す関数。</span><span class="sxs-lookup"><span data-stu-id="d24d1-115">A function representing the script code.</span></span>  
  
## <span data-ttu-id="d24d1-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="d24d1-116">Return Value</span></span>  
 <span data-ttu-id="d24d1-117">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="d24d1-117">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="d24d1-118">注釈</span><span class="sxs-lookup"><span data-stu-id="d24d1-118">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d24d1-119">この API は、ストア アプリではまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="d24d1-119">This API is not yet available for Store apps.</span></span>  
  
 <span data-ttu-id="d24d1-120">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="d24d1-120">Requires an active script context.</span></span>  
  
 <span data-ttu-id="d24d1-121">バッファーから作成された関数のすべてのインスタンスがガベージ コレクションされるまで、ランタイムはバッファーを保持します。</span><span class="sxs-lookup"><span data-stu-id="d24d1-121">The runtime will hold on to the buffer until all instances of any functions created from     the buffer are garbage collected.</span></span>  <span data-ttu-id="d24d1-122">その後、scriptUnloadCallback を呼び出して、解放しても安全だと呼び出し元に通知します。</span><span class="sxs-lookup"><span data-stu-id="d24d1-122">It will then call scriptUnloadCallback to inform the     caller that it is safe to release.</span></span>  
  
## <span data-ttu-id="d24d1-123">要件</span><span class="sxs-lookup"><span data-stu-id="d24d1-123">Requirements</span></span>  
 <span data-ttu-id="d24d1-124">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="d24d1-124">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="d24d1-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="d24d1-125">See Also</span></span>  
 [<span data-ttu-id="d24d1-126">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="d24d1-126">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
