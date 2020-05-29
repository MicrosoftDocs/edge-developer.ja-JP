---
description: Microsoft Edge DevTools プロトコルバージョン0.2 では、次の HTTP エンドポイントがサポートされています。
title: Microsoft Edge DevTools プロトコルバージョン 0.2 HTTP エンドポイント
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: cc3d0156d92ab479168e0b588ae2b7c9faa7e58f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569590"
---
# <span data-ttu-id="d5d66-103">DevTools プロトコルの HTTP エンドポイント</span><span class="sxs-lookup"><span data-stu-id="d5d66-103">DevTools Protocol HTTP Endpoints</span></span>

> [!NOTE]
> <span data-ttu-id="d5d66-104">Microsoft Edge DevTools プロトコルのバージョン0.2 は、 [windows 10 年 2018 10 月の更新プログラム]()以降の[windows Insider Preview](https://insider.windows.com/en-us/getting-started/)ビルドでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="d5d66-104">Version 0.2 of the Microsoft Edge DevTools Protocol works only on the [Windows 10 October 2018 Update]() and later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) builds.</span></span>

<span data-ttu-id="d5d66-105">**Devtools プロトコル 0.2**では、次の HTTP エンドポイントがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d5d66-105">**DevTools Protocol 0.2** supports the following HTTP endpoints.</span></span> <span data-ttu-id="d5d66-106">ブラウザコンテンツ処理への接続に関する詳細については、「web sockets ベースの devtools プロトコル API 用の[ドメイン](domains/index.md)[ドキュメント」を](../index.md#using-the-protocol)参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5d66-106">See [using the protocol](../index.md#using-the-protocol) for more on connecting to a browser content process and the [Domains](domains/index.md) documentation for the full web sockets-based devtools protocol API.</span></span>

## <span data-ttu-id="d5d66-107">/json/version</span><span class="sxs-lookup"><span data-stu-id="d5d66-107">/json/version</span></span>
<span data-ttu-id="d5d66-108">ホストコンピューターのブラウザーと、サポートされている DevTools プロトコルのバージョンについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d5d66-108">Provides information on the host machine's browser and which version of the DevTools Protocol it supports.</span></span>

**<span data-ttu-id="d5d66-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d5d66-109">Parameters</span></span>**

*<span data-ttu-id="d5d66-110">なし</span><span class="sxs-lookup"><span data-stu-id="d5d66-110">None</span></span>*

**<span data-ttu-id="d5d66-111">返されるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="d5d66-111">Return object</span></span>**

```json
{
    "Browser":"Edge/18.17763",
    "Protocol-Version":"0.2",
    "User-Agent":"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/64.0.3282.140 Safari/537.36 Edge/18.17763"
}
```

## <span data-ttu-id="d5d66-112">/json/protocol</span><span class="sxs-lookup"><span data-stu-id="d5d66-112">/json/protocol</span></span>

<span data-ttu-id="d5d66-113">JSON としてシリアル化されたプロトコル API サーフェス全体を提供します。</span><span class="sxs-lookup"><span data-stu-id="d5d66-113">Provides the entire protocol API surface serialized as JSON.</span></span>

**<span data-ttu-id="d5d66-114">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d5d66-114">Parameters</span></span>**

*<span data-ttu-id="d5d66-115">なし</span><span class="sxs-lookup"><span data-stu-id="d5d66-115">None</span></span>*

**<span data-ttu-id="d5d66-116">返されるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="d5d66-116">Return object</span></span>**

<span data-ttu-id="d5d66-117">プロトコルの現在のバージョンで利用できる API サーフェスを表す JSON オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5d66-117">JSON object which represents the available API surface for current version of the protocol.</span></span>

## <span data-ttu-id="d5d66-118">/json/list</span><span class="sxs-lookup"><span data-stu-id="d5d66-118">/json/list</span></span>

<span data-ttu-id="d5d66-119">デバッグ用のページターゲットの候補リストを提供します。</span><span class="sxs-lookup"><span data-stu-id="d5d66-119">Provides a candidate list of page targets for debugging.</span></span>

**<span data-ttu-id="d5d66-120">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d5d66-120">Parameters</span></span>**

*<span data-ttu-id="d5d66-121">なし</span><span class="sxs-lookup"><span data-stu-id="d5d66-121">None</span></span>*

**<span data-ttu-id="d5d66-122">返されるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="d5d66-122">Return object</span></span>**

```json
[{
    "id":"000001F5-87EE-4D55-0091-C4C08A1F30C8",
    "title":"Microsoft Edge Developer website - Microsoft Edge Development",
    "type":"Page",
    "url":"https://developer.microsoft.com/microsoft-edge/",
    "webSocketDebuggerUrl":"ws://localhost:9222/target/000001F5-87EE-4D55-0091-C4C08A1F30C8"
}, … ]
```

## <span data-ttu-id="d5d66-123">/json/close</span><span class="sxs-lookup"><span data-stu-id="d5d66-123">/json/close</span></span>

<span data-ttu-id="d5d66-124">ターゲットプロセスを終了します (例: Microsoft Edge では、[ページ] タブを閉じます)。</span><span class="sxs-lookup"><span data-stu-id="d5d66-124">Closes down the target process (e.g., in Microsoft Edge, closes the page tab.)</span></span>

**<span data-ttu-id="d5d66-125">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d5d66-125">Parameters</span></span>**

<span data-ttu-id="d5d66-126">ターゲット ID</span><span class="sxs-lookup"><span data-stu-id="d5d66-126">Target ID</span></span> 

**<span data-ttu-id="d5d66-127">返されるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="d5d66-127">Return object</span></span>**

```
String("Target is closing")
```
