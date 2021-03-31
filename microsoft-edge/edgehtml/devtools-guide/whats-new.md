---
description: Windows 10 October 2018 Update の Microsoft Edge DevTools の新機能を確認する
title: Microsoft Edge DevTools の新機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, edgehtml 18
ms.custom: RS5, seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2f1d3c6fe5bf061186d5c6593a115a8b6794c0dd
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234811"
---
# <span data-ttu-id="a367d-104">最新の Windows 10 更新プログラムの DevTools (EdgeHTML 18)</span><span class="sxs-lookup"><span data-stu-id="a367d-104">DevTools in the latest Windows 10 update (EdgeHTML 18)</span></span>

<span data-ttu-id="a367d-105">Microsoft Edge DevTools の最新の更新プログラムでは、UI とセキュリティの両方に多くの利便性が追加されています。たとえば、サービス[](#storage-panel)ワーカーとストレージ[](#source-file-search-tools)用の新しい専用パネル、デバッガーのソース ファイル検索ツール、スタイル/レイアウトのデバッグとコンソール API 用の新しい[Edge DevTools プロトコル](#edge-devtools-protocol-updates)ドメインが含まれます。 [](#service-workers-panel)</span><span class="sxs-lookup"><span data-stu-id="a367d-105">The latest update to Microsoft Edge DevTools adds a number of conveniences both to the UI and under the hood, including new dedicated panels for [*Service Workers*](#service-workers-panel) and [*Storage*](#storage-panel), source [file search](#source-file-search-tools) tools in the Debugger, and new [Edge DevTools Protocol domains](#edge-devtools-protocol-updates) for style/layout debugging and console APIs.</span></span>

<span data-ttu-id="a367d-106">[Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) ([EdgeHTML 18)](https://aka.ms/devguide_edgehtml_18)で利用可能な最新の Microsoft Edge DevTools 機能を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a367d-106">Here are the latest Microsoft Edge DevTools features available now in the [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) ([EdgeHTML 18](https://aka.ms/devguide_edgehtml_18)).</span></span> <span data-ttu-id="a367d-107">このすべてに加えて、多数のアクセシビリティ、信頼性、パフォーマンスのバグも修正して、基礎を改善しました。</span><span class="sxs-lookup"><span data-stu-id="a367d-107">In addition to all this, we’ve also fixed a number of accessibility, reliability, and performance bugs to improve fundamentals!</span></span>

## <span data-ttu-id="a367d-108">DevTools アプリ</span><span class="sxs-lookup"><span data-stu-id="a367d-108">DevTools app</span></span>

<span data-ttu-id="a367d-109">スタンドアロンの Microsoft Edge [DevTools Preview アプリが更新されました](./index.md#microsoft-store-app)。</span><span class="sxs-lookup"><span data-stu-id="a367d-109">We've updated the standalone [Microsoft Edge DevTools Preview app](./index.md#microsoft-store-app).</span></span> <span data-ttu-id="a367d-110">最新のリリースには、デバッガー、要素[**(読**](./elements.md)み取り専用操作[](./debugger.md)用)、コンソール パネルのコア機能へのリモート デバッグ アクセスが[**含**](./console.md)まれています。</span><span class="sxs-lookup"><span data-stu-id="a367d-110">The latest release includes remote debugging access to core funtionality in the [**Debugger**](./debugger.md), [**Elements**](./elements.md) (for read-only operations), and [**Console**](./console.md) panels.</span></span>

## <span data-ttu-id="a367d-111">[サービス ワーカー] パネル</span><span class="sxs-lookup"><span data-stu-id="a367d-111">Service Workers panel</span></span>

<span data-ttu-id="a367d-112">サイトのサービス [**ワーカーを検査**](./service-workers.md) 、管理、およびデバッグするための専用のサービス ワーカー パネルが追加されました。</span><span class="sxs-lookup"><span data-stu-id="a367d-112">There's now a dedicated [**Service Workers**](./service-workers.md) panel for inspecting, managing, and debugging your site's service workers.</span></span> <span data-ttu-id="a367d-113">これにより、デバッガー パネルで以前と同じ機能が *提供されます* (現在は UI が少なめでした)。</span><span class="sxs-lookup"><span data-stu-id="a367d-113">This provides the same functionality as was previously in the *Debugger* panel (now with a less-crowded UI!).</span></span>

![[サービス ワーカー] パネル](./media/service_worker.png)

## <span data-ttu-id="a367d-115">記憶域パネル</span><span class="sxs-lookup"><span data-stu-id="a367d-115">Storage panel</span></span>

<span data-ttu-id="a367d-116">また、デバッガーで以前にローカルストレージインスペクター (*ローカルおよび Sesion ストレージ、IndexedDB、Cookie、キャッシュ*) を 独自の専用ストレージ[](./storage.md)パネルに移動しました。</span><span class="sxs-lookup"><span data-stu-id="a367d-116">We've also moved all the local storage inspectors (*Local and Sesion Storage, IndexedDB, Cookies, Cache*) previously in the *Debugger* to their own dedicated [**Storage**](./storage.md) panel.</span></span>

![記憶域パネル](./media/storage_cache.png)

## <span data-ttu-id="a367d-118">ソース ファイル検索ツール</span><span class="sxs-lookup"><span data-stu-id="a367d-118">Source file search tools</span></span>

<span data-ttu-id="a367d-119">デバッガー [**に**](./debugger.md) ソース ファイル [検索ウィンドウが表示](./debugger.md#file-search) されます。</span><span class="sxs-lookup"><span data-stu-id="a367d-119">The [**Debugger**](./debugger.md) now has a [source file search](./debugger.md#file-search) pane.</span></span> <span data-ttu-id="a367d-120">ソースで検索*しようとしている*特定のコード文字列がある場合は、[ファイル内の検索] コマンド ( ) で開 `Ctrl` + `Shift` + `F` きます。</span><span class="sxs-lookup"><span data-stu-id="a367d-120">Open it with the *Find in files* command (`Ctrl`+`Shift`+`F`) when you have a specific string of code you're trying to find in the source.</span></span> <span data-ttu-id="a367d-121">ツール バーには、正規表現など、さまざまな検索オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="a367d-121">The toolbar provides different search options, including regular expressions.</span></span> 

![デバッガー ファイルの検索](./media/debugger_file_search.png)

<span data-ttu-id="a367d-123">読み込まれたソース ファイルは、[ファイルを開く( ) ] コマンド*ですばやく* `Ctrl` + `P` 開く方法があります。</span><span class="sxs-lookup"><span data-stu-id="a367d-123">You can also quickly open any loaded source file with the *Open file* (`Ctrl`+`P`) command.</span></span>

![デバッガーの開いているファイル](./media/debugger_open_file.png)

## <span data-ttu-id="a367d-125">Edge DevTools プロトコルの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="a367d-125">Edge DevTools Protocol updates</span></span>

<span data-ttu-id="a367d-126">DevTools プロトコルのバージョン[0.2](../devtools-protocol/0.2/index.md)には、バージョン[0.1](../devtools-protocol/0.1/index.md)で導入されたコア スクリプトデバッグ機能に加えて、スタイルとレイアウト (読み取り専用) デバッグとコンソール API 用の新しいドメインが提供されています。</span><span class="sxs-lookup"><span data-stu-id="a367d-126">[Version 0.2](../devtools-protocol/0.2/index.md) of the DevTools Protocol provides new domains for style and layout (read-only) debugging and console APIs, in addition to the core script debugging functionality introduced in [Version 0.1](../devtools-protocol/0.1/index.md).</span></span> <span data-ttu-id="a367d-127">Edge DevTools UI では、これは要素[**(読**](../devtools-guide/elements.md)み取り専用操作用)、コンソール パネル、デバッガー パネルで利用可能な[**機能に**](../devtools-guide/console.md)[**変換**](../devtools-guide/debugger.md)されます。</span><span class="sxs-lookup"><span data-stu-id="a367d-127">In the Edge DevTools UI, this translates to functionality available in the [**Elements**](../devtools-guide/elements.md) (for read-only operations), [**Console**](../devtools-guide/console.md) and [**Debugger**](../devtools-guide/debugger.md) panels.</span></span>
