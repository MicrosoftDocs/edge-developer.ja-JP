---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2WindowCloseRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2WindowCloseRequestedEventHandler
ms.openlocfilehash: fcfdb3b28f4f1d1e1d1159e6664cb898613d0601
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879962"
---
# <span data-ttu-id="08bdf-104">インターフェイス ICoreWebView2WindowCloseRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="08bdf-104">interface ICoreWebView2WindowCloseRequestedEventHandler</span></span> 

```
interface ICoreWebView2WindowCloseRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="08bdf-105">呼び出し元は、このインターフェイスを実装して、NewWindowRequested されたイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="08bdf-105">The caller implements this interface to receive NewWindowRequested events.</span></span>

## <span data-ttu-id="08bdf-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="08bdf-106">Summary</span></span>

 <span data-ttu-id="08bdf-107">Members</span><span class="sxs-lookup"><span data-stu-id="08bdf-107">Members</span></span>                        | <span data-ttu-id="08bdf-108">説明</span><span class="sxs-lookup"><span data-stu-id="08bdf-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="08bdf-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="08bdf-109">Invoke</span></span>](#invoke) | <span data-ttu-id="08bdf-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="08bdf-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="08bdf-111">Members</span><span class="sxs-lookup"><span data-stu-id="08bdf-111">Members</span></span>

#### <span data-ttu-id="08bdf-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="08bdf-112">Invoke</span></span> 

<span data-ttu-id="08bdf-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="08bdf-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="08bdf-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="08bdf-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="08bdf-115">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="08bdf-115">There are no event args and the args parameter will be null.</span></span>

