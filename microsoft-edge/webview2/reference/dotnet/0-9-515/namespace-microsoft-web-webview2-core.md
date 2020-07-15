---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 の基本
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: e9270705ff6c72167185bddfea6f6f310ebc2e3d
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877666"
---
# 0.9.515-WebView2 の名前空間 

> [!NOTE]
> この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。 最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[CoreWebView2CapturePreviewImageFormat](#corewebview2capturepreviewimageformat) | CoreWebView2CapturePreview メソッドで使用される画像形式。
[CoreWebView2KeyEventKind](#corewebview2keyeventkind) | AcceleratorKeyPressed イベントをトリガーしたキーイベントの種類です。
[CoreWebView2MoveFocusReason](#corewebview2movefocusreason) | フォーカスを移動する理由。
[CoreWebView2PermissionKind](#corewebview2permissionkind) | アクセス許可要求の種類。
[CoreWebView2PermissionState](#corewebview2permissionstate) | アクセス許可要求に対する応答。
[CoreWebView2ProcessFailedKind](#corewebview2processfailedkind) | CoreWebView2ProcessFailedEventHandler クラスで使われているプロセスエラーの種類。
[CoreWebView2ScriptDialogKind](#corewebview2scriptdialogkind) | CoreWebView2ScriptDialogOpeningEventHandler クラスで使用される JavaScript ダイアログの種類。
[CoreWebView2WebErrorStatus](#corewebview2weberrorstatus) | Web ナビゲーションのエラー状態の値。
[CoreWebView2WebResourceContext](#corewebview2webresourcecontext) | Web リソース要求コンテキストの列挙。
CoreWebView2 | WebView2 では、最新の Edge web ブラウザー技術を使用して、web コンテンツをホストすることができます。
CoreWebView2AcceleratorKeyPressedEventArgs | AcceleratorKeyPressed イベントのイベント引数。
CoreWebView2ContentLoadingEventArgs | ContentLoading イベントのイベント引数。
CoreWebView2Controller | このクラスは、CoreWebView2 オブジェクトの所有者であり、ウィンドウ化やコンポジションに関連する、サイズ変更、表示/非表示、フォーカス、およびその他の機能のサポートを提供します。
CoreWebView2Deferral | このクラスは、GetDeferral メソッドによる保留の取得をサポートするイベント引数で保留を完了するために使われます。
CoreWebView2DevToolsProtocolEventReceivedEventArgs | DevToolsProtocolEventReceived イベントのイベント引数。
CoreWebView2DevToolsProtocolEventReceiver | 特定の DevTools プロトコルイベント用に受信者が作成され、そのイベントのサブスクライブとサブスクライブ解除を行うことができます。
CoreWebView2Environment | これは、WebView2 環境を表します。
CoreWebView2EnvironmentOptions | WebView2 環境の作成に使用するオプション。
CoreWebView2MoveFocusRequestedEventArgs | MoveFocusRequested されたイベントのイベント引数。
CoreWebView2NavigationCompletedEventArgs | NavigationCompleted イベントのイベント引数。
CoreWebView2NavigationStartingEventArgs | NavigationStarting イベントのイベント引数。
CoreWebView2NewWindowRequestedEventArgs | NewWindowRequested イベントのイベント引数。
CoreWebView2PermissionRequestedEventArgs | PermissionRequested されたイベントのイベント引数。
CoreWebView2ProcessFailedEventArgs | ProcessFailed イベントのイベント引数。
CoreWebView2ScriptDialogOpeningEventArgs | Scriptな開始イベントのイベント引数。
CoreWebView2Settings | WebView 機能を有効、無効、または変更するプロパティを定義します。
CoreWebView2SourceChangedEventArgs | SourceChanged イベントのイベント引数。
CoreWebView2WebMessageReceivedEventArgs | WebMessageReceived イベントのイベント引数。
CoreWebView2WebResourceRequestedEventArgs | WebResourceRequested イベントのイベント引数。
EdgeNotFoundException | エッジのインストールが見つからない場合にスローされる例外。
CoreWebView2PhysicalKeyStatus | Win32 キーイベントに指定された LPARAM にパックされた情報を表す構造体。

## Members

#### CoreWebView2CapturePreviewImageFormat 

> 列挙型[CoreWebView2CapturePreviewImageFormat](#corewebview2capturepreviewimageformat)

 値                         | 説明
--------------------------------|---------------------------------------------
.Png            | PNG 画像形式。
Jpeg            | JPEG イメージ形式。

CoreWebView2CapturePreview メソッドで使用される画像形式。

#### CoreWebView2KeyEventKind 

> 列挙型[CoreWebView2KeyEventKind](#corewebview2keyeventkind)

 値                         | 説明
--------------------------------|---------------------------------------------
KeyDown            | ウィンドウメッセージ WM_KEYDOWN に対応します。
KeyUp            | ウィンドウメッセージ WM_KEYUP に対応します。
SystemKeyDown            | ウィンドウメッセージ WM_SYSKEYDOWN に対応します。
SystemKeyUp            | ウィンドウメッセージ WM_SYSKEYUP に対応します。

AcceleratorKeyPressed イベントをトリガーしたキーイベントの種類です。

#### CoreWebView2MoveFocusReason 

> 列挙型[CoreWebView2MoveFocusReason](#corewebview2movefocusreason)

 値                         | 説明
--------------------------------|---------------------------------------------
計画的            | コード設定による WebView へのフォーカス。
Next            | タブトラバーサルを前方に移動するためにフォーカスを移動する。
Previous            | タブトラバーサルに戻るためにフォーカスを移動する。

フォーカスを移動する理由。

#### CoreWebView2PermissionKind 

> 列挙型[CoreWebView2PermissionKind](#corewebview2permissionkind)

 値                         | 説明
--------------------------------|---------------------------------------------
UnknownPermission            | 不明な権限。
マイク            | オーディオをキャプチャするためのアクセス許可。
カメラ            | ビデオをキャプチャするためのアクセス許可。
位置情報            | 位置情報へのアクセス許可。
通知            | Web 通知を送信するためのアクセス許可。
その他のセンサー            | 汎用センサーへのアクセス許可。
クリップボードの読み取り            | ユーザーのジェスチャを使わずにシステムクリップボードを読み取る権限。

アクセス許可要求の種類。

#### CoreWebView2PermissionState 

> 列挙型[CoreWebView2PermissionState](#corewebview2permissionstate)

 値                         | 説明
--------------------------------|---------------------------------------------
既定値            | 既定のブラウザー動作を使用します。通常はユーザーに判断を求めます。
許可            | 権限の要求を許可します。
拒否            | 権限の要求を拒否します。

アクセス許可要求に対する応答。

#### CoreWebView2ProcessFailedKind 

> 列挙型[CoreWebView2ProcessFailedKind](#corewebview2processfailedkind)

 値                         | 説明
--------------------------------|---------------------------------------------
Browserproces            | ブラウザープロセスが予期せず終了したことを示します。
Renderprocessex            | レンダリング処理が予期せず終了したことを示します。
RenderProcessUnresponsive が応答しません            | レンダリングプロセスが応答しなくなったことを示します。

CoreWebView2ProcessFailedEventHandler クラスで使われているプロセスエラーの種類。

#### CoreWebView2ScriptDialogKind 

> 列挙型[CoreWebView2ScriptDialogKind](#corewebview2scriptdialogkind)

 値                         | 説明
--------------------------------|---------------------------------------------
アラート            | ウィンドウで呼び出されるダイアログ。警告 JavaScript 関数。
確認            | ウィンドウを通じて呼び出されるダイアログ。 JavaScript 関数を確認してください。
プロンプト            | Window というプロンプトで呼び出されるダイアログ。
Beforeunload            | Beforeunload JavaScript 関数を使用して呼び出されたダイアログ。

CoreWebView2ScriptDialogOpeningEventHandler クラスで使用される JavaScript ダイアログの種類。

#### CoreWebView2WebErrorStatus 

> 列挙型[CoreWebView2WebErrorStatus](#corewebview2weberrorstatus)

 値                         | 説明
--------------------------------|---------------------------------------------
Unknown            | 不明なエラーが発生しました。
名前の間違い            | SSL 証明書の共通名が web アドレスと一致しません。
CertificateExpired 切れ            | SSL 証明書の有効期限が切れています。
ClientCertificateContainsErrors            | SSL クライアント証明書にエラーが含まれています。
CertificateRevoked            | SSL 証明書が失効しています。
CertificateIsInvalid            | SSL 証明書が無効になっている可能性があります。これは、 &ndash; 証明書がホスト名の公開キーピンと一致しなかったことを意味します。証明書が信頼されていない機関によって署名されている、または脆弱な署名アルゴリズムを使用している場合、証明書が名前の制限を超えている証明書、証明書の有効期間が長い、証明書の透過情報がない、証明書が[従来のシマンテックルート](https://security.googleblog.com/2018/03/distrust-of-symantec-pki-immediate.html)にチェーンされている。
ServerUnreachable 不可            | ホストに到達できません。
タイムアウト            | 接続がタイムアウトしました。
ErrorHttpInvalidServerResponse            | サーバーが無効または認識不能な応答を返しました。
ConnectionAborted            | 接続が中止されました。
ConnectionReset            | 接続がリセットされました。
外し            | インターネット接続が切断されました。
CannotConnect            | 宛先に接続できません。
HostNameNotResolved            | 指定されたホスト名を解決できませんでした。
OperationCanceled            | 操作が取り消されました。
RedirectFailed            | 要求のリダイレクトに失敗しました。
UnexpectedError            | 予期しないエラーが発生しました。

Web ナビゲーションのエラー状態の値。

#### CoreWebView2WebResourceContext 

> 列挙型[CoreWebView2WebResourceContext](#corewebview2webresourcecontext)

 値                         | 説明
--------------------------------|---------------------------------------------
すべて            | すべてのリソース。
Document            | ドキュメントリソース。
スタイルシート            | CSS リソース。
画像            | 画像リソース。
メディア            | その他のメディアリソース (ビデオなど)。
フォント            | フォントリソース。
スクリプト            | スクリプトリソース。
XmlHttpRequest            | XML HTTP 要求。
フェッチ            | API 通信を取得します。
TextTrack            | TextTrack のリソース。
EventSource            | EventSource API の通信。
WebSocket            | WebSocket API 通信。
ノート            | Web App マニフェスト。
SignedExchange            | 署名された HTTP 交換。
Ping.exe            | Ping 要求。
Csp・ Ationreport            | CSP 違反レポート。
Other            | その他のリソース。

Web リソース要求コンテキストの列挙。

