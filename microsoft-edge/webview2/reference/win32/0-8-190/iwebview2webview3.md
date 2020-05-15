---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 436e0e33180c65afcce0487fffeff5f168dceab7
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654164"
---
# <span data-ttu-id="b31c7-104">インターフェイス IWebView2WebView3</span><span class="sxs-lookup"><span data-stu-id="b31c7-104">interface IWebView2WebView3</span></span> 

> [!NOTE]
> <span data-ttu-id="b31c7-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b31c7-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="b31c7-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b31c7-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebView3
  : public IWebView2WebView
```

<span data-ttu-id="b31c7-107">プライマリ WebView オブジェクトによって実装されるその他の機能。</span><span class="sxs-lookup"><span data-stu-id="b31c7-107">Additional functionality implemented by the primary WebView object.</span></span>

## <span data-ttu-id="b31c7-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="b31c7-108">Summary</span></span>

 <span data-ttu-id="b31c7-109">Members</span><span class="sxs-lookup"><span data-stu-id="b31c7-109">Members</span></span>                        | <span data-ttu-id="b31c7-110">説明</span><span class="sxs-lookup"><span data-stu-id="b31c7-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b31c7-111">Stop</span><span class="sxs-lookup"><span data-stu-id="b31c7-111">Stop</span></span>](#stop) | <span data-ttu-id="b31c7-112">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="b31c7-112">Stop all navigations and pending resource fetches.</span></span>
[<span data-ttu-id="b31c7-113">add_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="b31c7-113">add_NewWindowRequested</span></span>](#add_newwindowrequested) | <span data-ttu-id="b31c7-114">NewWindowRequested イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b31c7-114">Add an event handler for the NewWindowRequested event.</span></span>
[<span data-ttu-id="b31c7-115">remove_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="b31c7-115">remove_NewWindowRequested</span></span>](#remove_newwindowrequested) | <span data-ttu-id="b31c7-116">Add_NewWindowRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="b31c7-116">Remove an event handler previously added with add_NewWindowRequested.</span></span>
[<span data-ttu-id="b31c7-117">add_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="b31c7-117">add_DocumentTitleChanged</span></span>](#add_documenttitlechanged) | <span data-ttu-id="b31c7-118">Documentechanged Lechanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b31c7-118">Add an event handler for the DocumentTitleChanged event.</span></span>
[<span data-ttu-id="b31c7-119">remove_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="b31c7-119">remove_DocumentTitleChanged</span></span>](#remove_documenttitlechanged) | <span data-ttu-id="b31c7-120">Add_DocumentTitleChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="b31c7-120">Remove an event handler previously added with add_DocumentTitleChanged.</span></span>
[<span data-ttu-id="b31c7-121">get_DocumentTitle</span><span class="sxs-lookup"><span data-stu-id="b31c7-121">get_DocumentTitle</span></span>](#get_documenttitle) | <span data-ttu-id="b31c7-122">現在のトップレベルドキュメントのタイトル。</span><span class="sxs-lookup"><span data-stu-id="b31c7-122">The title for the current top level document.</span></span>

<span data-ttu-id="b31c7-123">このインターフェイスの QueryInterface は、 [IWebView2WebView](IWebView2WebView.md)を実装するオブジェクトから行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b31c7-123">You can QueryInterface for this interface from the object that implements [IWebView2WebView](IWebView2WebView.md).</span></span> <span data-ttu-id="b31c7-124">詳細については、 [IWebView2WebView](IWebView2WebView.md)インターフェイスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b31c7-124">See the [IWebView2WebView](IWebView2WebView.md) interface for more details.</span></span>

## <span data-ttu-id="b31c7-125">Members</span><span class="sxs-lookup"><span data-stu-id="b31c7-125">Members</span></span>

#### <span data-ttu-id="b31c7-126">Stop</span><span class="sxs-lookup"><span data-stu-id="b31c7-126">Stop</span></span> 

<span data-ttu-id="b31c7-127">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="b31c7-127">Stop all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="b31c7-128">パブリック HRESULT [Stop](#stop)()</span><span class="sxs-lookup"><span data-stu-id="b31c7-128">public HRESULT [Stop](#stop)()</span></span>

#### <span data-ttu-id="b31c7-129">add_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="b31c7-129">add_NewWindowRequested</span></span> 

<span data-ttu-id="b31c7-130">NewWindowRequested イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b31c7-130">Add an event handler for the NewWindowRequested event.</span></span>

> <span data-ttu-id="b31c7-131">パブリック HRESULT [add_NewWindowRequested](#add_newwindowrequested)([IWebView2NewWindowRequestedEventHandler](IWebView2NewWindowRequestedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="b31c7-131">public HRESULT [add_NewWindowRequested](#add_newwindowrequested)([IWebView2NewWindowRequestedEventHandler](IWebView2NewWindowRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="b31c7-132">ウィンドウを開くなど、WebView 内のコンテンツが新しいウィンドウを開くように要求したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="b31c7-132">Fires when content inside the WebView requested to open a new window, such as through window.open.</span></span> <span data-ttu-id="b31c7-133">アプリは、開かれたウィンドウと見なされるターゲット webview を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="b31c7-133">The app can pass a target webview that will be considered the opened window.</span></span>

```cpp
    // Register a handler for the NewWindowRequested event.
    // This handler will defer the event, create a new app window, and then once the
    // new window is ready, it'll provide that new window's WebView as the response to
    // the request.
    CHECK_FAILURE(m_webView->add_NewWindowRequested(
        Callback<IWebView2NewWindowRequestedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2NewWindowRequestedEventArgs* args) {
                wil::com_ptr<IWebView2Deferral> deferral;
                CHECK_FAILURE(args->GetDeferral(&deferral));

                auto newAppWindow = new AppWindow(L"");
                newAppWindow->m_onWebViewFirstInitialized = [args, deferral, newAppWindow]() {
                    CHECK_FAILURE(args->put_NewWindow(newAppWindow->m_webView.get()));
                    CHECK_FAILURE(args->put_Handled(TRUE));
                    CHECK_FAILURE(deferral->Complete());
                };

                return S_OK;
            })
            .Get(),
        nullptr));
```

#### <span data-ttu-id="b31c7-134">remove_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="b31c7-134">remove_NewWindowRequested</span></span> 

<span data-ttu-id="b31c7-135">Add_NewWindowRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="b31c7-135">Remove an event handler previously added with add_NewWindowRequested.</span></span>

> <span data-ttu-id="b31c7-136">パブリック HRESULT [remove_NewWindowRequested](#remove_newwindowrequested)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="b31c7-136">public HRESULT [remove_NewWindowRequested](#remove_newwindowrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="b31c7-137">add_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="b31c7-137">add_DocumentTitleChanged</span></span> 

<span data-ttu-id="b31c7-138">Documentechanged Lechanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b31c7-138">Add an event handler for the DocumentTitleChanged event.</span></span>

> <span data-ttu-id="b31c7-139">パブリック HRESULT [add_DocumentTitleChanged](#add_documenttitlechanged)([IWebView2DocumentTitleChangedEventHandler](IWebView2DocumentTitleChangedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="b31c7-139">public HRESULT [add_DocumentTitleChanged](#add_documenttitlechanged)([IWebView2DocumentTitleChangedEventHandler](IWebView2DocumentTitleChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="b31c7-140">イベントは、WebView の DocumentTitle プロパティが変更されたとき、または NavigationCompleted イベントの前または後に発生する可能性があるときに発生します。</span><span class="sxs-lookup"><span data-stu-id="b31c7-140">The event fires when the DocumentTitle property of the WebView changes and may fire before or after the NavigationCompleted event.</span></span>

```cpp
    // Register a handler for the DocumentTitleChanged event.
    // This handler just announces the new title on the window's title bar.
    CHECK_FAILURE(m_webView->add_DocumentTitleChanged(
        Callback<IWebView2DocumentTitleChangedEventHandler>(
            [this](IWebView2WebView3* sender, IUnknown* args) -> HRESULT {
                wil::unique_cotaskmem_string title;
                CHECK_FAILURE(sender->get_DocumentTitle(&title));
                SetWindowText(m_appWindow->GetMainWindow(), title.get());
                return S_OK;
            })
            .Get(),
        &m_documentTitleChangedToken));
```

#### <span data-ttu-id="b31c7-141">remove_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="b31c7-141">remove_DocumentTitleChanged</span></span> 

<span data-ttu-id="b31c7-142">Add_DocumentTitleChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="b31c7-142">Remove an event handler previously added with add_DocumentTitleChanged.</span></span>

> <span data-ttu-id="b31c7-143">パブリック HRESULT [remove_DocumentTitleChanged](#remove_documenttitlechanged)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="b31c7-143">public HRESULT [remove_DocumentTitleChanged](#remove_documenttitlechanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="b31c7-144">get_DocumentTitle</span><span class="sxs-lookup"><span data-stu-id="b31c7-144">get_DocumentTitle</span></span> 

<span data-ttu-id="b31c7-145">現在のトップレベルドキュメントのタイトル。</span><span class="sxs-lookup"><span data-stu-id="b31c7-145">The title for the current top level document.</span></span>

> <span data-ttu-id="b31c7-146">パブリック HRESULT [get_DocumentTitle](#get_documenttitle)(LPWSTR \* title)</span><span class="sxs-lookup"><span data-stu-id="b31c7-146">public HRESULT [get_DocumentTitle](#get_documenttitle)(LPWSTR \* title)</span></span>

<span data-ttu-id="b31c7-147">ドキュメントに明示的なタイトルが含まれていない場合、または空の場合は、ドキュメントの URI と一致しないかもしれない既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b31c7-147">If the document has no explicit title or is otherwise empty, a default that may or may not match the URI of the document will be used.</span></span>

