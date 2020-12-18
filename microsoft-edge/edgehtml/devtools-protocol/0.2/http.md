---
description: Microsoft Edge DevTools Protocol Version 0.2 は、次の HTTP エンドポイントをサポートしています。
title: Microsoft Edge DevTools プロトコル バージョン 0.2 HTTP エンドポイント (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a0e100cee6a73d688b9b74a9b38d1dd37722428f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234786"
---
# <span data-ttu-id="d2c8c-103">Microsoft Edge DevTools プロトコル バージョン 0.2 HTTP エンドポイント (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="d2c8c-103">Microsoft Edge DevTools Protocol Version 0.2 HTTP Endpoints (EdgeHTML)</span></span>  

> [!NOTE]
> <span data-ttu-id="d2c8c-104">Microsoft Edge DevTools プロトコルのバージョン 0.2 は [、Windows 10 October 2018 Update]() 以降の [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) ビルドでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="d2c8c-104">Version 0.2 of the Microsoft Edge DevTools Protocol works only on the [Windows 10 October 2018 Update]() and later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) builds.</span></span>

<span data-ttu-id="d2c8c-105">**DevTools Protocol 0.2** は、次の HTTP エンドポイントをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d2c8c-105">**DevTools Protocol 0.2** supports the following HTTP endpoints.</span></span> <span data-ttu-id="d2c8c-106">ブラウザー[コンテンツ プロセスへの接続](../index.md#using-the-protocol)の詳細についてはプロトコルの使用を参照[](domains/index.md)してください。また、完全な Web ソケット ベースの devtools プロトコル API については、「ドメイン」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2c8c-106">See [using the protocol](../index.md#using-the-protocol) for more on connecting to a browser content process and the [Domains](domains/index.md) documentation for the full web sockets-based devtools protocol API.</span></span>

## <span data-ttu-id="d2c8c-107">/json/version</span><span class="sxs-lookup"><span data-stu-id="d2c8c-107">/json/version</span></span>
<span data-ttu-id="d2c8c-108">ホスト コンピューターのブラウザーと、それがサポートする DevTools プロトコルのバージョンに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d2c8c-108">Provides information on the host machine's browser and which version of the DevTools Protocol it supports.</span></span>

**<span data-ttu-id="d2c8c-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d2c8c-109">Parameters</span></span>**

*<span data-ttu-id="d2c8c-110">なし</span><span class="sxs-lookup"><span data-stu-id="d2c8c-110">None</span></span>*

**<span data-ttu-id="d2c8c-111">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="d2c8c-111">Return object</span></span>**

```json
{
    "Browser":"Edge/18.17763",
    "Protocol-Version":"0.2",
    "User-Agent":"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/64.0.3282.140 Safari/537.36 Edge/18.17763"
}
```

## <span data-ttu-id="d2c8c-112">/json/protocol</span><span class="sxs-lookup"><span data-stu-id="d2c8c-112">/json/protocol</span></span>

<span data-ttu-id="d2c8c-113">JSON としてシリアル化されたプロトコル API サーフェス全体を提供します。</span><span class="sxs-lookup"><span data-stu-id="d2c8c-113">Provides the entire protocol API surface serialized as JSON.</span></span>

**<span data-ttu-id="d2c8c-114">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d2c8c-114">Parameters</span></span>**

*<span data-ttu-id="d2c8c-115">なし</span><span class="sxs-lookup"><span data-stu-id="d2c8c-115">None</span></span>*

**<span data-ttu-id="d2c8c-116">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="d2c8c-116">Return object</span></span>**

<span data-ttu-id="d2c8c-117">プロトコルの現在のバージョンで使用可能な API サーフェスを表す JSON オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d2c8c-117">JSON object which represents the available API surface for current version of the protocol.</span></span>

## <span data-ttu-id="d2c8c-118">/json/list</span><span class="sxs-lookup"><span data-stu-id="d2c8c-118">/json/list</span></span>

<span data-ttu-id="d2c8c-119">デバッグ対象のページ ターゲットの候補リストを提供します。</span><span class="sxs-lookup"><span data-stu-id="d2c8c-119">Provides a candidate list of page targets for debugging.</span></span>

**<span data-ttu-id="d2c8c-120">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d2c8c-120">Parameters</span></span>**

*<span data-ttu-id="d2c8c-121">なし</span><span class="sxs-lookup"><span data-stu-id="d2c8c-121">None</span></span>*

**<span data-ttu-id="d2c8c-122">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="d2c8c-122">Return object</span></span>**

```json
[{
    "id":"000001F5-87EE-4D55-0091-C4C08A1F30C8",
    "title":"Microsoft Edge Developer website - Microsoft Edge Development",
    "type":"Page",
    "url":"https://developer.microsoft.com/microsoft-edge/",
    "webSocketDebuggerUrl":"ws://localhost:9222/target/000001F5-87EE-4D55-0091-C4C08A1F30C8"
}, … ]
```

## <span data-ttu-id="d2c8c-123">/json/close</span><span class="sxs-lookup"><span data-stu-id="d2c8c-123">/json/close</span></span>

<span data-ttu-id="d2c8c-124">ターゲット プロセスを終了します (Microsoft Edge でページ タブを閉じるなど)。</span><span class="sxs-lookup"><span data-stu-id="d2c8c-124">Closes down the target process (e.g., in Microsoft Edge, closes the page tab.)</span></span>

**<span data-ttu-id="d2c8c-125">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d2c8c-125">Parameters</span></span>**

<span data-ttu-id="d2c8c-126">ターゲット ID</span><span class="sxs-lookup"><span data-stu-id="d2c8c-126">Target ID</span></span> 

**<span data-ttu-id="d2c8c-127">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="d2c8c-127">Return object</span></span>**

```
String("Target is closing")
```
