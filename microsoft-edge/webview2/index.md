---
description: Microsoft Edge WebView2 コントロールを使用して Win32、.NET、UWP アプリで Web コンテンツをホストする
title: Microsoft Edge WebView2 コントロール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、CoreWebView2、ICoreWebView2Host、ブラウザー コントロール、edge html、Windows フォーム、WinForms、WPF、.NET、WinUI、Project Reunion
ms.openlocfilehash: 64c835d0122a1c72e610efed2c060f7921a8e2b5
ms.sourcegitcommit: 5ae09b1ad6cd576c9fec12538b23cd849861f2b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2021
ms.locfileid: "11627986"
---
# <a name="introduction-to-microsoft-edge-webview2"></a>Microsoft Edge WebView2 の概要  

Microsoft Edge WebView2 を使用すると、Web テクノロジ \(HTML、CSS、JavaScript\) をユーザーのネイティブ アプリに埋め込みできます。  WebView2 コントロールは、[Microsoft Edge (Chromium)][MicrosoftedgeinsiderMain]をレンダリング エンジンとして使用して、ネイティブ アプリに Web コンテンツを表示します。  WebView2 を使用すると、ネイティブ アプリの異なる部分に Web コードを埋め込むことが可能になります。  1 つの WebView インスタンスを使用して、すべてのネイティブ アプリをビルドします。  WebView2 アプリの構築を開始する方法の詳細については、「[開始する方法](#get-started)」をご覧ください。  

:::image type="complex" source="./media/WebView2/what-webview.png" alt-text="WebView とは?" lightbox="./media/WebView2/what-webview.png":::
   WebView とは?  
:::image-end:::    

## <a name="hybrid-app-approach"></a>ハイブリッド アプリのアプローチ  

開発者はひんぱんに、Web アプリを使用するか、またはネイティブ アプリを作成するかの選択をすることが必要になります。  意思決定は、リーチとパワーの間のトレードオフにかかっています。  Web アプリを使用すると、広範囲にアクセスできます。  Web 開発者は、さまざまなプラットフォームでほとんどのコードを再利用する可能性があります。  ネイティブ プラットフォームのすべての機能にアクセスするには、ネイティブ アプリを使用します。  

:::image type="complex" source="./media/WebView2/web-native.png" alt-text="Web ネイティブ" lightbox="./media/WebView2/web-native.png":::
   Web ネイティブ  
:::image-end:::    

ハイブリッド アプリを使用すると、開発者は Webアプリとネイティブ アプリの両方の最高の機能を利用できます。  ハイブリッド アプリ開発者は、次の利点からの恩恵を受けることができます。  

*   Web プラットフォームのユビキタスと強さ。  
*   ネイティブ プラットフォームのパワーとフル機能。  
    
## <a name="webview2-benefits"></a>WebView2 の利点   

:::row:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-web-ecosystem-skillset-small.msft.png":::  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-rapid-innovation-small.msft.png":::  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-windows-7-8-10-support-small.msft.png":::  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ### <a name="web-ecosystem--skillset"></a>Web エコシステム & スキルセット  
   :::column-end:::
   :::column span="1":::
      ### <a name="rapid-innovation"></a>急速な革新  
   :::column-end:::
   :::column span="1":::
      ### <a name="windows-7-8-and-10-support"></a>Windows 7、8、および 10 のサポート  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      Web エコシステム内に存在する Web プラットフォーム、ライブラリ、ツール、人材をすべて活用できます。  
   :::column-end:::
   :::column span="1":::
      Web 開発により、迅速な展開とイテレーションが可能になります。  
   :::column-end:::
   :::column span="1":::
      Windows 7、Windows 8、および Windows 10 全体での一貫したユーザー エクスペリエンへのサポート。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-native-capabilities-small.msft.png":::  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-code-sharing-small.msft.png":::  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-microsoft-support-small.msft.png":::  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ### <a name="native-capabilities"></a>ネイティブ機能  
   :::column-end:::
   :::column span="1":::
      ### <a name="code-sharing"></a>コード共有  
   :::column-end:::
   :::column span="1":::
      ### <a name="microsoft-support"></a>Microsoft サポート  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ネイティブ API のフル セットにアクセスします。  
   :::column-end:::
   :::column span="1":::
      コードベースに Web コードを追加すると、複数のプラットフォームで再利用が増えます。  
   :::column-end:::
   :::column span="1":::
      WebView2 が全般可用性 \(GA\) でリリースされる場合、Microsoft はサポートを提供し、新しい機能要求を追加します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-evergreen-small.msft.png":::  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-fixed-small.msft.png":::  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-incremental-adoption-small.msft.png":::  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ### <a name="evergreen-distribution"></a>Evergreen 分布  
   :::column-end:::
   :::column span="1":::
      ### <a name="fixed"></a>固定  
   :::column-end:::
   :::column span="1":::
      ### <a name="incremental-adoption"></a>段階的導入  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      最新バージョンの Chromium を使用して、定期的なプラットフォームの更新とセキュリティ更新プログラムを利用します。  
   :::column-end:::
   :::column span="1":::
      \( 近日公開 \) アプリ内の Chromium ビットをパッケージ化することを選択します。  
   :::column-end:::
   :::column span="1":::
      Web コンポーネントをアプリに 1 つずつ追加します。  
   :::column-end:::
:::row-end:::  

## <a name="get-started"></a>作業の開始  

WebView2 コントロールを使用してアプリをビルドしてテストするには、以下が必要です <!--both [Microsoft Edge (Chromium)][MicrosoftedgeinsiderDownload] and  -->[WebView2 SDK][NugetPackagesMicrosoftWebWebView2] がインストールされていること。  開始するには、次のいずれかのオプションから １つ選択します。  

*   [はじめに Win32 C/C++ を使用する][Webview2GetStartedWin32]  
*   [WPF の使用を開始する][Webview2GetStartedWpf]  
*   [WinForms の使用を開始する][Webview2GetStartedWinforms]  
*   [WinUI3 の使用を開始する][Webview2GetStartedWinui]  
    
[WebView2 サンプル][GithubMicrosoftedgeWebview2samples]リポジトリには、すべての WebView2 SDK 機能と API の使用パターンを示すサンプルが含まれています。  WebView2 SDK に追加される機能が多い場合、サンプル アプリは更新されます。  

## <a name="supported-platforms"></a>サポートされているプラットフォーム  

一般提供 \ (GA\) またはプレビュー版は、次のプログラミング環境で利用できます。  

*   Win32 C/c + + \ (GA \)  
*   .NET Framework 4.5 以降  
*   .NET Core 3.1 以降  
*   .NET 5  
*   [WinUI 3.0][UwpToolkitsWinui3] \ (プレビュー \)  
    
WebView2 アプリは、次のバージョンの Windowsで実行可能です。。  

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

## <a name="next-steps"></a>次の手順  

WebView2 アプリをビルドおよび展開する方法の詳細については、概念ドキュメントと方法ガイドを参照してください。  

### <a name="concepts"></a>概念  

*   [WebView2 SDK バージョンの概要][Webview2ConceptsVersioning]  
*   [WebView2 を使用したアプリの配布][Webview2ConceptsDistribution]  
*   [セキュリティで保護された WebView2 アプリを開発するためのベスト プラクティス][Webview2ConceptsSecurity]  
*   [WebView2 アプリでユーザー データ フォルダーを管理する][Webview2ConceptsUserDataFolder]  
 
### <a name="how-to-guides"></a>使い方ガイド  

*   [WebView2 を使用してデバッグする方法][Webview2HowToDebug]  
*   [Microsoft Edge Driverを使用した WebView2 の自動化とテスト][Webview2HowToWebdriver]  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](./includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2ConceptsDistribution]: ./concepts/distribution.md "WebView2 を使用したアプリの配布|Microsoft Docs"  
[Webview2ConceptsSecurity]: ./concepts/security.md "セキュリティで保護された WebView2 アプリを開発するためのベスト プラクティス |Microsoft Docs"  
[Webview2ConceptsUserDataFolder]: ./concepts/user-data-folder.md "ユーザー データ フォルダーの管理|Microsoft Docs"  
[Webview2ConceptsVersioning]: ./concepts/versioning.md "WebView2 SDK のバージョンについて理解する |Microsoft Docs"  
[Webview2GetStartedWin32]: ./get-started/win32.md "WebView2 の使用を開始する|Microsoft Docs"  
[Webview2GetStartedWinforms]: ./get-started/winforms.md "Windows フォーム アプリ (プレビュー) でのWebView2 の使用を開始する|Microsoft Docs"  
[Webview2GetStartedWinui]: ./get-started/winui.md "WinUI3 の WebView2 の使用を開始する (プレビュー) |Microsoft Docs"  
[Webview2GetStartedWpf]: ./get-started/wpf.md "WPF (プレビュー) の WebView2 の概要|Microsoft Docs"  
[Webview2HowToDebug]: ./how-to/debug.md "WebView2 を使用してデバッグする方法 |Microsoft Docs"  
[Webview2HowToWebdriver]: ./how-to/webdriver.md "Microsoft Edge Driver での WebView2 の自動化とテスト |Microsoft Docs"  
[Webview2ReleaseNotes]: ./release-notes.md "WebView2 SDK のリリースノート |Microsoft Docs"  

[UwpToolkitsWinui3]: /uwp/toolkits/winui3/index "Windows UI ライブラリ 3 プレビュー 2 (2020 年7 月) |Microsoft Docs"  

[DeployedgeMicrosoftEdgeSupportedOS]: /deployedge/microsoft-edge-supported-operating-systems "Microsoft Edge でサポートされているオペレーティングシステム |Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  
[GithubMicrosoftedgeWebviewfeddback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback | GitHub"  

[MicrosoftedgeinsiderMain]: https://www.microsoftedgeinsider.com "Microsoft Edge Insider"  
[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider をダウンロードする"  

[NugetPackagesMicrosoftWebWebView2]: https://www.nuget.org/packages/Microsoft.Web.WebView2 "Microsoft.Web.WebView2 | NuGet Gallery"  
