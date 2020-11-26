---
description: EdgeDriver (Chromium) でサポートされている WebDriver 機能と Microsoft Edge 固有のオプションのリファレンス。
title: 機能と EdgeOptions
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/25/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 開発、html、css、javascript、開発者、webdriver、selenium、テスト、ツール、オートメーション、テスト
ms.openlocfilehash: 1f6dca1b7ce3eb4fab3aaaab6450eee7cbf3eae5
ms.sourcegitcommit: 2e14ff82350f700d7eabc8d33b3ec3e5fc8c61fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "11192253"
---
# 機能と EdgeOptions  

機能は、セッションをカスタマイズして構成するために使用できるオプションです `EdgeDriver` 。  セッションを開始するに `EdgeDriver` は、[ [Microsoft Edge の駆動][DrivingEdgeWebDriverIndex]] に移動します。  この記事では、 [Microsoft Edge][DownloadEdgeWebDriverIndex] でサポートされているすべての機能と、その機能をセッションに渡すための追加の詳細について説明し `EdgeDriver` ます。  

WebDriver 言語バインドは、機能を渡すための手段を提供 `EdgeDriver` します。  正確なメカニズムは、 [選択した言語バインド][ChooseLanguageBindingWebDriverIndex]によって異なります。  [Selenium][SeleniumMain]では、機能はクラスによって提供され `EdgeOptions` ます。  

## EdgeOptions クラスの使用  

のインスタンスを作成 `EdgeOptions` します。これには、Microsoft Edge 固有の機能を設定するための便利なメソッドがあります。  オブジェクトを設定したら `EdgeOptions` 、 `EdgeOptions` コンストラクターに渡し `EdgeDriver` ます。  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddExtensions("/path/to/extension.crx");
var driver = new EdgeDriver(options);
```  

まだ便利な方法がない機能については、メソッドを使い `AddAdditionalCapability` ます。  機能の名前とそれが受け付ける値の種類を知っている必要があります。  完全な一覧を確認するには、 [EdgeOptions オブジェクト](#edgeoptions-object)に移動します。  

```csharp
options.AddAdditionalCapability("wdpAddress", "remotehost:50080");
```  

## 認識される機能  

受け入れる標準機能については `EdgeDriver` 、 [Selenium のドキュメント][SharedCapabilitiesSeleniumDocumentation] に移動して、 [W3C webdriver standard][CapabilitiesW3cWebdriver]に移動してください。  この記事では、Microsoft Edge 固有の機能のみを示します。  

## EdgeOptions オブジェクト  

Microsoft Edge 固有の機能は、ほとんどがオブジェクトを通じて公開され `EdgeOptions` ます。  一部の言語では、機能がクラスによって実装され `EdgeOptions` ます。  他の言語では、機能はのディクショナリの下に保存され `ms:edgeOptions` `DesiredCapabilities` ます。  

| Capability | 型 | 既定値 | 詳細 |  
|:--- |:--- |:--- |:--- |  
| 引数 | 文字列の一覧 |  | Microsoft Edge を起動するときに使用するコマンドライン引数の一覧です。  値が関連付けられた引数は、 `=` アットマーク (\ など) で区切る必要があり `['start-maximized', 'user-data-dir=/tmp/temp_profile']` ます。  |  
| 演算 | string |  | 使用する Microsoft Edge バイナリのパス \ (macOS では、アプリだけでなく実際のバイナリである必要があります。  たとえば、 `/Applications/Microsoft Edge.app/Contents/MacOS/Microsoft Edge` \)。  |  
| extensions | 文字列の一覧 |  | 起動時にインストールする拡張機能の一覧。  リスト内の各項目は、base-64 でエンコードされたパック拡張 (\) である必要があり `.crx` ます。  |  
| localState | 辞書 |  | 優先順位の名前とその値で構成される各エントリのディクショナリ。  ユーザー設定は、ユーザーデータフォルダー内のローカル状態ファイルに適用されます。  |  
| ミラーリング | 辞書 |  | 優先順位の名前とその値で構成される各エントリのディクショナリ。  この設定は、使用中のユーザープロファイルにのみ適用されます。  例として、 `Preferences` Microsoft Edge のユーザーデータディレクトリ内のファイルに移動します。  |  
| 適用 | boolean | false | False の場合、終了すると `EdgeDriver` 、セッションが終了するかどうかにかかわらず、Microsoft Edge は終了します。  True の場合、Microsoft Edge は、セッションが終了した場合にのみ終了します (または閉じた状態)。  **注**: true の場合、セッションが終了しない場合、 `EdgeDriver` Microsoft Edge インスタンスで使用される一時ユーザーデータディレクトリはクリーンアップされません。  |  
| デバッガアドレス | string |  | <hostname/ip: port> の形式で、接続先のデバッガーサーバーのアドレス  `127.0.0.1:38947` です。  |
| excludeSwitches | 文字列の一覧 |  | Microsoft edge を起動すると、既定では、EdgeDriver によって除外される Microsoft Edge コマンドラインスイッチの一覧。  スイッチのプレフィックスは使用できません `--` 。  |  
| minidumpPath | string |  | Microsoft Edge ミニダンプを保存するディレクトリ。  \ (Linux でのみサポートされています) |  
| mobileEmulation | 辞書 |  | And の値の値 `deviceName` または値を含むディクショナリ `deviceMetrics` `userAgent` 。  |  
| perfLoggingPrefs 環境環境 | 辞書 |  | パフォーマンスログの設定を指定するオプションのディクショナリです。  詳細については、「 [perfloggingprefs 環境オブジェクト](#perfloggingprefs-object)」を参照してください。  |  
| windowTypes | 文字列の一覧 |  | ウィンドウハンドルの一覧に表示されるウィンドウの種類の一覧です。  Android webview 要素にアクセスするには、 `webview` 一覧にを含めます。  |  
| wdpAddress | string |  | 接続先の Windows Device Portal サーバーのアドレス。などの形式で指定 `hostname/ip:port`  `127.0.0.1:50080` します。  詳細については、「 [リモートデバッグ-Windows 10 デバイス][DevtoolsRemoteDebuggingWindows]」を参照してください。  |  
| wdpUsername | string |  | Windows Device Portal サーバーに接続するときに使用するオプションのユーザー名です。  サーバーで認証が有効になっている場合は必須です。  |  
| wdpPassword | string |  | Windows Device Portal サーバーに接続するときに使用するオプションのパスワードです。  サーバーで認証が有効になっている場合は必須です。  |  
| Windowsapp.lib | string |  | 起動する Microsoft Edge アプリパッケージのアプリケーションユーザーモデル ID `Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE` 。  Windows `windowsApp` `binary` device Portal を使って windows 10 デバイスまたはエミュレーターに接続する場合は、代わりにを使います。  |  

## perfLoggingPrefs オブジェクト  

`perfLoggingPrefs`辞書の形式は次のとおりです。 \ (すべてのキーはオプションです)。  

| キー | 型 | 既定値 | 詳細 |  
|:--- |:--- |:--- |:--- |  
| enableNetwork | boolean | true | ネットワークドメインから \ (収集しない \) イベントを収集するには、  |  
| enablePage | boolean | true | ページドメインから \ (収集しない \) イベントを収集するには、  |  
| traceCategories | string | \ (空 \) | トレースイベントを収集する Microsoft Edge トレースカテゴリのコンマ区切り文字列。  未指定または空の文字列は、トレースを無効にします。  |  
| bufferUsageReportingInterval | 正の整数 | 1000 | DevTools トレースバッファー使用量イベント間の要求されたミリ秒数。  たとえば、1000の場合は1秒に1回、すべてのトレースバッファーの量が報告されます。  レポートにバッファー使用量が100% と示されている場合は、警告が発生します。  |  

## 返される機能  

次の一覧には、 `EdgeDriver` 新しいセッションを作成するときに返される Microsoft Edge 固有のすべての機能が含まれています。  

| Capability | 型 | 詳細 |  
|:--- |:--- |:--- |  
| msedge.msedgedriverVersion | string | EdgeDriver のバージョン。 |  
| msedge.userDataDir | string | Microsoft Edge インスタンスで使用されるユーザーデータディレクトリへのパス。 |  

<!-- links -->  

[DevtoolsRemoteDebuggingWindows]: ../devtools-guide-chromium/remote-debugging/windows.md "Windows 10 デバイスのリモートデバッグの概要 |Microsoft ドキュメント"  
[DrivingEdgeWebDriverIndex]: ./index.md#driving-microsoft-edge-chromium "Microsoft Edge の推進 (Chromium) |Microsoft ドキュメント"    
[DownloadEdgeWebDriverIndex]: ./index.md#install-microsoft-edge-chromium "Microsoft Edge をインストールする (Chromium) |Microsoft ドキュメント"  
[ChooseLanguageBindingWebDriverIndex]: ./index.md#choose-a-webdriver-language-binding "WebDriver 言語バインドを選択してください |Microsoft ドキュメント"

[SeleniumMain]: https://www.selenium.dev "SeleniumHQ ブラウザオートメーション"  
[SharedCapabilitiesSeleniumDocumentation]: https://www.selenium.dev/documentation/en/driver_idiosyncrasies/shared_capabilities/ "共有機能 |Selenium ドキュメント"   

[CapabilitiesW3cWebdriver]: https://www.w3.org/TR/webdriver/#capabilities "機能-WebDriver の仕様 |勧告"   
