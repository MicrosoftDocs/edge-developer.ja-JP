---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2DevToolsProtocolEventReceiver
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 8b29e3a4262afc708608de20d81e3463718a50c2
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884226"
---
# <span data-ttu-id="c8e8d-104">0.9.430-インターフェイス ICoreWebView2DevToolsProtocolEventReceiver</span><span class="sxs-lookup"><span data-stu-id="c8e8d-104">0.9.430 - interface ICoreWebView2DevToolsProtocolEventReceiver</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2DevToolsProtocolEventReceiver
  : public IUnknown
```

<span data-ttu-id="c8e8d-105">特定の DevTools プロトコルイベント用に受信者が作成され、そのイベントからの登録と解除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c8e8d-105">A Receiver is created for a particular DevTools Protocol event and allows you to subscribe and unsubsribe from that event.</span></span>

## <span data-ttu-id="c8e8d-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="c8e8d-106">Summary</span></span>

 <span data-ttu-id="c8e8d-107">Members</span><span class="sxs-lookup"><span data-stu-id="c8e8d-107">Members</span></span>                        | <span data-ttu-id="c8e8d-108">説明</span><span class="sxs-lookup"><span data-stu-id="c8e8d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c8e8d-109">add_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="c8e8d-109">add_DevToolsProtocolEventReceived</span></span>](#add_devtoolsprotocoleventreceived) | <span data-ttu-id="c8e8d-110">Devツールプロトコルイベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="c8e8d-110">Subscribe to a DevToolsProtocol event.</span></span>
[<span data-ttu-id="c8e8d-111">remove_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="c8e8d-111">remove_DevToolsProtocolEventReceived</span></span>](#remove_devtoolsprotocoleventreceived) | <span data-ttu-id="c8e8d-112">Add_DevToolsProtocolEventReceived で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c8e8d-112">Remove an event handler previously added with add_DevToolsProtocolEventReceived.</span></span>

<span data-ttu-id="c8e8d-113">GetDevToolsProtocolEventReceiver 経由で WebView オブジェクトから取得されます。</span><span class="sxs-lookup"><span data-stu-id="c8e8d-113">Obtained from the WebView object via GetDevToolsProtocolEventReceiver.</span></span>

## <span data-ttu-id="c8e8d-114">Members</span><span class="sxs-lookup"><span data-stu-id="c8e8d-114">Members</span></span>

#### <span data-ttu-id="c8e8d-115">add_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="c8e8d-115">add_DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="c8e8d-116">Devツールプロトコルイベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="c8e8d-116">Subscribe to a DevToolsProtocol event.</span></span>

> <span data-ttu-id="c8e8d-117">パブリック HRESULT [add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived)([ICoreWebView2DevToolsProtocolEventReceivedEventHandler](ICoreWebView2DevToolsProtocolEventReceivedEventHandler.md) \* handler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="c8e8d-117">public HRESULT [add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived)([ICoreWebView2DevToolsProtocolEventReceivedEventHandler](ICoreWebView2DevToolsProtocolEventReceivedEventHandler.md) \* handler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="c8e8d-118">ハンドラーの Invoke メソッドは、対応する Devて Protocol イベントが発生するたびに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c8e8d-118">The handler's Invoke method will be called whenever the corresponding DevToolsProtocol event fires.</span></span> <span data-ttu-id="c8e8d-119">Invoke は、DevTools プロトコルイベントのパラメーターオブジェクトを JSON 文字列として含むイベント引数オブジェクトで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c8e8d-119">Invoke will be called with the an event args object containing the DevTools Protocol event's parameter object as a JSON string.</span></span>

```cpp
// Prompt the user to name a CDP event, and then subscribe to that event.
void ScriptComponent::SubscribeToCdpEvent()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Subscribe to CDP Event",
        L"CDP event name:",
        L"Enter the name of the CDP event to subscribe to.\r\n"
            L"You may also have to call the \"enable\" method of the\r\n"
            L"event's domain to receive events (for example \"Log.enable\").\r\n",
        L"Log.entryAdded");
    if (dialog.confirmed)
    {
        std::wstring eventName = dialog.input;
        wil::com_ptr<ICoreWebView2DevToolsProtocolEventReceiver> receiver;
        CHECK_FAILURE(
            m_webView->GetDevToolsProtocolEventReceiver(eventName.c_str(), &receiver));

        // If we are already subscribed to this event, unsubscribe first.
        auto preexistingToken = m_devToolsProtocolEventReceivedTokenMap.find(eventName);
        if (preexistingToken != m_devToolsProtocolEventReceivedTokenMap.end())
        {
            CHECK_FAILURE(receiver->remove_DevToolsProtocolEventReceived(
                preexistingToken->second));
        }

        CHECK_FAILURE(receiver->add_DevToolsProtocolEventReceived(
            Callback<ICoreWebView2DevToolsProtocolEventReceivedEventHandler>(
                [eventName](
                    ICoreWebView2* sender,
                    ICoreWebView2DevToolsProtocolEventReceivedEventArgs* args) -> HRESULT {
                    wil::unique_cotaskmem_string parameterObjectAsJson;
                    CHECK_FAILURE(args->get_ParameterObjectAsJson(&parameterObjectAsJson));
                    MessageBox(
                        nullptr, parameterObjectAsJson.get(),
                        (L"CDP Event Fired: " + eventName).c_str(), MB_OK);
                    return S_OK;
                })
                .Get(),
            &m_devToolsProtocolEventReceivedTokenMap[eventName]));
    }
}
```

#### <span data-ttu-id="c8e8d-120">remove_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="c8e8d-120">remove_DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="c8e8d-121">Add_DevToolsProtocolEventReceived で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c8e8d-121">Remove an event handler previously added with add_DevToolsProtocolEventReceived.</span></span>

> <span data-ttu-id="c8e8d-122">パブリック HRESULT [remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="c8e8d-122">public HRESULT [remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived)(EventRegistrationToken token)</span></span>

