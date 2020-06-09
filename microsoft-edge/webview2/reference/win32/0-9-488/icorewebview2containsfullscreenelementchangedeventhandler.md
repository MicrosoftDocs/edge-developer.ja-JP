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
ms.openlocfilehash: d48baec759174d9dcecc236a685db12c5de03db1
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697057"
---
# <span data-ttu-id="d4271-104">インターフェイス ICoreWebView2ContainsFullScreenElementChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="d4271-104">interface ICoreWebView2ContainsFullScreenElementChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="d4271-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d4271-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="d4271-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4271-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ContainsFullScreenElementChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="d4271-107">呼び出し元は、このメソッドを実装して、すべての Fullfullscreenelementchanged イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d4271-107">The caller implements this method to receive the ContainsFullScreenElementChanged events.</span></span>

## <span data-ttu-id="d4271-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="d4271-108">Summary</span></span>

 <span data-ttu-id="d4271-109">Members</span><span class="sxs-lookup"><span data-stu-id="d4271-109">Members</span></span>                        | <span data-ttu-id="d4271-110">説明</span><span class="sxs-lookup"><span data-stu-id="d4271-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d4271-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="d4271-111">Invoke</span></span>](#invoke) | <span data-ttu-id="d4271-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d4271-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="d4271-113">このイベントのイベント引数はありません。</span><span class="sxs-lookup"><span data-stu-id="d4271-113">There are no event args for this event.</span></span>

## <span data-ttu-id="d4271-114">Members</span><span class="sxs-lookup"><span data-stu-id="d4271-114">Members</span></span>

#### <span data-ttu-id="d4271-115">Invoke</span><span class="sxs-lookup"><span data-stu-id="d4271-115">Invoke</span></span> 

<span data-ttu-id="d4271-116">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d4271-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="d4271-117">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="d4271-117">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="d4271-118">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="d4271-118">There are no event args and the args parameter will be null.</span></span>

