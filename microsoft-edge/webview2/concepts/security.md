---
description: セキュリティで保護された WebView2 アプリケーションの開発方法を理解する
title: セキュリティで保護された WebView2 アプリケーションを開発するためのベストプラクティス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/14/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html、security
ms.openlocfilehash: d53417cc1ac98b44565692edbaec06216f7c110b
ms.sourcegitcommit: 61cc15d2fc89aee3e09cec48ef1e0e5bbf8d289a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2020
ms.locfileid: "11119003"
---
# セキュリティで保護された WebView2 アプリケーションを開発するためのベストプラクティス  

[WebView2 コントロール][Webview2Main]を使うと、開発者はネイティブアプリケーションで web コンテンツをホストできます。 適切に使用されると、web ベースの UI の使用、web プラットフォームの機能へのアクセス、コードのクロスプラットフォームの共有など、さまざまな利点が提供されます。  Web コンテンツをホストすることで発生する可能性のある脆弱性を回避するために、WebView2 アプリケーションを設計して、web コンテンツとホストアプリケーション間の相互作用を厳密に監視してください。  

1.  すべての web コンテンツを安全ではないとして扱う。  
    *   Web メッセージとパラメーターを検証してから各パラメーターを使うことができます。これは、web メッセージとパラメーターの形式が間違っている可能性があります。
    *   WebView2 内で実行されているドキュメントの出所を常に確認して、コンテンツの信頼性を評価してください。  
1.  汎用プロキシを使う代わりに、特定の web メッセージとホストオブジェクトの操作を設計します。  
1.  次のオプションを設定して、 [ICoreWebView2Settings (Win32)][Webview2ReferenceWin32Icorewebview2settings] または [CoreWebView2Settings (.net)][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2settings]を変更することにより、web コンテンツの機能を制限します。  
    *   `AreHostObjectsAllowed` `false` Web コンテンツがホストオブジェクトにアクセスすることを想定していない場合は、をに設定します。  
    *   Web `IsWebMessageEnabled` `false` コンテンツによってネイティブアプリケーションに web メッセージが投稿されないようにする場合は、をに設定します。  
    *   `IsScriptEnabled` `false` Web コンテンツがスクリプトを実行することを想定していない場合は、をに設定します (静的 html コンテンツを表示する場合など)。  
    *   `AreDefaultScriptDialogsEnabled` `false` Web コンテンツが表示されない場合、またはダイアログボックスを表示しない場合は、をに設定 `alert` `prompt` します。  
1.  次の手順では、およびイベントを使用して、 `NavigationStarting` `FrameNavigationStarting` 新しいページの起点に基づいて設定を更新します。  
    1.  アプリケーションが特定のページに移動できないようにするには、イベントを使用して、ページまたはフレームのナビゲーションを確認してからブロックします。  
    1.  新しいページに移動するときは、前に説明したように、 [ICoreWebView2Settings (Win32)][Webview2ReferenceWin32Icorewebview2settings] または [CoreWebView2Settings (.net)][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2settings] でプロパティ値を調整する必要がある場合があります。  
1.  新しいドキュメントに移動するときは、 `ContentLoading` を使用して、公開されているホストオブジェクトを削除し `RemoveHostObjectFromScript` ます。  

<!--## Security

Always check the Source property of the WebView before using `ExecuteScript`, `PostWebMessageAsJson`, `PostWebMessageAsString`, or any other method to send information into the WebView. The WebView may have navigated to another page via the end user interacting with the page or script in the page causing navigation. Similarly, be very careful with `AddScriptToExecuteOnDocumentCreated`. All future `navigations` run the same script and if it provides access to information intended only for a certain origin, any HTML document may have access.

When examining the result of an `ExecuteScript` method call, a `WebMessageReceived` event, always check the Source of the sender, or any other mechanism of receiving information from an HTML document in a WebView validate the URI of the HTML document is what you expect.

When constructing a message to send into a WebView, prefer using `PostWebMessageAsJson` and construct the JSON string parameter using a JSON library. This avoids any potential accidents of encoding information into a JSON string or script and ensure no attacker controlled input can modify the rest of the JSON message or run arbitrary script. -->  

<!-- links -->  

[Webview2Main]: ../index.md "Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  

[Webview2ReferenceWin32Icorewebview2settings]: /microsoft-edge/webview2/reference/win32/icorewebview2settings "インターフェイス ICoreWebView2Settings |Microsoft ドキュメント"  

[Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2settings]: /dotnet/api/microsoft.web.webview2.core.corewebview2settings "CoreWebView2Settings クラス (WebView2 の場合) |Microsoft ドキュメント"  
