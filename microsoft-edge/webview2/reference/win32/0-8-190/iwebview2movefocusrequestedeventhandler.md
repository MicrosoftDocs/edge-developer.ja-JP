---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: e24db15aba667f1002c95ed84ead63d812284586
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654182"
---
# <span data-ttu-id="2d4d9-104">インターフェイス IWebView2MoveFocusRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="2d4d9-104">interface IWebView2MoveFocusRequestedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="2d4d9-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d4d9-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="2d4d9-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d4d9-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2MoveFocusRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="2d4d9-107">呼び出し元は、このメソッドを実装して MoveFocusRequested イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2d4d9-107">The caller implements this method to receive the MoveFocusRequested event.</span></span>

## <span data-ttu-id="2d4d9-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="2d4d9-108">Summary</span></span>

 <span data-ttu-id="2d4d9-109">Members</span><span class="sxs-lookup"><span data-stu-id="2d4d9-109">Members</span></span>                        | <span data-ttu-id="2d4d9-110">説明</span><span class="sxs-lookup"><span data-stu-id="2d4d9-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2d4d9-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="2d4d9-111">Invoke</span></span>](#invoke) | <span data-ttu-id="2d4d9-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2d4d9-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="2d4d9-113">Members</span><span class="sxs-lookup"><span data-stu-id="2d4d9-113">Members</span></span>

#### <span data-ttu-id="2d4d9-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="2d4d9-114">Invoke</span></span> 

<span data-ttu-id="2d4d9-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2d4d9-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="2d4d9-116">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview、[IWebView2MoveFocusRequestedEventArgs](IWebView2MoveFocusRequestedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="2d4d9-116">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2MoveFocusRequestedEventArgs](IWebView2MoveFocusRequestedEventArgs.md) \* args)</span></span>

