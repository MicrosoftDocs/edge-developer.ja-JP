---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2CreateCoreWebView2HostCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 9c2b5568e6a276b07dc91bd639c730b2009aa9e5
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884282"
---
# <span data-ttu-id="6a6e8-104">0.9.430-インターフェイス ICoreWebView2CreateCoreWebView2HostCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="6a6e8-104">0.9.430 - interface ICoreWebView2CreateCoreWebView2HostCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2CreateCoreWebView2HostCompletedHandler
  : public IUnknown
```

<span data-ttu-id="6a6e8-105">呼び出し元はこのインターフェイスを実装して、CreateCoreWebView2Host 経由で作成された CoreWebView2Host を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6a6e8-105">The caller implements this interface to receive the CoreWebView2Host created via CreateCoreWebView2Host.</span></span>

## <span data-ttu-id="6a6e8-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="6a6e8-106">Summary</span></span>

 <span data-ttu-id="6a6e8-107">Members</span><span class="sxs-lookup"><span data-stu-id="6a6e8-107">Members</span></span>                        | <span data-ttu-id="6a6e8-108">説明</span><span class="sxs-lookup"><span data-stu-id="6a6e8-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6a6e8-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="6a6e8-109">Invoke</span></span>](#invoke) | <span data-ttu-id="6a6e8-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6a6e8-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="6a6e8-111">Members</span><span class="sxs-lookup"><span data-stu-id="6a6e8-111">Members</span></span>

#### <span data-ttu-id="6a6e8-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="6a6e8-112">Invoke</span></span> 

<span data-ttu-id="6a6e8-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6a6e8-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="6a6e8-114">パブリック HRESULT[呼び出し](#invoke)(hresult Result、[ICoreWebView2Host](ICoreWebView2Host.md) \* created_host)</span><span class="sxs-lookup"><span data-stu-id="6a6e8-114">public HRESULT [Invoke](#invoke)(HRESULT result,[ICoreWebView2Host](ICoreWebView2Host.md) \* created_host)</span></span>

