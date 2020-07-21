---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2Experimental
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2Experimental
ms.openlocfilehash: 98f13193e73781f9f7371db05ed3ca99ca93c128
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886545"
---
# <span data-ttu-id="450bf-104">インターフェイス ICoreWebView2Experimental</span><span class="sxs-lookup"><span data-stu-id="450bf-104">interface ICoreWebView2Experimental</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2Experimental
  : public IUnknown
```

## <span data-ttu-id="450bf-105">まとめ</span><span class="sxs-lookup"><span data-stu-id="450bf-105">Summary</span></span>

 <span data-ttu-id="450bf-106">Members</span><span class="sxs-lookup"><span data-stu-id="450bf-106">Members</span></span>                        | <span data-ttu-id="450bf-107">説明</span><span class="sxs-lookup"><span data-stu-id="450bf-107">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="450bf-108">add_WebResourceResponseReceived</span><span class="sxs-lookup"><span data-stu-id="450bf-108">add_WebResourceResponseReceived</span></span>](#add_webresourceresponsereceived) | <span data-ttu-id="450bf-109">WebResourceResponseReceived イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="450bf-109">Add an event handler for the WebResourceResponseReceived event.</span></span>
[<span data-ttu-id="450bf-110">remove_WebResourceResponseReceived</span><span class="sxs-lookup"><span data-stu-id="450bf-110">remove_WebResourceResponseReceived</span></span>](#remove_webresourceresponsereceived) | <span data-ttu-id="450bf-111">Add_WebResourceResponseReceived で以前に追加された WebResourceResponseReceived イベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="450bf-111">Removes the WebResourceResponseReceived event handler previously added with add_WebResourceResponseReceived.</span></span>

## <span data-ttu-id="450bf-112">Members</span><span class="sxs-lookup"><span data-stu-id="450bf-112">Members</span></span>

#### <span data-ttu-id="450bf-113">add_WebResourceResponseReceived</span><span class="sxs-lookup"><span data-stu-id="450bf-113">add_WebResourceResponseReceived</span></span> 

<span data-ttu-id="450bf-114">WebResourceResponseReceived イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="450bf-114">Add an event handler for the WebResourceResponseReceived event.</span></span>

> <span data-ttu-id="450bf-115">パブリック HRESULT [add_WebResourceResponseReceived](#add_webresourceresponsereceived)([ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler](icorewebview2experimentalwebresourceresponsereceivedeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="450bf-115">public HRESULT [add_WebResourceResponseReceived](#add_webresourceresponsereceived)([ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler](icorewebview2experimentalwebresourceresponsereceivedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="450bf-116">WebResourceResponseReceived イベントは、WebView が WebResource 要求に対する応答を受信して処理した後に発生します。</span><span class="sxs-lookup"><span data-stu-id="450bf-116">WebResourceResponseReceived event fires after the WebView has received and processed the response for a WebResource request.</span></span> <span data-ttu-id="450bf-117">イベント引数には、WebResourceResponse によって送信された WebResourceRequest が含まれています。これには、認証ヘッダーなど、関連付けられた WebResourceRequested イベントの一部として含まれていないネットワークスタックによって追加されたヘッダーも含まれています。</span><span class="sxs-lookup"><span data-stu-id="450bf-117">The event args include the WebResourceRequest as sent by the wire and WebResourceResponse received, including any additional headers added by the network stack that were not be included as part of the associated WebResourceRequested event, such as Authentication headers.</span></span> 
```cpp
    wil::com_ptr<ICoreWebView2Experimental> webviewExperimental;
    CHECK_FAILURE(m_appWindow->GetWebView()->QueryInterface(IID_PPV_ARGS(&webviewExperimental)));
    CHECK_FAILURE(webviewExperimental->add_WebResourceResponseReceived(
        Callback<ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler>(
            [this](
                ICoreWebView2Experimental* sender,
                ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs* args) {           
                wil::com_ptr<ICoreWebView2WebResourceRequest> request;
                CHECK_FAILURE(args->get_Request(&request));
                wil::unique_cotaskmem_string uri;
                CHECK_FAILURE(request->get_Uri(&uri));
                if (wcscmp(uri.get(), L"https://authenticationtest.com/HTTPAuth/") == 0)
                {
                    wil::com_ptr<ICoreWebView2HttpRequestHeaders> requestHeaders;
                    CHECK_FAILURE(request->get_Headers(&requestHeaders));

                    wil::unique_cotaskmem_string authHeaderValue;
                    if (requestHeaders->GetHeader(L"Authorization", &authHeaderValue) == S_OK)
                    {
                        std::wstring message(L"Authorization: ");
                        message += authHeaderValue.get();
                        MessageBox(nullptr, message.c_str(), nullptr, MB_OK);
                        m_appWindow->DeleteComponent(this);
                    }
                }
                
                return S_OK;
            })
            .Get(),
        &m_webResourceResponseReceivedToken));
```

#### <span data-ttu-id="450bf-118">remove_WebResourceResponseReceived</span><span class="sxs-lookup"><span data-stu-id="450bf-118">remove_WebResourceResponseReceived</span></span> 

<span data-ttu-id="450bf-119">Add_WebResourceResponseReceived で以前に追加された WebResourceResponseReceived イベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="450bf-119">Removes the WebResourceResponseReceived event handler previously added with add_WebResourceResponseReceived.</span></span>

> <span data-ttu-id="450bf-120">パブリック HRESULT [remove_WebResourceResponseReceived](#remove_webresourceresponsereceived)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="450bf-120">public HRESULT [remove_WebResourceResponseReceived](#remove_webresourceresponsereceived)(EventRegistrationToken token)</span></span>

