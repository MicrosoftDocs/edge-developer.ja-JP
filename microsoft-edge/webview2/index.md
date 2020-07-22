---
description: Microsoft Edge WebView 2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Microsoft Edge WebView2 コントロール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、CoreWebView2、ICoreWebView2Host、browser control、edge html、Windows フォーム、WinForms、WPF、.NET
ms.openlocfilehash: ea3d25d16aa9e8c182d564c68615b9643c9993b4
ms.sourcegitcommit: a82aa5fc1ada35cd8274490fbff3c0a850785835
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "10888599"
---
# Microsoft Edge WebView2 の概要 (プレビュー)  

Microsoft Edge WebView2 コントロールを使うと、ネイティブアプリケーションで web 技術 (HTML、CSS、JavaScript \) を埋め込むことができます。  WebView2 コントロールは、 [Microsoft Edge (Chromium)][MicrosoftedgeinsiderMain]をレンダリングエンジンとして使用して、ネイティブアプリケーションで web コンテンツを表示します。  WebView2 を使用すると、ネイティブアプリケーションのさまざまな場所に web コードを埋め込むことができます。または、1つの WebView 内でネイティブアプリケーション全体をビルドすることもできます。  WebView2 アプリケーションの作成を開始する方法については、「使用[を開始する」を参照し](#getting-started)てください。  

:::image type="complex" source="./media/WebView2/whatwebview.png" alt-text="WebView とは" lightbox="./media/WebView2/whatwebview.png":::
   WebView とは  
:::image-end:::  

> [!NOTE]
> WebView2 Preview は、早期にプロトタイプを形成し、API の形成に役立つフィードバックを収集することを目的としています。  変更内容が壊れる可能性があるため、実稼働アプリではプレビューを使用しないでください。  詳細については、「 [Webview2Releasenotes]」を参照してください。  

## ハイブリッドアプリケーションのアプローチ  

開発者は、多くの場合、web アプリケーションまたはネイティブアプリケーションの構築を決定する必要があります。  意思決定は、リーチとパワーの間のトレードオフに対して行われます。  Web アプリケーションを使用すると広範なアクセスが可能になります。  Web 開発者は、すべての異なるプラットフォームで、ほとんどのコードを再利用することができます。  ただし、ネイティブアプリケーションは、ネイティブプラットフォーム全体の機能を利用します。  

:::image type="complex" source="./media/WebView2/webnative.png" alt-text="Web native" lightbox="./media/WebView2/webnative.png":::
   Web native  
:::image-end:::  

ハイブリッドアプリケーションを使用すると、開発者は両方のメリットを享受できます。  ハイブリッドアプリケーションの開発者は、web プラットフォームの ubiquity と強み、およびネイティブプラットフォームの機能と機能を最大限に活用できます。  

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
      Windows 7、8、10での一貫したユーザーエクスペリエンスのサポート。  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      **ネイティブ機能**  
      ネイティブ Api の完全なセットにアクセスします。  
   :::column-end:::
   :::column span="1":::
      **コード共有**  
      Web コードをコードベースに追加することで、複数のプラットフォーム間での再利用を高速化できます。  
   :::column-end:::
   :::column span="1":::
      **Microsoft サポート**  
      Microsoft は、WebView2 が GA としてリリースされたときにサポートを提供し、新しい機能要求を追加します。  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      **Evergreen 分布**  
      最新バージョンの Chromium を使用して、定期的なプラットフォームの更新とセキュリティ更新プログラムを利用します。  
   :::column-end:::
   :::column span="1":::
      **固定**\ (近日公開)  
      アプリケーションに Chromium ビットをパッケージ化することを選択します。  
   :::column-end:::
   :::column span="1":::
      **段階的導入**  
      アプリケーションに web コンポーネントを追加します。  
   :::column-end:::
:::row-end:::

## 開始するには  

WebView2 コントロールを使用してアプリケーションをビルドしてテストするには、 [Microsoft Edge (Chromium)][MicrosoftedgeinsiderDownload]と[WebView2 SDK][NugetPackagesMicrosoftWebWebView2]の両方をインストールする必要があります。  開始するには、次のいずれかのオプションを選択します。  

*   [Win32 C/C + + の概要][Webview2GettingstartedWin32]  
*   [WPF の概要][Webview2GettingstartedWpf]  
*   [WinForms の概要][Webview2GettingstartedWinforms]  
*   [WinUI3 の概要][Webview2GettingstartedWinui]  

[WebView2 サンプル][GithubMicrosoftedgeWebview2samples]リポジトリには、すべての WebView2 SDK 機能と API の使用パターンを示すサンプルが含まれています。  WebView2 SDK に追加された機能により、サンプルアプリケーションが更新されます。  

## サポートされているプラットフォーム  

開発者プレビューは、次のプログラミング環境で利用できます。  

*   Win32 C/c + +  
*   .NET Framework 4.6.2 以降  
*   .NET Core 3.0 以降  
*   [WinUI 3.0][UwpToolkitsWinui3]  

WebView2 アプリケーションは、次のバージョンの Windows で実行できます。  

*   Windows 10  
*   Windows 8.1  
*   Windows 8  
*   Windows 7  
*   Windows Server 2016  
*   Windows Server 2012  
*   Windows Server 2012R2  
*   Windows Server 2008 R2  

## 次のステップ  

WebView2 アプリケーションを作成して展開する方法の詳細については、概念的なドキュメントと使い方ガイドを参照してください。  

#### 概念  

*   [WebView2 SDK のバージョンについて][Webview2ConceptsVersioning]
*   [WebView2 を使用したアプリケーションの配布][Webview2ConceptsDistribution]  
*   [セキュリティで保護された WebView2 アプリケーションを開発するためのベストプラクティス][Webview2ConceptsSecurity]
*   [WebView2 アプリケーションでユーザーデータフォルダーを管理する][Webview2ConceptsUserdatafolder]
 
#### 使い方ガイド  

*   [WebView2 を使用してデバッグする方法][Webview2HowtoDebug]  
*   [Microsoft Edge ドライバーを使用した WebView2 の自動化とテスト][Webview2HowtoWebdriver]  

## WebView2 チームと連絡を取り合う  

フィードバックを共有して、より充実した WebView2 エクスペリエンスを構築できます。  機能のリクエストまたはバグレポートを送信するには、「 [WebView フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeddback]」を参照してください。  また、既知の問題を検索するのに適した場所です。  

> [!NOTE]
> プレビューでは、より優れた製品の構築に役立つデータが収集されます。  WebView2 データの収集をオフにするには、ブラウザーデータの収集に移動してオフにし `edge://settings/privacy` ます。  

<!-- links -->  

[Webview2ConceptsDistribution]: ./concepts/distribution.md "WebView2 を使用したアプリケーションの配布 |Microsoft ドキュメント"  
[Webview2ConceptsSecurity]: ./concepts/security.md "セキュリティで保護された WebView2 アプリケーションを開発するためのベストプラクティス |Microsoft ドキュメント"  
[Webview2ConceptsUserdatafolder]: ./concepts/userdatafolder.md "ユーザーデータフォルダーの管理 |Microsoft ドキュメント"  
[Webview2ConceptsVersioning]: ./concepts/versioning.md "WebView2 SDK のバージョンについて理解する |Microsoft ドキュメント"  
[Webview2GettingstartedWin32]: ./gettingstarted/win32.md "WebView2 の概要 (開発者用プレビュー) |Microsoft ドキュメント"   
[Webview2GettingstartedWinforms]: ./gettingstarted/winforms.md "Windows フォームアプリでの WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  
[Webview2GettingstartedWinui]: ./gettingstarted/winui.md "WinUI3 での WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  
[Webview2GettingstartedWpf]: ./gettingstarted/wpf.md "WPF での WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  
[Webview2HowtoDebug]: ./howto/debug.md "WebView2 を使用してデバッグする方法 |Microsoft ドキュメント"  
[Webview2HowtoWebdriver]: ./howto/webdriver.md "Microsoft Edge Driver での WebView2 の自動化とテスト |Microsoft ドキュメント"  
[Webview2Releasenotes]: ./releasenotes.md "Release NOTES for WebView2 SDK |Microsoft ドキュメント"  

[UwpToolkitsWinui3]: ./gettingstarted/winui.md "Windows UI ライブラリ3プレビュー 2 (2020 年7月) |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebviewfeddback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub" 

[MicrosoftedgeinsiderMain]: https://www.microsoftedgeinsider.com "Microsoft Edge Insider"  
[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider をダウンロードする"  

[NugetPackagesMicrosoftWebWebView2]: https://www.nuget.org/packages/Microsoft.Web.WebView2 "WebView2 |NuGet ギャラリー"  
