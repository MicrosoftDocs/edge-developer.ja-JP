---
description: スレッドモデル
title: スレッドモデル
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: ad51afee97d3cc3e913ecdd73c4f0c2a99c70564
ms.sourcegitcommit: 553957c101f83681b363103cb6af56bf20173f23
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "10895561"
---
# <span data-ttu-id="f7bc6-104">スレッドモデル</span><span class="sxs-lookup"><span data-stu-id="f7bc6-104">Threading model</span></span>  

## <span data-ttu-id="f7bc6-105">スレッド セーフティ</span><span class="sxs-lookup"><span data-stu-id="f7bc6-105">Thread safety</span></span>  

<span data-ttu-id="f7bc6-106">WebView2 は、UI スレッドで作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7bc6-106">The WebView2 must be created on a UI thread.</span></span>  <span data-ttu-id="f7bc6-107">特にメッセージポンプを持つスレッド。</span><span class="sxs-lookup"><span data-stu-id="f7bc6-107">Specifically a thread with a message pump.</span></span>  <span data-ttu-id="f7bc6-108">このスレッドですべてのコールバックが発生し、WebView2 への要求はそのスレッドで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7bc6-108">All callbacks occur on that thread and requests into the WebView2 must be done on that thread.</span></span>  <span data-ttu-id="f7bc6-109">別のスレッドから WebView2 を使うことは安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="f7bc6-109">It is not safe to use the WebView2 from another thread.</span></span>  

<span data-ttu-id="f7bc6-110">このプロパティの唯一の例外は `Content` `CoreWebView2WebResourceRequest` です。</span><span class="sxs-lookup"><span data-stu-id="f7bc6-110">The only exception is for the `Content` property of `CoreWebView2WebResourceRequest`.</span></span>  <span data-ttu-id="f7bc6-111">`Content`プロパティストリームは、バックグラウンドスレッドから読み取ります。</span><span class="sxs-lookup"><span data-stu-id="f7bc6-111">The `Content` property stream is read from a background thread.</span></span>  <span data-ttu-id="f7bc6-112">UI スレッドへのパフォーマンスへの影響を防ぐために、ストリームは、バックグラウンド STA から作成するか、または作成してください。</span><span class="sxs-lookup"><span data-stu-id="f7bc6-112">The stream should be agile or be created from a background STA to prevent performance impact to the UI thread.</span></span>  

## <span data-ttu-id="f7bc6-113">再</span><span class="sxs-lookup"><span data-stu-id="f7bc6-113">Reentrancy</span></span>  

<span data-ttu-id="f7bc6-114">イベントハンドラーと完了ハンドラーを含むコールバックは逐次実行されます。</span><span class="sxs-lookup"><span data-stu-id="f7bc6-114">Callbacks including event handlers and completion handlers run serially.</span></span>  <span data-ttu-id="f7bc6-115">イベントハンドラーを実行していて、メッセージループを開始した場合、他のイベントハンドラーまたは完了コールバックは再入可能な方法で開始できません。</span><span class="sxs-lookup"><span data-stu-id="f7bc6-115">If you have an event handler running and begin a message loop, no other event handlers or completion callbacks are able to begin running in a reentrant manner.</span></span>  

## <span data-ttu-id="f7bc6-116">保留</span><span class="sxs-lookup"><span data-stu-id="f7bc6-116">Deferrals</span></span>  

<span data-ttu-id="f7bc6-117">一部の WebView2 イベントは、イベント引数で設定された値を読み取ります。または、イベントハンドラーの完了後に何らかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7bc6-117">Some WebView2 events read values set on their event args or perform some action after the event handler completes.</span></span>  <span data-ttu-id="f7bc6-118">また、イベントハンドラーなどの非同期操作も実行する必要がある場合は、 `GetDeferral` 関連付けられているイベントのイベント引数でメソッドを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="f7bc6-118">If you also need to run an asynchronous operation such an event handler, you may use the `GetDeferral` method on the event args of the associated events.</span></span>  <span data-ttu-id="f7bc6-119">返された繰延オブジェクトは、のメソッドが要求されるまで、イベントハンドラーが完了したと見なされないようにし `Complete` `Deferral` ます。</span><span class="sxs-lookup"><span data-stu-id="f7bc6-119">The returned Deferral object ensures the event handler is not considered complete until the `Complete` method of the `Deferral` is requested.</span></span>  

<span data-ttu-id="f7bc6-120">たとえば、イベントを使うと、 `NewWindowRequested` `CoreWebView2` イベントハンドラーが完了したときに、子ウィンドウとして接続することができます。</span><span class="sxs-lookup"><span data-stu-id="f7bc6-120">For instance, you may use the `NewWindowRequested` event to provide a `CoreWebView2` to connect as a child window when the event handler completes.</span></span>  <span data-ttu-id="f7bc6-121">ただし、を非同期的に作成する必要がある場合は、 `CoreWebView2` `GetDeferral` のメソッドをに要求し `NewWindowRequestedEventArgs` ます。</span><span class="sxs-lookup"><span data-stu-id="f7bc6-121">But if you need to asynchronously create the `CoreWebView2`, request the `GetDeferral` method on the `NewWindowRequestedEventArgs`.</span></span>  <span data-ttu-id="f7bc6-122">非同期的にを作成 `CoreWebView2` してプロパティをに設定すると `NewWindow` 、その `NewWindowRequestedEventArgs` `Complete` `Deferral` メソッドを使ってオブジェクトの要求が返され `GetDeferral` ます。</span><span class="sxs-lookup"><span data-stu-id="f7bc6-122">After you have asynchronously created the `CoreWebView2` and set the `NewWindow` property on the `NewWindowRequestedEventArgs`, request `Complete` on the `Deferral` object be returned using the `GetDeferral` method.</span></span>  

<!-- links -->  
