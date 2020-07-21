---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2WebMessageReceivedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 772ad4ce7bd1ae0c1f02475206380c146ecabf7b
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885745"
---
# <span data-ttu-id="f01b0-104">0.8.355-インターフェイス IWebView2WebMessageReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="f01b0-104">0.8.355 - interface IWebView2WebMessageReceivedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2WebMessageReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="f01b0-105">呼び出し元は、このインターフェイスを実装して WebMessageReceived イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f01b0-105">The caller implements this interface to receive the WebMessageReceived event.</span></span>

## <span data-ttu-id="f01b0-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="f01b0-106">Summary</span></span>

 <span data-ttu-id="f01b0-107">Members</span><span class="sxs-lookup"><span data-stu-id="f01b0-107">Members</span></span>                        | <span data-ttu-id="f01b0-108">説明</span><span class="sxs-lookup"><span data-stu-id="f01b0-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f01b0-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="f01b0-109">Invoke</span></span>](#invoke) | <span data-ttu-id="f01b0-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f01b0-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="f01b0-111">Members</span><span class="sxs-lookup"><span data-stu-id="f01b0-111">Members</span></span>

#### <span data-ttu-id="f01b0-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="f01b0-112">Invoke</span></span> 

<span data-ttu-id="f01b0-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f01b0-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="f01b0-114">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview、[IWebView2WebMessageReceivedEventArgs](IWebView2WebMessageReceivedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="f01b0-114">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2WebMessageReceivedEventArgs](IWebView2WebMessageReceivedEventArgs.md) \* args)</span></span>

