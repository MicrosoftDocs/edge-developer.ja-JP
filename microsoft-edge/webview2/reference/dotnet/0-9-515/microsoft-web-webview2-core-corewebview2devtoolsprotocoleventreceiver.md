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
ms.openlocfilehash: 23ee363fd90416d07c76644879a5f4b6cc2acabe
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654481"
---
# <span data-ttu-id="87237-104">WebView2 クラス (CoreWebView2DevToolsProtocolEventReceiver クラス)</span><span class="sxs-lookup"><span data-stu-id="87237-104">Microsoft.Web.WebView2.Core.CoreWebView2DevToolsProtocolEventReceiver class</span></span> 

<span data-ttu-id="87237-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="87237-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="87237-106">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="87237-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="87237-107">特定の DevTools プロトコルイベント用に受信者が作成され、そのイベントのサブスクライブとサブスクライブ解除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="87237-107">A Receiver is created for a particular DevTools Protocol event and allows you to subscribe and unsubscribe from that event.</span></span>

## <span data-ttu-id="87237-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="87237-108">Summary</span></span>

 <span data-ttu-id="87237-109">Members</span><span class="sxs-lookup"><span data-stu-id="87237-109">Members</span></span>                        | <span data-ttu-id="87237-110">説明</span><span class="sxs-lookup"><span data-stu-id="87237-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="87237-111">DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="87237-111">DevToolsProtocolEventReceived</span></span>](#devtoolsprotocoleventreceived) | <span data-ttu-id="87237-112">Devツールプロトコルイベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="87237-112">Subscribe to a DevToolsProtocol event.</span></span>

<span data-ttu-id="87237-113">GetDevToolsProtocolEventReceiver 経由で WebView オブジェクトから取得されます。</span><span class="sxs-lookup"><span data-stu-id="87237-113">Obtained from the WebView object via GetDevToolsProtocolEventReceiver.</span></span>

## <span data-ttu-id="87237-114">Members</span><span class="sxs-lookup"><span data-stu-id="87237-114">Members</span></span>

#### <span data-ttu-id="87237-115">DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="87237-115">DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="87237-116">Devツールプロトコルイベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="87237-116">Subscribe to a DevToolsProtocol event.</span></span>

> <span data-ttu-id="87237-117">パブリックイベント EventHandler< [CoreWebView2DevToolsProtocolEventReceivedEventArgs](microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md)  >  [DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived)</span><span class="sxs-lookup"><span data-stu-id="87237-117">public event EventHandler< [CoreWebView2DevToolsProtocolEventReceivedEventArgs](microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md) > [DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived)</span></span>

<span data-ttu-id="87237-118">ハンドラーの Invoke メソッドは、対応する Devて Protocol イベントが発生するたびに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="87237-118">The handler's Invoke method will be called whenever the corresponding DevToolsProtocol event fires.</span></span> <span data-ttu-id="87237-119">Invoke は、DevTools プロトコルイベントのパラメーターオブジェクトを JSON 文字列として含むイベント引数オブジェクトで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="87237-119">Invoke will be called with the an event args object containing the DevTools Protocol event's parameter object as a JSON string.</span></span>

