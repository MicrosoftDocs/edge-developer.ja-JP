---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 5d810b4261d139eb867240a060df76126e70ade4
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654569"
---
# <span data-ttu-id="0b110-104">インターフェイス ICoreWebView2MoveFocusRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="0b110-104">interface ICoreWebView2MoveFocusRequestedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="0b110-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0b110-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="0b110-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b110-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2MoveFocusRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="0b110-107">呼び出し元は、このメソッドを実装して MoveFocusRequested イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0b110-107">The caller implements this method to receive the MoveFocusRequested event.</span></span>

## <span data-ttu-id="0b110-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="0b110-108">Summary</span></span>

 <span data-ttu-id="0b110-109">Members</span><span class="sxs-lookup"><span data-stu-id="0b110-109">Members</span></span>                        | <span data-ttu-id="0b110-110">説明</span><span class="sxs-lookup"><span data-stu-id="0b110-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0b110-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="0b110-111">Invoke</span></span>](#invoke) | <span data-ttu-id="0b110-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0b110-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="0b110-113">Members</span><span class="sxs-lookup"><span data-stu-id="0b110-113">Members</span></span>

#### <span data-ttu-id="0b110-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="0b110-114">Invoke</span></span> 

<span data-ttu-id="0b110-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0b110-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="0b110-116">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Host](ICoreWebView2Host.md) \* sender,[ICoreWebView2MoveFocusRequestedEventArgs](ICoreWebView2MoveFocusRequestedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="0b110-116">public HRESULT [Invoke](#invoke)([ICoreWebView2Host](ICoreWebView2Host.md) \* sender,[ICoreWebView2MoveFocusRequestedEventArgs](ICoreWebView2MoveFocusRequestedEventArgs.md) \* args)</span></span>
