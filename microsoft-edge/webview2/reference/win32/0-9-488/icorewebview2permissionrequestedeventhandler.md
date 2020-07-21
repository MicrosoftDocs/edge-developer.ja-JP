---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2PermissionRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: e8e318caf3195afc58e9d4c33e09841377cbeb64
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884807"
---
# <span data-ttu-id="e4be6-104">0.9.515-インターフェイス ICoreWebView2PermissionRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="e4be6-104">0.9.515 - interface ICoreWebView2PermissionRequestedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2PermissionRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="e4be6-105">呼び出し元は、このインターフェイスを実装して、PermissionRequested されたイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e4be6-105">The caller implements this interface to receive the PermissionRequested event.</span></span>

## <span data-ttu-id="e4be6-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="e4be6-106">Summary</span></span>

 <span data-ttu-id="e4be6-107">Members</span><span class="sxs-lookup"><span data-stu-id="e4be6-107">Members</span></span>                        | <span data-ttu-id="e4be6-108">説明</span><span class="sxs-lookup"><span data-stu-id="e4be6-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e4be6-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="e4be6-109">Invoke</span></span>](#invoke) | <span data-ttu-id="e4be6-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e4be6-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="e4be6-111">Members</span><span class="sxs-lookup"><span data-stu-id="e4be6-111">Members</span></span>

#### <span data-ttu-id="e4be6-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="e4be6-112">Invoke</span></span> 

<span data-ttu-id="e4be6-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e4be6-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="e4be6-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2PermissionRequestedEventArgs](icorewebview2permissionrequestedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="e4be6-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2PermissionRequestedEventArgs](icorewebview2permissionrequestedeventargs.md) \* args)</span></span>

