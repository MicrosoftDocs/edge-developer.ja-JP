---
description: Microsoft Edge DevTools プロトコルの更新
title: Microsoft Edge DevTools プロトコル更新プログラム
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/02/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: 15b13e2b93d1dbd013a82ea52b643071fa5b6f7e
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234832"
---
# <span data-ttu-id="dea08-103">Microsoft Edge (Chromium) DevTools プロトコルの概要</span><span class="sxs-lookup"><span data-stu-id="dea08-103">Microsoft Edge (Chromium) DevTools Protocol overview</span></span>  

<span data-ttu-id="dea08-104">Microsoft Edge の基礎となる Web プラットフォームが Chromium に移行すると [、Microsoft Edge (EdgeHTML) DevTools プロトコル](../edgehtml/devtools-protocol/index.md) はそれ以上の更新プログラムを受信しなくる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dea08-104">With the shift in the underlying web platform of Microsoft Edge to Chromium, the [Microsoft Edge (EdgeHTML) DevTools Protocol](../edgehtml/devtools-protocol/index.md) will not be receiving any further updates.</span></span>  <span data-ttu-id="dea08-105">Microsoft Edge \(Chromium\) DevTools プロトコルは、今後 Chrome DevTools プロトコルの API と一致します。</span><span class="sxs-lookup"><span data-stu-id="dea08-105">The Microsoft Edge \(Chromium\) DevTools Protocol will match the APIs of the Chrome DevTools Protocol going forward.</span></span>  

<span data-ttu-id="dea08-106">これらのドメインとメソッドに関するドキュメントは [、Chrome DevTools](https://chromedevtools.github.io/devtools-protocol/tot/)プロトコル ビューアーを参照して確認できます。</span><span class="sxs-lookup"><span data-stu-id="dea08-106">You can find documentation on those domains and methods by referring to the [Chrome DevTools Protocol Viewer](https://chromedevtools.github.io/devtools-protocol/tot/).</span></span>  

> [!NOTE]
> <span data-ttu-id="dea08-107">`ms` [Microsoft Edge (EdgeHTML) DevTools プロトコル](../edgehtml/devtools-protocol/index.md)でプレフィックスが付いたメソッドは、Microsoft Edge \(Chromium\) DevTools プロトコルではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="dea08-107">Any methods that were prefixed with `ms` in the [Microsoft Edge (EdgeHTML) DevTools Protocol](../edgehtml/devtools-protocol/index.md) are no longer supported in the Microsoft Edge \(Chromium\) DevTools Protocol.</span></span>  

## <span data-ttu-id="dea08-108">DevTools プロトコルの使用</span><span class="sxs-lookup"><span data-stu-id="dea08-108">Using the DevTools Protocol</span></span>  

<span data-ttu-id="dea08-109">Microsoft Edge \(Chromium\) の DevTools Server にカスタム ツール クライアントを接続する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dea08-109">Here's how to attach a custom tooling client to the DevTools Server in Microsoft Edge \(Chromium\).</span></span>  

1.  <span data-ttu-id="dea08-110">Microsoft Edge \(Chromium\) のすべてのインスタンスが閉じているか確認します。</span><span class="sxs-lookup"><span data-stu-id="dea08-110">Ensure all instances of Microsoft Edge \(Chromium\) are closed.</span></span>  
1.  <span data-ttu-id="dea08-111">リモート デバッグ ポートを使用して Microsoft Edge \(Chromium\) を起動します。</span><span class="sxs-lookup"><span data-stu-id="dea08-111">Launch Microsoft Edge \(Chromium\) with the remote debugging port:.</span></span> 
    
    ```shell
    msedge.exe --remote-debugging-port=9222
    ```  
    
1.  <span data-ttu-id="dea08-112">必要に応じて、個別のユーザー プロファイルを使用して Edge の個別のインスタンスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="dea08-112">Optionally, you can start a separate instance of Edge using a distinct user profile if desired.</span></span>  
    
    ```shell
    msedge.exe --user-data-dir=<some directory>
    ```  
    
1.  <span data-ttu-id="dea08-113">次に、HTTP エンドポイント `list` を使用して、接続可能なページ ターゲットの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="dea08-113">Next, use the HTTP `list` endpoint to get a list of attachable page targets.</span></span>  
    
    ```http
    http://localhost:9222/json/list
    ```  
    
1.  <span data-ttu-id="dea08-114">最後に、目的のターゲットの接続とコマンドの発行/DevTools Web ソケット サーバー経由でのイベント メッセージ `webSocketDebuggerUrl` のサブスクライブを行います。</span><span class="sxs-lookup"><span data-stu-id="dea08-114">Finally, connect to the `webSocketDebuggerUrl` of the desired target and issue commands/subscribe to event messages through the DevTools web socket server.</span></span>  

## <span data-ttu-id="dea08-115">DevTools プロトコル HTTP エンドポイント</span><span class="sxs-lookup"><span data-stu-id="dea08-115">DevTools Protocol HTTP Endpoints</span></span>  

<span data-ttu-id="dea08-116">Microsoft Edge \(Chromium\) DevTools プロトコルは、次の HTTP エンドポイントをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="dea08-116">The Microsoft Edge \(Chromium\) DevTools Protocol supports the following HTTP endpoints.</span></span>  

## <span data-ttu-id="dea08-117">/json/version</span><span class="sxs-lookup"><span data-stu-id="dea08-117">/json/version</span></span>  

<span data-ttu-id="dea08-118">ホスト コンピューターのブラウザーと、それがサポートする DevTools プロトコルのバージョンに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="dea08-118">Provides information on the browser of the host machine and which version of the DevTools Protocol it supports.</span></span>  

**<span data-ttu-id="dea08-119">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dea08-119">Parameters</span></span>**  

**<span data-ttu-id="dea08-120">なし</span><span class="sxs-lookup"><span data-stu-id="dea08-120">None</span></span>**  

**<span data-ttu-id="dea08-121">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="dea08-121">Return object</span></span>**  

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

## <span data-ttu-id="dea08-122">/json/protocol</span><span class="sxs-lookup"><span data-stu-id="dea08-122">/json/protocol</span></span>  

<span data-ttu-id="dea08-123">JSON としてシリアル化されたプロトコル API サーフェス全体を提供します。</span><span class="sxs-lookup"><span data-stu-id="dea08-123">Provides the entire protocol API surface serialized as JSON.</span></span>  

**<span data-ttu-id="dea08-124">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dea08-124">Parameters</span></span>**  

**<span data-ttu-id="dea08-125">なし</span><span class="sxs-lookup"><span data-stu-id="dea08-125">None</span></span>**  

**<span data-ttu-id="dea08-126">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="dea08-126">Return object</span></span>**  

<span data-ttu-id="dea08-127">プロトコルの現在のバージョンで使用可能な API サーフェスを表す JSON オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="dea08-127">JSON object which represents the available API surface for current version of the protocol.</span></span>  

## <span data-ttu-id="dea08-128">/json/list</span><span class="sxs-lookup"><span data-stu-id="dea08-128">/json/list</span></span>  

<span data-ttu-id="dea08-129">デバッグ対象のページ ターゲットの候補リストを提供します。</span><span class="sxs-lookup"><span data-stu-id="dea08-129">Provides a candidate list of page targets for debugging.</span></span>  

**<span data-ttu-id="dea08-130">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dea08-130">Parameters</span></span>**  

**<span data-ttu-id="dea08-131">なし</span><span class="sxs-lookup"><span data-stu-id="dea08-131">None</span></span>**  

**<span data-ttu-id="dea08-132">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="dea08-132">Return object</span></span>**  

```json
[{
   "description": "",
   "devtoolsFrontendUrl": "/devtools/inspector.html?ws=localhost:9222/devtools/page/AB07C11A262D1EC8634EB12E2DCA4989",
   "id": "AB07C11A262D1EC8634EB12E2DCA4989",
   "title": "localhost:9222/json/protocol",
   "type": "page",
   "url": "http://localhost:9222/json/list",
   "webSocketDebuggerUrl": "ws://localhost:9222/devtools/page/AB07C11A262D1EC8634EB12E2DCA4989"
}, ...  ]
```  

## <span data-ttu-id="dea08-133">/json/close</span><span class="sxs-lookup"><span data-stu-id="dea08-133">/json/close</span></span>  

<span data-ttu-id="dea08-134">ターゲット プロセス \(たとえば、Microsoft Edge \(Chromium\) を閉じ、ページ タブ\) を閉じます。</span><span class="sxs-lookup"><span data-stu-id="dea08-134">Closes down the target process \(for example, in Microsoft Edge \(Chromium\), closes the page tab\).</span></span>  

**<span data-ttu-id="dea08-135">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dea08-135">Parameters</span></span>**  

<span data-ttu-id="dea08-136">ターゲット ID</span><span class="sxs-lookup"><span data-stu-id="dea08-136">Target ID</span></span>  

**<span data-ttu-id="dea08-137">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="dea08-137">Return object</span></span>**  

```
String(“Target is closing”)
```  

## <span data-ttu-id="dea08-138">Microsoft Edge のリモート ツール (ベータ版)</span><span class="sxs-lookup"><span data-stu-id="dea08-138">Remote Tools for Microsoft Edge (Beta)</span></span>  

<span data-ttu-id="dea08-139">これで[、Microsoft Store](https://www.microsoft.com/store/apps/windows)から Microsoft Edge 用リモート ツール[(ベータ版)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="dea08-139">You are now able to install the [Remote Tools for Microsoft Edge (Beta)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) from the [Microsoft Store](https://www.microsoft.com/store/apps/windows).</span></span>  <span data-ttu-id="dea08-140">このアプリを使用すると、開発用コンピューターから Windows 10 デバイスで実行されている Microsoft Edge (Chromium) をリモートでデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="dea08-140">This app enables you to remotely debug Microsoft Edge (Chromium) running on a Windows 10 device from your development machine.</span></span>  

<span data-ttu-id="dea08-141">Windows 10 デバイスをセットアップし、開発用コンピューターからデバイスに接続する方法については [、「Windows 10](../devtools-guide-chromium/remote-debugging/windows.md)デバイスのリモート デバッグの開始」に移動します。</span><span class="sxs-lookup"><span data-stu-id="dea08-141">To learn how to set up your Windows 10 device and connect to it from your development machine, navigate to [Get Started with Remote Debugging Windows 10 Devices](../devtools-guide-chromium/remote-debugging/windows.md).</span></span>  

<span data-ttu-id="dea08-142">Microsoft Edge 用リモート ツール [(ベータ版)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) は [、DevTools](../devtools-guide-chromium/index.md) と同じ Microsoft Edge (Chromium) DevTools プロトコルを使用して、デバッグする Windows 10 デバイスで実行されている Microsoft Edge と通信します。</span><span class="sxs-lookup"><span data-stu-id="dea08-142">The [Remote Tools for Microsoft Edge (Beta)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) uses the same Microsoft Edge (Chromium) DevTools Protocol as the [DevTools](../devtools-guide-chromium/index.md) to communicate with Microsoft Edge running on the Windows 10 device you want to debug.</span></span>  <span data-ttu-id="dea08-143">このアプリでは、プロトコルの `/msedge/` 各呼び出しの前に先頭に追加され、プロセス ID ( ) `pid` が追加されます。</span><span class="sxs-lookup"><span data-stu-id="dea08-143">This app just prepends `/msedge/` and a process ID (`pid`) before each call to the protocol.</span></span>  <span data-ttu-id="dea08-144">次の HTTP エンドポイントをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="dea08-144">It supports the following HTTP endpoints.</span></span>  

### <span data-ttu-id="dea08-145">/msedge/json/list</span><span class="sxs-lookup"><span data-stu-id="dea08-145">/msedge/json/list</span></span>  

<span data-ttu-id="dea08-146">デバッグ用の Windows 10 デバイス上のすべてのプロセス \(PAS と Microsoft Edge のすべてのインスタンスのすべてのタブを含む) の候補リストを `msedge.exe` 提供します。 [](../progressive-web-apps-chromium/index.md)</span><span class="sxs-lookup"><span data-stu-id="dea08-146">Provides a candidate list of all `msedge.exe` processes \(including [PWAs](../progressive-web-apps-chromium/index.md) and all tabs in all instances of Microsoft Edge\) on the Windows 10 device for debugging.</span></span>  

**<span data-ttu-id="dea08-147">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dea08-147">Parameters</span></span>**  

**<span data-ttu-id="dea08-148">なし</span><span class="sxs-lookup"><span data-stu-id="dea08-148">None</span></span>**  

**<span data-ttu-id="dea08-149">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="dea08-149">Return object</span></span>**  

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
}, ...  ]
```  

### <span data-ttu-id="dea08-150">/msedge/</span><span class="sxs-lookup"><span data-stu-id="dea08-150">/msedge/</span></span>  

<span data-ttu-id="dea08-151">[/msedge/json/list と機能的に同等です](#msedgejsonlist)。</span><span class="sxs-lookup"><span data-stu-id="dea08-151">Functionally equivalent to [/msedge/json/list](#msedgejsonlist).</span></span>  

### <span data-ttu-id="dea08-152">/msedge/[pid]/json/list</span><span class="sxs-lookup"><span data-stu-id="dea08-152">/msedge/[pid]/json/list</span></span>  

<span data-ttu-id="dea08-153">提供されたデバッグに一致する Microsoft Edge インスタンスのページ ターゲットの候補リスト `[pid]` を提供します。</span><span class="sxs-lookup"><span data-stu-id="dea08-153">Provides a candidate list of page targets for the Microsoft Edge instance that matches the provided `[pid]` for debugging.</span></span>  

**<span data-ttu-id="dea08-154">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dea08-154">Parameters</span></span>**  

**<span data-ttu-id="dea08-155">なし</span><span class="sxs-lookup"><span data-stu-id="dea08-155">None</span></span>**  

**<span data-ttu-id="dea08-156">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="dea08-156">Return object</span></span>**  

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
}, ...  ]
```  

### <span data-ttu-id="dea08-157">/msedge/[pid]/json/version</span><span class="sxs-lookup"><span data-stu-id="dea08-157">/msedge/[pid]/json/version</span></span>  

<span data-ttu-id="dea08-158">指定されたバージョンと一致する Microsoft Edge インスタンスと、それがサポートする DevTools プロトコルのバージョンに関する `[pid]` 情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="dea08-158">Provides information about the Microsoft Edge instance that matches the provided `[pid]` and which version of the DevTools Protocol it supports.</span></span>  

**<span data-ttu-id="dea08-159">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dea08-159">Parameters</span></span>**  

**<span data-ttu-id="dea08-160">なし</span><span class="sxs-lookup"><span data-stu-id="dea08-160">None</span></span>**  

**<span data-ttu-id="dea08-161">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="dea08-161">Return object</span></span>**  

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

### <span data-ttu-id="dea08-162">/msedge/[pid]/json/protocol/</span><span class="sxs-lookup"><span data-stu-id="dea08-162">/msedge/[pid]/json/protocol/</span></span>  

<span data-ttu-id="dea08-163">指定されたオブジェクトに一致する Microsoft Edge インスタンスの JSON としてシリアル化されたプロトコル API サーフェス全体を提供します `[pid]` 。</span><span class="sxs-lookup"><span data-stu-id="dea08-163">Provides the entire protocol API surface serialized as JSON for the Microsoft Edge instance that matches the provided `[pid]`.</span></span>  

**<span data-ttu-id="dea08-164">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dea08-164">Parameters</span></span>**  

**<span data-ttu-id="dea08-165">なし</span><span class="sxs-lookup"><span data-stu-id="dea08-165">None</span></span>**  

**<span data-ttu-id="dea08-166">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="dea08-166">Return object</span></span>**  

<span data-ttu-id="dea08-167">指定されたバージョンと一致する Microsoft Edge インスタンスが使用しているプロトコルのバージョンで使用可能な API サーフェスを表す JSON `[pid]` オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="dea08-167">JSON object which represents the available API surface for the version of the protocol that the Microsoft Edge instance that matches the provided `[pid]` is using.</span></span>  
