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
# 0.8.355-インターフェイス IWebView2HttpHeadersCollectionIterator 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2HttpHeadersCollectionIterator
  : public IUnknown
```

HTTP ヘッダーのコレクションの Iterator。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[GetCurrentHeader](#getcurrentheader) | イテレータの現在の HTTP ヘッダーの名前と値を取得します。
[MoveNext](#movenext) | 反復子をコレクション内の次の HTTP ヘッダーに移動します。

[IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md)と[IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md)を参照してください。

## Members

#### GetCurrentHeader 

イテレータの現在の HTTP ヘッダーの名前と値を取得します。

> パブリック HRESULT [GetCurrentHeader](#getcurrentheader)(LPWSTR * NAME, LPWSTR * value)

このメソッドは、MoveNext セットへの最後の呼び出し has_next が FALSE になった場合に失敗します。

#### MoveNext 

反復子をコレクション内の次の HTTP ヘッダーに移動します。

> パブリック HRESULT [MoveNext](#movenext)(BOOL * has_next)

HTTP ヘッダーが追加されていない場合は、has_next パラメーターが FALSE に設定されます。 この処理を実行すると、GetCurrentHeader メソッドは呼び出されたときに失敗します。

