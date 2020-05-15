---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 9196f2d9503efbaf9f15b43e7e6d7e80c2de00f7
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654422"
---
# <span data-ttu-id="f91fd-104">インターフェイス ICoreWebView2NewBrowserVersionAvailableEventHandler</span><span class="sxs-lookup"><span data-stu-id="f91fd-104">interface ICoreWebView2NewBrowserVersionAvailableEventHandler</span></span> 

```
interface ICoreWebView2NewBrowserVersionAvailableEventHandler
  : public IUnknown
```

<span data-ttu-id="f91fd-105">呼び出し元は、このインターフェイスを実装して、新しい参照サーバーの使用可能なイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f91fd-105">The caller implements this interface to receive NewBrowserVersionAvailable events.</span></span>

## <span data-ttu-id="f91fd-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="f91fd-106">Summary</span></span>

 <span data-ttu-id="f91fd-107">Members</span><span class="sxs-lookup"><span data-stu-id="f91fd-107">Members</span></span>                        | <span data-ttu-id="f91fd-108">説明</span><span class="sxs-lookup"><span data-stu-id="f91fd-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f91fd-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="f91fd-109">Invoke</span></span>](#invoke) | <span data-ttu-id="f91fd-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f91fd-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="f91fd-111">Members</span><span class="sxs-lookup"><span data-stu-id="f91fd-111">Members</span></span>

#### <span data-ttu-id="f91fd-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="f91fd-112">Invoke</span></span> 

<span data-ttu-id="f91fd-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f91fd-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="f91fd-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Environment](icorewebview2environment.md) \* Webviewenvironment、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="f91fd-114">public HRESULT [Invoke](#invoke)([ICoreWebView2Environment](icorewebview2environment.md) \* webviewEnvironment, IUnknown \* args)</span></span>

