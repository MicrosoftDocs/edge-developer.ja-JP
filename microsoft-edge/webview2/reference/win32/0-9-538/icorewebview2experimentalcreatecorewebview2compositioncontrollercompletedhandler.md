---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
ms.openlocfilehash: 8fc3efa6bf1ba9a9e721dcba67e8350ded38cc62
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011138"
---
# <span data-ttu-id="b5eff-104">0.9.579-インターフェイス ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="b5eff-104">0.9.579 - interface ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
  : public IUnknown
```

<span data-ttu-id="b5eff-105">呼び出し元はこのインターフェイスを実装して、CreateCoreWebView2CompositionController 経由で作成された CoreWebView2Controller を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b5eff-105">The caller implements this interface to receive the CoreWebView2Controller created via CreateCoreWebView2CompositionController.</span></span>

## <span data-ttu-id="b5eff-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="b5eff-106">Summary</span></span>

 <span data-ttu-id="b5eff-107">Members</span><span class="sxs-lookup"><span data-stu-id="b5eff-107">Members</span></span>                        | <span data-ttu-id="b5eff-108">説明</span><span class="sxs-lookup"><span data-stu-id="b5eff-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b5eff-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="b5eff-109">Invoke</span></span>](#invoke) | <span data-ttu-id="b5eff-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b5eff-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="b5eff-111">Members</span><span class="sxs-lookup"><span data-stu-id="b5eff-111">Members</span></span>

#### <span data-ttu-id="b5eff-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="b5eff-112">Invoke</span></span> 

<span data-ttu-id="b5eff-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b5eff-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="b5eff-114">パブリック HRESULT [呼び出し](#invoke)(hresult Result、 [ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* webView)</span><span class="sxs-lookup"><span data-stu-id="b5eff-114">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* webView)</span></span>

