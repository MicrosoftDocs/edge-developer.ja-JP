---
description: EdgeDriver (Chromium) でサポートされている WebDriver の Capabilities と Microsoft Edge 固有のオプションのリファレンス。
title: Capabilities と EdgeOptions
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/25/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: Microsoft Edge、Web 開発、html、css、javascript、開発者、WebDriver、Selenium、テスト、ツール、オートメーション、テスト
ms.openlocfilehash: 1f6dca1b7ce3eb4fab3aaaab6450eee7cbf3eae5
ms.sourcegitcommit: 2e14ff82350f700d7eabc8d33b3ec3e5fc8c61fa
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "11192253"
---
# Capabilities と EdgeOptions  

Capabilities は、`EdgeDriver` セッションをカスタマイズして構成するために使用できるオプションです。  `EdgeDriver` セッションを開始するには、「[Microsoft Edge の推進][DrivingEdgeWebDriverIndex]」を参照してください。  この記事では、[Microsoft Edge][DownloadEdgeWebDriverIndex] でサポートされているすべての Capabilities と、Capabilities を `EdgeDriver` セッションに渡すための追加の詳細について説明します。  

WebDriver 言語バインディングは、Capabilities を `EdgeDriver` に渡すための手段を提供します。  正確なメカニズムは、[選択した言語バインディング][ChooseLanguageBindingWebDriverIndex]によって異なります。  [Selenium][SeleniumMain] では、Capabilities は `EdgeOptions` クラスによって提供されます。  

## EdgeOptions クラスの使用  

`EdgeOptions` のインスタンスを作成 します。これには、Microsoft Edge 固有の Capabilities を設定するための便利なメソッドがあります。  `EdgeOptions` オブジェクトを設定したら、`EdgeOptions` を `EdgeDriver` コンストラクターに渡します。  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddExtensions("/path/to/extension.crx");
var driver = new EdgeDriver(options);
```  

便利なメソッドがない Capabilities については、`AddAdditionalCapability` メソッドを使います。  Capability の名前とそれが受け入れる値の型を知っている必要があります。  完全な一覧を確認するには、「[EdgeOptions オブジェクト](#edgeoptions-object)」を参照してください。  

```csharp
options.AddAdditionalCapability("wdpAddress", "remotehost:50080");
```  

## 認識される Capabilities  

`EdgeDriver` が受け入れる標準の Capabilities については、「[Selenium ドキュメント][SharedCapabilitiesSeleniumDocumentation]」と「[W3C WebDriver 標準][CapabilitiesW3cWebdriver]」を参照してください。  この記事では、Microsoft Edge 固有の Capabilities のみを示します。  

## EdgeOptions オブジェクト  

Microsoft Edge 固有の Capabilities は、ほとんどが `EdgeOptions` オブジェクトを通じて発行され ます。  一部の言語では、Capabilities は `EdgeOptions` クラスによって実装され ます。  他の言語では、Capabilities は `DesiredCapabilities` の `ms:edgeOptions` ディクショナリの下に保存され ます。  

| Capability | 型 | 既定値 | 詳細 |  
|:--- |:--- |:--- |:--- |  
| args | 文字列のリスト |  | Microsoft Edge を起動するときに使用するコマンドライン引数の一覧です。  値が関連付けられた引数は、`=` 記号で区切る必要があります (`['start-maximized', 'user-data-dir=/tmp/temp_profile']` など)。  |  
| binary | 文字列 |  | 使用する Microsoft Edge バイナリのパス (macOS では、アプリだけでなく実際のバイナリである必要があります。  例: `/Applications/Microsoft Edge.app/Contents/MacOS/Microsoft Edge`)。  |  
| extensions | 文字列のリスト |  | 起動時にインストールする拡張機能の一覧。  リスト内の各項目は、base-64 でエンコードされたパック拡張 (`.crx`) である必要があります。  |  
| localState | ディクショナリ |  | ユーザー設定の名前とその値で構成される各エントリのディクショナリ。  ユーザー設定は、ユーザー データ フォルダー内のローカル状態ファイルに適用されます。  |  
| prefs | ディクショナリ |  | ユーザー設定の名前とその値で構成される各エントリのディクショナリ。  ユーザー設定は、使用中のユーザー プロファイルにのみ適用されます。  たとえば、Microsoft Edge のユーザー データ ディレクトリ内の `Preferences` ファイルに移動します。  |  
| detach | ブール値 | false | false の場合、`EdgeDriver` が終了すると、セッションが終了するかどうかにかかわらず、Microsoft Edge は終了します。  true の場合、Microsoft Edge は、セッションが終了 (または閉じられた状態) の場合にのみ終了します。  **注**: true の場合、セッションが終了しない場合、Microsoft Edge インスタンスで使用される一時ユーザー データ ディレクトリは `EdgeDriver` によってクリーンアップされません。  |  
| debuggerAddress | 文字列 |  | <hostname/ip: port> の形式で表される接続先のデバッガー サーバーのアドレス。例: `127.0.0.1:38947`。  |
| excludeSwitches | 文字列のリスト |  | Microsoft Edge の起動時に、既定で EdgeDriver によって除外される Microsoft Edge コマンド ライン スイッチの一覧。  `--` は、スイッチのプレフィックスとして使用できません。  |  
| minidumpPath | 文字列 |  | Microsoft Edge ミニダンプを保存するディレクトリ。  (Linux でのみサポートされています。) |  
| mobileEmulation | ディクショナリ |  | `deviceName` の値、または `deviceMetrics` および `userAgent` の値を含むディクショナリ。  |  
| perfLoggingPrefs | ディクショナリ |  | パフォーマンス ログの設定を指定するオプションのディクショナリ。  詳細については、「[perfLoggingPrefs オブジェクト](#perfloggingprefs-object)」を参照してください。  |  
| windowTypes | 文字列のリスト |  | ウィンドウ ハンドルの一覧に表示されるウィンドウの型の一覧。  Android webview 要素にアクセスするには、一覧に `webview` を含めます。  |  
| wdpAddress | 文字列 |  | 接続先の Windows デバイス ポータル サーバーのアドレス。`hostname/ip:port` の形式で指定します。例: `127.0.0.1:50080`。  詳細については、「[リモート デバッグ-Windows 10 デバイス][DevtoolsRemoteDebuggingWindows]」を参照してください。  |  
| wdpUsername | 文字列 |  | Windows デバイス ポータル サーバーに接続するときに使用するオプションのユーザー名です。  サーバーで認証が有効になっている場合は必須です。  |  
| wdpPassword | 文字列 |  | Windows デバイス ポータル サーバーに接続するときに使用するオプションのパスワードです。  サーバーで認証が有効になっている場合は必須です。  |  
| windowsApp | 文字列 |  | 起動する Microsoft Edge アプリ パッケージのアプリケーション ユーザー モデル ID。例: `Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE`。  Windows デバイス ポータルを使って Windows 10X デバイスまたはエミュレーターに接続する場合は、`binary` の代わりに `windowsApp` を使います。  |  

## perfLoggingPrefs オブジェクト  

`perfLoggingPrefs` ディクショナリの形式は次のとおりです (すべてのキーは省略可能です)。  

| キー | 型 | 既定値 | 詳細 |  
|:--- |:--- |:--- |:--- |  
| enableNetwork | ブール値 | true | ネットワーク ドメインからイベントを収集します (または収集しません)。  |  
| enablePage | ブール値 | true | ページ ドメインからイベントを収集します (または収集しません)。  |  
| traceCategories | 文字列 | (空) | トレース イベントを収集する Microsoft Edge トレース カテゴリのコンマ区切り文字列。  未指定または空の文字列は、トレースを無効にします。  |  
| bufferUsageReportingInterval | 正の整数 | 1000 | DevTools トレース バッファー使用量イベント間の要求されたミリ秒数。  たとえば、1000 の場合は 1 秒に 1 回、すべてのトレースバッファーの量が報告されます。  レポートにバッファー使用量が 100% と示されている場合は、警告が発生します。  |  

## 返される Capabilities  

次の一覧には、新しいセッションを作成するときに `EdgeDriver` によって返される Microsoft Edge 固有のすべての Capabilities が含まれています。  

| Capability | 型 | 詳細 |  
|:--- |:--- |:--- |  
| msedge.msedgedriverVersion | 文字列 | EdgeDriver のバージョン。 |  
| msedge.userDataDir | 文字列 | Microsoft Edge インスタンスで使用されるユーザー データ ディレクトリのパス。 |  

<!-- links -->  

[DevtoolsRemoteDebuggingWindows]: ../devtools-guide-chromium/remote-debugging/windows.md "Windows 10 デバイスのリモート デバッグの概要 | Microsoft Docs"  
[DrivingEdgeWebDriverIndex]: ./index.md#driving-microsoft-edge-chromium "Microsoft Edge の推進 (Chromium) | Microsoft Docs"    
[DownloadEdgeWebDriverIndex]: ./index.md#install-microsoft-edge-chromium "Microsoft Edge をインストールする (Chromium) | Microsoft Docs"  
[ChooseLanguageBindingWebDriverIndex]: ./index.md#choose-a-webdriver-language-binding "WebDriver 言語バインディングを選択する | Microsoft Docs"

[SeleniumMain]: https://www.selenium.dev "SeleniumHQ ブラウザ オートメーション"  
[SharedCapabilitiesSeleniumDocumentation]: https://www.selenium.dev/documentation/en/driver_idiosyncrasies/shared_capabilities/ "共有 Capabilities | Selenium ドキュメント"   

[CapabilitiesW3cWebdriver]: https://www.w3.org/TR/webdriver/#capabilities "Capabilities - WebDriver の仕様 | W3C"   
