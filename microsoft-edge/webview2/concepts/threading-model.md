---
description: スレッド化
title: スレッド化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 61e3b7fc8d25e2a1ce9c60fb84f5f39ba43f281b
ms.sourcegitcommit: efdc6369c48942bfa39e45c713300ed70f0e3655
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "11013738"
---
# <span data-ttu-id="5d9d6-104">スレッド化</span><span class="sxs-lookup"><span data-stu-id="5d9d6-104">Threading model</span></span> 

<span data-ttu-id="5d9d6-105">WebView2 コントロールは、 [コンポーネントオブジェクトモデル (COM)](https://docs.microsoft.com/windows/win32/com/the-component-object-model) に基づいており、 [シングルスレッドアパートメント (STA)](https://docs.microsoft.com/windows/win32/com/single-threaded-apartments) スレッドで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d9d6-105">The WebView2 control is based on the [Component Object Model (COM)](https://docs.microsoft.com/windows/win32/com/the-component-object-model) and must run on a [Single Threaded Apartments (STA)](https://docs.microsoft.com/windows/win32/com/single-threaded-apartments) thread.</span></span>

## <span data-ttu-id="5d9d6-106">スレッド セーフティ</span><span class="sxs-lookup"><span data-stu-id="5d9d6-106">Thread safety</span></span>  

<span data-ttu-id="5d9d6-107">WebView2 は、UI スレッドで作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d9d6-107">The WebView2 must be created on a UI thread.</span></span>  <span data-ttu-id="5d9d6-108">特にメッセージポンプを持つスレッド。</span><span class="sxs-lookup"><span data-stu-id="5d9d6-108">Specifically a thread with a message pump.</span></span>  <span data-ttu-id="5d9d6-109">このスレッドですべてのコールバックが発生し、WebView2 への要求はそのスレッドで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d9d6-109">All callbacks occur on that thread and requests into the WebView2 must be done on that thread.</span></span>  <span data-ttu-id="5d9d6-110">別のスレッドから WebView2 を使うことは安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="5d9d6-110">It is not safe to use the WebView2 from another thread.</span></span>  

<span data-ttu-id="5d9d6-111">このプロパティの唯一の例外は `Content` `CoreWebView2WebResourceRequest` です。</span><span class="sxs-lookup"><span data-stu-id="5d9d6-111">The only exception is for the `Content` property of `CoreWebView2WebResourceRequest`.</span></span>  <span data-ttu-id="5d9d6-112">`Content`プロパティストリームは、バックグラウンドスレッドから読み取ります。</span><span class="sxs-lookup"><span data-stu-id="5d9d6-112">The `Content` property stream is read from a background thread.</span></span>  <span data-ttu-id="5d9d6-113">UI スレッドへのパフォーマンスへの影響を防ぐために、ストリームは、バックグラウンド STA から作成するか、または作成してください。</span><span class="sxs-lookup"><span data-stu-id="5d9d6-113">The stream should be agile or be created from a background STA to prevent performance impact to the UI thread.</span></span>  

## <span data-ttu-id="5d9d6-114">再</span><span class="sxs-lookup"><span data-stu-id="5d9d6-114">Reentrancy</span></span>  

<span data-ttu-id="5d9d6-115">イベントハンドラーと完了ハンドラーを含むコールバックは逐次実行されます。</span><span class="sxs-lookup"><span data-stu-id="5d9d6-115">Callbacks including event handlers and completion handlers run serially.</span></span>  <span data-ttu-id="5d9d6-116">イベントハンドラーを実行していて、メッセージループを開始した場合、他のイベントハンドラーまたは完了コールバックは再入可能な方法で開始できません。</span><span class="sxs-lookup"><span data-stu-id="5d9d6-116">If you have an event handler running and begin a message loop, no other event handlers or completion callbacks are able to begin running in a reentrant manner.</span></span>  

## <span data-ttu-id="5d9d6-117">保留</span><span class="sxs-lookup"><span data-stu-id="5d9d6-117">Deferrals</span></span>  

<span data-ttu-id="5d9d6-118">一部の WebView2 イベントは、イベント引数で設定された値を読み取ります。または、イベントハンドラーの完了後に何らかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="5d9d6-118">Some WebView2 events read values set on their event args or perform some action after the event handler completes.</span></span>  <span data-ttu-id="5d9d6-119">また、イベントハンドラーなどの非同期操作も実行する必要がある場合は、 `GetDeferral` 関連付けられているイベントのイベント引数でメソッドを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="5d9d6-119">If you also need to run an asynchronous operation such an event handler, you may use the `GetDeferral` method on the event args of the associated events.</span></span>  <span data-ttu-id="5d9d6-120">返された繰延オブジェクトは、のメソッドが要求されるまで、イベントハンドラーが完了したと見なされないようにし `Complete` `Deferral` ます。</span><span class="sxs-lookup"><span data-stu-id="5d9d6-120">The returned Deferral object ensures the event handler is not considered complete until the `Complete` method of the `Deferral` is requested.</span></span>  

<span data-ttu-id="5d9d6-121">たとえば、イベントを使うと、 `NewWindowRequested` `CoreWebView2` イベントハンドラーが完了したときに、子ウィンドウとして接続することができます。</span><span class="sxs-lookup"><span data-stu-id="5d9d6-121">For instance, you may use the `NewWindowRequested` event to provide a `CoreWebView2` to connect as a child window when the event handler completes.</span></span>  <span data-ttu-id="5d9d6-122">ただし、を非同期的に作成する必要がある場合は、 `CoreWebView2` `GetDeferral` のメソッドをに要求し `NewWindowRequestedEventArgs` ます。</span><span class="sxs-lookup"><span data-stu-id="5d9d6-122">But if you need to asynchronously create the `CoreWebView2`, request the `GetDeferral` method on the `NewWindowRequestedEventArgs`.</span></span>  <span data-ttu-id="5d9d6-123">非同期的にを作成 `CoreWebView2` してプロパティをに設定すると `NewWindow` 、その `NewWindowRequestedEventArgs` `Complete` `Deferral` メソッドを使ってオブジェクトの要求が返され `GetDeferral` ます。</span><span class="sxs-lookup"><span data-stu-id="5d9d6-123">After you have asynchronously created the `CoreWebView2` and set the `NewWindow` property on the `NewWindowRequestedEventArgs`, request `Complete` on the `Deferral` object be returned using the `GetDeferral` method.</span></span>  

<!-- links -->  
