---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 9b54f9f519c76440d3556bb67f5ab7ad186ba290
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697666"
---
# <span data-ttu-id="dd10f-104">WebView2 クラス (CoreWebView2DevToolsProtocolEventReceiver クラス)</span><span class="sxs-lookup"><span data-stu-id="dd10f-104">Microsoft.Web.WebView2.Core.CoreWebView2DevToolsProtocolEventReceiver class</span></span> 

> [!NOTE]
> <span data-ttu-id="dd10f-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dd10f-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="dd10f-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd10f-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="dd10f-107">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="dd10f-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="dd10f-108">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd10f-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="dd10f-109">特定の DevTools プロトコルイベント用に受信者が作成され、そのイベントのサブスクライブとサブスクライブ解除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="dd10f-109">A Receiver is created for a particular DevTools Protocol event and allows you to subscribe and unsubscribe from that event.</span></span>

## <span data-ttu-id="dd10f-110">まとめ</span><span class="sxs-lookup"><span data-stu-id="dd10f-110">Summary</span></span>

 <span data-ttu-id="dd10f-111">Members</span><span class="sxs-lookup"><span data-stu-id="dd10f-111">Members</span></span>                        | <span data-ttu-id="dd10f-112">説明</span><span class="sxs-lookup"><span data-stu-id="dd10f-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="dd10f-113">DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="dd10f-113">DevToolsProtocolEventReceived</span></span>](#devtoolsprotocoleventreceived) | <span data-ttu-id="dd10f-114">Devツールプロトコルイベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="dd10f-114">Subscribe to a DevToolsProtocol event.</span></span>

<span data-ttu-id="dd10f-115">GetDevToolsProtocolEventReceiver 経由で WebView オブジェクトから取得されます。</span><span class="sxs-lookup"><span data-stu-id="dd10f-115">Obtained from the WebView object via GetDevToolsProtocolEventReceiver.</span></span>

## <span data-ttu-id="dd10f-116">Members</span><span class="sxs-lookup"><span data-stu-id="dd10f-116">Members</span></span>

#### <span data-ttu-id="dd10f-117">DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="dd10f-117">DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="dd10f-118">Devツールプロトコルイベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="dd10f-118">Subscribe to a DevToolsProtocol event.</span></span>

> <span data-ttu-id="dd10f-119">パブリックイベント EventHandler< [CoreWebView2DevToolsProtocolEventReceivedEventArgs](microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md)  >  [DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived)</span><span class="sxs-lookup"><span data-stu-id="dd10f-119">public event EventHandler< [CoreWebView2DevToolsProtocolEventReceivedEventArgs](microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md) > [DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived)</span></span>

<span data-ttu-id="dd10f-120">ハンドラーの Invoke メソッドは、対応する Devて Protocol イベントが発生するたびに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="dd10f-120">The handler's Invoke method will be called whenever the corresponding DevToolsProtocol event fires.</span></span> <span data-ttu-id="dd10f-121">Invoke は、DevTools プロトコルイベントのパラメーターオブジェクトを JSON 文字列として含むイベント引数オブジェクトで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="dd10f-121">Invoke will be called with the an event args object containing the DevTools Protocol event's parameter object as a JSON string.</span></span>

