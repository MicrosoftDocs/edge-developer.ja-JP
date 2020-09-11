---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2PermissionRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2PermissionRequestedEventHandler
ms.openlocfilehash: 5d906c85cf36ccf270d9af342e329e1d969ff494
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012347"
---
# <span data-ttu-id="b17e8-104">インターフェイス ICoreWebView2PermissionRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="b17e8-104">interface ICoreWebView2PermissionRequestedEventHandler</span></span> 

```
interface ICoreWebView2PermissionRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="b17e8-105">呼び出し元は、このインターフェイスを実装して、PermissionRequested されたイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b17e8-105">The caller implements this interface to receive the PermissionRequested event.</span></span>

## <span data-ttu-id="b17e8-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="b17e8-106">Summary</span></span>

 <span data-ttu-id="b17e8-107">Members</span><span class="sxs-lookup"><span data-stu-id="b17e8-107">Members</span></span>                        | <span data-ttu-id="b17e8-108">説明</span><span class="sxs-lookup"><span data-stu-id="b17e8-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b17e8-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="b17e8-109">Invoke</span></span>](#invoke) | <span data-ttu-id="b17e8-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b17e8-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="b17e8-111">Members</span><span class="sxs-lookup"><span data-stu-id="b17e8-111">Members</span></span>

#### <span data-ttu-id="b17e8-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="b17e8-112">Invoke</span></span> 

<span data-ttu-id="b17e8-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b17e8-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="b17e8-114">パブリック HRESULT [呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2PermissionRequestedEventArgs](icorewebview2permissionrequestedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="b17e8-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2PermissionRequestedEventArgs](icorewebview2permissionrequestedeventargs.md) \* args)</span></span>

