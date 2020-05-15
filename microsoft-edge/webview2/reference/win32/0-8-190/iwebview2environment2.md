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
ms.openlocfilehash: 00b19d1174a5d5ac643a04038ecdd60c82211194
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654420"
---
# インターフェイス IWebView2Environment2 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface IWebView2Environment2
  : public IWebView2Environment
```

環境オブジェクトによって実装される追加機能。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_BrowserVersionInfo](#get_browserversioninfo) | IWebView2Environment が安定していない場合は、チャネル名を含む現在の[IWebView2Environment](IWebView2Environment.md)のブラウザーバージョン情報。

詳細については、 [IWebView2Environment](IWebView2Environment.md)インターフェイスを参照してください。 このインターフェイスの QueryInterface は、 [IWebView2Environment](IWebView2Environment.md)を実装するオブジェクトから行うことができます。

## Members

#### get_BrowserVersionInfo 

IWebView2Environment が安定していない場合は、チャネル名を含む現在の[IWebView2Environment](IWebView2Environment.md)のブラウザーバージョン情報。

> パブリック HRESULT [get_BrowserVersionInfo](#get_browserversioninfo)(LPWSTR * versionInfo)

これは、GetWebView2BrowserVersionInfo API の形式と一致します。 チャネル名は、"ベータ"、"dev"、"カナリア" のようになります。

```cpp
        wil::unique_cotaskmem_string version_info;
        m_webViewEnvironment->get_BrowserVersionInfo(&version_info);
        MessageBox(
            m_mainWindow, version_info.get(), L"Browser Version Info After WebView Creation",
            MB_OK);
```

