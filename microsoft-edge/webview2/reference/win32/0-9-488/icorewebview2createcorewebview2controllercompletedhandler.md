---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 9baf172a112f7fa84dae3a38cdbc0b0e0324473f
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880802"
---
# <span data-ttu-id="ffc65-104">0.9.515-インターフェイス ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="ffc65-104">0.9.515 - interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="ffc65-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ffc65-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="ffc65-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffc65-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
  : public IUnknown
```

<span data-ttu-id="ffc65-107">呼び出し元はこのインターフェイスを実装して、CreateCoreWebView2Controller 経由で作成された CoreWebView2Controller を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ffc65-107">The caller implements this interface to receive the CoreWebView2Controller created via CreateCoreWebView2Controller.</span></span>

## <span data-ttu-id="ffc65-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="ffc65-108">Summary</span></span>

 <span data-ttu-id="ffc65-109">Members</span><span class="sxs-lookup"><span data-stu-id="ffc65-109">Members</span></span>                        | <span data-ttu-id="ffc65-110">説明</span><span class="sxs-lookup"><span data-stu-id="ffc65-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ffc65-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="ffc65-111">Invoke</span></span>](#invoke) | <span data-ttu-id="ffc65-112">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ffc65-112">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="ffc65-113">Members</span><span class="sxs-lookup"><span data-stu-id="ffc65-113">Members</span></span>

#### <span data-ttu-id="ffc65-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="ffc65-114">Invoke</span></span> 

<span data-ttu-id="ffc65-115">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ffc65-115">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="ffc65-116">パブリック HRESULT[呼び出し](#invoke)(hresult Result, [ICoreWebView2Controller](icorewebview2controller.md) \* の生成コントローラー)</span><span class="sxs-lookup"><span data-stu-id="ffc65-116">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2Controller](icorewebview2controller.md) \* createdController)</span></span>

