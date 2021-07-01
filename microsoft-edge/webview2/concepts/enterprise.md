---
description: WebView2 アプリケーションを管理する方法を理解する
title: WebView2 アプリケーションの管理
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/21/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、Webview2、Webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ HTML、エンタープライズ、グループ ポリシー、管理性
ms.openlocfilehash: f32488a26f3e3c926517b0e40e6aac6a309e42b8
ms.sourcegitcommit: 5ae09b1ad6cd576c9fec12538b23cd849861f2b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2021
ms.locfileid: "11627965"
---
# <a name="managing-webview2-applications"></a>WebView2 アプリケーションの管理  

[WebView2][WebView2Landing] は、開発者がアプリケーションのビルドに使用するコンポーネントであり、開発者はアプリケーションに電力を供給するために、ユーザー デバイスに自己更新 [の Evergreen WebView2 ランタイム][Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview] を展開できます。  このドキュメントでは、IT 管理者が WebView2 アプリケーションとランタイムを管理する方法について説明します。  WEBView2 Feedback repo では、IT 管理者と開発者 [の両方からのフィードバックを歓迎します][GithubMicrosoftedgeWebviewfeddback]。  

## <a name="group-policies-for-webview2"></a>WebView2 のグループ ポリシー  

IT 管理者は、グループ ポリシー オブジェクト \(GPO\) を使用して WebView2 のポリシー設定を構成できます。  次の一連のポリシーは、WebView2 には適用できません。  

*   [Microsoft Edge -][EdgeUpdatePolicies]更新ポリシーは、IT 管理者が WebView2 ランタイムのインストールおよび更新の側面を管理するために使用できます。  ブラウザー Microsoft Edge WebView2 ランタイムは、同じ更新メカニズムを使用して更新されます。  チャネル固有のポリシーがない限り、ブラウザーと `Update` WebView2 ランタイムの両方に適用されます。  たとえば、IT 管理者は、ブラウザーと WebView2 ランタイムの両方の自動更新を抑制するために、毎日の時間を `UpdateSuppressed` 設定できます。  これにより、IT 管理者は、ブラウザーと WebView2 ランタイムの両方の設定とプロキシを 1 回構成して、ネットワーク帯域幅/トラフィックを制御したり、その他の目的で構成することができます。  IT 管理者は、Microsoft Edge[の][ConfigureMicrosoftEdge]ガイドに従って、Microsoft Edgeポリシーを構成できます。  
*   [Microsoft Edge - ブラウザー ポリシー][EdgeBrowserPolicies]は WebView2 アプリケーションには適用されません。  これは、アプリとブラウザーの使用例が異なって、IT 管理者が WebView2 を使用するアプリケーションを認識していない可能性があるからです。  WebView2 にブラウザー ポリシーを適用すると、意図しない結果が生じ得る可能性があります。  たとえば、IT 管理者はブラウザーで JavaScript をブロックし、JavaScript を使用しているすべての WebView2 アプリが壊れている可能性があります。  
*   [WebView2 固有のポリシーを][WebView2Policies] 使用すると、WebView2 を直接管理できます。  ただし、WebView2 を直接管理する代わりに管理者がアプリを管理しやすいため、開発者は WebView2 の使用を管理するために独自のグループ ポリシーを実装することをお勧めします。  

<!-- Links -->  

[Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview]: ./distribution.md#understanding-the-webview2-runtime "WebView2 ランタイムとインストーラー (プレビュー) - WebView2 を使用したアプリケーションの配布について|Microsoft Docs"  

[WebView2Landing]: ../index.md "WebView2 Microsoft Edge (プレビュー) の概要|Microsoft Docs"  

[EdgeUpdatePolicies]: /deployedge/microsoft-edge-update-policies "Microsoft Edge - ポリシーの更新|Microsoft Docs"  
[EdgeBrowserPolicies]: /deployedge/microsoft-edge-policies "Microsoft Edge - ブラウザー ポリシー|Microsoft Docs"  
[ConfigureMicrosoftEdge]: /deployedge/configure-microsoft-edge "サーバー Microsoft Edgeポリシー設定を構成Windows |Microsoft Docs"  
[WebView2Policies]: /deployedge/microsoft-edge-webview-policies "Microsoft EdgeWebView2 ポリシー ドキュメント |Microsoft Docs" 

[GithubMicrosoftedgeWebviewfeddback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック - MicrosoftEdge/WebViewFeedback | GitHub"  
