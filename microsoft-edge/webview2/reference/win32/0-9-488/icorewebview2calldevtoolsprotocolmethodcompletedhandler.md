---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2CallDevToolsProtocolMethodCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 7a983d313e242cc163fb16a9c0d0068a9d6663d9
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883932"
---
# <span data-ttu-id="cc7c2-104">0.9.515-インターフェイス ICoreWebView2CallDevToolsProtocolMethodCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="cc7c2-104">0.9.515 - interface ICoreWebView2CallDevToolsProtocolMethodCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2CallDevToolsProtocolMethodCompletedHandler
  : public IUnknown
```

<span data-ttu-id="cc7c2-105">呼び出し元はこのインターフェイスを実装して、Calldevcompletion Protocolメソッドの完了結果を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="cc7c2-105">The caller implements this interface to receive CallDevToolsProtocolMethod completion results.</span></span>

## <span data-ttu-id="cc7c2-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="cc7c2-106">Summary</span></span>

 <span data-ttu-id="cc7c2-107">Members</span><span class="sxs-lookup"><span data-stu-id="cc7c2-107">Members</span></span>                        | <span data-ttu-id="cc7c2-108">説明</span><span class="sxs-lookup"><span data-stu-id="cc7c2-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="cc7c2-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="cc7c2-109">Invoke</span></span>](#invoke) | <span data-ttu-id="cc7c2-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cc7c2-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="cc7c2-111">Members</span><span class="sxs-lookup"><span data-stu-id="cc7c2-111">Members</span></span>

#### <span data-ttu-id="cc7c2-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="cc7c2-112">Invoke</span></span> 

<span data-ttu-id="cc7c2-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cc7c2-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="cc7c2-114">パブリック HRESULT[呼び出し](#invoke)(hresult ERRORCODE、LPCWSTR returnObjectAsJson)</span><span class="sxs-lookup"><span data-stu-id="cc7c2-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode, LPCWSTR returnObjectAsJson)</span></span>

