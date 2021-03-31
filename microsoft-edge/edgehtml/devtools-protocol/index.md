---
description: Microsoft Edge DevTools プロトコルを使用して、Microsoft Edge (EdgeHTML) ブラウザーを検査およびデバッグします。
title: Microsoft Edge DevTools プロトコル
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 03/16/2021
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: bc95f6c167479e958ffd16137176418aba872a43
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439311"
---
# <a name="microsoft-edge-edgehtml-devtools-protocol"></a><span data-ttu-id="16307-103">Microsoft Edge (EdgeHTML) DevTools プロトコル</span><span class="sxs-lookup"><span data-stu-id="16307-103">Microsoft Edge (EdgeHTML) DevTools Protocol</span></span>

> [!NOTE]
> <span data-ttu-id="16307-104">Microsoft Edge (EdgeHTML) DevTools プロトコルは [、Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 以降のビルドでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="16307-104">The Microsoft Edge (EdgeHTML) DevTools Protocol works only on [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) and later builds.</span></span>

<span data-ttu-id="16307-105">開発者ツールは **、Microsoft Edge (EdgeHTML) DevTools プロトコル** を使用して、Microsoft Edge (EdgeHTML) ブラウザーを検査およびデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="16307-105">Developer tools can use the **Microsoft Edge (EdgeHTML) DevTools Protocol** to inspect and debug the Microsoft Edge (EdgeHTML) browser.</span></span> <span data-ttu-id="16307-106">さまざまな [Domains](0.2/domains/index.md) of EdgeHTML エンジンインストルメンテーションに編成された一連のメソッドとイベントを提供します。</span><span class="sxs-lookup"><span data-stu-id="16307-106">It provides a set of methods and events that are organized into different [Domains](0.2/domains/index.md) of EdgeHTML engine instrumentation.</span></span>

 <span data-ttu-id="16307-107">ツール クライアントは、Microsoft Edge (EdgeHTML) または Windows デバイス ポータルによってホストされる *DevTools Server* と交換される JSON Web ソケット メッセージを使用して、これらのメソッドを呼び出し、これらのイベントを監視できます。</span><span class="sxs-lookup"><span data-stu-id="16307-107">Tooling clients can call these methods and monitor these events through JSON web socket messages exchanged with the *DevTools Server* hosted by Microsoft Edge (EdgeHTML) or the Windows Device Portal.</span></span> <span data-ttu-id="16307-108">Microsoft Edge (EdgeHTML) DevTools は[](0.2/clients.md#microsoft-edge-devtools-preview)、このプロトコルを使用して[、Microsoft Store](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)から利用できるスタンドアロンの DevTools クライアントから Microsoft Edge (EdgeHTML) を実行しているホスト マシンのリモート デバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="16307-108">Microsoft Edge (EdgeHTML) DevTools uses this protocol to enable [remote debugging](0.2/clients.md#microsoft-edge-devtools-preview) of a host machine running Microsoft Edge (EdgeHTML) from the standalone DevTools client available from the [Microsoft Store](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj).</span></span>

<span data-ttu-id="16307-109">Microsoft Edge (EdgeHTML) DevTools プロトコルは、このリリースでは相互運用性のギャップが既知ですが、Chrome DevTools プロトコルと密接に一致するように設計されています [(「W3C WICG for DevTools Protocols」](https://github.com/WICG/devtools-protocol/)を参照)。</span><span class="sxs-lookup"><span data-stu-id="16307-109">The Microsoft Edge (EdgeHTML) DevTools Protocol is designed to align closely with the Chrome DevTools Protocol (see the [W3C WICG for DevTools Protocols](https://github.com/WICG/devtools-protocol/)), though there are known interoperability gaps in this release.</span></span>

## <a name="using-the-protocol"></a><span data-ttu-id="16307-110">プロトコルの使用</span><span class="sxs-lookup"><span data-stu-id="16307-110">Using the protocol</span></span>

<span data-ttu-id="16307-111">Microsoft Edge (EdgeHTML) の DevTools Server にカスタム ツール クライアントを接続する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16307-111">Here's how to attach a custom tooling client to the DevTools Server in Microsoft Edge (EdgeHTML).</span></span> <span data-ttu-id="16307-112">Microsoft Edge DevTools [を](0.2/clients.md#microsoft-edge-devtools-preview) クライアントとして使用している場合は、リモート デバッグの手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16307-112">See the [remote debugging](0.2/clients.md#microsoft-edge-devtools-preview) instructions if you're using Microsoft Edge DevTools as your client.</span></span>

1. <span data-ttu-id="16307-113">開く URL を指定して、リモート デバッグ ポートを開いた Microsoft Edge (EdgeHTML) を起動します。</span><span class="sxs-lookup"><span data-stu-id="16307-113">Launch Microsoft Edge (EdgeHTML) with the remote debugging port open, specifying the URL you wish to open.</span></span> <span data-ttu-id="16307-114">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="16307-114">For example:</span></span>

    ```shell
    MicrosoftEdge.exe --devtools-server-port 9222 https://www.bing.com
    ```

    <span data-ttu-id="16307-115">Edge が既に起動されている場合、URL パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="16307-115">If Edge is already launched, the URL parameter is optional.</span></span> <span data-ttu-id="16307-116">開発者ツール サーバーが起動したかどうかを示すボタンがブラウザーのアドレス バー **の横に** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="16307-116">A button will appear next to the browser address bar to indicate the **Developer tools server** has started:</span></span>

    ![開発者ツール サーバー](media/developer-tools-server.png) 

2. <span data-ttu-id="16307-118">接続可能 [なページ ターゲット](0.2/http.md) の一覧を取得するには、次の HTTP エンドポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="16307-118">Use this [HTTP endpoint](0.2/http.md) to get a list of attachable page targets:</span></span>

    ```http
    http://localhost:9222/json/list
    ```

3. <span data-ttu-id="16307-119">目的のページの一覧に接続して、さらにプロトコル コマンドを発行し、devtools ソケット サーバーを介してイベント メッセージ `webSocketDebuggerUrl` を受信します。 [](0.2/domains/index.md)</span><span class="sxs-lookup"><span data-stu-id="16307-119">Connect to the listed `webSocketDebuggerUrl` of the desired page to issue further [protocol commands](0.2/domains/index.md) and receive event messages through the devtools socket server.</span></span>

## <a name="status-and-feedback"></a><span data-ttu-id="16307-120">状態とフィードバック</span><span class="sxs-lookup"><span data-stu-id="16307-120">Status and feedback</span></span>

<span data-ttu-id="16307-121">DevTools プロトコルのバージョン[0.2](0.2/index.md)には、バージョン[0.1](0.1/index.md)で導入されたコア スクリプト デバッグ機能に加えて、スタイルとレイアウト (読み取り専用) デバッグおよびコンソール API 用の新しいドメインが提供されています。</span><span class="sxs-lookup"><span data-stu-id="16307-121">[Version 0.2](0.2/index.md) of the DevTools Protocol provides new domains for style and layout (read-only) debugging and console APIs, in addition to the core script debugging functionality introduced in [Version 0.1](0.1/index.md).</span></span> <span data-ttu-id="16307-122">Microsoft Edge DevTools UI では、これは要素、コンソール、デバッガー[](../devtools-guide/elements.md)パネルで使用できる[**機能**](../devtools-guide/console.md)に[**変換**](../devtools-guide/debugger.md)されます。</span><span class="sxs-lookup"><span data-stu-id="16307-122">In the Microsoft Edge DevTools UI, this translates to functionality available in the [**Elements**](../devtools-guide/elements.md), [**Console**](../devtools-guide/console.md) and [**Debugger**](../devtools-guide/debugger.md) panels.</span></span>

<span data-ttu-id="16307-123">Edge DevTools プロトコルを試してありがとう!</span><span class="sxs-lookup"><span data-stu-id="16307-123">Thanks for trying the Edge DevTools Protocol!</span></span> <span data-ttu-id="16307-124">次の場所でフィードバックをお寄せください。</span><span class="sxs-lookup"><span data-stu-id="16307-124">We'd love to hear your feedback at:</span></span>

<!-- - [**Microsoft Edge Developer UserVoice**](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer?category_id=84475): DevTools feature ideas and requests-->  

 - <span data-ttu-id="16307-125">[**EdgeHTML Issue Tracker**](https://developer.microsoft.com/microsoft-edge/platform/issues/): プロトコル、DevTools、EdgeHTML プラットフォームのバグと問題</span><span class="sxs-lookup"><span data-stu-id="16307-125">[**EdgeHTML Issue Tracker**](https://developer.microsoft.com/microsoft-edge/platform/issues/): Protocol, DevTools, and EdgeHTML platform bugs and issues</span></span>

 - <span data-ttu-id="16307-126">[**Microsoft Edge DevTools フィードバック ハブ**](feedback-hub:?referrer=microsoftEdge&tabID=2&newFeedback=true&ContextId=344): フィードバック ハブ アプリによるプロトコルと DevTools の問題と提案</span><span class="sxs-lookup"><span data-stu-id="16307-126">[**Microsoft Edge DevTools Feedback Hub**](feedback-hub:?referrer=microsoftEdge&tabID=2&newFeedback=true&ContextId=344): Protocol and DevTools problems and suggestions through the Feedback Hub app</span></span>

## <a name="faq"></a><span data-ttu-id="16307-127">FAQ</span><span class="sxs-lookup"><span data-stu-id="16307-127">FAQ</span></span>

#### <a name="can-multiple-clients-connect-to-the-same-devtools-server"></a><span data-ttu-id="16307-128">複数のクライアントが同じ DevTools Server に接続できますか?</span><span class="sxs-lookup"><span data-stu-id="16307-128">Can multiple clients connect to the same DevTools Server?</span></span>
<span data-ttu-id="16307-129">いいえ、クライアントがデバッグする場合は同時ではありません。</span><span class="sxs-lookup"><span data-stu-id="16307-129">No, not simultaneously when the clients are debugging.</span></span> <span data-ttu-id="16307-130">接続する最後のクライアントは、前のクライアントを開始します。</span><span class="sxs-lookup"><span data-stu-id="16307-130">The last client to connect will kick off the previous one.</span></span> <span data-ttu-id="16307-131">今後、追加のツールがサポートされる場合、同時クライアント接続がサポートされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="16307-131">In the future when additional tools are supported, those will likely support simultaneous client connections.</span></span>

#### <a name="do-i-have-to-use-9222-as-the-devtools-server-port"></a><span data-ttu-id="16307-132">DevTools Server ポートとして 9222 を使用する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="16307-132">Do I have to use 9222 as the DevTools Server port?</span></span>
<span data-ttu-id="16307-133">いいえ、</span><span class="sxs-lookup"><span data-stu-id="16307-133">No.</span></span> <span data-ttu-id="16307-134">任意のポートを指定することができますが、まだ使用されていないポートを選択してください。</span><span class="sxs-lookup"><span data-stu-id="16307-134">You can specify any port, though be sure to pick one that isn't already in use.</span></span> <span data-ttu-id="16307-135">リモート デバッグ用のポート 9222 は、規則によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="16307-135">Port 9222 for remote debugging is used by convention.</span></span>

#### <a name="how-do-i-connect-my-custom-tooling-client-to-microsoft-edge-edgehtml-running-the-devtools-server"></a><span data-ttu-id="16307-136">DevTools Server を実行している Microsoft Edge (EdgeHTML) にカスタム ツール クライアントを接続する方法</span><span class="sxs-lookup"><span data-stu-id="16307-136">How do I connect my custom tooling client to Microsoft Edge (EdgeHTML) running the DevTools Server?</span></span>
<span data-ttu-id="16307-137">ローカル [*コンピューターで実行されている*](#using-the-protocol) Microsoft Edge (EdgeHTML) に接続するには、上記のプロトコル手順を使用するを参照してください。</span><span class="sxs-lookup"><span data-stu-id="16307-137">See [*Using the protocol*](#using-the-protocol) instructions above for attaching to Microsoft Edge (EdgeHTML) running on the local machine.</span></span> <span data-ttu-id="16307-138">リモート デバッグをサポートする場合は、ホスト コンピューターの SSL 証明書をクライアントにインストールするユーザー ワークフロー ( [たとえば、Microsoft Edge DevTools Preview](./0.2/clients.md#microsoft-edge-devtools-preview) が使用するインストール ダイアログなど) を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16307-138">If you're looking to support remote debugging, you'll need to devise a user workflow for installing the host machine's SSL certificate on the client, for example with an install dialog as [Microsoft Edge DevTools Preview](./0.2/clients.md#microsoft-edge-devtools-preview) uses.</span></span>

#### <a name="if-im-remote-debugging-using-edge-devtools-do-i-need-to-start-the-host-browser-process-with---devtools-server-port-cmd-line-switch"></a><span data-ttu-id="16307-139">Edge DevTools を使用してリモート デバッグを行う場合 *、--devtools-server-port cmd* 行スイッチを使用してホスト ブラウザー プロセスを開始する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="16307-139">If I'm remote debugging using Edge DevTools, do I need to start the host browser process with *--devtools-server-port* cmd line switch?</span></span> 
<span data-ttu-id="16307-140">いいえ、</span><span class="sxs-lookup"><span data-stu-id="16307-140">No.</span></span> <span data-ttu-id="16307-141">[Microsoft Edge DevTools Preview](./0.2/clients.md#microsoft-edge-devtools-preview)を使用してリモート デバッグを設定する場合、Edge の起動にはコマンド ライン スイッチ `--devtools-server-port` は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="16307-141">If you're setting up [remote debugging using Microsoft Edge DevTools Preview](./0.2/clients.md#microsoft-edge-devtools-preview), the `--devtools-server-port` command line switch is not necessary for starting Edge.</span></span> <span data-ttu-id="16307-142">この場合、Windows *デバイス ポータルは* ブラウザーの代わりに DevTools Server をホストしています。</span><span class="sxs-lookup"><span data-stu-id="16307-142">In this case, Windows *Device Portal* is hosting the DevTools Server on behalf of the browser.</span></span>

#### <a name="can-i-use-the-edge-devtools-protocol-to-remotely-debug-a-wwahostexe-or-webview-process"></a><span data-ttu-id="16307-143">Edge DevTools プロトコルを使用して、リモートでアプリケーション プロセスまたは webview プロセスWWAHost.exeデバッグできますか?</span><span class="sxs-lookup"><span data-stu-id="16307-143">Can I use the Edge DevTools Protocol to remotely debug a WWAHost.exe or webview process?</span></span>
<span data-ttu-id="16307-144">エッジ DevTools プロトコルは現在、ブラウザー タブのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="16307-144">The Edge DevTools Protocol currently supports only browser tabs.</span></span> <span data-ttu-id="16307-145">WWAHost.exe Webview プロセスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="16307-145">WWAHost.exe and webview processes are not supported.</span></span>
