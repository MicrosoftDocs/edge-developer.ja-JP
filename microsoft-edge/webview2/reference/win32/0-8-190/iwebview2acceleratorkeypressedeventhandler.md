---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2AcceleratorKeyPressedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 6b5cf77e8091d79b582907b4cbfe7c9aa415de9c
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879066"
---
# <span data-ttu-id="1d672-104">0.8.355-インターフェイス IWebView2AcceleratorKeyPressedEventHandler</span><span class="sxs-lookup"><span data-stu-id="1d672-104">0.8.355 - interface IWebView2AcceleratorKeyPressedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="1d672-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1d672-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="1d672-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d672-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2AcceleratorKeyPressedEventHandler
  : public IUnknown
```

<span data-ttu-id="1d672-107">呼び出し元は、このインターフェイスを実装して AcceleratorKeyPressed イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1d672-107">The caller implements this interface to receive the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="1d672-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="1d672-108">Summary</span></span>

 <span data-ttu-id="1d672-109">Members</span><span class="sxs-lookup"><span data-stu-id="1d672-109">Members</span></span>                        | <span data-ttu-id="1d672-110">説明</span><span class="sxs-lookup"><span data-stu-id="1d672-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="1d672-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="1d672-111">Invoke</span></span>](#invoke) | <span data-ttu-id="1d672-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1d672-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="1d672-113">Members</span><span class="sxs-lookup"><span data-stu-id="1d672-113">Members</span></span>

#### <span data-ttu-id="1d672-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="1d672-114">Invoke</span></span> 

<span data-ttu-id="1d672-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1d672-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="1d672-116">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview、[IWebView2AcceleratorKeyPressedEventArgs](IWebView2AcceleratorKeyPressedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="1d672-116">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2AcceleratorKeyPressedEventArgs](IWebView2AcceleratorKeyPressedEventArgs.md) \* args)</span></span>

