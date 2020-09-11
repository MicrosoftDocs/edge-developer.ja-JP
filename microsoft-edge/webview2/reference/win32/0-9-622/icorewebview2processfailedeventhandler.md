---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ProcessFailedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ProcessFailedEventHandler
ms.openlocfilehash: 98f3f092bc1feb75ea2f94857c31dd80bcb907ee
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012331"
---
# <span data-ttu-id="4c808-104">インターフェイス ICoreWebView2ProcessFailedEventHandler</span><span class="sxs-lookup"><span data-stu-id="4c808-104">interface ICoreWebView2ProcessFailedEventHandler</span></span> 

```
interface ICoreWebView2ProcessFailedEventHandler
  : public IUnknown
```

<span data-ttu-id="4c808-105">呼び出し元は、ProcessFailed イベントを受け取るために、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="4c808-105">The caller implements this interface to receive ProcessFailed events.</span></span>

## <span data-ttu-id="4c808-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="4c808-106">Summary</span></span>

 <span data-ttu-id="4c808-107">Members</span><span class="sxs-lookup"><span data-stu-id="4c808-107">Members</span></span>                        | <span data-ttu-id="4c808-108">説明</span><span class="sxs-lookup"><span data-stu-id="4c808-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4c808-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="4c808-109">Invoke</span></span>](#invoke) | <span data-ttu-id="4c808-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4c808-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="4c808-111">Members</span><span class="sxs-lookup"><span data-stu-id="4c808-111">Members</span></span>

#### <span data-ttu-id="4c808-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="4c808-112">Invoke</span></span> 

<span data-ttu-id="4c808-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4c808-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="4c808-114">パブリック HRESULT [呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2ProcessFailedEventArgs](icorewebview2processfailedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="4c808-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2ProcessFailedEventArgs](icorewebview2processfailedeventargs.md) \* args)</span></span>
