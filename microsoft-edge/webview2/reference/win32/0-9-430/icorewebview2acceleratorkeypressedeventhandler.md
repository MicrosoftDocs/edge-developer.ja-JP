---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2AcceleratorKeyPressedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: a12d8f08d16597b2201404931c2cd9edea8b3dbc
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881187"
---
# <span data-ttu-id="fcbd8-104">0.9.430-インターフェイス ICoreWebView2AcceleratorKeyPressedEventHandler</span><span class="sxs-lookup"><span data-stu-id="fcbd8-104">0.9.430 - interface ICoreWebView2AcceleratorKeyPressedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="fcbd8-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fcbd8-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="fcbd8-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcbd8-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2AcceleratorKeyPressedEventHandler
  : public IUnknown
```

<span data-ttu-id="fcbd8-107">呼び出し元は、このインターフェイスを実装して AcceleratorKeyPressed イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="fcbd8-107">The caller implements this interface to receive the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="fcbd8-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="fcbd8-108">Summary</span></span>

 <span data-ttu-id="fcbd8-109">Members</span><span class="sxs-lookup"><span data-stu-id="fcbd8-109">Members</span></span>                        | <span data-ttu-id="fcbd8-110">説明</span><span class="sxs-lookup"><span data-stu-id="fcbd8-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="fcbd8-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="fcbd8-111">Invoke</span></span>](#invoke) | <span data-ttu-id="fcbd8-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fcbd8-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="fcbd8-113">Members</span><span class="sxs-lookup"><span data-stu-id="fcbd8-113">Members</span></span>

#### <span data-ttu-id="fcbd8-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="fcbd8-114">Invoke</span></span> 

<span data-ttu-id="fcbd8-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fcbd8-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="fcbd8-116">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Host](ICoreWebView2Host.md) \* sender,[ICoreWebView2AcceleratorKeyPressedEventArgs](ICoreWebView2AcceleratorKeyPressedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="fcbd8-116">public HRESULT [Invoke](#invoke)([ICoreWebView2Host](ICoreWebView2Host.md) \* sender,[ICoreWebView2AcceleratorKeyPressedEventArgs](ICoreWebView2AcceleratorKeyPressedEventArgs.md) \* args)</span></span>

