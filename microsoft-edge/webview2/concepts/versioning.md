---
description: Microsoft Edge WebView2 で使用されるバージョン管理モデル
title: Microsoft Edge WebView2 のバージョン管理
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 059bbeb34f372af0cef944e484599c0b50543cc9
ms.sourcegitcommit: 288bd2a1bec418a84d1f0bda013c1913886bd269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "10844426"
---
# WebView2 SDK のバージョンについて  

WebView2 は Microsoft Edge によって異なります。  各 WebView2 SDK では、最小ブラウザーバージョンがインストールされている必要があります。  最小バージョンは、SDK のパッケージバージョンに反映されています。  たとえば、を使用する場合は、 `SDK package version 0.9.488` 488 以降のビルド番号で Microsoft Edge をインストールする必要があります。  ブラウザーのバージョンも、WebView2 の[リリースノート][Releasenotes]で指定されています。  ブラウザーの最新リリースの詳細については、「[ブラウザーチャネル][DeployedgeChannels]」を参照してください。  

> [!NOTE]
> WebView2 は現在、プレビューに表示されています。  WebView チームは、ブラウザーのバージョンと Sdk の下位互換性を確保するために努力していますが、新しいバージョンのブラウザーでは旧バージョンの SDK がサポートされていない可能性があるため、これは保証されていません。  ブラウザーのバージョンと Sdk の間に互換性のある変更がある場合、WebView チームで[リリースノート][Releasenotes]の変更を指定します。  

今後、WebView チームは WebView2 アプリケーションの配布モデルを変更することを計画しています。  詳細については、「 [Evergreen 配布モード][DistributionEvergreenMode]」を参照してください。  
 
## リリースとプレリリース版のパッケージ  

[プレビュー] のリリースパッケージには、次の情報が含まれています。  

*   [Win32 C/c + + api][ReferenceWin3209538]: SDK の api であり、GA 時には同じままであると想定されています。 

プレビューでは、プレリリースパッケージには次のコンポーネントが含まれています。  

*   .NET Api: [WPF][ReferenceWpf09515]、 [WinForms][ReferenceWinforms09515]、および[Core][ReferenceDotnet09538]
*   実験的な Api。  詳細については、「[実験的 api](#experimental-apis) 」セクションを参照してください。  

### 試験的な API  

WebView チームは、実験的な Api という名前の将来の機能を表す Api をテストしています。  実験的な Api は、SDK で示されてい `experimental` ます。  一部の実験的な Api は、リリースパッケージで完全に安定した Api として配布される場合があります。  すべての実験的な Api は、リリース前に変更することを前提としています。  [WebView フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeedback]を使って、実験的な api を評価し、フィードバックを共有してください。   

> [!CAUTION]
> プロダクションアプリケーションで実験的な Api を使うことは避けてください。  

### ロードマップ  

WebView2 が安定した一般的な状態に達すると、リリースパッケージには、サポートされているすべての安定した Win32 C/c + + + .NET Api が含まれます。  プレリリースパッケージには、開発者のフィードバックおよび共有の分析に基づいて変更される実験的な Api が含まれています。  

<!--links -->

[DistributionEvergreenMode]: ./distribution.md#evergreen-distribution-mode "Evergreen 配布モード-WebView2 を使用したアプリケーションの配布 |Microsoft ドキュメント"  
[ReferenceDotnet09538]: ../reference/dotnet/0-9-538-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[ReferenceWinforms09515]: ../reference/winforms/0-9-515-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[ReferenceWin3209538]: ../reference/win32/0-9-538-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[ReferenceWpf09515]: ../reference/wpf/0-9-515-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[Releasenotes]: ../releasenotes.md "WebView2 SDK のリリースノート |Microsoft ドキュメント"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge チャネルの概要 |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  
