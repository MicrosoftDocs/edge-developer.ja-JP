---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2SourceChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2SourceChangedEventHandler
ms.openlocfilehash: b856211b8a4b4088acc741d4d5626b49340124d1
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879332"
---
# <span data-ttu-id="2c021-104">インターフェイス ICoreWebView2SourceChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="2c021-104">interface ICoreWebView2SourceChangedEventHandler</span></span> 

```
interface ICoreWebView2SourceChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="2c021-105">呼び出し元は、このインターフェイスを実装して、SourceChanged イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2c021-105">The caller implements this interface to receive the SourceChanged event.</span></span>

## <span data-ttu-id="2c021-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="2c021-106">Summary</span></span>

 <span data-ttu-id="2c021-107">Members</span><span class="sxs-lookup"><span data-stu-id="2c021-107">Members</span></span>                        | <span data-ttu-id="2c021-108">説明</span><span class="sxs-lookup"><span data-stu-id="2c021-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2c021-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="2c021-109">Invoke</span></span>](#invoke) | <span data-ttu-id="2c021-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2c021-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="2c021-111">Members</span><span class="sxs-lookup"><span data-stu-id="2c021-111">Members</span></span>

#### <span data-ttu-id="2c021-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="2c021-112">Invoke</span></span> 

<span data-ttu-id="2c021-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2c021-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="2c021-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* webview、 [ICoreWebView2SourceChangedEventArgs](icorewebview2sourcechangedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="2c021-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* webview, [ICoreWebView2SourceChangedEventArgs](icorewebview2sourcechangedeventargs.md) \* args)</span></span>

