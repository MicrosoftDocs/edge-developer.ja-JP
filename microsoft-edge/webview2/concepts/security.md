---
description: セキュリティで保護された WebView2 アプリケーションを開発する方法を理解する
title: 安全な WebView2 アプリケーションを開発するためのベスト プラクティス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/14/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、Webview2、Webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ html、セキュリティ
ms.openlocfilehash: d53417cc1ac98b44565692edbaec06216f7c110b
ms.sourcegitcommit: 61cc15d2fc89aee3e09cec48ef1e0e5bbf8d289a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2020
ms.locfileid: "11119003"
---
# 安全な WebView2 アプリケーションを開発するためのベスト プラクティス  

[WebView2 コントロールを使用][Webview2Main]すると、開発者はネイティブ アプリケーションで Web コンテンツをホストできます。 正しく使用すると、Web コンテンツのホスティングには、Web ベースの UI の使用、Web プラットフォームの機能へのアクセス、コードクロスプラットフォームの共有など、いくつかの利点があります。  Web コンテンツのホストから発生する可能性のある脆弱性を回避するには、Web コンテンツとホスト アプリケーションの間の相互作用を密接に監視するために、必ず WebView2 アプリケーションを設計してください。  

1.  すべての Web コンテンツを安全でないと扱います。  
    *   Web メッセージとパラメーターの形式が正しく設定されていない \(意図しない、または悪意を持って\)、アプリが予期せず動作する可能性があるため、Web メッセージとホスト オブジェクト パラメーターを使用する前に検証します。
    *   WebView2 内で実行されているドキュメントの原点を常に確認し、コンテンツの信頼性を評価します。  
1.  汎用プロキシを使用する代わりに、特定の Web メッセージとホスト オブジェクトの操作を設計します。  
1.  [ICoreWebView2Settings (Win32)][Webview2ReferenceWin32Icorewebview2settings]または[CoreWebView2Settings (.NET)][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2settings]を変更して、Web コンテンツ機能を制限するには、次のオプションを設定します。  
    *   Web `AreHostObjectsAllowed` コンテンツ `false` がホスト オブジェクトにアクセスしない場合は、に設定します。  
    *   Web コンテンツが Web メッセージをネイティブ アプリケーションに投稿しない場合は `IsWebMessageEnabled` `false` 、に設定します。  
    *   Web コンテンツでスクリプト \(静的な html コンテンツ\を表示する場合など) を実行しない場合は、に `IsScriptEnabled` `false` 設定します。  
    *   Web コンテンツが表示またはダイアログ ボックスに表示されない場合は、 `AreDefaultScriptDialogsEnabled` `false` `alert` に `prompt` 設定します。  
1.  次の手順では、and `NavigationStarting` イベントを使用して、新しいページの原点に基づいて `FrameNavigationStarting` 設定を更新します。  
    1.  アプリケーションで特定のページへの移動を防止するには、イベントを使用してページまたはフレームのナビゲーションを確認してからブロックします。  
    1.  新しいページに移動する場合は、前述のように [ICoreWebView2Settings (Win32)][Webview2ReferenceWin32Icorewebview2settings] または [CoreWebView2Settings (.NET)][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2settings] のプロパティ値を調整する必要があります。  
1.  新しいドキュメントに移動する場合は、イベントを使用して公開 `ContentLoading` されているホスト オブジェクトを削除します `RemoveHostObjectFromScript` 。  

<!--## Security

Always check the Source property of the WebView before using `ExecuteScript`, `PostWebMessageAsJson`, `PostWebMessageAsString`, or any other method to send information into the WebView. The WebView may have navigated to another page via the end user interacting with the page or script in the page causing navigation. Similarly, be very careful with `AddScriptToExecuteOnDocumentCreated`. All future `navigations` run the same script and if it provides access to information intended only for a certain origin, any HTML document may have access.

When examining the result of an `ExecuteScript` method call, a `WebMessageReceived` event, always check the Source of the sender, or any other mechanism of receiving information from an HTML document in a WebView validate the URI of the HTML document is what you expect.

When constructing a message to send into a WebView, prefer using `PostWebMessageAsJson` and construct the JSON string parameter using a JSON library. This avoids any potential accidents of encoding information into a JSON string or script and ensure no attacker controlled input can modify the rest of the JSON message or run arbitrary script. -->  

<!-- links -->  

[Webview2Main]: ../index.md "WebView2 Microsoft Edge (プレビュー) の概要|Microsoft Docs"  

[Webview2ReferenceWin32Icorewebview2settings]: /microsoft-edge/webview2/reference/win32/icorewebview2settings "インターフェイス ICoreWebView2Settings |Microsoft Docs"  

[Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2settings]: /dotnet/api/microsoft.web.webview2.core.corewebview2settings "CoreWebView2Settings クラス (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
