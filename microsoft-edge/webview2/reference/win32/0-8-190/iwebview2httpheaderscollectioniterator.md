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
ms.openlocfilehash: 4b9ad48d9b09343bad04d4acbe7c49750e76427d
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654525"
---
# <span data-ttu-id="5fea7-104">インターフェイス IWebView2HttpHeadersCollectionIterator</span><span class="sxs-lookup"><span data-stu-id="5fea7-104">interface IWebView2HttpHeadersCollectionIterator</span></span> 

> [!NOTE]
> <span data-ttu-id="5fea7-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5fea7-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="5fea7-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fea7-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2HttpHeadersCollectionIterator
  : public IUnknown
```

<span data-ttu-id="5fea7-107">HTTP ヘッダーのコレクションの Iterator。</span><span class="sxs-lookup"><span data-stu-id="5fea7-107">Iterator for a collection of HTTP headers.</span></span>

## <span data-ttu-id="5fea7-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="5fea7-108">Summary</span></span>

 <span data-ttu-id="5fea7-109">Members</span><span class="sxs-lookup"><span data-stu-id="5fea7-109">Members</span></span>                        | <span data-ttu-id="5fea7-110">説明</span><span class="sxs-lookup"><span data-stu-id="5fea7-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5fea7-111">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="5fea7-111">GetCurrentHeader</span></span>](#getcurrentheader) | <span data-ttu-id="5fea7-112">イテレータの現在の HTTP ヘッダーの名前と値を取得します。</span><span class="sxs-lookup"><span data-stu-id="5fea7-112">Get the name and value of the current HTTP header of the iterator.</span></span>
[<span data-ttu-id="5fea7-113">MoveNext</span><span class="sxs-lookup"><span data-stu-id="5fea7-113">MoveNext</span></span>](#movenext) | <span data-ttu-id="5fea7-114">反復子をコレクション内の次の HTTP ヘッダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="5fea7-114">Move the iterator to the next HTTP header in the collection.</span></span>

<span data-ttu-id="5fea7-115">[IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md)と[IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fea7-115">See [IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md) and [IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md).</span></span>

## <span data-ttu-id="5fea7-116">Members</span><span class="sxs-lookup"><span data-stu-id="5fea7-116">Members</span></span>

#### <span data-ttu-id="5fea7-117">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="5fea7-117">GetCurrentHeader</span></span> 

<span data-ttu-id="5fea7-118">イテレータの現在の HTTP ヘッダーの名前と値を取得します。</span><span class="sxs-lookup"><span data-stu-id="5fea7-118">Get the name and value of the current HTTP header of the iterator.</span></span>

> <span data-ttu-id="5fea7-119">パブリック HRESULT [GetCurrentHeader](#getcurrentheader)(LPWSTR \* NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="5fea7-119">public HRESULT [GetCurrentHeader](#getcurrentheader)(LPWSTR \* name,LPWSTR \* value)</span></span>

<span data-ttu-id="5fea7-120">このメソッドは、MoveNext セットへの最後の呼び出し has_next が FALSE になった場合に失敗します。</span><span class="sxs-lookup"><span data-stu-id="5fea7-120">This method will fail if the last call to MoveNext set has_next to FALSE.</span></span>

#### <span data-ttu-id="5fea7-121">MoveNext</span><span class="sxs-lookup"><span data-stu-id="5fea7-121">MoveNext</span></span> 

<span data-ttu-id="5fea7-122">反復子をコレクション内の次の HTTP ヘッダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="5fea7-122">Move the iterator to the next HTTP header in the collection.</span></span>

> <span data-ttu-id="5fea7-123">パブリック HRESULT [MoveNext](#movenext)(BOOL \* has_next)</span><span class="sxs-lookup"><span data-stu-id="5fea7-123">public HRESULT [MoveNext](#movenext)(BOOL \* has_next)</span></span>

<span data-ttu-id="5fea7-124">HTTP ヘッダーが追加されていない場合は、has_next パラメーターが FALSE に設定されます。</span><span class="sxs-lookup"><span data-stu-id="5fea7-124">The has_next parameter will be set to FALSE if there are no more HTTP headers.</span></span> <span data-ttu-id="5fea7-125">この処理を実行すると、GetCurrentHeader メソッドは呼び出されたときに失敗します。</span><span class="sxs-lookup"><span data-stu-id="5fea7-125">After this occurs the GetCurrentHeader method will fail if called.</span></span>

