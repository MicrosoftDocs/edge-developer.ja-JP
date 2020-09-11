---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2HttpHeadersCollectionIterator
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2HttpHeadersCollectionIterator。
ms.openlocfilehash: e7aad408372acbbd19ecab9d04312f21e2396e88
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012285"
---
# <span data-ttu-id="f1fbb-104">WebView2 クラス (CoreWebView2HttpHeadersCollectionIterator クラス)</span><span class="sxs-lookup"><span data-stu-id="f1fbb-104">Microsoft.Web.WebView2.Core.CoreWebView2HttpHeadersCollectionIterator class</span></span> 

<span data-ttu-id="f1fbb-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="f1fbb-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="f1fbb-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="f1fbb-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="f1fbb-107">HTTP ヘッダーのコレクションの Iterator。</span><span class="sxs-lookup"><span data-stu-id="f1fbb-107">Iterator for a collection of HTTP headers.</span></span>

## <span data-ttu-id="f1fbb-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="f1fbb-108">Summary</span></span>

 <span data-ttu-id="f1fbb-109">Members</span><span class="sxs-lookup"><span data-stu-id="f1fbb-109">Members</span></span>                        | <span data-ttu-id="f1fbb-110">説明</span><span class="sxs-lookup"><span data-stu-id="f1fbb-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f1fbb-111">HasCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="f1fbb-111">HasCurrentHeader</span></span>](#hascurrentheader) | <span data-ttu-id="f1fbb-112">反復子でヘッダーが不足していない場合は True です。</span><span class="sxs-lookup"><span data-stu-id="f1fbb-112">True when the iterator hasn't run out of headers.</span></span>
[<span data-ttu-id="f1fbb-113">MoveNext</span><span class="sxs-lookup"><span data-stu-id="f1fbb-113">MoveNext</span></span>](#movenext) | <span data-ttu-id="f1fbb-114">反復子をコレクション内の次の HTTP ヘッダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="f1fbb-114">Move the iterator to the next HTTP header in the collection.</span></span>

<span data-ttu-id="f1fbb-115">CoreWebView2HttpRequestHeaders と CoreWebView2HttpResponseHeaders を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1fbb-115">See CoreWebView2HttpRequestHeaders and CoreWebView2HttpResponseHeaders.</span></span>

## <span data-ttu-id="f1fbb-116">Members</span><span class="sxs-lookup"><span data-stu-id="f1fbb-116">Members</span></span>

#### <span data-ttu-id="f1fbb-117">HasCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="f1fbb-117">HasCurrentHeader</span></span> 

<span data-ttu-id="f1fbb-118">反復子でヘッダーが不足していない場合は True です。</span><span class="sxs-lookup"><span data-stu-id="f1fbb-118">True when the iterator hasn't run out of headers.</span></span>

> <span data-ttu-id="f1fbb-119">public bool [HasCurrentHeader](#hascurrentheader)</span><span class="sxs-lookup"><span data-stu-id="f1fbb-119">public bool [HasCurrentHeader](#hascurrentheader)</span></span>

<span data-ttu-id="f1fbb-120">反復子が反復処理を行っているコレクションが空である場合、または反復子がコレクションの末尾を超えている場合、この値は false になります。</span><span class="sxs-lookup"><span data-stu-id="f1fbb-120">If the collection over which the iterator is iterating is empty or if the iterator has gone past the end of the collection then this is false.</span></span>

#### <span data-ttu-id="f1fbb-121">MoveNext</span><span class="sxs-lookup"><span data-stu-id="f1fbb-121">MoveNext</span></span> 

<span data-ttu-id="f1fbb-122">反復子をコレクション内の次の HTTP ヘッダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="f1fbb-122">Move the iterator to the next HTTP header in the collection.</span></span>

> <span data-ttu-id="f1fbb-123">パブリックブール [MoveNext](#movenext)()</span><span class="sxs-lookup"><span data-stu-id="f1fbb-123">public bool [MoveNext](#movenext)()</span></span>

<span data-ttu-id="f1fbb-124">他の HTTP ヘッダーがない場合は、hasNext パラメーターが FALSE に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f1fbb-124">The hasNext parameter will be set to FALSE if there are no more HTTP headers.</span></span> <span data-ttu-id="f1fbb-125">この処理を実行すると、GetCurrentHeader メソッドは呼び出されたときに失敗します。</span><span class="sxs-lookup"><span data-stu-id="f1fbb-125">After this occurs the GetCurrentHeader method will fail if called.</span></span>

