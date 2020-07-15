---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 0bbd1f79e4ecd9e0816ec144149f2e66f20fc5fe
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880816"
---
# <span data-ttu-id="5ec9c-104">0.9.515-インターフェイス ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="5ec9c-104">0.9.515 - interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="5ec9c-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5ec9c-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="5ec9c-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ec9c-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
  : public IUnknown
```

<span data-ttu-id="5ec9c-107">呼び出し元はこのインターフェイスを実装して、CreateCoreWebView2Environment 経由で作成された WebView2Environment を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5ec9c-107">The caller implements this interface to receive the WebView2Environment created via CreateCoreWebView2Environment.</span></span>

## <span data-ttu-id="5ec9c-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="5ec9c-108">Summary</span></span>

 <span data-ttu-id="5ec9c-109">Members</span><span class="sxs-lookup"><span data-stu-id="5ec9c-109">Members</span></span>                        | <span data-ttu-id="5ec9c-110">説明</span><span class="sxs-lookup"><span data-stu-id="5ec9c-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5ec9c-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="5ec9c-111">Invoke</span></span>](#invoke) | <span data-ttu-id="5ec9c-112">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5ec9c-112">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="5ec9c-113">Members</span><span class="sxs-lookup"><span data-stu-id="5ec9c-113">Members</span></span>

#### <span data-ttu-id="5ec9c-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="5ec9c-114">Invoke</span></span> 

<span data-ttu-id="5ec9c-115">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5ec9c-115">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="5ec9c-116">パブリック HRESULT[呼び出し](#invoke)(hresult Result、 [ICoreWebView2Environment](icorewebview2environment.md) \* created_environment)</span><span class="sxs-lookup"><span data-stu-id="5ec9c-116">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2Environment](icorewebview2environment.md) \* created_environment)</span></span>

