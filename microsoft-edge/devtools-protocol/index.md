---
description: Microsoft Edge DevTools プロトコルを使用して、Microsoft Edge (EdgeHTML) ブラウザーを検査およびデバッグします。
title: Microsoft Edge DevTools プロトコル
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/11/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: 8bef24c98dae284f2111f6a16fca4a6f27c89dc4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569592"
---
# <span data-ttu-id="3e19b-103">Microsoft Edge (EdgeHTML) DevTools プロトコル</span><span class="sxs-lookup"><span data-stu-id="3e19b-103">Microsoft Edge (EdgeHTML) DevTools Protocol</span></span>

> [!NOTE]
> <span data-ttu-id="3e19b-104">Microsoft Edge (EdgeHTML) DevTools プロトコルは、 [Windows 10 年 4 2018 月の更新プログラム](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97)以降のビルドでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="3e19b-104">The Microsoft Edge (EdgeHTML) DevTools Protocol works only on [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) and later builds.</span></span>

<span data-ttu-id="3e19b-105">開発者ツールでは、 **Microsoft edge (EdgeHTML) DevTools プロトコル**を使用して、microsoft Edge (EdgeHTML) ブラウザーを検査およびデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="3e19b-105">Developer tools can use the **Microsoft Edge (EdgeHTML) DevTools Protocol** to inspect and debug the Microsoft Edge (EdgeHTML) browser.</span></span> <span data-ttu-id="3e19b-106">EdgeHTML engine インストルメンテーションのさまざまな[ドメイン](0.2/domains/index.md)で構成されている一連のメソッドとイベントを提供します。</span><span class="sxs-lookup"><span data-stu-id="3e19b-106">It provides a set of methods and events that are organized into different [Domains](0.2/domains/index.md) of EdgeHTML engine instrumentation.</span></span>

 <span data-ttu-id="3e19b-107">ツールクライアントは、これらのメソッドを呼び出し、Microsoft Edge (EdgeHTML) または Windows Device Portal でホストされている*Devtools サーバー*との間でやり取りされる JSON web ソケットメッセージを通じて、これらのイベントを監視します。</span><span class="sxs-lookup"><span data-stu-id="3e19b-107">Tooling clients can call these methods and monitor these events through JSON web socket messages exchanged with the *DevTools Server* hosted by Microsoft Edge (EdgeHTML) or the Windows Device Portal.</span></span> <span data-ttu-id="3e19b-108">Microsoft Edge (EdgeHTML) DevTools はこのプロトコルを使用して、microsoft [Store](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)から入手できるスタンドアロンの devtools クライアントから microsoft Edge (EdgeHTML) を実行しているホストコンピューターの[リモートデバッグ](0.2/clients.md#microsoft-edge-devtools-preview)を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3e19b-108">Microsoft Edge (EdgeHTML) DevTools uses this protocol to enable [remote debugging](0.2/clients.md#microsoft-edge-devtools-preview) of a host machine running Microsoft Edge (EdgeHTML) from the standalone DevTools client available from the [Microsoft Store](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj).</span></span>

<span data-ttu-id="3e19b-109">Microsoft Edge (EdgeHTML) DevTools プロトコルは、Chrome DevTools プロトコルと密接に整列するように設計されていますが、このリリースでは、相互運用性に[関する](https://github.com/WICG/devtools-protocol/)重要な点があります。</span><span class="sxs-lookup"><span data-stu-id="3e19b-109">The Microsoft Edge (EdgeHTML) DevTools Protocol is designed to align closely with the Chrome DevTools Protocol (see the [W3C WICG for DevTools Protocols](https://github.com/WICG/devtools-protocol/)), though there are known interoperability gaps in this release.</span></span>

## <span data-ttu-id="3e19b-110">プロトコルの使用</span><span class="sxs-lookup"><span data-stu-id="3e19b-110">Using the protocol</span></span>

<span data-ttu-id="3e19b-111">Microsoft Edge (EdgeHTML) の DevTools サーバーにカスタムツールクライアントをアタッチする方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3e19b-111">Here's how to attach a custom tooling client to the DevTools Server in Microsoft Edge (EdgeHTML).</span></span> <span data-ttu-id="3e19b-112">クライアントとして Microsoft Edge DevTools を使っている場合は、[リモートデバッグ](0.2/clients.md#microsoft-edge-devtools-preview)の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e19b-112">See the [remote debugging](0.2/clients.md#microsoft-edge-devtools-preview) instructions if you're using Microsoft Edge DevTools as your client.</span></span>

1. <span data-ttu-id="3e19b-113">リモートデバッグポートを開いた状態で Microsoft Edge (EdgeHTML) を起動し、開こうとしている URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="3e19b-113">Launch Microsoft Edge (EdgeHTML) with the remote debugging port open, specifying the URL you wish to open.</span></span> <span data-ttu-id="3e19b-114">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="3e19b-114">For example:</span></span>

    ```
    MicrosoftEdge.exe --devtools-server-port 9222 https://www.bing.com
    ```

    <span data-ttu-id="3e19b-115">Edge が既に起動されている場合、URL パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="3e19b-115">If Edge is already launched, the URL parameter is optional.</span></span> <span data-ttu-id="3e19b-116">ブラウザーのアドレスバーの横に、**開発者ツールサーバー**が起動したことを示すボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e19b-116">A button will appear next to the browser address bar to indicate the **Developer tools server** has started:</span></span>

    ![開発者ツールサーバー](media/developer-tools-server.png) 

2. <span data-ttu-id="3e19b-118">この[HTTP エンドポイント](0.2/http.md)を使用して、アタッチ可能なページターゲットの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="3e19b-118">Use this [HTTP endpoint](0.2/http.md) to get a list of attachable page targets:</span></span>

    ```
    http://localhost:9222/json/list
    ```

3. <span data-ttu-id="3e19b-119">目的のページの一覧に接続して、 `webSocketDebuggerUrl` さらに[プロトコルコマンド](0.2/domains/index.md)を発行し、devtools ソケットサーバーを通じてイベントメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="3e19b-119">Connect to the listed `webSocketDebuggerUrl` of the desired page to issue further [protocol commands](0.2/domains/index.md) and receive event messages through the devtools socket server.</span></span>

## <span data-ttu-id="3e19b-120">状態とフィードバック</span><span class="sxs-lookup"><span data-stu-id="3e19b-120">Status and feedback</span></span>

<span data-ttu-id="3e19b-121">DevTools プロトコルの[バージョン 0.2](0.2/index.md)では、[バージョン 0.1](0.1/index.md)で導入されたコアスクリプトのデバッグ機能に加えて、スタイルとレイアウト (読み取り専用) デバッグとコンソール api 用の新しいドメインが提供されています。</span><span class="sxs-lookup"><span data-stu-id="3e19b-121">[Version 0.2](0.2/index.md) of the DevTools Protocol provides new domains for style and layout (read-only) debugging and console APIs, in addition to the core script debugging functionality introduced in [Version 0.1](0.1/index.md).</span></span> <span data-ttu-id="3e19b-122">Microsoft Edge DevTools UI では、[**要素**](../devtools-guide/elements.md)、[**コンソール**](../devtools-guide/console.md)、[**デバッガー**](../devtools-guide/debugger.md)パネルで利用できる機能に変換されます。</span><span class="sxs-lookup"><span data-stu-id="3e19b-122">In the Microsoft Edge DevTools UI, this translates to functionality available in the [**Elements**](../devtools-guide/elements.md), [**Console**](../devtools-guide/console.md) and [**Debugger**](../devtools-guide/debugger.md) panels.</span></span>

<span data-ttu-id="3e19b-123">ご利用いただき、ありがとうございました。</span><span class="sxs-lookup"><span data-stu-id="3e19b-123">Thanks for trying the Edge DevTools Protocol!</span></span> <span data-ttu-id="3e19b-124">皆様からのフィードバックは、次のページでご意見をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="3e19b-124">We'd love to hear your feedback at:</span></span>

 - <span data-ttu-id="3e19b-125">[**Microsoft Edge Developer UserVoice**](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer?category_id=84475): devtools 機能のアイデアと要求</span><span class="sxs-lookup"><span data-stu-id="3e19b-125">[**Microsoft Edge Developer UserVoice**](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer?category_id=84475): DevTools feature ideas and requests</span></span>

 - <span data-ttu-id="3e19b-126">[**EdgeHTML Issue Tracker**](https://developer.microsoft.com/microsoft-edge/platform/issues/): Protocol、Devtools、EdgeHTML platform のバグと問題</span><span class="sxs-lookup"><span data-stu-id="3e19b-126">[**EdgeHTML Issue Tracker**](https://developer.microsoft.com/microsoft-edge/platform/issues/): Protocol, DevTools, and EdgeHTML platform bugs and issues</span></span>

 - <span data-ttu-id="3e19b-127">[**Microsoft Edge DevTools フィードバック hub**](feedback-hub:?referrer=microsoftEdge&tabID=2&newFeedback=true&ContextId=344): フィードバック hub アプリによるプロトコルおよび devtools の問題と提案</span><span class="sxs-lookup"><span data-stu-id="3e19b-127">[**Microsoft Edge DevTools Feedback Hub**](feedback-hub:?referrer=microsoftEdge&tabID=2&newFeedback=true&ContextId=344): Protocol and DevTools problems and suggestions through the Feedback Hub app</span></span>

## <span data-ttu-id="3e19b-128">FAQ</span><span class="sxs-lookup"><span data-stu-id="3e19b-128">FAQ</span></span>

#### <span data-ttu-id="3e19b-129">複数のクライアントが同じ DevTools サーバに接続することはできますか?</span><span class="sxs-lookup"><span data-stu-id="3e19b-129">Can multiple clients connect to the same DevTools Server?</span></span>
<span data-ttu-id="3e19b-130">いいえ。クライアントがデバッグしているときに、同時には表示されません。</span><span class="sxs-lookup"><span data-stu-id="3e19b-130">No, not simultaneously when the clients are debugging.</span></span> <span data-ttu-id="3e19b-131">接続する最後のクライアントは、前のものを開始します。</span><span class="sxs-lookup"><span data-stu-id="3e19b-131">The last client to connect will kick off the previous one.</span></span> <span data-ttu-id="3e19b-132">今後、その他のツールがサポートされると、クライアント間の同時接続がサポートされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3e19b-132">In the future when additional tools are supported, those will likely support simultaneous client connections.</span></span>

#### <span data-ttu-id="3e19b-133">DevTools サーバーのポートとして9222を使用する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="3e19b-133">Do I have to use 9222 as the DevTools Server port?</span></span>
<span data-ttu-id="3e19b-134">いいえ、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="3e19b-134">No.</span></span> <span data-ttu-id="3e19b-135">どのポートも指定できますが、まだ使用していないものを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="3e19b-135">You can specify any port, though be sure to pick one that isn't already in use.</span></span> <span data-ttu-id="3e19b-136">リモートデバッグ用のポート9222は、慣例で使用されます。</span><span class="sxs-lookup"><span data-stu-id="3e19b-136">Port 9222 for remote debugging is used by convention.</span></span>

#### <span data-ttu-id="3e19b-137">DevTools サーバーを実行しているカスタムツールクライアントを Microsoft Edge (EdgeHTML) に接続するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="3e19b-137">How do I connect my custom tooling client to Microsoft Edge (EdgeHTML) running the DevTools Server?</span></span>
<span data-ttu-id="3e19b-138">ローカルコンピューターで実行されている Microsoft Edge (EdgeHTML) への接続については、上記のプロトコルの手順[*を*](#using-the-protocol)参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e19b-138">See [*Using the protocol*](#using-the-protocol) instructions above for attaching to Microsoft Edge (EdgeHTML) running on the local machine.</span></span> <span data-ttu-id="3e19b-139">リモートデバッグをサポートすることを検討している場合は、クライアントにホストコンピューターの SSL 証明書をインストールするためのユーザーワークフローを考案する必要があります。たとえば、 [Microsoft Edge DevTools Preview](./0.2/clients.md#microsoft-edge-devtools-preview)でのインストールダイアログが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3e19b-139">If you're looking to support remote debugging, you'll need to devise a user workflow for installing the host machine's SSL certificate on the client, for example with an install dialog as [Microsoft Edge DevTools Preview](./0.2/clients.md#microsoft-edge-devtools-preview) uses.</span></span>

#### <span data-ttu-id="3e19b-140">Edge DevTools を使ってリモートデバッグを行う場合は、ホストブラウザープロセスを開始する必要があります。 *--devtools-server-port* cmd line スイッチ</span><span class="sxs-lookup"><span data-stu-id="3e19b-140">If I'm remote debugging using Edge DevTools, do I need to start the host browser process with *--devtools-server-port* cmd line switch?</span></span> 
<span data-ttu-id="3e19b-141">いいえ、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="3e19b-141">No.</span></span> <span data-ttu-id="3e19b-142">[Microsoft Edge DevTools Preview を使ってリモートデバッグ](./0.2/clients.md#microsoft-edge-devtools-preview)をセットアップしている場合、 `--devtools-server-port` コマンドラインスイッチは、edge を起動するために必要ありません。</span><span class="sxs-lookup"><span data-stu-id="3e19b-142">If you're setting up [remote debugging using Microsoft Edge DevTools Preview](./0.2/clients.md#microsoft-edge-devtools-preview), the `--devtools-server-port` command line switch is not necessary for starting Edge.</span></span> <span data-ttu-id="3e19b-143">この場合、Windows *Device Portal*は、ブラウザの代わりに Devtools サーバーをホストしています。</span><span class="sxs-lookup"><span data-stu-id="3e19b-143">In this case, Windows *Device Portal* is hosting the DevTools Server on behalf of the browser.</span></span>

#### <span data-ttu-id="3e19b-144">エッジ DevTools プロトコルを使用して、WWAHost .exe または webview プロセスをリモートでデバッグすることはできますか?</span><span class="sxs-lookup"><span data-stu-id="3e19b-144">Can I use the Edge DevTools Protocol to remotely debug a WWAHost.exe or webview process?</span></span>
<span data-ttu-id="3e19b-145">Edge DevTools プロトコルは現在、ブラウザーのタブのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3e19b-145">The Edge DevTools Protocol currently supports only browser tabs.</span></span> <span data-ttu-id="3e19b-146">WWAHost と webview のプロセスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3e19b-146">WWAHost.exe and webview processes are not supported.</span></span>
