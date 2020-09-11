---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ScriptDialogOpeningEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ScriptDialogOpeningEventHandler
ms.openlocfilehash: 72d8f198e8a212dfd2088591453ea2885a1dbc0d
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012324"
---
# <span data-ttu-id="3a987-104">インターフェイス ICoreWebView2ScriptDialogOpeningEventHandler</span><span class="sxs-lookup"><span data-stu-id="3a987-104">interface ICoreWebView2ScriptDialogOpeningEventHandler</span></span> 

```
interface ICoreWebView2ScriptDialogOpeningEventHandler
  : public IUnknown
```

<span data-ttu-id="3a987-105">呼び出し元は、このインターフェイスを実装して Scriptの開始イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3a987-105">The caller implements this interface to receive the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="3a987-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="3a987-106">Summary</span></span>

 <span data-ttu-id="3a987-107">Members</span><span class="sxs-lookup"><span data-stu-id="3a987-107">Members</span></span>                        | <span data-ttu-id="3a987-108">説明</span><span class="sxs-lookup"><span data-stu-id="3a987-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3a987-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="3a987-109">Invoke</span></span>](#invoke) | <span data-ttu-id="3a987-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3a987-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="3a987-111">Members</span><span class="sxs-lookup"><span data-stu-id="3a987-111">Members</span></span>

#### <span data-ttu-id="3a987-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="3a987-112">Invoke</span></span> 

<span data-ttu-id="3a987-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3a987-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="3a987-114">パブリック HRESULT [呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2ScriptDialogOpeningEventArgs](icorewebview2scriptdialogopeningeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="3a987-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2ScriptDialogOpeningEventArgs](icorewebview2scriptdialogopeningeventargs.md) \* args)</span></span>

