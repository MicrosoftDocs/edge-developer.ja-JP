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
ms.openlocfilehash: 8451620cc819a6c2934efe80b241e7127861d48e
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654564"
---
# <span data-ttu-id="d082d-104">インターフェイス ICoreWebView2ScriptDialogOpeningEventHandler</span><span class="sxs-lookup"><span data-stu-id="d082d-104">interface ICoreWebView2ScriptDialogOpeningEventHandler</span></span> 

```
interface ICoreWebView2ScriptDialogOpeningEventHandler
  : public IUnknown
```

<span data-ttu-id="d082d-105">呼び出し元は、このインターフェイスを実装して Scriptの開始イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d082d-105">The caller implements this interface to receive the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="d082d-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="d082d-106">Summary</span></span>

 <span data-ttu-id="d082d-107">Members</span><span class="sxs-lookup"><span data-stu-id="d082d-107">Members</span></span>                        | <span data-ttu-id="d082d-108">説明</span><span class="sxs-lookup"><span data-stu-id="d082d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d082d-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="d082d-109">Invoke</span></span>](#invoke) | <span data-ttu-id="d082d-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d082d-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="d082d-111">Members</span><span class="sxs-lookup"><span data-stu-id="d082d-111">Members</span></span>

#### <span data-ttu-id="d082d-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="d082d-112">Invoke</span></span> 

<span data-ttu-id="d082d-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d082d-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="d082d-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2ScriptDialogOpeningEventArgs](icorewebview2scriptdialogopeningeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="d082d-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2ScriptDialogOpeningEventArgs](icorewebview2scriptdialogopeningeventargs.md) \* args)</span></span>

