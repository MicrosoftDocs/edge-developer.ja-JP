---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
ms.openlocfilehash: ab811f717c90ce77293c74a0e54bd3a66c896e72
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885269"
---
# <span data-ttu-id="28934-104">インターフェイス ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="28934-104">interface ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
  : public IUnknown
```

<span data-ttu-id="28934-105">呼び出し元はこのインターフェイスを実装して、CreateCoreWebView2CompositionController 経由で作成された CoreWebView2Controller を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="28934-105">The caller implements this interface to receive the CoreWebView2Controller created via CreateCoreWebView2CompositionController.</span></span>

## <span data-ttu-id="28934-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="28934-106">Summary</span></span>

 <span data-ttu-id="28934-107">Members</span><span class="sxs-lookup"><span data-stu-id="28934-107">Members</span></span>                        | <span data-ttu-id="28934-108">説明</span><span class="sxs-lookup"><span data-stu-id="28934-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="28934-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="28934-109">Invoke</span></span>](#invoke) | <span data-ttu-id="28934-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="28934-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="28934-111">Members</span><span class="sxs-lookup"><span data-stu-id="28934-111">Members</span></span>

#### <span data-ttu-id="28934-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="28934-112">Invoke</span></span> 

<span data-ttu-id="28934-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="28934-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="28934-114">パブリック HRESULT[呼び出し](#invoke)(hresult Result、 [ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* webView)</span><span class="sxs-lookup"><span data-stu-id="28934-114">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* webView)</span></span>

