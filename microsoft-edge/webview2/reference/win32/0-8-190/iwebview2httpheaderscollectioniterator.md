---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2HttpHeadersCollectionIterator
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: dbcc5b10ce1973df61554f3f27174f600fb25280
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885982"
---
# <span data-ttu-id="8808f-104">0.8.355-インターフェイス IWebView2HttpHeadersCollectionIterator</span><span class="sxs-lookup"><span data-stu-id="8808f-104">0.8.355 - interface IWebView2HttpHeadersCollectionIterator</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2HttpHeadersCollectionIterator
  : public IUnknown
```

<span data-ttu-id="8808f-105">HTTP ヘッダーのコレクションの Iterator。</span><span class="sxs-lookup"><span data-stu-id="8808f-105">Iterator for a collection of HTTP headers.</span></span>

## <span data-ttu-id="8808f-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="8808f-106">Summary</span></span>

 <span data-ttu-id="8808f-107">Members</span><span class="sxs-lookup"><span data-stu-id="8808f-107">Members</span></span>                        | <span data-ttu-id="8808f-108">説明</span><span class="sxs-lookup"><span data-stu-id="8808f-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8808f-109">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="8808f-109">GetCurrentHeader</span></span>](#getcurrentheader) | <span data-ttu-id="8808f-110">イテレータの現在の HTTP ヘッダーの名前と値を取得します。</span><span class="sxs-lookup"><span data-stu-id="8808f-110">Get the name and value of the current HTTP header of the iterator.</span></span>
[<span data-ttu-id="8808f-111">MoveNext</span><span class="sxs-lookup"><span data-stu-id="8808f-111">MoveNext</span></span>](#movenext) | <span data-ttu-id="8808f-112">反復子をコレクション内の次の HTTP ヘッダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="8808f-112">Move the iterator to the next HTTP header in the collection.</span></span>

<span data-ttu-id="8808f-113">[IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md)と[IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8808f-113">See [IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md) and [IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md).</span></span>

## <span data-ttu-id="8808f-114">Members</span><span class="sxs-lookup"><span data-stu-id="8808f-114">Members</span></span>

#### <span data-ttu-id="8808f-115">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="8808f-115">GetCurrentHeader</span></span> 

<span data-ttu-id="8808f-116">イテレータの現在の HTTP ヘッダーの名前と値を取得します。</span><span class="sxs-lookup"><span data-stu-id="8808f-116">Get the name and value of the current HTTP header of the iterator.</span></span>

> <span data-ttu-id="8808f-117">パブリック HRESULT [GetCurrentHeader](#getcurrentheader)(LPWSTR \* NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="8808f-117">public HRESULT [GetCurrentHeader](#getcurrentheader)(LPWSTR \* name,LPWSTR \* value)</span></span>

<span data-ttu-id="8808f-118">このメソッドは、MoveNext セットへの最後の呼び出し has_next が FALSE になった場合に失敗します。</span><span class="sxs-lookup"><span data-stu-id="8808f-118">This method will fail if the last call to MoveNext set has_next to FALSE.</span></span>

#### <span data-ttu-id="8808f-119">MoveNext</span><span class="sxs-lookup"><span data-stu-id="8808f-119">MoveNext</span></span> 

<span data-ttu-id="8808f-120">反復子をコレクション内の次の HTTP ヘッダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="8808f-120">Move the iterator to the next HTTP header in the collection.</span></span>

> <span data-ttu-id="8808f-121">パブリック HRESULT [MoveNext](#movenext)(BOOL \* has_next)</span><span class="sxs-lookup"><span data-stu-id="8808f-121">public HRESULT [MoveNext](#movenext)(BOOL \* has_next)</span></span>

<span data-ttu-id="8808f-122">HTTP ヘッダーが追加されていない場合は、has_next パラメーターが FALSE に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8808f-122">The has_next parameter will be set to FALSE if there are no more HTTP headers.</span></span> <span data-ttu-id="8808f-123">この処理を実行すると、GetCurrentHeader メソッドは呼び出されたときに失敗します。</span><span class="sxs-lookup"><span data-stu-id="8808f-123">After this occurs the GetCurrentHeader method will fail if called.</span></span>

