---
description: WebView2 の次の予定について説明します。
title: Microsoft Edge WebView 2 のロードマップ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、Webview2、Webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ html
ms.openlocfilehash: 0f51b5cab32bdb9b9aa9b6baceef5fe5a17eea54
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398414"
---
# <a name="microsoft-edge-webview2-roadmap"></a>Microsoft Edge WebView2 ロードマップ  

> [!NOTE]
> 最終更新日: 2020 年 11 月  

WebView2 コントロールを使用すると、開発者は Web テクノロジをネイティブ アプリケーションに埋め込むできます。  次のページでは、WebView2 のロードマップの概要を示します。  

> [!NOTE]
> WebView2 は積極的な開発中であり、市場の変化や顧客からのフィードバックに基づいてロードマップが進化し続けているので、ここで説明する計画は網羅的ではなく、変更される可能性があります。  

ロードマップに関する懸念や質問がある場合は、フィードバック repo でフィードバック [を提供してください][GithubMicrosoftedgeWebviewfeedbackMain]。  

WebView2 チームは、今後の更新に向けた以下の主要な取り組みを計画しています。  

:::row:::
   :::column span="1":::
      WebView2 ランタイム インストーラー  
   :::column-end:::
   :::column span="2":::
      *   Q4 2020
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      修正済みバージョン  
   :::column-end:::
   :::column span="2":::
      *   Q4 2020  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      一般提供  
   :::column-end:::
   :::column span="2":::
      *   Win32 C/C++ \(Q4 2020\)  
      *   .NET \(Q4 2020\)  
      *   [WinUI 3.0][GithubMicrosoftUiXamlRoadmap]  
   :::column-end:::
:::row-end:::  

## <a name="webview2-runtime-and-installer"></a>WebView2 ランタイムとインストーラー  

[Evergreen 配布モデルを使用][ConceptDistributionEvergreenModel] すると、WebView2 ランタイムをユーザーのコンピューターにターゲットまたはチェーンインストールできます。  Evergreen WebView2 ランタイムとインストーラーが一般提供 \(GA\) に達しました。  

## <a name="fixed-version"></a>固定バージョン  

[固定バージョン配布モデルを使用][ConceptsDistributionFixedVersionModel] すると、ネイティブ アプリケーション内で Microsoft Edge バイナリをパッケージ化できます。  固定バージョンが一般提供 \(GA\) に達しました。  

## <a name="general-availability"></a>一般提供  

### <a name="win32-cc"></a>Win32 C/C++  

Win32 C/C++ SDK が GA に達しました。  

### <a name="net"></a>.NET  

.NET SDK が GA に達しました。 

### <a name="winui-30"></a>WinUI 3.0  

現在アルファ版の Win [UI 3.0][UwpToolkitsWinui3Index]を使用して、UWP アプリケーションの WebView2 にアクセスできます。  最新の状態を維持する方法の詳細については [、「Windows UI ライブラリのロードマップ」に移動します][GithubMicrosoftUiXamlRoadmap]。  

<!-- links -->  

[ConceptDistributionEvergreenModel]: ./concepts/distribution.md#evergreen-distribution-mode "Evergreen 配布モデル - WebView2 を使用したアプリケーションの|Microsoft Docs"  
[ConceptsDistributionFixedVersionModel]: ./concepts/distribution.md#fixed-version-distribution-mode "固定バージョン配布モデル - WebView2 を使用したアプリケーションの|Microsoft Docs"  

[UwpToolkitsWinui3Index]: /uwp/toolkits/winui3/index "Windows UI ライブラリ 3.0 プレビュー 1 (2020 年 5 月) |Microsoft Docs"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック - MicrosoftEdge/WebViewFeedback | GitHub"  

[GithubMicrosoftUiXamlRoadmap]: https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md "Windows UI ライブラリのロードマップ - microsoft/microsoft-ui-xaml |GitHub"  
