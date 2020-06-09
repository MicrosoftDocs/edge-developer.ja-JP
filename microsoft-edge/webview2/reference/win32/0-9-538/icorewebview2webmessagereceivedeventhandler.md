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
ms.openlocfilehash: 1d5c015e3ec7a3306c5ae93ed3668b42f5a47aa5
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699040"
---
# <span data-ttu-id="b8218-104">インターフェイス ICoreWebView2WebMessageReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="b8218-104">interface ICoreWebView2WebMessageReceivedEventHandler</span></span> 

```
interface ICoreWebView2WebMessageReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="b8218-105">呼び出し元は、このインターフェイスを実装して WebMessageReceived イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b8218-105">The caller implements this interface to receive the WebMessageReceived event.</span></span>

## <span data-ttu-id="b8218-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="b8218-106">Summary</span></span>

 <span data-ttu-id="b8218-107">Members</span><span class="sxs-lookup"><span data-stu-id="b8218-107">Members</span></span>                        | <span data-ttu-id="b8218-108">説明</span><span class="sxs-lookup"><span data-stu-id="b8218-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b8218-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="b8218-109">Invoke</span></span>](#invoke) | <span data-ttu-id="b8218-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b8218-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="b8218-111">Members</span><span class="sxs-lookup"><span data-stu-id="b8218-111">Members</span></span>

#### <span data-ttu-id="b8218-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="b8218-112">Invoke</span></span> 

<span data-ttu-id="b8218-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b8218-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="b8218-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebMessageReceivedEventArgs](icorewebview2webmessagereceivedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="b8218-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebMessageReceivedEventArgs](icorewebview2webmessagereceivedeventargs.md) \* args)</span></span>

