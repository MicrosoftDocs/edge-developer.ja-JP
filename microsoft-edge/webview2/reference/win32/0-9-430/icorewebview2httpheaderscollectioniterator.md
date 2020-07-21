---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2HttpHeadersCollectionIterator
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 640926481e99c6571c0cbf9c345efa56d97e3f66
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885598"
---
# <span data-ttu-id="56989-104">0.9.430-インターフェイス ICoreWebView2HttpHeadersCollectionIterator</span><span class="sxs-lookup"><span data-stu-id="56989-104">0.9.430 - interface ICoreWebView2HttpHeadersCollectionIterator</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2HttpHeadersCollectionIterator
  : public IUnknown
```

<span data-ttu-id="56989-105">HTTP ヘッダーのコレクションの Iterator。</span><span class="sxs-lookup"><span data-stu-id="56989-105">Iterator for a collection of HTTP headers.</span></span>

## <span data-ttu-id="56989-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="56989-106">Summary</span></span>

 <span data-ttu-id="56989-107">Members</span><span class="sxs-lookup"><span data-stu-id="56989-107">Members</span></span>                        | <span data-ttu-id="56989-108">説明</span><span class="sxs-lookup"><span data-stu-id="56989-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="56989-109">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="56989-109">GetCurrentHeader</span></span>](#getcurrentheader) | <span data-ttu-id="56989-110">イテレータの現在の HTTP ヘッダーの名前と値を取得します。</span><span class="sxs-lookup"><span data-stu-id="56989-110">Get the name and value of the current HTTP header of the iterator.</span></span>
[<span data-ttu-id="56989-111">get_HasCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="56989-111">get_HasCurrentHeader</span></span>](#get_hascurrentheader) | <span data-ttu-id="56989-112">反復子でヘッダーが不足していない場合は True です。</span><span class="sxs-lookup"><span data-stu-id="56989-112">True when the iterator hasn't run out of headers.</span></span>
[<span data-ttu-id="56989-113">MoveNext</span><span class="sxs-lookup"><span data-stu-id="56989-113">MoveNext</span></span>](#movenext) | <span data-ttu-id="56989-114">反復子をコレクション内の次の HTTP ヘッダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="56989-114">Move the iterator to the next HTTP header in the collection.</span></span>

<span data-ttu-id="56989-115">[ICoreWebView2HttpRequestHeaders](ICoreWebView2HttpRequestHeaders.md)と[ICoreWebView2HttpResponseHeaders](ICoreWebView2HttpResponseHeaders.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56989-115">See [ICoreWebView2HttpRequestHeaders](ICoreWebView2HttpRequestHeaders.md) and [ICoreWebView2HttpResponseHeaders](ICoreWebView2HttpResponseHeaders.md).</span></span> 

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

## <span data-ttu-id="56989-116">Members</span><span class="sxs-lookup"><span data-stu-id="56989-116">Members</span></span>

#### <span data-ttu-id="56989-117">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="56989-117">GetCurrentHeader</span></span> 

<span data-ttu-id="56989-118">イテレータの現在の HTTP ヘッダーの名前と値を取得します。</span><span class="sxs-lookup"><span data-stu-id="56989-118">Get the name and value of the current HTTP header of the iterator.</span></span>

> <span data-ttu-id="56989-119">パブリック HRESULT [GetCurrentHeader](#getcurrentheader)(LPWSTR \* NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="56989-119">public HRESULT [GetCurrentHeader](#getcurrentheader)(LPWSTR \* name,LPWSTR \* value)</span></span>

<span data-ttu-id="56989-120">このメソッドは、MoveNext セットへの最後の呼び出し has_next が FALSE になった場合に失敗します。</span><span class="sxs-lookup"><span data-stu-id="56989-120">This method will fail if the last call to MoveNext set has_next to FALSE.</span></span>

#### <span data-ttu-id="56989-121">get_HasCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="56989-121">get_HasCurrentHeader</span></span> 

<span data-ttu-id="56989-122">反復子でヘッダーが不足していない場合は True です。</span><span class="sxs-lookup"><span data-stu-id="56989-122">True when the iterator hasn't run out of headers.</span></span>

> <span data-ttu-id="56989-123">パブリック HRESULT [get_HasCurrentHeader](#get_hascurrentheader)(ブール \* hascurrent)</span><span class="sxs-lookup"><span data-stu-id="56989-123">public HRESULT [get_HasCurrentHeader](#get_hascurrentheader)(BOOL \* hasCurrent)</span></span>

<span data-ttu-id="56989-124">反復子が反復処理を行っているコレクションが空である場合、または反復子がコレクションの末尾を超えている場合、この値は false になります。</span><span class="sxs-lookup"><span data-stu-id="56989-124">If the collection over which the iterator is iterating is empty or if the iterator has gone past the end of the collection then this is false.</span></span>

#### <span data-ttu-id="56989-125">MoveNext</span><span class="sxs-lookup"><span data-stu-id="56989-125">MoveNext</span></span> 

<span data-ttu-id="56989-126">反復子をコレクション内の次の HTTP ヘッダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="56989-126">Move the iterator to the next HTTP header in the collection.</span></span>

> <span data-ttu-id="56989-127">パブリック HRESULT [MoveNext](#movenext)(BOOL \* hasnext)</span><span class="sxs-lookup"><span data-stu-id="56989-127">public HRESULT [MoveNext](#movenext)(BOOL \* hasNext)</span></span>

<span data-ttu-id="56989-128">他の HTTP ヘッダーがない場合は、hasNext パラメーターが FALSE に設定されます。</span><span class="sxs-lookup"><span data-stu-id="56989-128">The hasNext parameter will be set to FALSE if there are no more HTTP headers.</span></span> <span data-ttu-id="56989-129">この処理を実行すると、GetCurrentHeader メソッドは呼び出されたときに失敗します。</span><span class="sxs-lookup"><span data-stu-id="56989-129">After this occurs the GetCurrentHeader method will fail if called.</span></span>

