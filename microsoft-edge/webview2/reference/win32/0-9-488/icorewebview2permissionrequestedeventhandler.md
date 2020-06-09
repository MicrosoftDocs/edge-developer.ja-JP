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
ms.openlocfilehash: 4ba3a5acd293b67947622ef4a409319164a23d35
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698030"
---
# <span data-ttu-id="6ecdc-104">インターフェイス ICoreWebView2PermissionRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="6ecdc-104">interface ICoreWebView2PermissionRequestedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="6ecdc-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6ecdc-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="6ecdc-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ecdc-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2PermissionRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="6ecdc-107">呼び出し元は、このインターフェイスを実装して、PermissionRequested されたイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6ecdc-107">The caller implements this interface to receive the PermissionRequested event.</span></span>

## <span data-ttu-id="6ecdc-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="6ecdc-108">Summary</span></span>

 <span data-ttu-id="6ecdc-109">Members</span><span class="sxs-lookup"><span data-stu-id="6ecdc-109">Members</span></span>                        | <span data-ttu-id="6ecdc-110">説明</span><span class="sxs-lookup"><span data-stu-id="6ecdc-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6ecdc-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="6ecdc-111">Invoke</span></span>](#invoke) | <span data-ttu-id="6ecdc-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6ecdc-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="6ecdc-113">Members</span><span class="sxs-lookup"><span data-stu-id="6ecdc-113">Members</span></span>

#### <span data-ttu-id="6ecdc-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="6ecdc-114">Invoke</span></span> 

<span data-ttu-id="6ecdc-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6ecdc-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="6ecdc-116">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2PermissionRequestedEventArgs](icorewebview2permissionrequestedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="6ecdc-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2PermissionRequestedEventArgs](icorewebview2permissionrequestedeventargs.md) \* args)</span></span>

