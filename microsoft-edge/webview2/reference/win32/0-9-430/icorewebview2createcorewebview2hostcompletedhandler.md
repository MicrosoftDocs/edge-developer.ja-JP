---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 1d2956aee178c2bdc581d51a93006e14cfb539e3
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654327"
---
# <span data-ttu-id="4af4e-104">インターフェイス ICoreWebView2CreateCoreWebView2HostCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="4af4e-104">interface ICoreWebView2CreateCoreWebView2HostCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="4af4e-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4af4e-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="4af4e-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4af4e-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2CreateCoreWebView2HostCompletedHandler
  : public IUnknown
```

<span data-ttu-id="4af4e-107">呼び出し元はこのインターフェイスを実装して、CreateCoreWebView2Host 経由で作成された CoreWebView2Host を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="4af4e-107">The caller implements this interface to receive the CoreWebView2Host created via CreateCoreWebView2Host.</span></span>

## <span data-ttu-id="4af4e-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="4af4e-108">Summary</span></span>

 <span data-ttu-id="4af4e-109">Members</span><span class="sxs-lookup"><span data-stu-id="4af4e-109">Members</span></span>                        | <span data-ttu-id="4af4e-110">説明</span><span class="sxs-lookup"><span data-stu-id="4af4e-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4af4e-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="4af4e-111">Invoke</span></span>](#invoke) | <span data-ttu-id="4af4e-112">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4af4e-112">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="4af4e-113">Members</span><span class="sxs-lookup"><span data-stu-id="4af4e-113">Members</span></span>

#### <span data-ttu-id="4af4e-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="4af4e-114">Invoke</span></span> 

<span data-ttu-id="4af4e-115">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4af4e-115">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="4af4e-116">パブリック HRESULT[呼び出し](#invoke)(hresult Result、[ICoreWebView2Host](ICoreWebView2Host.md) \* created_host)</span><span class="sxs-lookup"><span data-stu-id="4af4e-116">public HRESULT [Invoke](#invoke)(HRESULT result,[ICoreWebView2Host](ICoreWebView2Host.md) \* created_host)</span></span>

