---
description: Microsoft Edge DevTools プロトコルバージョン0.1 でサポートされているドメインの参照の一覧です。
title: DevTools プロトコルのドメイン-DevTools Protocol バージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: de816e2b07838ba1b6151967ff7b8751789c60ea
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882948"
---
# <span data-ttu-id="1dac2-103">DevTools プロトコルのドメイン-DevTools Protocol バージョン 0.1 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="1dac2-103">DevTools Protocol Domains - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  

## [<span data-ttu-id="1dac2-104">デバッガー</span><span class="sxs-lookup"><span data-stu-id="1dac2-104">Debugger</span></span>](debugger.md)  

<span data-ttu-id="1dac2-105">デバッガードメインは、JavaScript のデバッグ機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="1dac2-105">Debugger domain exposes JavaScript debugging capabilities.</span></span> <span data-ttu-id="1dac2-106">これにより、ブレークポイントの設定と削除、実行のステップ実行、スタックトレースの調査などを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1dac2-106">It allows setting and removing breakpoints, stepping through execution, exploring stack traces, etc.</span></span>
## [<span data-ttu-id="1dac2-107">Page</span><span class="sxs-lookup"><span data-stu-id="1dac2-107">Page</span></span>](page.md)
<span data-ttu-id="1dac2-108">検査されたページに関連するアクションとイベントは、ページドメインに属しています。</span><span class="sxs-lookup"><span data-stu-id="1dac2-108">Actions and events related to the inspected page belong to the page domain.</span></span>
## [<span data-ttu-id="1dac2-109">ランタイム</span><span class="sxs-lookup"><span data-stu-id="1dac2-109">Runtime</span></span>](runtime.md)
<span data-ttu-id="1dac2-110">ランタイムドメインは、リモートの評価とミラーオブジェクトによって JavaScript ランタイムを公開します。</span><span class="sxs-lookup"><span data-stu-id="1dac2-110">Runtime domain exposes JavaScript runtime by means of remote evaluation and mirror objects.</span></span> <span data-ttu-id="1dac2-111">評価結果は、オブジェクトの型、文字列表現、およびさらにオブジェクト参照に使用できる一意の識別子を公開するミラーオブジェクトとして返されます。</span><span class="sxs-lookup"><span data-stu-id="1dac2-111">Evaluation results are returned as mirror object that expose object type, string representation and unique identifier that can be used for further object reference.</span></span> <span data-ttu-id="1dac2-112">元のオブジェクトは、明示的に解放されない限り、メモリ内に保持されます。</span><span class="sxs-lookup"><span data-stu-id="1dac2-112">Original objects are maintained in memory unless they are either explicitly released.</span></span>
## [<span data-ttu-id="1dac2-113">スキーマ</span><span class="sxs-lookup"><span data-stu-id="1dac2-113">Schema</span></span>](schema.md)
<span data-ttu-id="1dac2-114">プロトコルスキーマに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="1dac2-114">Provides information about the protocol schema.</span></span>