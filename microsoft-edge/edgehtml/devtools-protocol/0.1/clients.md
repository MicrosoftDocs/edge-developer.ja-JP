---
description: Microsoft Edge DevTools Protocol Version 0.1 は、次のツール クライアントをサポートしています。
title: DevTools プロトコル バージョン 0.1 クライアント (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cb7355524ec6dab5cf0275538c5b0c030891d4a9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234427"
---
# <span data-ttu-id="1de41-103">DevTools プロトコル バージョン 0.1 クライアント (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="1de41-103">DevTools Protocol Version 0.1 Clients (EdgeHTML)</span></span>  

> [!NOTE]
> <span data-ttu-id="1de41-104">Microsoft Edge DevTools プロトコルは [、Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 以降の [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) ビルドでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="1de41-104">The Microsoft Edge DevTools Protocol works only on [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) and later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) builds.</span></span>

<span data-ttu-id="1de41-105">**DevTools Protocol 0.1 は、次** のツール クライアントをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1de41-105">**DevTools Protocol 0.1** supports the following tooling clients.</span></span>

<span data-ttu-id="1de41-106">[ ![ Microsoft Edge DevTools Preview](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [ ![ Microsoft Visual Studio 15.7 Preview 2](../media/visual-studio-2017.png)](#microsoft-visual-studio-preview)</span><span class="sxs-lookup"><span data-stu-id="1de41-106">[![Microsoft Edge DevTools Preview](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [![Microsoft Visual Studio 15.7 Preview 2](../media/visual-studio-2017.png)](#microsoft-visual-studio-preview)</span></span>

## <span data-ttu-id="1de41-107">Microsoft Edge DevTools プレビュー</span><span class="sxs-lookup"><span data-stu-id="1de41-107">Microsoft Edge DevTools Preview</span></span>

<span data-ttu-id="1de41-108">Microsoft Store からスタンドアロン [**の Microsoft Edge DevTools Preview**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) Windows 10 アプリを使用して、Microsoft Edge を実行しているホスト デバイス[(EdgeHTML 17](../../dev-guide/index.md) 以降) をリモートでデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="1de41-108">You can use the standalone [**Microsoft Edge DevTools Preview**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) Windows 10 app from the Microsoft Store to remotely debug a host device running Microsoft Edge ([EdgeHTML 17](../../dev-guide/index.md) or later).</span></span>

<span data-ttu-id="1de41-109">DevTools プロトコルのこの暫定的なバージョン 0.1 リリースは、ブレークポイントの設定、コードのステップ実行、スタック トレースの探索など、コア デバッグ機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="1de41-109">This preliminary Version 0.1 release of the DevTools Protocol provides core debugging functionality, such as setting breakpoints, stepping through code, and exploring stack traces.</span></span> <span data-ttu-id="1de41-110">Edge DevTools UI では、これはデバッガー パネルで使用可能な[](../../devtools-guide/debugger.md)機能 (Web ストレージ、サービス ワーカー、キャッシュ API、および IndexedDB の場合) からキャッシュ検査を差し引いた機能に変換されます。</span><span class="sxs-lookup"><span data-stu-id="1de41-110">In the Edge DevTools UI, this translates to functionality available in the [**Debugger**](../../devtools-guide/debugger.md) panel, minus cache inspection (for Web storage, Service worker, Cache API, and IndexedDB).</span></span> <span data-ttu-id="1de41-111">現在、Microsoft Edge のリモート デバッグはデスクトップ ホストに限定されています。今後のリリースで予定されている他の Windows 10 デバイスもサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1de41-111">Currently Microsoft Edge remote debugging is limited to desktop hosts, with support for other Windows 10 devices coming in future releases.</span></span>

<span data-ttu-id="1de41-112">Microsoft Edge DevTools Preview アプリを使ってリモート デバッグをセットアップする方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1de41-112">Here's how to set up remote debugging with the Microsoft Edge DevTools Preview app.</span></span> <span data-ttu-id="1de41-113">DevTools プロトコルはプレビュー中であり、ホスト (デバッグ先) コンピューター上に [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 以降の Windows Insider Preview ビルドが必要です。</span><span class="sxs-lookup"><span data-stu-id="1de41-113">The DevTools Protocol is in preview and requires [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) or a later Windows Insider Preview build on the host (debugee) machine.</span></span> <span data-ttu-id="1de41-114">Edge DevTools Preview アプリ (デバッガー コンピューターで使用) は、Fall Creators Update (バージョン 1709) ビルドと Windows Insider Preview ビルドで実行されます。</span><span class="sxs-lookup"><span data-stu-id="1de41-114">The Edge DevTools Preview app (used on the debugger machine) will run on Fall Creators Update (version 1709) and Windows Insider Preview builds.</span></span>

**<span data-ttu-id="1de41-115">ホスト (デバッグ先) コンピューターで...</span><span class="sxs-lookup"><span data-stu-id="1de41-115">On the host (debugee) machine...</span></span>**

1. <span data-ttu-id="1de41-116">WiFi ネットワークを使用している場合は、ネットワークがドメインまたはプライベートとして **マーク付け** されている必要 **があります**。</span><span class="sxs-lookup"><span data-stu-id="1de41-116">If you're on a WiFi network, ensure the network is marked as either **Domain** or **Private**.</span></span> <span data-ttu-id="1de41-117">これを確認するには[**、Windows Defender**](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)セキュリティ センター アプリを開き、**ファイアウォール &** ネットワーク保護をクリックし、ネットワークがドメイン ネットワークまたはプライベート ネットワークとして 一覧表示されるのか確認*します。*</span><span class="sxs-lookup"><span data-stu-id="1de41-117">You can verify this by opening the [**Windows Defender Security Center**](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) app, clicking on **Firewall & network protection** and checking if your network is listed as a *Domain network* or *Private network*.</span></span> 

    <span data-ttu-id="1de41-118">If its listed as *Public,* go to **Settings**  >  **Network & Internet**  >  **Wi-Fi,** click on your network and toggle the Network *profile* button to **Private**.</span><span class="sxs-lookup"><span data-stu-id="1de41-118">If its listed as *Public*, go to **Settings** > **Network & Internet** > **Wi-Fi**, click on your network and toggle the *Network profile* button to **Private**.</span></span>

2. <span data-ttu-id="1de41-119">*Windows*の**設定で [開発者**向け] コントロール パネルを開き (開発者向けの検索を行い、[開発者向け機能の使用] をクリックします)、*次*の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1de41-119">Open the **For developers** control panel in Windows *Settings* (search for *developer* and click on *Use developer features*), and:</span></span> 

    <span data-ttu-id="1de41-120">a. </span><span class="sxs-lookup"><span data-stu-id="1de41-120">a.</span></span> <span data-ttu-id="1de41-121">開発者モードを **切り替えます**。</span><span class="sxs-lookup"><span data-stu-id="1de41-121">Toggle on **Developer Mode**.</span></span> <span data-ttu-id="1de41-122">これにより、開発者モード *パッケージがインストール* され、デスクトップ用のリモート ツールが有効になります。</span><span class="sxs-lookup"><span data-stu-id="1de41-122">This will install the *Developer Mode* package, enabling remote tooling for desktop.</span></span>

    <span data-ttu-id="1de41-123">b. </span><span class="sxs-lookup"><span data-stu-id="1de41-123">b.</span></span> <span data-ttu-id="1de41-124">[**Device Portal**](/windows/uwp/debug-test-perf/device-portal) (ローカル*エリア ネットワーク*接続でリモート診断を有効にする) とデバイス**検出を有効**にします (デバイスを USB 接続とローカル ネットワークに表示*します*)。</span><span class="sxs-lookup"><span data-stu-id="1de41-124">Enable [**Device Portal**](/windows/uwp/debug-test-perf/device-portal) (*Turn on remote diagnostics over local area network connections*) and **Device discovery** (*Make your device visible to USB connections and your local network*).</span></span>

    <span data-ttu-id="1de41-125">c. </span><span class="sxs-lookup"><span data-stu-id="1de41-125">c.</span></span> <span data-ttu-id="1de41-126">認証を **有効に** し、ユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="1de41-126">Turn on **Authentication** and supply a username / password.</span></span>

    <span data-ttu-id="1de41-127">d. </span><span class="sxs-lookup"><span data-stu-id="1de41-127">d.</span></span> <span data-ttu-id="1de41-128">コンピューターの IP アドレスと接続ポート (50443) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1de41-128">Note the machine IP address and connection port (50443) displayed.</span></span>

3. <span data-ttu-id="1de41-129">クライアント コンピューターからデバッグする Microsoft Edge のタブを開きます。</span><span class="sxs-lookup"><span data-stu-id="1de41-129">Open tabs in Microsoft Edge that you wish to debug from the client machine.</span></span>

**<span data-ttu-id="1de41-130">クライアント (デバッガー) コンピューターで...</span><span class="sxs-lookup"><span data-stu-id="1de41-130">On the client (debugger) machine...</span></span>**

1.  <span data-ttu-id="1de41-131">Microsoft Store からスタンドアロン [の Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) アプリをインストールして起動します。</span><span class="sxs-lookup"><span data-stu-id="1de41-131">Install and launch the standalone [Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) app from the Microsoft Store.</span></span>

2. <span data-ttu-id="1de41-132">リモート パネル **を開** き、ホスト マシンのネットワークの場所 (URL とポート) を入力し、[接続] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="1de41-132">Open the **Remote** panel and enter the network location (URL and port) of the host machine and click **Connect**.</span></span>

3. <span data-ttu-id="1de41-133">**[** 信頼されていない証明書] ダイアログボックスが表示 *されたら、ホスト コンピューターの* 証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="1de41-133">**Install** the host machine's certificate from the *Untrusted Certificate* dialog that appears.</span></span>

4. <span data-ttu-id="1de41-134">Device Portal 認証用に指定したユーザー名/パスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="1de41-134">Supply the username/password you designated for Device Portal authentication.</span></span>

5. <span data-ttu-id="1de41-135">リモート *パネル* は、デバッグ可能なページ ターゲットの一覧をホスト コンピューターに読み込む。</span><span class="sxs-lookup"><span data-stu-id="1de41-135">The *Remote* panel will load a list of debuggable page targets on the host machine.</span></span> <span data-ttu-id="1de41-136">デバッグを開始するには、1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="1de41-136">Select one to start debugging.</span></span>

6. <span data-ttu-id="1de41-137">[更新 **] ボタン** を使用して、ホスト コンピューター上のリモート ページ ターゲットの一覧を更新して再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="1de41-137">Use the **Refresh** button to update and reload the list of remote page targets on the host machine.</span></span> <span data-ttu-id="1de41-138">[切断 **]** ボタンをクリックして、リモート デバイスへの *接続画面に戻* り、別のホストに接続します。</span><span class="sxs-lookup"><span data-stu-id="1de41-138">Click the **Disconnect** button to return to the *Connect to a remote device* screen and attach to a different host.</span></span>

## <span data-ttu-id="1de41-139">Microsoft Visual Studio Preview</span><span class="sxs-lookup"><span data-stu-id="1de41-139">Microsoft Visual Studio Preview</span></span>

<span data-ttu-id="1de41-140">最新の [**Visual Studio プレビュー**](https://www.visualstudio.com/vs/preview/) ビルド (Visual Studio 15.7 Preview 1 以降) を使用すると、任意の ASP.NET または .NET Core プロジェクトで IDE から Microsoft Edge を起動してデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="1de41-140">Using the latest [**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/) build (Visual Studio 15.7 Preview 1 or later), you can launch and debug Microsoft Edge from the IDE on any ASP.NET or .NET Core project.</span></span> <span data-ttu-id="1de41-141">DevTools プロトコルは現在プレビュー中であり [、Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) ビルドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1de41-141">The DevTools Protocol is currently in preview and requires you to be running a [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) build.</span></span>

<span data-ttu-id="1de41-142">Microsoft Edge のデバッグをセットアップする方法を次に示Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="1de41-142">Here's how to set up Microsoft Edge debugging with Visual Studio:</span></span>

1.  <span data-ttu-id="1de41-143">最新の Visual Studio [**プレビュー ビルド**](https://www.visualstudio.com/vs/preview/) (Visual Studio 15.7 Preview 1 以降) をインストールして起動します。</span><span class="sxs-lookup"><span data-stu-id="1de41-143">Install and launch the latest [**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/) build (Visual Studio 15.7 Preview 1 or later).</span></span>

2. <span data-ttu-id="1de41-144">**Visual C#** .NET ASP.NETを使用して、既存 のプロジェクトまたは .NET Core プロジェクトを開く、または新しいプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1de41-144">Open an existing ASP.NET or .NET Core project or **Create new project...** using one of the **Visual C#** .NET templates.</span></span>

3. <span data-ttu-id="1de41-145">プロジェクト ソリューション エクスプローラー **で**、デバッグする JavaScript ファイルを開き、サーバー側コードと同様に IDE 内にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="1de41-145">In the project **Solution Explorer**, open the JavaScript files you wish to debug and set breakpoints within the IDE just as you would with server-side code.</span></span>

4. <span data-ttu-id="1de41-146">`F5`DevTools Server を実行している Microsoft Edge を押して起動します。</span><span class="sxs-lookup"><span data-stu-id="1de41-146">Press `F5` to launch Microsoft Edge running the DevTools Server.</span></span> <span data-ttu-id="1de41-147">ブレークポイントにヒットすると、ブレークポイントに分割Visual Studio、そこからコードをさらに検査してステップ実行できます。</span><span class="sxs-lookup"><span data-stu-id="1de41-147">When a breakpoint is hit, you'll break into Visual Studio and can further inspect and step through the code from there.</span></span>
