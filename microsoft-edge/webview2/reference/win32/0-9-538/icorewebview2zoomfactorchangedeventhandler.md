---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2ZoomFactorChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ZoomFactorChangedEventHandler
ms.openlocfilehash: c941629ab8ee87c0c964b00798878bb69265669a
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011392"
---
# <span data-ttu-id="c8b29-104">0.9.579-インターフェイス ICoreWebView2ZoomFactorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="c8b29-104">0.9.579 - interface ICoreWebView2ZoomFactorChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ZoomFactorChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="c8b29-105">呼び出し元は、このインターフェイスを実装して ZoomFactorChanged イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c8b29-105">The caller implements this interface to receive ZoomFactorChanged events.</span></span>

## <span data-ttu-id="c8b29-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="c8b29-106">Summary</span></span>

 <span data-ttu-id="c8b29-107">Members</span><span class="sxs-lookup"><span data-stu-id="c8b29-107">Members</span></span>                        | <span data-ttu-id="c8b29-108">説明</span><span class="sxs-lookup"><span data-stu-id="c8b29-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c8b29-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="c8b29-109">Invoke</span></span>](#invoke) | <span data-ttu-id="c8b29-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c8b29-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="c8b29-111">変更されたズームファクターを取得するには、ICoreWebView2Controller プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="c8b29-111">Use the ICoreWebView2Controller.ZoomFactor property to get the modified zoom factor.</span></span>

## <span data-ttu-id="c8b29-112">Members</span><span class="sxs-lookup"><span data-stu-id="c8b29-112">Members</span></span>

#### <span data-ttu-id="c8b29-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="c8b29-113">Invoke</span></span> 

<span data-ttu-id="c8b29-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c8b29-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="c8b29-115">パブリック HRESULT [呼び出し](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="c8b29-115">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="c8b29-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="c8b29-116">There are no event args and the args parameter will be null.</span></span>

