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
ms.openlocfilehash: 81d3fe4620dcb439933d661d7b061819b5e07a00
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654472"
---
# <span data-ttu-id="84e19-104">インターフェイス ICoreWebView2NavigationStartingEventHandler</span><span class="sxs-lookup"><span data-stu-id="84e19-104">interface ICoreWebView2NavigationStartingEventHandler</span></span> 

```
interface ICoreWebView2NavigationStartingEventHandler
  : public IUnknown
```

<span data-ttu-id="84e19-105">呼び出し元は、NavigationStarting イベントを受け取るために、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="84e19-105">The caller implements this interface to receive the NavigationStarting event.</span></span>

## <span data-ttu-id="84e19-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="84e19-106">Summary</span></span>

 <span data-ttu-id="84e19-107">Members</span><span class="sxs-lookup"><span data-stu-id="84e19-107">Members</span></span>                        | <span data-ttu-id="84e19-108">説明</span><span class="sxs-lookup"><span data-stu-id="84e19-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="84e19-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="84e19-109">Invoke</span></span>](#invoke) | <span data-ttu-id="84e19-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="84e19-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="84e19-111">Members</span><span class="sxs-lookup"><span data-stu-id="84e19-111">Members</span></span>

#### <span data-ttu-id="84e19-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="84e19-112">Invoke</span></span> 

<span data-ttu-id="84e19-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="84e19-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="84e19-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationStartingEventArgs](icorewebview2navigationstartingeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="84e19-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationStartingEventArgs](icorewebview2navigationstartingeventargs.md) \* args)</span></span>

