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
ms.openlocfilehash: 5cbf358780d196168976fc0812c9845d0ec59b24
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654278"
---
# <span data-ttu-id="10253-104">インターフェイス ICoreWebView2AcceleratorKeyPressedEventHandler</span><span class="sxs-lookup"><span data-stu-id="10253-104">interface ICoreWebView2AcceleratorKeyPressedEventHandler</span></span> 

```
interface ICoreWebView2AcceleratorKeyPressedEventHandler
  : public IUnknown
```

<span data-ttu-id="10253-105">呼び出し元は、このインターフェイスを実装して AcceleratorKeyPressed イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="10253-105">The caller implements this interface to receive the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="10253-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="10253-106">Summary</span></span>

 <span data-ttu-id="10253-107">Members</span><span class="sxs-lookup"><span data-stu-id="10253-107">Members</span></span>                        | <span data-ttu-id="10253-108">説明</span><span class="sxs-lookup"><span data-stu-id="10253-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="10253-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="10253-109">Invoke</span></span>](#invoke) | <span data-ttu-id="10253-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="10253-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="10253-111">Members</span><span class="sxs-lookup"><span data-stu-id="10253-111">Members</span></span>

#### <span data-ttu-id="10253-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="10253-112">Invoke</span></span> 

<span data-ttu-id="10253-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="10253-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="10253-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2AcceleratorKeyPressedEventArgs](icorewebview2acceleratorkeypressedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="10253-114">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2AcceleratorKeyPressedEventArgs](icorewebview2acceleratorkeypressedeventargs.md) \* args)</span></span>

