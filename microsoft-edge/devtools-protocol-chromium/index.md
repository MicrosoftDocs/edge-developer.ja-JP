---
description: DevTools プロトコルMicrosoft Edge更新
title: Microsoft EdgeDevTools プロトコルの更新
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/06/2021
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: de7d6c39c09ba321f21b34e6e461ec030f09f6ad
ms.sourcegitcommit: 146072bf606b84e5145a48333abf9c6b892a12d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2021
ms.locfileid: "11480161"
---
# <a name="microsoft-edge-chromium-devtools-protocol-overview"></a><span data-ttu-id="65045-103">Microsoft Edge (Chromium) DevTools プロトコルの概要</span><span class="sxs-lookup"><span data-stu-id="65045-103">Microsoft Edge (Chromium) DevTools Protocol overview</span></span>  

<span data-ttu-id="65045-104">Microsoft Edge の基になる Web プラットフォームが Chromium に移行すると[、Microsoft Edge (EdgeHTML) DevTools プロトコル](/archive/microsoft-edge/legacy/developer/devtools-protocol/index)はそれ以上の更新プログラムを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="65045-104">With the shift in the underlying web platform of Microsoft Edge to Chromium, the [Microsoft Edge (EdgeHTML) DevTools Protocol](/archive/microsoft-edge/legacy/developer/devtools-protocol/index) will not be receiving any further updates.</span></span>  <span data-ttu-id="65045-105">Microsoft Edge \(Chromium\) DevTools プロトコルは、今後の Chrome DevTools プロトコルの API と一致します。</span><span class="sxs-lookup"><span data-stu-id="65045-105">The Microsoft Edge \(Chromium\) DevTools Protocol will match the APIs of the Chrome DevTools Protocol going forward.</span></span>  

<span data-ttu-id="65045-106">これらのドメインとメソッドについては [、Chrome DevTools](https://chromedevtools.github.io/devtools-protocol/tot)プロトコル ビューアーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="65045-106">You can find documentation on those domains and methods by referring to the [Chrome DevTools Protocol Viewer](https://chromedevtools.github.io/devtools-protocol/tot).</span></span>  

> [!NOTE]
> <span data-ttu-id="65045-107">`ms` [Microsoft Edge (EdgeHTML) DevTools プロトコル](/archive/microsoft-edge/legacy/developer/devtools-protocol/index)でプレフィックスが付いたメソッドは、Microsoft Edge \(Chromium\) DevTools プロトコルではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="65045-107">Any methods that were prefixed with `ms` in the [Microsoft Edge (EdgeHTML) DevTools Protocol](/archive/microsoft-edge/legacy/developer/devtools-protocol/index) are no longer supported in the Microsoft Edge \(Chromium\) DevTools Protocol.</span></span>  

## <a name="using-the-devtools-protocol"></a><span data-ttu-id="65045-108">DevTools プロトコルの使用</span><span class="sxs-lookup"><span data-stu-id="65045-108">Using the DevTools Protocol</span></span>  

<span data-ttu-id="65045-109">\(Chromium\) の DevTools Server にカスタム ツール クライアントを接続するMicrosoft Edge次に示します。</span><span class="sxs-lookup"><span data-stu-id="65045-109">Here's how to attach a custom tooling client to the DevTools Server in Microsoft Edge \(Chromium\).</span></span>  

1.  <span data-ttu-id="65045-110">\(Microsoft Edge\) のすべてのインスタンスがChromium閉じられます。</span><span class="sxs-lookup"><span data-stu-id="65045-110">Ensure all instances of Microsoft Edge \(Chromium\) are closed.</span></span>  
1.  <span data-ttu-id="65045-111">リモート デバッグ Microsoft Edge \(Chromium\) を起動します。</span><span class="sxs-lookup"><span data-stu-id="65045-111">Launch Microsoft Edge \(Chromium\) with the remote debugging port:.</span></span> 
    
    ```shell
    msedge.exe --remote-debugging-port=9222
    ```  
    
1.  <span data-ttu-id="65045-112">必要に応じて、個別のユーザー プロファイルを使用してエッジの別のインスタンスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="65045-112">Optionally, you can start a separate instance of Edge using a distinct user profile if desired.</span></span>  
    
    ```shell
    msedge.exe --user-data-dir=<some directory>
    ```  
    
1.  <span data-ttu-id="65045-113">次に、HTTP エンドポイント `list` を使用して、接続可能なページ ターゲットの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="65045-113">Next, use the HTTP `list` endpoint to get a list of attachable page targets.</span></span>  
    
    ```http
    http://localhost:9222/json/list
    ```  
    
1.  <span data-ttu-id="65045-114">最後に、目的のターゲットに接続し、コマンドを発行/DevTools Web ソケット サーバーを介してイベント メッセージ `webSocketDebuggerUrl` をサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="65045-114">Finally, connect to the `webSocketDebuggerUrl` of the desired target and issue commands/subscribe to event messages through the DevTools web socket server.</span></span>  

## <a name="devtools-protocol-http-endpoints"></a><span data-ttu-id="65045-115">DevTools プロトコル HTTP エンドポイント</span><span class="sxs-lookup"><span data-stu-id="65045-115">DevTools Protocol HTTP Endpoints</span></span>  

<span data-ttu-id="65045-116">Microsoft Edge \(Chromium\) DevTools プロトコルは、次の HTTP エンドポイントをサポートします。</span><span class="sxs-lookup"><span data-stu-id="65045-116">The Microsoft Edge \(Chromium\) DevTools Protocol supports the following HTTP endpoints.</span></span>  

## <a name="jsonversion"></a><span data-ttu-id="65045-117">/json/version</span><span class="sxs-lookup"><span data-stu-id="65045-117">/json/version</span></span>  

<span data-ttu-id="65045-118">ホスト コンピューターのブラウザーと、サポートする DevTools プロトコルのバージョンに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="65045-118">Provides information on the browser of the host machine and which version of the DevTools Protocol it supports.</span></span>  

**<span data-ttu-id="65045-119">パラメーター</span><span class="sxs-lookup"><span data-stu-id="65045-119">Parameters</span></span>**  

**<span data-ttu-id="65045-120">なし</span><span class="sxs-lookup"><span data-stu-id="65045-120">None</span></span>**  

**<span data-ttu-id="65045-121">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="65045-121">Return object</span></span>**  

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

## <a name="jsonprotocol"></a><span data-ttu-id="65045-122">/json/protocol</span><span class="sxs-lookup"><span data-stu-id="65045-122">/json/protocol</span></span>  

<span data-ttu-id="65045-123">JSON としてシリアル化されたプロトコル API サーフェス全体を提供します。</span><span class="sxs-lookup"><span data-stu-id="65045-123">Provides the entire protocol API surface serialized as JSON.</span></span>  

**<span data-ttu-id="65045-124">パラメーター</span><span class="sxs-lookup"><span data-stu-id="65045-124">Parameters</span></span>**  

**<span data-ttu-id="65045-125">なし</span><span class="sxs-lookup"><span data-stu-id="65045-125">None</span></span>**  

**<span data-ttu-id="65045-126">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="65045-126">Return object</span></span>**  

<span data-ttu-id="65045-127">現在のバージョンのプロトコルで使用可能な API サーフェスを表す JSON オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="65045-127">JSON object which represents the available API surface for current version of the protocol.</span></span>  

## <a name="jsonlist"></a><span data-ttu-id="65045-128">/json/list</span><span class="sxs-lookup"><span data-stu-id="65045-128">/json/list</span></span>  

<span data-ttu-id="65045-129">デバッグ用のページ ターゲットの候補リストを提供します。</span><span class="sxs-lookup"><span data-stu-id="65045-129">Provides a candidate list of page targets for debugging.</span></span>  

**<span data-ttu-id="65045-130">パラメーター</span><span class="sxs-lookup"><span data-stu-id="65045-130">Parameters</span></span>**  

**<span data-ttu-id="65045-131">なし</span><span class="sxs-lookup"><span data-stu-id="65045-131">None</span></span>**  

**<span data-ttu-id="65045-132">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="65045-132">Return object</span></span>**  

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

## <a name="jsonclose"></a><span data-ttu-id="65045-133">/json/close</span><span class="sxs-lookup"><span data-stu-id="65045-133">/json/close</span></span>  

<span data-ttu-id="65045-134">ターゲット プロセス \(たとえば、\(Microsoft Edge Chromium\) を閉じて、ページ タブ\を閉じます。</span><span class="sxs-lookup"><span data-stu-id="65045-134">Closes down the target process \(for example, in Microsoft Edge \(Chromium\), closes the page tab\).</span></span>  

**<span data-ttu-id="65045-135">パラメーター</span><span class="sxs-lookup"><span data-stu-id="65045-135">Parameters</span></span>**  

<span data-ttu-id="65045-136">ターゲット ID</span><span class="sxs-lookup"><span data-stu-id="65045-136">Target ID</span></span>  

**<span data-ttu-id="65045-137">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="65045-137">Return object</span></span>**  

```
String(“Target is closing”)
```  

## <a name="remote-tools-for-microsoft-edge-beta"></a><span data-ttu-id="65045-138">リモート ツール for Microsoft Edge (Beta)</span><span class="sxs-lookup"><span data-stu-id="65045-138">Remote Tools for Microsoft Edge (Beta)</span></span>  

<span data-ttu-id="65045-139">これで、リモート ツール[(Beta)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) Microsoft Edgeからインストール[Microsoft Store。](https://www.microsoft.com/store/apps/windows)</span><span class="sxs-lookup"><span data-stu-id="65045-139">You are now able to install the [Remote Tools for Microsoft Edge (Beta)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) from the [Microsoft Store](https://www.microsoft.com/store/apps/windows).</span></span>  <span data-ttu-id="65045-140">このアプリを使用すると、開発Microsoft EdgeデバイスChromium (Chromium Windows 10) をリモートでデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="65045-140">This app enables you to remotely debug Microsoft Edge (Chromium) running on a Windows 10 device from your development machine.</span></span>  

<span data-ttu-id="65045-141">開発マシンから Windows 10 デバイスをセットアップして接続する方法については、「リモート デバッグ はじめに デバイス」にWindows 10[します](../devtools-guide-chromium/remote-debugging/windows.md)。</span><span class="sxs-lookup"><span data-stu-id="65045-141">To learn how to set up your Windows 10 device and connect to it from your development machine, navigate to [Get Started with Remote Debugging Windows 10 Devices](../devtools-guide-chromium/remote-debugging/windows.md).</span></span>  

<span data-ttu-id="65045-142">[Microsoft Edge (Beta)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)のリモート ツールは、デバッグする Windows 10 デバイスで実行されている Microsoft Edge と通信するために、DevTools と同じ Microsoft Edge (Chromium) DevTools プロトコルを使用します。 [](../devtools-guide-chromium/index.md)</span><span class="sxs-lookup"><span data-stu-id="65045-142">The [Remote Tools for Microsoft Edge (Beta)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) uses the same Microsoft Edge (Chromium) DevTools Protocol as the [DevTools](../devtools-guide-chromium/index.md) to communicate with Microsoft Edge running on the Windows 10 device you want to debug.</span></span>  <span data-ttu-id="65045-143">このアプリは、プロトコルへの各呼び出しの前に、先頭とプロセス `/msedge/` ID ( `pid` ) を追加します。</span><span class="sxs-lookup"><span data-stu-id="65045-143">This app just prepends `/msedge/` and a process ID (`pid`) before each call to the protocol.</span></span>  <span data-ttu-id="65045-144">次の HTTP エンドポイントがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="65045-144">It supports the following HTTP endpoints.</span></span>  

### <a name="msedgejsonlist"></a><span data-ttu-id="65045-145">/msedge/json/list</span><span class="sxs-lookup"><span data-stu-id="65045-145">/msedge/json/list</span></span>  

<span data-ttu-id="65045-146">デバッグ用のデバイス上のすべてのプロセス `msedge.exe` [\(PWA](../progressive-web-apps-chromium/index.md)と Microsoft Edge\のすべてのインスタンスのすべてのタブを含む) の候補リストをWindows 10します。</span><span class="sxs-lookup"><span data-stu-id="65045-146">Provides a candidate list of all `msedge.exe` processes \(including [PWAs](../progressive-web-apps-chromium/index.md) and all tabs in all instances of Microsoft Edge\) on the Windows 10 device for debugging.</span></span>  

**<span data-ttu-id="65045-147">パラメーター</span><span class="sxs-lookup"><span data-stu-id="65045-147">Parameters</span></span>**  

**<span data-ttu-id="65045-148">なし</span><span class="sxs-lookup"><span data-stu-id="65045-148">None</span></span>**  

**<span data-ttu-id="65045-149">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="65045-149">Return object</span></span>**  

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

### <a name="msedge"></a><span data-ttu-id="65045-150">/msedge/</span><span class="sxs-lookup"><span data-stu-id="65045-150">/msedge/</span></span>  

<span data-ttu-id="65045-151">機能的には [/msedge/json/list と同等です](#msedgejsonlist)。</span><span class="sxs-lookup"><span data-stu-id="65045-151">Functionally equivalent to [/msedge/json/list](#msedgejsonlist).</span></span>  

### <a name="msedgepidjsonlist"></a><span data-ttu-id="65045-152">/msedge/[pid]/json/list</span><span class="sxs-lookup"><span data-stu-id="65045-152">/msedge/[pid]/json/list</span></span>  

<span data-ttu-id="65045-153">デバッグ用に指定されたインスタンスと一致するMicrosoft Edgeページ ターゲットの候補リスト `[pid]` を提供します。</span><span class="sxs-lookup"><span data-stu-id="65045-153">Provides a candidate list of page targets for the Microsoft Edge instance that matches the provided `[pid]` for debugging.</span></span>  

**<span data-ttu-id="65045-154">パラメーター</span><span class="sxs-lookup"><span data-stu-id="65045-154">Parameters</span></span>**  

**<span data-ttu-id="65045-155">なし</span><span class="sxs-lookup"><span data-stu-id="65045-155">None</span></span>**  

**<span data-ttu-id="65045-156">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="65045-156">Return object</span></span>**  

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

### <a name="msedgepidjsonversion"></a><span data-ttu-id="65045-157">/msedge/[pid]/json/version</span><span class="sxs-lookup"><span data-stu-id="65045-157">/msedge/[pid]/json/version</span></span>  

<span data-ttu-id="65045-158">指定されたバージョンと一Microsoft Edge、サポートする DevTools プロトコルのバージョンに一致するインスタンスに関する情報 `[pid]` を提供します。</span><span class="sxs-lookup"><span data-stu-id="65045-158">Provides information about the Microsoft Edge instance that matches the provided `[pid]` and which version of the DevTools Protocol it supports.</span></span>  

**<span data-ttu-id="65045-159">パラメーター</span><span class="sxs-lookup"><span data-stu-id="65045-159">Parameters</span></span>**  

**<span data-ttu-id="65045-160">なし</span><span class="sxs-lookup"><span data-stu-id="65045-160">None</span></span>**  

**<span data-ttu-id="65045-161">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="65045-161">Return object</span></span>**  

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

### <a name="msedgepidjsonprotocol"></a><span data-ttu-id="65045-162">/msedge/[pid]/json/protocol/</span><span class="sxs-lookup"><span data-stu-id="65045-162">/msedge/[pid]/json/protocol/</span></span>  

<span data-ttu-id="65045-163">指定されたインスタンスと一致するインスタンスの JSON としてシリアル化Microsoft Edgeプロトコル API サーフェス全体を提供します `[pid]` 。</span><span class="sxs-lookup"><span data-stu-id="65045-163">Provides the entire protocol API surface serialized as JSON for the Microsoft Edge instance that matches the provided `[pid]`.</span></span>  

**<span data-ttu-id="65045-164">パラメーター</span><span class="sxs-lookup"><span data-stu-id="65045-164">Parameters</span></span>**  

**<span data-ttu-id="65045-165">なし</span><span class="sxs-lookup"><span data-stu-id="65045-165">None</span></span>**  

**<span data-ttu-id="65045-166">Return オブジェクト</span><span class="sxs-lookup"><span data-stu-id="65045-166">Return object</span></span>**  

<span data-ttu-id="65045-167">指定されたインスタンスに一致するプロトコルのバージョンで使用可能な API サーフェスを表Microsoft Edge JSON `[pid]` オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="65045-167">JSON object which represents the available API surface for the version of the protocol that the Microsoft Edge instance that matches the provided `[pid]` is using.</span></span>  
