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
ms.openlocfilehash: ac2f17c621dc6ad5093bacac685e01688a663cb1
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697953"
---
# <span data-ttu-id="0076e-104">インターフェイス ICoreWebView2MoveFocusRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="0076e-104">interface ICoreWebView2MoveFocusRequestedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="0076e-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0076e-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="0076e-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0076e-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2MoveFocusRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="0076e-107">呼び出し元は、このメソッドを実装して MoveFocusRequested イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0076e-107">The caller implements this method to receive the MoveFocusRequested event.</span></span>

## <span data-ttu-id="0076e-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="0076e-108">Summary</span></span>

 <span data-ttu-id="0076e-109">Members</span><span class="sxs-lookup"><span data-stu-id="0076e-109">Members</span></span>                        | <span data-ttu-id="0076e-110">説明</span><span class="sxs-lookup"><span data-stu-id="0076e-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0076e-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="0076e-111">Invoke</span></span>](#invoke) | <span data-ttu-id="0076e-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0076e-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="0076e-113">Members</span><span class="sxs-lookup"><span data-stu-id="0076e-113">Members</span></span>

#### <span data-ttu-id="0076e-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="0076e-114">Invoke</span></span> 

<span data-ttu-id="0076e-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0076e-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="0076e-116">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2MoveFocusRequestedEventArgs](icorewebview2movefocusrequestedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="0076e-116">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2MoveFocusRequestedEventArgs](icorewebview2movefocusrequestedeventargs.md) \* args)</span></span>

