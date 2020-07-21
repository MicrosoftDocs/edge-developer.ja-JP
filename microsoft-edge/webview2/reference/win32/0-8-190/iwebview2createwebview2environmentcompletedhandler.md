---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2CreateWebView2EnvironmentCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 9937fe08f440ce468f178e4ac17935bbb8a1a8ed
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886172"
---
# <span data-ttu-id="2500b-104">0.8.355-インターフェイス IWebView2CreateWebView2EnvironmentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="2500b-104">0.8.355 - interface IWebView2CreateWebView2EnvironmentCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2CreateWebView2EnvironmentCompletedHandler
  : public IUnknown
```

<span data-ttu-id="2500b-105">呼び出し元はこのインターフェイスを実装して、CreateWebView2Environment 経由で作成された WebView2Environment を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2500b-105">The caller implements this interface to receive the WebView2Environment created via CreateWebView2Environment.</span></span>

## <span data-ttu-id="2500b-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="2500b-106">Summary</span></span>

 <span data-ttu-id="2500b-107">Members</span><span class="sxs-lookup"><span data-stu-id="2500b-107">Members</span></span>                        | <span data-ttu-id="2500b-108">説明</span><span class="sxs-lookup"><span data-stu-id="2500b-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2500b-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="2500b-109">Invoke</span></span>](#invoke) | <span data-ttu-id="2500b-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2500b-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="2500b-111">Members</span><span class="sxs-lookup"><span data-stu-id="2500b-111">Members</span></span>

#### <span data-ttu-id="2500b-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="2500b-112">Invoke</span></span> 

<span data-ttu-id="2500b-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2500b-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="2500b-114">パブリック HRESULT[呼び出し](#invoke)(hresult Result,[IWebView2Environment](IWebView2Environment.md) \* webviewenvironment)</span><span class="sxs-lookup"><span data-stu-id="2500b-114">public HRESULT [Invoke](#invoke)(HRESULT result,[IWebView2Environment](IWebView2Environment.md) \* webViewEnvironment)</span></span>

