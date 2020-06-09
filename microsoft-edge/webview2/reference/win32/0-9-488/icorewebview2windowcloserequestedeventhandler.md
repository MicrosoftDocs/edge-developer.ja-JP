---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 8d464202e224647c02953312810475b2755c530b
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698114"
---
# <span data-ttu-id="1dc7f-104">インターフェイス ICoreWebView2WindowCloseRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="1dc7f-104">interface ICoreWebView2WindowCloseRequestedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="1dc7f-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1dc7f-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="1dc7f-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dc7f-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2WindowCloseRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="1dc7f-107">呼び出し元は、このインターフェイスを実装して、NewWindowRequested されたイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1dc7f-107">The caller implements this interface to receive NewWindowRequested events.</span></span>

## <span data-ttu-id="1dc7f-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="1dc7f-108">Summary</span></span>

 <span data-ttu-id="1dc7f-109">Members</span><span class="sxs-lookup"><span data-stu-id="1dc7f-109">Members</span></span>                        | <span data-ttu-id="1dc7f-110">説明</span><span class="sxs-lookup"><span data-stu-id="1dc7f-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="1dc7f-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="1dc7f-111">Invoke</span></span>](#invoke) | <span data-ttu-id="1dc7f-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1dc7f-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="1dc7f-113">Members</span><span class="sxs-lookup"><span data-stu-id="1dc7f-113">Members</span></span>

#### <span data-ttu-id="1dc7f-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="1dc7f-114">Invoke</span></span> 

<span data-ttu-id="1dc7f-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1dc7f-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="1dc7f-116">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="1dc7f-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="1dc7f-117">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="1dc7f-117">There are no event args and the args parameter will be null.</span></span>

