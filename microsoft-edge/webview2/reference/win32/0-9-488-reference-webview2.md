---
description: Microsoft Edge WebView 2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリの Microsoft Edge WebView 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 8c0511dc0e7327ebc2f6ee3bac34f62716dff472
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697883"
---
# 0.9.515-参照 (WebView2)  

> [!NOTE]
> この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。 最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../webview2-api-reference.md)を参照してください。

Microsoft Edge WebView2 コントロールを使用すると、 [Microsoft edge \ (Chromium \)](https://www.microsoftedgeinsider.com)を使ってアプリケーションの web コンテンツをレンダリングエンジンとしてホストすることができます。  詳細については、「 [Microsoft Edge WebView2 の概要](../../index.md)」および「 [WebView2 の使用を開始](../../gettingstarted/win32.md)する」を参照してください。  [ICoreWebView2](0-9-488/ICoreWebView2.md)は、API の詳細を理解するのに最適な場所です。  

## グローバル  

*   [グローバル](0-9-488/webview2-idl.md)  

## インターフェイス  
*   [ICoreWebView2](0-9-488/icorewebview2.md)
*   [ICoreWebView2Controller](0-9-488/icorewebview2controller.md)
*   [ICoreWebView2Deferral](0-9-488/icorewebview2deferral.md)
*   [ICoreWebView2DevToolsProtocolEventReceiver](0-9-488/icorewebview2devtoolsprotocoleventreceiver.md)
*   [ICoreWebView2Environment](0-9-488/icorewebview2environment.md)
*   [ICoreWebView2EnvironmentOptions](0-9-488/icorewebview2environmentoptions.md)
*   [ICoreWebView2HttpHeadersCollectionIterator](0-9-488/icorewebview2httpheaderscollectioniterator.md)
*   [ICoreWebView2HttpRequestHeaders](0-9-488/icorewebview2httprequestheaders.md)
*   [ICoreWebView2HttpResponseHeaders](0-9-488/icorewebview2httpresponseheaders.md)
*   [ICoreWebView2Settings](0-9-488/icorewebview2settings.md)
*   [ICoreWebView2WebResourceRequest](0-9-488/icorewebview2webresourcerequest.md)
*   [ICoreWebView2WebResourceResponse](0-9-488/icorewebview2webresourceresponse.md)

### イベント引数

*   [ICoreWebView2AcceleratorKeyPressedEventArgs](0-9-488/icorewebview2acceleratorkeypressedeventargs.md)
*   [ICoreWebView2ContentLoadingEventArgs](0-9-488/icorewebview2contentloadingeventargs.md)
*   [ICoreWebView2DevToolsProtocolEventReceivedEventArgs](0-9-488/icorewebview2devtoolsprotocoleventreceivedeventargs.md)
*   [ICoreWebView2MoveFocusRequestedEventArgs](0-9-488/icorewebview2movefocusrequestedeventargs.md)
*   [ICoreWebView2NavigationCompletedEventArgs](0-9-488/icorewebview2navigationcompletedeventargs.md)
*   [ICoreWebView2NavigationStartingEventArgs](0-9-488/icorewebview2navigationstartingeventargs.md)
*   [ICoreWebView2NewWindowRequestedEventArgs](0-9-488/icorewebview2newwindowrequestedeventargs.md)
*   [ICoreWebView2PermissionRequestedEventArgs](0-9-488/icorewebview2permissionrequestedeventargs.md)
*   [ICoreWebView2ProcessFailedEventArgs](0-9-488/icorewebview2processfailedeventargs.md)
*   [ICoreWebView2ScriptDialogOpeningEventArgs](0-9-488/icorewebview2scriptdialogopeningeventargs.md)
*   [ICoreWebView2SourceChangedEventArgs](0-9-488/icorewebview2sourcechangedeventargs.md)
*   [ICoreWebView2WebMessageReceivedEventArgs](0-9-488/icorewebview2webmessagereceivedeventargs.md)
*   [ICoreWebView2WebResourceRequestedEventArgs](0-9-488/icorewebview2webresourcerequestedeventargs.md)

### デリゲート

*   [ICoreWebView2AcceleratorKeyPressedEventHandler](0-9-488/icorewebview2acceleratorkeypressedeventhandler.md)
*   [ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler](0-9-488/icorewebview2addscripttoexecuteondocumentcreatedcompletedhandler.md)
*   [ICoreWebView2CallDevToolsProtocolMethodCompletedHandler](0-9-488/icorewebview2calldevtoolsprotocolmethodcompletedhandler.md)
*   [ICoreWebView2CapturePreviewCompletedHandler](0-9-488/icorewebview2capturepreviewcompletedhandler.md)
*   [ICoreWebView2ContainsFullScreenElementChangedEventHandler](0-9-488/icorewebview2containsfullscreenelementchangedeventhandler.md)
*   [ICoreWebView2ContentLoadingEventHandler](0-9-488/icorewebview2contentloadingeventhandler.md)
*   [ICoreWebView2CreateCoreWebView2ControllerCompletedHandler](0-9-488/icorewebview2createcorewebview2controllercompletedhandler.md)
*   [ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](0-9-488/icorewebview2createcorewebview2environmentcompletedhandler.md)
*   [ICoreWebView2DevToolsProtocolEventReceivedEventHandler](0-9-488/icorewebview2devtoolsprotocoleventreceivedeventhandler.md)
*   [ICoreWebView2DocumentTitleChangedEventHandler](0-9-488/icorewebview2documenttitlechangedeventhandler.md)
*   [ICoreWebView2ExecuteScriptCompletedHandler](0-9-488/icorewebview2executescriptcompletedhandler.md)
*   [ICoreWebView2FocusChangedEventHandler](0-9-488/icorewebview2focuschangedeventhandler.md)
*   [ICoreWebView2HistoryChangedEventHandler](0-9-488/icorewebview2historychangedeventhandler.md)
*   [ICoreWebView2MoveFocusRequestedEventHandler](0-9-488/icorewebview2movefocusrequestedeventhandler.md)
*   [ICoreWebView2NavigationCompletedEventHandler](0-9-488/icorewebview2navigationcompletedeventhandler.md)
*   [ICoreWebView2NavigationStartingEventHandler](0-9-488/icorewebview2navigationstartingeventhandler.md)
*   [ICoreWebView2NewBrowserVersionAvailableEventHandler](0-9-488/icorewebview2newbrowserversionavailableeventhandler.md)
*   [ICoreWebView2NewWindowRequestedEventHandler](0-9-488/icorewebview2newwindowrequestedeventhandler.md)
*   [ICoreWebView2PermissionRequestedEventHandler](0-9-488/icorewebview2permissionrequestedeventhandler.md)
*   [ICoreWebView2ProcessFailedEventHandler](0-9-488/icorewebview2processfailedeventhandler.md)
*   [ICoreWebView2ScriptDialogOpeningEventHandler](0-9-488/icorewebview2scriptdialogopeningeventhandler.md)
*   [ICoreWebView2SourceChangedEventHandler](0-9-488/icorewebview2sourcechangedeventhandler.md)
*   [ICoreWebView2WebMessageReceivedEventHandler](0-9-488/icorewebview2webmessagereceivedeventhandler.md)
*   [ICoreWebView2WebResourceRequestedEventHandler](0-9-488/icorewebview2webresourcerequestedeventhandler.md)
*   [ICoreWebView2WindowCloseRequestedEventHandler](0-9-488/icorewebview2windowcloserequestedeventhandler.md)
*   [ICoreWebView2ZoomFactorChangedEventHandler](0-9-488/icorewebview2zoomfactorchangedeventhandler.md)

### 試験的な

*   [ICoreWebView2ExperimentalCompositionController](0-9-488/icorewebview2experimentalcompositioncontroller.md)
*   [ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler](0-9-488/icorewebview2experimentalcreatecorewebview2compositioncontrollercompletedhandler.md)
*   [ICoreWebView2ExperimentalCursorChangedEventHandler](0-9-488/icorewebview2experimentalcursorchangedeventhandler.md)
*   [ICoreWebView2ExperimentalEnvironment](0-9-488/icorewebview2experimentalenvironment.md)
*   [ICoreWebView2ExperimentalPointerInfo](0-9-488/icorewebview2experimentalpointerinfo.md)
