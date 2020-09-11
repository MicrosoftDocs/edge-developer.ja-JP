---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 92fad0c93e4942a92f5940834b0057043491b539
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010209"
---
# 0.9.579-Reference (WebView2 Win32 C++)  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]

Microsoft Edge WebView2 コントロールを使用すると、 [Microsoft edge \ (Chromium \)](https://www.microsoftedgeinsider.com) を使ってアプリケーションの web コンテンツをレンダリングエンジンとしてホストすることができます。  詳細については、「 [Microsoft Edge WebView2 の概要](../../index.md)」および「 [WebView2 の使用を開始](../../gettingstarted/win32.md)する」を参照してください。  [ICoreWebView2](0-9-538/ICoreWebView2.md) は、API の詳細を理解するのに最適な場所です。  

## グローバル  

*   [グローバル](0-9-538/webview2-idl.md)  

## インターフェイス  
*   [ICoreWebView2](0-9-538/icorewebview2.md)
*   [ICoreWebView2Controller](0-9-538/icorewebview2controller.md)
*   [ICoreWebView2Deferral](0-9-538/icorewebview2deferral.md)
*   [ICoreWebView2DevToolsProtocolEventReceiver](0-9-538/icorewebview2devtoolsprotocoleventreceiver.md)
*   [ICoreWebView2Environment](0-9-538/icorewebview2environment.md)
*   [ICoreWebView2EnvironmentOptions](0-9-538/icorewebview2environmentoptions.md)
*   [ICoreWebView2HttpHeadersCollectionIterator](0-9-538/icorewebview2httpheaderscollectioniterator.md)
*   [ICoreWebView2HttpRequestHeaders](0-9-538/icorewebview2httprequestheaders.md)
*   [ICoreWebView2HttpResponseHeaders](0-9-538/icorewebview2httpresponseheaders.md)
*   [ICoreWebView2Settings](0-9-538/icorewebview2settings.md)
*   [ICoreWebView2WebResourceRequest](0-9-538/icorewebview2webresourcerequest.md)
*   [ICoreWebView2WebResourceResponse](0-9-538/icorewebview2webresourceresponse.md)

### イベント引数

*   [ICoreWebView2AcceleratorKeyPressedEventArgs](0-9-538/icorewebview2acceleratorkeypressedeventargs.md)
*   [ICoreWebView2ContentLoadingEventArgs](0-9-538/icorewebview2contentloadingeventargs.md)
*   [ICoreWebView2DevToolsProtocolEventReceivedEventArgs](0-9-538/icorewebview2devtoolsprotocoleventreceivedeventargs.md)
*   [ICoreWebView2MoveFocusRequestedEventArgs](0-9-538/icorewebview2movefocusrequestedeventargs.md)
*   [ICoreWebView2NavigationCompletedEventArgs](0-9-538/icorewebview2navigationcompletedeventargs.md)
*   [ICoreWebView2NavigationStartingEventArgs](0-9-538/icorewebview2navigationstartingeventargs.md)
*   [ICoreWebView2NewWindowRequestedEventArgs](0-9-538/icorewebview2newwindowrequestedeventargs.md)
*   [ICoreWebView2PermissionRequestedEventArgs](0-9-538/icorewebview2permissionrequestedeventargs.md)
*   [ICoreWebView2ProcessFailedEventArgs](0-9-538/icorewebview2processfailedeventargs.md)
*   [ICoreWebView2ScriptDialogOpeningEventArgs](0-9-538/icorewebview2scriptdialogopeningeventargs.md)
*   [ICoreWebView2SourceChangedEventArgs](0-9-538/icorewebview2sourcechangedeventargs.md)
*   [ICoreWebView2WebMessageReceivedEventArgs](0-9-538/icorewebview2webmessagereceivedeventargs.md)
*   [ICoreWebView2WebResourceRequestedEventArgs](0-9-538/icorewebview2webresourcerequestedeventargs.md)

### デリゲート

*   [ICoreWebView2AcceleratorKeyPressedEventHandler](0-9-538/icorewebview2acceleratorkeypressedeventhandler.md)
*   [ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler](0-9-538/icorewebview2addscripttoexecuteondocumentcreatedcompletedhandler.md)
*   [ICoreWebView2CallDevToolsProtocolMethodCompletedHandler](0-9-538/icorewebview2calldevtoolsprotocolmethodcompletedhandler.md)
*   [ICoreWebView2CapturePreviewCompletedHandler](0-9-538/icorewebview2capturepreviewcompletedhandler.md)
*   [ICoreWebView2ContainsFullScreenElementChangedEventHandler](0-9-538/icorewebview2containsfullscreenelementchangedeventhandler.md)
*   [ICoreWebView2ContentLoadingEventHandler](0-9-538/icorewebview2contentloadingeventhandler.md)
*   [ICoreWebView2CreateCoreWebView2ControllerCompletedHandler](0-9-538/icorewebview2createcorewebview2controllercompletedhandler.md)
*   [ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](0-9-538/icorewebview2createcorewebview2environmentcompletedhandler.md)
*   [ICoreWebView2DevToolsProtocolEventReceivedEventHandler](0-9-538/icorewebview2devtoolsprotocoleventreceivedeventhandler.md)
*   [ICoreWebView2DocumentTitleChangedEventHandler](0-9-538/icorewebview2documenttitlechangedeventhandler.md)
*   [ICoreWebView2ExecuteScriptCompletedHandler](0-9-538/icorewebview2executescriptcompletedhandler.md)
*   [ICoreWebView2FocusChangedEventHandler](0-9-538/icorewebview2focuschangedeventhandler.md)
*   [ICoreWebView2HistoryChangedEventHandler](0-9-538/icorewebview2historychangedeventhandler.md)
*   [ICoreWebView2MoveFocusRequestedEventHandler](0-9-538/icorewebview2movefocusrequestedeventhandler.md)
*   [ICoreWebView2NavigationCompletedEventHandler](0-9-538/icorewebview2navigationcompletedeventhandler.md)
*   [ICoreWebView2NavigationStartingEventHandler](0-9-538/icorewebview2navigationstartingeventhandler.md)
*   [ICoreWebView2NewBrowserVersionAvailableEventHandler](0-9-538/icorewebview2newbrowserversionavailableeventhandler.md)
*   [ICoreWebView2NewWindowRequestedEventHandler](0-9-538/icorewebview2newwindowrequestedeventhandler.md)
*   [ICoreWebView2PermissionRequestedEventHandler](0-9-538/icorewebview2permissionrequestedeventhandler.md)
*   [ICoreWebView2ProcessFailedEventHandler](0-9-538/icorewebview2processfailedeventhandler.md)
*   [ICoreWebView2ScriptDialogOpeningEventHandler](0-9-538/icorewebview2scriptdialogopeningeventhandler.md)
*   [ICoreWebView2SourceChangedEventHandler](0-9-538/icorewebview2sourcechangedeventhandler.md)
*   [ICoreWebView2WebMessageReceivedEventHandler](0-9-538/icorewebview2webmessagereceivedeventhandler.md)
*   [ICoreWebView2WebResourceRequestedEventHandler](0-9-538/icorewebview2webresourcerequestedeventhandler.md)
*   [ICoreWebView2WindowCloseRequestedEventHandler](0-9-538/icorewebview2windowcloserequestedeventhandler.md)
*   [ICoreWebView2ZoomFactorChangedEventHandler](0-9-538/icorewebview2zoomfactorchangedeventhandler.md)

### 試験的な

*   [ICoreWebView2Experimental](0-9-538/icorewebview2experimental.md)
*   [ICoreWebView2ExperimentalCompositionController](0-9-538/icorewebview2experimentalcompositioncontroller.md)
*   [ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler](0-9-538/icorewebview2experimentalcreatecorewebview2compositioncontrollercompletedhandler.md)
*   [ICoreWebView2ExperimentalCursorChangedEventHandler](0-9-538/icorewebview2experimentalcursorchangedeventhandler.md)
*   [ICoreWebView2ExperimentalEnvironment](0-9-538/icorewebview2experimentalenvironment.md)
*   [ICoreWebView2ExperimentalEnvironmentOptions](0-9-538/icorewebview2experimentalenvironmentoptions.md)
*   [ICoreWebView2ExperimentalNewWindowRequestedEventArgs](0-9-538/icorewebview2experimentalnewwindowrequestedeventargs.md)
*   [ICoreWebView2ExperimentalPointerInfo](0-9-538/icorewebview2experimentalpointerinfo.md)
*   [ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs](0-9-538/icorewebview2experimentalwebresourceresponsereceivedeventargs.md)
*   [ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler](0-9-538/icorewebview2experimentalwebresourceresponsereceivedeventargspopulateresponsecontentcompletedhandler.md)
*   [ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler](0-9-538/icorewebview2experimentalwebresourceresponsereceivedeventhandler.md)
*   [ICoreWebView2ExperimentalWindowFeatures](0-9-538/icorewebview2experimentalwindowfeatures.md)
