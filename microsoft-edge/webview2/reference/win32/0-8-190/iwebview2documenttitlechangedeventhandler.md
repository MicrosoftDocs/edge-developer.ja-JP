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
ms.openlocfilehash: 69d8f410c7d9e7c4a8b1dc526babf535a372048f
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654404"
---
# <span data-ttu-id="63234-104">インターフェイス IWebView2DocumentTitleChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="63234-104">interface IWebView2DocumentTitleChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="63234-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="63234-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="63234-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63234-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2DocumentTitleChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="63234-107">呼び出し元は、このインターフェイスを実装して、Documentのイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="63234-107">The caller implements this interface to receive DocumentTitleChanged events.</span></span>

## <span data-ttu-id="63234-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="63234-108">Summary</span></span>

 <span data-ttu-id="63234-109">Members</span><span class="sxs-lookup"><span data-stu-id="63234-109">Members</span></span>                        | <span data-ttu-id="63234-110">説明</span><span class="sxs-lookup"><span data-stu-id="63234-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="63234-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="63234-111">Invoke</span></span>](#invoke) | <span data-ttu-id="63234-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="63234-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="63234-113">変更したタイトルを取得するには、DocumentTitle プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="63234-113">Use the DocumentTitle property to get the modified title.</span></span>

## <span data-ttu-id="63234-114">Members</span><span class="sxs-lookup"><span data-stu-id="63234-114">Members</span></span>

#### <span data-ttu-id="63234-115">Invoke</span><span class="sxs-lookup"><span data-stu-id="63234-115">Invoke</span></span> 

<span data-ttu-id="63234-116">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="63234-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="63234-117">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView3](IWebView2WebView3.md) \* webview、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="63234-117">public HRESULT [Invoke](#invoke)([IWebView2WebView3](IWebView2WebView3.md) \* webview,IUnknown \* args)</span></span>

<span data-ttu-id="63234-118">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="63234-118">There are no event args and the args parameter will be null.</span></span>

