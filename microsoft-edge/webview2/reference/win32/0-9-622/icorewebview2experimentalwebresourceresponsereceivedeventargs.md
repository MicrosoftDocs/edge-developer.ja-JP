---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs
ms.openlocfilehash: 552421aa003be2ea52493f16ad94ed2b08e8c3a9
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012315"
---
# <span data-ttu-id="ed08d-104">インターフェイス ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="ed08d-104">interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="ed08d-105">WebResourceResponseReceived イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="ed08d-105">Event args for the WebResourceResponseReceived event.</span></span>

## <span data-ttu-id="ed08d-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="ed08d-106">Summary</span></span>

 <span data-ttu-id="ed08d-107">Members</span><span class="sxs-lookup"><span data-stu-id="ed08d-107">Members</span></span>                        | <span data-ttu-id="ed08d-108">説明</span><span class="sxs-lookup"><span data-stu-id="ed08d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ed08d-109">get_Request</span><span class="sxs-lookup"><span data-stu-id="ed08d-109">get_Request</span></span>](#get_request) | <span data-ttu-id="ed08d-110">Web リソース要求オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ed08d-110">Web resource request object.</span></span> <span data-ttu-id="ed08d-111">このオブジェクトに加えた変更はすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="ed08d-111">Any modifications to this object will be ignored.</span></span>
[<span data-ttu-id="ed08d-112">get_Response</span><span class="sxs-lookup"><span data-stu-id="ed08d-112">get_Response</span></span>](#get_response) | <span data-ttu-id="ed08d-113">Web リソース応答オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ed08d-113">Web resource response object.</span></span>
[<span data-ttu-id="ed08d-114">PopulateResponseContent</span><span class="sxs-lookup"><span data-stu-id="ed08d-114">PopulateResponseContent</span></span>](#populateresponsecontent) | <span data-ttu-id="ed08d-115">応答のコンテンツストリームを要求する Async メソッド。</span><span class="sxs-lookup"><span data-stu-id="ed08d-115">Async method to request the Content stream of the response.</span></span>

<span data-ttu-id="ed08d-116">送信された要求と受信した返信が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ed08d-116">Will contain the request as it was sent and the response as it was received.</span></span> <span data-ttu-id="ed08d-117">注: 応答コンテンツストリームを取得するには、最初に PopulateResponseContent を呼び出し、非同期呼び出しが完了するまで待ちます。そうでない場合、返されるコンテンツストリームオブジェクトは null になります。</span><span class="sxs-lookup"><span data-stu-id="ed08d-117">Note: To get the response content stream, first call PopulateResponseContent and wait for the async call to complete, otherwise the content stream object returned will be null.</span></span>

## <span data-ttu-id="ed08d-118">Members</span><span class="sxs-lookup"><span data-stu-id="ed08d-118">Members</span></span>

#### <span data-ttu-id="ed08d-119">get_Request</span><span class="sxs-lookup"><span data-stu-id="ed08d-119">get_Request</span></span> 

<span data-ttu-id="ed08d-120">Web リソース要求オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ed08d-120">Web resource request object.</span></span> <span data-ttu-id="ed08d-121">このオブジェクトに加えた変更はすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="ed08d-121">Any modifications to this object will be ignored.</span></span>

> <span data-ttu-id="ed08d-122">パブリック HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](icorewebview2webresourcerequest.md) \* \* Request)</span><span class="sxs-lookup"><span data-stu-id="ed08d-122">public HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](icorewebview2webresourcerequest.md) \*\* request)</span></span>

#### <span data-ttu-id="ed08d-123">get_Response</span><span class="sxs-lookup"><span data-stu-id="ed08d-123">get_Response</span></span> 

<span data-ttu-id="ed08d-124">Web リソース応答オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ed08d-124">Web resource response object.</span></span>

> <span data-ttu-id="ed08d-125">パブリック HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* \* 応答)</span><span class="sxs-lookup"><span data-stu-id="ed08d-125">public HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \*\* response)</span></span>

<span data-ttu-id="ed08d-126">このオブジェクトに加えた変更はすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="ed08d-126">Any modifications to this object will be ignored.</span></span>

#### <span data-ttu-id="ed08d-127">PopulateResponseContent</span><span class="sxs-lookup"><span data-stu-id="ed08d-127">PopulateResponseContent</span></span> 

<span data-ttu-id="ed08d-128">応答のコンテンツストリームを要求する Async メソッド。</span><span class="sxs-lookup"><span data-stu-id="ed08d-128">Async method to request the Content stream of the response.</span></span>

> <span data-ttu-id="ed08d-129">パブリック HRESULT [PopulateResponseContent](#populateresponsecontent)([ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler](icorewebview2experimentalwebresourceresponsereceivedeventargspopulateresponsecontentcompletedhandler.md) \* handler)</span><span class="sxs-lookup"><span data-stu-id="ed08d-129">public HRESULT [PopulateResponseContent](#populateresponsecontent)([ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler](icorewebview2experimentalwebresourceresponsereceivedeventargspopulateresponsecontentcompletedhandler.md) \* handler)</span></span>

```cpp
                    args->PopulateResponseContent(
                        Callback<
                            ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler>(
                            [this, webResourceRequest, webResourceResponse](HRESULT result) {
                                std::wstring message =
                                    L"{ \"kind\": \"event\", \"name\": "
                                    L"\"WebResourceResponseReceived\", \"args\": {"
                                    L"\"request\": " +
                                    RequestToJsonString(webResourceRequest.get()) +
                                    L", "
                                    L"\"response\": " +
                                    ResponseToJsonString(webResourceResponse.get()) + L"}";

                                message +=
                                    WebViewPropertiesToJsonString(m_webviewEventSource.get());
                                message += L"}";
                                PostEventMessage(message);
                                return S_OK;
                            })
                            .Get());
```

