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
ms.openlocfilehash: 62daeaab702b431f787bc800ab79664fc183c4ce
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654160"
---
# <span data-ttu-id="55ad8-104">インターフェイス IWebView2WebView2</span><span class="sxs-lookup"><span data-stu-id="55ad8-104">interface IWebView2WebView2</span></span> 

> [!NOTE]
> <span data-ttu-id="55ad8-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="55ad8-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="55ad8-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55ad8-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebView2
  : public IUnknown
```

<span data-ttu-id="55ad8-107">プライマリ WebView オブジェクトによって実装されるその他の機能。</span><span class="sxs-lookup"><span data-stu-id="55ad8-107">Additional functionality implemented by the primary WebView object.</span></span>

## <span data-ttu-id="55ad8-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="55ad8-108">Summary</span></span>

 <span data-ttu-id="55ad8-109">Members</span><span class="sxs-lookup"><span data-stu-id="55ad8-109">Members</span></span>                        | <span data-ttu-id="55ad8-110">説明</span><span class="sxs-lookup"><span data-stu-id="55ad8-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="55ad8-111">Stop</span><span class="sxs-lookup"><span data-stu-id="55ad8-111">Stop</span></span>](#stop) | <span data-ttu-id="55ad8-112">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="55ad8-112">Stop all navigations and pending resource fetches.</span></span>

<span data-ttu-id="55ad8-113">このインターフェイスの QueryInterface は、 [IWebView2WebView](IWebView2WebView.md)を実装するオブジェクトから行うことができます。</span><span class="sxs-lookup"><span data-stu-id="55ad8-113">You can QueryInterface for this interface from the object that implements [IWebView2WebView](IWebView2WebView.md).</span></span> <span data-ttu-id="55ad8-114">詳細については、 [IWebView2WebView](IWebView2WebView.md)インターフェイスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="55ad8-114">See the [IWebView2WebView](IWebView2WebView.md) interface for more details.</span></span>

## <span data-ttu-id="55ad8-115">Members</span><span class="sxs-lookup"><span data-stu-id="55ad8-115">Members</span></span>

#### <span data-ttu-id="55ad8-116">Stop</span><span class="sxs-lookup"><span data-stu-id="55ad8-116">Stop</span></span> 

<span data-ttu-id="55ad8-117">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="55ad8-117">Stop all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="55ad8-118">パブリック HRESULT [Stop](#stop)()</span><span class="sxs-lookup"><span data-stu-id="55ad8-118">public HRESULT [Stop](#stop)()</span></span>

