---
description: Microsoft Edge WebView2 で使用されるバージョン管理モデル
title: Microsoft Edge WebView2 のバージョン管理
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/25/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 54d62de00a89a3c433fd77e9ec20945adbfc19c3
ms.sourcegitcommit: 2e14ff82350f700d7eabc8d33b3ec3e5fc8c61fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "11191611"
---
# WebView2 SDK のバージョンについて  

WebView2 SDK の新しいバージョンは、Microsoft Edge \ (Chromium \) ブラウザーと同じ一般的なリズムで出荷されています。これは、約6週間です。  

## Release パッケージとプレリリースパッケージ  

WebView2 NuGet パッケージには、リリースとプレリリースの両方のパッケージが含まれています。  

**リリースパッケージ**には上位互換性があり、次のコンポーネントが含まれています。  

*   [Win32 C/c + + Api][ReferenceWin32]
*   .NET Api:  [WPF][DotnetMicrosoftWebWebview2WpfNamespace]、 [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace]、および [Core][DotnetMicrosoftWebWebview2CoreNamespace]。  
    
SDK の Api は完全にサポートされています。  

**プレリリースパッケージ**は、[実験的 api](#experimental-apis)を使用したリリースパッケージのスーパーセットです。  

### ロードマップ  

リリースパッケージには、サポートされているすべての安定した Win32 C/c + + .NET Api が含まれています。  プレリリースパッケージには、フィードバックに基づいて変更される可能性がある実験的な Api が含まれています。  

## 試験的な API  

WebView チームは、今後のリリースに含まれる可能性がある実験的な Api についてのフィードバックを求めています。  実験的な Api は、SDK で示されてい `experimental` ます。  実験的な Api を評価してフィードバックを共有できるように、 [WebView フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeedback]に移動します。  

> [!CAUTION]
> 実験的な Api は、SDK から SDK に導入、変更、削除される可能性があります。  プロダクションアプリで実験的な Api を使うことは避けてください。  

> [!NOTE]
> 実験的な Api は、インストールされているバージョンの WebView2 Runtime では使用できない場合があります。  

## WebView2 のランタイムバージョンの一致  
WebView2 アプリでは、ユーザーが [WebView2 ランタイム][MicrosoftDeveloperEdgeWebview2]をインストールする必要があります。  WebView2 ランタイムは、利用可能な最新バージョンに自動的に更新されます。  一部のシナリオでは、ユーザーが自動 WebView2 ランタイム更新を停止する必要があります。これにより、アプリの互換性の問題が発生する可能性があります。  

WebView2 ランタイムの更新プログラムが停止している場合は、アプリで必要な最小バージョンの [WebView2 ランタイム][MicrosoftDeveloperEdgeWebview2] を理解していることを確認してください。  次の2つの項目を検討してください。  

1.  SDK の最低限必要なバージョンは、WebView2 の [リリースノート][Webview2Releasenotes] の「 **最小 WebView2 ランタイムバージョン**」に記載されています。  たとえば、SDK バージョン [1.0.622.22][Webview2Releasenotes1062222]の場合は、 [WebView2 ランタイム][MicrosoftDeveloperEdgeWebview2] 、またはビルド番号以降の [非安定した Microsoft Edge チャネル][MicrosoftedgeinsiderDownload] をインストールする必要があり `86.0.616.0` ます。  SDK で必要な最小バージョンは、web プラットフォームで変更が行われない場合にのみ変更されます。  
1.  アプリで使うインターフェイスと Api をサポートするために必要な、最低限の必須バージョンの NuGet パッケージ。  WebView2 には、新しいインターフェイスと Api が定期的に追加されます。  SDK にバンドルされている Api とインターフェイスは、異なるタイミングで SDK に Api とインターフェイスが追加されるため、異なるバージョンの WebView2 ランタイムを必要とします。  必須の WebView2 ランタイムバージョンは、API が最初に導入された SDK バージョンの3番目の番号のビルド番号と一致します。  たとえば、SDK バージョン [1.0.622.22][Webview2Releasenotes1062222] で追加された新しい api またはインターフェイスには、WebView2 ランタイムバージョンが必要です。この  `86.0.622.0`  ような sdk リリースで追加された api やインターフェイスには、sdk と同じバージョン番号の WebView2 ランタイムが必要です。  WebView2 ランタイムバージョンがインターフェイスまたは API をサポートしているかどうかを判断するには、 [WebView2 ランタイム要件を決定](#determine-webview2-runtime-requirement)するに移動します。  
    
> [!IMPORTANT]
> [Evergreen WebView2 アプリ][Webview2ConceptsDistributionEvergreenDistributionMode]を開発する場合は、最新バージョンの WebView2 Runtime と、安定していない Microsoft Edge ブラウザーに対して、アプリを定期的にテストしてください。  Web プラットフォームは絶えず進化しているため、アプリが意図したとおりに動作するための最適な方法は、通常のテストです。  

### WebView2 のランタイム要件を決定する  

使用する SDK に応じて、次の項目について検討します。  

*   **Win32 C/c + +**。  を使って新しいインターフェイスを取得するときは `QueryInterface` 、の戻り値を確認し `E_NOINTERFACE` ます。  この値は、WebView2 ランタイムが以前のバージョンであり、そのインターフェイスをサポートしていないことを示している可能性があります。  このしくみの例については、「 [行 622-AppWindow .cpp」][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisampleAppwindowCppL622]を参照してください。  
*   **.Net と WinUI**。  `No such interface supported`新しい sdk に追加されたメソッド、プロパティ、イベントを使用している場合は、例外を確認します。  この例外は、WebView2 ランタイムが以前のバージョンであり、Api をサポートしていない場合に発生する可能性があります。  
    
API が利用できない場合は、関連する機能の削除を検討するか、WebView2 ランタイムの更新が必要であることをユーザーに通知します。  

<!--
## Versioning  

After you have used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.  Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that prevent your SDK from working with different versions of installed browser binaries.  After version 1.0.0.0, different versions of the SDK may work with different versions of the installed browser by using the following best practices.  

1.  To account for breaking changes to the API be sure to check for failure when requesting the DLL export `CreateCoreWebView2Environment` and when running `QueryInterface` on any `CoreWebView2` object.  A return value of `E_NOINTERFACE` indicates that the SDK is not compatible with the Microsoft Edge browser binaries.  
1.  Checking for failure from `QueryInterface` also accounts for cases where the SDK is newer than the version of the Microsoft Edge browser and your app attempts to use an interface of which the Microsoft Edge browser is unaware.  
1.  When an interface is unavailable, you may consider disabling the associated feature if possible, or otherwise informing your users to update their browsers.  
    -->  

<!--links -->  

[Webview2ConceptsDistributionEvergreenDistributionMode]: ./distribution.md#evergreen-distribution-mode "Evergreen 配布モード-WebView2 を使用したアプリの配布 |Microsoft ドキュメント"  
[Webview2Releasenotes]: ../releasenotes.md "WebView2 SDK のリリースノート |Microsoft ドキュメント"  
[Webview2Releasenotes1062222]: ../releasenotes.md#1062222 "1.0.622.22-WebView2 SDK のリリースノート |Microsoft ドキュメント"   

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge チャネルの概要 |Microsoft ドキュメント"  

[DotnetMicrosoftWebWebview2CoreNamespace]: /dotnet/api/microsoft.web.webview2.core "WebView2 の名前空間 |Microsoft ドキュメント"  
[DotnetMicrosoftWebWebview2WpfNamespace]: /dotnet/api/microsoft.web.webview2.wpf "WebView2 の名前空間 |Microsoft ドキュメント"  
[DotnetMicrosoftWebWebview2WinformsNamespace]: /dotnet/api/microsoft.web.webview2.winforms "WinForms 名前空間 WebView2 |Microsoft ドキュメント"  
[ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 C++ リファレンス |Microsoft ドキュメント"  

[MicrosoftDeveloperEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2/ "Microsoft Edge WebView2 |Microsoft 開発者"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisampleAppwindowCppL622]: https://github.com/MicrosoftEdge/WebView2Samples/blob/8ec7de9d3e80a942bc7025cffad98eee75e11e64/SampleApps/WebView2APISample/AppWindow.cpp#L622 "Line 622-AppWindow .cpp-MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  
