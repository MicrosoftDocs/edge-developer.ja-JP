---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2ScriptDialogOpeningEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 31fea451b377b86eda0055a1074706ea12d9538e
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884023"
---
# <span data-ttu-id="e3838-104">0.9.430-インターフェイス ICoreWebView2ScriptDialogOpeningEventHandler</span><span class="sxs-lookup"><span data-stu-id="e3838-104">0.9.430 - interface ICoreWebView2ScriptDialogOpeningEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ScriptDialogOpeningEventHandler
  : public IUnknown
```

<span data-ttu-id="e3838-105">呼び出し元は、このインターフェイスを実装して Scriptの開始イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e3838-105">The caller implements this interface to receive the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="e3838-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="e3838-106">Summary</span></span>

 <span data-ttu-id="e3838-107">Members</span><span class="sxs-lookup"><span data-stu-id="e3838-107">Members</span></span>                        | <span data-ttu-id="e3838-108">説明</span><span class="sxs-lookup"><span data-stu-id="e3838-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e3838-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="e3838-109">Invoke</span></span>](#invoke) | <span data-ttu-id="e3838-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e3838-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="e3838-111">Members</span><span class="sxs-lookup"><span data-stu-id="e3838-111">Members</span></span>

#### <span data-ttu-id="e3838-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="e3838-112">Invoke</span></span> 

<span data-ttu-id="e3838-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e3838-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="e3838-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2ScriptDialogOpeningEventArgs](ICoreWebView2ScriptDialogOpeningEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="e3838-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2ScriptDialogOpeningEventArgs](ICoreWebView2ScriptDialogOpeningEventArgs.md) \* args)</span></span>

