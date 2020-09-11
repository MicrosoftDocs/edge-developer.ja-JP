---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2WebMessageReceivedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2WebMessageReceivedEventHandler
ms.openlocfilehash: 3d88ffc5e7821ef3163c357738019ecb914ea758
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012367"
---
# <span data-ttu-id="ad8d4-104">インターフェイス ICoreWebView2WebMessageReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="ad8d4-104">interface ICoreWebView2WebMessageReceivedEventHandler</span></span> 

```
interface ICoreWebView2WebMessageReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="ad8d4-105">呼び出し元は、このインターフェイスを実装して WebMessageReceived イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ad8d4-105">The caller implements this interface to receive the WebMessageReceived event.</span></span>

## <span data-ttu-id="ad8d4-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="ad8d4-106">Summary</span></span>

 <span data-ttu-id="ad8d4-107">Members</span><span class="sxs-lookup"><span data-stu-id="ad8d4-107">Members</span></span>                        | <span data-ttu-id="ad8d4-108">説明</span><span class="sxs-lookup"><span data-stu-id="ad8d4-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ad8d4-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="ad8d4-109">Invoke</span></span>](#invoke) | <span data-ttu-id="ad8d4-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ad8d4-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="ad8d4-111">Members</span><span class="sxs-lookup"><span data-stu-id="ad8d4-111">Members</span></span>

#### <span data-ttu-id="ad8d4-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="ad8d4-112">Invoke</span></span> 

<span data-ttu-id="ad8d4-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ad8d4-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="ad8d4-114">パブリック HRESULT [呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebMessageReceivedEventArgs](icorewebview2webmessagereceivedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="ad8d4-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebMessageReceivedEventArgs](icorewebview2webmessagereceivedeventargs.md) \* args)</span></span>

