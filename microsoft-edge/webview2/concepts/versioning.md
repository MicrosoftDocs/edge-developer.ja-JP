---
description: Microsoft Edge WebView2 で使用されるバージョン管理モデル
title: Microsoft Edge WebView2 のバージョン管理
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/18/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 132ccab0f9f378eedd8c83a7404c350161556f2e
ms.sourcegitcommit: fab44f7e183a3c4f12bf925512fc62d84a4d6edc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "11182396"
---
# WebView2 SDK のバージョンについて

WebView2 SDK の新しいバージョンは、Microsoft Edge \ (Chromium \) ブラウザーと同じ一般的なリズムで出荷されています。これは、約6週間です。  

## Release パッケージとプレリリースパッケージ  

WebView2 NuGet パッケージには、リリースとプレリリースの両方のパッケージが含まれています。  

リリースパッケージには上位互換性があり、 [Win32 C/c + + api][ReferenceWin32]が含まれています。  この SDK の Api は完全にサポートされています。  

プレリリースパッケージは、以下に示すような追加のコンポーネントを含むリリースパッケージのスーパーセットです。  

*   .NET Api: [WPF][DotnetMicrosoftWebWebview2WpfNamespace]、 [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace]、および [Core][DotnetMicrosoftWebWebview2CoreNamespace]  
*   実験的な Api: 詳細については、「 [実験的 api](#experimental-apis) 」セクションを参照してください。  

### ロードマップ  

リリースパッケージには、サポートされているすべての安定した Win32 C/C + + C++ Api が含まれています。  今後、リリースパッケージには、一般に公開されるときに、サポートされているすべての安定した .NET Api が含まれます。  プレリリースパッケージには、フィードバックに基づいて変更される可能性がある実験的な Api が含まれています。 

## 試験的な API  

WebView チームは、今後のリリースに含まれる可能性がある実験的な Api についてのフィードバックを求めています。  実験的な Api は、SDK で示されてい `experimental` ます。  [WebView フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeedback]を使って、実験的な api を評価し、フィードバックを共有することができます。  

> [!CAUTION]
> 実験的な Api は、SDK から SDK に導入、変更、削除される可能性があります。  プロダクションアプリで実験的な Api を使うことは避けてください。  

> [!NOTE]
> 実験的な Api は、インストールされているバージョンの WebView2 Runtime では使用できない場合があります。  

## WebView2 のランタイムバージョンの一致  
WebView2 アプリケーションでは、ユーザーが [WebView2 ランタイム][MicrosoftDeveloperEdgeWebview2]をインストールする必要があります。 WebView2 ランタイムは、使用できる最新バージョンに自動的に更新されます。 一部のシナリオでは、ユーザーが自動 WebView2 ランタイム更新を停止する必要があります。これにより、アプリケーションの互換性の問題が発生する可能性があります。

WebView2 ランタイムの更新プログラムが停止している場合は、アプリケーションで必要な最小バージョンの [WebView2 ランタイム][MicrosoftDeveloperEdgeWebview2] を理解していることを確認してください。 次の2つの項目を検討してください。  

1. SDK の必須バージョンのうち、最小の**WebView2 ランタイムバージョン**の WebView2[リリースノート][Releasenotes]に記載されているものを参照してください。 たとえば、SDK バージョン[1.0.622.22](https://docs.microsoft.com/microsoft-edge/webview2/releasenotes#1062222)の場合は、 [WebView2 ランタイム][MicrosoftDeveloperEdgeWebview2]、または**86.0.616.0**以降のビルド番号を持つ[非安定した Microsoft Edge チャネル][MicrosoftedgeinsiderDownload]をインストールする必要があります。 SDK で必要な最小バージョンは、web プラットフォームで変更が行われた場合にのみ変更されます。

2. アプリで使用されるインターフェイスと Api をサポートするために必要な、最低限必要なバージョンの NuGet パッケージ。 WebView2 には、新しいインターフェイスと Api が定期的に追加されます。 SDK にバンドルされている Api とインターフェイスは、異なるタイミングで SDK に追加されたため、異なるバージョンの WebView2 ランタイムを必要とします。  必須の WebView2 ランタイムバージョンは、API が最初に導入された SDK バージョンの3番目の番号のビルド番号と一致します。 たとえば、SDK バージョン [1.0.622.22](https://docs.microsoft.com/microsoft-edge/webview2/releasenotes#1062222) に追加された新しい API またはインターフェイスには、WebView2 ランタイムバージョン86.0 が必要です。**622**. 0。 後続の SDK リリースで追加された API またはインターフェイスでは、SDK と同じバージョン番号の WebView2 ランタイムが必要です。 WebView2 ランタイムバージョンが、インターフェイスまたは API を [プログラム](#determine-webview2-runtime-requirement)でサポートしているかどうかを確認できます。

> [!IMPORTANT]
> [Evergreen WebView2 アプリケーション](distribution.md#evergreen-distribution-mode)を開発する際には、最新バージョンの WebView2 ランタイムと、安定していない Microsoft Edge ブラウザーを使用して、アプリケーションを定期的にテストします。  Web プラットフォームは絶えず進化しているため、アプリケーションが意図したとおりに動作するための最適な方法は、通常のテストです。  

### WebView2 のランタイム要件を決定する

使用する SDK に応じて、次の項目について検討します。 

*   **Win32 C/c + +**。  を使って `QueryInterface` 新しいインターフェイスを取得するときは、の戻り値を確認し `E_NOINTERFACE` ます。  この値は、WebView2 ランタイムが以前のバージョンであり、そのインターフェイスをサポートしていないことを示す場合があります。 このしくみの [例](https://github.com/MicrosoftEdge/WebView2Samples/blob/8ec7de9d3e80a942bc7025cffad98eee75e11e64/SampleApps/WebView2APISample/AppWindow.cpp#L622) については、WebView2API のサンプルを参照してください。
*   **.Net と WinUI**。  `No such interface supported`新しい sdk に追加されたメソッド、プロパティ、イベントを使用している場合は、例外を確認します。  この例外は、WebView2 ランタイムが以前のバージョンであり、その Api をサポートしていない場合に発生する可能性があります。  

API が利用できない場合は、関連する機能を削除するか、WebView2 ランタイムのバージョンを更新する必要があることをユーザーに知らせてください。  



 

<!--## Versioning  

After you have used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.  Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that prevent your SDK from working with different versions of installed browser binaries.  After version 1.0.0.0, different versions of the SDK may work with different versions of the installed browser by using the following best practices.  

1.  To account for breaking changes to the API be sure to check for failure when requesting the DLL export `CreateCoreWebView2Environment` and when running `QueryInterface` on any `CoreWebView2` object.  A return value of `E_NOINTERFACE` indicates that the SDK is not compatible with the Microsoft Edge browser binaries.  
1.  Checking for failure from `QueryInterface` also accounts for cases where the SDK is newer than the version of the Microsoft Edge browser and your app attempts to use an interface of which the Microsoft Edge browser is unaware.  

1.  When an interface is unavailable, you may consider disabling the associated feature if possible, or otherwise informing your users to update their browsers.  -->  

<!--links -->  

[Releasenotes]: ../releasenotes.md "WebView2 SDK のリリースノート |Microsoft ドキュメント"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge チャネルの概要 |Microsoft ドキュメント"  

[DotnetMicrosoftWebWebview2CoreNamespace]: /dotnet/api/microsoft.web.webview2.core "WebView2 の名前空間 |Microsoft ドキュメント"  
[DotnetMicrosoftWebWebview2WpfNamespace]: /dotnet/api/microsoft.web.webview2.wpf "WebView2 の名前空間 |Microsoft ドキュメント"  
[DotnetMicrosoftWebWebview2WinformsNamespace]: /dotnet/api/microsoft.web.webview2.winforms "WinForms 名前空間 WebView2 |Microsoft ドキュメント"  
[ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 C++ リファレンス |Microsoft ドキュメント"  

[MicrosoftDeveloperEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2/ "Microsoft Edge WebView2 |Microsoft 開発者"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  
