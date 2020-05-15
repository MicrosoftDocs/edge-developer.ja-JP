---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: d669b73edd8def1d8a44491705e0f80888da2b3f
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654367"
---
# <span data-ttu-id="a0a12-104">インターフェイス IWebView2PermissionRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="a0a12-104">interface IWebView2PermissionRequestedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="a0a12-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a0a12-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="a0a12-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0a12-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2PermissionRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="a0a12-107">呼び出し元は、このインターフェイスを実装して、PermissionRequested されたイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a0a12-107">The caller implements this interface to receive the PermissionRequested event.</span></span>

## <span data-ttu-id="a0a12-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="a0a12-108">Summary</span></span>

 <span data-ttu-id="a0a12-109">Members</span><span class="sxs-lookup"><span data-stu-id="a0a12-109">Members</span></span>                        | <span data-ttu-id="a0a12-110">説明</span><span class="sxs-lookup"><span data-stu-id="a0a12-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a0a12-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="a0a12-111">Invoke</span></span>](#invoke) | <span data-ttu-id="a0a12-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a0a12-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="a0a12-113">Members</span><span class="sxs-lookup"><span data-stu-id="a0a12-113">Members</span></span>

#### <span data-ttu-id="a0a12-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="a0a12-114">Invoke</span></span> 

<span data-ttu-id="a0a12-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a0a12-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="a0a12-116">パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview、[IWebView2PermissionRequestedEventArgs](IWebView2PermissionRequestedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="a0a12-116">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2PermissionRequestedEventArgs](IWebView2PermissionRequestedEventArgs.md) \* args)</span></span>

