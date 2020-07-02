---
description: WebView2 の次の項目について
title: Microsoft Edge WebView のロードマップ2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/22/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 151eca3da5909b9d418451617b6bf09319752c55
ms.sourcegitcommit: 288bd2a1bec418a84d1f0bda013c1913886bd269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "10844412"
---
# Microsoft Edge WebView2 のロードマップ  

##### 最終更新日: 2020 年5月  

WebView2 コントロールを使うと、開発者はネイティブアプリケーションに web テクノロジを埋め込むことができます。  次のページは、WebView2 の予想されるロードマップの概要を示しています。  

> [!NOTE]
> WebView2 は [アクティブな開発] の下にあります。また、ロードマップは市場の変化や顧客のフィードバックに基づいて進化し続けているため、ここで説明されているプランは完全ではなく、変更される可能性があることに注意してください。  

ロードマップについて懸念事項や質問がある場合は、フィードバックの[リポジトリ][GithubMicrosoftedgeWebviewfeedbackMain]にフィードバックをお寄せください。  

WebView2 チームは今後の更新プログラムに対して、次の主な取り組みを計画しています。  

:::row:::
   :::column span="1":::
      WebView2 Runtime Installer  
   :::column-end:::
   :::column span="2":::
      *   2020年第4四半期
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      修正されたバージョン  
   :::column-end:::
   :::column span="2":::
      *   2020年第4四半期  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      Ga  
   :::column-end:::
   :::column span="2":::
      *   Win32 C/c + + (2020 年4四半期 \)  
      *   .NET \ (Q4 年4四半期 2020 \)  
      *   [WinUI 3.0][GithubMicrosoftUiXamlRoadmap]  
   :::column-end:::
:::row-end:::  

## WebView2 のランタイムとインストーラー  

[Evergreen 配布モデル][ConceptDistributionEvergreenModel]では、ユーザーのコンピューターに WebView2 ランタイムをターゲットまたは連鎖してインストールすることができます。  WebView2 のランタイムとインストーラーのプレビューは、2020年第4四半期2020および GA として提供される予定です。  

## 修正されたバージョン  

[固定バージョンの配布モデル][ConceptsDistributionFixedVersionModel]では、ネイティブアプリケーション内に Microsoft Edge バイナリをパッケージ化することができます。  現時点では、エンジニアリング作業は、第3四半期2020および GA 四半期の2020年の終わりまでに、プレビューを表示する方法となっています。  

## Ga  

### Win32 C/c + +  

Win32 C/c + + SDK の GA は、WebView2 Runtime および installer の GA の直後である、2020年4四半期に GA となります。  

### .NET  

.NET SDK は、Win32 C/C + + SDK をラップします。  .NET SDK は、2020年4四半期に Win32 C/c + + GA の後、まもなく GA となります。  

### WinUI 3.0  

WebView2 には、現在の alpha の[UI 3.0][UwpToolkitsWinui3Index]を使って UWP アプリケーションでアクセスできます。  最新の状態に保つ方法について詳しくは、「 [WINDOWS UI ライブラリのロードマップ][GithubMicrosoftUiXamlRoadmap]」をご覧ください。  

<!-- links -->  

[ConceptDistributionEvergreenModel]: ./concepts/distribution.md#evergreen-distribution-mode "Evergreen 配布モデル-WebView2 を使用したアプリケーションの配布 |Microsoft ドキュメント"  
[ConceptsDistributionFixedVersionModel]: ./concepts/distribution.md#fixed-version-distribution-mode "WebView2 を使用したアプリケーションの配布モデルの固定バージョン |Microsoft ドキュメント"  

[UwpToolkitsWinui3Index]: /uwp/toolkits/winui3/index "Windows UI ライブラリ3.0 プレビュー 1 (2020 年5月) |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  

[GithubMicrosoftUiXamlRoadmap]: https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md "Windows UI ライブラリのロードマップ-microsoft/microsoft-UI-xaml |GitHub"  
