---
ms.assetid: e56172c0-b635-4c02-8e0c-56bf8cb4c164
description: Web ブラウザーの動作をプログラムやスクリプトで制御できるようにするワイヤプロトコルである WebDriver の使用を開始する方法について説明します。
title: WebDriver (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: edge、web 開発、html、css、javascript、開発者、webdriver、selenium、テスト
ms.openlocfilehash: 0a6ef78103852234a6b52dfe88e60273cc3bd3d0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570799"
---
# WebDriver (EdgeHTML)
W3C [Webdriver](https://www.w3.org/TR/webdriver/) API は、プラットフォームと言語に依存しないインターフェイスとワイヤプロトコルで、プログラムまたはスクリプトが web ブラウザーの動作を制御できるようにします。

WebDriver を使うと、開発者は、ユーザーの操作をシミュレートする自動テストを作成できます。 WebDriver はブラウザーで実行されている JavaScript の機能と情報にアクセスできないため、これは JavaScript 単体テストとは異なり、ユーザーイベントや OS レベルのイベントをより正確にシミュレートすることができます。 WebDriver は、1回のテストセッションで複数のウィンドウ、タブ、web ページ間でテストを管理することもできます。

Microsoft Edge 用 WebDriver (EdgeHTML) の使用を開始する方法は次のとおりです。

WebDriver の Microsoft Edge (EdgeHTML) 実装は、W3C [webdriver](https://www.w3.org/TR/webdriver/)仕様と[JSON Wire Protocol](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol)の両方をサポートしており、既存のテストとの下位互換性があります。

## Microsoft Edge 用 WebDriver の概要 (EdgeHTML)
* Windows 10 をインストールします。
* Windows と Microsoft Edge (EdgeHTML) のビルド用の適切な[Microsoft WebDriver](https://developer.microsoft.com/microsoft-edge/tools/webdriver/)サーバーをダウンロードします。
* 選択した WebDriver 言語バインドをダウンロードします。 [Selenium のすべての言語バインドは、Microsoft Edge (EdgeHTML) をサポート](https://docs.seleniumhq.org/download/)しています。

> [!NOTE]
> [Microsoft Edge (EdgeHTML) のフィードバック & サポート](https://developer.microsoft.com/microsoft-edge/support/)については、ヘルプ、問題の報告、ファイル機能の要求を参照してください。


## WebDriver を使用する
Microsoft Edge (EdgeHTML) で WebDriver の使用を開始するには、次のサンプルをご確認ください。

* [C \ # コードサンプル](https://gist.github.com/InstyleVII/baf25274c55e891076d5#file-webdriver-cs)ブラウザーウィンドウを開くには、bing.com に移動し、' webdriver ' (GitHub Gist) を検索します。

## WebDriver server コマンドラインフラグ
WebDriver server のコマンドラインフラグの一覧です。

| 名前    | 説明                                                                                                      | 利用可能なリリース |
|:--------|:-----------------------------------------------------------------------------------------------------------------|:------------------|
| 提供    | WebDriver server に使用するホスト IP (既定: localhost)                                                     | 14393             |
| ポート    | WebDriver server に使用するポート (既定: 17556)                                                            | 14393             |
| package | WebDriver server によって起動されるアプリケーションの ApplicationUserModelId (AUMID)                        | 14393             |
| 詳細な | WebDriver サーバーによって送信された要求と応答要求の出力                                             | 14393             |
| silent  | 何も出力しません                                                                                                  | 15063             |
| version | Microsoft Webdriver .exe のバージョンを出力します                                                                    | 17763             |
| 勧告     | W3C WebDriver protocol を使用する (既定オプション)                                                                      | 17763             |
| jwp     | JSON Wire protocol を使用する                                                                                           | 17763             |
| アップ | パッケージ用の WebDriver server によって設定された一時データとレジストリキーをクリーンアップします。 その他のパラメーターは無視されます。 | 17763             |

## W3C WebDriver
[W3C WebDriver 仕様](https://www.w3.org/TR/webdriver/)のコマンド単位のサポート。

### 機能
| Capability                       | Key                       | ステータス                   | 利用可能なリリース |
|:---------------------------------|:--------------------------|:-------------------------|:------------------|
| ブラウザー名                     | "browserName"             | サポートされています                | 17763             |
| ブラウザーのバージョン                  | "いいね!"          | サポートされています                | 17763             |
| プラットフォーム名                    | "platformName"            | サポートされています                | 17763             |
| 安全でない TLS 証明書を受け入れる | "acceptInsecureCerts"     | サポートされていない &nbsp;       | なし               |
| ページ読み込みの計画               | "pageLoadStrategy"        | サポートされています                | 17763             |
| プロキシの構成              | プロキシ                   | サポートされていない &nbsp;       | なし               |
| ウィンドウの寸法/配置  | "setWindowRect"           | サポートされています                | 17763             |
| セッションタイムアウト構成   | アウト                | サポートされています                | 17763             |
| 処理されないプロンプトの動作        | "unhandledPromptBehavior" | 部分的に &nbsp; サポートされる | 17763             |
| InPrivate                        | "ms: inPrivate"            | サポートされています                | 17763             |
| 拡張機能のパス                  | "ms: extensionPaths"       | サポートされています                | 17763             |
| スタートページ                       | "ms: startPage"            | サポートされています                | 17763             |

### ロケーター戦略
| ロケーター戦略                                                        | ステータス    | 利用可能なリリース |
|:------------------------------------------------------------------------|:----------|:------------------|
| [CSS セレクター](https://www.w3.org/TR/webdriver/#css-selectors)         | サポートされています | 17763             |
| [テキストをリンクする](https://www.w3.org/TR/webdriver/#link-text)                 | サポートされています | 17763             |
| [部分的なリンクテキスト](https://www.w3.org/TR/webdriver/#partial-link-text) | サポートされています | 17763             |
| [タグ名](https://www.w3.org/TR/webdriver/#tag-name)                   | サポートされています | 17763             |
| [X](https://www.w3.org/TR/webdriver/#xpath)                         | サポートされています | 17763             |

### コマンド
| HTTP メソッド | URI テンプレート                                                   | コマンド                                                                                   | ステータス             | 利用可能なリリース |
|:------------|:---------------------------------------------------------------|:------------------------------------------------------------------------------------------|:-------------------|:----------------  |
| POST        | /セッション                                                       | [新しいセッション](https://www.w3.org/TR/webdriver/#new-session)                               | サポートされています          | 17763             |
| DELETE      | セッション id/{セッション id}                                          | [セッションの削除](https://www.w3.org/TR/webdriver/#delete-session)                         | サポートされています          | 17763             |
| GET         | 全                                                        | [ステータス](https://www.w3.org/TR/webdriver/#status)                                         | サポートされています          | 17763             |
| GET         | /セッション id/タイムアウト                                 | [タイムアウトを取得する](https://www.w3.org/TR/webdriver/#get-timeouts)                             | サポートされています          | 17763             |
| POST        | /セッション id/タイムアウト                                 | [タイムアウトを設定する](https://www.w3.org/TR/webdriver/#set-timeouts)                             | サポートされています          | 17763             |
| POST        | /セッション id}/url                                      | [移動先](https://www.w3.org/TR/webdriver/#navigate-to)                               | サポートされています          | 17763             |
| GET         | /セッション id}/url                                      | [現在の URL を取得する](https://www.w3.org/TR/webdriver/#get-current-url)                       | サポートされています          | 17763             |
| POST        | /セッション id/バックアップ                                     | [戻る](https://www.w3.org/TR/webdriver/#back)                                             | サポートされています          | 17763             |
| POST        | /セッション id}/forward                                  | [Forward](https://www.w3.org/TR/webdriver/#forward)                                       | サポートされています          | 17763             |
| POST        | /セッション id/更新                                  | [Refresh](https://www.w3.org/TR/webdriver/#refresh)                                       | サポートされています          | 17763             |
| GET         | /セッション id/タイトル                                    | [タイトルを取得する](https://www.w3.org/TR/webdriver/#get-title)                                   | サポートされています          | 17763             |
| GET         | /セッション id}/window                                   | [ウィンドウハンドルを取得する](https://www.w3.org/TR/webdriver/#get-window-handle)                   | サポートされています          | 17763             |
| DELETE      | /セッション id}/window                                   | [ウィンドウを閉じる](https://www.w3.org/TR/webdriver/#close-window)                             | サポートされています          | 17763             |
| POST        | /セッション id}/window                                   | [ウィンドウに切り替える](https://www.w3.org/TR/webdriver/#switch-to-window)                     | サポートされています          | 17763             |
| GET         | /セッション id/ウィンドウのウィンドウ/ハンドル                           | [ウィンドウハンドルを取得する](https://www.w3.org/TR/webdriver/#get-window-handles)                 | サポートされています          | 17763             |
| POST        | /セッション id/フレーム                                    | [レイアウト枠に切り替える](https://www.w3.org/TR/webdriver/#switch-to-frame)                       | サポートされています          | 17763             |
| POST        | /セッション id/フレーム/親                             | [親フレームに切り替える](https://www.w3.org/TR/webdriver/#switch-to-parent-frame)         | サポートされています          | 17763             |
| GET         | /セッション id}/window/rect                              | [ウィンドウの Rect を取得する](https://www.w3.org/TR/webdriver/#get-window-rect)                       | サポートされています          | 17763             |
| POST        | /セッション id}/window/rect                              | [ウィンドウの Rect を設定する](https://www.w3.org/TR/webdriver/#set-window-rect)                       | サポートされています          | 17763             |
| POST        | /セッション id/ウィンドウのウィンドウ                          | [ウィンドウを最大化する](https://www.w3.org/TR/webdriver/#maximize-window)                       | サポートされています          | 17763             |
| POST        | セッション id/ウィンドウを 1/最小化する                          | [ウィンドウを最小化する](https://www.w3.org/TR/webdriver/#minimize-window)                       | サポートされています          | 17763             |
| POST        | /セッション id/ウィンドウのウィンドウ                        | [全画面表示ウィンドウ](https://www.w3.org/TR/webdriver/#fullscreen-window)                   | サポートされていない &nbsp; | なし               |
| GET         | /セッション id}/要素/アクティブ                           | [アクティブな要素を取得する](https://www.w3.org/TR/webdriver/#get-active-element)                 | サポートされています          | 17763             |
| POST        | /{session id}/要素                                  | [Find 要素](https://www.w3.org/TR/webdriver/#find-element)                             | サポートされています          | 17763             |
| POST        | /{セッション id}/要素                                 | [要素を検索する](https://www.w3.org/TR/webdriver/#find-elements)                           | サポートされています          | 17763             |
| POST        | /セッション id}/要素/{要素 id}/要素             | [要素から要素を検索する](https://www.w3.org/TR/webdriver/#find-element-from-element)   | サポートされています          | 17763             |
| POST        | /セッション id}/要素/{要素 id}/要素            | [要素から要素を検索する](https://www.w3.org/TR/webdriver/#find-elements-from-element) | サポートされています          | 17763             |
| GET         | /セッション id/イベント id/要素/{element id}/選択            | [要素が選択されています](https://www.w3.org/TR/webdriver/#is-element-selected)               | サポートされています          | 17763             |
| GET         | セッション id/イベント id/要素/{要素 id}/属性/{名}    | [Get Element 属性](https://www.w3.org/TR/webdriver/#get-element-attribute)           | サポートされています          | 17763             |
| GET         | セッション id/イベント id/要素/{要素 id}/プロパティ/{名}     | [Get Element プロパティ](https://www.w3.org/TR/webdriver/#get-element-property)             | サポートされています          | 17763             |
| GET         | /セッション id}/要素/{element id}/css/{property name} | [要素 CSS の値を取得する](https://www.w3.org/TR/webdriver/#get-element-css-value)           | サポートされています          | 17763             |
| GET         | /セッション id}/要素/{element id}/text                | [要素のテキストを取得する](https://www.w3.org/TR/webdriver/#get-element-text)                     | サポートされています          | 17763             |
| GET         | /セッション id}/要素/{element id}/name                | [要素タグ名を取得する](https://www.w3.org/TR/webdriver/#get-element-tag-name)             | サポートされています          | 17763             |
| GET         | /セッション id}/要素/{element id}/rect                | [要素の Rect を取得する](https://www.w3.org/TR/webdriver/#get-element-rect)                     | サポートされています          | 17763             |
| GET         | /セッション id/{session id}/enabled/{element id}/enabled             | [要素が有効になっている](https://www.w3.org/TR/webdriver/#is-element-enabled)                 | サポートされています          | 17763             |
| POST        | /セッション id/イベント id/要素/{element id}/クリック               | [要素のクリック](https://www.w3.org/TR/webdriver/#element-click)                           | サポートされています          | 17763             |
| POST        | /セッション id}/要素/{element id}/clear               | [要素のクリア](https://www.w3.org/TR/webdriver/#element-clear)                           | サポートされています          | 17763             |
| POST        | /セッション id/{セッション id}/イベント送信            | [要素送信キー](https://www.w3.org/TR/webdriver/#element-send-keys)                   | サポートされています          | 17763             |
| GET         | /セッション id}/source                                   | [ページのソースを取得する](https://www.w3.org/TR/webdriver/#get-page-source)                       | サポートされています          | 17763             |
| POST        | /セッション id/execute/sync                             | [スクリプトを実行する](https://www.w3.org/TR/webdriver/#execute-script)                         | サポートされています          | 17763             |
| POST        | /セッション id/execute/async                            | [Async スクリプトを実行する](https://www.w3.org/TR/webdriver/#execute-async-script)             | サポートされています          | 17763             |
| GET         | /セッション id/cookie                                   | [すべての Cookie を取得する](https://www.w3.org/TR/webdriver/#get-all-cookies)                       | サポートされています          | 17763             |
| GET         | /セッション id/名前/名前/名前/{名}                            | [名前付き Cookie を取得する](https://www.w3.org/TR/webdriver/#get-named-cookie)                     | サポートされています          | 17763             |
| POST        | /セッション id/cookie                                   | [Cookie を追加する](https://www.w3.org/TR/webdriver/#add-cookie)                                 | サポートされています          | 17763             |
| DELETE      | /セッション id/名前/名前/名前/{名}                            | [Cookie を削除する](https://www.w3.org/TR/webdriver/#delete-cookie)                           | サポートされています          | 17763             |
| DELETE      | /セッション id/cookie                                   | [すべての Cookie を削除する](https://www.w3.org/TR/webdriver/#delete-all-cookies)                 | サポートされています          | 17763             |
| POST        | /セッション id/操作                                  | [アクションを実行する](https://www.w3.org/TR/webdriver/#perform-actions)                       | サポートされています          | 17763             |
| DELETE      | /セッション id/操作                                  | [リリースアクション](https://www.w3.org/TR/webdriver/#release-actions)                       | サポートされています          | 17763             |
| POST        | /セッション id/イベント id/通知/無視                            | [通知を無視する](https://www.w3.org/TR/webdriver/#dismiss-alert)                           | サポートされています          | 17763             |
| POST        | /セッション id/イベント id/alert/accept                             | [通知を受信する](https://www.w3.org/TR/webdriver/#accept-alert)                             | サポートされています          | 17763             |
| GET         | セッション id/イベント id}/alert/text                               | [通知テキストを取得する](https://www.w3.org/TR/webdriver/#get-alert-text)                         | サポートされています          | 17763             |
| POST        | セッション id/イベント id}/alert/text                               | [通知テキストを送信する](https://www.w3.org/TR/webdriver/#send-alert-text)                       | サポートされています          | 17763             |
| GET         | /セッション id}/スクリーンショット                               | [スクリーンショットを撮る](https://www.w3.org/TR/webdriver/#take-screenshot)                       | サポートされています          | 17763             |
| GET         | セッション id/セッション id}/スクリーン放送の id}                  | [要素の取得のスクリーンショット](https://www.w3.org/TR/webdriver/#take-element-screenshot)       | サポートされています          | 17763             |

## JSON Wire Protocol
[JSON Wire Protocol](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol)のコマンド単位のサポート。

### コマンド
| HTTP メソッド | パス                                                                                                                                                         | ステータス             | 利用可能なリリース |
|:------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------|:------------------|
| GET         | [全](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#status)                                                                               | サポートされています          | 10240             |
| POST        | [/セッション](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#session-1)                                                                           | サポートされています          | 10240             |
| GET         | [/セッション](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessions)                                                                           | サポートされています          | 10240             |
| GET         | [/セッション/: sessionId](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionid)                                                         | サポートされています          | 10240             |
| DELETE      | [/セッション/: sessionId](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionid)                                                         | サポートされています          | 10240             |
| POST        | [/セッション/: sessionId/タイムアウト](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtimeouts)                                        | サポートされています          | 10240             |
| POST        | [/セッション/: sessionId/タイムアウト/async_script](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtimeoutsasync_script)               | サポートされていない &nbsp; | なし               |
| POST        | [/セッション/: sessionId/タイムアウト/implicit_wait](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtimeoutsimplicit_wait)             | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/window_handle](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindow_handle)                              | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/window_handles](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindow_handles)                            | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/url](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidurl)                                                  | サポートされています          | 10240             |
| POST        | [/セッション/: sessionId/url](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidurl)                                                  | サポートされています          | 10240             |
| POST        | [/セッション/: sessionId/転送](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidforward)                                          | サポートされています          | 10240             |
| POST        | [/セッション/: sessionId/バック](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidback)                                                | サポートされています          | 10240             |
| POST        | [/セッション/: セッション Id/更新](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidrefresh)                                          | サポートされています          | 10240             |
| POST        | [/セッション/: sessionId/実行](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidexecute)                                          | サポートされています          | 10240             |
| POST        | [/セッション/: sessionId/execute_async](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidexecute_async)                              | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/のスクリーンショット](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidscreenshot)                                    | サポートされています          | 10240             |
| GET         | [/セッション/: sessionId/ime/available_engines](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidimeavailable_engines)               | サポートされていない &nbsp; | なし               |
| GET         | [/セッション/: sessionId/ime/active_engine](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidimeactive_engine)                       | サポートされていない &nbsp; | なし               |
| GET         | [/セッション/: sessionId/ime/ライセンス認証](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidimeactivated)                               | サポートされていない &nbsp; | なし               |
| POST        | [/セッション/: sessionId/ime/非アクティブ化](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidimedeactivate)                             | サポートされていない &nbsp; | なし               |
| POST        | [/セッション/: sessionId/ime/activate](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidimeactivate)                                 | サポートされていない &nbsp; | なし               |
| POST        | [/セッション/: sessionId/フレーム](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidframe)                                              | サポートされています          | 10586             |
| POST        | [/セッション/: sessionId/フレーム/親](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidframeparent)                                 | サポートされています          | 10586             |
| POST        | [/セッション/: sessionId/ウィンドウ](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindow)                                            | サポートされています          | 10586             |
| DELETE      | [/セッション/: sessionId/ウィンドウ](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindow)                                            | サポートされています          | 10586             |
| POST        | [/セッション/: sessionId/ウィンドウ/: windowHandle/size](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindowwindowhandlesize)         | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/ウィンドウ/: windowHandle/size](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindowwindowhandlesize)         | サポートされています          | 10586             |
| POST        | [/セッション/: sessionId/ウィンドウ/: windowHandle/position](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindowwindowhandleposition) | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/ウィンドウ/: windowHandle/position](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindowwindowhandleposition) | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/ウィンドウ/: windowHandle/最大化](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindowwindowhandlemaximize) | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/cookie](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidcookie)                                            | サポートされています          | 10586             |
| POST        | [/セッション/: sessionId/cookie](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidcookie)                                            | サポートされています          | 10240             |
| DELETE      | [/セッション/: sessionId/cookie](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidcookie)                                            | サポートされています          | 10586             |
| DELETE      | [/セッション/: sessionId/クッキー/: name](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidcookiename)                                  | サポートされています          | 10240             |
| GET         | [/セッション/: sessionId/ソース](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsource)                                            | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId}/タイトル](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtitle)                                             | サポートされています          | 10240             |
| POST        | [/セッション/: sessionId/要素](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelement)                                          | サポートされています          | 10586             |
| POST        | [/セッション/: sessionId/要素](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelements)                                        | サポートされています          | 10586             |
| POST        | [/セッション/: sessionId/要素/アクティブ](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementactive)                             | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/要素/: id](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementid)                                    | サポートされていない &nbsp; | なし               |
| POST        | [/セッション/: sessionId/要素/: id/要素](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidelement)                     | サポートされています          | 10586             |
| POST        | [/セッション/: sessionId/要素/: id/要素](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidelements)                   | サポートされています          | 10586             |
| POST        | [/セッション/: sessionId/要素/: id/クリック](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidclick)                         | サポートされています          | 10240             |
| POST        | [/セッション/: sessionId/要素/: id/submit](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidsubmit)                       | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/要素/: id/text](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidtext)                           | サポートされています          | 10240             |
| POST        | [/セッション/: sessionId/要素/: id/値](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidvalue)                         | サポートされています          | 10240             |
| POST        | [/セッション/: セッション Id/キー](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidkeys)                                                | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/要素/: id/name](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidname)                           | サポートされています          | 10240             |
| POST        | [/セッション/: sessionId/要素/: id/clear](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidclear)                         | サポートされています          | 10240             |
| GET         | [/セッション/: sessionId/要素/: id/選択](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidselected)                   | サポートされています          | 10240             |
| GET         | [/セッション/: sessionId/要素/: id/enabled](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidenabled)                     | サポートされています          | 10240             |
| GET         | [/セッション/: sessionId/要素/: id/attribute/: name](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidattribute/:name)     | サポートされています          | 10240             |
| GET         | [/セッション/: sessionId/要素/: id/equals/: other](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidequals/:other)         | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/要素/: id/表示される](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementiddisplayed)                 | サポートされています          | 10240             |
| GET         | [/セッション/: sessionId/要素/: id/場所](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidlocation)                   | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/要素/: id/location_in_view](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidlocation_in_view)   | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/要素/: id/size](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidsize)                           | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/要素/: id/css/:p ropertyName](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidcss/:propertyName) | サポートされています          | 10240             |
| GET         | [/セッション/: sessionId/向き](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidorientation)                                  | サポートされていない &nbsp; | なし               |
| POST        | [/セッション/: sessionId/向き](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidorientation)                                  | サポートされていない &nbsp; | なし               |
| GET         | [/セッション/: sessionId/alert_text](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidalert_text)                                    | サポートされています          | 10240             |
| POST        | [/セッション/: sessionId/alert_text](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidalert_text)                                    | サポートされています          | 10586             |
| POST        | [/セッション/: sessionId/accept_alert](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidaccept_alert)                                | サポートされています          | 10240             |
| POST        | [/セッション/: sessionId/dismiss_alert](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessioniddismiss_alert)                              | サポートされています          | 10240             |
| POST        | [/セッション/: sessionId/moveto](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidmoveto)                                            | サポートされています          | 10586             |
| POST        | [/セッション/: sessionId/クリック](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidclick)                                              | サポートされています          | 10240             |
| POST        | [/セッション/: sessionId/ボタンダウン](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidbuttondown)                                    | サポートされています          | 10586             |
| POST        | [/セッション/: sessionId/ボタンアップ](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidbuttonup)                                        | サポートされています          | 10586             |
| POST        | [/セッション/: sessionId/doubleclick](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessioniddoubleclick)                                  | サポートされています          | 10586             |
| POST        | [/セッション/: sessionId/タッチ/クリック](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchclick)                                   | サポートされていない &nbsp; | なし               |
| POST        | [/セッション/: sessionId/タッチ/ダウン](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchdown)                                     | サポートされていない &nbsp; | なし               |
| POST        | [/セッション/: sessionId/タッチ/アップ](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchup)                                         | サポートされていない &nbsp; | なし               |
| POST        | [/セッション/: sessionId/タッチ/移動](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchmove)                                     | サポートされていない &nbsp; | なし               |
| POST        | [/セッション/: sessionId/タッチ/スクロール](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchscroll)                                 | サポートされていない &nbsp; | なし               |
| POST        | [/セッション/: sessionId/タッチ/スクロール](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchscroll-1)                               | サポートされていない &nbsp; | なし               |
| POST        | [/セッション/: sessionId/タッチ/doubleclick](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchdoubleclick)                       | サポートされていない &nbsp; | なし               |
| POST        | [/セッション/: sessionId/タッチ/longclick](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchlongclick)                           | サポートされていない &nbsp; | なし               |
| POST        | [/セッション/: sessionId/タッチ/フリック](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchflick)                                   | サポートされていない &nbsp; | なし               |
| POST        | [/セッション/: sessionId/タッチ/フリック](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchflick-1)                                 | サポートされていない &nbsp; | なし               |
| GET         | [/セッション/: sessionId/場所](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocation)                                        | サポートされています          | 10586             |
| POST        | [/セッション/: sessionId/場所](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocation)                                        | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/local_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storage)                              | サポートされています          | 10586             |
| POST        | [/セッション/: sessionId/local_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storage)                              | サポートされています          | 10586             |
| DELETE      | [/セッション/: sessionId/local_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storage)                              | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/local_storage/key/: キー](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storagekeykey)               | サポートされています          | 10586             |
| DELETE      | [/セッション/: sessionId/local_storage/key/: キー](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storagekeykey)               | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/local_storage/size](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storagesize)                     | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/session_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storage)                          | サポートされています          | 10586             |
| POST        | [/セッション/: sessionId/session_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storage)                          | サポートされています          | 10586             |
| DELETE      | [/セッション/: sessionId/session_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storage)                          | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/session_storage/key/: キー](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storagekeykey)           | サポートされています          | 10586             |
| DELETE      | [/セッション/: sessionId/session_storage/key/: キー](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storagekeykey)           | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/session_storage/size](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storagesize)                 | サポートされています          | 10586             |
| GET         | [/セッション/: sessionId/ログ](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlog)                                                  | サポートされていない &nbsp; | なし               |
| GET         | [/セッション/: sessionId/ログ/タイプ](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlogtypes)                                       | サポートされていない &nbsp; | なし               |
| GET         | [/セッション/: sessionId/application_cache/status](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidapplication_cachestatus)         | サポートされています          | 10586             |  
