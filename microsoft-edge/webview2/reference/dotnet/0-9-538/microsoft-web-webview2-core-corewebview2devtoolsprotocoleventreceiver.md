---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: d99349ec763796bd6b1ea242abbe5c2219c221c2
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698965"
---
# <span data-ttu-id="46373-104">WebView2 クラス (CoreWebView2DevToolsProtocolEventReceiver クラス)</span><span class="sxs-lookup"><span data-stu-id="46373-104">Microsoft.Web.WebView2.Core.CoreWebView2DevToolsProtocolEventReceiver class</span></span> 

<span data-ttu-id="46373-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="46373-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="46373-106">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="46373-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="46373-107">特定の DevTools プロトコルイベント用に受信者が作成され、そのイベントのサブスクライブとサブスクライブ解除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="46373-107">A Receiver is created for a particular DevTools Protocol event and allows you to subscribe and unsubscribe from that event.</span></span>

## <span data-ttu-id="46373-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="46373-108">Summary</span></span>

 <span data-ttu-id="46373-109">Members</span><span class="sxs-lookup"><span data-stu-id="46373-109">Members</span></span>                        | <span data-ttu-id="46373-110">説明</span><span class="sxs-lookup"><span data-stu-id="46373-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="46373-111">DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="46373-111">DevToolsProtocolEventReceived</span></span>](#devtoolsprotocoleventreceived) | <span data-ttu-id="46373-112">Devツールプロトコルイベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="46373-112">Subscribe to a DevToolsProtocol event.</span></span>

<span data-ttu-id="46373-113">GetDevToolsProtocolEventReceiver 経由で WebView オブジェクトから取得されます。</span><span class="sxs-lookup"><span data-stu-id="46373-113">Obtained from the WebView object via GetDevToolsProtocolEventReceiver.</span></span>

## <span data-ttu-id="46373-114">Members</span><span class="sxs-lookup"><span data-stu-id="46373-114">Members</span></span>

#### <span data-ttu-id="46373-115">DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="46373-115">DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="46373-116">Devツールプロトコルイベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="46373-116">Subscribe to a DevToolsProtocol event.</span></span>

> <span data-ttu-id="46373-117">パブリックイベント EventHandler< [CoreWebView2DevToolsProtocolEventReceivedEventArgs](microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md)  >  [DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived)</span><span class="sxs-lookup"><span data-stu-id="46373-117">public event EventHandler< [CoreWebView2DevToolsProtocolEventReceivedEventArgs](microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md) > [DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived)</span></span>

<span data-ttu-id="46373-118">ハンドラーの Invoke メソッドは、対応する Devて Protocol イベントが発生するたびに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="46373-118">The handler's Invoke method will be called whenever the corresponding DevToolsProtocol event fires.</span></span> <span data-ttu-id="46373-119">Invoke は、DevTools プロトコルイベントのパラメーターオブジェクトを JSON 文字列として含むイベント引数オブジェクトで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="46373-119">Invoke will be called with the an event args object containing the DevTools Protocol event's parameter object as a JSON string.</span></span>

