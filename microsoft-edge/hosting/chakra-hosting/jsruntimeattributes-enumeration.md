---
description: 'ランタイムの属性。 '
title: JsRuntimeAttributes 列挙 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsRuntimeAttributes
helpviewer_keywords:
- JsRuntimeAttributes enumeration
ms.assetid: f76d82e9-a695-4d6a-96c1-b3a4d27fed68
caps.latest.revision: 14
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9b8f6788f1de4988e3936701cfc742a564c92cfd
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570392"
---
# <span data-ttu-id="62b8f-103">JsRuntimeAttributes 列挙</span><span class="sxs-lookup"><span data-stu-id="62b8f-103">JsRuntimeAttributes Enumeration</span></span>
<span data-ttu-id="62b8f-104">ランタイムの属性。</span><span class="sxs-lookup"><span data-stu-id="62b8f-104">Attributes of a runtime.</span></span>  
  
## <span data-ttu-id="62b8f-105">構文</span><span class="sxs-lookup"><span data-stu-id="62b8f-105">Syntax</span></span>  
  
```cpp  
enum JsRuntimeAttributes;  
```  
  
## <span data-ttu-id="62b8f-106">Members</span><span class="sxs-lookup"><span data-stu-id="62b8f-106">Members</span></span>  
  
### <span data-ttu-id="62b8f-107">値</span><span class="sxs-lookup"><span data-stu-id="62b8f-107">Values</span></span>  
  
|<span data-ttu-id="62b8f-108">名前</span><span class="sxs-lookup"><span data-stu-id="62b8f-108">Name</span></span>|<span data-ttu-id="62b8f-109">説明</span><span class="sxs-lookup"><span data-stu-id="62b8f-109">Description</span></span>|  
|----------|-----------------|  
|`JsRuntimeAttributeAllowScriptInterrupt`|<span data-ttu-id="62b8f-110">ランタイムは、信頼性の高いスクリプトの中断をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="62b8f-110">The runtime should support reliable script interruption.</span></span> <span data-ttu-id="62b8f-111">これにより、実行時のパフォーマンスがわずかな場合に、実行時にスクリプト割り込み要求がチェックされる場所の数が増えます。</span><span class="sxs-lookup"><span data-stu-id="62b8f-111">This increases the number of places where the runtime will check for a script interrupt request at the cost of a small amount of runtime performance.</span></span>|  
|`JsRuntimeAttributeDisableBackgroundWork`|<span data-ttu-id="62b8f-112">ランタイムは、バックグラウンドスレッドでの作業 (ガベージコレクションなど) を実行しません。</span><span class="sxs-lookup"><span data-stu-id="62b8f-112">The runtime will not do any work (such as garbage collection) on background threads.</span></span>|  
|`JsRuntimeAttributeDisableEval`|<span data-ttu-id="62b8f-113">Using `eval` または `function` コンストラクターで例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="62b8f-113">Using `eval` or `function` constructor will throw an exception.</span></span>|  
|`JsRuntimeAttributeDisableNativeCodeGeneration`|<span data-ttu-id="62b8f-114">実行時にネイティブコードは生成されません。</span><span class="sxs-lookup"><span data-stu-id="62b8f-114">Runtime will not generate native code.</span></span>|  
|`JsRuntimeAttributeEnableExperimentalFeatures`|<span data-ttu-id="62b8f-115">Runtime は、すべての実験的な機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="62b8f-115">Runtime will enable all experimental features.</span></span>|  
|`JsRuntimeAttributeEnableIdleProcessing`|<span data-ttu-id="62b8f-116">ホストが通話 `JsIdle` を発信し、アイドル処理を有効にします。</span><span class="sxs-lookup"><span data-stu-id="62b8f-116">Host will call `JsIdle`, so enable idle processing.</span></span> <span data-ttu-id="62b8f-117">そうしないと、ランタイムはメモリをやや積極的に管理します。</span><span class="sxs-lookup"><span data-stu-id="62b8f-117">Otherwise, the runtime will manage memory slightly more aggressively.</span></span>|  
|`JsRuntimeAttributeDispatchSetExceptionsToDebugger`|<span data-ttu-id="62b8f-118">呼び出しによって、例外が発生した `JsSetException` 場合にデバッガーに例外が発生する可能性があります (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="62b8f-118">Calling `JsSetException` will also dispatch the exception to the script debugger (if any) giving the debugger a chance to break on the exception.</span></span>|  
|`JsRuntimeAttributeNone`|<span data-ttu-id="62b8f-119">特別な属性はありません。</span><span class="sxs-lookup"><span data-stu-id="62b8f-119">No special attributes.</span></span>|  
  
## <span data-ttu-id="62b8f-120">要件</span><span class="sxs-lookup"><span data-stu-id="62b8f-120">Requirements</span></span>  
 <span data-ttu-id="62b8f-121">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="62b8f-121">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="62b8f-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="62b8f-122">See Also</span></span>  
 [<span data-ttu-id="62b8f-123">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="62b8f-123">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)