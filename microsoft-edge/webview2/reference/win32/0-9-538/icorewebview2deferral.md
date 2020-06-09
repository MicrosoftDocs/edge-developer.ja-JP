---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: b5fcd04d702483778ef31549c2e7d989ebfe3689
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699007"
---
# インターフェイス ICoreWebView2Deferral 

```
interface ICoreWebView2Deferral
  : public IUnknown
```

このインターフェイスは、GetDeferral メソッドによる保留の取得をサポートするイベント引数で保留を完了するために使われます。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[Complete](#complete) | 関連付けられている遅延イベントを完了します。

## Members

#### Complete 

関連付けられている遅延イベントを完了します。

> パブリック HRESULT[完了](#complete)()

完了は、各繰延が行われるたびに1回のみ呼び出されます。

