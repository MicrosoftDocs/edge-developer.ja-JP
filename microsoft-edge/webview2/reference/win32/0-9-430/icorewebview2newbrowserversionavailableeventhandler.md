---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2NewBrowserVersionAvailableEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 04859c0a22e8571a4fe8015a089c9b7d708c1dd3
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884877"
---
# <span data-ttu-id="2b1fd-104">0.9.430-インターフェイス ICoreWebView2NewBrowserVersionAvailableEventHandler</span><span class="sxs-lookup"><span data-stu-id="2b1fd-104">0.9.430 - interface ICoreWebView2NewBrowserVersionAvailableEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2NewBrowserVersionAvailableEventHandler
  : public IUnknown
```

<span data-ttu-id="2b1fd-105">呼び出し元は、このインターフェイスを実装して、新しい参照サーバーの使用可能なイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2b1fd-105">The caller implements this interface to receive NewBrowserVersionAvailable events.</span></span>

## <span data-ttu-id="2b1fd-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="2b1fd-106">Summary</span></span>

 <span data-ttu-id="2b1fd-107">Members</span><span class="sxs-lookup"><span data-stu-id="2b1fd-107">Members</span></span>                        | <span data-ttu-id="2b1fd-108">説明</span><span class="sxs-lookup"><span data-stu-id="2b1fd-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2b1fd-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="2b1fd-109">Invoke</span></span>](#invoke) | <span data-ttu-id="2b1fd-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2b1fd-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="2b1fd-111">新しいバージョン番号を取得するには、 [ICoreWebView2NewBrowserVersionAvailableEventArgs](ICoreWebView2NewBrowserVersionAvailableEventArgs.md)の get_NewVersion メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2b1fd-111">Use the get_NewVersion method of [ICoreWebView2NewBrowserVersionAvailableEventArgs](ICoreWebView2NewBrowserVersionAvailableEventArgs.md) to get the new version number.</span></span>

## <span data-ttu-id="2b1fd-112">Members</span><span class="sxs-lookup"><span data-stu-id="2b1fd-112">Members</span></span>

#### <span data-ttu-id="2b1fd-113">Invoke</span><span class="sxs-lookup"><span data-stu-id="2b1fd-113">Invoke</span></span> 

<span data-ttu-id="2b1fd-114">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2b1fd-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="2b1fd-115">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Environment](ICoreWebView2Environment.md) \* Webviewenvironment、[ICoreWebView2NewBrowserVersionAvailableEventArgs](ICoreWebView2NewBrowserVersionAvailableEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="2b1fd-115">public HRESULT [Invoke](#invoke)([ICoreWebView2Environment](ICoreWebView2Environment.md) \* webviewEnvironment,[ICoreWebView2NewBrowserVersionAvailableEventArgs](ICoreWebView2NewBrowserVersionAvailableEventArgs.md) \* args)</span></span>

