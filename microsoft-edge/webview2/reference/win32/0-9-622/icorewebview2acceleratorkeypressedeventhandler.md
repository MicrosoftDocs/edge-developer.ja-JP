---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2AcceleratorKeyPressedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2AcceleratorKeyPressedEventHandler
ms.openlocfilehash: 15ad3a4afb76ea8068066097340af204b45fe416
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012355"
---
# <span data-ttu-id="5de51-104">インターフェイス ICoreWebView2AcceleratorKeyPressedEventHandler</span><span class="sxs-lookup"><span data-stu-id="5de51-104">interface ICoreWebView2AcceleratorKeyPressedEventHandler</span></span> 

```
interface ICoreWebView2AcceleratorKeyPressedEventHandler
  : public IUnknown
```

<span data-ttu-id="5de51-105">呼び出し元は、このインターフェイスを実装して AcceleratorKeyPressed イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5de51-105">The caller implements this interface to receive the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="5de51-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="5de51-106">Summary</span></span>

 <span data-ttu-id="5de51-107">Members</span><span class="sxs-lookup"><span data-stu-id="5de51-107">Members</span></span>                        | <span data-ttu-id="5de51-108">説明</span><span class="sxs-lookup"><span data-stu-id="5de51-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5de51-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="5de51-109">Invoke</span></span>](#invoke) | <span data-ttu-id="5de51-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5de51-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="5de51-111">Members</span><span class="sxs-lookup"><span data-stu-id="5de51-111">Members</span></span>

#### <span data-ttu-id="5de51-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="5de51-112">Invoke</span></span> 

<span data-ttu-id="5de51-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5de51-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="5de51-114">パブリック HRESULT [呼び出し](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2AcceleratorKeyPressedEventArgs](icorewebview2acceleratorkeypressedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="5de51-114">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2AcceleratorKeyPressedEventArgs](icorewebview2acceleratorkeypressedeventargs.md) \* args)</span></span>

