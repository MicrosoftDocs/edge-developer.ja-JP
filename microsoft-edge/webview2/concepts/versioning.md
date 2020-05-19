---
description: Microsoft Edge WebView2 で使用されるバージョン管理モデル
title: Microsoft Edge WebView2 のバージョン管理
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/18/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 8463ce403af069cf25dbf7b08bb49d44c1e54501
ms.sourcegitcommit: f1aa8925f7985a2bbfd951f188a8c19c97e4ff6f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2020
ms.locfileid: "10659570"
---
# ブラウザーのバージョンと WebView2 について  

WebView2 は Microsoft Edge によって異なります。  各 WebView2 SDK では、最小ブラウザーバージョンがインストールされている必要があります。  このブラウザバージョンは、[リリースノート][Webview2Releasenotes]で指定されています。  パッケージバージョンの SDK には、最小バージョンが反映されています。  たとえば、を使用する場合は、 `SDK package version 0.9.488` 488 以降のビルド番号で Microsoft Edge をインストールする必要があります。  ブラウザーの最新リリースの詳細については、「[ブラウザーチャネル][DeployedgeChannels]」を参照してください。  

> [!NOTE]
> WebView2 は現在、プレビューに表示されています。  Microsoft Edge WebView チームは、ブラウザーバージョンと Sdk 間の下位互換性を確保するために努力していますが、ブラウザーの新しいバージョンによっては、古いバージョンの SDK がサポートされていない可能性があることを保証していません。  ブラウザーのバージョンと Sdk の間に互換性のある変更がある場合は、Microsoft Edge WebView チームに[リリースノート][Webview2Releasenotes]の変更が示されます。  

今後、Microsoft Edge WebView チームは、配布モデルの変更を計画しています。  Microsoft Edge WebView チームは、WebView2 から Microsoft Edge ブラウザーへの直接の依存関係を削除することを計画しています。  <!--To learn more, see [WebView2 Runtime][Webview2IndexEdgeRuntime] in the [Distribution][Webview2Distibution] section.  -->  

<!--todo: dd link to distribution.md after publication  -->  

## 試験的な API  

WebView2 はプレビューですが、SDK の Api は GA 時に同じであると想定されています。  SDK には[実験的な api][Webview2ReferenceWin3209488Experimental]が含まれています。  試用版 Api を評価し、 [WebView フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeedback]を使ってフィードバックを送信してください。  

### ロードマップ  

WebView2 が安定した一般的な状態に到達して、1.0.0 SDK を解放すると、Microsoft Edge WebView チームは、すべての実験的 Api をプレリリースパッケージに移行することを計画します。  プレリリース版のパッケージでは、引き続き最新機能を利用できます。また、安定性の高いリリースバージョンでは下位互換性が維持されます。  

<!--links -->

[Webview2Distibution]: ./distribution.md "存在しない |Microsoft ドキュメント"  
[Webview2IndexEdgeRuntime]: ../index.md#microsoft-edge-webview2-runtime "Microsoft Edge WebView2 Runtime-Microsoft Edge WebView2 (開発者向けプレビュー) |Microsoft ドキュメント"  
[Webview2ReferenceWin3209488Experimental]: ../reference/win32/0-9-488-reference-webview2.md#experimental "実験的な参照 (WebView2) |Microsoft ドキュメント"  
[Webview2Releasenotes]: ../releasenotes.md "WebView2 SDK のリリースノート |Microsoft ドキュメント"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge チャネルの概要 |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  
