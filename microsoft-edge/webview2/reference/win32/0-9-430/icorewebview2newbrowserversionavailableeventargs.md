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
ms.openlocfilehash: 3ac37f7d90fc03214381b991c8becae602bac738
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654403"
---
# <span data-ttu-id="5d93f-104">インターフェイス ICoreWebView2NewBrowserVersionAvailableEventArgs</span><span class="sxs-lookup"><span data-stu-id="5d93f-104">interface ICoreWebView2NewBrowserVersionAvailableEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="5d93f-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5d93f-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="5d93f-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d93f-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2NewBrowserVersionAvailableEventArgs
  : public IUnknown
```

<span data-ttu-id="5d93f-107">新しい参照サーバーの available イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="5d93f-107">Event args for the NewBrowserVersionAvailable event.</span></span>

## <span data-ttu-id="5d93f-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="5d93f-108">Summary</span></span>

 <span data-ttu-id="5d93f-109">Members</span><span class="sxs-lookup"><span data-stu-id="5d93f-109">Members</span></span>                        | <span data-ttu-id="5d93f-110">説明</span><span class="sxs-lookup"><span data-stu-id="5d93f-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5d93f-111">get_NewVersion</span><span class="sxs-lookup"><span data-stu-id="5d93f-111">get_NewVersion</span></span>](#get_newversion) | <span data-ttu-id="5d93f-112">現在の[ICoreWebView2Environment](ICoreWebView2Environment.md)のブラウザーのバージョン情報です。</span><span class="sxs-lookup"><span data-stu-id="5d93f-112">The browser version info of the current [ICoreWebView2Environment](ICoreWebView2Environment.md).</span></span>

## <span data-ttu-id="5d93f-113">Members</span><span class="sxs-lookup"><span data-stu-id="5d93f-113">Members</span></span>

#### <span data-ttu-id="5d93f-114">get_NewVersion</span><span class="sxs-lookup"><span data-stu-id="5d93f-114">get_NewVersion</span></span> 

<span data-ttu-id="5d93f-115">現在の[ICoreWebView2Environment](ICoreWebView2Environment.md)のブラウザーのバージョン情報です。</span><span class="sxs-lookup"><span data-stu-id="5d93f-115">The browser version info of the current [ICoreWebView2Environment](ICoreWebView2Environment.md).</span></span>

> <span data-ttu-id="5d93f-116">パブリック HRESULT [get_NewVersion](#get_newversion)(LPWSTR \* NewVersion)</span><span class="sxs-lookup"><span data-stu-id="5d93f-116">public HRESULT [get_NewVersion](#get_newversion)(LPWSTR \* newVersion)</span></span>

