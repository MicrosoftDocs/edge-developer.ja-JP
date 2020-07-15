---
description: セキュリティで保護された WebView2 アプリケーションの開発方法を理解する
title: セキュリティで保護された WebView2 アプリケーションを開発するためのベストプラクティス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html、security
ms.openlocfilehash: 998bcf056e6350efc66880a9ad520f6d969af2f1
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879145"
---
# セキュリティで保護された WebView2 アプリケーションを開発するためのベストプラクティス

[WebView2 コントロール](https://docs.microsoft.com/microsoft-edge/webview2/)を使うと、開発者はネイティブアプリケーションで web コンテンツをホストできます。 適切に使用されると、web ベースの UI の使用、web プラットフォームの機能へのアクセス、コードのクロスプラットフォームの共有など、さまざまな利点が提供されます。 Web コンテンツをホストすることで発生する可能性のある脆弱性を回避するために、WebView2 アプリケーションを設計して、web コンテンツとホストアプリケーション間の相互作用を厳密に監視してください。 

1. すべての web コンテンツを安全なセキュリティとして扱う
    - Web メッセージとホストオブジェクトパラメーターを使用する前に検証します。これは、web メッセージとパラメーターの形式が間違っている可能性があり (意図せず、または故意でなく)、アプリが予期せず動作する可能性があるためです。
    - WebView2 内で実行されているドキュメントの出所を常に確認して、コンテンツの信頼性を評価してください。 

2. 汎用プロキシを使う代わりに、特定の web メッセージとホストオブジェクトの操作を設計します。

3. 次のように[ICoreWebView2Settings](../reference/win32/0-9-538/icorewebview2settings.md) (Win32) または[CoreWebView2Settings](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2settings.md) (.net) を変更して、web コンテンツの機能を制限します。
    - `AreHostObjectsAllowed` `false` Web コンテンツがホストオブジェクトにアクセスすることを想定していない場合は、をに設定します。
    - `IsWebMessageEnabled` `false` Web コンテンツがネイティブアプリケーションに web メッセージを投稿しない場合は、をに設定します。 
    - `IsScriptEnabled` `false` Web コンテンツによってスクリプトが実行されない場合 (静的 html コンテンツを表示する場合など) に設定します。
    - `AreDefaultScriptDialogsEnabled` `false` Web コンテンツが表示されない場合、またはダイアログボックスが表示されない場合は、をに設定 `alert` `prompt` します。

4. `NavigationStarting` `FrameNavigationStarting` 次に示すように、イベントを使用して、新しいページの原点に基づいて設定を更新します。
    1. アプリケーションが特定のページに移動できないようにするには、これらのイベントを使用して、ページまたはフレームのナビゲーションを確認してからブロックします。 
    2. 新しいページに移動するときは、上で説明したように、 [ICoreWebView2Settings](../reference/win32/0-9-538/icorewebview2settings.md) (Win32) または[CoreWebView2Settings](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2settings.md) (.net) のプロパティ値の調整が必要になることがあります。

5. 新しいドキュメントに移動するときは、 `ContentLoading` を使用して、公開されているホストオブジェクトを削除し `RemoveHostObjectFromScript` ます。 