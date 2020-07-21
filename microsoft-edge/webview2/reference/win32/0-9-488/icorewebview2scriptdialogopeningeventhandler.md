---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2ScriptDialogOpeningEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 90721fff94948c632c1bb19d861ffc7d4911faff
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884765"
---
# <span data-ttu-id="105e2-104">0.9.515-インターフェイス ICoreWebView2ScriptDialogOpeningEventHandler</span><span class="sxs-lookup"><span data-stu-id="105e2-104">0.9.515 - interface ICoreWebView2ScriptDialogOpeningEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ScriptDialogOpeningEventHandler
  : public IUnknown
```

<span data-ttu-id="105e2-105">呼び出し元は、このインターフェイスを実装して Scriptの開始イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="105e2-105">The caller implements this interface to receive the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="105e2-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="105e2-106">Summary</span></span>

 <span data-ttu-id="105e2-107">Members</span><span class="sxs-lookup"><span data-stu-id="105e2-107">Members</span></span>                        | <span data-ttu-id="105e2-108">説明</span><span class="sxs-lookup"><span data-stu-id="105e2-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="105e2-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="105e2-109">Invoke</span></span>](#invoke) | <span data-ttu-id="105e2-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="105e2-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="105e2-111">Members</span><span class="sxs-lookup"><span data-stu-id="105e2-111">Members</span></span>

#### <span data-ttu-id="105e2-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="105e2-112">Invoke</span></span> 

<span data-ttu-id="105e2-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="105e2-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="105e2-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2ScriptDialogOpeningEventArgs](icorewebview2scriptdialogopeningeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="105e2-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2ScriptDialogOpeningEventArgs](icorewebview2scriptdialogopeningeventargs.md) \* args)</span></span>

