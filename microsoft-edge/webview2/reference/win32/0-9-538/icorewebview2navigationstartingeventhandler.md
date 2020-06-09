---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: faeafdb0f2da5fa5037f41faab0d0b5ee8434eb4
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699043"
---
# <span data-ttu-id="44cba-104">インターフェイス ICoreWebView2NavigationStartingEventHandler</span><span class="sxs-lookup"><span data-stu-id="44cba-104">interface ICoreWebView2NavigationStartingEventHandler</span></span> 

```
interface ICoreWebView2NavigationStartingEventHandler
  : public IUnknown
```

<span data-ttu-id="44cba-105">呼び出し元は、NavigationStarting イベントを受け取るために、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="44cba-105">The caller implements this interface to receive the NavigationStarting event.</span></span>

## <span data-ttu-id="44cba-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="44cba-106">Summary</span></span>

 <span data-ttu-id="44cba-107">Members</span><span class="sxs-lookup"><span data-stu-id="44cba-107">Members</span></span>                        | <span data-ttu-id="44cba-108">説明</span><span class="sxs-lookup"><span data-stu-id="44cba-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="44cba-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="44cba-109">Invoke</span></span>](#invoke) | <span data-ttu-id="44cba-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="44cba-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="44cba-111">Members</span><span class="sxs-lookup"><span data-stu-id="44cba-111">Members</span></span>

#### <span data-ttu-id="44cba-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="44cba-112">Invoke</span></span> 

<span data-ttu-id="44cba-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="44cba-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="44cba-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationStartingEventArgs](icorewebview2navigationstartingeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="44cba-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationStartingEventArgs](icorewebview2navigationstartingeventargs.md) \* args)</span></span>

