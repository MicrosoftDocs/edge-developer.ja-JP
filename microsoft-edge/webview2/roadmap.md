---
description: WebView2 の次の項目について
title: Microsoft Edge WebView のロードマップ2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: dcc9a92ee4db4c41a024aee565dfafe22b185e2a
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698177"
---
# Microsoft Edge WebView2 のロードマップ

##### 最終更新日: 2020 年5月

WebView2 コントロールを使うと、開発者はネイティブアプリケーションに web テクノロジを埋め込むことができます。 このドキュメントでは、WebView2 の予想されるロードマップについて説明します。 

> [!NOTE]
> WebView2 は [アクティブな開発] の下にあり、ロードマップは市場の変更や顧客のフィードバックに基づいて進化し続けますので、ここに記載されているプランは網羅的ではなく、変更される可能性があることに注意してください。 

ロードマップについて懸念事項や質問がある場合は、フィードバックの[リポジトリ](https://github.com/MicrosoftEdge/WebViewFeedback)にフィードバックをお寄せください。

WebView2 チームは、いくつかの主な取り組みを行っています。

1.  WebView2 Runtime Installer (2020 年4四半期)
2.  修正済みバージョン (2020 年4四半期)
3.  Ga 
    *   Win32 C/c + + (2020 年4四半期)
    *   .NET (Q4 年4四半期 2020)
    *   [WinUI 3.0](https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md)

## WebView2 Runtime & Installer

WebView2 [Evergreen](./concepts/distribution.md#microsoft-edge-webview2-runtime)配布モデルでは、ユーザーのコンピューターに WebView2 ランタイムをターゲット設定またはチェーンすることができます。 WebView2 のランタイムとインストーラーのプレビューは、2020年第4四半期2020および GA として提供される予定です。

## 修正されたバージョン

WebView2[固定](./concepts/distribution.md#roadmap)配布モデルでは、ネイティブアプリケーション内に Microsoft Edge バイナリをパッケージ化することができます。 現時点では、エンジニアリング作業は、第3四半期2020および GA 四半期の2020年の終わりまでに、プレビューを表示する方法となっています。

## Ga 

### Win32 C/c + +

Win32 C/c + + SDK の GA は、WebView2 Runtime および installer の GA の直後である、2020年4四半期に GA となります。

### .NET

.NET SDK は、Win32 C/C + + SDK をラップします。 .NET SDK は、2020年4四半期に Win32 C/c + + GA の後、まもなく GA となります。

### WinUI 3.0

WebView2 は、現在 alpha の[WIN UI 3.0](/uwp/toolkits/winui3/)経由で UWP アプリケーションに移動できます。 [WINDOWS UI ライブラリのロードマップ](https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md)をチェックアウトして、最新の状態に維持します。  
