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
ms.openlocfilehash: 73af2e217ca645536623eca18ceafad3270529cd
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654457"
---
# <span data-ttu-id="f59b3-104">インターフェイス ICoreWebView2WebMessageReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="f59b3-104">interface ICoreWebView2WebMessageReceivedEventHandler</span></span> 

```
interface ICoreWebView2WebMessageReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="f59b3-105">呼び出し元は、このインターフェイスを実装して WebMessageReceived イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f59b3-105">The caller implements this interface to receive the WebMessageReceived event.</span></span>

## <span data-ttu-id="f59b3-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="f59b3-106">Summary</span></span>

 <span data-ttu-id="f59b3-107">Members</span><span class="sxs-lookup"><span data-stu-id="f59b3-107">Members</span></span>                        | <span data-ttu-id="f59b3-108">説明</span><span class="sxs-lookup"><span data-stu-id="f59b3-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f59b3-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="f59b3-109">Invoke</span></span>](#invoke) | <span data-ttu-id="f59b3-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f59b3-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="f59b3-111">Members</span><span class="sxs-lookup"><span data-stu-id="f59b3-111">Members</span></span>

#### <span data-ttu-id="f59b3-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="f59b3-112">Invoke</span></span> 

<span data-ttu-id="f59b3-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f59b3-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="f59b3-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebMessageReceivedEventArgs](icorewebview2webmessagereceivedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="f59b3-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebMessageReceivedEventArgs](icorewebview2webmessagereceivedeventargs.md) \* args)</span></span>

