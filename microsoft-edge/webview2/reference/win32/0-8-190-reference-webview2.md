---
description: Microsoft Edge WebView 2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 7ef060f17eb3e7c7bceef3084208de1a533c904a
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879584"
---
# 0.8.355-参照 (WebView2)  

> [!NOTE]
> この参照は、SDK バージョン0.8.355 後のリリースで変更される可能性があります。  最新 API リファレンスについては、[リファレンス](../../webview2-api-reference.md)を参照してください。

Microsoft Edge WebView2 コントロールを使用すると、 [Microsoft edge \ (Chromium \)](https://www.microsoftedgeinsider.com)を使ってアプリケーションの web コンテンツをレンダリングエンジンとしてホストすることができます。  詳細については、「 [Microsoft Edge WebView2 の概要](../../index.md)」および「 [WebView2 の使用を開始](../../gettingstarted/win32.md)する」を参照してください。  [IWebView2WebView](0-8-190/IWebView2WebView.md)は、API の詳細を理解するのに最適な場所です。  

## グローバル  

*   [グローバル](0-8-190/webview2-idl.md)  

## インターフェイス  
*   [IWebView2Deferral](0-8-190/IWebView2Deferral.md)
*   [IWebView2Environment](0-8-190/IWebView2Environment.md)
*   [IWebView2Environment2](0-8-190/IWebView2Environment2.md)
*   [IWebView2Environment3](0-8-190/IWebView2Environment3.md)
*   [IWebView2HttpHeadersCollectionIterator](0-8-190/IWebView2HttpHeadersCollectionIterator.md)
*   [IWebView2HttpRequestHeaders](0-8-190/IWebView2HttpRequestHeaders.md)
*   [IWebView2HttpResponseHeaders](0-8-190/IWebView2HttpResponseHeaders.md)
*   [IWebView2Settings](0-8-190/IWebView2Settings.md)
*   [IWebView2Settings2](0-8-190/IWebView2Settings2.md)
*   [IWebView2WebResourceRequest](0-8-190/IWebView2WebResourceRequest.md)
*   [IWebView2WebResourceRequestedEventArgs2](0-8-190/IWebView2WebResourceRequestedEventArgs2.md)
*   [IWebView2WebResourceResponse](0-8-190/IWebView2WebResourceResponse.md)
*   [IWebView2WebView](0-8-190/IWebView2WebView.md)
*   [IWebView2WebView2](0-8-190/IWebView2WebView2.md)
*   [IWebView2WebView3](0-8-190/IWebView2WebView3.md)
*   [IWebView2WebView4](0-8-190/IWebView2WebView4.md)
*   [IWebView2WebView5](0-8-190/IWebView2WebView5.md)

### イベント引数インターフェイス

*   [IWebView2AcceleratorKeyPressedEventArgs](0-8-190/IWebView2AcceleratorKeyPressedEventArgs.md)
*   [IWebView2DevToolsProtocolEventReceivedEventArgs](0-8-190/IWebView2DevToolsProtocolEventReceivedEventArgs.md)
*   [IWebView2DocumentStateChangedEventArgs](0-8-190/IWebView2DocumentStateChangedEventArgs.md)
*   [IWebView2MoveFocusRequestedEventArgs](0-8-190/IWebView2MoveFocusRequestedEventArgs.md)
*   [IWebView2NavigationCompletedEventArgs](0-8-190/IWebView2NavigationCompletedEventArgs.md)
*   [IWebView2NavigationStartingEventArgs](0-8-190/IWebView2NavigationStartingEventArgs.md)
*   [IWebView2NewVersionAvailableEventArgs](0-8-190/IWebView2NewVersionAvailableEventArgs.md)
*   [IWebView2NewWindowRequestedEventArgs](0-8-190/IWebView2NewWindowRequestedEventArgs.md)
*   [IWebView2PermissionRequestedEventArgs](0-8-190/IWebView2PermissionRequestedEventArgs.md)
*   [IWebView2ProcessFailedEventArgs](0-8-190/IWebView2ProcessFailedEventArgs.md)
*   [IWebView2ScriptDialogOpeningEventArgs](0-8-190/IWebView2ScriptDialogOpeningEventArgs.md)
*   [IWebView2WebMessageReceivedEventArgs](0-8-190/IWebView2WebMessageReceivedEventArgs.md)
*   [IWebView2WebResourceRequestedEventArgs](0-8-190/IWebView2WebResourceRequestedEventArgs.md)

### デリゲートインターフェイス

*   [IWebView2AcceleratorKeyPressedEventHandler](0-8-190/IWebView2AcceleratorKeyPressedEventHandler.md)
*   [IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler](0-8-190/IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler.md)
*   [IWebView2CallDevToolsProtocolMethodCompletedHandler](0-8-190/IWebView2CallDevToolsProtocolMethodCompletedHandler.md)
*   [IWebView2CapturePreviewCompletedHandler](0-8-190/IWebView2CapturePreviewCompletedHandler.md)
*   [IWebView2ContainsFullScreenElementChangedEventHandler](0-8-190/IWebView2ContainsFullScreenElementChangedEventHandler.md)
*   [IWebView2CreateWebView2EnvironmentCompletedHandler](0-8-190/IWebView2CreateWebView2EnvironmentCompletedHandler.md)
*   [IWebView2CreateWebViewCompletedHandler](0-8-190/IWebView2CreateWebViewCompletedHandler.md)
*   [IWebView2DevToolsProtocolEventReceivedEventHandler](0-8-190/IWebView2DevToolsProtocolEventReceivedEventHandler.md)
*   [IWebView2DocumentStateChangedEventHandler](0-8-190/IWebView2DocumentStateChangedEventHandler.md)
*   [IWebView2DocumentTitleChangedEventHandler](0-8-190/IWebView2DocumentTitleChangedEventHandler.md)
*   [IWebView2ExecuteScriptCompletedHandler](0-8-190/IWebView2ExecuteScriptCompletedHandler.md)
*   [IWebView2FocusChangedEventHandler](0-8-190/IWebView2FocusChangedEventHandler.md)
*   [IWebView2MoveFocusRequestedEventHandler](0-8-190/IWebView2MoveFocusRequestedEventHandler.md)
*   [IWebView2NavigationCompletedEventHandler](0-8-190/IWebView2NavigationCompletedEventHandler.md)
*   [IWebView2NavigationStartingEventHandler](0-8-190/IWebView2NavigationStartingEventHandler.md)
*   [IWebView2NewVersionAvailableEventHandler](0-8-190/IWebView2NewVersionAvailableEventHandler.md)
*   [IWebView2NewWindowRequestedEventHandler](0-8-190/IWebView2NewWindowRequestedEventHandler.md)
*   [IWebView2PermissionRequestedEventHandler](0-8-190/IWebView2PermissionRequestedEventHandler.md)
*   [IWebView2ProcessFailedEventHandler](0-8-190/IWebView2ProcessFailedEventHandler.md)
*   [IWebView2ScriptDialogOpeningEventHandler](0-8-190/IWebView2ScriptDialogOpeningEventHandler.md)
*   [IWebView2WebMessageReceivedEventHandler](0-8-190/IWebView2WebMessageReceivedEventHandler.md)
*   [IWebView2WebResourceRequestedEventHandler](0-8-190/IWebView2WebResourceRequestedEventHandler.md)
*   [IWebView2ZoomFactorChangedEventHandler](0-8-190/IWebView2ZoomFactorChangedEventHandler.md)
