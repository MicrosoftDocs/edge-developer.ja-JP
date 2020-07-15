---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2NewVersionAvailableEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: e8965ebe2e0434d83b4d6e8eabe74466adb7cec6
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878345"
---
# <span data-ttu-id="0d646-104">0.8.355-インターフェイス IWebView2NewVersionAvailableEventArgs</span><span class="sxs-lookup"><span data-stu-id="0d646-104">0.8.355 - interface IWebView2NewVersionAvailableEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="0d646-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0d646-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="0d646-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d646-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2NewVersionAvailableEventArgs
  : public IUnknown
```

<span data-ttu-id="0d646-107">NewVersionAvailable イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="0d646-107">Event args for the NewVersionAvailable event.</span></span>

## <span data-ttu-id="0d646-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="0d646-108">Summary</span></span>

 <span data-ttu-id="0d646-109">Members</span><span class="sxs-lookup"><span data-stu-id="0d646-109">Members</span></span>                        | <span data-ttu-id="0d646-110">説明</span><span class="sxs-lookup"><span data-stu-id="0d646-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0d646-111">get_NewVersion</span><span class="sxs-lookup"><span data-stu-id="0d646-111">get_NewVersion</span></span>](#get_newversion) | <span data-ttu-id="0d646-112">現在の[IWebView2Environment](IWebView2Environment.md)のブラウザーのバージョン情報です。</span><span class="sxs-lookup"><span data-stu-id="0d646-112">The browser version info of the current [IWebView2Environment](IWebView2Environment.md).</span></span>

## <span data-ttu-id="0d646-113">Members</span><span class="sxs-lookup"><span data-stu-id="0d646-113">Members</span></span>

#### <span data-ttu-id="0d646-114">get_NewVersion</span><span class="sxs-lookup"><span data-stu-id="0d646-114">get_NewVersion</span></span> 

<span data-ttu-id="0d646-115">現在の[IWebView2Environment](IWebView2Environment.md)のブラウザーのバージョン情報です。</span><span class="sxs-lookup"><span data-stu-id="0d646-115">The browser version info of the current [IWebView2Environment](IWebView2Environment.md).</span></span>

> <span data-ttu-id="0d646-116">パブリック HRESULT [get_NewVersion](#get_newversion)(LPWSTR \* NewVersion)</span><span class="sxs-lookup"><span data-stu-id="0d646-116">public HRESULT [get_NewVersion](#get_newversion)(LPWSTR \* newVersion)</span></span>

