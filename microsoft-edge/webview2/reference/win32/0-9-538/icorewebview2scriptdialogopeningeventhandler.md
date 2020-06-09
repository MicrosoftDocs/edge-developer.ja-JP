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
ms.openlocfilehash: d594e009a7a125866268ea62a0bc6d235c282b46
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699099"
---
# <span data-ttu-id="431cc-104">インターフェイス ICoreWebView2ScriptDialogOpeningEventHandler</span><span class="sxs-lookup"><span data-stu-id="431cc-104">interface ICoreWebView2ScriptDialogOpeningEventHandler</span></span> 

```
interface ICoreWebView2ScriptDialogOpeningEventHandler
  : public IUnknown
```

<span data-ttu-id="431cc-105">呼び出し元は、このインターフェイスを実装して Scriptの開始イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="431cc-105">The caller implements this interface to receive the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="431cc-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="431cc-106">Summary</span></span>

 <span data-ttu-id="431cc-107">Members</span><span class="sxs-lookup"><span data-stu-id="431cc-107">Members</span></span>                        | <span data-ttu-id="431cc-108">説明</span><span class="sxs-lookup"><span data-stu-id="431cc-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="431cc-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="431cc-109">Invoke</span></span>](#invoke) | <span data-ttu-id="431cc-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="431cc-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="431cc-111">Members</span><span class="sxs-lookup"><span data-stu-id="431cc-111">Members</span></span>

#### <span data-ttu-id="431cc-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="431cc-112">Invoke</span></span> 

<span data-ttu-id="431cc-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="431cc-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="431cc-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2ScriptDialogOpeningEventArgs](icorewebview2scriptdialogopeningeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="431cc-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2ScriptDialogOpeningEventArgs](icorewebview2scriptdialogopeningeventargs.md) \* args)</span></span>

