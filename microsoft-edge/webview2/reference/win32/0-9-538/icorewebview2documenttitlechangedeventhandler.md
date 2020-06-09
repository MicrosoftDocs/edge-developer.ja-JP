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
ms.openlocfilehash: 2908ad851a7899d2ea053bfa50616c8b244bca6c
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699004"
---
# <span data-ttu-id="e1820-104">インターフェイス ICoreWebView2DocumentTitleChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="e1820-104">interface ICoreWebView2DocumentTitleChangedEventHandler</span></span> 

```
interface ICoreWebView2DocumentTitleChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="e1820-105">呼び出し元は、このインターフェイスを実装して、Documentのイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e1820-105">The caller implements this interface to receive DocumentTitleChanged events.</span></span>

## <span data-ttu-id="e1820-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="e1820-106">Summary</span></span>

 <span data-ttu-id="e1820-107">Members</span><span class="sxs-lookup"><span data-stu-id="e1820-107">Members</span></span>                        | <span data-ttu-id="e1820-108">説明</span><span class="sxs-lookup"><span data-stu-id="e1820-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e1820-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="e1820-109">Invoke</span></span>](#invoke) | <span data-ttu-id="e1820-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e1820-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="e1820-111">変更したタイトルを取得するには、DocumentTitle プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="e1820-111">Use the DocumentTitle property to get the modified title.</span></span>

## <span data-ttu-id="e1820-112">Members</span><span class="sxs-lookup"><span data-stu-id="e1820-112">Members</span></span>

#### <span data-ttu-id="e1820-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="e1820-113">Invoke</span></span> 

<span data-ttu-id="e1820-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e1820-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="e1820-115">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="e1820-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="e1820-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="e1820-116">There are no event args and the args parameter will be null.</span></span>

