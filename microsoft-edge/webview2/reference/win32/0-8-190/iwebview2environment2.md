---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2Environment2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: e3177f159ff397ee9d4781936aa32f2715d4af02
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886088"
---
# 0.8.355-インターフェイス IWebView2Environment2 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

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

