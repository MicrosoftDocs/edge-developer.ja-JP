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
ms.openlocfilehash: 062d6d3201acc71e58ab4cedd85f697f560bb7c0
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654407"
---
# <span data-ttu-id="c90af-104">インターフェイス IWebView2DocumentStateChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="c90af-104">interface IWebView2DocumentStateChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="c90af-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c90af-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="c90af-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c90af-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2DocumentStateChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="c90af-107">呼び出し元は、このインターフェイスを実装して DocumentStateChanged イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c90af-107">The caller implements this interface to receive the DocumentStateChanged event.</span></span>

## <span data-ttu-id="c90af-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="c90af-108">Summary</span></span>

 <span data-ttu-id="c90af-109">Members</span><span class="sxs-lookup"><span data-stu-id="c90af-109">Members</span></span>                        | <span data-ttu-id="c90af-110">説明</span><span class="sxs-lookup"><span data-stu-id="c90af-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c90af-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="c90af-111">Invoke</span></span>](#invoke) | <span data-ttu-id="c90af-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c90af-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="c90af-113">Members</span><span class="sxs-lookup"><span data-stu-id="c90af-113">Members</span></span>

#### <span data-ttu-id="c90af-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="c90af-114">Invoke</span></span> 

<span data-ttu-id="c90af-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c90af-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="c90af-116">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview、[IWebView2DocumentStateChangedEventArgs](IWebView2DocumentStateChangedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="c90af-116">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2DocumentStateChangedEventArgs](IWebView2DocumentStateChangedEventArgs.md) \* args)</span></span>

