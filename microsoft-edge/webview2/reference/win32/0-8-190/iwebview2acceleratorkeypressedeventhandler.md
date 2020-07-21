---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2AcceleratorKeyPressedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 7d510a547e43a4f04ef517c393ceeb3040d914e7
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885032"
---
# <span data-ttu-id="3e7f8-104">0.8.355-インターフェイス IWebView2AcceleratorKeyPressedEventHandler</span><span class="sxs-lookup"><span data-stu-id="3e7f8-104">0.8.355 - interface IWebView2AcceleratorKeyPressedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2AcceleratorKeyPressedEventHandler
  : public IUnknown
```

<span data-ttu-id="3e7f8-105">呼び出し元は、このインターフェイスを実装して AcceleratorKeyPressed イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3e7f8-105">The caller implements this interface to receive the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="3e7f8-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="3e7f8-106">Summary</span></span>

 <span data-ttu-id="3e7f8-107">Members</span><span class="sxs-lookup"><span data-stu-id="3e7f8-107">Members</span></span>                        | <span data-ttu-id="3e7f8-108">説明</span><span class="sxs-lookup"><span data-stu-id="3e7f8-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3e7f8-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="3e7f8-109">Invoke</span></span>](#invoke) | <span data-ttu-id="3e7f8-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3e7f8-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="3e7f8-111">Members</span><span class="sxs-lookup"><span data-stu-id="3e7f8-111">Members</span></span>

#### <span data-ttu-id="3e7f8-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="3e7f8-112">Invoke</span></span> 

<span data-ttu-id="3e7f8-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3e7f8-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="3e7f8-114">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview、[IWebView2AcceleratorKeyPressedEventArgs](IWebView2AcceleratorKeyPressedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="3e7f8-114">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2AcceleratorKeyPressedEventArgs](IWebView2AcceleratorKeyPressedEventArgs.md) \* args)</span></span>

