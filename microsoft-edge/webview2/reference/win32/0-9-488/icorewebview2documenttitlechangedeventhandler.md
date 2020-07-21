---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2DocumentTitleChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 486218dcb54281da559fb5b5f69314248a0d2cad
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883820"
---
# <span data-ttu-id="8bca2-104">0.9.515-インターフェイス ICoreWebView2DocumentTitleChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="8bca2-104">0.9.515 - interface ICoreWebView2DocumentTitleChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2DocumentTitleChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="8bca2-105">呼び出し元は、このインターフェイスを実装して、Documentのイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8bca2-105">The caller implements this interface to receive DocumentTitleChanged events.</span></span>

## <span data-ttu-id="8bca2-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="8bca2-106">Summary</span></span>

 <span data-ttu-id="8bca2-107">Members</span><span class="sxs-lookup"><span data-stu-id="8bca2-107">Members</span></span>                        | <span data-ttu-id="8bca2-108">説明</span><span class="sxs-lookup"><span data-stu-id="8bca2-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8bca2-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="8bca2-109">Invoke</span></span>](#invoke) | <span data-ttu-id="8bca2-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8bca2-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="8bca2-111">変更したタイトルを取得するには、DocumentTitle プロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="8bca2-111">Use the DocumentTitle property to get the modified title.</span></span>

## <span data-ttu-id="8bca2-112">Members</span><span class="sxs-lookup"><span data-stu-id="8bca2-112">Members</span></span>

#### <span data-ttu-id="8bca2-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="8bca2-113">Invoke</span></span> 

<span data-ttu-id="8bca2-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8bca2-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="8bca2-115">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="8bca2-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="8bca2-116">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="8bca2-116">There are no event args and the args parameter will be null.</span></span>

