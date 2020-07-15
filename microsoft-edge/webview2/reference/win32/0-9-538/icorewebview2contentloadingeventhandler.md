---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ContentLoadingEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ContentLoadingEventHandler
ms.openlocfilehash: fb6e3cfabae0116ac746d6e8e5cc03efa0f1c1b6
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877448"
---
# <span data-ttu-id="f3b8e-104">インターフェイス ICoreWebView2ContentLoadingEventHandler</span><span class="sxs-lookup"><span data-stu-id="f3b8e-104">interface ICoreWebView2ContentLoadingEventHandler</span></span> 

```
interface ICoreWebView2ContentLoadingEventHandler
  : public IUnknown
```

<span data-ttu-id="f3b8e-105">呼び出し元は、このインターフェイスを実装して ContentLoading イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f3b8e-105">The caller implements this interface to receive the ContentLoading event.</span></span>

## <span data-ttu-id="f3b8e-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="f3b8e-106">Summary</span></span>

 <span data-ttu-id="f3b8e-107">Members</span><span class="sxs-lookup"><span data-stu-id="f3b8e-107">Members</span></span>                        | <span data-ttu-id="f3b8e-108">説明</span><span class="sxs-lookup"><span data-stu-id="f3b8e-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f3b8e-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="f3b8e-109">Invoke</span></span>](#invoke) | <span data-ttu-id="f3b8e-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f3b8e-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="f3b8e-111">Members</span><span class="sxs-lookup"><span data-stu-id="f3b8e-111">Members</span></span>

#### <span data-ttu-id="f3b8e-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="f3b8e-112">Invoke</span></span> 

<span data-ttu-id="f3b8e-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f3b8e-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="f3b8e-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* webview、 [ICoreWebView2ContentLoadingEventArgs](icorewebview2contentloadingeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="f3b8e-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* webview, [ICoreWebView2ContentLoadingEventArgs](icorewebview2contentloadingeventargs.md) \* args)</span></span>

