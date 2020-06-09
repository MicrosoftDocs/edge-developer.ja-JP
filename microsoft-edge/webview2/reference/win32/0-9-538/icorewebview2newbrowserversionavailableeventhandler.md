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
ms.openlocfilehash: c8444741480ba3b07d2755dcac0ec11f7194a783
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699109"
---
# <span data-ttu-id="58361-104">インターフェイス ICoreWebView2NewBrowserVersionAvailableEventHandler</span><span class="sxs-lookup"><span data-stu-id="58361-104">interface ICoreWebView2NewBrowserVersionAvailableEventHandler</span></span> 

```
interface ICoreWebView2NewBrowserVersionAvailableEventHandler
  : public IUnknown
```

<span data-ttu-id="58361-105">呼び出し元は、このインターフェイスを実装して、新しい参照サーバーの使用可能なイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="58361-105">The caller implements this interface to receive NewBrowserVersionAvailable events.</span></span>

## <span data-ttu-id="58361-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="58361-106">Summary</span></span>

 <span data-ttu-id="58361-107">Members</span><span class="sxs-lookup"><span data-stu-id="58361-107">Members</span></span>                        | <span data-ttu-id="58361-108">説明</span><span class="sxs-lookup"><span data-stu-id="58361-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="58361-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="58361-109">Invoke</span></span>](#invoke) | <span data-ttu-id="58361-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="58361-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="58361-111">Members</span><span class="sxs-lookup"><span data-stu-id="58361-111">Members</span></span>

#### <span data-ttu-id="58361-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="58361-112">Invoke</span></span> 

<span data-ttu-id="58361-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="58361-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="58361-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Environment](icorewebview2environment.md) \* Webviewenvironment、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="58361-114">public HRESULT [Invoke](#invoke)([ICoreWebView2Environment](icorewebview2environment.md) \* webviewEnvironment, IUnknown \* args)</span></span>

