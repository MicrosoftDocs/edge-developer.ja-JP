---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: cc3cf67a03f81acc546ab17fded5d7430496033f
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654303"
---
# <span data-ttu-id="40f78-104">インターフェイス ICoreWebView2HttpHeadersCollectionIterator</span><span class="sxs-lookup"><span data-stu-id="40f78-104">interface ICoreWebView2HttpHeadersCollectionIterator</span></span> 

```
interface ICoreWebView2HttpHeadersCollectionIterator
  : public IUnknown
```

<span data-ttu-id="40f78-105">HTTP ヘッダーのコレクションの Iterator。</span><span class="sxs-lookup"><span data-stu-id="40f78-105">Iterator for a collection of HTTP headers.</span></span>

## <span data-ttu-id="40f78-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="40f78-106">Summary</span></span>

 <span data-ttu-id="40f78-107">Members</span><span class="sxs-lookup"><span data-stu-id="40f78-107">Members</span></span>                        | <span data-ttu-id="40f78-108">説明</span><span class="sxs-lookup"><span data-stu-id="40f78-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="40f78-109">get_HasCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="40f78-109">get_HasCurrentHeader</span></span>](#get_hascurrentheader) | <span data-ttu-id="40f78-110">反復子でヘッダーが不足していない場合は True です。</span><span class="sxs-lookup"><span data-stu-id="40f78-110">True when the iterator hasn't run out of headers.</span></span>
[<span data-ttu-id="40f78-111">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="40f78-111">GetCurrentHeader</span></span>](#getcurrentheader) | <span data-ttu-id="40f78-112">イテレータの現在の HTTP ヘッダーの名前と値を取得します。</span><span class="sxs-lookup"><span data-stu-id="40f78-112">Get the name and value of the current HTTP header of the iterator.</span></span>
[<span data-ttu-id="40f78-113">MoveNext</span><span class="sxs-lookup"><span data-stu-id="40f78-113">MoveNext</span></span>](#movenext) | <span data-ttu-id="40f78-114">反復子をコレクション内の次の HTTP ヘッダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="40f78-114">Move the iterator to the next HTTP header in the collection.</span></span>

<span data-ttu-id="40f78-115">[ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md)と[ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40f78-115">See [ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) and [ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md).</span></span> 
```cpp
std::wstring RequestHeadersToJsonString(ICoreWebView2HttpRequestHeaders* requestHeaders)
{
    wil::com_ptr<ICoreWebView2HttpHeadersCollectionIterator> iterator;
    CHECK_FAILURE(requestHeaders->GetIterator(&iterator));
    BOOL hasCurrent = FALSE;
    std::wstring result = L"[";

    while (SUCCEEDED(iterator->get_HasCurrentHeader(&hasCurrent)) && hasCurrent)
    {
        wil::unique_cotaskmem_string name;
        wil::unique_cotaskmem_string value;

        CHECK_FAILURE(iterator->GetCurrentHeader(&name, &value));
        result += L"{\"name\": " + EncodeQuote(name.get())
            + L", \"value\": " + EncodeQuote(value.get()) + L"}";

        BOOL hasNext = FALSE;
        CHECK_FAILURE(iterator->MoveNext(&hasNext));
        if (hasNext)
        {
            result += L", ";
        }
    }

    return result + L"]";
}
```

## <span data-ttu-id="40f78-116">Members</span><span class="sxs-lookup"><span data-stu-id="40f78-116">Members</span></span>

#### <span data-ttu-id="40f78-117">get_HasCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="40f78-117">get_HasCurrentHeader</span></span> 

<span data-ttu-id="40f78-118">反復子でヘッダーが不足していない場合は True です。</span><span class="sxs-lookup"><span data-stu-id="40f78-118">True when the iterator hasn't run out of headers.</span></span>

> <span data-ttu-id="40f78-119">パブリック HRESULT [get_HasCurrentHeader](#get_hascurrentheader)(ブール \* hascurrent)</span><span class="sxs-lookup"><span data-stu-id="40f78-119">public HRESULT [get_HasCurrentHeader](#get_hascurrentheader)(BOOL \* hasCurrent)</span></span>

<span data-ttu-id="40f78-120">反復子が反復処理を行っているコレクションが空である場合、または反復子がコレクションの末尾を超えている場合、この値は false になります。</span><span class="sxs-lookup"><span data-stu-id="40f78-120">If the collection over which the iterator is iterating is empty or if the iterator has gone past the end of the collection then this is false.</span></span>

#### <span data-ttu-id="40f78-121">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="40f78-121">GetCurrentHeader</span></span> 

<span data-ttu-id="40f78-122">イテレータの現在の HTTP ヘッダーの名前と値を取得します。</span><span class="sxs-lookup"><span data-stu-id="40f78-122">Get the name and value of the current HTTP header of the iterator.</span></span>

> <span data-ttu-id="40f78-123">パブリック HRESULT [GetCurrentHeader](#getcurrentheader)(LPWSTR \* NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="40f78-123">public HRESULT [GetCurrentHeader](#getcurrentheader)(LPWSTR \* name, LPWSTR \* value)</span></span>

<span data-ttu-id="40f78-124">このメソッドは、MoveNext セットへの最後の呼び出し has_next が FALSE になった場合に失敗します。</span><span class="sxs-lookup"><span data-stu-id="40f78-124">This method will fail if the last call to MoveNext set has_next to FALSE.</span></span>

#### <span data-ttu-id="40f78-125">MoveNext</span><span class="sxs-lookup"><span data-stu-id="40f78-125">MoveNext</span></span> 

<span data-ttu-id="40f78-126">反復子をコレクション内の次の HTTP ヘッダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="40f78-126">Move the iterator to the next HTTP header in the collection.</span></span>

> <span data-ttu-id="40f78-127">パブリック HRESULT [MoveNext](#movenext)(BOOL \* hasnext)</span><span class="sxs-lookup"><span data-stu-id="40f78-127">public HRESULT [MoveNext](#movenext)(BOOL \* hasNext)</span></span>

<span data-ttu-id="40f78-128">他の HTTP ヘッダーがない場合は、hasNext パラメーターが FALSE に設定されます。</span><span class="sxs-lookup"><span data-stu-id="40f78-128">The hasNext parameter will be set to FALSE if there are no more HTTP headers.</span></span> <span data-ttu-id="40f78-129">この処理を実行すると、GetCurrentHeader メソッドは呼び出されたときに失敗します。</span><span class="sxs-lookup"><span data-stu-id="40f78-129">After this occurs the GetCurrentHeader method will fail if called.</span></span>

