---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 9aa9a18701621ca78b74b12340ef5132953fbd2b
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880669"
---
# <span data-ttu-id="1ec49-104">0.9.515-インターフェイス ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="1ec49-104">0.9.515 - interface ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="1ec49-105">これは、プレリリース SDK バージョン0.9.488 に同梱されている実験的な API です。</span><span class="sxs-lookup"><span data-stu-id="1ec49-105">This an experimental API that is shipped with our prerelease SDK version 0.9.488.</span></span>

```
interface ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
  : public IUnknown
```

<span data-ttu-id="1ec49-106">呼び出し元はこのインターフェイスを実装して、CreateCoreWebView2CompositionController 経由で作成された CoreWebView2Controller を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1ec49-106">The caller implements this interface to receive the CoreWebView2Controller created via CreateCoreWebView2CompositionController.</span></span>

## <span data-ttu-id="1ec49-107">まとめ</span><span class="sxs-lookup"><span data-stu-id="1ec49-107">Summary</span></span>

 <span data-ttu-id="1ec49-108">Members</span><span class="sxs-lookup"><span data-stu-id="1ec49-108">Members</span></span>                        | <span data-ttu-id="1ec49-109">説明</span><span class="sxs-lookup"><span data-stu-id="1ec49-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="1ec49-110">Invoke</span><span class="sxs-lookup"><span data-stu-id="1ec49-110">Invoke</span></span>](#invoke) | <span data-ttu-id="1ec49-111">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1ec49-111">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="1ec49-112">Members</span><span class="sxs-lookup"><span data-stu-id="1ec49-112">Members</span></span>

#### <span data-ttu-id="1ec49-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="1ec49-113">Invoke</span></span> 

<span data-ttu-id="1ec49-114">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1ec49-114">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="1ec49-115">パブリック HRESULT[呼び出し](#invoke)(hresult Result、 [ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* webView)</span><span class="sxs-lookup"><span data-stu-id="1ec49-115">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* webView)</span></span>

