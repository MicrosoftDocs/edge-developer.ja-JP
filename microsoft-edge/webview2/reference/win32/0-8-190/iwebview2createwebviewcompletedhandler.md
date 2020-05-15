---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 2788a18898da1f878520f4c4eb072c1a8b43375b
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654181"
---
# <span data-ttu-id="01c47-104">インターフェイス IWebView2CreateWebViewCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="01c47-104">interface IWebView2CreateWebViewCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="01c47-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="01c47-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="01c47-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01c47-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2CreateWebViewCompletedHandler
  : public IUnknown
```

<span data-ttu-id="01c47-107">呼び出し元は、CreateWebView 経由で作成された WebView を受け取るために、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="01c47-107">The caller implements this interface to receive the WebView created via CreateWebView.</span></span>

## <span data-ttu-id="01c47-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="01c47-108">Summary</span></span>

 <span data-ttu-id="01c47-109">Members</span><span class="sxs-lookup"><span data-stu-id="01c47-109">Members</span></span>                        | <span data-ttu-id="01c47-110">説明</span><span class="sxs-lookup"><span data-stu-id="01c47-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="01c47-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="01c47-111">Invoke</span></span>](#invoke) | <span data-ttu-id="01c47-112">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="01c47-112">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="01c47-113">Members</span><span class="sxs-lookup"><span data-stu-id="01c47-113">Members</span></span>

#### <span data-ttu-id="01c47-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="01c47-114">Invoke</span></span> 

<span data-ttu-id="01c47-115">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="01c47-115">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="01c47-116">パブリック HRESULT[呼び出し](#invoke)(hresult Result、[IWebView2WebView](IWebView2WebView.md) \* webView)</span><span class="sxs-lookup"><span data-stu-id="01c47-116">public HRESULT [Invoke](#invoke)(HRESULT result,[IWebView2WebView](IWebView2WebView.md) \* webView)</span></span>

