---
description: Microsoft Edge DevTools プロトコルバージョン0.1 では、次のツールクライアントがサポートされています。
title: DevTools プロトコルバージョン0.1 クライアント (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 5fdf375634bb63c944b3fe09d1c0cbd5a935dcd7
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882766"
---
# <span data-ttu-id="334ee-103">DevTools プロトコルバージョン0.1 クライアント (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="334ee-103">DevTools Protocol Version 0.1 Clients (EdgeHTML)</span></span>  

> [!NOTE]
> <span data-ttu-id="334ee-104">Microsoft Edge の DevTools プロトコルは、 [windows 10 年4月の2018更新プログラム](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97)以降の[windows Insider Preview](https://insider.windows.com/en-us/getting-started/)ビルドでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="334ee-104">The Microsoft Edge DevTools Protocol works only on [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) and later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) builds.</span></span>

<span data-ttu-id="334ee-105">**Devtools プロトコル 0.1**では、次のツールクライアントがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="334ee-105">**DevTools Protocol 0.1** supports the following tooling clients.</span></span>

<span data-ttu-id="334ee-106">[ ![ Microsoft Edge devtools](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [ ![ microsoft Visual Studio 15.7 preview 2](../media/visual-studio-2017.png)](#microsoft-visual-studio-preview)のプレビュー</span><span class="sxs-lookup"><span data-stu-id="334ee-106">[![Microsoft Edge DevTools Preview](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [![Microsoft Visual Studio 15.7 Preview 2](../media/visual-studio-2017.png)](#microsoft-visual-studio-preview)</span></span>

## <span data-ttu-id="334ee-107">Microsoft Edge DevTools プレビュー</span><span class="sxs-lookup"><span data-stu-id="334ee-107">Microsoft Edge DevTools Preview</span></span>

<span data-ttu-id="334ee-108">Microsoft Store からスタンドアロンの[**Microsoft Edge DevTools Preview**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) Windows 10 アプリを使用して、microsoft Edge ([EdgeHTML 17](../../dev-guide.md)以降) を実行しているホストデバイスをリモートでデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="334ee-108">You can use the standalone [**Microsoft Edge DevTools Preview**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) Windows 10 app from the Microsoft Store to remotely debug a host device running Microsoft Edge ([EdgeHTML 17](../../dev-guide.md) or later).</span></span>

<span data-ttu-id="334ee-109">DevTools プロトコルのこの暫定バージョン0.1 リリースでは、ブレークポイントの設定、コードのステップ実行、スタックトレースの表示など、基本的なデバッグ機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="334ee-109">This preliminary Version 0.1 release of the DevTools Protocol provides core debugging functionality, such as setting breakpoints, stepping through code, and exploring stack traces.</span></span> <span data-ttu-id="334ee-110">エッジ DevTools UI では、[**デバッガー**](../../devtools-guide/debugger.md)パネルで使用可能な機能、マイナスキャッシュ検査 (Web ストレージ、Service Worker、cache API、IndexedDB) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="334ee-110">In the Edge DevTools UI, this translates to functionality available in the [**Debugger**](../../devtools-guide/debugger.md) panel, minus cache inspection (for Web storage, Service worker, Cache API, and IndexedDB).</span></span> <span data-ttu-id="334ee-111">現在、Microsoft Edge リモートデバッグはデスクトップホストに制限されており、今後のリリースで登場する他の Windows 10 デバイスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="334ee-111">Currently Microsoft Edge remote debugging is limited to desktop hosts, with support for other Windows 10 devices coming in future releases.</span></span>

<span data-ttu-id="334ee-112">Microsoft Edge DevTools Preview アプリを使ったリモートデバッグのセットアップ方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="334ee-112">Here's how to set up remote debugging with the Microsoft Edge DevTools Preview app.</span></span> <span data-ttu-id="334ee-113">DevTools プロトコルは preview になっており、 [windows 10 年 4 2018 月の更新プログラム](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97)または、ホスト (debugee) コンピューター上の Windows Insider preview ビルドを後で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="334ee-113">The DevTools Protocol is in preview and requires [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) or a later Windows Insider Preview build on the host (debugee) machine.</span></span> <span data-ttu-id="334ee-114">(デバッガーコンピューターで使用されている) Edge の DevTools プレビューアプリは、アプリの作成者の更新 (バージョン 1709) および Windows Insider Preview ビルドで実行されます。</span><span class="sxs-lookup"><span data-stu-id="334ee-114">The Edge DevTools Preview app (used on the debugger machine) will run on Fall Creators Update (version 1709) and Windows Insider Preview builds.</span></span>

**<span data-ttu-id="334ee-115">ホスト (debugee) マシンの場合...</span><span class="sxs-lookup"><span data-stu-id="334ee-115">On the host (debugee) machine...</span></span>**

1. <span data-ttu-id="334ee-116">WiFi ネットワークを使用している場合は、ネットワークが [**ドメイン**] または [**プライベート**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="334ee-116">If you're on a WiFi network, ensure the network is marked as either **Domain** or **Private**.</span></span> <span data-ttu-id="334ee-117">これを確認するには、 [**Windows Defender セキュリティセンター**](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)アプリを開き、[**ファイアウォール & ネットワーク保護**] をクリックして、使用しているネットワークが*ドメインネットワーク*と*プライベートネットワーク*のどちらであるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="334ee-117">You can verify this by opening the [**Windows Defender Security Center**](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) app, clicking on **Firewall & network protection** and checking if your network is listed as a *Domain network* or *Private network*.</span></span> 

    <span data-ttu-id="334ee-118">*パブリック*として表示されている場合は、[**設定**  >  **ネットワーク & インターネット**  >  **wi-fi**] に移動して、ネットワークをクリックし、[*ネットワークプロファイル*] ボタンを [**プライベート**] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="334ee-118">If its listed as *Public*, go to **Settings** > **Network & Internet** > **Wi-Fi**, click on your network and toggle the *Network profile* button to **Private**.</span></span>

2. <span data-ttu-id="334ee-119">Windows の [*設定*] (*開発*者を検索して [*開発者向け機能を使用*] をクリックします) の [**開発者向け**] コントロールパネルを開き、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="334ee-119">Open the **For developers** control panel in Windows *Settings* (search for *developer* and click on *Use developer features*), and:</span></span> 

    <span data-ttu-id="334ee-120">a. </span><span class="sxs-lookup"><span data-stu-id="334ee-120">a.</span></span> <span data-ttu-id="334ee-121">**開発者モード**で切り替えます。</span><span class="sxs-lookup"><span data-stu-id="334ee-121">Toggle on **Developer Mode**.</span></span> <span data-ttu-id="334ee-122">これにより、*開発者モード*パッケージがインストールされ、デスクトップのリモートツールが有効になります。</span><span class="sxs-lookup"><span data-stu-id="334ee-122">This will install the *Developer Mode* package, enabling remote tooling for desktop.</span></span>

    <span data-ttu-id="334ee-123">b. </span><span class="sxs-lookup"><span data-stu-id="334ee-123">b.</span></span> <span data-ttu-id="334ee-124">[**Device Portal**](/windows/uwp/debug-test-perf/device-portal)を有効にする (*ローカルエリアネットワーク接続経由のリモート診断を有効*にする) と**デバイス検出**(*デバイスを USB 接続とローカルネットワークから認識できるよう*にします)。</span><span class="sxs-lookup"><span data-stu-id="334ee-124">Enable [**Device Portal**](/windows/uwp/debug-test-perf/device-portal) (*Turn on remote diagnostics over local area network connections*) and **Device discovery** (*Make your device visible to USB connections and your local network*).</span></span>

    <span data-ttu-id="334ee-125">c. </span><span class="sxs-lookup"><span data-stu-id="334ee-125">c.</span></span> <span data-ttu-id="334ee-126">**認証**を有効にして、ユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="334ee-126">Turn on **Authentication** and supply a username / password.</span></span>

    <span data-ttu-id="334ee-127">d. </span><span class="sxs-lookup"><span data-stu-id="334ee-127">d.</span></span> <span data-ttu-id="334ee-128">コンピューターの IP アドレスと接続ポート (50443) が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="334ee-128">Note the machine IP address and connection port (50443) displayed.</span></span>

3. <span data-ttu-id="334ee-129">クライアントコンピューターからデバッグするタブを Microsoft Edge で開きます。</span><span class="sxs-lookup"><span data-stu-id="334ee-129">Open tabs in Microsoft Edge that you wish to debug from the client machine.</span></span>

**<span data-ttu-id="334ee-130">クライアント (デバッガー) コンピューターで...</span><span class="sxs-lookup"><span data-stu-id="334ee-130">On the client (debugger) machine...</span></span>**

1.  <span data-ttu-id="334ee-131">Microsoft Store からスタンドアロンの[Microsoft Edge DevTools プレビュー](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab)アプリをインストールして起動します。</span><span class="sxs-lookup"><span data-stu-id="334ee-131">Install and launch the standalone [Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) app from the Microsoft Store.</span></span>

2. <span data-ttu-id="334ee-132">**リモート**パネルを開き、ホストコンピューターのネットワークの場所 (URL とポート) を入力して、[**接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="334ee-132">Open the **Remote** panel and enter the network location (URL and port) of the host machine and click **Connect**.</span></span>

3. <span data-ttu-id="334ee-133">表示される [信頼されてい*ない証明書*] ダイアログからホストコンピューターの証明書を**インストール**します。</span><span class="sxs-lookup"><span data-stu-id="334ee-133">**Install** the host machine's certificate from the *Untrusted Certificate* dialog that appears.</span></span>

4. <span data-ttu-id="334ee-134">Device Portal の認証用に指定したユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="334ee-134">Supply the username/password you designated for Device Portal authentication.</span></span>

5. <span data-ttu-id="334ee-135">*リモート*パネルでは、ホストコンピューター上のデバッグ可能なページターゲットの一覧が読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="334ee-135">The *Remote* panel will load a list of debuggable page targets on the host machine.</span></span> <span data-ttu-id="334ee-136">いずれかを選択してデバッグを開始します。</span><span class="sxs-lookup"><span data-stu-id="334ee-136">Select one to start debugging.</span></span>

6. <span data-ttu-id="334ee-137">[**更新**] ボタンを使用して、ホストコンピューター上のリモートページターゲットの一覧を更新して再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="334ee-137">Use the **Refresh** button to update and reload the list of remote page targets on the host machine.</span></span> <span data-ttu-id="334ee-138">[**切断**] ボタンをクリックして、[*リモートデバイスへの接続*] 画面に戻り、別のホストに接続します。</span><span class="sxs-lookup"><span data-stu-id="334ee-138">Click the **Disconnect** button to return to the *Connect to a remote device* screen and attach to a different host.</span></span>

## <span data-ttu-id="334ee-139">Microsoft Visual Studio Preview</span><span class="sxs-lookup"><span data-stu-id="334ee-139">Microsoft Visual Studio Preview</span></span>

<span data-ttu-id="334ee-140">最新の[**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/)ビルド (visual Studio 15.7 preview 1 以降) を使用して、ASP.NET または .net コアプロジェクトの IDE から Microsoft Edge を起動してデバッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="334ee-140">Using the latest [**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/) build (Visual Studio 15.7 Preview 1 or later), you can launch and debug Microsoft Edge from the IDE on any ASP.NET or .NET Core project.</span></span> <span data-ttu-id="334ee-141">現在、DevTools プロトコルはプレビューに含まれており、 [Windows Insider preview](https://insider.windows.com/en-us/getting-started/)ビルドを実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="334ee-141">The DevTools Protocol is currently in preview and requires you to be running a [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) build.</span></span>

<span data-ttu-id="334ee-142">Visual Studio で Microsoft Edge のデバッグを設定する方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="334ee-142">Here's how to set up Microsoft Edge debugging with Visual Studio:</span></span>

1.  <span data-ttu-id="334ee-143">最新の[**Visual Studio preview**](https://www.visualstudio.com/vs/preview/)ビルド (visual Studio 15.7 preview 1 以降) をインストールして起動します。</span><span class="sxs-lookup"><span data-stu-id="334ee-143">Install and launch the latest [**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/) build (Visual Studio 15.7 Preview 1 or later).</span></span>

2. <span data-ttu-id="334ee-144">**Visual C#** .net テンプレートのいずれかを使用して、既存の ASP.NET または .net コアプロジェクトを開くか、**新しいプロジェクトを作成します。**</span><span class="sxs-lookup"><span data-stu-id="334ee-144">Open an existing ASP.NET or .NET Core project or **Create new project...** using one of the **Visual C#** .NET templates.</span></span>

3. <span data-ttu-id="334ee-145">プロジェクト**ソリューションエクスプローラー**で、デバッグする JavaScript ファイルを開き、サーバー側コードの場合と同様に、IDE でブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="334ee-145">In the project **Solution Explorer**, open the JavaScript files you wish to debug and set breakpoints within the IDE just as you would with server-side code.</span></span>

4. <span data-ttu-id="334ee-146">を押して `F5` 、DevTools サーバーを実行している Microsoft Edge を起動します。</span><span class="sxs-lookup"><span data-stu-id="334ee-146">Press `F5` to launch Microsoft Edge running the DevTools Server.</span></span> <span data-ttu-id="334ee-147">ブレークポイントにヒットすると、Visual Studio にブレークし、そこからコードをさらに調べていくことができます。</span><span class="sxs-lookup"><span data-stu-id="334ee-147">When a breakpoint is hit, you'll break into Visual Studio and can further inspect and step through the code from there.</span></span>
