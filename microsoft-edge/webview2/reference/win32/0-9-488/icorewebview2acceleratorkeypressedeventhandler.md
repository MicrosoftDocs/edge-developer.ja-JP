---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2AcceleratorKeyPressedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 8b0d6a4db4a4af6710df54e42b3cddee061a4040
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880963"
---
# <span data-ttu-id="53e30-104">0.9.515-インターフェイス ICoreWebView2AcceleratorKeyPressedEventHandler</span><span class="sxs-lookup"><span data-stu-id="53e30-104">0.9.515 - interface ICoreWebView2AcceleratorKeyPressedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="53e30-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="53e30-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="53e30-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53e30-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2AcceleratorKeyPressedEventHandler
  : public IUnknown
```

<span data-ttu-id="53e30-107">呼び出し元は、このインターフェイスを実装して AcceleratorKeyPressed イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="53e30-107">The caller implements this interface to receive the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="53e30-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="53e30-108">Summary</span></span>

 <span data-ttu-id="53e30-109">Members</span><span class="sxs-lookup"><span data-stu-id="53e30-109">Members</span></span>                        | <span data-ttu-id="53e30-110">説明</span><span class="sxs-lookup"><span data-stu-id="53e30-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="53e30-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="53e30-111">Invoke</span></span>](#invoke) | <span data-ttu-id="53e30-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="53e30-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="53e30-113">Members</span><span class="sxs-lookup"><span data-stu-id="53e30-113">Members</span></span>

#### <span data-ttu-id="53e30-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="53e30-114">Invoke</span></span> 

<span data-ttu-id="53e30-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="53e30-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="53e30-116">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2AcceleratorKeyPressedEventArgs](icorewebview2acceleratorkeypressedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="53e30-116">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2AcceleratorKeyPressedEventArgs](icorewebview2acceleratorkeypressedeventargs.md) \* args)</span></span>

