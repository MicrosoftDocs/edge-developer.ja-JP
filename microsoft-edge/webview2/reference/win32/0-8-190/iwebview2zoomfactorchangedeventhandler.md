---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2ZoomFactorChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 237179df5ef704fb88516780696f3a9c10c9a198
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884667"
---
# <span data-ttu-id="4d1ab-104">0.8.355-インターフェイス IWebView2ZoomFactorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="4d1ab-104">0.8.355 - interface IWebView2ZoomFactorChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2ZoomFactorChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="4d1ab-105">呼び出し元は、このインターフェイスを実装して ZoomFactorChanged イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-105">The caller implements this interface to receive ZoomFactorChanged events.</span></span>

## <span data-ttu-id="4d1ab-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="4d1ab-106">Summary</span></span>

 <span data-ttu-id="4d1ab-107">Members</span><span class="sxs-lookup"><span data-stu-id="4d1ab-107">Members</span></span>                        | <span data-ttu-id="4d1ab-108">説明</span><span class="sxs-lookup"><span data-stu-id="4d1ab-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4d1ab-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="4d1ab-109">Invoke</span></span>](#invoke) | <span data-ttu-id="4d1ab-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="4d1ab-111">変更されたズームファクターを取得するには、IWebView2WebView プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-111">Use the IWebView2WebView.ZoomFactor property to get the modified zoom factor.</span></span>

## <span data-ttu-id="4d1ab-112">Members</span><span class="sxs-lookup"><span data-stu-id="4d1ab-112">Members</span></span>

#### <span data-ttu-id="4d1ab-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="4d1ab-113">Invoke</span></span> 

<span data-ttu-id="4d1ab-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="4d1ab-115">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="4d1ab-115">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,IUnknown \* args)</span></span>

<span data-ttu-id="4d1ab-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="4d1ab-116">There are no event args and the args parameter will be null.</span></span>

