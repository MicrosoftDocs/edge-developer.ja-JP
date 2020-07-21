---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ExperimentalNewWindowRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalNewWindowRequestedEventArgs
ms.openlocfilehash: d18ccc91d16213cf0a915420b406b65823b3f9d9
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886452"
---
# インターフェイス ICoreWebView2ExperimentalNewWindowRequestedEventArgs 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalNewWindowRequestedEventArgs
  : public IUnknown
```

NewWindowRequested イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_WindowFeatures](#get_windowfeatures) | ウィンドウで指定されたウィンドウ機能。 [通話] を開きます。

このイベントは、webview 内のコンテンツが新しいウィンドウを開くように要求したときに発生します (ウィンドウを開く () など)。

## Members

#### get_WindowFeatures 

ウィンドウで指定されたウィンドウ機能。 [通話] を開きます。

> パブリック HRESULT [get_WindowFeatures](#get_windowfeatures)([ICoreWebView2ExperimentalWindowFeatures](icorewebview2experimentalwindowfeatures.md) * * windowfeatures)

これらの機能は、新しい webview ウィンドウの配置とサイズ変更のために考慮することができます。

