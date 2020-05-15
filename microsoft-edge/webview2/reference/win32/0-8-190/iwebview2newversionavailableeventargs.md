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
ms.openlocfilehash: 0314c796865d3d745b831d050498f59868e38e8f
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654502"
---
# <span data-ttu-id="11a69-104">インターフェイス IWebView2NewVersionAvailableEventArgs</span><span class="sxs-lookup"><span data-stu-id="11a69-104">interface IWebView2NewVersionAvailableEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="11a69-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="11a69-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="11a69-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11a69-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2NewVersionAvailableEventArgs
  : public IUnknown
```

<span data-ttu-id="11a69-107">NewVersionAvailable イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="11a69-107">Event args for the NewVersionAvailable event.</span></span>

## <span data-ttu-id="11a69-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="11a69-108">Summary</span></span>

 <span data-ttu-id="11a69-109">Members</span><span class="sxs-lookup"><span data-stu-id="11a69-109">Members</span></span>                        | <span data-ttu-id="11a69-110">説明</span><span class="sxs-lookup"><span data-stu-id="11a69-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="11a69-111">get_NewVersion</span><span class="sxs-lookup"><span data-stu-id="11a69-111">get_NewVersion</span></span>](#get_newversion) | <span data-ttu-id="11a69-112">現在の[IWebView2Environment](IWebView2Environment.md)のブラウザーのバージョン情報です。</span><span class="sxs-lookup"><span data-stu-id="11a69-112">The browser version info of the current [IWebView2Environment](IWebView2Environment.md).</span></span>

## <span data-ttu-id="11a69-113">Members</span><span class="sxs-lookup"><span data-stu-id="11a69-113">Members</span></span>

#### <span data-ttu-id="11a69-114">get_NewVersion</span><span class="sxs-lookup"><span data-stu-id="11a69-114">get_NewVersion</span></span> 

<span data-ttu-id="11a69-115">現在の[IWebView2Environment](IWebView2Environment.md)のブラウザーのバージョン情報です。</span><span class="sxs-lookup"><span data-stu-id="11a69-115">The browser version info of the current [IWebView2Environment](IWebView2Environment.md).</span></span>

> <span data-ttu-id="11a69-116">パブリック HRESULT [get_NewVersion](#get_newversion)(LPWSTR \* NewVersion)</span><span class="sxs-lookup"><span data-stu-id="11a69-116">public HRESULT [get_NewVersion](#get_newversion)(LPWSTR \* newVersion)</span></span>

