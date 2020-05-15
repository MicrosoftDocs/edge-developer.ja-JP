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
ms.openlocfilehash: b44724f8e18e11374f88ed2cd22711f06f59f12d
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654405"
---
# <span data-ttu-id="59116-104">インターフェイス ICoreWebView2NewBrowserVersionAvailableEventHandler</span><span class="sxs-lookup"><span data-stu-id="59116-104">interface ICoreWebView2NewBrowserVersionAvailableEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="59116-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="59116-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="59116-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59116-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2NewBrowserVersionAvailableEventHandler
  : public IUnknown
```

<span data-ttu-id="59116-107">呼び出し元は、このインターフェイスを実装して、新しい参照サーバーの使用可能なイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="59116-107">The caller implements this interface to receive NewBrowserVersionAvailable events.</span></span>

## <span data-ttu-id="59116-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="59116-108">Summary</span></span>

 <span data-ttu-id="59116-109">Members</span><span class="sxs-lookup"><span data-stu-id="59116-109">Members</span></span>                        | <span data-ttu-id="59116-110">説明</span><span class="sxs-lookup"><span data-stu-id="59116-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="59116-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="59116-111">Invoke</span></span>](#invoke) | <span data-ttu-id="59116-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="59116-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="59116-113">新しいバージョン番号を取得するには、 [ICoreWebView2NewBrowserVersionAvailableEventArgs](ICoreWebView2NewBrowserVersionAvailableEventArgs.md)の get_NewVersion メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="59116-113">Use the get_NewVersion method of [ICoreWebView2NewBrowserVersionAvailableEventArgs](ICoreWebView2NewBrowserVersionAvailableEventArgs.md) to get the new version number.</span></span>

## <span data-ttu-id="59116-114">Members</span><span class="sxs-lookup"><span data-stu-id="59116-114">Members</span></span>

#### <span data-ttu-id="59116-115">Invoke</span><span class="sxs-lookup"><span data-stu-id="59116-115">Invoke</span></span> 

<span data-ttu-id="59116-116">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="59116-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="59116-117">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Environment](ICoreWebView2Environment.md) \* Webviewenvironment、[ICoreWebView2NewBrowserVersionAvailableEventArgs](ICoreWebView2NewBrowserVersionAvailableEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="59116-117">public HRESULT [Invoke](#invoke)([ICoreWebView2Environment](ICoreWebView2Environment.md) \* webviewEnvironment,[ICoreWebView2NewBrowserVersionAvailableEventArgs](ICoreWebView2NewBrowserVersionAvailableEventArgs.md) \* args)</span></span>

