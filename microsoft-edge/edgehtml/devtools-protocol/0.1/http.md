---
description: Microsoft Edge DevTools Protocol Version 0.1 は、次の HTTP エンドポイントをサポートしています。
title: DevTools Protocol Version 0.1 HTTP エンドポイント (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5fe50122728304de137efdfb25ebed7274c55cee
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234422"
---
# <span data-ttu-id="bfc67-103">DevTools Protocol Version 0.1 HTTP エンドポイント (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="bfc67-103">DevTools Protocol Version 0.1 HTTP Endpoints (EdgeHTML)</span></span>  

> [!NOTE]
> <span data-ttu-id="bfc67-104">Microsoft Edge DevTools プロトコルは [、Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 以降の [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) ビルドでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="bfc67-104">The Microsoft Edge DevTools Protocol works only on [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) and later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) builds.</span></span>

<span data-ttu-id="bfc67-105">**DevTools Protocol 0.1 は、** 次の HTTP エンドポイントをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bfc67-105">**DevTools Protocol 0.1** supports the following HTTP endpoints.</span></span> <span data-ttu-id="bfc67-106">ブラウザー[コンテンツ プロセスへの接続](../index.md#using-the-protocol)の詳細については、プロトコルの使用と[](domains/index.md)、完全な Web ソケット ベースの devtools プロトコル API のドメインに関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfc67-106">See [using the protocol](../index.md#using-the-protocol) for more on connecting to a browser content process and the [Domains](domains/index.md) documentation for the full web sockets-based devtools protocol API.</span></span>

## <span data-ttu-id="bfc67-107">/json/version</span><span class="sxs-lookup"><span data-stu-id="bfc67-107">/json/version</span></span>
<span data-ttu-id="bfc67-108">ホスト コンピューターのブラウザーと、それがサポートする DevTools プロトコルのバージョンに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="bfc67-108">Provides information on the host machine's browser and which version of the DevTools Protocol it supports.</span></span>

**<span data-ttu-id="bfc67-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bfc67-109">Parameters</span></span>**

*<span data-ttu-id="bfc67-110">なし</span><span class="sxs-lookup"><span data-stu-id="bfc67-110">None</span></span>*

**<span data-ttu-id="bfc67-111">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="bfc67-111">Return object</span></span>**

```json
{
    "Browser":"Edge/17.17627",
    "Protocol-Version":"0.1",
    "User-Agent":"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/64.0.3282.140 Safari/537.36 Edge/17.17627"
}
```

## <span data-ttu-id="bfc67-112">/json/protocol</span><span class="sxs-lookup"><span data-stu-id="bfc67-112">/json/protocol</span></span>

<span data-ttu-id="bfc67-113">JSON としてシリアル化されたプロトコル API サーフェス全体を提供します。</span><span class="sxs-lookup"><span data-stu-id="bfc67-113">Provides the entire protocol API surface serialized as JSON.</span></span>

**<span data-ttu-id="bfc67-114">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bfc67-114">Parameters</span></span>**

*<span data-ttu-id="bfc67-115">なし</span><span class="sxs-lookup"><span data-stu-id="bfc67-115">None</span></span>*

**<span data-ttu-id="bfc67-116">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="bfc67-116">Return object</span></span>**

<span data-ttu-id="bfc67-117">プロトコルの現在のバージョンで使用可能な API サーフェスを表す JSON オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="bfc67-117">JSON object which represents the available API surface for current version of the protocol.</span></span>

## <span data-ttu-id="bfc67-118">/json/list</span><span class="sxs-lookup"><span data-stu-id="bfc67-118">/json/list</span></span>

<span data-ttu-id="bfc67-119">デバッグ対象のページ ターゲットの候補リストを提供します。</span><span class="sxs-lookup"><span data-stu-id="bfc67-119">Provides a candidate list of page targets for debugging.</span></span>

**<span data-ttu-id="bfc67-120">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bfc67-120">Parameters</span></span>**

*<span data-ttu-id="bfc67-121">なし</span><span class="sxs-lookup"><span data-stu-id="bfc67-121">None</span></span>*

**<span data-ttu-id="bfc67-122">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="bfc67-122">Return object</span></span>**

```json
[{
    "id":"000001F5-87EE-4D55-0091-C4C08A1F30C8",
    "title":"Microsoft Edge Developer website - Microsoft Edge Development",
    "type":"Page",
    "url":"https://developer.microsoft.com/microsoft-edge/",
    "webSocketDebuggerUrl":"ws://localhost:9222/target/000001F5-87EE-4D55-0091-C4C08A1F30C8"
}, … ]
```

## <span data-ttu-id="bfc67-123">/json/close</span><span class="sxs-lookup"><span data-stu-id="bfc67-123">/json/close</span></span>

<span data-ttu-id="bfc67-124">ターゲット プロセスを終了します (Microsoft Edge でページ タブを閉じるなど)。</span><span class="sxs-lookup"><span data-stu-id="bfc67-124">Closes down the target process (e.g., in Microsoft Edge, closes the page tab.)</span></span>

**<span data-ttu-id="bfc67-125">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bfc67-125">Parameters</span></span>**

<span data-ttu-id="bfc67-126">ターゲット ID</span><span class="sxs-lookup"><span data-stu-id="bfc67-126">Target ID</span></span> 

**<span data-ttu-id="bfc67-127">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="bfc67-127">Return object</span></span>**

```
String("Target is closing")
```
