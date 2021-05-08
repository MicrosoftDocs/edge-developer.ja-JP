---
description: EdgeDriver (Chromium) でサポートされている WebDriver の Capabilities と Microsoft Edge 固有のオプションのリファレンス。
title: Capabilities と EdgeOptions
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: Microsoft Edge、Web 開発、html、css、javascript、開発者、WebDriver、Selenium、テスト、ツール、オートメーション、テスト
ms.openlocfilehash: 5a48ca34e46b56fa60bcacfade2add23026be144
ms.sourcegitcommit: f95812c4e1b7277f67c6c4891be2779cc1b5bdf1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "11343780"
---
# Capabilities と EdgeOptions  

Capabilities は、`EdgeDriver` セッションをカスタマイズして構成するために使用できるオプションです。  新しいセッションを開始する方法については `EdgeDriver` [、「Microsoft Edge の自動化」に移動します][WebdriverIndexAutomateMicrosoftEdgeChromium]。  この記事では [、Microsoft Edge][WebdriverIndexInstallMicrosoftEdgeChromium] でサポートされているすべての機能と、その機能をセッションに渡す方法の詳細について説明 `EdgeDriver` します。  

機能は、JSON マップとして WebDriver セッションに渡されます。  WebDriver 言語バインドは、通常、タイプ セーフな便利なメソッドを提供します。そのため、JSON マップを自分で構成する必要はありません。  WebDriver 言語のバインドによって、機能を構成するために異なるメカニズムが使用されます。  機能を構成する方法の詳細 [については][WebdriverIndexChooseWebdriverLanguageBinding] 、優先言語バインドのドキュメントに移動します。  [Selenium は][SeleniumMain] 、クラスを通じて機能を構成 `EdgeOptions` します。  

## EdgeOptions クラスの使用  

Microsoft Edge 固有の機能を設定する便利なメソッドを提供するインスタンス `EdgeOptions` を作成します。  オブジェクトを構成した `EdgeOptions` 後、コンストラクター `EdgeOptions` に渡 `EdgeDriver` します。  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddExtensions("/path/to/extension.crx");
var driver = new EdgeDriver(options);
```  

関連付けられた便利なメソッドを持つ機能を使用するには、メソッドを使用 `AddAdditionalCapability` します。  機能の完全な名前と、正しい型の値を渡す必要があります。  受け入れられる機能と値の種類の完全な一覧を確認するには [、EdgeOptions オブジェクトに移動します](#edgeoptions-object)。  

```csharp
options.AddAdditionalCapability("wdpAddress", "remotehost:50080");
```  

## 認識される Capabilities  

`EdgeDriver` が受け入れる標準の Capabilities については、「[Selenium ドキュメント][SharedCapabilitiesSeleniumDocumentation]」と「[W3C WebDriver 標準][CapabilitiesW3cWebdriver]」を参照してください。  この記事では、Microsoft Edge 固有の Capabilities のみを示します。  

## EdgeOptions オブジェクト  

Microsoft Edge 固有の Capabilities は、ほとんどが `EdgeOptions` オブジェクトを通じて発行され ます。  一部の言語では、Capabilities は `EdgeOptions` クラスによって実装され ます。  他の言語では、Capabilities は `DesiredCapabilities` の `ms:edgeOptions` ディクショナリの下に保存され ます。  

| Capability | 型 | 既定値 | 詳細 |  
|:--- |:--- |:--- |:--- |  
| args | 文字列のリスト |  | Microsoft Edge を起動するときに使用するコマンドライン引数の一覧です。  値が関連付けられた引数は、`=` 記号で区切る必要があります (`['start-maximized', 'user-data-dir=/tmp/temp_profile']` など)。 |  
| binary | 文字列 |  | 使用する Microsoft Edge バイナリのパス (macOS では、アプリだけでなく実際のバイナリである必要があります。  例: `/Applications/Microsoft Edge.app/Contents/MacOS/Microsoft Edge`)。 |  
| debuggerAddress | 文字列 |  | たとえば、接続先のデバッガー サーバーのアドレスを、次の `hostname/ip:port` 形式で指定します `127.0.0.1:38947` 。 |
| detach | ブール値 | `false` | 場合は、WebDriver ローカル エンドがセッションを閉じていなくても、WebDriver サービスがシャットダウンすると `false` 、Microsoft Edge が終了します。  場合 `true` は、WebDriver ローカル エンドがセッションを閉じる場合にのみ、Microsoft Edge が終了します。  WebDriver ローカル エンドがセッションを閉じない場合、Microsoft Edge インスタンスで使用される一時的なユーザー データ フォルダー `true` `EdgeDriver` はクリーンアップされません。 |  
| excludeSwitches | 文字列のリスト |  | Microsoft Edge の起動時に、既定で EdgeDriver によって除外される Microsoft Edge コマンド ライン スイッチの一覧。  スイッチの `--` プレフィックスは使用しないようにします。 |  
| extensions | 文字列のリスト |  | 起動時にインストールする拡張機能の一覧。  リスト内の各項目は、base-64 でエンコードされたパック拡張 (`.crx`) である必要があります。 |  
| localState | ディクショナリ |  | 基本設定の名前と値で構成される各エントリを持つ辞書。  ユーザー設定は、ユーザー データ フォルダー内のローカル状態ファイルに適用されます。 |  
| minidumpPath | 文字列 |  | Microsoft Edge ミニダンプを保存するディレクトリ。  (Linux でのみサポートされています。) |  
| mobileEmulation | ディクショナリ |  | `deviceName` の値、または `deviceMetrics` および `userAgent` の値を含むディクショナリ。 |  
| perfLoggingPrefs | ディクショナリ |  | パフォーマンス ログの設定を指定するオプションのディクショナリ。  詳細については、「[perfLoggingPrefs オブジェクト](#perfloggingprefs-object)」を参照してください。 |  
| prefs | ディクショナリ |  | 基本設定の名前と値で構成される各エントリを持つ辞書。  ユーザー設定は、使用中のユーザー プロファイルにのみ適用されます。  たとえば、Microsoft Edge のユーザー `Preferences` データ フォルダー内のファイルに移動します。 |  
| wdpAddress | 文字列 |  | 接続先の Windows デバイス ポータル サーバーのアドレス。`hostname/ip:port` の形式で指定します。例: `127.0.0.1:50080`。  詳細については、「[リモート デバッグ-Windows 10 デバイス][DevtoolsRemoteDebuggingWindows]」を参照してください。 |  
| wdpPassword | 文字列 |  | Windows デバイス ポータル サーバーに接続するときに使用するオプションのパスワードです。  サーバーで認証が有効になっている場合は必須です。 |  
| wdpUsername | 文字列 |  | Windows デバイス ポータル サーバーに接続するときに使用するオプションのユーザー名。  サーバーで認証が有効になっている場合は必須です。 |  
| windowsApp | 文字列 |  | 起動する Microsoft Edge アプリ パッケージのアプリケーション ユーザー モデル ID。例: `Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE`。  Windows デバイス ポータルを使って Windows 10X デバイスまたはエミュレーターに接続する場合は、`binary` の代わりに `windowsApp` を使います。 |  
| windowTypes | 文字列のリスト |  | ウィンドウ ハンドルの一覧に表示されるウィンドウの型の一覧。  Android webview 要素にアクセスするには、一覧に `webview` を含めます。 |  

## perfLoggingPrefs オブジェクト  

`perfLoggingPrefs` ディクショナリの形式は次のとおりです (すべてのキーは省略可能です)。  

| キー | 型 | 既定値 | 詳細 |  
|:--- |:--- |:--- |:--- |  
| bufferUsageReportingInterval | 正の整数 | 1000 | DevTools トレース バッファー使用量イベント間の要求されたミリ秒数。  たとえば、1000 の場合は 1 秒に 1 回、すべてのトレースバッファーの量が報告されます。  レポートにバッファー使用量が 100% と示されている場合は、警告が発生します。 |  
| enableNetwork | ブール値 | true | ネットワーク ドメインからイベントを収集します (または収集しません)。 |  
| enablePage | ブール値 | true | ページ ドメインからイベントを収集します (または収集しません)。 |  
| traceCategories | 文字列 | (空) | トレース イベントを収集する Microsoft Edge トレース カテゴリのコンマ区切り文字列。  未指定または空の文字列は、トレースを無効にします。 |  

## 返される機能  

次の一覧には、新しいセッションを作成するときに `EdgeDriver` によって返される Microsoft Edge 固有のすべての Capabilities が含まれています。  

| Capability | 型 | 詳細 |  
|:--- |:--- |:--- |  
| msedge.msedgedriverVersion | 文字列 | EdgeDriver のバージョン。 |  
| msedge.userDataDir | 文字列 | Microsoft Edge インスタンスで使用されるユーザー データ フォルダーへのパス。 |  

<!-- links -->  

[DevtoolsRemoteDebuggingWindows]: ../devtools-guide-chromium/remote-debugging/windows.md "リモート デバッグ Windows 10 デバイスの使用|Microsoft Docs"  
[WebdriverIndexChooseWebdriverLanguageBinding]: ./index.md#choose-a-webdriver-language-binding "WebDriver 言語バインドを選択する - WebDriver (クロム) |Microsoft Docs"
[WebdriverIndexAutomateMicrosoftEdgeChromium]: ./index.md#automate-microsoft-edge-chromium "Microsoft Edge (クロム) の自動化 - WebDriver (クロム) |Microsoft Docs"    
[WebdriverIndexInstallMicrosoftEdgeChromium]: ./index.md#install-microsoft-edge-chromium "Microsoft Edge (クロム) のインストール - WebDriver (クロム) |Microsoft Docs"  

[SeleniumMain]: https://www.selenium.dev "SeleniumHQ ブラウザ オートメーション"  
[SharedCapabilitiesSeleniumDocumentation]: https://www.selenium.dev/documentation/en/driver_idiosyncrasies/shared_capabilities/ "共有 Capabilities | Selenium ドキュメント"   

[CapabilitiesW3cWebdriver]: https://www.w3.org/TR/webdriver#capabilities "Capabilities - WebDriver の仕様 | W3C"   
