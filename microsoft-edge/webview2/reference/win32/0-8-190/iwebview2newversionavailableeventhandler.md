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
ms.openlocfilehash: a02a7ac3e31f959e80d5a3bdc41e39f653b9949c
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654501"
---
# <span data-ttu-id="559e1-104">インターフェイス IWebView2NewVersionAvailableEventHandler</span><span class="sxs-lookup"><span data-stu-id="559e1-104">interface IWebView2NewVersionAvailableEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="559e1-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="559e1-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="559e1-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559e1-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2NewVersionAvailableEventHandler
  : public IUnknown
```

<span data-ttu-id="559e1-107">呼び出し元は、このインターフェイスを実装して、新しいバージョンの利用可能なイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="559e1-107">The caller implements this interface to receive NewVersionAvailable events.</span></span>

## <span data-ttu-id="559e1-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="559e1-108">Summary</span></span>

 <span data-ttu-id="559e1-109">Members</span><span class="sxs-lookup"><span data-stu-id="559e1-109">Members</span></span>                        | <span data-ttu-id="559e1-110">説明</span><span class="sxs-lookup"><span data-stu-id="559e1-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="559e1-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="559e1-111">Invoke</span></span>](#invoke) | <span data-ttu-id="559e1-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="559e1-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="559e1-113">新しいバージョン番号を取得するには、 [IWebView2NewVersionAvailableEventArgs](IWebView2NewVersionAvailableEventArgs.md)の get_NewVersion メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="559e1-113">Use the get_NewVersion method of [IWebView2NewVersionAvailableEventArgs](IWebView2NewVersionAvailableEventArgs.md) to get the new version number.</span></span>

## <span data-ttu-id="559e1-114">Members</span><span class="sxs-lookup"><span data-stu-id="559e1-114">Members</span></span>

#### <span data-ttu-id="559e1-115">Invoke</span><span class="sxs-lookup"><span data-stu-id="559e1-115">Invoke</span></span> 

<span data-ttu-id="559e1-116">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="559e1-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="559e1-117">パブリック HRESULT[呼び出し](#invoke)([IWebView2Environment](IWebView2Environment.md) \* Webviewenvironment、[IWebView2NewVersionAvailableEventArgs](IWebView2NewVersionAvailableEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="559e1-117">public HRESULT [Invoke](#invoke)([IWebView2Environment](IWebView2Environment.md) \* webviewEnvironment,[IWebView2NewVersionAvailableEventArgs](IWebView2NewVersionAvailableEventArgs.md) \* args)</span></span>

