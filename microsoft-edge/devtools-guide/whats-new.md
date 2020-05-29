---
description: 2018年10月更新プログラムの Microsoft Edge DevTools の新機能を参照してください。
title: Microsoft Edge DevTools の新機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、edgehtml 18
ms.custom: RS5, seodec18
ms.openlocfilehash: 604419f4c77ccaaf2dfd3179273be803cde86fc8
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569641"
---
# <span data-ttu-id="eda83-104">最新の Windows 10 更新プログラム (EdgeHTML 18) の DevTools</span><span class="sxs-lookup"><span data-stu-id="eda83-104">DevTools in the latest Windows 10 update (EdgeHTML 18)</span></span>

<span data-ttu-id="eda83-105">Microsoft Edge DevTools の最新の更新プログラムでは、[*サービス作業者*](#service-workers-panel)と[*ストレージ*](#storage-panel)のための新しい専用パネル、デバッガーのソース[ファイル検索](#source-file-search-tools)ツール、スタイル/レイアウトのデバッグとコンソール Api 用の新しい[エッジツールプロトコルドメイン](#edge-devtools-protocol-updates)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="eda83-105">The latest update to Microsoft Edge DevTools adds a number of conveniences both to the UI and under the hood, including new dedicated panels for [*Service Workers*](#service-workers-panel) and [*Storage*](#storage-panel), source [file search](#source-file-search-tools) tools in the Debugger, and new [Edge DevTools Protocol domains](#edge-devtools-protocol-updates) for style/layout debugging and console APIs.</span></span>

<span data-ttu-id="eda83-106">ここでは、 [Windows 10 年 2018 10 月の更新プログラム](/windows/uwp/whats-new/windows-10-build-17763)([EdgeHTML 18](https://aka.ms/devguide_edgehtml_18)) で現在利用できる最新の Microsoft Edge の devtools 機能を示します。</span><span class="sxs-lookup"><span data-stu-id="eda83-106">Here are the latest Microsoft Edge DevTools features available now in the [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) ([EdgeHTML 18](https://aka.ms/devguide_edgehtml_18)).</span></span> <span data-ttu-id="eda83-107">さらに、さまざまなアクセシビリティ、信頼性、およびパフォーマンスのバグも修正され、基本的な機能が向上しました。</span><span class="sxs-lookup"><span data-stu-id="eda83-107">In addition to all this, we’ve also fixed a number of accessibility, reliability, and performance bugs to improve fundamentals!</span></span>

## <span data-ttu-id="eda83-108">DevTools アプリ</span><span class="sxs-lookup"><span data-stu-id="eda83-108">DevTools app</span></span>

<span data-ttu-id="eda83-109">スタンドアロンの[Microsoft Edge DevTools Preview アプリ](../devtools-guide.md#microsoft-store-app)が更新されました。</span><span class="sxs-lookup"><span data-stu-id="eda83-109">We've updated the standalone [Microsoft Edge DevTools Preview app](../devtools-guide.md#microsoft-store-app).</span></span> <span data-ttu-id="eda83-110">最新のリリースには、[**デバッガー**](./debugger.md)のコア機能へのリモートデバッグアクセス、[**要素**](./elements.md)(読み取り専用操作の場合)、[**コンソール**](./console.md)パネルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="eda83-110">The latest release includes remote debugging access to core funtionality in the [**Debugger**](./debugger.md), [**Elements**](./elements.md) (for read-only operations), and [**Console**](./console.md) panels.</span></span>

## <span data-ttu-id="eda83-111">Service Worker パネル</span><span class="sxs-lookup"><span data-stu-id="eda83-111">Service Workers panel</span></span>

<span data-ttu-id="eda83-112">サイトのサービスワーカーを調査、管理、デバッグするための専用の[**サービスワーカー**](./service-workers.md)パネルが登場しました。</span><span class="sxs-lookup"><span data-stu-id="eda83-112">There's now a dedicated [**Service Workers**](./service-workers.md) panel for inspecting, managing, and debugging your site's service workers.</span></span> <span data-ttu-id="eda83-113">これにより、以前の*デバッガー*パネルでのものと同じ機能が提供されます (現在は、あまりに混雑している UI があります)。</span><span class="sxs-lookup"><span data-stu-id="eda83-113">This provides the same functionality as was previously in the *Debugger* panel (now with a less-crowded UI!).</span></span>

![Service Worker パネル](./media/service_worker.png)

## <span data-ttu-id="eda83-115">ストレージパネル</span><span class="sxs-lookup"><span data-stu-id="eda83-115">Storage panel</span></span>

<span data-ttu-id="eda83-116">また、*デバッガー*の前のローカルストレージ検査 (*Local と Sesion Storage、Indexeddb、cookie、キャッシュ*) も、独自の専用[**ストレージ**](./storage.md)パネルに移されました。</span><span class="sxs-lookup"><span data-stu-id="eda83-116">We've also moved all the local storage inspectors (*Local and Sesion Storage, IndexedDB, Cookies, Cache*) previously in the *Debugger* to their own dedicated [**Storage**](./storage.md) panel.</span></span>

![ストレージパネル](./media/storage_cache.png)

## <span data-ttu-id="eda83-118">ソースファイルの検索ツール</span><span class="sxs-lookup"><span data-stu-id="eda83-118">Source file search tools</span></span>

<span data-ttu-id="eda83-119">これで、[**デバッガー**](./debugger.md)の[ソースファイル検索](./debugger.md#file-search)ウィンドウが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="eda83-119">The [**Debugger**](./debugger.md) now has a [source file search](./debugger.md#file-search) pane.</span></span> <span data-ttu-id="eda83-120">*Find in files* `Ctrl` + `Shift` + `F` ソースで検索しようとしている特定のコードの文字列がある場合は、[ファイル内を検索] コマンド () を使用してアプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="eda83-120">Open it with the *Find in files* command (`Ctrl`+`Shift`+`F`) when you have a specific string of code you're trying to find in the source.</span></span> <span data-ttu-id="eda83-121">ツールバーには、正規表現などのさまざまな検索オプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="eda83-121">The toolbar provides different search options, including regular expressions.</span></span> 

![デバッガーファイルの検索](./media/debugger_file_search.png)

<span data-ttu-id="eda83-123">[*ファイルを開く*] () コマンドを使用して、読み込まれたすべてのソースファイルをすばやく開くこともでき `Ctrl` + `P` ます。</span><span class="sxs-lookup"><span data-stu-id="eda83-123">You can also quickly open any loaded source file with the *Open file* (`Ctrl`+`P`) command.</span></span>

![デバッガファイルを開く](./media/debugger_open_file.png)

## <span data-ttu-id="eda83-125">Edge DevTools プロトコルの更新</span><span class="sxs-lookup"><span data-stu-id="eda83-125">Edge DevTools Protocol updates</span></span>

<span data-ttu-id="eda83-126">DevTools プロトコルの[バージョン 0.2](../devtools-protocol/0.2/index.md)では、[バージョン 0.1](../devtools-protocol/0.1/index.md)で導入されたコアスクリプトのデバッグ機能に加えて、スタイルとレイアウト (読み取り専用) デバッグとコンソール api 用の新しいドメインが提供されています。</span><span class="sxs-lookup"><span data-stu-id="eda83-126">[Version 0.2](../devtools-protocol/0.2/index.md) of the DevTools Protocol provides new domains for style and layout (read-only) debugging and console APIs, in addition to the core script debugging functionality introduced in [Version 0.1](../devtools-protocol/0.1/index.md).</span></span> <span data-ttu-id="eda83-127">エッジ DevTools UI では、[**要素**](../devtools-guide/elements.md)(読み取り専用操作の場合)、[**本体**](../devtools-guide/console.md)、[**デバッガー**](../devtools-guide/debugger.md)パネルで利用できる機能に変換されます。</span><span class="sxs-lookup"><span data-stu-id="eda83-127">In the Edge DevTools UI, this translates to functionality available in the [**Elements**](../devtools-guide/elements.md) (for read-only operations), [**Console**](../devtools-guide/console.md) and [**Debugger**](../devtools-guide/debugger.md) panels.</span></span>
