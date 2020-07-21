---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler
ms.openlocfilehash: c021cfa866e55bfdf30185eeaf6015db1b523271
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886542"
---
# <span data-ttu-id="97b88-104">インターフェイス ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="97b88-104">interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler
  : public IUnknown
```

<span data-ttu-id="97b88-105">PopulateResponseContent async メソッドの完了ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="97b88-105">Completion handler for PopulateResponseContent async method.</span></span>

## <span data-ttu-id="97b88-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="97b88-106">Summary</span></span>

 <span data-ttu-id="97b88-107">Members</span><span class="sxs-lookup"><span data-stu-id="97b88-107">Members</span></span>                        | <span data-ttu-id="97b88-108">説明</span><span class="sxs-lookup"><span data-stu-id="97b88-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="97b88-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="97b88-109">Invoke</span></span>](#invoke) | <span data-ttu-id="97b88-110">対応する非同期メソッド呼び出しの完了状態を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="97b88-110">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

<span data-ttu-id="97b88-111">WebResourceResponseReceieved イベントの応答のコンテンツストリームを利用できる場合に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="97b88-111">It's invoked when the Content stream of the Response of a WebResourceResponseReceieved event is available.</span></span>

## <span data-ttu-id="97b88-112">Members</span><span class="sxs-lookup"><span data-stu-id="97b88-112">Members</span></span>

#### <span data-ttu-id="97b88-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="97b88-113">Invoke</span></span> 

<span data-ttu-id="97b88-114">対応する非同期メソッド呼び出しの完了状態を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="97b88-114">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="97b88-115">パブリック HRESULT[呼び出し](#invoke)(hresult 結果)</span><span class="sxs-lookup"><span data-stu-id="97b88-115">public HRESULT [Invoke](#invoke)(HRESULT result)</span></span>

