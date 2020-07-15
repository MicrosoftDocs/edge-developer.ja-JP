---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2HttpHeadersCollectionIterator
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 06efdaaa851d9426eb12887ae88e94e2aa6680f0
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880557"
---
# <span data-ttu-id="9fb26-104">0.9.515-インターフェイス ICoreWebView2HttpHeadersCollectionIterator</span><span class="sxs-lookup"><span data-stu-id="9fb26-104">0.9.515 - interface ICoreWebView2HttpHeadersCollectionIterator</span></span> 

> [!NOTE]
> <span data-ttu-id="9fb26-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9fb26-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="9fb26-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fb26-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2HttpHeadersCollectionIterator
  : public IUnknown
```

<span data-ttu-id="9fb26-107">HTTP ヘッダーのコレクションの Iterator。</span><span class="sxs-lookup"><span data-stu-id="9fb26-107">Iterator for a collection of HTTP headers.</span></span>

## <span data-ttu-id="9fb26-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="9fb26-108">Summary</span></span>

 <span data-ttu-id="9fb26-109">Members</span><span class="sxs-lookup"><span data-stu-id="9fb26-109">Members</span></span>                        | <span data-ttu-id="9fb26-110">説明</span><span class="sxs-lookup"><span data-stu-id="9fb26-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9fb26-111">get_HasCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="9fb26-111">get_HasCurrentHeader</span></span>](#get_hascurrentheader) | <span data-ttu-id="9fb26-112">反復子でヘッダーが不足していない場合は True です。</span><span class="sxs-lookup"><span data-stu-id="9fb26-112">True when the iterator hasn't run out of headers.</span></span>
[<span data-ttu-id="9fb26-113">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="9fb26-113">GetCurrentHeader</span></span>](#getcurrentheader) | <span data-ttu-id="9fb26-114">イテレータの現在の HTTP ヘッダーの名前と値を取得します。</span><span class="sxs-lookup"><span data-stu-id="9fb26-114">Get the name and value of the current HTTP header of the iterator.</span></span>
[<span data-ttu-id="9fb26-115">MoveNext</span><span class="sxs-lookup"><span data-stu-id="9fb26-115">MoveNext</span></span>](#movenext) | <span data-ttu-id="9fb26-116">反復子をコレクション内の次の HTTP ヘッダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="9fb26-116">Move the iterator to the next HTTP header in the collection.</span></span>

<span data-ttu-id="9fb26-117">[ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md)と[ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fb26-117">See [ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) and [ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md).</span></span> 
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

## <span data-ttu-id="9fb26-118">Members</span><span class="sxs-lookup"><span data-stu-id="9fb26-118">Members</span></span>

#### <span data-ttu-id="9fb26-119">get_HasCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="9fb26-119">get_HasCurrentHeader</span></span> 

<span data-ttu-id="9fb26-120">反復子でヘッダーが不足していない場合は True です。</span><span class="sxs-lookup"><span data-stu-id="9fb26-120">True when the iterator hasn't run out of headers.</span></span>

> <span data-ttu-id="9fb26-121">パブリック HRESULT [get_HasCurrentHeader](#get_hascurrentheader)(ブール \* hascurrent)</span><span class="sxs-lookup"><span data-stu-id="9fb26-121">public HRESULT [get_HasCurrentHeader](#get_hascurrentheader)(BOOL \* hasCurrent)</span></span>

<span data-ttu-id="9fb26-122">反復子が反復処理を行っているコレクションが空である場合、または反復子がコレクションの末尾を超えている場合、この値は false になります。</span><span class="sxs-lookup"><span data-stu-id="9fb26-122">If the collection over which the iterator is iterating is empty or if the iterator has gone past the end of the collection then this is false.</span></span>

#### <span data-ttu-id="9fb26-123">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="9fb26-123">GetCurrentHeader</span></span> 

<span data-ttu-id="9fb26-124">イテレータの現在の HTTP ヘッダーの名前と値を取得します。</span><span class="sxs-lookup"><span data-stu-id="9fb26-124">Get the name and value of the current HTTP header of the iterator.</span></span>

> <span data-ttu-id="9fb26-125">パブリック HRESULT [GetCurrentHeader](#getcurrentheader)(LPWSTR \* NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="9fb26-125">public HRESULT [GetCurrentHeader](#getcurrentheader)(LPWSTR \* name, LPWSTR \* value)</span></span>

<span data-ttu-id="9fb26-126">このメソッドは、MoveNext セットへの最後の呼び出し has_next が FALSE になった場合に失敗します。</span><span class="sxs-lookup"><span data-stu-id="9fb26-126">This method will fail if the last call to MoveNext set has_next to FALSE.</span></span>

#### <span data-ttu-id="9fb26-127">MoveNext</span><span class="sxs-lookup"><span data-stu-id="9fb26-127">MoveNext</span></span> 

<span data-ttu-id="9fb26-128">反復子をコレクション内の次の HTTP ヘッダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="9fb26-128">Move the iterator to the next HTTP header in the collection.</span></span>

> <span data-ttu-id="9fb26-129">パブリック HRESULT [MoveNext](#movenext)(BOOL \* hasnext)</span><span class="sxs-lookup"><span data-stu-id="9fb26-129">public HRESULT [MoveNext](#movenext)(BOOL \* hasNext)</span></span>

<span data-ttu-id="9fb26-130">他の HTTP ヘッダーがない場合は、hasNext パラメーターが FALSE に設定されます。</span><span class="sxs-lookup"><span data-stu-id="9fb26-130">The hasNext parameter will be set to FALSE if there are no more HTTP headers.</span></span> <span data-ttu-id="9fb26-131">この処理を実行すると、GetCurrentHeader メソッドは呼び出されたときに失敗します。</span><span class="sxs-lookup"><span data-stu-id="9fb26-131">After this occurs the GetCurrentHeader method will fail if called.</span></span>

