---
description: Windows 10 April 2018 Update (EdgeHTML 17) で Microsoft Edge DevTools に追加された機能
title: EdgeHTML 17 の DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, edgehtml 17
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 937525f349a1db650b795db1efb983f1359fcaa5
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234806"
---
# <span data-ttu-id="65d76-104">Windows 10 April 2018 更新プログラムの DevTools (EdgeHTML 17)</span><span class="sxs-lookup"><span data-stu-id="65d76-104">DevTools in the Windows 10 April 2018 update (EdgeHTML 17)</span></span>

<span data-ttu-id="65d76-105">DevTools の EdgeHTML 17 リリースには、Microsoft Edge 用の従来のブラウザー内 ( ) ツールと、Microsoft Store からスタンドアロン `F12` [の Windows 10](#microsoft-edge-devtools-app-preview) アプリとしてプレビューする 2 つの方法が含まれています。</span><span class="sxs-lookup"><span data-stu-id="65d76-105">The EdgeHTML 17 release of the DevTools ships in two ways: as the traditional in-browser (`F12`) tools for Microsoft Edge, and previewing as a standalone [Windows 10 app](#microsoft-edge-devtools-app-preview) from the Microsoft Store!</span></span>

<span data-ttu-id="65d76-106">このツールは、リモート デバッグの基本的なサポート (新しい[DevTools プロトコル](#devtools-protocol)経由[](../index.md#remote-debugging)[](#docking-to-the-right-in-microsoft-edge)[)、PWA](#pwa-debugging)デバッグ機能[、IndexedDB](#indexeddb-inspection)キャッシュ管理、垂直ドッキングなど、多くの主要な機能で更新されました。</span><span class="sxs-lookup"><span data-stu-id="65d76-106">The tools have been updated with a number of major features, including basic support for [remote debugging](../index.md#remote-debugging) (via our new [DevTools Protocol](#devtools-protocol)), [PWA debugging features](#pwa-debugging), [IndexedDB cache management](#indexeddb-inspection), [vertical docking](#docking-to-the-right-in-microsoft-edge) and more!</span></span> <span data-ttu-id="65d76-107">また、パフォーマンスと信頼性 [に対](./edgehtml-16.md) する継続的な投資の一環として、最後のリリースで開始された全体的なリファクタリング作業も継続しました。</span><span class="sxs-lookup"><span data-stu-id="65d76-107">We also continued the overall [refactoring effort](./edgehtml-16.md) started last release as part of ongoing investments in performance and reliability.</span></span>

<span data-ttu-id="65d76-108">[Windows 10 April 2018 Update](/windows/uwp/whats-new/windows-10-build-17134) ([EdgeHTML 17)](https://aka.ms/devguide_edgehtml_17)にリリースされた最新の Microsoft Edge DevTools 機能を次に示します。</span><span class="sxs-lookup"><span data-stu-id="65d76-108">Here are the latest Microsoft Edge DevTools features that shipped in the [Windows 10 April 2018 Update](/windows/uwp/whats-new/windows-10-build-17134) ([EdgeHTML 17](https://aka.ms/devguide_edgehtml_17)).</span></span>

## <span data-ttu-id="65d76-109">Microsoft Edge DevTools アプリのプレビュー</span><span class="sxs-lookup"><span data-stu-id="65d76-109">Microsoft Edge DevTools app preview</span></span>

![Microsoft Edge DevTools アプリ](../../devtools-protocol/media/microsoft-edge-devtools.png) 

<span data-ttu-id="65d76-111">Microsoft [Edge DevTools は](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj) 、Microsoft Store からスタンドアロンの Windows 10 アプリとしてプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="65d76-111">The [Microsoft Edge DevTools](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj) are now available for preview as a standalone Windows 10 app from the Microsoft Store.</span></span> <span data-ttu-id="65d76-112">ストア バージョンでは、ローカルとリモートのページ　ターゲットを開くために [*セレクター*] パネルが表示されます。これには、DevTools インスタンス間で簡単に切り替えられるようにタブ レイアウトが用意されています。</span><span class="sxs-lookup"><span data-stu-id="65d76-112">With the store version comes a *chooser* panel for attaching to open local and remote page targets and a tabbed layout for easy switching between DevTools instances.</span></span> <span data-ttu-id="65d76-113">また、DevTools アプリ専用の機能は、アプリ \(Office、Cortana、EdgeHTML [Webview、Windows](../../hosting/webview/index.md)にインストールされた PAS のアドインなど) で Web コンテンツをデバッグする [機能](../../progressive-web-apps/windows-features.md)です。</span><span class="sxs-lookup"><span data-stu-id="65d76-113">Also exclusive to the DevTools app is the ability to debug web content in apps \(such as add-ins for Office, Cortana, EdgeHTML [webview](../../hosting/webview/index.md), and [Windows-installed PWAs](../../progressive-web-apps/windows-features.md)\).</span></span>

<span data-ttu-id="65d76-114">Edge DevTools は、ブラウザー内から (選択パネルなしで) 引き続 `F12` き利用できます。</span><span class="sxs-lookup"><span data-stu-id="65d76-114">The Edge DevTools are also still available (`F12`) from within the browser (without the chooser panel).</span></span>

<span data-ttu-id="65d76-115">DevTools をブラウザーから切り離すには、次の UX とアーキテクチャ上の利点があります。</span><span class="sxs-lookup"><span data-stu-id="65d76-115">Decoupling the DevTools from the browser provides these UX and architectural advantages:</span></span>

- <span data-ttu-id="65d76-116">DevTools は、Microsoft Edge とは別のアプリ コンテナー サンドボックスで実行され、両方の信頼性が向上します。</span><span class="sxs-lookup"><span data-stu-id="65d76-116">The DevTools run in a separate app container sandbox from Microsoft Edge, providing better reliability for both.</span></span>
- <span data-ttu-id="65d76-117">アプリは、アクティブな DevTools インスタンスタブを簡単に切り替える機能を提供します (開いている Microsoft Edge タブを切り替える必要は不要です)。</span><span class="sxs-lookup"><span data-stu-id="65d76-117">The app provides easy switching between active DevTools instance tabs (rather than having to switch between open Microsoft Edge tabs)</span></span>
- <span data-ttu-id="65d76-118">*EdgeHTML*ブラウザー エンジンをインストルメント化し、クロスブラウザー API を使用して大規模な devtools エコシステムに[開くこともできます](https://github.com/WICG/devtools-protocol/)。</span><span class="sxs-lookup"><span data-stu-id="65d76-118">We're able to instrument the *EdgeHTML* browser engine and open it to the larger devtools ecosystem with [cross-browser APIs](https://github.com/WICG/devtools-protocol/).</span></span>
- <span data-ttu-id="65d76-119">DevTools の更新プログラムは、Windows (および EdgeHTML) リリース サイクルとは独立して出荷できます。</span><span class="sxs-lookup"><span data-stu-id="65d76-119">We can ship DevTools updates independently from the Windows (and EdgeHTML) release cycle.</span></span>

<span data-ttu-id="65d76-120">*DevTools アプリを使った*ローカルデバッグとリモート デバッグの詳細については[、DevTools ガイドを参照してください](../index.md)。</span><span class="sxs-lookup"><span data-stu-id="65d76-120">Check out the *DevTools guide* for more on [local and remote debugging using the DevTools app](../index.md).</span></span>

## <span data-ttu-id="65d76-121">DevTools プロトコル</span><span class="sxs-lookup"><span data-stu-id="65d76-121">DevTools Protocol</span></span>

<span data-ttu-id="65d76-122">開発者ツールでは [**、Microsoft Edge DevTools プロトコルを使用**](../../devtools-protocol/index.md) して、Microsoft Edge ブラウザーを検査およびデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="65d76-122">Developer tools can use the [**Microsoft Edge DevTools Protocol**](../../devtools-protocol/index.md) to inspect and debug the Microsoft Edge browser.</span></span> <span data-ttu-id="65d76-123">EdgeHTML エンジンインストルメンテーションの異なる [ドメイン](../../devtools-protocol/0.1/domains/index.md) に編成されたメソッドとイベントのセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="65d76-123">It provides a set of methods and events that are organized into different [Domains](../../devtools-protocol/0.1/domains/index.md) of EdgeHTML engine instrumentation.</span></span>

 <span data-ttu-id="65d76-124">ツール クライアントは、これらのメソッドを呼び出し、Microsoft Edge または Windows Device Portal によってホストされる *DevTools Server* と交換される JSON Web ソケット メッセージを介してこれらのイベント [を監視できます](/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="65d76-124">Tooling clients can call these methods and monitor these events through JSON web socket messages exchanged with the *DevTools Server* hosted by Microsoft Edge or the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span> 
 
 <span data-ttu-id="65d76-125">Microsoft Edge DevTools は、[](../../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview)このプロトコルを使用して、Microsoft Store から利用できるスタンドアロン[の DevTools](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)クライアントから Microsoft Edge を実行しているホスト コンピューターのリモート デバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="65d76-125">Microsoft Edge DevTools uses this protocol to enable [remote debugging](../../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview) of a host machine running Microsoft Edge from the [standalone DevTools client](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj) available from the Microsoft Store.</span></span> <span data-ttu-id="65d76-126">現在、このプレビュー サポートは、別のデスクトップ デバイスまたは VM 上の別の Edge の JS デバッグに限定されています。</span><span class="sxs-lookup"><span data-stu-id="65d76-126">Currently this preview support is limited to JS debugging of another Edge on another desktop device or VM.</span></span> <span data-ttu-id="65d76-127">時間の間に、すべての Windows 10 デバイス上の EdgeHTML インスタンスに対する DevTools の完全なセットのサポートが追加されます。</span><span class="sxs-lookup"><span data-stu-id="65d76-127">Over time, we'll add support for the full set of DevTools against any EdgeHTML instance on any Windows 10 device.</span></span>  
 
 <span data-ttu-id="65d76-128">最新の [**Visual Studio プレビュー**](https://www.visualstudio.com/vs/preview/) ビルド (Visual Studio 15.7 Preview 1 以降) では、DevTools プロトコルを使用して、任意の ASP.NET または .NET Core プロジェクトの Visual Studio IDE 内から Microsoft Edge (JavaScript コード) の起動とデバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="65d76-128">The latest [**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/) builds (Visual Studio 15.7 Preview 1 or later) use the DevTools Protocol to enable launching and debugging Microsoft Edge (JavaScript code) from within the Visual Studio IDE of any ASP.NET or .NET Core project.</span></span>

## <span data-ttu-id="65d76-129">IndexedDB 検査</span><span class="sxs-lookup"><span data-stu-id="65d76-129">IndexedDB inspection</span></span>

<span data-ttu-id="65d76-130">[**デバッガー**](../debugger.md)の新機能このリリースは、オブジェクト ストアの検査と更新、個々のキー値エントリの削除をサポートする[IndexedDB](../storage.md#indexeddb-manager)マネージャーです。</span><span class="sxs-lookup"><span data-stu-id="65d76-130">New to the [**Debugger**](../debugger.md) this release is an [IndexedDB Manager](../storage.md#indexeddb-manager) with support for inspecting and refreshing your object stores and deleting individual key-value entries.</span></span> <span data-ttu-id="65d76-131">今後のリリースでは、さらに多くの機能が期待されます。</span><span class="sxs-lookup"><span data-stu-id="65d76-131">Expect even more functionality in future releases.</span></span>

## <span data-ttu-id="65d76-132">PWA デバッグ</span><span class="sxs-lookup"><span data-stu-id="65d76-132">PWA debugging</span></span>

<span data-ttu-id="65d76-133">段階的 Web アプリ (PAS) のデバッグのサポートが既定で有効にされ[\*\*\*\*](../service-workers.md)、サービス ワーカー、キャッシュ[**API、**](../storage.md#cache-manager)[**および IndexedDB**](../storage.md#indexeddb-manager)管理のツール タブが提供されます。</span><span class="sxs-lookup"><span data-stu-id="65d76-133">Support for debugging Progressive Web Apps (PWAs) is now enabled by default, providing tool tabs for [**Service Workers**](../service-workers.md), [**Cache API**](../storage.md#cache-manager), and [**IndexedDB**](../storage.md#indexeddb-manager) management.</span></span>

<span data-ttu-id="65d76-134">さらに、[ネットワーク[](../network.md#toolbar)パネル] ツール バーには、\*\*\*\* すべてのネットワーク要求に対してサービス ワーカーをバイパスする新しいボタンがあります。このボタンを使用すると、登録済みのサービス ワーカーをネットワーク プロキシとしてオン/オフできます。</span><span class="sxs-lookup"><span data-stu-id="65d76-134">Additionally, the [Network panel toolbar](../network.md#toolbar) has a new button, **Bypass Service Worker for all network requests**, to toggle on/off your registered service workers as network proxies:</span></span>

![[ネットワーク] ツール バー ボタン: すべてのネットワーク要求に対してサービス ワーカーをバイパスする](../media/network_toolbar_bypass_sw.png)

<span data-ttu-id="65d76-136">スタンドアロン[DevTools](../index.md#microsoft-store-app)アプリの選択ツールでローカル ターゲット (ブラウザー タブ/PWA/webview) の一覧から PWA を選択すると、インストール済み[Windows 10](../../progressive-web-apps/windows-features.md)アプリとして PWA をデバッグできます。 [\*\*\*\*](../../progressive-web-apps/windows-features.md#debug-your-pwa-edgehtml-as-a-windows-app)</span><span class="sxs-lookup"><span data-stu-id="65d76-136">You can debug your [PWA as an installed Windows 10 app](../../progressive-web-apps/windows-features.md) by selecting it from the list of [**Local**](../../progressive-web-apps/windows-features.md#debug-your-pwa-edgehtml-as-a-windows-app) targets (browser tab/PWA/webview) in the chooser of the [standalone DevTools app](../index.md#microsoft-store-app).</span></span>  

## <span data-ttu-id="65d76-137">Microsoft Edge の右側へのドッキング</span><span class="sxs-lookup"><span data-stu-id="65d76-137">Docking to the right in Microsoft Edge</span></span>

<span data-ttu-id="65d76-138">これで、Microsoft Edge 内からデバッグするページの右側に DevTools をドッキングできます。また、下部にドッキングしてブラウザー ウィンドウから DevTools をドッキング解除することもできます。</span><span class="sxs-lookup"><span data-stu-id="65d76-138">You can now dock the DevTools to the right of the page you're debugging from within Microsoft Edge, in addition to docking at the bottom and undocking the DevTools from the browser window.</span></span> <span data-ttu-id="65d76-139">ドック `Ctrl+Shift+D` の下、ドック\*\*\*\*\*\*の右\*\*、およびドッキング解除の\*\*\*\* 位置、または DevTools の右上隅にあるアイコンを切り替える場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="65d76-139">Use `Ctrl+Shift+D` to cycle between the **Dock Bottom**, **Dock Right**, and **Undock** positions, or the icons in the top-right corner of the DevTools:</span></span>

![DevTools (ドッキングされていない状態) のドッキング オプション](../media/docking_buttons.png) 
