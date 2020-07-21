---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: f2598d40afc7c7def1c3fec634016f1a64905479
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885668"
---
# <span data-ttu-id="b7137-104">0.9.515-インターフェイス ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="b7137-104">0.9.515 - interface ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
  : public IUnknown
```

<span data-ttu-id="b7137-105">呼び出し元はこのインターフェイスを実装して、CreateCoreWebView2CompositionController 経由で作成された CoreWebView2Controller を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b7137-105">The caller implements this interface to receive the CoreWebView2Controller created via CreateCoreWebView2CompositionController.</span></span>

## <span data-ttu-id="b7137-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="b7137-106">Summary</span></span>

 <span data-ttu-id="b7137-107">Members</span><span class="sxs-lookup"><span data-stu-id="b7137-107">Members</span></span>                        | <span data-ttu-id="b7137-108">説明</span><span class="sxs-lookup"><span data-stu-id="b7137-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b7137-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="b7137-109">Invoke</span></span>](#invoke) | <span data-ttu-id="b7137-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b7137-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="b7137-111">Members</span><span class="sxs-lookup"><span data-stu-id="b7137-111">Members</span></span>

#### <span data-ttu-id="b7137-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="b7137-112">Invoke</span></span> 

<span data-ttu-id="b7137-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b7137-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="b7137-114">パブリック HRESULT[呼び出し](#invoke)(hresult Result、 [ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* webView)</span><span class="sxs-lookup"><span data-stu-id="b7137-114">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* webView)</span></span>

