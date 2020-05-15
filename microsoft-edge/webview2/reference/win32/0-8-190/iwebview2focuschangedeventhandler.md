---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 23cce166d4ef2d05b6ffe5814c1568f75a72be0e
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654237"
---
# <span data-ttu-id="8c416-104">インターフェイス IWebView2FocusChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="8c416-104">interface IWebView2FocusChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="8c416-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8c416-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="8c416-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c416-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2FocusChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="8c416-107">呼び出し元は、このメソッドを実装して GotFocus イベントと LostFocus イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8c416-107">The caller implements this method to receive the GotFocus and LostFocus events.</span></span>

## <span data-ttu-id="8c416-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="8c416-108">Summary</span></span>

 <span data-ttu-id="8c416-109">Members</span><span class="sxs-lookup"><span data-stu-id="8c416-109">Members</span></span>                        | <span data-ttu-id="8c416-110">説明</span><span class="sxs-lookup"><span data-stu-id="8c416-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8c416-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="8c416-111">Invoke</span></span>](#invoke) | <span data-ttu-id="8c416-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8c416-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="8c416-113">このイベントのイベント引数はありません。</span><span class="sxs-lookup"><span data-stu-id="8c416-113">There are no event args for this event.</span></span>

## <span data-ttu-id="8c416-114">Members</span><span class="sxs-lookup"><span data-stu-id="8c416-114">Members</span></span>

#### <span data-ttu-id="8c416-115">Invoke</span><span class="sxs-lookup"><span data-stu-id="8c416-115">Invoke</span></span> 

<span data-ttu-id="8c416-116">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8c416-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="8c416-117">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="8c416-117">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,IUnknown \* args)</span></span>

<span data-ttu-id="8c416-118">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="8c416-118">There are no event args and the args parameter will be null.</span></span>

