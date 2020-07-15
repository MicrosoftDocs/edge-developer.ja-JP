---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2HistoryChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 5c4807a6f1772354f4448b25d49ea7ea86278f57
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880606"
---
# <span data-ttu-id="64f46-104">0.9.515-インターフェイス ICoreWebView2HistoryChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="64f46-104">0.9.515 - interface ICoreWebView2HistoryChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="64f46-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="64f46-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="64f46-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64f46-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2HistoryChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="64f46-107">呼び出し元は、このインターフェイスを実装して、履歴変更イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="64f46-107">The caller implements this interface to receive the HistoryChanged event.</span></span>

## <span data-ttu-id="64f46-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="64f46-108">Summary</span></span>

 <span data-ttu-id="64f46-109">Members</span><span class="sxs-lookup"><span data-stu-id="64f46-109">Members</span></span>                        | <span data-ttu-id="64f46-110">説明</span><span class="sxs-lookup"><span data-stu-id="64f46-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="64f46-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="64f46-111">Invoke</span></span>](#invoke) | <span data-ttu-id="64f46-112">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="64f46-112">There are no event args and the args parameter will be null.</span></span>

## <span data-ttu-id="64f46-113">Members</span><span class="sxs-lookup"><span data-stu-id="64f46-113">Members</span></span>

#### <span data-ttu-id="64f46-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="64f46-114">Invoke</span></span> 

<span data-ttu-id="64f46-115">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="64f46-115">There are no event args and the args parameter will be null.</span></span>

> <span data-ttu-id="64f46-116">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* webview、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="64f46-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* webview, IUnknown \* args)</span></span>

