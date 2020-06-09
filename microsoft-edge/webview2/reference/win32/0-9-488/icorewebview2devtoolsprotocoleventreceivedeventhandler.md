---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: a38d451f4ee99e4ab1392f4685a66abf1f274ddb
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698065"
---
# <span data-ttu-id="9197c-104">インターフェイス ICoreWebView2DevToolsProtocolEventReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="9197c-104">interface ICoreWebView2DevToolsProtocolEventReceivedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="9197c-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9197c-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="9197c-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9197c-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="9197c-107">呼び出し元は、このインターフェイスを実装して WebView から DevToolsProtocolEventReceived イベントを受信します。</span><span class="sxs-lookup"><span data-stu-id="9197c-107">The caller implements this interface to receive DevToolsProtocolEventReceived events from the WebView.</span></span>

## <span data-ttu-id="9197c-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="9197c-108">Summary</span></span>

 <span data-ttu-id="9197c-109">Members</span><span class="sxs-lookup"><span data-stu-id="9197c-109">Members</span></span>                        | <span data-ttu-id="9197c-110">説明</span><span class="sxs-lookup"><span data-stu-id="9197c-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9197c-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="9197c-111">Invoke</span></span>](#invoke) | <span data-ttu-id="9197c-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9197c-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="9197c-113">Members</span><span class="sxs-lookup"><span data-stu-id="9197c-113">Members</span></span>

#### <span data-ttu-id="9197c-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="9197c-114">Invoke</span></span> 

<span data-ttu-id="9197c-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9197c-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="9197c-116">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2DevToolsProtocolEventReceivedEventArgs](icorewebview2devtoolsprotocoleventreceivedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="9197c-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2DevToolsProtocolEventReceivedEventArgs](icorewebview2devtoolsprotocoleventreceivedeventargs.md) \* args)</span></span>

