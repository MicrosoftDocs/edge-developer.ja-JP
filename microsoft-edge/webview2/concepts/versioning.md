---
description: Microsoft Edge WebView2 で使用されるバージョン管理モデル
title: Microsoft Edge WebView2 のバージョン管理
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/22/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: acf3103f39d33586ee0614aeb0f10de0ab71c89a
ms.sourcegitcommit: b3555043e9d5aefa5a9e36ba4d73934d41559f49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "10894313"
---
# WebView2 SDK のバージョンについて  

WebView2 は Microsoft Edge によって異なります。  各 WebView2 SDK では、最小ブラウザーバージョンがインストールされている必要があります。  最小バージョンは、SDK のパッケージバージョンに反映されています。  たとえば、を使用する場合は、 `SDK package version 0.9.488` 488 以降のビルド番号で Microsoft Edge をインストールする必要があります。  ブラウザーのバージョンも、WebView2 の[リリースノート][Releasenotes]で指定されています。  ブラウザーの最新リリースの詳細については、「[ブラウザーチャネル][DeployedgeChannels]」を参照してください。  

> [!NOTE]
> WebView2 は現在、プレビューに表示されています。  WebView チームは、ブラウザーのバージョンと Sdk の間の下位互換性を確保することを目的としていますが、新しいバージョンのブラウザーでは以前の SDK バージョンがサポートされていない可能性があるため、これは保証されません。  ブラウザーのバージョンと Sdk の間に互換性のある変更がある場合は、[リリースノート][Releasenotes]で変更を指定します。  

今後、WebView2 アプリケーションの配布モデルを変更する予定です。  詳細については、「 [Evergreen 配布モード][DistributionEvergreenMode]」を参照してください。  
 
## リリースとプレリリース版のパッケージ  

[プレビュー] のリリースパッケージには、次の情報が含まれています。  

*   [Win32 C/c + + api][ReferenceWin3209538]: SDK の api であり、GA 時には同じままであると想定されています。  

プレビューでは、プレリリースパッケージには次のコンポーネントが含まれています。  

*   .NET Api: [WPF][ReferenceWpf09515]、 [WinForms][ReferenceWinforms09515]、および[Core][ReferenceDotnet09538]  
*   実験的な Api。  詳細については、「[実験的 api](#experimental-apis) 」セクションを参照してください。  

## 試験的な API  

今後の機能を表す実験的な Api をテストしています。  実験的な Api は、SDK で示されてい `experimental` ます。  実験的な Api は、リリースパッケージで完全に安定した Api として出荷される場合があります。  すべての実験的な Api は、リリース前に変更することを前提としています。  [WebView フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeedback]を使って、実験的な api を評価し、フィードバックを共有してください。   

> [!CAUTION]
> プロダクションアプリケーションで実験的な Api を使うことは避けてください。  

## ロードマップ  

WebView2 が安定した一般的な状態に達すると、リリースパッケージには、サポートされているすべての安定した Win32 C/c + + + .NET Api が含まれます。  プレリリースパッケージには、開発者のフィードバックおよび共有の分析に基づいて変更される実験的な Api が含まれています。  

<!--## Versioning  

After you have used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.  Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that prevent your SDK from working with different versions of installed browser binaries.  After version 1.0.0.0, different versions of the SDK may work with different versions of the installed browser by using the following best practices.  

1.  To account for breaking changes to the API be sure to check for failure when requesting the DLL export `CreateCoreWebView2Environment` and when running `QueryInterface` on any `CoreWebView2` object.  A return value of `E_NOINTERFACE` indicates that the SDK is not compatible with the Microsoft Edge browser binaries.  
1.  Checking for failure from `QueryInterface` also accounts for cases where the SDK is newer than the version of the Microsoft Edge browser and your app attempts to use an interface of which the Microsoft Edge browser is unaware.  

1.  When an interface is unavailable, you may consider disabling the associated feature if possible, or otherwise informing your users to update their browsers.  -->  

<!--links -->

[DistributionEvergreenMode]: ./distribution.md#evergreen-distribution-mode "Evergreen 配布モード-WebView2 を使用したアプリケーションの配布 |Microsoft ドキュメント"  
[ReferenceDotnet09538]: ../reference/dotnet/0-9-538-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[ReferenceWinforms09515]: ../reference/winforms/0-9-515-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[ReferenceWin3209538]: ../reference/win32/0-9-538-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[ReferenceWpf09515]: ../reference/wpf/0-9-515-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[Releasenotes]: ../releasenotes.md "WebView2 SDK のリリースノート |Microsoft ドキュメント"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge チャネルの概要 |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  
