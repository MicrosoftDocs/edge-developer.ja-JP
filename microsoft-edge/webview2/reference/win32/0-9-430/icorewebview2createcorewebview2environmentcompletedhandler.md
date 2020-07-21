---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 5cc3ca23dcababc35a73b44a81c54439d0dbe1a3
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884310"
---
# <span data-ttu-id="82358-104">0.9.430-インターフェイス ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="82358-104">0.9.430 - interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
  : public IUnknown
```

<span data-ttu-id="82358-105">呼び出し元はこのインターフェイスを実装して、CreateCoreWebView2Environment 経由で作成された WebView2Environment を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="82358-105">The caller implements this interface to receive the WebView2Environment created via CreateCoreWebView2Environment.</span></span>

## <span data-ttu-id="82358-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="82358-106">Summary</span></span>

 <span data-ttu-id="82358-107">Members</span><span class="sxs-lookup"><span data-stu-id="82358-107">Members</span></span>                        | <span data-ttu-id="82358-108">説明</span><span class="sxs-lookup"><span data-stu-id="82358-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="82358-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="82358-109">Invoke</span></span>](#invoke) | <span data-ttu-id="82358-110">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="82358-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="82358-111">Members</span><span class="sxs-lookup"><span data-stu-id="82358-111">Members</span></span>

#### <span data-ttu-id="82358-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="82358-112">Invoke</span></span> 

<span data-ttu-id="82358-113">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="82358-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="82358-114">パブリック HRESULT[呼び出し](#invoke)(hresult Result、[ICoreWebView2Environment](ICoreWebView2Environment.md) \* created_environment)</span><span class="sxs-lookup"><span data-stu-id="82358-114">public HRESULT [Invoke](#invoke)(HRESULT result,[ICoreWebView2Environment](ICoreWebView2Environment.md) \* created_environment)</span></span>

