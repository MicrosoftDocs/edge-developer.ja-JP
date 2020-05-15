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
ms.openlocfilehash: 3d70e87f9521beb8761d61012305f6d5eb06f923
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654240"
---
# <span data-ttu-id="a378b-104">インターフェイス ICoreWebView2FocusChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="a378b-104">interface ICoreWebView2FocusChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="a378b-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a378b-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="a378b-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a378b-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2FocusChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="a378b-107">呼び出し元は、このメソッドを実装して GotFocus イベントと LostFocus イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a378b-107">The caller implements this method to receive the GotFocus and LostFocus events.</span></span>

## <span data-ttu-id="a378b-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="a378b-108">Summary</span></span>

 <span data-ttu-id="a378b-109">Members</span><span class="sxs-lookup"><span data-stu-id="a378b-109">Members</span></span>                        | <span data-ttu-id="a378b-110">説明</span><span class="sxs-lookup"><span data-stu-id="a378b-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a378b-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="a378b-111">Invoke</span></span>](#invoke) | <span data-ttu-id="a378b-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a378b-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="a378b-113">このイベントのイベント引数はありません。</span><span class="sxs-lookup"><span data-stu-id="a378b-113">There are no event args for this event.</span></span>

## <span data-ttu-id="a378b-114">Members</span><span class="sxs-lookup"><span data-stu-id="a378b-114">Members</span></span>

#### <span data-ttu-id="a378b-115">Invoke</span><span class="sxs-lookup"><span data-stu-id="a378b-115">Invoke</span></span> 

<span data-ttu-id="a378b-116">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a378b-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="a378b-117">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Host](ICoreWebView2Host.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="a378b-117">public HRESULT [Invoke](#invoke)([ICoreWebView2Host](ICoreWebView2Host.md) \* sender,IUnknown \* args)</span></span>

<span data-ttu-id="a378b-118">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="a378b-118">There are no event args and the args parameter will be null.</span></span>

