---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2ScriptDialogOpeningEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 58e76c377d8d5709c006cb3a4da2e0edf73ec8fb
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884912"
---
# <span data-ttu-id="89af4-104">0.8.355-インターフェイス IWebView2ScriptDialogOpeningEventHandler</span><span class="sxs-lookup"><span data-stu-id="89af4-104">0.8.355 - interface IWebView2ScriptDialogOpeningEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2ScriptDialogOpeningEventHandler
  : public IUnknown
```

<span data-ttu-id="89af4-105">呼び出し元は、このインターフェイスを実装して Scriptの開始イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="89af4-105">The caller implements this interface to receive the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="89af4-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="89af4-106">Summary</span></span>

 <span data-ttu-id="89af4-107">Members</span><span class="sxs-lookup"><span data-stu-id="89af4-107">Members</span></span>                        | <span data-ttu-id="89af4-108">説明</span><span class="sxs-lookup"><span data-stu-id="89af4-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="89af4-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="89af4-109">Invoke</span></span>](#invoke) | <span data-ttu-id="89af4-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="89af4-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="89af4-111">Members</span><span class="sxs-lookup"><span data-stu-id="89af4-111">Members</span></span>

#### <span data-ttu-id="89af4-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="89af4-112">Invoke</span></span> 

<span data-ttu-id="89af4-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="89af4-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="89af4-114">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview、[IWebView2ScriptDialogOpeningEventArgs](IWebView2ScriptDialogOpeningEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="89af4-114">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2ScriptDialogOpeningEventArgs](IWebView2ScriptDialogOpeningEventArgs.md) \* args)</span></span>

