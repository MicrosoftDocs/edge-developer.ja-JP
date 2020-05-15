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
ms.openlocfilehash: ec48b8659a5778b7f552695ee511b5af61d38d9c
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654358"
---
# <span data-ttu-id="2f6b4-104">インターフェイス ICoreWebView2PermissionRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="2f6b4-104">interface ICoreWebView2PermissionRequestedEventHandler</span></span> 

```
interface ICoreWebView2PermissionRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="2f6b4-105">呼び出し元は、このインターフェイスを実装して、PermissionRequested されたイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-105">The caller implements this interface to receive the PermissionRequested event.</span></span>

## <span data-ttu-id="2f6b4-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="2f6b4-106">Summary</span></span>

 <span data-ttu-id="2f6b4-107">Members</span><span class="sxs-lookup"><span data-stu-id="2f6b4-107">Members</span></span>                        | <span data-ttu-id="2f6b4-108">説明</span><span class="sxs-lookup"><span data-stu-id="2f6b4-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2f6b4-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="2f6b4-109">Invoke</span></span>](#invoke) | <span data-ttu-id="2f6b4-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="2f6b4-111">Members</span><span class="sxs-lookup"><span data-stu-id="2f6b4-111">Members</span></span>

#### <span data-ttu-id="2f6b4-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="2f6b4-112">Invoke</span></span> 

<span data-ttu-id="2f6b4-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2f6b4-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="2f6b4-114">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2PermissionRequestedEventArgs](icorewebview2permissionrequestedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="2f6b4-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2PermissionRequestedEventArgs](icorewebview2permissionrequestedeventargs.md) \* args)</span></span>

