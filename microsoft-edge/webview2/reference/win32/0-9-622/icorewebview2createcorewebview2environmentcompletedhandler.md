---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
ms.openlocfilehash: 3f6b6b9a2d4df2a450b4589c351c3ea98f7cc28f
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012377"
---
# <span data-ttu-id="a4bfb-104">インターフェイス ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="a4bfb-104">interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span></span> 

```
interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
  : public IUnknown
```

<span data-ttu-id="a4bfb-105">呼び出し元はこのインターフェイスを実装して、CreateCoreWebView2Environment 経由で作成された WebView2Environment を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a4bfb-105">The caller implements this interface to receive the WebView2Environment created via CreateCoreWebView2Environment.</span></span>

## <span data-ttu-id="a4bfb-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="a4bfb-106">Summary</span></span>

 <span data-ttu-id="a4bfb-107">Members</span><span class="sxs-lookup"><span data-stu-id="a4bfb-107">Members</span></span>                        | <span data-ttu-id="a4bfb-108">説明</span><span class="sxs-lookup"><span data-stu-id="a4bfb-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a4bfb-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="a4bfb-109">Invoke</span></span>](#invoke) | <span data-ttu-id="a4bfb-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a4bfb-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="a4bfb-111">Members</span><span class="sxs-lookup"><span data-stu-id="a4bfb-111">Members</span></span>

#### <span data-ttu-id="a4bfb-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="a4bfb-112">Invoke</span></span> 

<span data-ttu-id="a4bfb-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a4bfb-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="a4bfb-114">パブリック HRESULT [呼び出し](#invoke)(hresult ErrorCode、 [ICoreWebView2Environment](icorewebview2environment.md) \* があります)</span><span class="sxs-lookup"><span data-stu-id="a4bfb-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode, [ICoreWebView2Environment](icorewebview2environment.md) \* createdEnvironment)</span></span>

