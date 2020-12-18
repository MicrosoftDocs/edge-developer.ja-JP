---
description: Microsoft Edge DevTools Protocol Version 0.2 は、次のツール クライアントをサポートしています。
title: Microsoft Edge DevTools プロトコル バージョン 0.2 クライアント (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b471ff5a4051411fc205a269d811524c38acac72
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234415"
---
# <span data-ttu-id="36188-103">Microsoft Edge DevTools プロトコル バージョン 0.2 クライアント (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="36188-103">Microsoft Edge DevTools Protocol Version 0.2 Clients (EdgeHTML)</span></span>  

> [!NOTE]
> <span data-ttu-id="36188-104">Microsoft Edge DevTools プロトコルのバージョン 0.2 は [、Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) 以降の [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) ビルドでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="36188-104">Version 0.2 of the Microsoft Edge DevTools Protocol works only on the [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) and later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) builds.</span></span>  

<span data-ttu-id="36188-105">**DevTools Protocol 0.2 は、次** のツール クライアントをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="36188-105">**DevTools Protocol 0.2** supports the following tooling clients.</span></span>

<span data-ttu-id="36188-106">[ ![ Microsoft Edge DevTools Preview](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [ ![ Visual Studio Code](../media/visual-studio-code.png)](#visual-studio-code) Microsoft Visual Studio [ ![ 15.8](../media/visual-studio-2017.png)](#microsoft-visual-studio)</span><span class="sxs-lookup"><span data-stu-id="36188-106">[![Microsoft Edge DevTools Preview](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [![Visual Studio Code](../media/visual-studio-code.png)](#visual-studio-code) [![Microsoft Visual Studio 15.8](../media/visual-studio-2017.png)](#microsoft-visual-studio)</span></span>

## <span data-ttu-id="36188-107">Microsoft Edge DevTools プレビュー</span><span class="sxs-lookup"><span data-stu-id="36188-107">Microsoft Edge DevTools Preview</span></span>

<span data-ttu-id="36188-108">Microsoft Store からスタンドアロン [**の Microsoft Edge DevTools Preview**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) Windows 10 アプリを使用して、Microsoft Edge を実行しているホスト デバイス[(EdgeHTML 17](../../dev-guide/index.md) 以降) をリモートでデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="36188-108">You can use the standalone [**Microsoft Edge DevTools Preview**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) Windows 10 app from the Microsoft Store to remotely debug a host device running Microsoft Edge ([EdgeHTML 17](../../dev-guide/index.md) or later).</span></span>

<span data-ttu-id="36188-109">DevTools プロトコルのバージョン 0.2 には、バージョン 0.1 で導入されたコア スクリプト デバッグ機能に加えて、スタイルとレイアウトのデバッグとコンソール API 用の新しいドメインが提供されています。</span><span class="sxs-lookup"><span data-stu-id="36188-109">Version 0.2 of the DevTools Protocol provides new domains for style and layout debugging and console APIs, in addition to the core script debugging functionality introduced in Version 0.1.</span></span> <span data-ttu-id="36188-110">Edge DevTools UI では、これは要素パネル、コンソール パネル[\*\*\*\*](../../devtools-guide/elements.md)、デバッガー パネルで利用可能な[**機能**](../../devtools-guide/console.md)に[**変換**](../../devtools-guide/debugger.md)されます。</span><span class="sxs-lookup"><span data-stu-id="36188-110">In the Edge DevTools UI, this translates to functionality available in the [**Elements**](../../devtools-guide/elements.md), [**Console**](../../devtools-guide/console.md) and [**Debugger**](../../devtools-guide/debugger.md) panels.</span></span> <span data-ttu-id="36188-111">現在、Microsoft Edge のリモート デバッグはデスクトップ ホストに限定されています。今後のリリースで予定されている他の Windows 10 デバイスもサポートされます。</span><span class="sxs-lookup"><span data-stu-id="36188-111">Currently Microsoft Edge remote debugging is limited to desktop hosts, with support for other Windows 10 devices coming in future releases.</span></span>

<span data-ttu-id="36188-112">Microsoft Edge DevTools Preview アプリを使ってリモート デバッグをセットアップする方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="36188-112">Here's how to set up remote debugging with the Microsoft Edge DevTools Preview app.</span></span> <span data-ttu-id="36188-113">DevTools プロトコル バージョン 0.2 では、ホスト (デバッグ先) コンピューター上に [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) 以降の Windows Insider Preview ビルドが必要です。</span><span class="sxs-lookup"><span data-stu-id="36188-113">The DevTools Protocol version 0.2 requires [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) or a later Windows Insider Preview build on the host (debugee) machine.</span></span> <span data-ttu-id="36188-114">Edge DevTools Preview アプリ (デバッガー コンピューターで使用) は、Windows 10 バージョン 16299 (Windows 10 Fall Creators Update、10/2017) 以上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="36188-114">The Edge DevTools Preview app (used on the debugger machine) will run on Windows 10 version 16299 (Windows 10 Fall Creators Update, 10/2017) or higher.</span></span>

**<span data-ttu-id="36188-115">ホスト (デバッグ先) コンピューターで...</span><span class="sxs-lookup"><span data-stu-id="36188-115">On the host (debugee) machine...</span></span>**

1. <span data-ttu-id="36188-116">WiFi ネットワークを使用している場合は、ネットワークがドメインまたはプライベートとして **マーク付け** されている必要 **があります**。</span><span class="sxs-lookup"><span data-stu-id="36188-116">If you're on a WiFi network, ensure the network is marked as either **Domain** or **Private**.</span></span> <span data-ttu-id="36188-117">これを確認するには[**、Windows Defender**](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)セキュリティ センター アプリを開き、**ファイアウォール &** ネットワーク保護をクリックし、ネットワークがドメイン ネットワークまたはプライベート ネットワークとして\*\* 一覧表示されるのか確認*します。*</span><span class="sxs-lookup"><span data-stu-id="36188-117">You can verify this by opening the [**Windows Defender Security Center**](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) app, clicking on **Firewall & network protection** and checking if your network is listed as a *Domain network* or *Private network*.</span></span> 

    <span data-ttu-id="36188-118">If its listed as *Public,* go to **Settings**  >  **Network & Internet**  >  **Wi-Fi,** click on your network and toggle the Network *profile* button to **Private**.</span><span class="sxs-lookup"><span data-stu-id="36188-118">If its listed as *Public*, go to **Settings** > **Network & Internet** > **Wi-Fi**, click on your network and toggle the *Network profile* button to **Private**.</span></span>

2. <span data-ttu-id="36188-119">*Windows*の**設定で [開発者**向け] コントロール\*\* パネルを開き (開発者向けの検索を行い、[開発者向け機能の使用] をクリックします)、*次*の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="36188-119">Open the **For developers** control panel in Windows *Settings* (search for *developer* and click on *Use developer features*), and:</span></span> 

    <span data-ttu-id="36188-120">a. </span><span class="sxs-lookup"><span data-stu-id="36188-120">a.</span></span> <span data-ttu-id="36188-121">開発者モードを **切り替えます**。</span><span class="sxs-lookup"><span data-stu-id="36188-121">Toggle on **Developer Mode**.</span></span> <span data-ttu-id="36188-122">これにより、開発者モード *パッケージがインストール* され、デスクトップ用のリモート ツールが有効になります。</span><span class="sxs-lookup"><span data-stu-id="36188-122">This will install the *Developer Mode* package, enabling remote tooling for desktop.</span></span>

    <span data-ttu-id="36188-123">b. </span><span class="sxs-lookup"><span data-stu-id="36188-123">b.</span></span> <span data-ttu-id="36188-124">[**Device Portal**](/windows/uwp/debug-test-perf/device-portal) (ローカル*エリア ネットワーク*接続でリモート診断を有効にする) とデバイス**検出を有効**にします (デバイスを USB 接続とローカル ネットワークに表示*します*)。</span><span class="sxs-lookup"><span data-stu-id="36188-124">Enable [**Device Portal**](/windows/uwp/debug-test-perf/device-portal) (*Turn on remote diagnostics over local area network connections*) and **Device discovery** (*Make your device visible to USB connections and your local network*).</span></span>

    <span data-ttu-id="36188-125">c. </span><span class="sxs-lookup"><span data-stu-id="36188-125">c.</span></span> <span data-ttu-id="36188-126">認証を **有効に** し、ユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="36188-126">Turn on **Authentication** and supply a username / password.</span></span>

    <span data-ttu-id="36188-127">d. </span><span class="sxs-lookup"><span data-stu-id="36188-127">d.</span></span> <span data-ttu-id="36188-128">コンピューターの IP アドレスと接続ポート (50443) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="36188-128">Note the machine IP address and connection port (50443) displayed.</span></span>

3. <span data-ttu-id="36188-129">クライアント コンピューターからデバッグする Microsoft Edge のタブを開きます。</span><span class="sxs-lookup"><span data-stu-id="36188-129">Open tabs in Microsoft Edge that you wish to debug from the client machine.</span></span>

**<span data-ttu-id="36188-130">クライアント (デバッガー) コンピューターで...</span><span class="sxs-lookup"><span data-stu-id="36188-130">On the client (debugger) machine...</span></span>**

1.  <span data-ttu-id="36188-131">Microsoft Store からスタンドアロン [の Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) アプリをインストールして起動します。</span><span class="sxs-lookup"><span data-stu-id="36188-131">Install and launch the standalone [Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) app from the Microsoft Store.</span></span>

2. <span data-ttu-id="36188-132">リモート パネル **を開** き、ホスト マシンのネットワークの場所 (URL とポート) を入力し、[接続] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="36188-132">Open the **Remote** panel and enter the network location (URL and port) of the host machine and click **Connect**.</span></span>

3. <span data-ttu-id="36188-133">**[** 信頼されていない証明書] ダイアログボックスが表示 *されたら、ホスト コンピューターの* 証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="36188-133">**Install** the host machine's certificate from the *Untrusted Certificate* dialog that appears.</span></span>

4. <span data-ttu-id="36188-134">Device Portal 認証用に指定したユーザー名/パスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="36188-134">Supply the username/password you designated for Device Portal authentication.</span></span>

5. <span data-ttu-id="36188-135">リモート *パネル* は、デバッグ可能なページ ターゲットの一覧をホスト コンピューターに読み込む。</span><span class="sxs-lookup"><span data-stu-id="36188-135">The *Remote* panel will load a list of debuggable page targets on the host machine.</span></span> <span data-ttu-id="36188-136">デバッグを開始するには、1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="36188-136">Select one to start debugging.</span></span>

6. <span data-ttu-id="36188-137">[更新 **] ボタン** を使用して、ホスト コンピューター上のリモート ページ ターゲットの一覧を更新して再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="36188-137">Use the **Refresh** button to update and reload the list of remote page targets on the host machine.</span></span> <span data-ttu-id="36188-138">[切断 **]** ボタンをクリックして、リモート デバイスへの *接続画面に戻* り、別のホストに接続します。</span><span class="sxs-lookup"><span data-stu-id="36188-138">Click the **Disconnect** button to return to the *Connect to a remote device* screen and attach to a different host.</span></span>

## <span data-ttu-id="36188-139">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="36188-139">Visual Studio Code</span></span>

<span data-ttu-id="36188-140">Debugger [for Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) VS Code 拡張機能を使用すると、Microsoft Edge で実行されているスクリプトを、Visual Studio Code で直接デバッグできます。</span><span class="sxs-lookup"><span data-stu-id="36188-140">With the [Debugger for Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) VS Code extension, you can debug script running in Microsoft Edge directly in Visual Studio Code.</span></span> <span data-ttu-id="36188-141">この拡張機能では、localhost から Web アプリケーションを提供する必要があります。このサービスは、コマンドラインまたはタスクから開始 [できます](https://code.visualstudio.com/docs/editor/tasks)。</span><span class="sxs-lookup"><span data-stu-id="36188-141">The extension requires you to be serving your web application from localhost, which you can start from either command-line or a [Task](https://code.visualstudio.com/docs/editor/tasks).</span></span>

<span data-ttu-id="36188-142">次の手順をお試しください。</span><span class="sxs-lookup"><span data-stu-id="36188-142">To get started:</span></span>

1. <span data-ttu-id="36188-143">Debugger [for Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) VS Code 拡張機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="36188-143">Install the [Debugger for Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) VS Code extension.</span></span>

2. <span data-ttu-id="36188-144">VS Code を再起動し、デバッグするプロジェクトを含むフォルダーを開き、コードにブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="36188-144">Restart VS Code, open the folder containing the project you wish to debug and set breakpoints in your code.</span></span>

3. <span data-ttu-id="36188-145">localhost 起動タスク[を構成して](https://code.visualstudio.com/docs/editor/debugging#_launch-configurations)、プロジェクトの目的のページである [**デバッグ**構成の追加]  >  **を開きます**。例えば：</span><span class="sxs-lookup"><span data-stu-id="36188-145">Configure a localhost [launch task](https://code.visualstudio.com/docs/editor/debugging#_launch-configurations) to open the desired page of your project: **Debug** > **Add Configuration...**. For example:</span></span>

    ```json
    {
        "version": "0.2.0",
        "configurations": [

            {
                "name": "Launch localhost",
                "type": "edge",
                "request": "launch",
                "url": "http://localhost/mypage.html",
                "webRoot": "${workspaceFolder}/wwwroot"
            }
        ]
    }
    ```

    <span data-ttu-id="36188-146">[*デバッガーの使用には、*](https://github.com/Microsoft/vscode-edge-debug2#using-the-debugger) 起動構成設定の詳細があります。</span><span class="sxs-lookup"><span data-stu-id="36188-146">[*Using the debugger*](https://github.com/Microsoft/vscode-edge-debug2#using-the-debugger) has more on launch configuration settings.</span></span> 

4. <span data-ttu-id="36188-147">localhost でサーバーを起動し、[デバッグの開始 **(再生** ) ボタンを押す、または Microsoft `F5` Edge を起動します。</span><span class="sxs-lookup"><span data-stu-id="36188-147">Start your server on localhost and press the **Start Debugging** (play) button or `F5` to launch Microsoft Edge.</span></span> <span data-ttu-id="36188-148">ブレークポイントにヒットすると、VS Code に分割し、そこからさらにコードを検査してステップ実行できます。</span><span class="sxs-lookup"><span data-stu-id="36188-148">When a breakpoint is hit, you'll break into VS Code and can further inspect and step through code from there.</span></span>

<span data-ttu-id="36188-149">詳細については [、MICROSOFT Edge のドキュメントの VS Code デバッガーを参照](https://github.com/Microsoft/vscode-edge-debug2#----vs-code---debugger-for-microsoft-edge--) してください。</span><span class="sxs-lookup"><span data-stu-id="36188-149">For more, check out the [VS Code - Debugger for Microsoft Edge](https://github.com/Microsoft/vscode-edge-debug2#----vs-code---debugger-for-microsoft-edge--) documentation.</span></span>

## <span data-ttu-id="36188-150">Microsoft Visual Studio</span><span class="sxs-lookup"><span data-stu-id="36188-150">Microsoft Visual Studio</span></span>

<span data-ttu-id="36188-151">[Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763)で実行されている最新の[**Visual Studio**](https://www.visualstudio.com)バージョン (Visual Studio 15.8 以降) を使用すると、任意の ASP.NET または .NET Core プロジェクトで IDE から Microsoft Edge を起動してデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="36188-151">Using the latest [**Visual Studio**](https://www.visualstudio.com) version (Visual Studio 15.8 or later) running on [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763), you can launch and debug Microsoft Edge from the IDE on any ASP.NET or .NET Core project.</span></span>

<span data-ttu-id="36188-152">Microsoft Edge のデバッグをセットアップする方法を次に示Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="36188-152">Here's how to set up Microsoft Edge debugging with Visual Studio:</span></span>

1.  <span data-ttu-id="36188-153">最新のバージョンをインストールして [**起動Visual Studio**](https://www.visualstudio.com/) (Visual Studio 15.8 以降)。</span><span class="sxs-lookup"><span data-stu-id="36188-153">Install and launch the latest [**Visual Studio**](https://www.visualstudio.com/) (Visual Studio 15.8 or later).</span></span>

2. <span data-ttu-id="36188-154">**Visual C#** .NET ASP.NETを使用して、既存\*\*\*\* のプロジェクトまたは .NET Core プロジェクトを開く、または新しいプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="36188-154">Open an existing ASP.NET or .NET Core project or **Create new project...** using one of the **Visual C#** .NET templates.</span></span>

3. <span data-ttu-id="36188-155">プロジェクト ソリューション エクスプローラー **で**、デバッグする JavaScript ファイルを開き、サーバー側コードと同様に IDE 内にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="36188-155">In the project **Solution Explorer**, open the JavaScript files you wish to debug and set breakpoints within the IDE just as you would with server-side code.</span></span>

4. <span data-ttu-id="36188-156">`F5`DevTools Server を実行している Microsoft Edge を押して起動します。</span><span class="sxs-lookup"><span data-stu-id="36188-156">Press `F5` to launch Microsoft Edge running the DevTools Server.</span></span> <span data-ttu-id="36188-157">ブレークポイントにヒットすると、ブレークポイントに分割Visual Studio、そこからコードをさらに検査してステップ実行できます。</span><span class="sxs-lookup"><span data-stu-id="36188-157">When a breakpoint is hit, you'll break into Visual Studio and can further inspect and step through the code from there.</span></span>
