---
description: Windows 10 年 4 2018 月の更新プログラム (EdgeHTML 17) で Microsoft Edge DevTools に追加された機能
title: EdgeHTML 17 の DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、edgehtml 17
ms.custom: seodec18
ms.openlocfilehash: cc110071422f858acf840c1eaf100696a6e3cf03
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569635"
---
# <span data-ttu-id="4160e-104">Windows 10 4 月の2018更新プログラム (EdgeHTML 17) の DevTools</span><span class="sxs-lookup"><span data-stu-id="4160e-104">DevTools in the Windows 10 April 2018 update (EdgeHTML 17)</span></span>

<span data-ttu-id="4160e-105">DevTools の EdgeHTML 17 リリースは、Microsoft Edge 用の従来のブラウザー () ツールとして、 `F12` Microsoft Store からスタンドアロンの[Windows 10 アプリ](#microsoft-edge-devtools-app-preview)としてプレビューする、2つの方法で提供されています。</span><span class="sxs-lookup"><span data-stu-id="4160e-105">The EdgeHTML 17 release of the DevTools ships in two ways: as the traditional in-browser (`F12`) tools for Microsoft Edge, and previewing as a standalone [Windows 10 app](#microsoft-edge-devtools-app-preview) from the Microsoft Store!</span></span>

<span data-ttu-id="4160e-106">このツールは、[リモートデバッグ](../../devtools-guide.md#remote-debugging)の基本的なサポート (新しい[devtools プロトコル](#devtools-protocol)を使用)、 [PWA のデバッグ機能](#pwa-debugging)、 [indexeddb キャッシュ管理](#indexeddb-inspection)、[縦型のドッキング](#docking-to-the-right-in-microsoft-edge)など、さまざまな主要機能によって更新されています。</span><span class="sxs-lookup"><span data-stu-id="4160e-106">The tools have been updated with a number of major features, including basic support for [remote debugging](../../devtools-guide.md#remote-debugging) (via our new [DevTools Protocol](#devtools-protocol)), [PWA debugging features](#pwa-debugging), [IndexedDB cache management](#indexeddb-inspection), [vertical docking](#docking-to-the-right-in-microsoft-edge) and more!</span></span> <span data-ttu-id="4160e-107">また、パフォーマンスと信頼性への継続的な投資の一環として、最後のリリースで行われた全体的な[リファクタリングの取り組み](./edgehtml-16.md)を継続しました。</span><span class="sxs-lookup"><span data-stu-id="4160e-107">We also continued the overall [refactoring effort](./edgehtml-16.md) started last release as part of ongoing investments in performance and reliability.</span></span>

<span data-ttu-id="4160e-108">[2018 年4月の更新プログラム](/windows/uwp/whats-new/windows-10-build-17134)([EdgeHTML 17](https://aka.ms/devguide_edgehtml_17)) で出荷された最新の Microsoft Edge の製品ツールの機能を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4160e-108">Here are the latest Microsoft Edge DevTools features that shipped in the [Windows 10 April 2018 Update](/windows/uwp/whats-new/windows-10-build-17134) ([EdgeHTML 17](https://aka.ms/devguide_edgehtml_17)).</span></span>

## <span data-ttu-id="4160e-109">Microsoft Edge DevTools アプリのプレビュー</span><span class="sxs-lookup"><span data-stu-id="4160e-109">Microsoft Edge DevTools app preview</span></span>

![Microsoft Edge DevTools アプリ](../../devtools-protocol/media/microsoft-edge-devtools.png) 

<span data-ttu-id="4160e-111">Microsoft [**Edge DevTools**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab)は、microsoft Store からスタンドアロンの Windows 10 アプリとしてプレビューできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4160e-111">The [**Microsoft Edge DevTools**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) are now available for preview as a standalone Windows 10 app from the Microsoft Store.</span></span> <span data-ttu-id="4160e-112">ストアバージョンでは、ローカルとリモートのページターゲットを開くための*セレクター*パネルが用意されています。これには、devtools インスタンス間で簡単に切り替えるためのタブ付きレイアウトが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4160e-112">With the store version comes a *chooser* panel for attaching to open local and remote page targets and a tabbed layout for easy switching between DevTools instances.</span></span> <span data-ttu-id="4160e-113">また、DevTools アプリに限定されているのは、アプリ (Office、Cortana、EdgeHTML [webview](../../webview.md)、 [Windows にインストールされている pwas](../../progressive-web-apps-edgehtml/windows-features.md)アドインなど) の web コンテンツをデバッグする機能です。</span><span class="sxs-lookup"><span data-stu-id="4160e-113">Also exclusive to the DevTools app is the ability to debug web content in apps (such as add-ins for Office, Cortana, EdgeHTML [webview](../../webview.md), and [Windows-installed PWAs](../../progressive-web-apps-edgehtml/windows-features.md)).</span></span>

<span data-ttu-id="4160e-114">また、Edge の DevTools は `F12` ブラウザー内から (セレクターパネルなしで) 利用できます。</span><span class="sxs-lookup"><span data-stu-id="4160e-114">The Edge DevTools are also still available (`F12`) from within the browser (without the chooser panel).</span></span>

<span data-ttu-id="4160e-115">ブラウザーから DevTools を分離すると、これらの UX と構造的な利点が得られます。</span><span class="sxs-lookup"><span data-stu-id="4160e-115">Decoupling the DevTools from the browser provides these UX and architectural advantages:</span></span>

- <span data-ttu-id="4160e-116">DevTools は、Microsoft Edge から独立したアプリコンテナーサンドボックスで実行され、両方に対してより高い信頼性を実現します。</span><span class="sxs-lookup"><span data-stu-id="4160e-116">The DevTools run in a separate app container sandbox from Microsoft Edge, providing better reliability for both.</span></span>
- <span data-ttu-id="4160e-117">アプリでは、アクティブな DevTools インスタンスタブ間を簡単に切り替えることができます (開いている Microsoft Edge タブを切り替える必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="4160e-117">The app provides easy switching between active DevTools instance tabs (rather than having to switch between open Microsoft Edge tabs)</span></span>
- <span data-ttu-id="4160e-118">*EdgeHTML*ブラウザーエンジンをインストルメント化し、[クロスブラウザー api](https://github.com/WICG/devtools-protocol/)を使用して、より大きな devtools エコシステムにそれを開くことができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4160e-118">We're able to instrument the *EdgeHTML* browser engine and open it to the larger devtools ecosystem with [cross-browser APIs](https://github.com/WICG/devtools-protocol/).</span></span>
- <span data-ttu-id="4160e-119">DevTools の更新プログラムは、Windows (および EdgeHTML) リリースサイクルから独立して提供することができます。</span><span class="sxs-lookup"><span data-stu-id="4160e-119">We can ship DevTools updates independently from the Windows (and EdgeHTML) release cycle.</span></span>

<span data-ttu-id="4160e-120">開発の詳細については、 [「devtools アプリを使ったローカルおよびリモートデバッグ](../../devtools-guide.md) *」* をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4160e-120">Check out the *DevTools guide* for more on [local and remote debugging using the DevTools app](../../devtools-guide.md).</span></span>

## <span data-ttu-id="4160e-121">DevTools プロトコル</span><span class="sxs-lookup"><span data-stu-id="4160e-121">DevTools Protocol</span></span>

<span data-ttu-id="4160e-122">開発者ツールでは、 [**Microsoft Edge DevTools プロトコル**](../../devtools-protocol/index.md)を使用して、microsoft edge ブラウザーを検査およびデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="4160e-122">Developer tools can use the [**Microsoft Edge DevTools Protocol**](../../devtools-protocol/index.md) to inspect and debug the Microsoft Edge browser.</span></span> <span data-ttu-id="4160e-123">EdgeHTML engine インストルメンテーションのさまざまな[ドメイン](../../devtools-protocol/0.1/domains/index.md)で構成されている一連のメソッドとイベントを提供します。</span><span class="sxs-lookup"><span data-stu-id="4160e-123">It provides a set of methods and events that are organized into different [Domains](../../devtools-protocol/0.1/domains/index.md) of EdgeHTML engine instrumentation.</span></span>

 <span data-ttu-id="4160e-124">ツールクライアントは、これらのメソッドを呼び出し、Microsoft Edge または[Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal)でホストされている*devtools サーバー*との間でやり取りされる JSON web ソケットメッセージを通じてこれらのイベントを監視します。</span><span class="sxs-lookup"><span data-stu-id="4160e-124">Tooling clients can call these methods and monitor these events through JSON web socket messages exchanged with the *DevTools Server* hosted by Microsoft Edge or the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span> 
 
 <span data-ttu-id="4160e-125">Microsoft Edge DevTools では、microsoft Store から入手できる[スタンドアロンの devtools クライアント](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)から microsoft edge を実行しているホストコンピューターの[リモートデバッグ](../../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview)を有効にするために、このプロトコルが使用されています。</span><span class="sxs-lookup"><span data-stu-id="4160e-125">Microsoft Edge DevTools uses this protocol to enable [remote debugging](../../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview) of a host machine running Microsoft Edge from the [standalone DevTools client](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj) available from the Microsoft Store.</span></span> <span data-ttu-id="4160e-126">現在、このプレビューのサポートは、別のデスクトップデバイスまたは VM での別のエッジの JS デバッグに限定されています。</span><span class="sxs-lookup"><span data-stu-id="4160e-126">Currently this preview support is limited to JS debugging of another Edge on another desktop device or VM.</span></span> <span data-ttu-id="4160e-127">時間の経過と共に、Windows 10 デバイスの任意の EdgeHTML インスタンスに対するすべての DevTools のサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="4160e-127">Over time, we'll add support for the full set of DevTools against any EdgeHTML instance on any Windows 10 device.</span></span>  
 
 <span data-ttu-id="4160e-128">最新の[**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/)ビルド (visual Studio 15.7 preview 1 以降) では、ASP.NET または .net コアプロジェクトの VISUAL studio IDE から Microsoft Edge (JavaScript コード) の起動とデバッグを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4160e-128">The latest [**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/) builds (Visual Studio 15.7 Preview 1 or later) use the DevTools Protocol to enable launching and debugging Microsoft Edge (JavaScript code) from within the Visual Studio IDE of any ASP.NET or .NET Core project.</span></span>

## <span data-ttu-id="4160e-129">IndexedDB 検査</span><span class="sxs-lookup"><span data-stu-id="4160e-129">IndexedDB inspection</span></span>

<span data-ttu-id="4160e-130">[**デバッガー**](../debugger.md)の新機能このリリースは、オブジェクトストアの調査と更新をサポートする[Indexeddb Manager](../storage.md#indexeddb-manager)であり、個々のキー値エントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="4160e-130">New to the [**Debugger**](../debugger.md) this release is an [IndexedDB Manager](../storage.md#indexeddb-manager) with support for inspecting and refreshing your object stores and deleting individual key-value entries.</span></span> <span data-ttu-id="4160e-131">今後のリリースでは、さらに機能が期待できます。</span><span class="sxs-lookup"><span data-stu-id="4160e-131">Expect even more functionality in future releases.</span></span>

## <span data-ttu-id="4160e-132">PWA のデバッグ</span><span class="sxs-lookup"><span data-stu-id="4160e-132">PWA debugging</span></span>

<span data-ttu-id="4160e-133">プログレッシブ Web アプリ (PWAs) のデバッグのサポートが既定で有効になりました。[**サービスワーカー**](../service-workers.md)、[**キャッシュ API**](../storage.md#cache-manager)、 [**indexeddb**](../storage.md#indexeddb-manager) management のツールタブが提供されます。</span><span class="sxs-lookup"><span data-stu-id="4160e-133">Support for debugging Progressive Web Apps (PWAs) is now enabled by default, providing tool tabs for [**Service Workers**](../service-workers.md), [**Cache API**](../storage.md#cache-manager), and [**IndexedDB**](../storage.md#indexeddb-manager) management.</span></span>

<span data-ttu-id="4160e-134">さらに、[[ネットワークパネル] ツールバー](../network.md#toolbar)には、[**すべてのネットワーク要求] の [サービスワーカー**を表示しない] があり、登録されているサービスワーカーをネットワークプロキシとしてオンまたはオフに切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="4160e-134">Additionally, the [Network panel toolbar](../network.md#toolbar) has a new button, **Bypass Service Worker for all network requests**, to toggle on/off your registered service workers as network proxies:</span></span>

![ネットワークツールバーボタン: すべてのネットワーク要求についてサービスワーカーをバイパスする](../media/network_toolbar_bypass_sw.png)

<span data-ttu-id="4160e-136">[スタンドアロンの DevTools アプリ](../../devtools-guide.md#microsoft-store-app)のセレクターで、[**ローカル**](../../progressive-web-apps-edgehtml/windows-features.md#debug-your-pwa-edgehtml-as-a-windows-app)ターゲット (browser tab/PWA/webview) の一覧から PWA を選択することによって、[インストールされている Windows 10 アプリとして](../../progressive-web-apps-edgehtml/windows-features.md)デバッグできます。</span><span class="sxs-lookup"><span data-stu-id="4160e-136">You can debug your [PWA as an installed Windows 10 app](../../progressive-web-apps-edgehtml/windows-features.md) by selecting it from the list of [**Local**](../../progressive-web-apps-edgehtml/windows-features.md#debug-your-pwa-edgehtml-as-a-windows-app) targets (browser tab/PWA/webview) in the chooser of the [standalone DevTools app](../../devtools-guide.md#microsoft-store-app).</span></span>  

## <span data-ttu-id="4160e-137">Microsoft Edge での右へのドッキング</span><span class="sxs-lookup"><span data-stu-id="4160e-137">Docking to the right in Microsoft Edge</span></span>

<span data-ttu-id="4160e-138">Microsoft Edge 内からデバッグしているページの右側に DevTools をドッキングできるようになりました。また、ブラウザーウィンドウから DevTools のドッキングを解除することもできます。</span><span class="sxs-lookup"><span data-stu-id="4160e-138">You can now dock the DevTools to the right of the page you're debugging from within Microsoft Edge, in addition to docking at the bottom and undocking the DevTools from the browser window.</span></span> <span data-ttu-id="4160e-139">[ `Ctrl+Shift+D` Dock] の**下**、[**右揃え**]、[ドッキング**解除**] の間の切り替え、および devtools の右上隅のアイコンの切り替えに使用します。</span><span class="sxs-lookup"><span data-stu-id="4160e-139">Use `Ctrl+Shift+D` to cycle between the **Dock Bottom**, **Dock Right**, and **Undock** positions, or the icons in the top-right corner of the DevTools:</span></span>

![DevTools (非ドッキング状態) のドッキングオプション](../media/docking_buttons.png) 
