---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: f85444231cb04857326d1662b2b4fb957e5305fe
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884499"
---
# <span data-ttu-id="19d5c-104">0.9.515-インターフェイス ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="19d5c-104">0.9.515 - interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
  : public IUnknown
```

<span data-ttu-id="19d5c-105">呼び出し元はこのインターフェイスを実装して、CreateCoreWebView2Controller 経由で作成された CoreWebView2Controller を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="19d5c-105">The caller implements this interface to receive the CoreWebView2Controller created via CreateCoreWebView2Controller.</span></span>

## <span data-ttu-id="19d5c-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="19d5c-106">Summary</span></span>

 <span data-ttu-id="19d5c-107">Members</span><span class="sxs-lookup"><span data-stu-id="19d5c-107">Members</span></span>                        | <span data-ttu-id="19d5c-108">説明</span><span class="sxs-lookup"><span data-stu-id="19d5c-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="19d5c-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="19d5c-109">Invoke</span></span>](#invoke) | <span data-ttu-id="19d5c-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="19d5c-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="19d5c-111">Members</span><span class="sxs-lookup"><span data-stu-id="19d5c-111">Members</span></span>

#### <span data-ttu-id="19d5c-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="19d5c-112">Invoke</span></span> 

<span data-ttu-id="19d5c-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="19d5c-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="19d5c-114">パブリック HRESULT[呼び出し](#invoke)(hresult Result, [ICoreWebView2Controller](icorewebview2controller.md) \* の生成コントローラー)</span><span class="sxs-lookup"><span data-stu-id="19d5c-114">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2Controller](icorewebview2controller.md) \* createdController)</span></span>

