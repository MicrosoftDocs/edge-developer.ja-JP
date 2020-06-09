---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: dbc1a3e05f9cdc5b5ced2e0b7d489b06392e6100
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699008"
---
# <span data-ttu-id="fb16a-104">インターフェイス ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="fb16a-104">interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span></span> 

```
interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
  : public IUnknown
```

<span data-ttu-id="fb16a-105">呼び出し元はこのインターフェイスを実装して、CreateCoreWebView2Environment 経由で作成された WebView2Environment を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="fb16a-105">The caller implements this interface to receive the WebView2Environment created via CreateCoreWebView2Environment.</span></span>

## <span data-ttu-id="fb16a-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="fb16a-106">Summary</span></span>

 <span data-ttu-id="fb16a-107">Members</span><span class="sxs-lookup"><span data-stu-id="fb16a-107">Members</span></span>                        | <span data-ttu-id="fb16a-108">説明</span><span class="sxs-lookup"><span data-stu-id="fb16a-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="fb16a-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="fb16a-109">Invoke</span></span>](#invoke) | <span data-ttu-id="fb16a-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fb16a-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="fb16a-111">Members</span><span class="sxs-lookup"><span data-stu-id="fb16a-111">Members</span></span>

#### <span data-ttu-id="fb16a-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="fb16a-112">Invoke</span></span> 

<span data-ttu-id="fb16a-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fb16a-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="fb16a-114">パブリック HRESULT[呼び出し](#invoke)(hresult Result、 [ICoreWebView2Environment](icorewebview2environment.md) \* created_environment)</span><span class="sxs-lookup"><span data-stu-id="fb16a-114">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2Environment](icorewebview2environment.md) \* created_environment)</span></span>

