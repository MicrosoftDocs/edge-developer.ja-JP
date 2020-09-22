---
description: WebView2 アプリケーションを管理する方法を理解する
title: WebView2 アプリケーションを管理する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/21/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html、enterprise、グループポリシー、管理性
ms.openlocfilehash: 1eb8b9dc1637daa8d10004ab8c340fe9ae33e38b
ms.sourcegitcommit: 24151cc65bad92d751a8e7a868c102e1121456e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "11057864"
---
# WebView2 アプリケーションを管理する  

[WebView2][WebView2Landing] は、開発者がアプリケーションを構築するために使用するコンポーネントであり、開発者は、ユーザーデバイスで [自己更新 Evergreen WebView2 ランタイム][Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview] を展開して、アプリの電源を入れている可能性があります。  このドキュメントでは、IT 管理者が WebView2 アプリケーションとランタイムを管理する方法について説明します。  IT の管理者と開発者の両方からのフィードバックは、 [WebView2 フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeddback]で歓迎されます。  

## WebView2 のグループポリシー  

IT 管理者は、グループポリシーオブジェクト \ (GPO \) を使って、WebView2 のポリシー設定を構成することができます。  次のポリシーセットは、WebView2 には適用されません。  

*   [Microsoft Edge-更新ポリシー][EdgeUpdatePolicies] は、IT 管理者が WebView2 ランタイムのインストールと更新の側面を管理するために使用できます。  Microsoft Edge ブラウザーと WebView2 ランタイムは、同じ更新メカニズムを使用して更新されます。  などのポリシーがチャネル固有のものである場合 `Update` を除き、ブラウザーと WebView2 の両方のランタイムに適用されます。  たとえば、 `UpdateSuppressed` IT 管理者は、ブラウザーと WebView2 の両方のランタイムの自動更新を非表示にするように、その日の間に時間を設定することができます。  これにより、IT 管理者は、ブラウザーと WebView2 ランタイムの両方に対して1回設定とプロキシを構成し、ネットワーク帯域幅やトラフィックを制御することができます。  IT 管理者は [microsoft edge のガイド][ConfigureMicrosoftEdge] に従って Microsoft edge 更新ポリシーを構成することができます。  
*   [Microsoft Edge-ブラウザーのポリシーは、][EdgeBrowserPolicies] WebView2 アプリケーションには適用されません。  これは、アプリとブラウザーがさまざまなユースケースを持つため、IT 管理者が WebView2 を使用するアプリケーションを認識しない場合があるためです。  WebView2 にブラウザーポリシーを適用すると、意図しない結果が生じることがあります。  たとえば、IT 管理者がブラウザーで JavaScript をブロックし、JavaScript を使っているすべての WebView2 アプリが壊れていることがあります。  
*   \ (近日中に) WebView2 固有のポリシー– WebView2 では、WebView2 の直接管理が適切である場合に、グループポリシーの小さな追加セットが公開されます。  アプリの開発者は、WebView2 の使用を管理するために、独自のグループポリシーを実装することをお勧めします。 IT 管理者は、WebView2 ではなく、アプリを直接管理できます。  

<!-- Links -->  

[Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview]: ./distribution.md#understanding-the-webview2-runtime "WebView2 Runtime と installer (Preview) を使ったアプリケーションの配布について WebView2 |Microsoft ドキュメント"  

[WebView2Landing]: ../index.md "Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  

[EdgeUpdatePolicies]: /deployedge/microsoft-edge-update-policies "Microsoft Edge-更新プログラムのポリシー |Microsoft ドキュメント"  
[EdgeBrowserPolicies]: /deployedge/microsoft-edge-policies "Microsoft Edge-ブラウザーのポリシー |Microsoft ドキュメント"  
[ConfigureMicrosoftEdge]: /deployedge/configure-microsoft-edge "Windows で Microsoft Edge のポリシー設定を構成するMicrosoft ドキュメント"  


[GithubMicrosoftedgeWebviewfeddback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  
