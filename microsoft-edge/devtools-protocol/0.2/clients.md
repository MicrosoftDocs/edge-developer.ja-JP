---
description: Microsoft Edge DevTools プロトコルバージョン0.2 では、次のツールクライアントがサポートされています。
title: Microsoft Edge DevTools プロトコルバージョン0.2 クライアント
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 657d594b85c47cc1d5c80b8f2ac3ecc4bd4e4502
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569615"
---
# <span data-ttu-id="57c83-103">DevTools プロトコルクライアント</span><span class="sxs-lookup"><span data-stu-id="57c83-103">DevTools Protocol Clients</span></span>

> [!NOTE]
> <span data-ttu-id="57c83-104">Microsoft Edge DevTools プロトコルのバージョン0.2 は、 [windows 10 年 2018 10 月の更新プログラム](/windows/uwp/whats-new/windows-10-build-17763)以降の[windows Insider Preview](https://insider.windows.com/en-us/getting-started/)ビルドでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="57c83-104">Version 0.2 of the Microsoft Edge DevTools Protocol works only on the [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) and later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) builds.</span></span>  

<span data-ttu-id="57c83-105">**Devtools プロトコル 0.2**では、次のツールクライアントがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="57c83-105">**DevTools Protocol 0.2** supports the following tooling clients.</span></span>

<span data-ttu-id="57c83-106">[ ![ Microsoft Edge devtools](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [ ![ visual studio コード](../media/visual-studio-code.png)](#visual-studio-code)のプレビュー [ ![ microsoft visual studio 15.8](../media/visual-studio-2017.png)](#microsoft-visual-studio)</span><span class="sxs-lookup"><span data-stu-id="57c83-106">[![Microsoft Edge DevTools Preview](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [![Visual Studio Code](../media/visual-studio-code.png)](#visual-studio-code) [![Microsoft Visual Studio 15.8](../media/visual-studio-2017.png)](#microsoft-visual-studio)</span></span>

## <span data-ttu-id="57c83-107">Microsoft Edge DevTools プレビュー</span><span class="sxs-lookup"><span data-stu-id="57c83-107">Microsoft Edge DevTools Preview</span></span>

<span data-ttu-id="57c83-108">Microsoft Store からスタンドアロンの[**Microsoft Edge DevTools Preview**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) Windows 10 アプリを使用して、microsoft Edge ([EdgeHTML 17](../../dev-guide.md)以降) を実行しているホストデバイスをリモートでデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="57c83-108">You can use the standalone [**Microsoft Edge DevTools Preview**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) Windows 10 app from the Microsoft Store to remotely debug a host device running Microsoft Edge ([EdgeHTML 17](../../dev-guide.md) or later).</span></span>

<span data-ttu-id="57c83-109">DevTools プロトコルのバージョン0.2 には、バージョン0.1 で導入されたコアスクリプトのデバッグ機能に加えて、スタイルとレイアウトのデバッグとコンソール Api の新しいドメインが用意されています。</span><span class="sxs-lookup"><span data-stu-id="57c83-109">Version 0.2 of the DevTools Protocol provides new domains for style and layout debugging and console APIs, in addition to the core script debugging functionality introduced in Version 0.1.</span></span> <span data-ttu-id="57c83-110">Edge の DevTools UI では、これは[**要素**](../../devtools-guide/elements.md)、[**コンソール**](../../devtools-guide/console.md)、[**デバッガー**](../../devtools-guide/debugger.md)パネルで利用できる機能に変換されます。</span><span class="sxs-lookup"><span data-stu-id="57c83-110">In the Edge DevTools UI, this translates to functionality available in the [**Elements**](../../devtools-guide/elements.md), [**Console**](../../devtools-guide/console.md) and [**Debugger**](../../devtools-guide/debugger.md) panels.</span></span> <span data-ttu-id="57c83-111">現在、Microsoft Edge リモートデバッグはデスクトップホストに制限されており、今後のリリースで登場する他の Windows 10 デバイスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="57c83-111">Currently Microsoft Edge remote debugging is limited to desktop hosts, with support for other Windows 10 devices coming in future releases.</span></span>

<span data-ttu-id="57c83-112">Microsoft Edge DevTools Preview アプリを使ったリモートデバッグのセットアップ方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="57c83-112">Here's how to set up remote debugging with the Microsoft Edge DevTools Preview app.</span></span> <span data-ttu-id="57c83-113">DevTools Protocol バージョン0.2 では、 [windows 10 年10月の2018更新プログラム](/windows/uwp/whats-new/windows-10-build-17763)またはホスト (debugee) コンピューター上の Windows Insider Preview ビルドが必要です。</span><span class="sxs-lookup"><span data-stu-id="57c83-113">The DevTools Protocol version 0.2 requires [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) or a later Windows Insider Preview build on the host (debugee) machine.</span></span> <span data-ttu-id="57c83-114">(デバッガーコンピューターで使用される) Edge の DevTools プレビューアプリは、Windows 10 バージョン 16299 (Windows 10 は、作成者向け更新プログラム、10/2017) 以上で動作します。</span><span class="sxs-lookup"><span data-stu-id="57c83-114">The Edge DevTools Preview app (used on the debugger machine) will run on Windows 10 version 16299 (Windows 10 Fall Creators Update, 10/2017) or higher.</span></span>

**<span data-ttu-id="57c83-115">ホスト (debugee) マシンの場合...</span><span class="sxs-lookup"><span data-stu-id="57c83-115">On the host (debugee) machine...</span></span>**

1. <span data-ttu-id="57c83-116">WiFi ネットワークを使用している場合は、ネットワークが [**ドメイン**] または [**プライベート**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="57c83-116">If you're on a WiFi network, ensure the network is marked as either **Domain** or **Private**.</span></span> <span data-ttu-id="57c83-117">これを確認するには、 [**Windows Defender セキュリティセンター**](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)アプリを開き、[**ファイアウォール & ネットワーク保護**] をクリックして、使用しているネットワークが*ドメインネットワーク*と*プライベートネットワーク*のどちらであるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="57c83-117">You can verify this by opening the [**Windows Defender Security Center**](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) app, clicking on **Firewall & network protection** and checking if your network is listed as a *Domain network* or *Private network*.</span></span> 

    <span data-ttu-id="57c83-118">*パブリック*として表示されている場合は、[**設定**  >  **ネットワーク & インターネット**  >  **wi-fi**] に移動して、ネットワークをクリックし、[*ネットワークプロファイル*] ボタンを [**プライベート**] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="57c83-118">If its listed as *Public*, go to **Settings** > **Network & Internet** > **Wi-Fi**, click on your network and toggle the *Network profile* button to **Private**.</span></span>

2. <span data-ttu-id="57c83-119">Windows の [*設定*] (*開発*者を検索して [*開発者向け機能を使用*] をクリックします) の [**開発者向け**] コントロールパネルを開き、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="57c83-119">Open the **For developers** control panel in Windows *Settings* (search for *developer* and click on *Use developer features*), and:</span></span> 

    <span data-ttu-id="57c83-120">a. </span><span class="sxs-lookup"><span data-stu-id="57c83-120">a.</span></span> <span data-ttu-id="57c83-121">**開発者モード**で切り替えます。</span><span class="sxs-lookup"><span data-stu-id="57c83-121">Toggle on **Developer Mode**.</span></span> <span data-ttu-id="57c83-122">これにより、*開発者モード*パッケージがインストールされ、デスクトップのリモートツールが有効になります。</span><span class="sxs-lookup"><span data-stu-id="57c83-122">This will install the *Developer Mode* package, enabling remote tooling for desktop.</span></span>

    <span data-ttu-id="57c83-123">b. </span><span class="sxs-lookup"><span data-stu-id="57c83-123">b.</span></span> <span data-ttu-id="57c83-124">[**Device Portal**](/windows/uwp/debug-test-perf/device-portal)を有効にする (*ローカルエリアネットワーク接続経由のリモート診断を有効*にする) と**デバイス検出**(*デバイスを USB 接続とローカルネットワークから認識できるよう*にします)。</span><span class="sxs-lookup"><span data-stu-id="57c83-124">Enable [**Device Portal**](/windows/uwp/debug-test-perf/device-portal) (*Turn on remote diagnostics over local area network connections*) and **Device discovery** (*Make your device visible to USB connections and your local network*).</span></span>

    <span data-ttu-id="57c83-125">c. </span><span class="sxs-lookup"><span data-stu-id="57c83-125">c.</span></span> <span data-ttu-id="57c83-126">**認証**を有効にして、ユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="57c83-126">Turn on **Authentication** and supply a username / password.</span></span>

    <span data-ttu-id="57c83-127">d. </span><span class="sxs-lookup"><span data-stu-id="57c83-127">d.</span></span> <span data-ttu-id="57c83-128">コンピューターの IP アドレスと接続ポート (50443) が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="57c83-128">Note the machine IP address and connection port (50443) displayed.</span></span>

3. <span data-ttu-id="57c83-129">クライアントコンピューターからデバッグするタブを Microsoft Edge で開きます。</span><span class="sxs-lookup"><span data-stu-id="57c83-129">Open tabs in Microsoft Edge that you wish to debug from the client machine.</span></span>

**<span data-ttu-id="57c83-130">クライアント (デバッガー) コンピューターで...</span><span class="sxs-lookup"><span data-stu-id="57c83-130">On the client (debugger) machine...</span></span>**

1.  <span data-ttu-id="57c83-131">Microsoft Store からスタンドアロンの[Microsoft Edge DevTools プレビュー](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab)アプリをインストールして起動します。</span><span class="sxs-lookup"><span data-stu-id="57c83-131">Install and launch the standalone [Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) app from the Microsoft Store.</span></span>

2. <span data-ttu-id="57c83-132">**リモート**パネルを開き、ホストコンピューターのネットワークの場所 (URL とポート) を入力して、[**接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57c83-132">Open the **Remote** panel and enter the network location (URL and port) of the host machine and click **Connect**.</span></span>

3. <span data-ttu-id="57c83-133">表示される [信頼されてい*ない証明書*] ダイアログからホストコンピューターの証明書を**インストール**します。</span><span class="sxs-lookup"><span data-stu-id="57c83-133">**Install** the host machine's certificate from the *Untrusted Certificate* dialog that appears.</span></span>

4. <span data-ttu-id="57c83-134">Device Portal の認証用に指定したユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="57c83-134">Supply the username/password you designated for Device Portal authentication.</span></span>

5. <span data-ttu-id="57c83-135">*リモート*パネルでは、ホストコンピューター上のデバッグ可能なページターゲットの一覧が読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="57c83-135">The *Remote* panel will load a list of debuggable page targets on the host machine.</span></span> <span data-ttu-id="57c83-136">いずれかを選択してデバッグを開始します。</span><span class="sxs-lookup"><span data-stu-id="57c83-136">Select one to start debugging.</span></span>

6. <span data-ttu-id="57c83-137">[**更新**] ボタンを使用して、ホストコンピューター上のリモートページターゲットの一覧を更新して再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="57c83-137">Use the **Refresh** button to update and reload the list of remote page targets on the host machine.</span></span> <span data-ttu-id="57c83-138">[**切断**] ボタンをクリックして、[*リモートデバイスへの接続*] 画面に戻り、別のホストに接続します。</span><span class="sxs-lookup"><span data-stu-id="57c83-138">Click the **Disconnect** button to return to the *Connect to a remote device* screen and attach to a different host.</span></span>

## <span data-ttu-id="57c83-139">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="57c83-139">Visual Studio Code</span></span>

<span data-ttu-id="57c83-140">Microsoft Edge で実行されている Edge とコード拡張[用のデバッガー](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge)を使うと、Visual Studio コードで直接 Microsoft Edge で実行されているスクリプトをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="57c83-140">With the [Debugger for Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) VS Code extension, you can debug script running in Microsoft Edge directly in Visual Studio Code.</span></span> <span data-ttu-id="57c83-141">拡張機能を使用するには、web アプリケーションが localhost から提供されている必要があります。これは、コマンドラインまたは[タスク](https://code.visualstudio.com/docs/editor/tasks)から開始できます。</span><span class="sxs-lookup"><span data-stu-id="57c83-141">The extension requires you to be serving your web application from localhost, which you can start from either command-line or a [Task](https://code.visualstudio.com/docs/editor/tasks).</span></span>

<span data-ttu-id="57c83-142">次の手順をお試しください。</span><span class="sxs-lookup"><span data-stu-id="57c83-142">To get started:</span></span>

1. <span data-ttu-id="57c83-143">Edge VS コード拡張[用のデバッガーを](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge)インストールします。</span><span class="sxs-lookup"><span data-stu-id="57c83-143">Install the [Debugger for Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) VS Code extension.</span></span>

2. <span data-ttu-id="57c83-144">VS コードを再起動し、デバッグするプロジェクトが含まれているフォルダーを開き、コードにブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="57c83-144">Restart VS Code, open the folder containing the project you wish to debug and set breakpoints in your code.</span></span>

3. <span data-ttu-id="57c83-145">Localhost[起動タスク](https://code.visualstudio.com/docs/editor/debugging#_launch-configurations)を構成して、プロジェクトの目的のページを開きます。**デバッグ**:  >  **構成の追加...** 例えば：</span><span class="sxs-lookup"><span data-stu-id="57c83-145">Configure a localhost [launch task](https://code.visualstudio.com/docs/editor/debugging#_launch-configurations) to open the desired page of your project: **Debug** > **Add Configuration...**. For example:</span></span>

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

    <span data-ttu-id="57c83-146">[*デバッガーの使用*](https://github.com/Microsoft/vscode-edge-debug2#using-the-debugger)について詳しくは、「起動構成の設定」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="57c83-146">[*Using the debugger*](https://github.com/Microsoft/vscode-edge-debug2#using-the-debugger) has more on launch configuration settings.</span></span> 

4. <span data-ttu-id="57c83-147">Localhost でサーバーを起動し、[**デバッグの開始**] (再生) ボタンを押すか、 `F5` Microsoft Edge を起動します。</span><span class="sxs-lookup"><span data-stu-id="57c83-147">Start your server on localhost and press the **Start Debugging** (play) button or `F5` to launch Microsoft Edge.</span></span> <span data-ttu-id="57c83-148">ブレークポイントにヒットすると、VS コードにブレークし、そこからコードをさらに検査していくことができます。</span><span class="sxs-lookup"><span data-stu-id="57c83-148">When a breakpoint is hit, you'll break into VS Code and can further inspect and step through code from there.</span></span>

<span data-ttu-id="57c83-149">詳細については、 [Microsoft Edge ドキュメントの VS コードデバッガーを](https://github.com/Microsoft/vscode-edge-debug2#----vs-code---debugger-for-microsoft-edge--)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="57c83-149">For more, check out the [VS Code - Debugger for Microsoft Edge](https://github.com/Microsoft/vscode-edge-debug2#----vs-code---debugger-for-microsoft-edge--) documentation.</span></span>

## <span data-ttu-id="57c83-150">Microsoft Visual Studio</span><span class="sxs-lookup"><span data-stu-id="57c83-150">Microsoft Visual Studio</span></span>

<span data-ttu-id="57c83-151">[Windows 10 年 2018 10 月の更新プログラム](/windows/uwp/whats-new/windows-10-build-17763)で実行されている最新の[**visual Studio**](https://www.visualstudio.com)バージョン (visual studio 15.8 以降) を使用している場合は、ASP.NET または .net のコアプロジェクトの IDE で Microsoft Edge を起動してデバッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="57c83-151">Using the latest [**Visual Studio**](https://www.visualstudio.com) version (Visual Studio 15.8 or later) running on [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763), you can launch and debug Microsoft Edge from the IDE on any ASP.NET or .NET Core project.</span></span>

<span data-ttu-id="57c83-152">Visual Studio で Microsoft Edge のデバッグを設定する方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="57c83-152">Here's how to set up Microsoft Edge debugging with Visual Studio:</span></span>

1.  <span data-ttu-id="57c83-153">最新の[**Visual studio**](https://www.visualstudio.com/)をインストールして起動します (visual studio 15.8 以降)。</span><span class="sxs-lookup"><span data-stu-id="57c83-153">Install and launch the latest [**Visual Studio**](https://www.visualstudio.com/) (Visual Studio 15.8 or later).</span></span>

2. <span data-ttu-id="57c83-154">**Visual C#** .net テンプレートのいずれかを使用して、既存の ASP.NET または .net コアプロジェクトを開くか、**新しいプロジェクトを作成します。**</span><span class="sxs-lookup"><span data-stu-id="57c83-154">Open an existing ASP.NET or .NET Core project or **Create new project...** using one of the **Visual C#** .NET templates.</span></span>

3. <span data-ttu-id="57c83-155">プロジェクト**ソリューションエクスプローラー**で、デバッグする JavaScript ファイルを開き、サーバー側コードの場合と同様に、IDE でブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="57c83-155">In the project **Solution Explorer**, open the JavaScript files you wish to debug and set breakpoints within the IDE just as you would with server-side code.</span></span>

4. <span data-ttu-id="57c83-156">を押して `F5` 、DevTools サーバーを実行している Microsoft Edge を起動します。</span><span class="sxs-lookup"><span data-stu-id="57c83-156">Press `F5` to launch Microsoft Edge running the DevTools Server.</span></span> <span data-ttu-id="57c83-157">ブレークポイントにヒットすると、Visual Studio にブレークし、そこからコードをさらに調べていくことができます。</span><span class="sxs-lookup"><span data-stu-id="57c83-157">When a breakpoint is hit, you'll break into Visual Studio and can further inspect and step through the code from there.</span></span>
