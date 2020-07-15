---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2DocumentTitleChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2DocumentTitleChangedEventHandler
ms.openlocfilehash: 6ea83bb610ff3348e361a7628f31aa022c3a62e9
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879542"
---
# <span data-ttu-id="c1d32-104">インターフェイス ICoreWebView2DocumentTitleChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="c1d32-104">interface ICoreWebView2DocumentTitleChangedEventHandler</span></span> 

```
interface ICoreWebView2DocumentTitleChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="c1d32-105">呼び出し元は、このインターフェイスを実装して、Documentのイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c1d32-105">The caller implements this interface to receive DocumentTitleChanged events.</span></span>

## <span data-ttu-id="c1d32-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="c1d32-106">Summary</span></span>

 <span data-ttu-id="c1d32-107">Members</span><span class="sxs-lookup"><span data-stu-id="c1d32-107">Members</span></span>                        | <span data-ttu-id="c1d32-108">説明</span><span class="sxs-lookup"><span data-stu-id="c1d32-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c1d32-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="c1d32-109">Invoke</span></span>](#invoke) | <span data-ttu-id="c1d32-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c1d32-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="c1d32-111">変更したタイトルを取得するには、DocumentTitle プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="c1d32-111">Use the DocumentTitle property to get the modified title.</span></span>

## <span data-ttu-id="c1d32-112">Members</span><span class="sxs-lookup"><span data-stu-id="c1d32-112">Members</span></span>

#### <span data-ttu-id="c1d32-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="c1d32-113">Invoke</span></span> 

<span data-ttu-id="c1d32-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c1d32-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="c1d32-115">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="c1d32-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="c1d32-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="c1d32-116">There are no event args and the args parameter will be null.</span></span>

