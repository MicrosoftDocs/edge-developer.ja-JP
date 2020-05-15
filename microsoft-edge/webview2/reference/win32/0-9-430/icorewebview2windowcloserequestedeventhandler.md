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
ms.openlocfilehash: 160395777b2936894001adfff1450d790e8da2c4
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654461"
---
# <span data-ttu-id="59f1e-104">インターフェイス ICoreWebView2WindowCloseRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="59f1e-104">interface ICoreWebView2WindowCloseRequestedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="59f1e-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="59f1e-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="59f1e-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59f1e-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2WindowCloseRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="59f1e-107">呼び出し元は、このインターフェイスを実装して、NewWindowRequested されたイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="59f1e-107">The caller implements this interface to receive NewWindowRequested events.</span></span>

## <span data-ttu-id="59f1e-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="59f1e-108">Summary</span></span>

 <span data-ttu-id="59f1e-109">Members</span><span class="sxs-lookup"><span data-stu-id="59f1e-109">Members</span></span>                        | <span data-ttu-id="59f1e-110">説明</span><span class="sxs-lookup"><span data-stu-id="59f1e-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="59f1e-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="59f1e-111">Invoke</span></span>](#invoke) | <span data-ttu-id="59f1e-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="59f1e-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="59f1e-113">Members</span><span class="sxs-lookup"><span data-stu-id="59f1e-113">Members</span></span>

#### <span data-ttu-id="59f1e-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="59f1e-114">Invoke</span></span> 

<span data-ttu-id="59f1e-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="59f1e-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="59f1e-116">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="59f1e-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,IUnknown \* args)</span></span>

<span data-ttu-id="59f1e-117">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="59f1e-117">There are no event args and the args parameter will be null.</span></span>

