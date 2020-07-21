---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2ZoomFactorChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 91cd4245ff6c75e72457410211deefd9ab7f09d1
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883694"
---
# <span data-ttu-id="66633-104">0.9.515-インターフェイス ICoreWebView2ZoomFactorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="66633-104">0.9.515 - interface ICoreWebView2ZoomFactorChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ZoomFactorChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="66633-105">呼び出し元は、このインターフェイスを実装して ZoomFactorChanged イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="66633-105">The caller implements this interface to receive ZoomFactorChanged events.</span></span>

## <span data-ttu-id="66633-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="66633-106">Summary</span></span>

 <span data-ttu-id="66633-107">Members</span><span class="sxs-lookup"><span data-stu-id="66633-107">Members</span></span>                        | <span data-ttu-id="66633-108">説明</span><span class="sxs-lookup"><span data-stu-id="66633-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="66633-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="66633-109">Invoke</span></span>](#invoke) | <span data-ttu-id="66633-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="66633-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="66633-111">変更されたズームファクターを取得するには、ICoreWebView2Controller プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="66633-111">Use the ICoreWebView2Controller.ZoomFactor property to get the modified zoom factor.</span></span>

## <span data-ttu-id="66633-112">Members</span><span class="sxs-lookup"><span data-stu-id="66633-112">Members</span></span>

#### <span data-ttu-id="66633-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="66633-113">Invoke</span></span> 

<span data-ttu-id="66633-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="66633-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="66633-115">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="66633-115">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="66633-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="66633-116">There are no event args and the args parameter will be null.</span></span>

