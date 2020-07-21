---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2DevToolsProtocolEventReceiver の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 1982c6926d2ed8805433efc4d46ff6f3cac691ce
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885059"
---
# <span data-ttu-id="7ee08-104">0.9.515 クラスの WebView2 クラス (CoreWebView2DevToolsProtocolEventReceiver)</span><span class="sxs-lookup"><span data-stu-id="7ee08-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2DevToolsProtocolEventReceiver class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="7ee08-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="7ee08-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="7ee08-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="7ee08-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="7ee08-107">特定の DevTools プロトコルイベント用に受信者が作成され、そのイベントのサブスクライブとサブスクライブ解除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7ee08-107">A Receiver is created for a particular DevTools Protocol event and allows you to subscribe and unsubscribe from that event.</span></span>

## <span data-ttu-id="7ee08-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="7ee08-108">Summary</span></span>

 <span data-ttu-id="7ee08-109">Members</span><span class="sxs-lookup"><span data-stu-id="7ee08-109">Members</span></span>                        | <span data-ttu-id="7ee08-110">説明</span><span class="sxs-lookup"><span data-stu-id="7ee08-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7ee08-111">DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="7ee08-111">DevToolsProtocolEventReceived</span></span>](#devtoolsprotocoleventreceived) | <span data-ttu-id="7ee08-112">Devツールプロトコルイベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="7ee08-112">Subscribe to a DevToolsProtocol event.</span></span>

<span data-ttu-id="7ee08-113">GetDevToolsProtocolEventReceiver 経由で WebView オブジェクトから取得されます。</span><span class="sxs-lookup"><span data-stu-id="7ee08-113">Obtained from the WebView object via GetDevToolsProtocolEventReceiver.</span></span>

## <span data-ttu-id="7ee08-114">Members</span><span class="sxs-lookup"><span data-stu-id="7ee08-114">Members</span></span>

#### <span data-ttu-id="7ee08-115">DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="7ee08-115">DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="7ee08-116">Devツールプロトコルイベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="7ee08-116">Subscribe to a DevToolsProtocol event.</span></span>

> <span data-ttu-id="7ee08-117">パブリックイベント EventHandler< [CoreWebView2DevToolsProtocolEventReceivedEventArgs](microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md)  >  [DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived)</span><span class="sxs-lookup"><span data-stu-id="7ee08-117">public event EventHandler< [CoreWebView2DevToolsProtocolEventReceivedEventArgs](microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md) > [DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived)</span></span>

<span data-ttu-id="7ee08-118">ハンドラーの Invoke メソッドは、対応する Devて Protocol イベントが発生するたびに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="7ee08-118">The handler's Invoke method will be called whenever the corresponding DevToolsProtocol event fires.</span></span> <span data-ttu-id="7ee08-119">Invoke は、DevTools プロトコルイベントのパラメーターオブジェクトを JSON 文字列として含むイベント引数オブジェクトで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="7ee08-119">Invoke will be called with the an event args object containing the DevTools Protocol event's parameter object as a JSON string.</span></span>

