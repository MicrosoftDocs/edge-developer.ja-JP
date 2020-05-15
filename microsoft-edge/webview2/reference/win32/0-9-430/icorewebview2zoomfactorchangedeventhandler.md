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
ms.openlocfilehash: dd9365fb8fb0215b3090928c8edb59575c6247fe
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654504"
---
# <span data-ttu-id="82821-104">インターフェイス ICoreWebView2ZoomFactorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="82821-104">interface ICoreWebView2ZoomFactorChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="82821-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82821-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="82821-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82821-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ZoomFactorChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="82821-107">呼び出し元は、このインターフェイスを実装して ZoomFactorChanged イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="82821-107">The caller implements this interface to receive ZoomFactorChanged events.</span></span>

## <span data-ttu-id="82821-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="82821-108">Summary</span></span>

 <span data-ttu-id="82821-109">Members</span><span class="sxs-lookup"><span data-stu-id="82821-109">Members</span></span>                        | <span data-ttu-id="82821-110">説明</span><span class="sxs-lookup"><span data-stu-id="82821-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="82821-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="82821-111">Invoke</span></span>](#invoke) | <span data-ttu-id="82821-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="82821-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="82821-113">変更されたズームファクターを取得するには、ICoreWebView2Host プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="82821-113">Use the ICoreWebView2Host.ZoomFactor property to get the modified zoom factor.</span></span>

## <span data-ttu-id="82821-114">Members</span><span class="sxs-lookup"><span data-stu-id="82821-114">Members</span></span>

#### <span data-ttu-id="82821-115">Invoke</span><span class="sxs-lookup"><span data-stu-id="82821-115">Invoke</span></span> 

<span data-ttu-id="82821-116">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="82821-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="82821-117">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Host](ICoreWebView2Host.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="82821-117">public HRESULT [Invoke](#invoke)([ICoreWebView2Host](ICoreWebView2Host.md) \* sender,IUnknown \* args)</span></span>

<span data-ttu-id="82821-118">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="82821-118">There are no event args and the args parameter will be null.</span></span>

