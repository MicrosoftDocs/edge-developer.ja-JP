---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 64dac6c56576b618cbdc84da2c8fcbcd0e41028f
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884737"
---
# <span data-ttu-id="35941-104">0.8.355-インターフェイス IWebView2WebView2</span><span class="sxs-lookup"><span data-stu-id="35941-104">0.8.355 - interface IWebView2WebView2</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2WebView2
  : public IUnknown
```

<span data-ttu-id="35941-105">プライマリ WebView オブジェクトによって実装されるその他の機能。</span><span class="sxs-lookup"><span data-stu-id="35941-105">Additional functionality implemented by the primary WebView object.</span></span>

## <span data-ttu-id="35941-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="35941-106">Summary</span></span>

 <span data-ttu-id="35941-107">Members</span><span class="sxs-lookup"><span data-stu-id="35941-107">Members</span></span>                        | <span data-ttu-id="35941-108">説明</span><span class="sxs-lookup"><span data-stu-id="35941-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="35941-109">Stop</span><span class="sxs-lookup"><span data-stu-id="35941-109">Stop</span></span>](#stop) | <span data-ttu-id="35941-110">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="35941-110">Stop all navigations and pending resource fetches.</span></span>

<span data-ttu-id="35941-111">このインターフェイスの QueryInterface は、 [IWebView2WebView](IWebView2WebView.md)を実装するオブジェクトから行うことができます。</span><span class="sxs-lookup"><span data-stu-id="35941-111">You can QueryInterface for this interface from the object that implements [IWebView2WebView](IWebView2WebView.md).</span></span> <span data-ttu-id="35941-112">詳細については、 [IWebView2WebView](IWebView2WebView.md)インターフェイスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="35941-112">See the [IWebView2WebView](IWebView2WebView.md) interface for more details.</span></span>

## <span data-ttu-id="35941-113">Members</span><span class="sxs-lookup"><span data-stu-id="35941-113">Members</span></span>

#### <span data-ttu-id="35941-114">Stop</span><span class="sxs-lookup"><span data-stu-id="35941-114">Stop</span></span> 

<span data-ttu-id="35941-115">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="35941-115">Stop all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="35941-116">パブリック HRESULT [Stop](#stop)()</span><span class="sxs-lookup"><span data-stu-id="35941-116">public HRESULT [Stop](#stop)()</span></span>

