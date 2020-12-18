---
description: Microsoft Edge DevTools プロトコル バージョン 0.1 でサポートされているドメインの参照リスト。
title: DevTools プロトコル ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 0f152c4418d77be55f5921d76410b51c1d1e2957
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234428"
---
# <span data-ttu-id="ebcf7-103">DevTools プロトコル ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="ebcf7-103">DevTools Protocol Domains - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  

## [<span data-ttu-id="ebcf7-104">デバッガー</span><span class="sxs-lookup"><span data-stu-id="ebcf7-104">Debugger</span></span>](debugger.md)  

<span data-ttu-id="ebcf7-105">デバッガー ドメインは、JavaScript デバッグ機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="ebcf7-105">Debugger domain exposes JavaScript debugging capabilities.</span></span> <span data-ttu-id="ebcf7-106">ブレークポイントの設定と削除、実行のステップ実行、スタック トレースの探索などを行えます。</span><span class="sxs-lookup"><span data-stu-id="ebcf7-106">It allows setting and removing breakpoints, stepping through execution, exploring stack traces, etc.</span></span>
## [<span data-ttu-id="ebcf7-107">Page</span><span class="sxs-lookup"><span data-stu-id="ebcf7-107">Page</span></span>](page.md)
<span data-ttu-id="ebcf7-108">検査されたページに関連するアクションとイベントは、ページ ドメインに属しています。</span><span class="sxs-lookup"><span data-stu-id="ebcf7-108">Actions and events related to the inspected page belong to the page domain.</span></span>
## [<span data-ttu-id="ebcf7-109">ランタイム</span><span class="sxs-lookup"><span data-stu-id="ebcf7-109">Runtime</span></span>](runtime.md)
<span data-ttu-id="ebcf7-110">ランタイム ドメインは、リモート評価オブジェクトとミラー オブジェクトを使用して JavaScript ランタイムを公開します。</span><span class="sxs-lookup"><span data-stu-id="ebcf7-110">Runtime domain exposes JavaScript runtime by means of remote evaluation and mirror objects.</span></span> <span data-ttu-id="ebcf7-111">評価結果は、オブジェクトの種類、文字列表現、および一意の識別子を公開するミラー オブジェクトとして返され、さらにオブジェクト参照に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebcf7-111">Evaluation results are returned as mirror object that expose object type, string representation and unique identifier that can be used for further object reference.</span></span> <span data-ttu-id="ebcf7-112">元のオブジェクトは、明示的に解放されていない限り、メモリ内に保持されます。</span><span class="sxs-lookup"><span data-stu-id="ebcf7-112">Original objects are maintained in memory unless they are either explicitly released.</span></span>
## [<span data-ttu-id="ebcf7-113">スキーマ</span><span class="sxs-lookup"><span data-stu-id="ebcf7-113">Schema</span></span>](schema.md)
<span data-ttu-id="ebcf7-114">プロトコル スキーマに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ebcf7-114">Provides information about the protocol schema.</span></span>
