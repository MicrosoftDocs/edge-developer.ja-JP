---
description: Microsoft Edge DevTools プロトコルバージョン0.1 では、次の HTTP エンドポイントがサポートされています。
title: DevTools プロトコルバージョン 0.1 HTTP エンドポイント (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: a9d40772b8175790c034ee67236c4887d0831785
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882871"
---
# <span data-ttu-id="6b349-103">DevTools プロトコルバージョン 0.1 HTTP エンドポイント (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="6b349-103">DevTools Protocol Version 0.1 HTTP Endpoints (EdgeHTML)</span></span>  

> [!NOTE]
> <span data-ttu-id="6b349-104">Microsoft Edge の DevTools プロトコルは、 [windows 10 年4月の2018更新プログラム](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97)以降の[windows Insider Preview](https://insider.windows.com/en-us/getting-started/)ビルドでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="6b349-104">The Microsoft Edge DevTools Protocol works only on [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) and later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) builds.</span></span>

<span data-ttu-id="6b349-105">**Devtools プロトコル 0.1**では、次の HTTP エンドポイントがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6b349-105">**DevTools Protocol 0.1** supports the following HTTP endpoints.</span></span> <span data-ttu-id="6b349-106">ブラウザコンテンツ処理への接続に関する詳細については、「web sockets ベースの devtools プロトコル API 用の[ドメイン](domains/index.md)[ドキュメント」を](../index.md#using-the-protocol)参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b349-106">See [using the protocol](../index.md#using-the-protocol) for more on connecting to a browser content process and the [Domains](domains/index.md) documentation for the full web sockets-based devtools protocol API.</span></span>

## <span data-ttu-id="6b349-107">/json/version</span><span class="sxs-lookup"><span data-stu-id="6b349-107">/json/version</span></span>
<span data-ttu-id="6b349-108">ホストコンピューターのブラウザーと、サポートされている DevTools プロトコルのバージョンについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6b349-108">Provides information on the host machine's browser and which version of the DevTools Protocol it supports.</span></span>

**<span data-ttu-id="6b349-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6b349-109">Parameters</span></span>**

*<span data-ttu-id="6b349-110">なし</span><span class="sxs-lookup"><span data-stu-id="6b349-110">None</span></span>*

**<span data-ttu-id="6b349-111">返されるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="6b349-111">Return object</span></span>**

```json
{
    "Browser":"Edge/17.17627",
    "Protocol-Version":"0.1",
    "User-Agent":"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/64.0.3282.140 Safari/537.36 Edge/17.17627"
}
```

## <span data-ttu-id="6b349-112">/json/protocol</span><span class="sxs-lookup"><span data-stu-id="6b349-112">/json/protocol</span></span>

<span data-ttu-id="6b349-113">JSON としてシリアル化されたプロトコル API サーフェス全体を提供します。</span><span class="sxs-lookup"><span data-stu-id="6b349-113">Provides the entire protocol API surface serialized as JSON.</span></span>

**<span data-ttu-id="6b349-114">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6b349-114">Parameters</span></span>**

*<span data-ttu-id="6b349-115">なし</span><span class="sxs-lookup"><span data-stu-id="6b349-115">None</span></span>*

**<span data-ttu-id="6b349-116">返されるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="6b349-116">Return object</span></span>**

<span data-ttu-id="6b349-117">プロトコルの現在のバージョンで利用できる API サーフェスを表す JSON オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6b349-117">JSON object which represents the available API surface for current version of the protocol.</span></span>

## <span data-ttu-id="6b349-118">/json/list</span><span class="sxs-lookup"><span data-stu-id="6b349-118">/json/list</span></span>

<span data-ttu-id="6b349-119">デバッグ用のページターゲットの候補リストを提供します。</span><span class="sxs-lookup"><span data-stu-id="6b349-119">Provides a candidate list of page targets for debugging.</span></span>

**<span data-ttu-id="6b349-120">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6b349-120">Parameters</span></span>**

*<span data-ttu-id="6b349-121">なし</span><span class="sxs-lookup"><span data-stu-id="6b349-121">None</span></span>*

**<span data-ttu-id="6b349-122">返されるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="6b349-122">Return object</span></span>**

```json
[{
    "id":"000001F5-87EE-4D55-0091-C4C08A1F30C8",
    "title":"Microsoft Edge Developer website - Microsoft Edge Development",
    "type":"Page",
    "url":"https://developer.microsoft.com/microsoft-edge/",
    "webSocketDebuggerUrl":"ws://localhost:9222/target/000001F5-87EE-4D55-0091-C4C08A1F30C8"
}, … ]
```

## <span data-ttu-id="6b349-123">/json/close</span><span class="sxs-lookup"><span data-stu-id="6b349-123">/json/close</span></span>

<span data-ttu-id="6b349-124">ターゲットプロセスを終了します (例: Microsoft Edge では、[ページ] タブを閉じます)。</span><span class="sxs-lookup"><span data-stu-id="6b349-124">Closes down the target process (e.g., in Microsoft Edge, closes the page tab.)</span></span>

**<span data-ttu-id="6b349-125">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6b349-125">Parameters</span></span>**

<span data-ttu-id="6b349-126">ターゲット ID</span><span class="sxs-lookup"><span data-stu-id="6b349-126">Target ID</span></span> 

**<span data-ttu-id="6b349-127">返されるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="6b349-127">Return object</span></span>**

```
String("Target is closing")
```
