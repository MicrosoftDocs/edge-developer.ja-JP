---
ms.assetid: e56172c0-b635-4c02-8e0c-56bf8cb4c164
description: プログラムとスクリプトで Web ブラウザーの動作を制御できるワイヤー プロトコルである WebDriver の使用を開始する方法について説明します。
title: WebDriver (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: edge, Web 開発, html, css, javascript, 開発者, webdriver, selenium, テスト
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: ab26931c09ecbae41ae88734b25038d21c93c0f6
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234707"
---
# WebDriver (EdgeHTML)

W3C [WebDriver](https://www.w3.org/TR/webdriver/) API はプラットフォームと言語に依存しないインターフェイスであり、プログラムやスクリプトで Web ブラウザーの動作を制御できるワイヤー プロトコルです。

WebDriver を使用すると、開発者はユーザーの操作をシミュレートする自動テストを作成できます。 これは JavaScript 単体テストとは異なります。WebDriver は、ブラウザーで実行されている JavaScript では実行できない機能や情報にアクセスできます。また、ユーザー イベントや OS レベルのイベントをより正確にシミュレートできます。 WebDriver では、1 つのテスト セッションで複数のウィンドウ、タブ、Web ページのテストを管理することもできます。

Microsoft Edge (EdgeHTML) 用 WebDriver の使用を開始する方法を次に示します。

WebDriver の Microsoft Edge (EdgeHTML) 実装では、既存のテストとの下位互換性のために W3C [WebDriver](https://www.w3.org/TR/webdriver/) 仕様と [JSON ワイヤー](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol) プロトコルの両方がサポートされています。

## Microsoft Edge (EdgeHTML) 用 WebDriver の使用を開始する
* Windows 10 をインストールします。
* Windows と Microsoft Edge (EdgeHTML) のビルドに適した Microsoft [WebDriver](https://developer.microsoft.com/microsoft-edge/tools/webdriver/) サーバーをダウンロードします。
* 選択した WebDriver 言語バインドをダウンロードします。 [すべての Selenium 言語バインドは、Microsoft Edge (EdgeHTML) をサポートします](https://docs.seleniumhq.org/download/)。

> [!NOTE]
> Microsoft Edge (EdgeHTML) Feedback & Support で、ヘルプ、問題の報告、およびファイル [機能の要求を確認できます](https://developer.microsoft.com/microsoft-edge/support/)。


## WebDriver の使用
Microsoft Edge (EdgeHTML) で WebDriver の使用を開始するには、次のサンプルを参照してください。

* [ブラウザー ウィンドウを開](https://gist.github.com/InstyleVII/baf25274c55e891076d5#file-webdriver-cs) き、ブラウザー ウィンドウにbing.comして 'webdriver' (GitHub Gist) を検索するための C\# コード サンプル。

## WebDriver サーバーのコマンド ライン フラグ
WebDriver サーバーのコマンド ライン フラグの一覧。

| 名前    | 説明                                                                                                      | 利用可能なリリース |
|:--------|:-----------------------------------------------------------------------------------------------------------------|:------------------|
| host    | WebDriver サーバーに使用するホスト IP (既定: localhost)                                                     | 14393             |
| ポート    | WebDriver サーバーに使用するポート (既定: 17556)                                                            | 14393             |
| package | WebDriver サーバーによって起動されるアプリケーションの ApplicationUserModelId (AUMID)                        | 14393             |
| verbose | 受信した要求と WebDriver サーバーから送信された応答を出力します。                                             | 14393             |
| silent  | 何も出力しない                                                                                                  | 15063             |
| version | ファイルのバージョンをMicrosoftWebDriver.exe                                                                    | 17763             |
| w3c     | W3C WebDriver プロトコルを使用する (既定のオプション)                                                                      | 17763             |
| jwp     | JSON Wire プロトコルを使用する                                                                                           | 17763             |
| クリーンアップ | --package 用に WebDriver サーバーによって設定された一時データとレジストリ キーをクリーンアップします。 その他のパラメーターは無視されます | 17763             |

## W3C WebDriver
[W3C WebDriver](https://www.w3.org/TR/webdriver/)仕様のコマンドごとのサポート。

### 機能
| Capability                       | キー                       | ステータス                   | 利用可能なリリース |
|:---------------------------------|:--------------------------|:-------------------------|:------------------|
| ブラウザー名                     | "browserName"             | サポートされています                | 17763             |
| ブラウザーのバージョン                  | "browserVersion"          | サポートされています                | 17763             |
| プラットフォーム名                    | "platformName"            | サポートされています                | 17763             |
| 安全でない TLS 証明書を受け入れる | "acceptInsecureCerts"     | サポート &nbsp; されていません       | 該当せず               |
| ページ読み込み戦略               | "pageLoadStrategy"        | サポートされています                | 17763             |
| プロキシの構成              | "proxy"                   | サポート &nbsp; されていません       | 該当せず               |
| ウィンドウのサイズ変更/配置  | "setWindowRect"           | サポートされています                | 17763             |
| セッション タイムアウト構成   | "timeouts"                | サポートされています                | 17763             |
| 未処理のプロンプト動作        | "unhandledPromptBehavior" | 部分的に &nbsp; サポート | 17763             |
| InPrivate                        | "ms:inPrivate"            | サポートされています                | 17763             |
| 拡張パス                  | "ms:extensionPaths"       | サポートされています                | 17763             |
| スタート ページ                       | "ms:startPage"            | サポートされています                | 17763             |

### Locator の戦略
| Locator Strategy                                                        | ステータス    | 利用可能なリリース |
|:------------------------------------------------------------------------|:----------|:------------------|
| [CSS セレクター](https://www.w3.org/TR/webdriver/#css-selectors)         | サポートされています | 17763             |
| [リンク テキスト](https://www.w3.org/TR/webdriver/#link-text)                 | サポートされています | 17763             |
| [部分的なリンク テキスト](https://www.w3.org/TR/webdriver/#partial-link-text) | サポートされています | 17763             |
| [タグ名](https://www.w3.org/TR/webdriver/#tag-name)                   | サポートされています | 17763             |
| [XPath](https://www.w3.org/TR/webdriver/#xpath)                         | サポートされています | 17763             |

### コマンド
| HTTP メソッド | URI テンプレート                                                   | コマンド                                                                                   | ステータス             | 利用可能なリリース |
|:------------|:---------------------------------------------------------------|:------------------------------------------------------------------------------------------|:-------------------|:----------------  |
| POST        | /session                                                       | [新しいセッション](https://www.w3.org/TR/webdriver/#new-session)                               | サポートされています          | 17763             |
| DELETE      | /session/{session id}                                          | [セッションを削除する](https://www.w3.org/TR/webdriver/#delete-session)                         | サポートされています          | 17763             |
| GET         | /status                                                        | [ステータス](https://www.w3.org/TR/webdriver/#status)                                         | サポートされています          | 17763             |
| GET         | /session/{session id}/timeouts                                 | [タイムアウトを取得する](https://www.w3.org/TR/webdriver/#get-timeouts)                             | サポートされています          | 17763             |
| POST        | /session/{session id}/timeouts                                 | [タイムアウトの設定](https://www.w3.org/TR/webdriver/#set-timeouts)                             | サポートされています          | 17763             |
| POST        | /session/{session id}/url                                      | [移動する](https://www.w3.org/TR/webdriver/#navigate-to)                               | サポートされています          | 17763             |
| GET         | /session/{session id}/url                                      | [現在の URL を取得する](https://www.w3.org/TR/webdriver/#get-current-url)                       | サポートされています          | 17763             |
| POST        | /session/{session id}/back                                     | [戻る](https://www.w3.org/TR/webdriver/#back)                                             | サポートされています          | 17763             |
| POST        | /session/{session id}/forward                                  | [Forward](https://www.w3.org/TR/webdriver/#forward)                                       | サポートされています          | 17763             |
| POST        | /session/{session id}/refresh                                  | [Refresh](https://www.w3.org/TR/webdriver/#refresh)                                       | サポートされています          | 17763             |
| GET         | /session/{session id}/title                                    | [タイトルを取得する](https://www.w3.org/TR/webdriver/#get-title)                                   | サポートされています          | 17763             |
| GET         | /session/{session id}/window                                   | [ウィンドウ ハンドルを取得する](https://www.w3.org/TR/webdriver/#get-window-handle)                   | サポートされています          | 17763             |
| DELETE      | /session/{session id}/window                                   | [ウィンドウを閉じる](https://www.w3.org/TR/webdriver/#close-window)                             | サポートされています          | 17763             |
| POST        | /session/{session id}/window                                   | [ウィンドウに切り替える](https://www.w3.org/TR/webdriver/#switch-to-window)                     | サポートされています          | 17763             |
| GET         | /session/{session id}/window/handles                           | [ウィンドウ ハンドルを取得する](https://www.w3.org/TR/webdriver/#get-window-handles)                 | サポートされています          | 17763             |
| POST        | /session/{session id}/frame                                    | [フレームに切り替える](https://www.w3.org/TR/webdriver/#switch-to-frame)                       | サポートされています          | 17763             |
| POST        | /session/{session id}/frame/parent                             | [親フレームに切り替える](https://www.w3.org/TR/webdriver/#switch-to-parent-frame)         | サポートされています          | 17763             |
| GET         | /session/{session id}/window/rect                              | [ウィンドウの Rect を取得する](https://www.w3.org/TR/webdriver/#get-window-rect)                       | サポートされています          | 17763             |
| POST        | /session/{session id}/window/rect                              | [Set Window Rect](https://www.w3.org/TR/webdriver/#set-window-rect)                       | サポートされています          | 17763             |
| POST        | /session/{session id}/window/maximize                          | [ウィンドウを最大化する](https://www.w3.org/TR/webdriver/#maximize-window)                       | サポートされています          | 17763             |
| POST        | /session/{session id}/window/minimize                          | [ウィンドウを最小化する](https://www.w3.org/TR/webdriver/#minimize-window)                       | サポートされています          | 17763             |
| POST        | /session/{session id}/window/fullscreen                        | [全画面ウィンドウ](https://www.w3.org/TR/webdriver/#fullscreen-window)                   | サポート &nbsp; されていません | 該当せず               |
| GET         | /session/{session id}/element/active                           | [Active 要素を取得する](https://www.w3.org/TR/webdriver/#get-active-element)                 | サポートされています          | 17763             |
| POST        | /session/{session id}/element                                  | [Find 要素](https://www.w3.org/TR/webdriver/#find-element)                             | サポートされています          | 17763             |
| POST        | /session/{session id}/elements                                 | [要素を検索する](https://www.w3.org/TR/webdriver/#find-elements)                           | サポートされています          | 17763             |
| POST        | /session/{session id}/element/{element id}/element             | [要素から要素を検索する](https://www.w3.org/TR/webdriver/#find-element-from-element)   | サポートされています          | 17763             |
| POST        | /session/{session id}/element/{element id}/elements            | [要素から要素を検索する](https://www.w3.org/TR/webdriver/#find-elements-from-element) | サポートされています          | 17763             |
| GET         | /session/{session id}/element/{element id}/selected            | [Is 要素が選択されている](https://www.w3.org/TR/webdriver/#is-element-selected)               | サポートされています          | 17763             |
| GET         | /session/{session id}/element/{element id}/attribute/{name}    | [Get 要素属性](https://www.w3.org/TR/webdriver/#get-element-attribute)           | サポートされています          | 17763             |
| GET         | /session/{session id}/element/{element id}/property/{name}     | [Get Element プロパティ](https://www.w3.org/TR/webdriver/#get-element-property)             | サポートされています          | 17763             |
| GET         | /session/{session id}/element/{element id}/css/{property name} | [要素 CSS 値を取得する](https://www.w3.org/TR/webdriver/#get-element-css-value)           | サポートされています          | 17763             |
| GET         | /session/{session id}/element/{element id}/text                | [要素テキストを取得する](https://www.w3.org/TR/webdriver/#get-element-text)                     | サポートされています          | 17763             |
| GET         | /session/{session id}/element/{element id}/name                | [要素タグ名を取得する](https://www.w3.org/TR/webdriver/#get-element-tag-name)             | サポートされています          | 17763             |
| GET         | /session/{session id}/element/{element id}/rect                | [Get Element Rect](https://www.w3.org/TR/webdriver/#get-element-rect)                     | サポートされています          | 17763             |
| GET         | /session/{session id}/element/{element id}/enabled             | [Is 要素の有効化](https://www.w3.org/TR/webdriver/#is-element-enabled)                 | サポートされています          | 17763             |
| POST        | /session/{session id}/element/{element id}/click               | [要素のクリック](https://www.w3.org/TR/webdriver/#element-click)                           | サポートされています          | 17763             |
| POST        | /session/{session id}/element/{element id}/clear               | [要素クリア](https://www.w3.org/TR/webdriver/#element-clear)                           | サポートされています          | 17763             |
| POST        | /session/{session id}/element/{element id}/sendKeys            | [要素の送信キー](https://www.w3.org/TR/webdriver/#element-send-keys)                   | サポートされています          | 17763             |
| GET         | /session/{session id}/source                                   | [ページ ソースを取得する](https://www.w3.org/TR/webdriver/#get-page-source)                       | サポートされています          | 17763             |
| POST        | /session/{session id}/execute/sync                             | [スクリプトの実行](https://www.w3.org/TR/webdriver/#execute-script)                         | サポートされています          | 17763             |
| POST        | /session/{session id}/execute/async                            | [非同期スクリプトの実行](https://www.w3.org/TR/webdriver/#execute-async-script)             | サポートされています          | 17763             |
| GET         | /session/{session id}/cookie                                   | [すべての Cookie を取得する](https://www.w3.org/TR/webdriver/#get-all-cookies)                       | サポートされています          | 17763             |
| GET         | /session/{session id}/cookie/{name}                            | [名前付き Cookie を取得する](https://www.w3.org/TR/webdriver/#get-named-cookie)                     | サポートされています          | 17763             |
| POST        | /session/{session id}/cookie                                   | [Cookie の追加](https://www.w3.org/TR/webdriver/#add-cookie)                                 | サポートされています          | 17763             |
| DELETE      | /session/{session id}/cookie/{name}                            | [Cookie を削除する](https://www.w3.org/TR/webdriver/#delete-cookie)                           | サポートされています          | 17763             |
| DELETE      | /session/{session id}/cookie                                   | [すべての Cookie を削除する](https://www.w3.org/TR/webdriver/#delete-all-cookies)                 | サポートされています          | 17763             |
| POST        | /session/{session id}/actions                                  | [アクションを実行する](https://www.w3.org/TR/webdriver/#perform-actions)                       | サポートされています          | 17763             |
| DELETE      | /session/{session id}/actions                                  | [リリース アクション](https://www.w3.org/TR/webdriver/#release-actions)                       | サポートされています          | 17763             |
| POST        | /session/{session id}/alert/dismiss                            | [アラートを閉じる](https://www.w3.org/TR/webdriver/#dismiss-alert)                           | サポートされています          | 17763             |
| POST        | /session/{session id}/alert/accept                             | [通知を受け入れる](https://www.w3.org/TR/webdriver/#accept-alert)                             | サポートされています          | 17763             |
| GET         | /session/{session id}/alert/text                               | [アラート テキストを取得する](https://www.w3.org/TR/webdriver/#get-alert-text)                         | サポートされています          | 17763             |
| POST        | /session/{session id}/alert/text                               | [通知テキストを送信する](https://www.w3.org/TR/webdriver/#send-alert-text)                       | サポートされています          | 17763             |
| GET         | /session/{session id}/screenshot                               | [スクリーンショットを撮る](https://www.w3.org/TR/webdriver/#take-screenshot)                       | サポートされています          | 17763             |
| GET         | /session/{session id}/screenshot/{element id}                  | [要素のスクリーンショットを取る](https://www.w3.org/TR/webdriver/#take-element-screenshot)       | サポートされています          | 17763             |

## JSON ワイヤー プロトコル
JSON ワイヤー プロトコルに対するコマンドごとの [サポート](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol)。

### コマンド
| HTTP メソッド | パス                                                                                                                                                         | ステータス             | 利用可能なリリース |
|:------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------|:------------------|
| GET         | [/status](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#status)                                                                               | サポートされています          | 10240             |
| POST        | [/session](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#session-1)                                                                           | サポートされています          | 10240             |
| GET         | [/sessions](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessions)                                                                           | サポートされています          | 10240             |
| GET         | [/session/:sessionId](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionid)                                                         | サポートされています          | 10240             |
| DELETE      | [/session/:sessionId](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionid)                                                         | サポートされています          | 10240             |
| POST        | [/session/:sessionId/timeouts](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtimeouts)                                        | サポートされています          | 10240             |
| POST        | [/session/:sessionId/timeouts/async_script](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtimeoutsasync_script)               | サポート &nbsp; されていません | 該当せず               |
| POST        | [/session/:sessionId/timeouts/implicit_wait](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtimeoutsimplicit_wait)             | サポートされています          | 10586             |
| GET         | [/session/:sessionId/window_handle](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindow_handle)                              | サポートされています          | 10586             |
| GET         | [/session/:sessionId/window_handles](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindow_handles)                            | サポートされています          | 10586             |
| GET         | [/session/:sessionId/url](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidurl)                                                  | サポートされています          | 10240             |
| POST        | [/session/:sessionId/url](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidurl)                                                  | サポートされています          | 10240             |
| POST        | [/session/:sessionId/forward](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidforward)                                          | サポートされています          | 10240             |
| POST        | [/session/:sessionId/back](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidback)                                                | サポートされています          | 10240             |
| POST        | [/session/:sessionId/refresh](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidrefresh)                                          | サポートされています          | 10240             |
| POST        | [/session/:sessionId/execute](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidexecute)                                          | サポートされています          | 10240             |
| POST        | [/session/:sessionId/execute_async](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidexecute_async)                              | サポートされています          | 10586             |
| GET         | [/session/:sessionId/screenshot](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidscreenshot)                                    | サポートされています          | 10240             |
| GET         | [/session/:sessionId/ime/available_engines](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidimeavailable_engines)               | サポート &nbsp; されていません | 該当せず               |
| GET         | [/session/:sessionId/ime/active_engine](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidimeactive_engine)                       | サポート &nbsp; されていません | 該当せず               |
| GET         | [/session/:sessionId/ime/activated](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidimeactivated)                               | サポート &nbsp; されていません | 該当せず               |
| POST        | [/session/:sessionId/ime/deactivate](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidimedeactivate)                             | サポート &nbsp; されていません | 該当せず               |
| POST        | [/session/:sessionId/ime/activate](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidimeactivate)                                 | サポート &nbsp; されていません | 該当せず               |
| POST        | [/session/:sessionId/frame](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidframe)                                              | サポートされています          | 10586             |
| POST        | [/session/:sessionId/frame/parent](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidframeparent)                                 | サポートされています          | 10586             |
| POST        | [/session/:sessionId/window](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindow)                                            | サポートされています          | 10586             |
| DELETE      | [/session/:sessionId/window](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindow)                                            | サポートされています          | 10586             |
| POST        | [/session/:sessionId/window/:windowHandle/size](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindowwindowhandlesize)         | サポートされています          | 10586             |
| GET         | [/session/:sessionId/window/:windowHandle/size](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindowwindowhandlesize)         | サポートされています          | 10586             |
| POST        | [/session/:sessionId/window/:windowHandle/position](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindowwindowhandleposition) | サポートされています          | 10586             |
| GET         | [/session/:sessionId/window/:windowHandle/position](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindowwindowhandleposition) | サポートされています          | 10586             |
| GET         | [/session/:sessionId/window/:windowHandle/maximize](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindowwindowhandlemaximize) | サポートされています          | 10586             |
| GET         | [/session/:sessionId/cookie](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidcookie)                                            | サポートされています          | 10586             |
| POST        | [/session/:sessionId/cookie](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidcookie)                                            | サポートされています          | 10240             |
| DELETE      | [/session/:sessionId/cookie](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidcookie)                                            | サポートされています          | 10586             |
| DELETE      | [/session/:sessionId/cookie/:name](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidcookiename)                                  | サポートされています          | 10240             |
| GET         | [/session/:sessionId/source](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsource)                                            | サポートされています          | 10586             |
| GET         | [/session/:sessionId}/title](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtitle)                                             | サポートされています          | 10240             |
| POST        | [/session/:sessionId/element](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelement)                                          | サポートされています          | 10586             |
| POST        | [/session/:sessionId/elements](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelements)                                        | サポートされています          | 10586             |
| POST        | [/session/:sessionId/element/active](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementactive)                             | サポートされています          | 10586             |
| GET         | [/session/:sessionId/element/:id](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementid)                                    | サポート &nbsp; されていません | 該当せず               |
| POST        | [/session/:sessionId/element/:id/element](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidelement)                     | サポートされています          | 10586             |
| POST        | [/session/:sessionId/element/:id/elements](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidelements)                   | サポートされています          | 10586             |
| POST        | [/session/:sessionId/element/:id/click](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidclick)                         | サポートされています          | 10240             |
| POST        | [/session/:sessionId/element/:id/submit](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidsubmit)                       | サポートされています          | 10586             |
| GET         | [/session/:sessionId/element/:id/text](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidtext)                           | サポートされています          | 10240             |
| POST        | [/session/:sessionId/element/:id/value](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidvalue)                         | サポートされています          | 10240             |
| POST        | [/session/:sessionId/keys](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidkeys)                                                | サポートされています          | 10586             |
| GET         | [/session/:sessionId/element/:id/name](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidname)                           | サポートされています          | 10240             |
| POST        | [/session/:sessionId/element/:id/clear](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidclear)                         | サポートされています          | 10240             |
| GET         | [/session/:sessionId/element/:id/selected](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidselected)                   | サポートされています          | 10240             |
| GET         | [/session/:sessionId/element/:id/enabled](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidenabled)                     | サポートされています          | 10240             |
| GET         | [/session/:sessionId/element/:id/attribute/:name](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidattribute/:name)     | サポートされています          | 10240             |
| GET         | [/session/:sessionId/element/:id/equals/:other](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidequals/:other)         | サポートされています          | 10586             |
| GET         | [/session/:sessionId/element/:id/displayed](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementiddisplayed)                 | サポートされています          | 10240             |
| GET         | [/session/:sessionId/element/:id/location](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidlocation)                   | サポートされています          | 10586             |
| GET         | [/session/:sessionId/element/:id/location_in_view](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidlocation_in_view)   | サポートされています          | 10586             |
| GET         | [/session/:sessionId/element/:id/size](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidsize)                           | サポートされています          | 10586             |
| GET         | [/session/:sessionId/element/:id/css/:p ropertyName](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidcss/:propertyName) | サポートされています          | 10240             |
| GET         | [/session/:sessionId/orientation](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidorientation)                                  | サポート &nbsp; されていません | 該当せず               |
| POST        | [/session/:sessionId/orientation](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidorientation)                                  | サポート &nbsp; されていません | 該当せず               |
| GET         | [/session/:sessionId/alert_text](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidalert_text)                                    | サポートされています          | 10240             |
| POST        | [/session/:sessionId/alert_text](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidalert_text)                                    | サポートされています          | 10586             |
| POST        | [/session/:sessionId/accept_alert](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidaccept_alert)                                | サポートされています          | 10240             |
| POST        | [/session/:sessionId/dismiss_alert](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessioniddismiss_alert)                              | サポートされています          | 10240             |
| POST        | [/session/:sessionId/moveto](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidmoveto)                                            | サポートされています          | 10586             |
| POST        | [/session/:sessionId/click](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidclick)                                              | サポートされています          | 10240             |
| POST        | [/session/:sessionId/buttondown](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidbuttondown)                                    | サポートされています          | 10586             |
| POST        | [/session/:sessionId/buttonup](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidbuttonup)                                        | サポートされています          | 10586             |
| POST        | [/session/:sessionId/doubleclick](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessioniddoubleclick)                                  | サポートされています          | 10586             |
| POST        | [/session/:sessionId/touch/click](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchclick)                                   | サポート &nbsp; されていません | 該当せず               |
| POST        | [/session/:sessionId/touch/down](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchdown)                                     | サポート &nbsp; されていません | 該当せず               |
| POST        | [/session/:sessionId/touch/up](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchup)                                         | サポート &nbsp; されていません | 該当せず               |
| POST        | [/session/:sessionId/touch/move](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchmove)                                     | サポート &nbsp; されていません | 該当せず               |
| POST        | [/session/:sessionId/touch/scroll](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchscroll)                                 | サポート &nbsp; されていません | 該当せず               |
| POST        | [/session/:sessionId/touch/scroll](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchscroll-1)                               | サポート &nbsp; されていません | 該当せず               |
| POST        | [/session/:sessionId/touch/doubleclick](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchdoubleclick)                       | サポート &nbsp; されていません | 該当せず               |
| POST        | [/session/:sessionId/touch/longclick](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchlongclick)                           | サポート &nbsp; されていません | 該当せず               |
| POST        | [/session/:sessionId/touch/flick](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchflick)                                   | サポート &nbsp; されていません | 該当せず               |
| POST        | [/session/:sessionId/touch/flick](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchflick-1)                                 | サポート &nbsp; されていません | 該当せず               |
| GET         | [/session/:sessionId/location](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocation)                                        | サポートされています          | 10586             |
| POST        | [/session/:sessionId/location](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocation)                                        | サポートされています          | 10586             |
| GET         | [/session/:sessionId/local_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storage)                              | サポートされています          | 10586             |
| POST        | [/session/:sessionId/local_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storage)                              | サポートされています          | 10586             |
| DELETE      | [/session/:sessionId/local_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storage)                              | サポートされています          | 10586             |
| GET         | [/session/:sessionId/local_storage/key/:key](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storagekeykey)               | サポートされています          | 10586             |
| DELETE      | [/session/:sessionId/local_storage/key/:key](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storagekeykey)               | サポートされています          | 10586             |
| GET         | [/session/:sessionId/local_storage/size](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storagesize)                     | サポートされています          | 10586             |
| GET         | [/session/:sessionId/session_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storage)                          | サポートされています          | 10586             |
| POST        | [/session/:sessionId/session_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storage)                          | サポートされています          | 10586             |
| DELETE      | [/session/:sessionId/session_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storage)                          | サポートされています          | 10586             |
| GET         | [/session/:sessionId/session_storage/key/:key](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storagekeykey)           | サポートされています          | 10586             |
| DELETE      | [/session/:sessionId/session_storage/key/:key](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storagekeykey)           | サポートされています          | 10586             |
| GET         | [/session/:sessionId/session_storage/size](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storagesize)                 | サポートされています          | 10586             |
| GET         | [/session/:sessionId/log](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlog)                                                  | サポート &nbsp; されていません | 該当せず               |
| GET         | [/session/:sessionId/log/types](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlogtypes)                                       | サポート &nbsp; されていません | 該当せず               |
| GET         | [/session/:sessionId/application_cache/status](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidapplication_cachestatus)         | サポートされています          | 10586             |  
