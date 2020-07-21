---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2WebMessageReceivedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: f566cb8aa876304d17e11bb47f24692aefda3b26
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883757"
---
# <span data-ttu-id="2c251-104">0.9.430-インターフェイス ICoreWebView2WebMessageReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="2c251-104">0.9.430 - interface ICoreWebView2WebMessageReceivedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebMessageReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="2c251-105">呼び出し元は、このインターフェイスを実装して WebMessageReceived イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2c251-105">The caller implements this interface to receive the WebMessageReceived event.</span></span>

## <span data-ttu-id="2c251-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="2c251-106">Summary</span></span>

 <span data-ttu-id="2c251-107">Members</span><span class="sxs-lookup"><span data-stu-id="2c251-107">Members</span></span>                        | <span data-ttu-id="2c251-108">説明</span><span class="sxs-lookup"><span data-stu-id="2c251-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2c251-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="2c251-109">Invoke</span></span>](#invoke) | <span data-ttu-id="2c251-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2c251-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="2c251-111">Members</span><span class="sxs-lookup"><span data-stu-id="2c251-111">Members</span></span>

#### <span data-ttu-id="2c251-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="2c251-112">Invoke</span></span> 

<span data-ttu-id="2c251-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2c251-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="2c251-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2WebMessageReceivedEventArgs](ICoreWebView2WebMessageReceivedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="2c251-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2WebMessageReceivedEventArgs](ICoreWebView2WebMessageReceivedEventArgs.md) \* args)</span></span>

