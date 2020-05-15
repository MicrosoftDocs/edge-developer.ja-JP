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
ms.openlocfilehash: 91c4e7885526def5de6fd1910a4a6f06c6a6953a
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654258"
---
# インターフェイス ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler 

> [!NOTE]
> これは、プレリリース SDK バージョン0.9.488 に同梱されている実験的な API です。

```
interface ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
  : public IUnknown
```

呼び出し元はこのインターフェイスを実装して、CreateCoreWebView2CompositionController 経由で作成された CoreWebView2Controller を受け取ります。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[Invoke](#invoke) | 呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。

## Members

#### Invoke 

呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。

> パブリック HRESULT[呼び出し](#invoke)(hresult Result、 [ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) * webView)

