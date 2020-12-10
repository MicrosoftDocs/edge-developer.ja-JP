---
description: Microsoft Edge WebView2 control を使用して Win32、.NET、UWP アプリケーションの web コンテンツをホストする
title: Microsoft Edge WebView2 control
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、CoreWebView2、ICoreWebView2Host、ブラウザー コントロール、edge html、Windows フォーム、WinForms、WPF、.NET、WinUI、Project Reunion
ms.openlocfilehash: 02d17b05364f02f26a4917b65ac497156be02b2e
ms.sourcegitcommit: fab44f7e183a3c4f12bf925512fc62d84a4d6edc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "11182368"
---
# Microsoft Edge WebView2 の概要  

Microsoft Edge WebView2 controlを使うと、ネイティブ アプリケーションで web テクノロジ (HTML、CSS、そしてJavaScript \) を埋め込むことができます。  WebView2 controlは、[Microsoft Edge (Chromium)][MicrosoftedgeinsiderMain] をレンダリングエンジンとして使用し、ネイティブ アプリケーションで web コンテンツを表示します。  WebView2 を使用すると、ネイティブ アプリケーションのさまざまな場所に web コードを埋め込むことができます。または、1つの WebView 内でネイティブ アプリケーション全体を作成することもできます。  WebView2 アプリケーションの作成を始める方法については、[はじめに](#getting-started)を参照してください。  

:::image type="complex" source="./media/WebView2/whatwebview.png" alt-text="WebView とは" lightbox="./media/WebView2/whatwebview.png":::
   WebView とは  
:::image-end:::  

## ハイブリッド アプリケーションのアプローチ  

開発者は多くの場合、web アプリケーションまたはネイティブ アプリケーションの構築にするかを決定する必要があります。  意思決定は、リーチとパワーの間のトレードオフにかかっています。  Web アプリケーションは広範囲に対応しています。  Web 開発者は、すべての異なるプラットフォームで、ほとんどのコードを再利用することができます。  ただし、ネイティブ アプリケーションは、ネイティブプラットフォーム全体の機能を利用します。  

:::image type="complex" source="./media/WebView2/webnative.png" alt-text="Web native" lightbox="./media/WebView2/webnative.png":::
   Web native  
:::image-end:::  

ハイブリッド アプリケーションを使用すると、開発者は両方の長所を享受できます。  ハイブリッド アプリケーションの開発者は、web プラットフォームの偏在と強み、およびネイティブ プラットフォームの機能とパワーを最大限に活用できます。  

## WebView2 の利点  

:::image type="complex" source="./media/WebView2/webviewreasons.png" alt-text="WebView の理由" lightbox="./media/WebView2/webviewreasons.png":::
   WebView の理由  
:::image-end:::  

:::row:::
   :::column span="1":::
      **Web エコシステム \ & のスキルセット**  
      Web エコシステム内に存在する web プラットフォーム、ライブラリ、ツール、人材をすべて活用できます。  
   :::column-end:::
   :::column span="1":::
      **急速な革新**  
      Web 開発により、迅速な展開とイテレーションが可能になります。  
   :::column-end:::
   :::column span="1":::
      **Windows 7、8、10のサポート**  
      Windows 7、8、10での一貫したユーザー エクスペリエンスのサポート。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **ネイティブ機能**  
      ネイティブ APIs のフル セットにアクセスします。  
   :::column-end:::
   :::column span="1":::
      **コード共有**  
      Web コードをコードベースに追加することで、複数のプラットフォーム間での再利用の向上が可能になります。  
   :::column-end:::
   :::column span="1":::
      **Microsoft サポート**  
      Microsoft は、WebView2 が GA としてリリースされたときにサポートを提供し、新しい機能の要望を追加します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Evergreen 分布**  
      最新バージョンの Chromium を使用して、定期的なプラットフォームの更新とセキュリティ更新プログラムを利用します。  
   :::column-end:::
   :::column span="1":::
      **修正済み** \ (近日公開\)  
      アプリケーションに Chromium ビットをパッケージ化することを選択します。  
   :::column-end:::
   :::column span="1":::
      **段階的導入**  
      アプリケーションに web コンポーネントをひとつづつ追加します。  
   :::column-end:::
:::row-end:::  

## 開始するには  

WebView2 コントロールを使用してアプリケーションを作成しテストするには、 [Microsoft Edge (Chromium)][MicrosoftedgeinsiderDownload] と [WebView2 SDK][NugetPackagesMicrosoftWebWebView2] の両方をインストールする必要があります。  開始するには、次のいずれかのオプションから一つ選択します。  

*   [Win32 C/C + + の概要][Webview2GettingstartedWin32]  
*   [WPF の概要][Webview2GettingstartedWpf]  
*   [WinForms の概要][Webview2GettingstartedWinforms]  
*   [WinUI3 の概要][Webview2GettingstartedWinui]  

[WebView2 サンプル][GithubMicrosoftedgeWebview2samples]リポジトリには、すべての WebView2 SDK 機能と API の使用パターンを示すサンプルが含まれています。  WebView2 SDK に追加された機能により、サンプル アプリケーションが更新されます。  

## サポートされているプラットフォーム  

一般提供 \ (GA\) またはプレビュー版は、次のプログラミング環境で利用できます。  

*   Win32 C/c + + \ (GA \)
*   .NET Framework 4.6.2 以降
*   .NET Core 3.1 以降
*   .NET 5
*   [WinUI 3.0][UwpToolkitsWinui3] \ (プレビュー \)

WebView2 アプリケーションは、次のバージョンの Windows で実行できます。  

*   Windows 10  
*   Windows 8.1  
*   Windows 7 \ * \ *  
*   Windows Server 2019  
*   Windows Server 2016  
*   Windows Server 2012  
*   Windows Server 2012 R2  
*   Windows Server 2008 R2 \ * \ *  

> [!IMPORTANT]
> \ * \ * WebView2 support for Windows 7 および Windows Server 2008 R2 のサポートサイクルは、Microsoft Edge と同じです。  詳細については、[Microsoft Edge でサポートされているオペレーティングシステム][DeployedgeMicrosoftEdgeSupportedOS]を参照してください。  

## 次のステップ  

WebView2 アプリケーションを作成して展開する方法の詳細については、概念のドキュメントと使い方ガイドを参照してください。  

#### 概念  

*   [WebView2 SDK バージョンの概要][Webview2ConceptsVersioning]
*   [WebView2 を使用したアプリケーションの配布][Webview2ConceptsDistribution]  
*   [安全な WebView2 アプリケーションを開発するためのベスト プラクティス][Webview2ConceptsSecurity]
*   [WebView2 アプリケーションでユーザー データ フォルダーを管理する][Webview2ConceptsUserdatafolder]
 
#### 使い方ガイド  

*   [WebView2 を使用してデバッグする方法][Webview2HowtoDebug]  
*   [Microsoft Edge Driverを使用した WebView2 の自動化とテスト][Webview2HowtoWebdriver]


## Microsoft Edge WebView チームと連絡を取る  

[!INCLUDE [contact WebView team note](./includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2ConceptsDistribution]: ./concepts/distribution.md "WebView2 を使用したアプリケーションの配布 |Microsoft Docs"  
[Webview2ConceptsSecurity]: ./concepts/security.md "セキュリティで保護された WebView2 アプリケーションを開発するためのベストプラクティス |Microsoft Docs"  
[Webview2ConceptsUserdatafolder]: ./concepts/userdatafolder.md "ユーザーデータフォルダーの管理 |Microsoft Docs"  
[Webview2ConceptsVersioning]: ./concepts/versioning.md "WebView2 SDK のバージョンについて理解する |Microsoft Docs"  
[Webview2GettingstartedWin32]: ./gettingstarted/win32.md "WebView2 の概要 |Microsoft Docs"  
[Webview2GettingstartedWinforms]: ./gettingstarted/winforms.md "Windows フォームアプリでの WebView2 の概要 (プレビュー) |Microsoft Docs"  
[Webview2GettingstartedWinui]: ./gettingstarted/winui.md "WinUI3 での WebView2 の概要 (プレビュー) |Microsoft Docs"  
[Webview2GettingstartedWpf]: ./gettingstarted/wpf.md "WPF での WebView2 の概要 (プレビュー) |Microsoft Docs"  
[Webview2HowtoDebug]: ./howto/debug.md "WebView2 を使用してデバッグする方法 |Microsoft Docs"  
[Webview2HowtoWebdriver]: ./howto/webdriver.md "Microsoft Edge Driver での WebView2 の自動化とテスト |Microsoft Docs"  
[Webview2Releasenotes]: ./releasenotes.md "WebView2 SDK のリリースノート |Microsoft Docs"  

[UwpToolkitsWinui3]: /uwp/toolkits/winui3/index "Windows UI ライブラリ 3 プレビュー 2 (2020 年7 月) |Microsoft Docs"  

[DeployedgeMicrosoftEdgeSupportedOS]: /deployedge/microsoft-edge-supported-operating-systems "Microsoft Edge でサポートされているオペレーティングシステム |Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  
[GithubMicrosoftedgeWebviewfeddback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback | GitHub" 

[MicrosoftedgeinsiderMain]: https://www.microsoftedgeinsider.com "Microsoft Edge Insider"  
[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider をダウンロードする"  

[NugetPackagesMicrosoftWebWebView2]: https://www.nuget.org/packages/Microsoft.Web.WebView2 "Microsoft.Web.WebView2 | NuGet Gallery"  
