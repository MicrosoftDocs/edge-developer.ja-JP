---
description: Microsoft Edge WebView2 で使用されるバージョン モデル
title: WebView2 SDK バージョンの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/17/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、edge html
ms.openlocfilehash: b292f59e264293a958eb619d04b751203cb517ac
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461179"
---
# <a name="understand-webview2-sdk-versions"></a>WebView2 SDK バージョンの概要  

WebView2 SDK の新しいバージョンは、Microsoft Edge \(Chromium\) ブラウザーと同じ一般的なケイデンスで出荷されます。これは約 6 週間ごとに行います。  

## <a name="release-and-prerelease-package"></a>リリースおよびプレリリース パッケージ  

WebView2 NuGet パッケージには、リリース パッケージとプレリリース パッケージの両方が含まれています。  

リリース **パッケージは前方** 互換性があり、次のコンポーネントが含まれています。  

*   [Win32 C/C++ API][ReferenceWin32]
*   .NET API:  [WPF][DotnetMicrosoftWebWebview2WpfNamespace] [、WinForms、][DotnetMicrosoftWebWebview2WinformsNamespace]および [Core][DotnetMicrosoftWebWebview2CoreNamespace]。  
    
SDK の API は完全にサポートされています。  

プレ **リリース パッケージは、** 実験的 API を使用したリリース パッケージ [のスーパーセットです](#experimental-apis)。  プレリリース SDK を使用して実稼働アプリをビルドしないようにします。  

### <a name="roadmap"></a>ロードマップ  

リリース パッケージには、サポートされている安定した Win32 C/C++ および .NET API すべてが含まれています。  prerelease パッケージには、フィードバックに基づいて変更される可能性がある実験的な API が含まれています。  

## <a name="experimental-apis"></a>試験的な API  

WebView チームは、将来のリリースに含まれる可能性がある実験的な API に関するフィードバックを求めている。  実験的な API は SDK のように `experimental` マークされます。  実験 API を評価し、フィードバックを共有するには [、WebView フィードバック repo に移動します][GithubMicrosoftedgeWebviewfeedback]。  

> [!CAUTION]
> 実験 API は、SDK から SDK に導入、変更、および削除される場合があります。  実稼働アプリで実験的な API を使用しないようにします。  

> [!NOTE]
> 実験的な API は、インストールされているバージョンの WebView2 ランタイムでは使用できない場合があります。  

## <a name="matching-webview2-runtime-versions"></a>一致する WebView2 ランタイム バージョン  
WebView2 アプリでは、ユーザーが [WebView2 ランタイムをインストールする必要があります][MicrosoftDeveloperEdgeWebview2]。  WebView2 ランタイムは、利用可能な最新バージョンに自動的に更新されます。  一部のシナリオでは、ユーザーが WebView2 ランタイムの自動更新を停止する必要が生じ、アプリの互換性の問題が発生する可能性があります。  

WebView2 ランタイム更新プログラムが停止している場合は、アプリに必要な [WebView2 ランタイム][MicrosoftDeveloperEdgeWebview2] の最小バージョンを理解してください。  次の 2 つの項目を検討してください。  

1.  Webview2 インスタンスを正常に読み込むのに必要な最小バージョンの SDK は、読[][Webview2Releasenotes]み込む最小 Microsoft Edge バージョンの WebView2 リリース ノート**にあります**。  SDK で必要な読み込み最小バージョンは、Web プラットフォームで変更が発生した場合にのみ変更されます。  たとえば、SDK バージョン [1.0.622.22][Webview2Releasenotes1062222]の場合、ビルド番号が 1 つ以上の [WebView2 ランタイム][MicrosoftDeveloperEdgeWebview2] または安定しない [Microsoft Edge][MicrosoftedgeinsiderDownload] チャネルをインストール `86.0.616.0` する必要があります。   
1.  アプリ内のインターフェイスと API をサポートするために必要な NuGet パッケージの最小必要バージョンは、WebView2[][Webview2Releasenotes]リリース ノートの「完全な API の互換性」の下に**示されています**。  新しいインターフェイスと API は WebView2 に定期的に追加されます。  SDK にバンドルされている API とインターフェイスでは、API とインターフェイスが SDK に異なる時間に追加されるので、WebView2 ランタイムのバージョンが異なっている必要があります。  必要な WebView2 ランタイム バージョンは、API が最初に導入された SDK バージョンのビルド番号 (3 番目の番号) と一致します。  たとえば、SDK バージョン [1.0.622.22][Webview2Releasenotes1062222] で追加された新しい API またはインターフェイスには、WebView2 ランタイム バージョン以降が `86.0.622.0` 必要です。  後の SDK リリースで追加された API またはインターフェイスには、SDK と同じバージョン番号を持つ WebView2 ランタイムが必要です。  WebView2 ランタイム バージョンがインターフェイスまたは API をサポートしているかどうかを判断するには [、[WebView2](#determine-webview2-runtime-requirement)ランタイム要件の決定] に移動します。  
    
> [!IMPORTANT]
> [Evergreen WebView2][Webview2ConceptsDistributionEvergreenDistributionMode]アプリを開発する場合は、WebView2 ランタイムと安定しない Microsoft Edge チャネルの最新バージョンに対してアプリを定期的にテストします。  Web プラットフォームは常に進化し続けるので、アプリが意図した通り動作することを確認するには、定期的なテストが最適な方法です。  

### <a name="determine-webview2-runtime-requirement"></a>WebView2 ランタイム要件の決定  

使用する SDK に応じて、次の項目を検討してください。  

*   **Win32 C/C++**。  新しいインターフェイス `QueryInterface` を取得するために使用する場合は、 の戻り値を確認します `E_NOINTERFACE` 。  この値は、WebView2 ランタイムが以前のバージョンであり、そのインターフェイスをサポートしない場合があります。  動作の例については [、Line 622 - AppWindow.cpp に移動します][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisampleAppwindowCppL622]。  
*   **.NET と WinUI**。  より新しい SDK に追加されたメソッド、プロパティ、およびイベントを使用する場合は、 `No such interface supported` 例外を確認します。  この例外は、WebView2 ランタイムが以前のバージョンであり、API をサポートしていない場合に発生することがあります。  
    
API が使用できない場合は、関連付けられた機能の削除を検討するか、WebView2 ランタイムの更新が必要です。  

<!--
## Versioning  

After you have used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.  Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that prevent your SDK from working with different versions of installed browser binaries.  After version 1.0.0.0, different versions of the SDK may work with different versions of the installed browser by using the following best practices.  

1.  To account for breaking changes to the API be sure to check for failure when requesting the DLL export `CreateCoreWebView2Environment` and when running `QueryInterface` on any `CoreWebView2` object.  A return value of `E_NOINTERFACE` indicates that the SDK is not compatible with the Microsoft Edge browser binaries.  
1.  Checking for failure from `QueryInterface` also accounts for cases where the SDK is newer than the version of the Microsoft Edge browser and your app attempts to use an interface of which the Microsoft Edge browser is unaware.  
1.  When an interface is unavailable, you may consider disabling the associated feature if possible, or otherwise informing your users to update their browsers.  
    -->  

<!--links -->  

[Webview2ConceptsDistributionEvergreenDistributionMode]: ./distribution.md#evergreen-distribution-mode "Evergreen 配布モード - WebView2 アプリケーションを使用したアプリの|Microsoft Docs"  
[Webview2Releasenotes]: ../releasenotes.md "WebView2 SDK のリリース ノート|Microsoft Docs"  
[Webview2Releasenotes1062222]: ../releasenotes.md#1062222 "1.0.622.22 - WebView2 SDK のリリース |Microsoft Docs"   

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge チャネルの概要 | Microsoft Docs"  

[DotnetMicrosoftWebWebview2CoreNamespace]: /dotnet/api/microsoft.web.webview2.core "Microsoft.Web.WebView2.Core 名前空間|Microsoft Docs"  
[DotnetMicrosoftWebWebview2WpfNamespace]: /dotnet/api/microsoft.web.webview2.wpf "Microsoft.Web.WebView2.Wpf 名前空間 | Microsoft Docs"  
[DotnetMicrosoftWebWebview2WinformsNamespace]: /dotnet/api/microsoft.web.webview2.winforms "Microsoft.Web.WebView2.WinForms 名前空間|Microsoft Docs"  
[ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 C++ リファレンス |Microsoft Docs"  

[MicrosoftDeveloperEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2/ "Microsoft Edge WebView2 |Microsoft 開発者"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック - MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisampleAppwindowCppL622]: https://github.com/MicrosoftEdge/WebView2Samples/blob/8ec7de9d3e80a942bc7025cffad98eee75e11e64/SampleApps/WebView2APISample/AppWindow.cpp#L622 "Line 622 - AppWindow.cpp - MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channels をダウンロードする"  
