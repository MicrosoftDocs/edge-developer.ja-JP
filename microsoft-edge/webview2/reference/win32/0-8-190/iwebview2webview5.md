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
ms.openlocfilehash: 3c32cd59e75eb81bf69661d01f6044a0628ba35d
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654159"
---
# <span data-ttu-id="3b730-104">インターフェイス IWebView2WebView5</span><span class="sxs-lookup"><span data-stu-id="3b730-104">interface IWebView2WebView5</span></span> 

> [!NOTE]
> <span data-ttu-id="3b730-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3b730-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="3b730-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b730-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebView5
  : public IWebView2WebView4
```

<span data-ttu-id="3b730-107">プライマリ WebView オブジェクトによって実装されるその他の機能。</span><span class="sxs-lookup"><span data-stu-id="3b730-107">Additional functionality implemented by the primary WebView object.</span></span>

## <span data-ttu-id="3b730-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="3b730-108">Summary</span></span>

 <span data-ttu-id="3b730-109">Members</span><span class="sxs-lookup"><span data-stu-id="3b730-109">Members</span></span>                        | <span data-ttu-id="3b730-110">説明</span><span class="sxs-lookup"><span data-stu-id="3b730-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3b730-111">add_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="3b730-111">add_ContainsFullScreenElementChanged</span></span>](#add_containsfullscreenelementchanged) | <span data-ttu-id="3b730-112">"の場合、要素のプロパティが変更されたときに通知します。</span><span class="sxs-lookup"><span data-stu-id="3b730-112">Notifies when the ContainsFullScreenElement property changes.</span></span>
[<span data-ttu-id="3b730-113">remove_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="3b730-113">remove_ContainsFullScreenElementChanged</span></span>](#remove_containsfullscreenelementchanged) | <span data-ttu-id="3b730-114">対応する add_ イベントメソッドを使用して、前に追加したイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="3b730-114">Remove an event handler previously added with the corresponding add_ event method.</span></span>
[<span data-ttu-id="3b730-115">get_ContainsFullScreenElement</span><span class="sxs-lookup"><span data-stu-id="3b730-115">get_ContainsFullScreenElement</span></span>](#get_containsfullscreenelement) | <span data-ttu-id="3b730-116">WebView にフルスクリーン HTML 要素が含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="3b730-116">Indicates if the WebView contains a fullscreen HTML element.</span></span>
[<span data-ttu-id="3b730-117">add_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="3b730-117">add_WebResourceRequested</span></span>](#add_webresourcerequested) | <span data-ttu-id="3b730-118">WebResourceRequested イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="3b730-118">Add an event handler for the WebResourceRequested event.</span></span>
[<span data-ttu-id="3b730-119">AddWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="3b730-119">AddWebResourceRequestedFilter</span></span>](#addwebresourcerequestedfilter) | <span data-ttu-id="3b730-120">URI とリソースのコンテキストフィルターを WebResourceRequested イベントに追加します。</span><span class="sxs-lookup"><span data-stu-id="3b730-120">Adds a URI and resource context filter to the WebResourceRequested event.</span></span>
[<span data-ttu-id="3b730-121">RemoveWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="3b730-121">RemoveWebResourceRequestedFilter</span></span>](#removewebresourcerequestedfilter) | <span data-ttu-id="3b730-122">以前に WebResourceRequested イベントに追加された、一致する WebResource フィルターを削除します。</span><span class="sxs-lookup"><span data-stu-id="3b730-122">Removes a matching WebResource filter that was previously added for the WebResourceRequested event.</span></span>

<span data-ttu-id="3b730-123">このインターフェイスの QueryInterface は、 [IWebView2WebView](IWebView2WebView.md)を実装するオブジェクトから行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3b730-123">You can QueryInterface for this interface from the object that implements [IWebView2WebView](IWebView2WebView.md).</span></span> <span data-ttu-id="3b730-124">詳細については、 [IWebView2WebView](IWebView2WebView.md)インターフェイスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b730-124">See the [IWebView2WebView](IWebView2WebView.md) interface for more details.</span></span>

## <span data-ttu-id="3b730-125">Members</span><span class="sxs-lookup"><span data-stu-id="3b730-125">Members</span></span>

#### <span data-ttu-id="3b730-126">add_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="3b730-126">add_ContainsFullScreenElementChanged</span></span> 

<span data-ttu-id="3b730-127">"の場合、要素のプロパティが変更されたときに通知します。</span><span class="sxs-lookup"><span data-stu-id="3b730-127">Notifies when the ContainsFullScreenElement property changes.</span></span>

> <span data-ttu-id="3b730-128">パブリック HRESULT [add_ContainsFullScreenElementChanged](#add_containsfullscreenelementchanged)([IWebView2ContainsFullScreenElementChangedEventHandler](IWebView2ContainsFullScreenElementChangedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="3b730-128">public HRESULT [add_ContainsFullScreenElementChanged](#add_containsfullscreenelementchanged)([IWebView2ContainsFullScreenElementChangedEventHandler](IWebView2ContainsFullScreenElementChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="3b730-129">これは、WebView 内の HTML 要素が、WebView のサイズまたはフルスクリーンのままであることを意味します。</span><span class="sxs-lookup"><span data-stu-id="3b730-129">This means that an HTML element inside the WebView is entering fullscreen to the size of the WebView or leaving fullscreen.</span></span> <span data-ttu-id="3b730-130">このイベントは、たとえば、ビデオ要素が全画面表示になっている要求の場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="3b730-130">This event is useful when, for example, a video element requests to go fullscreen.</span></span> <span data-ttu-id="3b730-131">次に、Fullfullscreenelementelementのリスナーが、応答で WebView のサイズを変更できます。</span><span class="sxs-lookup"><span data-stu-id="3b730-131">The listener of ContainsFullScreenElementChanged can then resize the WebView in response.</span></span>

```cpp
    // Register a handler for the ContainsFullScreenChanged event.
    CHECK_FAILURE(m_webView->add_ContainsFullScreenElementChanged(
        Callback<IWebView2ContainsFullScreenElementChangedEventHandler>(
            [this](IWebView2WebView5* sender, IUnknown* args) -> HRESULT {
                if (m_fullScreenAllowed)
                {
                    CHECK_FAILURE(sender->get_ContainsFullScreenElement(&m_containsFullscreenElement));
                    if (m_containsFullscreenElement)
                    {
                        EnterFullScreen();
                    }
                    else
                    {
                        ExitFullScreen();
                    }
                }
                return S_OK;
            })
            .Get(),
        nullptr));
```

#### <span data-ttu-id="3b730-132">remove_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="3b730-132">remove_ContainsFullScreenElementChanged</span></span> 

<span data-ttu-id="3b730-133">対応する add_ イベントメソッドを使用して、前に追加したイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="3b730-133">Remove an event handler previously added with the corresponding add_ event method.</span></span>

> <span data-ttu-id="3b730-134">パブリック HRESULT [remove_ContainsFullScreenElementChanged](#remove_containsfullscreenelementchanged)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="3b730-134">public HRESULT [remove_ContainsFullScreenElementChanged](#remove_containsfullscreenelementchanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="3b730-135">get_ContainsFullScreenElement</span><span class="sxs-lookup"><span data-stu-id="3b730-135">get_ContainsFullScreenElement</span></span> 

<span data-ttu-id="3b730-136">WebView にフルスクリーン HTML 要素が含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="3b730-136">Indicates if the WebView contains a fullscreen HTML element.</span></span>

> <span data-ttu-id="3b730-137">パブリック HRESULT [get_ContainsFullScreenElement](#get_containsfullscreenelement)(BOOL \* Fullfullscreenelement)</span><span class="sxs-lookup"><span data-stu-id="3b730-137">public HRESULT [get_ContainsFullScreenElement](#get_containsfullscreenelement)(BOOL \* containsFullScreenElement)</span></span>

#### <span data-ttu-id="3b730-138">add_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="3b730-138">add_WebResourceRequested</span></span> 

<span data-ttu-id="3b730-139">WebResourceRequested イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="3b730-139">Add an event handler for the WebResourceRequested event.</span></span>

> <span data-ttu-id="3b730-140">パブリック HRESULT [add_WebResourceRequested](#add_webresourcerequested)([IWebView2WebResourceRequestedEventHandler](IWebView2WebResourceRequestedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="3b730-140">public HRESULT [add_WebResourceRequested](#add_webresourcerequested)([IWebView2WebResourceRequestedEventHandler](IWebView2WebResourceRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="3b730-141">AddWebResourceRequestedFilter で追加された一致する URL とリソースコンテキストフィルターへの HTTP 要求を WebView が実行しているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3b730-141">Fires when the WebView is performing an HTTP request to a matching URL and resource context filter that was added with AddWebResourceRequestedFilter.</span></span> <span data-ttu-id="3b730-142">イベントを発生させるには、少なくとも1つのフィルターを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b730-142">At least one filter must be added for the event to fire.</span></span>

```cpp
        if (m_blockImages)
        {
            m_webView->AddWebResourceRequestedFilter(L"*", WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE);
            CHECK_FAILURE(m_webView->add_WebResourceRequested(
                Callback<IWebView2WebResourceRequestedEventHandler>(
                    [this](
                        IWebView2WebView* sender,
                        IWebView2WebResourceRequestedEventArgs* args) {
                        wil::com_ptr<IWebView2WebResourceRequestedEventArgs2>
                            webResourceEventArgs2;
                        args->QueryInterface(IID_PPV_ARGS(&webResourceEventArgs2));
                        WEBVIEW2_WEB_RESOURCE_CONTEXT resourceContext;
                        CHECK_FAILURE(
                            webResourceEventArgs2->get_ResourceContext(&resourceContext));
                        // Ensure that the type is image
                        if (resourceContext != WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE)
                        {
                            return E_INVALIDARG;
                        }
                        // Override the response with an empty one to block the image.
                        // If put_Response is not called, the request will continue as normal.
                        wil::com_ptr<IWebView2WebResourceResponse> response;
                        CHECK_FAILURE(m_webViewEnvironment->CreateWebResourceResponse(
                            nullptr, 403 /*NoContent*/, L"Blocked", L"", &response));
                        CHECK_FAILURE(args->put_Response(response.get()));
                        return S_OK;
                    })
                    .Get(),
                &m_webResourceRequestedTokenForImageBlocking));
        }
        else
        {
            CHECK_FAILURE(m_webView->remove_WebResourceRequested(
                m_webResourceRequestedTokenForImageBlocking));
        }
```

#### <span data-ttu-id="3b730-143">AddWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="3b730-143">AddWebResourceRequestedFilter</span></span> 

<span data-ttu-id="3b730-144">URI とリソースのコンテキストフィルターを WebResourceRequested イベントに追加します。</span><span class="sxs-lookup"><span data-stu-id="3b730-144">Adds a URI and resource context filter to the WebResourceRequested event.</span></span>

> <span data-ttu-id="3b730-145">パブリック HRESULT [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)(LPCWSTR const uri、[WEBVIEW2_WEB_RESOURCE_CONTEXT](IWebView2WebView.md#webview2_web_resource_context) const resourcecontext)</span><span class="sxs-lookup"><span data-stu-id="3b730-145">public HRESULT [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)(LPCWSTR const uri,[WEBVIEW2_WEB_RESOURCE_CONTEXT](IWebView2WebView.md#webview2_web_resource_context) const resourceContext)</span></span>

<span data-ttu-id="3b730-146">URI パラメーターは、ワイルドカード文字列 (0 以上、"?": 完全に1つ) にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3b730-146">URI parameter can be a wildcard string ('': zero or more, '?': exactly one).</span></span> <span data-ttu-id="3b730-147">nullptr は、L "" と同じです。</span><span class="sxs-lookup"><span data-stu-id="3b730-147">nullptr is equivalent to L"".</span></span> <span data-ttu-id="3b730-148">リソースコンテキストフィルターの説明については、「enum の WEBVIEW2_WEB_RESOURCE_CONTEXT」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b730-148">See WEBVIEW2_WEB_RESOURCE_CONTEXT enum for description of resource context filters.</span></span>

#### <span data-ttu-id="3b730-149">RemoveWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="3b730-149">RemoveWebResourceRequestedFilter</span></span> 

<span data-ttu-id="3b730-150">以前に WebResourceRequested イベントに追加された、一致する WebResource フィルターを削除します。</span><span class="sxs-lookup"><span data-stu-id="3b730-150">Removes a matching WebResource filter that was previously added for the WebResourceRequested event.</span></span>

> <span data-ttu-id="3b730-151">パブリック HRESULT [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)(LPCWSTR const uri、[WEBVIEW2_WEB_RESOURCE_CONTEXT](IWebView2WebView.md#webview2_web_resource_context) const resourcecontext)</span><span class="sxs-lookup"><span data-stu-id="3b730-151">public HRESULT [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)(LPCWSTR const uri,[WEBVIEW2_WEB_RESOURCE_CONTEXT](IWebView2WebView.md#webview2_web_resource_context) const resourceContext)</span></span>

<span data-ttu-id="3b730-152">同じフィルターが複数回追加された場合は、削除が有効になるまで何度も削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b730-152">If the same filter was added multiple times, then it will need to be removed as many times as it was added for the removal to be effective.</span></span> <span data-ttu-id="3b730-153">追加されていないフィルターの E_INVALIDARG を返します。</span><span class="sxs-lookup"><span data-stu-id="3b730-153">Returns E_INVALIDARG for a filter that was never added.</span></span>

