---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 の基本
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft のようになります。
ms.openlocfilehash: 9786e7b2062532fcb0d982afb0c864bddc1ad125
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010118"
---
# 0.9.579-WebView2 の名前空間 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[CoreWebView2CapturePreviewImageFormat](#corewebview2capturepreviewimageformat) | CoreWebView2CapturePreview メソッドで使用される画像形式。
[CoreWebView2KeyEventKind](#corewebview2keyeventkind) | AcceleratorKeyPressed イベントをトリガーしたキーイベントの種類です。
[CoreWebView2MouseEventKind](#corewebview2mouseeventkind) | WebView に送信されるマウスイベントの種類を伝えるために、SendMouseInput で使われるマウスイベントの種類。
[CoreWebView2MouseEventVirtualKeys](#corewebview2mouseeventvirtualkeys) | SendMouseInput の CoreWebView2MouseEventKind に関連付けられたマウスイベントの仮想キー。
[CoreWebView2MoveFocusReason](#corewebview2movefocusreason) | フォーカスを移動する理由。
[CoreWebView2PermissionKind](#corewebview2permissionkind) | アクセス許可要求の種類。
[CoreWebView2PermissionState](#corewebview2permissionstate) | アクセス許可要求に対する応答。
[CoreWebView2PointerEventKind](#corewebview2pointereventkind) | WebView に送信されるポインターイベントの種類を伝えるために Sendpointer 入力で使われるポインターイベントの種類です。
[CoreWebView2ProcessFailedKind](#corewebview2processfailedkind) | CoreWebView2ProcessFailedEventHandler クラスで使われているプロセスエラーの種類。
[CoreWebView2ScriptDialogKind](#corewebview2scriptdialogkind) | CoreWebView2ScriptDialogOpeningEventHandler クラスで使用される JavaScript ダイアログの種類。
[CoreWebView2WebErrorStatus](#corewebview2weberrorstatus) | Web ナビゲーションのエラー状態の値。
[CoreWebView2WebResourceContext](#corewebview2webresourcecontext) | Web リソース要求コンテキストの列挙。
CoreWebView2 | WebView2 では、最新の Edge web ブラウザー技術を使用して、web コンテンツをホストすることができます。
CoreWebView2AcceleratorKeyPressedEventArgs | AcceleratorKeyPressed イベントのイベント引数。
CoreWebView2CompositionController | このクラスは、CoreWebView2Controller クラスの拡張機能であり、ビジュアルホストをサポートします。
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
CoreWebView2PointerInfo | これは主に、win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO オブジェクトを組み合わせたものです。
CoreWebView2ProcessFailedEventArgs | ProcessFailed イベントのイベント引数。
CoreWebView2ScriptDialogOpeningEventArgs | Scriptな開始イベントのイベント引数。
CoreWebView2Settings | WebView 機能を有効、無効、または変更するプロパティを定義します。
CoreWebView2SourceChangedEventArgs | SourceChanged イベントのイベント引数。
CoreWebView2WebMessageReceivedEventArgs | WebMessageReceived イベントのイベント引数。
CoreWebView2WebResourceRequestedEventArgs | WebResourceRequested イベントのイベント引数。
CoreWebView2WebResourceResponseReceivedEventArgs | WebResourceResponseReceived イベントのイベント引数。
CoreWebView2WindowFeatures | WebView ポップアップウィンドウのウィンドウ機能。
EdgeNotFoundException | エッジのインストールが見つからない場合にスローされる例外。
CoreWebView2Matrix4x4 | この変換は、CreateCoreWebView2PointerInfoFromPointerId を呼び出したときに適切な座標を計算するために使われます。
CoreWebView2PhysicalKeyStatus | Win32 キーイベントに指定された LPARAM にパックされた情報を表す構造体。

## Members

#### CoreWebView2CapturePreviewImageFormat 

CoreWebView2CapturePreview メソッドで使用される画像形式。

> 列挙型 [CoreWebView2CapturePreviewImageFormat](#corewebview2capturepreviewimageformat)

 値                         | 説明
--------------------------------|---------------------------------------------
.Png            | PNG 画像形式。
Jpeg            | JPEG イメージ形式。

#### CoreWebView2KeyEventKind 

AcceleratorKeyPressed イベントをトリガーしたキーイベントの種類です。

> 列挙型 [CoreWebView2KeyEventKind](#corewebview2keyeventkind)

 値                         | 説明
--------------------------------|---------------------------------------------
KeyDown            | ウィンドウメッセージ WM_KEYDOWN に対応します。
KeyUp            | ウィンドウメッセージ WM_KEYUP に対応します。
SystemKeyDown            | ウィンドウメッセージ WM_SYSKEYDOWN に対応します。
SystemKeyUp            | ウィンドウメッセージ WM_SYSKEYUP に対応します。

#### CoreWebView2MouseEventKind 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

WebView に送信されるマウスイベントの種類を伝えるために、SendMouseInput で使われるマウスイベントの種類。

> 列挙型 [CoreWebView2MouseEventKind](#corewebview2mouseeventkind)

 値                         | 説明
--------------------------------|---------------------------------------------
水平ホイール            | マウスの水平ホイールスクロールイベント、WM_MOUSEHWHEEL。
LeftButtonDoubleClick            | [左] ボタンをダブルクリックすると、[マウスイベント] が WM_LBUTTONDBLCLK ます。
左ボタン            | [左] ボタンのマウスイベント、WM_LBUTTONDOWN。
左ボタンを上            | [左] ボタンのマウスイベント、WM_LBUTTONUP。
も            | マウスの終了イベント、WM_MOUSELEAVE。
MiddleButtonDoubleClick            | 中央ボタン [マウスイベント]、[WM_MBUTTONDBLCLK] の順にダブルクリックします。
MiddleButtonDown            | 中央ボタンのマウスイベント、WM_MBUTTONDOWN。
MiddleButtonUp            | 中央ボタン上のマウスイベント、WM_MBUTTONUP。
移動            | マウス移動イベント、WM_MOUSEMOVE。
RightButtonDoubleClick            | 右ボタン [マウスイベント]、[WM_RBUTTONDBLCLK] の順にダブルクリックします。
右ボタン            | 右ボタンのマウスイベント、WM_RBUTTONDOWN。
右 Buttonup            | マウスの右上にあるイベントの [WM_RBUTTONUP] をクリックします。
Wheel            | マウスホイールスクロールイベント、WM_MOUSEWHEEL。
XButtonDoubleClick            | 第1または第2の X ボタンをダブルクリックすると、[マウスイベント] が WM_XBUTTONDBLCLK ます。
XButtonDown            | 最初または2番目の X ボタンのマウスイベントを WM_XBUTTONDOWN します。
XButtonUp            | 最初または2番目の X ボタンのマウスイベントを WM_XBUTTONUP します。

#### CoreWebView2MouseEventVirtualKeys 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

SendMouseInput の CoreWebView2MouseEventKind に関連付けられたマウスイベントの仮想キー。

> 列挙型 [CoreWebView2MouseEventVirtualKeys](#corewebview2mouseeventvirtualkeys)

 値                         | 説明
--------------------------------|---------------------------------------------
なし            | 追加のキーが押されていません。
[左] ボタン            | マウスの左ボタンが押されています。 MK_LBUTTON。
[右] ボタン            | マウスの右ボタンが押されて MK_RBUTTON ます。
Shift            | SHIFT キーを押しながら MK_SHIFT ます。
コントロール            | CTRL キーを押しながら MK_CONTROL ます。
MiddleButton            | マウスの中央ボタンが押されて MK_MBUTTON。
XButton1            | 最初の X ボタンが押されて MK_XBUTTON1。
XButton2            | 第2の X ボタンが押され、MK_XBUTTON2 ます。

#### CoreWebView2MoveFocusReason 

フォーカスを移動する理由。

> 列挙型 [CoreWebView2MoveFocusReason](#corewebview2movefocusreason)

 値                         | 説明
--------------------------------|---------------------------------------------
計画的            | コード設定による WebView へのフォーカス。
Next            | タブトラバーサルを前方に移動するためにフォーカスを移動する。
Previous            | タブトラバーサルに戻るためにフォーカスを移動する。

#### CoreWebView2PermissionKind 

アクセス許可要求の種類。

> 列挙型 [CoreWebView2PermissionKind](#corewebview2permissionkind)

 値                         | 説明
--------------------------------|---------------------------------------------
UnknownPermission            | 不明な権限。
マイク            | オーディオをキャプチャするためのアクセス許可。
カメラ            | ビデオをキャプチャするためのアクセス許可。
位置情報            | 位置情報へのアクセス許可。
通知            | Web 通知を送信するためのアクセス許可。
その他のセンサー            | 汎用センサーへのアクセス許可。
クリップボードの読み取り            | ユーザーのジェスチャを使わずにシステムクリップボードを読み取る権限。

#### CoreWebView2PermissionState 

アクセス許可要求に対する応答。

> 列挙型 [CoreWebView2PermissionState](#corewebview2permissionstate)

 値                         | 説明
--------------------------------|---------------------------------------------
既定値            | 既定のブラウザー動作を使用します。通常はユーザーに判断を求めます。
許可            | 権限の要求を許可します。
拒否            | 権限の要求を拒否します。

#### CoreWebView2PointerEventKind 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

WebView に送信されるポインターイベントの種類を伝えるために Sendpointer 入力で使われるポインターイベントの種類です。

> 列挙型 [CoreWebView2PointerEventKind](#corewebview2pointereventkind)

 値                         | 説明
--------------------------------|---------------------------------------------
ライセンス認証            | WM_POINTERACTIVATE に対応します。
Down            | WM_POINTERDOWN に対応します。
Enter            | WM_POINTERENTER に対応します。
も            | WM_POINTERLEAVE に対応します。
Up            | WM_POINTERUP に対応します。
Update            | WM_POINTERUPDATE に対応します。

#### CoreWebView2ProcessFailedKind 

CoreWebView2ProcessFailedEventHandler クラスで使われているプロセスエラーの種類。

> 列挙型 [CoreWebView2ProcessFailedKind](#corewebview2processfailedkind)

 値                         | 説明
--------------------------------|---------------------------------------------
Browserproces            | ブラウザープロセスが予期せず終了したことを示します。
Renderprocessex            | レンダリング処理が予期せず終了したことを示します。
RenderProcessUnresponsive が応答しません            | レンダリングプロセスが応答しなくなったことを示します。

#### CoreWebView2ScriptDialogKind 

CoreWebView2ScriptDialogOpeningEventHandler クラスで使用される JavaScript ダイアログの種類。

> 列挙型 [CoreWebView2ScriptDialogKind](#corewebview2scriptdialogkind)

 値                         | 説明
--------------------------------|---------------------------------------------
アラート            | ウィンドウで呼び出されるダイアログ。警告 JavaScript 関数。
確認            | ウィンドウを通じて呼び出されるダイアログ。 JavaScript 関数を確認してください。
プロンプト            | Window というプロンプトで呼び出されるダイアログ。
Beforeunload            | Beforeunload JavaScript 関数を使用して呼び出されたダイアログ。

#### CoreWebView2WebErrorStatus 

Web ナビゲーションのエラー状態の値。

> 列挙型 [CoreWebView2WebErrorStatus](#corewebview2weberrorstatus)

 値                         | 説明
--------------------------------|---------------------------------------------
Unknown            | 不明なエラーが発生しました。
名前の間違い            | SSL 証明書の共通名が web アドレスと一致しません。
CertificateExpired 切れ            | SSL 証明書の有効期限が切れています。
ClientCertificateContainsErrors            | SSL クライアント証明書にエラーが含まれています。
CertificateRevoked            | SSL 証明書が失効しています。
CertificateIsInvalid            | SSL 証明書が無効になっている可能性があります。これは、 &ndash; 証明書がホスト名の公開キーピンと一致しなかったことを意味します。証明書が信頼されていない機関によって署名されている、または脆弱な署名アルゴリズムを使用している場合、証明書が名前の制限を超えている証明書、証明書の有効期間が長い、証明書の透過情報がない、証明書が [従来のシマンテックルート](https://security.googleblog.com/2018/03/distrust-of-symantec-pki-immediate.html)にチェーンされている。
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

#### CoreWebView2WebResourceContext 

Web リソース要求コンテキストの列挙。

> 列挙型 [CoreWebView2WebResourceContext](#corewebview2webresourcecontext)

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

