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
# 0.9.430-インターフェイス ICoreWebView2HttpHeadersCollectionIterator 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2HttpHeadersCollectionIterator
  : public IUnknown
```

HTTP ヘッダーのコレクションの Iterator。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[GetCurrentHeader](#getcurrentheader) | イテレータの現在の HTTP ヘッダーの名前と値を取得します。
[get_HasCurrentHeader](#get_hascurrentheader) | 反復子でヘッダーが不足していない場合は True です。
[MoveNext](#movenext) | 反復子をコレクション内の次の HTTP ヘッダーに移動します。

[ICoreWebView2HttpRequestHeaders](ICoreWebView2HttpRequestHeaders.md)と[ICoreWebView2HttpResponseHeaders](ICoreWebView2HttpResponseHeaders.md)を参照してください。 

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

## Members

#### GetCurrentHeader 

イテレータの現在の HTTP ヘッダーの名前と値を取得します。

> パブリック HRESULT [GetCurrentHeader](#getcurrentheader)(LPWSTR * NAME, LPWSTR * value)

このメソッドは、MoveNext セットへの最後の呼び出し has_next が FALSE になった場合に失敗します。

#### get_HasCurrentHeader 

反復子でヘッダーが不足していない場合は True です。

> パブリック HRESULT [get_HasCurrentHeader](#get_hascurrentheader)(ブール * hascurrent)

反復子が反復処理を行っているコレクションが空である場合、または反復子がコレクションの末尾を超えている場合、この値は false になります。

#### MoveNext 

反復子をコレクション内の次の HTTP ヘッダーに移動します。

> パブリック HRESULT [MoveNext](#movenext)(BOOL * hasnext)

他の HTTP ヘッダーがない場合は、hasNext パラメーターが FALSE に設定されます。 この処理を実行すると、GetCurrentHeader メソッドは呼び出されたときに失敗します。

