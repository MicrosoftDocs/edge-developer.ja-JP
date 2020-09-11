---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2NewBrowserVersionAvailableEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2NewBrowserVersionAvailableEventHandler
ms.openlocfilehash: 7cadbfddca9c05c8649b79503de3ce4f3695ea4c
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011273"
---
# <span data-ttu-id="68b5c-104">0.9.579-インターフェイス ICoreWebView2NewBrowserVersionAvailableEventHandler</span><span class="sxs-lookup"><span data-stu-id="68b5c-104">0.9.579 - interface ICoreWebView2NewBrowserVersionAvailableEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2NewBrowserVersionAvailableEventHandler
  : public IUnknown
```

<span data-ttu-id="68b5c-105">呼び出し元は、このインターフェイスを実装して、新しい参照サーバーの使用可能なイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="68b5c-105">The caller implements this interface to receive NewBrowserVersionAvailable events.</span></span>

## <span data-ttu-id="68b5c-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="68b5c-106">Summary</span></span>

 <span data-ttu-id="68b5c-107">Members</span><span class="sxs-lookup"><span data-stu-id="68b5c-107">Members</span></span>                        | <span data-ttu-id="68b5c-108">説明</span><span class="sxs-lookup"><span data-stu-id="68b5c-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="68b5c-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="68b5c-109">Invoke</span></span>](#invoke) | <span data-ttu-id="68b5c-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="68b5c-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="68b5c-111">Members</span><span class="sxs-lookup"><span data-stu-id="68b5c-111">Members</span></span>

#### <span data-ttu-id="68b5c-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="68b5c-112">Invoke</span></span> 

<span data-ttu-id="68b5c-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="68b5c-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="68b5c-114">パブリック HRESULT [呼び出し](#invoke)([ICoreWebView2Environment](icorewebview2environment.md) \* Webviewenvironment、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="68b5c-114">public HRESULT [Invoke](#invoke)([ICoreWebView2Environment](icorewebview2environment.md) \* webviewEnvironment, IUnknown \* args)</span></span>

