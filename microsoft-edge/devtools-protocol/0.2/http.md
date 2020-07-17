---
description: Microsoft Edge DevTools プロトコルバージョン0.2 では、次の HTTP エンドポイントがサポートされています。
title: Microsoft Edge DevTools プロトコルバージョン 0.2 HTTP エンドポイント (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: eb5b29e4d8149f511d8a7cbca3da72391a13e449
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882859"
---
# <span data-ttu-id="bf9c0-103">Microsoft Edge DevTools プロトコルバージョン 0.2 HTTP エンドポイント (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="bf9c0-103">Microsoft Edge DevTools Protocol Version 0.2 HTTP Endpoints (EdgeHTML)</span></span>  

> [!NOTE]
> <span data-ttu-id="bf9c0-104">Microsoft Edge DevTools プロトコルのバージョン0.2 は、 [windows 10 年 2018 10 月の更新プログラム]()以降の[windows Insider Preview](https://insider.windows.com/en-us/getting-started/)ビルドでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="bf9c0-104">Version 0.2 of the Microsoft Edge DevTools Protocol works only on the [Windows 10 October 2018 Update]() and later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) builds.</span></span>

<span data-ttu-id="bf9c0-105">**Devtools プロトコル 0.2**では、次の HTTP エンドポイントがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bf9c0-105">**DevTools Protocol 0.2** supports the following HTTP endpoints.</span></span> <span data-ttu-id="bf9c0-106">ブラウザコンテンツ処理への接続に関する詳細については、「web sockets ベースの devtools プロトコル API 用の[ドメイン](domains/index.md)[ドキュメント」を](../index.md#using-the-protocol)参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf9c0-106">See [using the protocol](../index.md#using-the-protocol) for more on connecting to a browser content process and the [Domains](domains/index.md) documentation for the full web sockets-based devtools protocol API.</span></span>

## <span data-ttu-id="bf9c0-107">/json/version</span><span class="sxs-lookup"><span data-stu-id="bf9c0-107">/json/version</span></span>
<span data-ttu-id="bf9c0-108">ホストコンピューターのブラウザーと、サポートされている DevTools プロトコルのバージョンについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bf9c0-108">Provides information on the host machine's browser and which version of the DevTools Protocol it supports.</span></span>

**<span data-ttu-id="bf9c0-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bf9c0-109">Parameters</span></span>**

*<span data-ttu-id="bf9c0-110">なし</span><span class="sxs-lookup"><span data-stu-id="bf9c0-110">None</span></span>*

**<span data-ttu-id="bf9c0-111">返されるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="bf9c0-111">Return object</span></span>**

```json
{
    "Browser":"Edge/18.17763",
    "Protocol-Version":"0.2",
    "User-Agent":"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/64.0.3282.140 Safari/537.36 Edge/18.17763"
}
```

## <span data-ttu-id="bf9c0-112">/json/protocol</span><span class="sxs-lookup"><span data-stu-id="bf9c0-112">/json/protocol</span></span>

<span data-ttu-id="bf9c0-113">JSON としてシリアル化されたプロトコル API サーフェス全体を提供します。</span><span class="sxs-lookup"><span data-stu-id="bf9c0-113">Provides the entire protocol API surface serialized as JSON.</span></span>

**<span data-ttu-id="bf9c0-114">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bf9c0-114">Parameters</span></span>**

*<span data-ttu-id="bf9c0-115">なし</span><span class="sxs-lookup"><span data-stu-id="bf9c0-115">None</span></span>*

**<span data-ttu-id="bf9c0-116">返されるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="bf9c0-116">Return object</span></span>**

<span data-ttu-id="bf9c0-117">プロトコルの現在のバージョンで利用できる API サーフェスを表す JSON オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="bf9c0-117">JSON object which represents the available API surface for current version of the protocol.</span></span>

## <span data-ttu-id="bf9c0-118">/json/list</span><span class="sxs-lookup"><span data-stu-id="bf9c0-118">/json/list</span></span>

<span data-ttu-id="bf9c0-119">デバッグ用のページターゲットの候補リストを提供します。</span><span class="sxs-lookup"><span data-stu-id="bf9c0-119">Provides a candidate list of page targets for debugging.</span></span>

**<span data-ttu-id="bf9c0-120">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bf9c0-120">Parameters</span></span>**

*<span data-ttu-id="bf9c0-121">なし</span><span class="sxs-lookup"><span data-stu-id="bf9c0-121">None</span></span>*

**<span data-ttu-id="bf9c0-122">返されるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="bf9c0-122">Return object</span></span>**

```json
[{
    "id":"000001F5-87EE-4D55-0091-C4C08A1F30C8",
    "title":"Microsoft Edge Developer website - Microsoft Edge Development",
    "type":"Page",
    "url":"https://developer.microsoft.com/microsoft-edge/",
    "webSocketDebuggerUrl":"ws://localhost:9222/target/000001F5-87EE-4D55-0091-C4C08A1F30C8"
}, … ]
```

## <span data-ttu-id="bf9c0-123">/json/close</span><span class="sxs-lookup"><span data-stu-id="bf9c0-123">/json/close</span></span>

<span data-ttu-id="bf9c0-124">ターゲットプロセスを終了します (例: Microsoft Edge では、[ページ] タブを閉じます)。</span><span class="sxs-lookup"><span data-stu-id="bf9c0-124">Closes down the target process (e.g., in Microsoft Edge, closes the page tab.)</span></span>

**<span data-ttu-id="bf9c0-125">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bf9c0-125">Parameters</span></span>**

<span data-ttu-id="bf9c0-126">ターゲット ID</span><span class="sxs-lookup"><span data-stu-id="bf9c0-126">Target ID</span></span> 

**<span data-ttu-id="bf9c0-127">返されるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="bf9c0-127">Return object</span></span>**

```
String("Target is closing")
```
