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
ms.openlocfilehash: 89c080bffbcb416b6ca611df28d518b01ecb3448
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654385"
---
# <span data-ttu-id="dbe6d-104">インターフェイス ICoreWebView2PermissionRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="dbe6d-104">interface ICoreWebView2PermissionRequestedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="dbe6d-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dbe6d-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="dbe6d-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbe6d-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2PermissionRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="dbe6d-107">呼び出し元は、このインターフェイスを実装して、PermissionRequested されたイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="dbe6d-107">The caller implements this interface to receive the PermissionRequested event.</span></span>

## <span data-ttu-id="dbe6d-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="dbe6d-108">Summary</span></span>

 <span data-ttu-id="dbe6d-109">Members</span><span class="sxs-lookup"><span data-stu-id="dbe6d-109">Members</span></span>                        | <span data-ttu-id="dbe6d-110">説明</span><span class="sxs-lookup"><span data-stu-id="dbe6d-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="dbe6d-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="dbe6d-111">Invoke</span></span>](#invoke) | <span data-ttu-id="dbe6d-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="dbe6d-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="dbe6d-113">Members</span><span class="sxs-lookup"><span data-stu-id="dbe6d-113">Members</span></span>

#### <span data-ttu-id="dbe6d-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="dbe6d-114">Invoke</span></span> 

<span data-ttu-id="dbe6d-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="dbe6d-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="dbe6d-116">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2PermissionRequestedEventArgs](ICoreWebView2PermissionRequestedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="dbe6d-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2PermissionRequestedEventArgs](ICoreWebView2PermissionRequestedEventArgs.md) \* args)</span></span>

