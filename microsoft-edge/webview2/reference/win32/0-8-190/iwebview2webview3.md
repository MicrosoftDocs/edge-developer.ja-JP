---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2WebView3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: a095b1ed085cd49a597195e01da21cde53b9095d
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884744"
---
# <span data-ttu-id="84a4a-104">0.8.355-インターフェイス IWebView2WebView3</span><span class="sxs-lookup"><span data-stu-id="84a4a-104">0.8.355 - interface IWebView2WebView3</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2WebView3
  : public IWebView2WebView
```

<span data-ttu-id="84a4a-105">プライマリ WebView オブジェクトによって実装されるその他の機能。</span><span class="sxs-lookup"><span data-stu-id="84a4a-105">Additional functionality implemented by the primary WebView object.</span></span>

## <span data-ttu-id="84a4a-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="84a4a-106">Summary</span></span>

 <span data-ttu-id="84a4a-107">Members</span><span class="sxs-lookup"><span data-stu-id="84a4a-107">Members</span></span>                        | <span data-ttu-id="84a4a-108">説明</span><span class="sxs-lookup"><span data-stu-id="84a4a-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="84a4a-109">Stop</span><span class="sxs-lookup"><span data-stu-id="84a4a-109">Stop</span></span>](#stop) | <span data-ttu-id="84a4a-110">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="84a4a-110">Stop all navigations and pending resource fetches.</span></span>
[<span data-ttu-id="84a4a-111">add_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="84a4a-111">add_NewWindowRequested</span></span>](#add_newwindowrequested) | <span data-ttu-id="84a4a-112">NewWindowRequested イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="84a4a-112">Add an event handler for the NewWindowRequested event.</span></span>
[<span data-ttu-id="84a4a-113">remove_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="84a4a-113">remove_NewWindowRequested</span></span>](#remove_newwindowrequested) | <span data-ttu-id="84a4a-114">Add_NewWindowRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="84a4a-114">Remove an event handler previously added with add_NewWindowRequested.</span></span>
[<span data-ttu-id="84a4a-115">add_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="84a4a-115">add_DocumentTitleChanged</span></span>](#add_documenttitlechanged) | <span data-ttu-id="84a4a-116">Documentechanged Lechanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="84a4a-116">Add an event handler for the DocumentTitleChanged event.</span></span>
[<span data-ttu-id="84a4a-117">remove_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="84a4a-117">remove_DocumentTitleChanged</span></span>](#remove_documenttitlechanged) | <span data-ttu-id="84a4a-118">Add_DocumentTitleChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="84a4a-118">Remove an event handler previously added with add_DocumentTitleChanged.</span></span>
[<span data-ttu-id="84a4a-119">get_DocumentTitle</span><span class="sxs-lookup"><span data-stu-id="84a4a-119">get_DocumentTitle</span></span>](#get_documenttitle) | <span data-ttu-id="84a4a-120">現在のトップレベルドキュメントのタイトル。</span><span class="sxs-lookup"><span data-stu-id="84a4a-120">The title for the current top level document.</span></span>

<span data-ttu-id="84a4a-121">このインターフェイスの QueryInterface は、 [IWebView2WebView](IWebView2WebView.md)を実装するオブジェクトから行うことができます。</span><span class="sxs-lookup"><span data-stu-id="84a4a-121">You can QueryInterface for this interface from the object that implements [IWebView2WebView](IWebView2WebView.md).</span></span> <span data-ttu-id="84a4a-122">詳細については、 [IWebView2WebView](IWebView2WebView.md)インターフェイスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="84a4a-122">See the [IWebView2WebView](IWebView2WebView.md) interface for more details.</span></span>

## <span data-ttu-id="84a4a-123">Members</span><span class="sxs-lookup"><span data-stu-id="84a4a-123">Members</span></span>

#### <span data-ttu-id="84a4a-124">Stop</span><span class="sxs-lookup"><span data-stu-id="84a4a-124">Stop</span></span> 

<span data-ttu-id="84a4a-125">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="84a4a-125">Stop all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="84a4a-126">パブリック HRESULT [Stop](#stop)()</span><span class="sxs-lookup"><span data-stu-id="84a4a-126">public HRESULT [Stop](#stop)()</span></span>

#### <span data-ttu-id="84a4a-127">add_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="84a4a-127">add_NewWindowRequested</span></span> 

<span data-ttu-id="84a4a-128">NewWindowRequested イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="84a4a-128">Add an event handler for the NewWindowRequested event.</span></span>

> <span data-ttu-id="84a4a-129">パブリック HRESULT [add_NewWindowRequested](#add_newwindowrequested)([IWebView2NewWindowRequestedEventHandler](IWebView2NewWindowRequestedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="84a4a-129">public HRESULT [add_NewWindowRequested](#add_newwindowrequested)([IWebView2NewWindowRequestedEventHandler](IWebView2NewWindowRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="84a4a-130">ウィンドウを開くなど、WebView 内のコンテンツが新しいウィンドウを開くように要求したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="84a4a-130">Fires when content inside the WebView requested to open a new window, such as through window.open.</span></span> <span data-ttu-id="84a4a-131">アプリは、開かれたウィンドウと見なされるターゲット webview を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="84a4a-131">The app can pass a target webview that will be considered the opened window.</span></span>

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

#### <span data-ttu-id="84a4a-132">remove_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="84a4a-132">remove_NewWindowRequested</span></span> 

<span data-ttu-id="84a4a-133">Add_NewWindowRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="84a4a-133">Remove an event handler previously added with add_NewWindowRequested.</span></span>

> <span data-ttu-id="84a4a-134">パブリック HRESULT [remove_NewWindowRequested](#remove_newwindowrequested)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="84a4a-134">public HRESULT [remove_NewWindowRequested](#remove_newwindowrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="84a4a-135">add_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="84a4a-135">add_DocumentTitleChanged</span></span> 

<span data-ttu-id="84a4a-136">Documentechanged Lechanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="84a4a-136">Add an event handler for the DocumentTitleChanged event.</span></span>

> <span data-ttu-id="84a4a-137">パブリック HRESULT [add_DocumentTitleChanged](#add_documenttitlechanged)([IWebView2DocumentTitleChangedEventHandler](IWebView2DocumentTitleChangedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="84a4a-137">public HRESULT [add_DocumentTitleChanged](#add_documenttitlechanged)([IWebView2DocumentTitleChangedEventHandler](IWebView2DocumentTitleChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="84a4a-138">イベントは、WebView の DocumentTitle プロパティが変更されたとき、または NavigationCompleted イベントの前または後に発生する可能性があるときに発生します。</span><span class="sxs-lookup"><span data-stu-id="84a4a-138">The event fires when the DocumentTitle property of the WebView changes and may fire before or after the NavigationCompleted event.</span></span>

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

#### <span data-ttu-id="84a4a-139">remove_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="84a4a-139">remove_DocumentTitleChanged</span></span> 

<span data-ttu-id="84a4a-140">Add_DocumentTitleChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="84a4a-140">Remove an event handler previously added with add_DocumentTitleChanged.</span></span>

> <span data-ttu-id="84a4a-141">パブリック HRESULT [remove_DocumentTitleChanged](#remove_documenttitlechanged)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="84a4a-141">public HRESULT [remove_DocumentTitleChanged](#remove_documenttitlechanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="84a4a-142">get_DocumentTitle</span><span class="sxs-lookup"><span data-stu-id="84a4a-142">get_DocumentTitle</span></span> 

<span data-ttu-id="84a4a-143">現在のトップレベルドキュメントのタイトル。</span><span class="sxs-lookup"><span data-stu-id="84a4a-143">The title for the current top level document.</span></span>

> <span data-ttu-id="84a4a-144">パブリック HRESULT [get_DocumentTitle](#get_documenttitle)(LPWSTR \* title)</span><span class="sxs-lookup"><span data-stu-id="84a4a-144">public HRESULT [get_DocumentTitle](#get_documenttitle)(LPWSTR \* title)</span></span>

<span data-ttu-id="84a4a-145">ドキュメントに明示的なタイトルが含まれていない場合、または空の場合は、ドキュメントの URI と一致しないかもしれない既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="84a4a-145">If the document has no explicit title or is otherwise empty, a default that may or may not match the URI of the document will be used.</span></span>

