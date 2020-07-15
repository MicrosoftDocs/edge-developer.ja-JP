---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2NewBrowserVersionAvailableEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: f59b5acac510b66eae0e1ada51e28b6dd9363ca8
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877855"
---
# <span data-ttu-id="601d1-104">0.9.430-インターフェイス ICoreWebView2NewBrowserVersionAvailableEventArgs</span><span class="sxs-lookup"><span data-stu-id="601d1-104">0.9.430 - interface ICoreWebView2NewBrowserVersionAvailableEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="601d1-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="601d1-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="601d1-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="601d1-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2NewBrowserVersionAvailableEventArgs
  : public IUnknown
```

<span data-ttu-id="601d1-107">新しい参照サーバーの available イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="601d1-107">Event args for the NewBrowserVersionAvailable event.</span></span>

## <span data-ttu-id="601d1-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="601d1-108">Summary</span></span>

 <span data-ttu-id="601d1-109">Members</span><span class="sxs-lookup"><span data-stu-id="601d1-109">Members</span></span>                        | <span data-ttu-id="601d1-110">説明</span><span class="sxs-lookup"><span data-stu-id="601d1-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="601d1-111">get_NewVersion</span><span class="sxs-lookup"><span data-stu-id="601d1-111">get_NewVersion</span></span>](#get_newversion) | <span data-ttu-id="601d1-112">現在の[ICoreWebView2Environment](ICoreWebView2Environment.md)のブラウザーのバージョン情報です。</span><span class="sxs-lookup"><span data-stu-id="601d1-112">The browser version info of the current [ICoreWebView2Environment](ICoreWebView2Environment.md).</span></span>

## <span data-ttu-id="601d1-113">Members</span><span class="sxs-lookup"><span data-stu-id="601d1-113">Members</span></span>

#### <span data-ttu-id="601d1-114">get_NewVersion</span><span class="sxs-lookup"><span data-stu-id="601d1-114">get_NewVersion</span></span> 

<span data-ttu-id="601d1-115">現在の[ICoreWebView2Environment](ICoreWebView2Environment.md)のブラウザーのバージョン情報です。</span><span class="sxs-lookup"><span data-stu-id="601d1-115">The browser version info of the current [ICoreWebView2Environment](ICoreWebView2Environment.md).</span></span>

> <span data-ttu-id="601d1-116">パブリック HRESULT [get_NewVersion](#get_newversion)(LPWSTR \* NewVersion)</span><span class="sxs-lookup"><span data-stu-id="601d1-116">public HRESULT [get_NewVersion](#get_newversion)(LPWSTR \* newVersion)</span></span>

