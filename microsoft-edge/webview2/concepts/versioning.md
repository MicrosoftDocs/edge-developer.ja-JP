---
description: Microsoft Edge WebView2 で使用されるバージョン管理モデル
title: Microsoft Edge WebView2 のバージョン管理
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/14/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: b673a2b250e46959a2eabaeb88cd8535f9a271e4
ms.sourcegitcommit: 61cc15d2fc89aee3e09cec48ef1e0e5bbf8d289a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2020
ms.locfileid: "11118983"
---
# WebView2 SDK のバージョンについて  

WebView2 は Microsoft Edge によって異なります。  各 WebView2 SDK では、最小ブラウザーバージョンがインストールされている必要があります。  最小バージョンは、SDK のパッケージバージョンに反映されています。  たとえば、を使用する場合は、 `SDK package version 0.9.488` 488 以降のビルド番号で Microsoft Edge をインストールする必要があります。  ブラウザーのバージョンも、WebView2 の [リリースノート][Releasenotes]で指定されています。  Microsoft Edge ブラウザーの最新リリースの詳細については、「 [ブラウザーチャネル][DeployedgeChannels]」を参照してください。  

> [!NOTE]
> WebView2 は現在、プレビューに表示されています。  WebView チームは、ブラウザーのバージョンと Sdk の間の下位互換性を確保することを目的としていますが、新しいバージョンのブラウザーでは以前の SDK バージョンがサポートされていない可能性があるため、これは保証されません。  ブラウザーのバージョンと Sdk の間に互換性のある変更があった場合、その変更は [リリースノート][Releasenotes]で指定されます。  

今後、WebView チームは WebView2 アプリの配布モデルを変更することを計画しています。  詳細については、「 [Evergreen 配布モード][DistributionEvergreenMode]に移動する」を参照してください。  

## Release パッケージとプレリリースパッケージ  

[プレビュー] のリリースパッケージには、次の情報が含まれています。  

*   [Win32 C/c + + api][ReferenceWin32]: SDK の api であり、GA 時には同じままであると想定されています。  

プレビューでは、プレリリースパッケージには次のコンポーネントが含まれています。  

*   .NET Api: [WPF][DotnetMicrosoftWebWebview2WpfNamespace]、 [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace]、および [Core][DotnetMicrosoftWebWebview2CoreNamespace]  
*   実験的な Api。  詳細については、「 [実験的 api](#experimental-apis) 」セクションを参照してください。  

## 試験的な API  

WebView チームは、将来の機能を示す実験的な Api をテストしています。  実験的な Api は、SDK で示されてい `experimental` ます。  実験的な Api は、リリースパッケージで完全に安定した Api として出荷される場合があります。  すべての実験的な Api は、リリース前に変更することを前提としています。  [WebView フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeedback]を使って、実験的な api を評価し、フィードバックを共有してください。  

> [!CAUTION]
> プロダクションアプリで実験的な Api を使うことは避けてください。  

## WebView2 のランタイムバージョンの一致  

特定の SDK バージョンを使って WebView2 アプリを作成する場合、ユーザーのアプリのユーザーは、互換性のあるさまざまなバージョンの WebView2 ランタイムでアプリを実行することができます。  今後の互換性のある WebView2 ランタイムバージョンには、以前の互換性のある WebView2 ランタイムバージョンと、新しい非実験的な Api 以外の、すべての非実験的な Api が含まれています。  

*   **Win32 C/c + +** の開発者は、 `QueryInterface` 新しいインターフェイスを取得するためにを使う場合、の戻り値を確認する必要があります `E_NOINTERFACE` 。これは、WebView2 ランタイムが古いため、その特定のインターフェイスがサポートされていないことを示している可能性があります。  
*   **.Net と WinUI** の開発者は、 `No such interface supported` WebView2 ランタイムが古い場合や特定の api がサポートされていない場合に発生する可能性がある、後日の sdk で追加されたメソッド、プロパティ、イベントを使用する場合に例外を確認する必要があります。  

API が利用できない場合は、可能であれば関連する機能を無効にするか、またはエンドユーザーに WebView2 ランタイムバージョンを更新する必要があることを通知することを検討してください。  

実験的な Api は、SDK から SDK に導入、変更、削除される可能性があります。  WebView2 ランタイムで利用できない実験的な API を使用しようとすると、先ほど説明したのと同じ動作が表示されることがあります。  

## ロードマップ  

WebView2 が安定した一般的な状態に達すると、リリースパッケージには、サポートされているすべての安定した Win32 C/c + + + .NET Api が含まれます。  プレリリースパッケージには、フィードバックに基づいて変更される可能性のある実験的な Api が含まれています。  

<!--## Versioning  

After you have used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.  Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that prevent your SDK from working with different versions of installed browser binaries.  After version 1.0.0.0, different versions of the SDK may work with different versions of the installed browser by using the following best practices.  

1.  To account for breaking changes to the API be sure to check for failure when requesting the DLL export `CreateCoreWebView2Environment` and when running `QueryInterface` on any `CoreWebView2` object.  A return value of `E_NOINTERFACE` indicates that the SDK is not compatible with the Microsoft Edge browser binaries.  
1.  Checking for failure from `QueryInterface` also accounts for cases where the SDK is newer than the version of the Microsoft Edge browser and your app attempts to use an interface of which the Microsoft Edge browser is unaware.  

1.  When an interface is unavailable, you may consider disabling the associated feature if possible, or otherwise informing your users to update their browsers.  -->  

<!--links -->

[DistributionEvergreenMode]: ./distribution.md#evergreen-distribution-mode "Evergreen 配布モード-WebView2 を使用したアプリケーションの配布 |Microsoft ドキュメント"  
[DotnetMicrosoftWebWebview2CoreNamespace]: /dotnet/api/microsoft.web.webview2.core "WebView2 の名前空間 |Microsoft ドキュメント"
[DotnetMicrosoftWebWebview2WpfNamespace]: /dotnet/api/microsoft.web.webview2.wpf "WebView2 の名前空間 |Microsoft ドキュメント"
[DotnetMicrosoftWebWebview2WinformsNamespace]: /dotnet/api/microsoft.web.webview2.winforms "WinForms 名前空間 WebView2 |Microsoft ドキュメント"
[ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 C++ リファレンス |Microsoft ドキュメント"  
[Releasenotes]: ../releasenotes.md "WebView2 SDK のリリースノート |Microsoft ドキュメント"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge チャネルの概要 |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  
