---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2FocusChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: f4976cc5077f211970a953cebe7f2c3647879861
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880601"
---
# <span data-ttu-id="a7c61-104">0.9.515-インターフェイス ICoreWebView2FocusChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="a7c61-104">0.9.515 - interface ICoreWebView2FocusChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="a7c61-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a7c61-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="a7c61-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7c61-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2FocusChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="a7c61-107">呼び出し元は、このメソッドを実装して GotFocus イベントと LostFocus イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a7c61-107">The caller implements this method to receive the GotFocus and LostFocus events.</span></span>

## <span data-ttu-id="a7c61-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="a7c61-108">Summary</span></span>

 <span data-ttu-id="a7c61-109">Members</span><span class="sxs-lookup"><span data-stu-id="a7c61-109">Members</span></span>                        | <span data-ttu-id="a7c61-110">説明</span><span class="sxs-lookup"><span data-stu-id="a7c61-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a7c61-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="a7c61-111">Invoke</span></span>](#invoke) | <span data-ttu-id="a7c61-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a7c61-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="a7c61-113">このイベントのイベント引数はありません。</span><span class="sxs-lookup"><span data-stu-id="a7c61-113">There are no event args for this event.</span></span>

## <span data-ttu-id="a7c61-114">Members</span><span class="sxs-lookup"><span data-stu-id="a7c61-114">Members</span></span>

#### <span data-ttu-id="a7c61-115">Invoke</span><span class="sxs-lookup"><span data-stu-id="a7c61-115">Invoke</span></span> 

<span data-ttu-id="a7c61-116">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a7c61-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="a7c61-117">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="a7c61-117">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="a7c61-118">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="a7c61-118">There are no event args and the args parameter will be null.</span></span>

