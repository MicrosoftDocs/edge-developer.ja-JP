---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2DevToolsProtocolEventReceiver
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2DevToolsProtocolEventReceiver。
ms.openlocfilehash: 42ea3beb51dc315ed7ab3b7b0c04c7414adab2db
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012216"
---
# <span data-ttu-id="293e4-104">WebView2 クラス (CoreWebView2DevToolsProtocolEventReceiver クラス)</span><span class="sxs-lookup"><span data-stu-id="293e4-104">Microsoft.Web.WebView2.Core.CoreWebView2DevToolsProtocolEventReceiver class</span></span> 

<span data-ttu-id="293e4-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="293e4-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="293e4-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="293e4-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="293e4-107">特定の DevTools プロトコルイベント用に受信者が作成され、そのイベントのサブスクライブとサブスクライブ解除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="293e4-107">A Receiver is created for a particular DevTools Protocol event and allows you to subscribe and unsubscribe from that event.</span></span>

## <span data-ttu-id="293e4-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="293e4-108">Summary</span></span>

 <span data-ttu-id="293e4-109">Members</span><span class="sxs-lookup"><span data-stu-id="293e4-109">Members</span></span>                        | <span data-ttu-id="293e4-110">説明</span><span class="sxs-lookup"><span data-stu-id="293e4-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="293e4-111">DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="293e4-111">DevToolsProtocolEventReceived</span></span>](#devtoolsprotocoleventreceived) | <span data-ttu-id="293e4-112">Devツールプロトコルイベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="293e4-112">Subscribe to a DevToolsProtocol event.</span></span>

<span data-ttu-id="293e4-113">GetDevToolsProtocolEventReceiver 経由で WebView オブジェクトから取得されます。</span><span class="sxs-lookup"><span data-stu-id="293e4-113">Obtained from the WebView object via GetDevToolsProtocolEventReceiver.</span></span>

## <span data-ttu-id="293e4-114">Members</span><span class="sxs-lookup"><span data-stu-id="293e4-114">Members</span></span>

#### <span data-ttu-id="293e4-115">DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="293e4-115">DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="293e4-116">Devツールプロトコルイベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="293e4-116">Subscribe to a DevToolsProtocol event.</span></span>

> <span data-ttu-id="293e4-117">パブリックイベント EventHandler< [CoreWebView2DevToolsProtocolEventReceivedEventArgs](microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md)  >  [DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived)</span><span class="sxs-lookup"><span data-stu-id="293e4-117">public event EventHandler< [CoreWebView2DevToolsProtocolEventReceivedEventArgs](microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md) > [DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived)</span></span>

<span data-ttu-id="293e4-118">ハンドラーの Invoke メソッドは、対応する Devて Protocol イベントが発生するたびに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="293e4-118">The handler's Invoke method will be called whenever the corresponding DevToolsProtocol event fires.</span></span> <span data-ttu-id="293e4-119">Invoke は、DevTools プロトコルイベントのパラメーターオブジェクトが JSON 文字列として含まれるイベント引数オブジェクトで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="293e4-119">Invoke will be called with an event args object containing the DevTools Protocol event's parameter object as a JSON string.</span></span>

