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
ms.openlocfilehash: 42e3767ad2a42a1d9e9931efa8a4fe844ea80dba
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654218"
---
# <span data-ttu-id="80b7b-104">インターフェイス ICoreWebView2HistoryChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="80b7b-104">interface ICoreWebView2HistoryChangedEventHandler</span></span> 

```
interface ICoreWebView2HistoryChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="80b7b-105">呼び出し元は、このインターフェイスを実装して、履歴変更イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="80b7b-105">The caller implements this interface to receive the HistoryChanged event.</span></span>

## <span data-ttu-id="80b7b-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="80b7b-106">Summary</span></span>

 <span data-ttu-id="80b7b-107">Members</span><span class="sxs-lookup"><span data-stu-id="80b7b-107">Members</span></span>                        | <span data-ttu-id="80b7b-108">説明</span><span class="sxs-lookup"><span data-stu-id="80b7b-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="80b7b-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="80b7b-109">Invoke</span></span>](#invoke) | <span data-ttu-id="80b7b-110">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="80b7b-110">There are no event args and the args parameter will be null.</span></span>

## <span data-ttu-id="80b7b-111">Members</span><span class="sxs-lookup"><span data-stu-id="80b7b-111">Members</span></span>

#### <span data-ttu-id="80b7b-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="80b7b-112">Invoke</span></span> 

<span data-ttu-id="80b7b-113">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="80b7b-113">There are no event args and the args parameter will be null.</span></span>

> <span data-ttu-id="80b7b-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* webview、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="80b7b-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* webview, IUnknown \* args)</span></span>

