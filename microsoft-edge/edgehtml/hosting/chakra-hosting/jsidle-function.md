---
description: 必要なアイドル処理を実行するランタイムに指示します。
title: JsIdle 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsIdle
helpviewer_keywords:
- JsIdle function
ms.assetid: 372d1c62-8e19-4886-aa33-364cabc09bba
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: ecba0aafb6b4dcccb4485c2956cae5ce4045355f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235039"
---
# <span data-ttu-id="f2b30-103">JsIdle 関数</span><span class="sxs-lookup"><span data-stu-id="f2b30-103">JsIdle Function</span></span>

<span data-ttu-id="f2b30-104">必要なアイドル処理を実行するランタイムに指示します。</span><span class="sxs-lookup"><span data-stu-id="f2b30-104">Tells the runtime to do any idle processing it need to do.</span></span>  
  
## <span data-ttu-id="f2b30-105">構文</span><span class="sxs-lookup"><span data-stu-id="f2b30-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsIdle(  
   _Out_opt_ unsigned int *nextIdleTick  
);  
```  
  
#### <span data-ttu-id="f2b30-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f2b30-106">Parameters</span></span>  
 `nextIdleTick`  
 <span data-ttu-id="f2b30-107">アイドル状態の作業が多い場合は、次のシステム ティックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2b30-107">The next system tick when there will be more idle work to do.</span></span> <span data-ttu-id="f2b30-108">null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f2b30-108">Can be null.</span></span> <span data-ttu-id="f2b30-109">今後のアイドル状態の作業がない場合は、ティックの最大数を返します。</span><span class="sxs-lookup"><span data-stu-id="f2b30-109">Returns the maximum number of ticks if there no upcoming idle work to do.</span></span>  
  
## <span data-ttu-id="f2b30-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="f2b30-110">Return Value</span></span>  
 <span data-ttu-id="f2b30-111">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="f2b30-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="f2b30-112">注釈</span><span class="sxs-lookup"><span data-stu-id="f2b30-112">Remarks</span></span>  
 <span data-ttu-id="f2b30-113">現在のランタイムでアイドル処理が有効になっている場合、呼び出しは、ホストがアイドル状態であり、ランタイムがメモリ クリーンアップ タスクを実行できると現在のランタイム `JsIdle` に通知します。</span><span class="sxs-lookup"><span data-stu-id="f2b30-113">If idle processing has been enabled for the current runtime, calling `JsIdle` will inform the current runtime that the host is idle and that the runtime can perform memory cleanup tasks.</span></span>  
  
 `JsIdle` <span data-ttu-id="f2b30-114">また、ランタイムが実行するアイドル状態の作業が増えるまで、システム ティックの数を返す場合があります。</span><span class="sxs-lookup"><span data-stu-id="f2b30-114">can also return the number of system ticks until there will be more idle work for the runtime to do.</span></span> <span data-ttu-id="f2b30-115">この `JsIdle` 数のティックが渡される前に呼び出す操作は機能しません。</span><span class="sxs-lookup"><span data-stu-id="f2b30-115">Calling `JsIdle` before this number of ticks has passed will do no work.</span></span>  
  
 <span data-ttu-id="f2b30-116">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="f2b30-116">Requires an active script context.</span></span>  
  
## <span data-ttu-id="f2b30-117">要件</span><span class="sxs-lookup"><span data-stu-id="f2b30-117">Requirements</span></span>  
 <span data-ttu-id="f2b30-118">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="f2b30-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="f2b30-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2b30-119">See Also</span></span>  
 [<span data-ttu-id="f2b30-120">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="f2b30-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
