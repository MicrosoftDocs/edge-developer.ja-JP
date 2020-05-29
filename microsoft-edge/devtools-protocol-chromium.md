---
description: Microsoft Edge DevTools プロトコルに更新する
title: Microsoft Edge DevTools プロトコル更新プログラム
author: zoherghadyali
ms.author: zoghadya
ms.date: 03/11/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: f1936a83f948dd17cc76139b7fd67fc73cd692d0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569634"
---
# <span data-ttu-id="2fbec-103">Microsoft Edge (Chromium) DevTools プロトコル</span><span class="sxs-lookup"><span data-stu-id="2fbec-103">Microsoft Edge (Chromium) DevTools Protocol</span></span>

<span data-ttu-id="2fbec-104">Microsoft Edge の基になっている web プラットフォーム (Microsoft Edge) で Chromium に移動しても、 [Microsoft edge (EdgeHTML) DevTools プロトコル](./devtools-protocol/index.md)は今後更新を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="2fbec-104">With the shift in the underlying web platform of Microsoft Edge to Chromium, the [Microsoft Edge (EdgeHTML) DevTools Protocol](./devtools-protocol/index.md) will not be receiving any further updates.</span></span> <span data-ttu-id="2fbec-105">Microsoft Edge (Chromium) DevTools プロトコルは、Chrome DevTools プロトコルの Api と一致します。</span><span class="sxs-lookup"><span data-stu-id="2fbec-105">The Microsoft Edge (Chromium) DevTools Protocol will match the APIs of the Chrome DevTools Protocol going forward.</span></span> 

<span data-ttu-id="2fbec-106">このようなドメインとメソッドのドキュメントについては、 [Chrome DevTools プロトコルビューアー](https://chromedevtools.github.io/devtools-protocol/tot/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fbec-106">You can find documentation on those domains and methods by referring to the [Chrome DevTools Protocol Viewer](https://chromedevtools.github.io/devtools-protocol/tot/).</span></span>

> [!NOTE]
> <span data-ttu-id="2fbec-107">`ms` [Microsoft Edge (EdgeHTML) devtools プロトコル](./devtools-protocol/index.md)でプレフィックスが付けられたメソッドは、Microsoft edge (Chromium) devtools プロトコルでサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="2fbec-107">Any methods that were prefixed with `ms` in the [Microsoft Edge (EdgeHTML) DevTools Protocol](./devtools-protocol/index.md) are no longer supported in the Microsoft Edge (Chromium) DevTools Protocol.</span></span>

## <span data-ttu-id="2fbec-108">DevTools プロトコルの使用</span><span class="sxs-lookup"><span data-stu-id="2fbec-108">Using the DevTools Protocol</span></span>

<span data-ttu-id="2fbec-109">Microsoft Edge (Chromium) の DevTools サーバーにカスタムツールクライアントをアタッチする方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2fbec-109">Here's how to attach a custom tooling client to the DevTools Server in Microsoft Edge (Chromium).</span></span>

1. <span data-ttu-id="2fbec-110">Microsoft Edge (Chromium) のすべてのインスタンスを閉じていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fbec-110">Ensure all instances of Microsoft Edge (Chromium) are closed.</span></span>

2. <span data-ttu-id="2fbec-111">リモートデバッグポートを使用して Microsoft Edge (Chromium) を起動します。</span><span class="sxs-lookup"><span data-stu-id="2fbec-111">Launch Microsoft Edge (Chromium) with the remote debugging port:</span></span>

    ```
    msedge.exe --remote-debugging-port=9222
    ```

3. <span data-ttu-id="2fbec-112">必要に応じて、個別のユーザープロファイルを使って別の Edge のインスタンスを開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="2fbec-112">Optionally, you can start a separate instance of Edge using a distinct user profile if desired:</span></span>

    ```
    msedge.exe --user-data-dir=<some directory>
    ```

4. <span data-ttu-id="2fbec-113">次に、HTTP エンドポイントを使用して、アタッチ可能な `list` ページターゲットの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="2fbec-113">Next, use the HTTP `list` endpoint to get a list of attachable page targets:</span></span>

    ```
    http://localhost:9222/json/list
    ```

5. <span data-ttu-id="2fbec-114">最後に、目的の `webSocketDebuggerUrl` ターゲットに接続してコマンドを実行するか、DevTools web ソケットサーバーからイベントメッセージを購読します。</span><span class="sxs-lookup"><span data-stu-id="2fbec-114">Finally, connect to the `webSocketDebuggerUrl` of the desired target and issue commands/subscribe to event messages through the DevTools web socket server.</span></span>

## <span data-ttu-id="2fbec-115">DevTools プロトコルの HTTP エンドポイント</span><span class="sxs-lookup"><span data-stu-id="2fbec-115">DevTools Protocol HTTP Endpoints</span></span>

<span data-ttu-id="2fbec-116">Microsoft Edge (Chromium) DevTools プロトコルでは、次の HTTP エンドポイントがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2fbec-116">The Microsoft Edge (Chromium) DevTools Protocol supports the following HTTP endpoints.</span></span>

## <span data-ttu-id="2fbec-117">/json/version</span><span class="sxs-lookup"><span data-stu-id="2fbec-117">/json/version</span></span>
<span data-ttu-id="2fbec-118">ホストコンピューターのブラウザーと、サポートされている DevTools プロトコルのバージョンについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2fbec-118">Provides information on the host machine's browser and which version of the DevTools Protocol it supports.</span></span>

**<span data-ttu-id="2fbec-119">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2fbec-119">Parameters</span></span>**

*<span data-ttu-id="2fbec-120">なし</span><span class="sxs-lookup"><span data-stu-id="2fbec-120">None</span></span>*

**<span data-ttu-id="2fbec-121">返されるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="2fbec-121">Return object</span></span>**

```json
{
   "Browser": "Edg/75.0.115.0",
   "Protocol-Version": "1.3",
   "User-Agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.115.0",
   "V8-Version": "7.5.98",
   "WebKit-Version": "537.36 (@68a98f73c7d0f766fb5a013ea7f8dbb41089bc1b)",
   "webSocketDebuggerUrl": "ws://localhost:9222/devtools/browser/a9d0e8cf-476a-4a89-bba9-0fc27ce691cd"
}
```

## <span data-ttu-id="2fbec-122">/json/protocol</span><span class="sxs-lookup"><span data-stu-id="2fbec-122">/json/protocol</span></span>

<span data-ttu-id="2fbec-123">JSON としてシリアル化されたプロトコル API サーフェス全体を提供します。</span><span class="sxs-lookup"><span data-stu-id="2fbec-123">Provides the entire protocol API surface serialized as JSON.</span></span>

**<span data-ttu-id="2fbec-124">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2fbec-124">Parameters</span></span>**

*<span data-ttu-id="2fbec-125">なし</span><span class="sxs-lookup"><span data-stu-id="2fbec-125">None</span></span>*

**<span data-ttu-id="2fbec-126">返されるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="2fbec-126">Return object</span></span>**

<span data-ttu-id="2fbec-127">プロトコルの現在のバージョンで利用できる API サーフェスを表す JSON オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2fbec-127">JSON object which represents the available API surface for current version of the protocol.</span></span>

## <span data-ttu-id="2fbec-128">/json/list</span><span class="sxs-lookup"><span data-stu-id="2fbec-128">/json/list</span></span>

<span data-ttu-id="2fbec-129">デバッグ用のページターゲットの候補リストを提供します。</span><span class="sxs-lookup"><span data-stu-id="2fbec-129">Provides a candidate list of page targets for debugging.</span></span>

**<span data-ttu-id="2fbec-130">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2fbec-130">Parameters</span></span>**

*<span data-ttu-id="2fbec-131">なし</span><span class="sxs-lookup"><span data-stu-id="2fbec-131">None</span></span>*

**<span data-ttu-id="2fbec-132">返されるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="2fbec-132">Return object</span></span>**

```json
[{
   "description": "",
   "devtoolsFrontendUrl": "/devtools/inspector.html?ws=localhost:9222/devtools/page/AB07C11A262D1EC8634EB12E2DCA4989",
   "id": "AB07C11A262D1EC8634EB12E2DCA4989",
   "title": "localhost:9222/json/protocol",
   "type": "page",
   "url": "http://localhost:9222/json/list",
   "webSocketDebuggerUrl": "ws://localhost:9222/devtools/page/AB07C11A262D1EC8634EB12E2DCA4989"
}, … ]
```

## <span data-ttu-id="2fbec-133">/json/close</span><span class="sxs-lookup"><span data-stu-id="2fbec-133">/json/close</span></span>

<span data-ttu-id="2fbec-134">ターゲットプロセスを終了します (たとえば、Microsoft Edge (Chromium) の場合は、[ページ] タブを閉じます)。</span><span class="sxs-lookup"><span data-stu-id="2fbec-134">Closes down the target process (e.g., in Microsoft Edge (Chromium), closes the page tab.)</span></span>

**<span data-ttu-id="2fbec-135">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2fbec-135">Parameters</span></span>**

<span data-ttu-id="2fbec-136">ターゲット ID</span><span class="sxs-lookup"><span data-stu-id="2fbec-136">Target ID</span></span> 

**<span data-ttu-id="2fbec-137">返されるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="2fbec-137">Return object</span></span>**

```
String(“Target is closing”)
```

## <span data-ttu-id="2fbec-138">Microsoft Edge 向けリモートツール (ベータ版)</span><span class="sxs-lookup"><span data-stu-id="2fbec-138">Remote Tools for Microsoft Edge (Beta)</span></span>

<span data-ttu-id="2fbec-139">Microsoft [Store](https://www.microsoft.com/store/apps/windows)から[Microsoft Edge (ベータ) 版のリモートツール](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)をインストールできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2fbec-139">You are now able to install the [Remote Tools for Microsoft Edge (Beta)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) from the [Microsoft Store](https://www.microsoft.com/store/apps/windows).</span></span> <span data-ttu-id="2fbec-140">このアプリでは、開発用コンピューターから Windows 10 デバイスで実行されている Microsoft Edge (Chromium) をリモートでデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="2fbec-140">This app enables you to remotely debug Microsoft Edge (Chromium) running on a Windows 10 device from your development machine.</span></span>

<span data-ttu-id="2fbec-141">Windows 10 デバイスをセットアップして開発用コンピューターから接続する方法については、[このチュートリアル](./devtools-guide-chromium/remote-debugging/windows.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2fbec-141">To learn how to set up your Windows 10 device and connect to it from your development machine, check out [this tutorial](./devtools-guide-chromium/remote-debugging/windows.md).</span></span>

<span data-ttu-id="2fbec-142">[Microsoft edge (ベータ版) のリモートツール](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)では、デバッグ対象の Windows 10 デバイスで実行されている microsoft edge と通信するための、同じ microsoft Edge (Chromium) Devtools プロトコルを[devtools](./devtools-guide-chromium.md)として使用しています。</span><span class="sxs-lookup"><span data-stu-id="2fbec-142">The [Remote Tools for Microsoft Edge (Beta)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) uses the same Microsoft Edge (Chromium) DevTools Protocol as the [DevTools](./devtools-guide-chromium.md) to communicate with Microsoft Edge running on the Windows 10 device you want to debug.</span></span> <span data-ttu-id="2fbec-143">このアプリで `/msedge/` `pid` は、プロトコルを呼び出す前に、先頭にプロセス ID () が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="2fbec-143">This app just prepends `/msedge/` and a process ID (`pid`) before each call to the protocol.</span></span> <span data-ttu-id="2fbec-144">次の HTTP エンドポイントがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2fbec-144">It supports the following HTTP endpoints.</span></span>

### <span data-ttu-id="2fbec-145">/msedge/json/list</span><span class="sxs-lookup"><span data-stu-id="2fbec-145">/msedge/json/list</span></span>

<span data-ttu-id="2fbec-146">`msedge.exe`デバッグ用の Windows 10 デバイス上のすべてのプロセス ( [pwas](./progressive-web-apps-chromium/index.md)およびすべての Microsoft Edge のすべてのタブを含む) の候補リストを提供します。</span><span class="sxs-lookup"><span data-stu-id="2fbec-146">Provides a candidate list of all `msedge.exe` processes (including [PWAs](./progressive-web-apps-chromium/index.md) and all tabs in all instances of Microsoft Edge) on the Windows 10 device for debugging.</span></span>

**<span data-ttu-id="2fbec-147">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2fbec-147">Parameters</span></span>**

*<span data-ttu-id="2fbec-148">なし</span><span class="sxs-lookup"><span data-stu-id="2fbec-148">None</span></span>*

**<span data-ttu-id="2fbec-149">返されるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="2fbec-149">Return object</span></span>**

```json
[{
   "description": "",
    "devtoolsFrontendUrl": "http://172.17.75.195:80/msedge/7264/devtools/inspector.html?ws=172.17.75.195:80/msedge/7264/devtools/page/ED4FFDB4529723A0FAFCBDB9B45851BB",
    "faviconUrl": "https://docs.microsoft.com/favicon.ico",
    "id": "ED4FFDB4529723A0FAFCBDB9B45851BB",
    "title": "Get Started with Remote Debugging Windows 10 Devices - Microsoft Edge Development | Microsoft Docs",
    "type": "page",
    "url": "https://docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium/remote-debugging/windows",
    "webSocketDebuggerUrl": "ws://172.17.75.195:80/msedge/7264/devtools/page/ED4FFDB4529723A0FAFCBDB9B45851BB",
    "browserProcessId": 7264
}, … ]
```

### <span data-ttu-id="2fbec-150">/msedge/</span><span class="sxs-lookup"><span data-stu-id="2fbec-150">/msedge/</span></span>

<span data-ttu-id="2fbec-151">[/Msedge/json/list](#msedgejsonlist)と同等の機能。</span><span class="sxs-lookup"><span data-stu-id="2fbec-151">Functionally equivalent to [/msedge/json/list](#msedgejsonlist).</span></span> 

### <span data-ttu-id="2fbec-152">/msedge/[pid]/json/list</span><span class="sxs-lookup"><span data-stu-id="2fbec-152">/msedge/[pid]/json/list</span></span>

<span data-ttu-id="2fbec-153">デバッグ用に指定されたものと一致する、Microsoft Edge インスタンスのページターゲットの候補リストを提供 `[pid]` します。</span><span class="sxs-lookup"><span data-stu-id="2fbec-153">Provides a candidate list of page targets for the Microsoft Edge instance that matches the provided `[pid]` for debugging.</span></span>

**<span data-ttu-id="2fbec-154">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2fbec-154">Parameters</span></span>**

*<span data-ttu-id="2fbec-155">なし</span><span class="sxs-lookup"><span data-stu-id="2fbec-155">None</span></span>*

**<span data-ttu-id="2fbec-156">返されるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="2fbec-156">Return object</span></span>**

```json
[{
    "description": "",
    "devtoolsFrontendUrl": "http://172.17.75.195:80/msedge/7264/devtools/inspector.html?ws=172.17.75.195:80/msedge/7264/devtools/page/ED4FFDB4529723A0FAFCBDB9B45851BB",
    "faviconUrl": "https://docs.microsoft.com/favicon.ico",
    "id": "ED4FFDB4529723A0FAFCBDB9B45851BB",
    "title": "Get Started with Remote Debugging Windows 10 Devices - Microsoft Edge Development | Microsoft Docs",
    "type": "page",
    "url": "https://docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium/remote-debugging/windows",
    "webSocketDebuggerUrl": "ws://172.17.75.195:80/msedge/7264/devtools/page/ED4FFDB4529723A0FAFCBDB9B45851BB"
}, … ]
```

### <span data-ttu-id="2fbec-157">/msedge/[pid]/json/version</span><span class="sxs-lookup"><span data-stu-id="2fbec-157">/msedge/[pid]/json/version</span></span>

<span data-ttu-id="2fbec-158">提供されている、およびサポートされている `[pid]` DevTools プロトコルのバージョンと一致する Microsoft Edge インスタンスに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2fbec-158">Provides information about the Microsoft Edge instance that matches the provided `[pid]` and which version of the DevTools Protocol it supports.</span></span>

**<span data-ttu-id="2fbec-159">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2fbec-159">Parameters</span></span>**

*<span data-ttu-id="2fbec-160">なし</span><span class="sxs-lookup"><span data-stu-id="2fbec-160">None</span></span>*

**<span data-ttu-id="2fbec-161">返されるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="2fbec-161">Return object</span></span>**

```json
{
    "Browser": "Edg/82.0.452.0",
    "Protocol-Version": "1.3",
    "User-Agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/82.0.4080.0 Safari/537.36 Edg/82.0.452.0",
    "V8-Version": "8.2.263",
    "WebKit-Version": "537.36 (@fe0232051787ca94ac8edfc0084c3488b7d9bdb2)",
    "webSocketDebuggerUrl": "172.17.75.195:80/msedge/7264/devtools/browser/7a67c8c4-138b-48e3-bfe0-cb7af34d559a"
}
```

### <span data-ttu-id="2fbec-162">/msedge/[pid]/json/protocol/</span><span class="sxs-lookup"><span data-stu-id="2fbec-162">/msedge/[pid]/json/protocol/</span></span>

<span data-ttu-id="2fbec-163">指定されたものと一致する Microsoft Edge インスタンスの JSON としてシリアル化されたプロトコル API サーフェス全体を提供し `[pid]` ます。</span><span class="sxs-lookup"><span data-stu-id="2fbec-163">Provides the entire protocol API surface serialized as JSON for the Microsoft Edge instance that matches the provided `[pid]`.</span></span>

**<span data-ttu-id="2fbec-164">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2fbec-164">Parameters</span></span>**

*<span data-ttu-id="2fbec-165">なし</span><span class="sxs-lookup"><span data-stu-id="2fbec-165">None</span></span>*

**<span data-ttu-id="2fbec-166">返されるオブジェクト</span><span class="sxs-lookup"><span data-stu-id="2fbec-166">Return object</span></span>**

<span data-ttu-id="2fbec-167">指定されたものと一致する Microsoft Edge インスタンスが使用しているプロトコルのバージョンで利用可能な API サーフェスを表す JSON オブジェクト `[pid]` 。</span><span class="sxs-lookup"><span data-stu-id="2fbec-167">JSON object which represents the available API surface for the version of the protocol that the Microsoft Edge instance that matches the provided `[pid]` is using.</span></span>
