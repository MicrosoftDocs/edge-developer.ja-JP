---
description: Microsoft Edge WebView2 で使用されるバージョン管理モデル
title: Microsoft Edge WebView2 のバージョン管理
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: a47c7295e87cf4295f8cdf898b62aa3b550aa9a5
ms.sourcegitcommit: af91bfc3e6d8afc51f0fbbc0fe392262f424225c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2020
ms.locfileid: "11120340"
---
# WebView2 SDK のバージョンについて  

WebView2 アプリケーションを開発するには、 [WebView2 ランタイム][MicrosoftDeveloperEdgeWebview2] または [非安定した Microsoft Edge チャネル][MicrosoftedgeinsiderDownload]のいずれかをインストールする必要があります。  必要な最小バージョンは、SDK の NuGet パッケージバージョンに含まれています。  たとえば、を使っている場合は、 `SDK package version 0.9.488` [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2] 、またはビルド番号が488以降の [非安定した Microsoft Edge チャネル][MicrosoftedgeinsiderDownload] をインストールする必要があります。  必要な最小バージョンは、WebView2 の [リリースノート][Releasenotes]にも指定されています。  WebView2 SDK の新しいバージョンは、Microsoft Edge \ (Chromium \) ブラウザーと同じ一般的なリズムで出荷されています。これは、約6週間です。  

> [!IMPORTANT]
> Evergreen WebView2 アプリケーションを開発する際には、最新バージョンの WebView2 ランタイムと、安定していない Microsoft Edge ブラウザーを使用して、アプリケーションを定期的にテストします。  Web プラットフォームは絶えず進化しているため、アプリケーションが意図したとおりに動作するための最適な方法は、通常のテストです。  

## Release パッケージとプレリリースパッケージ  

WebView2 NuGet パッケージには、リリースとプレリリースの両方のパッケージが含まれています。  

リリースパッケージには上位互換性があり、 [Win32 C/c + + api][ReferenceWin32]が含まれています。  この SDK の Api は完全にサポートされています。  

プレリリースパッケージは、以下に示すような追加のコンポーネントを含むリリースパッケージのスーパーセットです。  

*   .NET Api: [WPF][DotnetMicrosoftWebWebview2WpfNamespace]、 [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace]、および [Core][DotnetMicrosoftWebWebview2CoreNamespace]  
*   実験的な Api: 詳細については、「 [実験的 api](#experimental-apis) 」セクションを参照してください。  

## 試験的な API  

WebView チームは、今後のリリースに含まれる可能性がある実験的な Api をテストしています。  実験的な Api は、SDK で示されてい `experimental` ます。  実験的な Api は、リリースパッケージで完全に安定した Api として出荷される場合があります。  [WebView フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeedback]を使って、実験的な api を評価し、フィードバックを共有することができます。  

> [!CAUTION]
> プロダクションアプリで実験的な Api を使うことは避けてください。  

## WebView2 のランタイムバージョンの一致  

特定の SDK バージョンを使って WebView2 アプリを作成する場合、アプリのユーザーは、互換性のあるいくつかの WebView2 ランタイムバージョンでアプリを実行することができます。  WebView チームは、以前のバージョンのランタイムと新しい非実験的な Api からの非実験的な Api を含む互換性のある WebView2 ランタイムバージョンで作業しています。  

使用する SDK に応じて、次の項目について検討します。 

*   **Win32 C/c + +**。  を使って `QueryInterface` 新しいインターフェイスを取得するときは、の戻り値を確認し `E_NOINTERFACE` ます。  この値は、WebView2 ランタイムが以前のバージョンであり、そのインターフェイスをサポートしていないことを示す場合があります。  
*   **.Net と WinUI**。  `No such interface supported`新しい sdk に追加されたメソッド、プロパティ、イベントを使用している場合は、例外を確認します。  この例外は、WebView2 ランタイムが以前のバージョンであり、その Api をサポートしていない場合に発生する可能性があります。  

API が利用できない場合は、関連する機能を削除するか、WebView2 ランタイムのバージョンを更新する必要があることをユーザーに知らせてください。  

実験的な Api は、SDK から SDK に導入、変更、削除される可能性があります。  実験的な Api は、インストールされているバージョンの WebView2 Runtime では使用できない場合があります。  

## ロードマップ  

リリースパッケージには、サポートされているすべての安定した Win32 C/C + + C++ Api が含まれています。  今後、リリースパッケージには、一般公開されている限り、サポートされているすべての安定した .NET Api が含まれます。  プレリリースパッケージには、フィードバックに基づいて変更される可能性のある実験的な Api が含まれています。  

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
