---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: f0b90cec451a80225f657386fa06b8740d6e1385
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699068"
---
# <span data-ttu-id="a2b61-104">インターフェイス ICoreWebView2ZoomFactorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="a2b61-104">interface ICoreWebView2ZoomFactorChangedEventHandler</span></span> 

```
interface ICoreWebView2ZoomFactorChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="a2b61-105">呼び出し元は、このインターフェイスを実装して ZoomFactorChanged イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a2b61-105">The caller implements this interface to receive ZoomFactorChanged events.</span></span>

## <span data-ttu-id="a2b61-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="a2b61-106">Summary</span></span>

 <span data-ttu-id="a2b61-107">Members</span><span class="sxs-lookup"><span data-stu-id="a2b61-107">Members</span></span>                        | <span data-ttu-id="a2b61-108">説明</span><span class="sxs-lookup"><span data-stu-id="a2b61-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a2b61-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="a2b61-109">Invoke</span></span>](#invoke) | <span data-ttu-id="a2b61-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a2b61-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="a2b61-111">変更されたズームファクターを取得するには、ICoreWebView2Controller プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="a2b61-111">Use the ICoreWebView2Controller.ZoomFactor property to get the modified zoom factor.</span></span>

## <span data-ttu-id="a2b61-112">Members</span><span class="sxs-lookup"><span data-stu-id="a2b61-112">Members</span></span>

#### <span data-ttu-id="a2b61-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="a2b61-113">Invoke</span></span> 

<span data-ttu-id="a2b61-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a2b61-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="a2b61-115">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="a2b61-115">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="a2b61-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="a2b61-116">There are no event args and the args parameter will be null.</span></span>

