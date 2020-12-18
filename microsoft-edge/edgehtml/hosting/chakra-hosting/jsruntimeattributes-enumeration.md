---
description: 'ランタイムの属性。 '
title: JsRuntimeAttributes 列挙 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsRuntimeAttributes
helpviewer_keywords:
- JsRuntimeAttributes enumeration
ms.assetid: f76d82e9-a695-4d6a-96c1-b3a4d27fed68
caps.latest.revision: 14
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: bbc5341c3214d9796278d334507e284989ff45dd
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234650"
---
# <span data-ttu-id="ec057-103">JsRuntimeAttributes 列挙</span><span class="sxs-lookup"><span data-stu-id="ec057-103">JsRuntimeAttributes Enumeration</span></span>

<span data-ttu-id="ec057-104">ランタイムの属性。</span><span class="sxs-lookup"><span data-stu-id="ec057-104">Attributes of a runtime.</span></span>  
  
## <span data-ttu-id="ec057-105">構文</span><span class="sxs-lookup"><span data-stu-id="ec057-105">Syntax</span></span>  
  
```cpp  
enum JsRuntimeAttributes;  
```  
  
## <span data-ttu-id="ec057-106">Members</span><span class="sxs-lookup"><span data-stu-id="ec057-106">Members</span></span>  
  
### <span data-ttu-id="ec057-107">値</span><span class="sxs-lookup"><span data-stu-id="ec057-107">Values</span></span>  
  
|<span data-ttu-id="ec057-108">名前</span><span class="sxs-lookup"><span data-stu-id="ec057-108">Name</span></span>|<span data-ttu-id="ec057-109">説明</span><span class="sxs-lookup"><span data-stu-id="ec057-109">Description</span></span>|  
|----------|-----------------|  
|`JsRuntimeAttributeAllowScriptInterrupt`|<span data-ttu-id="ec057-110">ランタイムは、信頼性の高いスクリプト中断をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec057-110">The runtime should support reliable script interruption.</span></span> <span data-ttu-id="ec057-111">これにより、ランタイムがスクリプト割り込み要求をチェックする場所の数が増加しますが、実行時のパフォーマンスは小さくてすみません。</span><span class="sxs-lookup"><span data-stu-id="ec057-111">This increases the number of places where the runtime will check for a script interrupt request at the cost of a small amount of runtime performance.</span></span>|  
|`JsRuntimeAttributeDisableBackgroundWork`|<span data-ttu-id="ec057-112">ランタイムは、バックグラウンド スレッドで (ガベージ コレクションなどの) 作業を一切実行しません。</span><span class="sxs-lookup"><span data-stu-id="ec057-112">The runtime will not do any work (such as garbage collection) on background threads.</span></span>|  
|`JsRuntimeAttributeDisableEval`|<span data-ttu-id="ec057-113">使用 `eval` またはコンストラクター `function` は例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="ec057-113">Using `eval` or `function` constructor will throw an exception.</span></span>|  
|`JsRuntimeAttributeDisableNativeCodeGeneration`|<span data-ttu-id="ec057-114">ランタイムはネイティブ コードを生成しない。</span><span class="sxs-lookup"><span data-stu-id="ec057-114">Runtime will not generate native code.</span></span>|  
|`JsRuntimeAttributeEnableExperimentalFeatures`|<span data-ttu-id="ec057-115">ランタイムは、試験的な機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ec057-115">Runtime will enable all experimental features.</span></span>|  
|`JsRuntimeAttributeEnableIdleProcessing`|<span data-ttu-id="ec057-116">ホストが呼び `JsIdle` 出すので、アイドル処理が有効になります。</span><span class="sxs-lookup"><span data-stu-id="ec057-116">Host will call `JsIdle`, so enable idle processing.</span></span> <span data-ttu-id="ec057-117">そうしないと、ランタイムはメモリを少し積極的に管理します。</span><span class="sxs-lookup"><span data-stu-id="ec057-117">Otherwise, the runtime will manage memory slightly more aggressively.</span></span>|  
|`JsRuntimeAttributeDispatchSetExceptionsToDebugger`|<span data-ttu-id="ec057-118">また `JsSetException` 、呼び出しは例外をスクリプト デバッガーにディスパッチし (その場合)、デバッガーが例外でブレークする機会を与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec057-118">Calling `JsSetException` will also dispatch the exception to the script debugger (if any) giving the debugger a chance to break on the exception.</span></span>|  
|`JsRuntimeAttributeNone`|<span data-ttu-id="ec057-119">特別な属性はありません。</span><span class="sxs-lookup"><span data-stu-id="ec057-119">No special attributes.</span></span>|  
  
## <span data-ttu-id="ec057-120">要件</span><span class="sxs-lookup"><span data-stu-id="ec057-120">Requirements</span></span>  
 <span data-ttu-id="ec057-121">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="ec057-121">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ec057-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec057-122">See Also</span></span>  
 [<span data-ttu-id="ec057-123">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="ec057-123">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
