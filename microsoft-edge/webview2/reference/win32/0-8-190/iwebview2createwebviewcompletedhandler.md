---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2CreateWebViewCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 381f46c6682a77905d9caa720e4ba9b2d1d531b7
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886153"
---
# <span data-ttu-id="9bfd0-104">0.8.355-インターフェイス IWebView2CreateWebViewCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="9bfd0-104">0.8.355 - interface IWebView2CreateWebViewCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2CreateWebViewCompletedHandler
  : public IUnknown
```

<span data-ttu-id="9bfd0-105">呼び出し元は、CreateWebView 経由で作成された WebView を受け取るために、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="9bfd0-105">The caller implements this interface to receive the WebView created via CreateWebView.</span></span>

## <span data-ttu-id="9bfd0-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="9bfd0-106">Summary</span></span>

 <span data-ttu-id="9bfd0-107">Members</span><span class="sxs-lookup"><span data-stu-id="9bfd0-107">Members</span></span>                        | <span data-ttu-id="9bfd0-108">説明</span><span class="sxs-lookup"><span data-stu-id="9bfd0-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9bfd0-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="9bfd0-109">Invoke</span></span>](#invoke) | <span data-ttu-id="9bfd0-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9bfd0-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="9bfd0-111">Members</span><span class="sxs-lookup"><span data-stu-id="9bfd0-111">Members</span></span>

#### <span data-ttu-id="9bfd0-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="9bfd0-112">Invoke</span></span> 

<span data-ttu-id="9bfd0-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9bfd0-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="9bfd0-114">パブリック HRESULT[呼び出し](#invoke)(hresult Result、[IWebView2WebView](IWebView2WebView.md) \* webView)</span><span class="sxs-lookup"><span data-stu-id="9bfd0-114">public HRESULT [Invoke](#invoke)(HRESULT result,[IWebView2WebView](IWebView2WebView.md) \* webView)</span></span>

