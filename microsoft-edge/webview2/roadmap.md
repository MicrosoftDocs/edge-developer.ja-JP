---
description: WebView2 の次の予定について説明します。
title: WebView 2 Microsoft Edgeロードマップ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、Webview2、Webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ html
ms.openlocfilehash: 7b67e4a6844ead0f845667a70df8657745ece938
ms.sourcegitcommit: 8f37c931ecde4d58223113f7e3b42d37cc3df97f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2021
ms.locfileid: "11643421"
---
# <a name="microsoft-edge-webview2-roadmap"></a>Microsoft EdgeWebView2 ロードマップ  

> [!NOTE]
> 最終更新日: 2021 年 7 月  

WebView2 コントロールを使用すると、開発者は Web テクノロジをネイティブ アプリケーションに埋め込むできます。  次のページでは、WebView2 のロードマップの概要を示します。  

> [!NOTE]
> WebView2 は積極的な開発中であり、市場の変化や顧客からのフィードバックに基づいてロードマップが進化し続けているので、ここで説明する計画は網羅的ではなく、変更される可能性があります。  

ロードマップに関する懸念や質問がある場合は、フィードバック repo でフィードバック [を提供してください][GithubMicrosoftedgeWebviewfeedbackMain]。  

WebView2 チームは、今後の更新に向けた以下の主要な取り組みを計画しています。  

* UWP プレビュー
* MacOS プレビュー
* Xbox Preview
* HoloLensプレビュー

## <a name="webview2-runtime-and-installer"></a>WebView2 ランタイムとインストーラー  

[Evergreen 配布モデルを使用][ConceptDistributionEvergreenModel] すると、WebView2 ランタイムをユーザーのコンピューターにターゲットまたはチェーンインストールできます。  Evergreen WebView2 ランタイムとインストーラーが一般提供 \(GA\) に達しました。  

## <a name="fixed-version"></a>固定バージョン  

[固定バージョン配布モデルを使用][ConceptsDistributionFixedVersionModel]すると、ネイティブ アプリケーションMicrosoft Edgeバイナリをパッケージ化できます。  固定バージョンが一般提供 \(GA\) に達しました。  

## <a name="general-availability"></a>一般提供  

### <a name="win32-cc"></a>Win32 C/C++  

Win32 C/C++ SDK が GA に達しました。  

### <a name="net"></a>.NET  

.NET SDK が GA に達しました。 

### <a name="windows-ui-library-3"></a>WindowsUI ライブラリ 3

アプリケーションの WebView2 コントロールには、Windowsアプリ SDK を使用して UI ライブラリ[3 (WinUI3)][UwpToolkitsWinui3Index]をWindowsできます。 これは現在プレビュー中です。 詳細については、「App SDK ロードマップ[」Windowsを参照してください][WindowsAppSDK|::ref1::|]。

 
<!-- links -->  

[WindowsAppSDKRoadmap]: https://github.com/microsoft/WindowsAppSDK/blob/main/docs/roadmap.md "ロードマップ"
[ConceptDistributionEvergreenModel]: ./concepts/distribution.md#evergreen-distribution-mode "Evergreen 配布モデル - WebView2 を使用したアプリケーションの|Microsoft Docs"  
[ConceptsDistributionFixedVersionModel]: ./concepts/distribution.md#fixed-version-distribution-mode "固定バージョン配布モデル - WebView2 を使用したアプリケーションの|Microsoft Docs"  

[UwpToolkitsWinui3Index]: /uwp/toolkits/winui3/index "WindowsUI ライブラリ 3.0 プレビュー 1 (2020 年 5 月) |Microsoft Docs"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback | GitHub"  

[GithubMicrosoftUiXamlRoadmap]: https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md "WindowsUI ライブラリのロードマップ - microsoft/microsoft-ui-xaml |GitHub"  
