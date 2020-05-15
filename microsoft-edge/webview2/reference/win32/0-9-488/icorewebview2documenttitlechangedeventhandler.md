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
ms.openlocfilehash: 25e6318a695d67995f6fbf1b2ad4b02e1a982860
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654427"
---
# <span data-ttu-id="11ddb-104">インターフェイス ICoreWebView2DocumentTitleChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="11ddb-104">interface ICoreWebView2DocumentTitleChangedEventHandler</span></span> 

```
interface ICoreWebView2DocumentTitleChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="11ddb-105">呼び出し元は、このインターフェイスを実装して、Documentのイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="11ddb-105">The caller implements this interface to receive DocumentTitleChanged events.</span></span>

## <span data-ttu-id="11ddb-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="11ddb-106">Summary</span></span>

 <span data-ttu-id="11ddb-107">Members</span><span class="sxs-lookup"><span data-stu-id="11ddb-107">Members</span></span>                        | <span data-ttu-id="11ddb-108">説明</span><span class="sxs-lookup"><span data-stu-id="11ddb-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="11ddb-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="11ddb-109">Invoke</span></span>](#invoke) | <span data-ttu-id="11ddb-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="11ddb-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="11ddb-111">変更したタイトルを取得するには、DocumentTitle プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="11ddb-111">Use the DocumentTitle property to get the modified title.</span></span>

## <span data-ttu-id="11ddb-112">Members</span><span class="sxs-lookup"><span data-stu-id="11ddb-112">Members</span></span>

#### <span data-ttu-id="11ddb-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="11ddb-113">Invoke</span></span> 

<span data-ttu-id="11ddb-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="11ddb-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="11ddb-115">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="11ddb-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="11ddb-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="11ddb-116">There are no event args and the args parameter will be null.</span></span>

