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
ms.openlocfilehash: a39eeadaf1243d57223f3739dce836b1db998998
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698945"
---
# <span data-ttu-id="32a2b-104">インターフェイス ICoreWebView2NewWindowRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="32a2b-104">interface ICoreWebView2NewWindowRequestedEventHandler</span></span> 

```
interface ICoreWebView2NewWindowRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="32a2b-105">呼び出し元は、このインターフェイスを実装して、NewWindowRequested されたイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="32a2b-105">The caller implements this interface to receive NewWindowRequested events.</span></span>

## <span data-ttu-id="32a2b-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="32a2b-106">Summary</span></span>

 <span data-ttu-id="32a2b-107">Members</span><span class="sxs-lookup"><span data-stu-id="32a2b-107">Members</span></span>                        | <span data-ttu-id="32a2b-108">説明</span><span class="sxs-lookup"><span data-stu-id="32a2b-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="32a2b-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="32a2b-109">Invoke</span></span>](#invoke) | <span data-ttu-id="32a2b-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="32a2b-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="32a2b-111">Members</span><span class="sxs-lookup"><span data-stu-id="32a2b-111">Members</span></span>

#### <span data-ttu-id="32a2b-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="32a2b-112">Invoke</span></span> 

<span data-ttu-id="32a2b-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="32a2b-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="32a2b-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NewWindowRequestedEventArgs](icorewebview2newwindowrequestedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="32a2b-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NewWindowRequestedEventArgs](icorewebview2newwindowrequestedeventargs.md) \* args)</span></span>
