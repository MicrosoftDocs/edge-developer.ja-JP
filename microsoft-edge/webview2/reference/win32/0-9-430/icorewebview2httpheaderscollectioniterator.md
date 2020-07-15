---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2HttpHeadersCollectionIterator
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 29f4a09af459e80f8c299a66b24d061e79a96f92
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881026"
---
# <span data-ttu-id="39af0-104">0.9.430-インターフェイス ICoreWebView2HttpHeadersCollectionIterator</span><span class="sxs-lookup"><span data-stu-id="39af0-104">0.9.430 - interface ICoreWebView2HttpHeadersCollectionIterator</span></span> 

> [!NOTE]
> <span data-ttu-id="39af0-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="39af0-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="39af0-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39af0-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2HttpHeadersCollectionIterator
  : public IUnknown
```

<span data-ttu-id="39af0-107">HTTP ヘッダーのコレクションの Iterator。</span><span class="sxs-lookup"><span data-stu-id="39af0-107">Iterator for a collection of HTTP headers.</span></span>

## <span data-ttu-id="39af0-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="39af0-108">Summary</span></span>

 <span data-ttu-id="39af0-109">Members</span><span class="sxs-lookup"><span data-stu-id="39af0-109">Members</span></span>                        | <span data-ttu-id="39af0-110">説明</span><span class="sxs-lookup"><span data-stu-id="39af0-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="39af0-111">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="39af0-111">GetCurrentHeader</span></span>](#getcurrentheader) | <span data-ttu-id="39af0-112">イテレータの現在の HTTP ヘッダーの名前と値を取得します。</span><span class="sxs-lookup"><span data-stu-id="39af0-112">Get the name and value of the current HTTP header of the iterator.</span></span>
[<span data-ttu-id="39af0-113">get_HasCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="39af0-113">get_HasCurrentHeader</span></span>](#get_hascurrentheader) | <span data-ttu-id="39af0-114">反復子でヘッダーが不足していない場合は True です。</span><span class="sxs-lookup"><span data-stu-id="39af0-114">True when the iterator hasn't run out of headers.</span></span>
[<span data-ttu-id="39af0-115">MoveNext</span><span class="sxs-lookup"><span data-stu-id="39af0-115">MoveNext</span></span>](#movenext) | <span data-ttu-id="39af0-116">反復子をコレクション内の次の HTTP ヘッダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="39af0-116">Move the iterator to the next HTTP header in the collection.</span></span>

<span data-ttu-id="39af0-117">[ICoreWebView2HttpRequestHeaders](ICoreWebView2HttpRequestHeaders.md)と[ICoreWebView2HttpResponseHeaders](ICoreWebView2HttpResponseHeaders.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39af0-117">See [ICoreWebView2HttpRequestHeaders](ICoreWebView2HttpRequestHeaders.md) and [ICoreWebView2HttpResponseHeaders](ICoreWebView2HttpResponseHeaders.md).</span></span> 

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

## <span data-ttu-id="39af0-118">Members</span><span class="sxs-lookup"><span data-stu-id="39af0-118">Members</span></span>

#### <span data-ttu-id="39af0-119">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="39af0-119">GetCurrentHeader</span></span> 

<span data-ttu-id="39af0-120">イテレータの現在の HTTP ヘッダーの名前と値を取得します。</span><span class="sxs-lookup"><span data-stu-id="39af0-120">Get the name and value of the current HTTP header of the iterator.</span></span>

> <span data-ttu-id="39af0-121">パブリック HRESULT [GetCurrentHeader](#getcurrentheader)(LPWSTR \* NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="39af0-121">public HRESULT [GetCurrentHeader](#getcurrentheader)(LPWSTR \* name,LPWSTR \* value)</span></span>

<span data-ttu-id="39af0-122">このメソッドは、MoveNext セットへの最後の呼び出し has_next が FALSE になった場合に失敗します。</span><span class="sxs-lookup"><span data-stu-id="39af0-122">This method will fail if the last call to MoveNext set has_next to FALSE.</span></span>

#### <span data-ttu-id="39af0-123">get_HasCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="39af0-123">get_HasCurrentHeader</span></span> 

<span data-ttu-id="39af0-124">反復子でヘッダーが不足していない場合は True です。</span><span class="sxs-lookup"><span data-stu-id="39af0-124">True when the iterator hasn't run out of headers.</span></span>

> <span data-ttu-id="39af0-125">パブリック HRESULT [get_HasCurrentHeader](#get_hascurrentheader)(ブール \* hascurrent)</span><span class="sxs-lookup"><span data-stu-id="39af0-125">public HRESULT [get_HasCurrentHeader](#get_hascurrentheader)(BOOL \* hasCurrent)</span></span>

<span data-ttu-id="39af0-126">反復子が反復処理を行っているコレクションが空である場合、または反復子がコレクションの末尾を超えている場合、この値は false になります。</span><span class="sxs-lookup"><span data-stu-id="39af0-126">If the collection over which the iterator is iterating is empty or if the iterator has gone past the end of the collection then this is false.</span></span>

#### <span data-ttu-id="39af0-127">MoveNext</span><span class="sxs-lookup"><span data-stu-id="39af0-127">MoveNext</span></span> 

<span data-ttu-id="39af0-128">反復子をコレクション内の次の HTTP ヘッダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="39af0-128">Move the iterator to the next HTTP header in the collection.</span></span>

> <span data-ttu-id="39af0-129">パブリック HRESULT [MoveNext](#movenext)(BOOL \* hasnext)</span><span class="sxs-lookup"><span data-stu-id="39af0-129">public HRESULT [MoveNext](#movenext)(BOOL \* hasNext)</span></span>

<span data-ttu-id="39af0-130">他の HTTP ヘッダーがない場合は、hasNext パラメーターが FALSE に設定されます。</span><span class="sxs-lookup"><span data-stu-id="39af0-130">The hasNext parameter will be set to FALSE if there are no more HTTP headers.</span></span> <span data-ttu-id="39af0-131">この処理を実行すると、GetCurrentHeader メソッドは呼び出されたときに失敗します。</span><span class="sxs-lookup"><span data-stu-id="39af0-131">After this occurs the GetCurrentHeader method will fail if called.</span></span>

