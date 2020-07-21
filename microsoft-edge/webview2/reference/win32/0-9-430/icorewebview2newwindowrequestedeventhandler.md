---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2NewWindowRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 606b9f87dfbce1f4c9a899ad6f78ec8c52794682
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886393"
---
# <span data-ttu-id="abc0f-104">0.9.430-インターフェイス ICoreWebView2NewWindowRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="abc0f-104">0.9.430 - interface ICoreWebView2NewWindowRequestedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2NewWindowRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="abc0f-105">呼び出し元は、このインターフェイスを実装して、NewWindowRequested されたイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="abc0f-105">The caller implements this interface to receive NewWindowRequested events.</span></span>

## <span data-ttu-id="abc0f-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="abc0f-106">Summary</span></span>

 <span data-ttu-id="abc0f-107">Members</span><span class="sxs-lookup"><span data-stu-id="abc0f-107">Members</span></span>                        | <span data-ttu-id="abc0f-108">説明</span><span class="sxs-lookup"><span data-stu-id="abc0f-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="abc0f-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="abc0f-109">Invoke</span></span>](#invoke) | <span data-ttu-id="abc0f-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="abc0f-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="abc0f-111">Members</span><span class="sxs-lookup"><span data-stu-id="abc0f-111">Members</span></span>

#### <span data-ttu-id="abc0f-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="abc0f-112">Invoke</span></span> 

<span data-ttu-id="abc0f-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="abc0f-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="abc0f-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2NewWindowRequestedEventArgs](ICoreWebView2NewWindowRequestedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="abc0f-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2NewWindowRequestedEventArgs](ICoreWebView2NewWindowRequestedEventArgs.md) \* args)</span></span>

