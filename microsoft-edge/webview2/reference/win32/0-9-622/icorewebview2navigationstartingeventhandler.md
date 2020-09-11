---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2NavigationStartingEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2NavigationStartingEventHandler
ms.openlocfilehash: ab4181d8a334ae4263665d964448f67cca965ff5
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012341"
---
# <span data-ttu-id="75954-104">インターフェイス ICoreWebView2NavigationStartingEventHandler</span><span class="sxs-lookup"><span data-stu-id="75954-104">interface ICoreWebView2NavigationStartingEventHandler</span></span> 

```
interface ICoreWebView2NavigationStartingEventHandler
  : public IUnknown
```

<span data-ttu-id="75954-105">呼び出し元は、NavigationStarting イベントを受け取るために、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="75954-105">The caller implements this interface to receive the NavigationStarting event.</span></span>

## <span data-ttu-id="75954-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="75954-106">Summary</span></span>

 <span data-ttu-id="75954-107">Members</span><span class="sxs-lookup"><span data-stu-id="75954-107">Members</span></span>                        | <span data-ttu-id="75954-108">説明</span><span class="sxs-lookup"><span data-stu-id="75954-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="75954-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="75954-109">Invoke</span></span>](#invoke) | <span data-ttu-id="75954-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="75954-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="75954-111">Members</span><span class="sxs-lookup"><span data-stu-id="75954-111">Members</span></span>

#### <span data-ttu-id="75954-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="75954-112">Invoke</span></span> 

<span data-ttu-id="75954-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="75954-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="75954-114">パブリック HRESULT [呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationStartingEventArgs](icorewebview2navigationstartingeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="75954-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationStartingEventArgs](icorewebview2navigationstartingeventargs.md) \* args)</span></span>

