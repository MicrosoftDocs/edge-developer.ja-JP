---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ グローバル
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 38ebe9bb98ecb58fb9ec52d11e6885ac0b06cdd2
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879731"
---
# 0.9.515-グローバル 

> [!NOTE]
> この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。 最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[CompareBrowserVersions](#comparebrowserversions) | このメソッドは、すべてのバージョンが正しいかどうかを調べるために、バージョンを適切に比較することを目的としています。
[CreateCoreWebView2Environment](#createcorewebview2environment) | インストールされている Edge バージョンを使って、evergreen WebView2 環境を作成します。
[CreateCoreWebView2EnvironmentWithDetails](#createcorewebview2environmentwithdetails) | この API は、次の SDK リリースでは削除される予定です。
[CreateCoreWebView2EnvironmentWithOptions](#createcorewebview2environmentwithoptions) | [DLL エクスポート] を使用して、カスタムバージョンの Edge、ユーザーデータディレクトリ、または追加オプションを使って WebView2 環境を作成します。
[GetAvailableCoreWebView2BrowserVersionString](#getavailablecorewebview2browserversionstring) | 安定したチャネルまたは埋め込みエッジでない場合は、チャネル名などのブラウザーのバージョン情報を取得します。

## Members

#### CompareBrowserVersions 

> パブリック STDAPI [CompareBrowserVersions](#comparebrowserversions)(PCWSTR VERSION1、PCWSTR version2、int * result)

このメソッドは、すべてのバージョンが正しいかどうかを調べるために、バージョンを適切に比較することを目的としています。

Webview2 または特定の機能ベースをバージョンで使うかどうかを決定するために使うことができます。 結果の値を-1、0、または1に設定します (version1 が version2 より小さいか、等しいか、等しい場合)。 いずれかのバージョン文字列が解析できなかった場合、または入力パラメーターが null である場合に E_INVALIDARG を返します。 入力では、GetAvailableCoreWebView2BrowserVersionString から取得した versionInfo を直接使うことができます。チャネル情報は無視されます。

#### CreateCoreWebView2Environment 

> パブリック STDAPI [CreateCoreWebView2Environment](#createcorewebview2environment)([ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](icorewebview2createcorewebview2environmentcompletedhandler.md) * environment_created_handler)

インストールされている Edge バージョンを使って、evergreen WebView2 環境を作成します。

これは、CreateCoreWebView2EnvironmentWithOptions と browserExecutableFolder、userDataFolder、additionalBrowserArguments を使用してを呼び出すことに相当します。 詳細については、「CreateCoreWebView2EnvironmentWithOptions」を参照してください。

#### CreateCoreWebView2EnvironmentWithDetails 

> パブリック STDAPI [CreateCoreWebView2EnvironmentWithDetails](#createcorewebview2environmentwithdetails)(PCWSTR browserExecutableFolder、PCWSTR userDataFolder、PCWSTR additionalBrowserArguments、 [ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](icorewebview2createcorewebview2environmentcompletedhandler.md) * environment_created_handler)

この API は、次の SDK リリースでは削除される予定です。

CreateCoreWebView2EnvironmentWithOptions を使用してください。

#### CreateCoreWebView2EnvironmentWithOptions 

> パブリック STDAPI [CreateCoreWebView2EnvironmentWithOptions](#createcorewebview2environmentwithoptions)(PCWSTR browserExecutableFolder、PCWSTR userDataFolder、 [ICoreWebView2EnvironmentOptions](icorewebview2environmentoptions.md) * environmentOptions、 [ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](icorewebview2createcorewebview2environmentcompletedhandler.md) * environment_created_handler)

[DLL エクスポート] を使用して、カスタムバージョンの Edge、ユーザーデータディレクトリ、または追加オプションを使って WebView2 環境を作成します。

browserExecutableFolder は、埋め込まれた端を含むフォルダーへの相対パスです。 埋め込まれたエッジを取得するには、インストールされている Edge のフォルダーという名前のバージョン (インストールされている 73.0.52.0 Edge の 73.0.52.0 sub フォルダーなど) をコピーします。 フォルダーの msedge.exe、msedge.dll などを行う必要があります。 BrowserExecutableFolder に null または空の文字列を使用してコンピューターにインストールされている Edge を使用して、コンピューターにインストールされている microsoft Edge の互換性のあるバージョンを検索します。この場合は、ユーザーごとに最初にインストールしてから、コンピューターごとにインストールします。

既定のチャネル検索順序は、安定、ベータ、dev、カナリアです。 WEBVIEW2_RELEASE_CHANNEL_PREFERENCE 環境変数または該当する releaseChannelPreference レジストリ値に1を指定すると、チャネルの検索順序が逆になります。

userDataFolder を指定して、WebView2 の既定のユーザーデータフォルダーの場所を変更できます。 パスには、絶対ファイルパス、または現在のプロセスの実行可能ファイルを基準として解釈される相対ファイルパスを指定できます。 それ以外の場合、UWP アプリでは、既定のユーザーデータフォルダーはパッケージのアプリデータフォルダーになります。UWP 以外のアプリの場合、既定のユーザーデータフォルダーは、 `{Executable File Name}.WebView2` アプリの実行可能ファイルの横にある同じディレクトリに作成されます。 プロセスに新しいフォルダーを作成する権限がないディレクトリで実行可能ファイルが実行されている場合、WebView2 の作成に失敗することがあります。 アプリは、完了時にユーザーデータフォルダーをクリーンアップする必要があります。

ブラウザープロセスが WebViews 間で共有されている可能性があることに注意してください。指定したオプションが共有ブラウザープロセスで現在実行されている WebViews のオプションと一致しない場合、WebView の作成は HRESULT_FROM_WIN32 (ERROR_INVALID_STATE) で失敗します。

environment_created_handler は、作成した WebView2Environment が含まれる async 操作に対するハンドラーの結果です。

EnvironmentOptions の browserExecutableFolder、userDataFolder、および additionalBrowserArguments は、環境変数またはレジストリで指定した値によって上書きされる可能性があります。

WebView2Environment を作成すると、次の環境変数がチェックされます。

```
WEBVIEW2_BROWSER_EXECUTABLE_FOLDER
WEBVIEW2_USER_DATA_FOLDER
WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS
WEBVIEW2_RELEASE_CHANNEL_PREFERENCE
```

Override 環境変数が見つかった場合は、browserExecutableFolder、userDataFolder、additionalBrowserArguments の各値を CreateCoreWebView2EnvironmentWithOptions parameters の対応する値の代わりとして使います。

厳密には上書きしませんが、次のような追加の環境変数を設定することができます。

```
WEBVIEW2_WAIT_FOR_SCRIPT_DEBUGGER
```

空でない値が含まれる場合は、スクリプトデバッガーの下で WebView が起動されていることを示します。 この場合、WebView は cdp コマンドを発行し `Page.waitForDebugger` ます。これにより、デバッガーが対応する cdp コマンドを発行して実行を再開するまで、webview 内でスクリプトの実行が一時停止し `Runtime.runIfWaitingForDebugger` ます。 注: この環境変数に相当するレジストリキーはありません。

```
WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER
```

空でない値が含まれる場合は、複数の WebViews を使うホストアプリケーションもサポートするスクリプトデバッガーで WebView が起動されていることを示します。 この値は、ホストアプリケーションによって新しい WebView が作成されるときに、開かれて書き込まれる名前付きパイプの識別子として使われます。 このペイロードは、リモートデバッグポートの JSON ターゲットと一致し、外部デバッガーが特定の WebView インスタンスにアタッチするために使うことができます。 デバッガーによって作成されるパイプの形式は、次のようになり `\\.\pipe\WebView2\Debugger\{app_name}\{pipe_name}` ます。

* `{app_name}` は、ホストアプリケーションの exe ファイル名 (WebView2Example.exe など) です。

* `{pipe_name}` は WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER の値に設定されています。

JSON によって識別されたターゲットのデバッグを有効にするには、次の場所に WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS 環境変数を設定する必要があり `--remote-debugging-port={port_num}` ます。

* `{port_num}` は、CDP サーバーがバインドするポートです。

WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER と WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS 環境変数の両方を設定すると、アプリケーションでホストされている WebViews とその内容がデバッガーなどのサードパーティアプリケーションに公開されることに注意してください。

注: この環境変数に相当するレジストリキーはありません。

これらの環境変数が存在しない場合は、次のようにレジストリが検査されます。 次のレジストリキーがオンになっています。

```
[{Root}\Software\Policies\Microsoft\EmbeddedBrowserWebView\LoaderOverride\{AppId}]
"releaseChannelPreference"=dword:00000000
"browserExecutableFolder"=""
"userDataFolder"=""
"additionalBrowserArguments"=""
```

ブラウザーの更新中に WebView の一部のインスタンスが開かれる可能性が低いシナリオでは、古い Edge ブラウザーの削除がブロックされることがあります。 ディスク領域が不足しないようにするために、新しい WebView の作成は、多数の古いバージョンが存在することが検出された場合、次のエラーで失敗します。

```
ERROR_DISK_FULL
```

使用できる Edge バージョンの既定の最大数は20です。

許可されている古い Edge バージョンの最大数は、次の環境変数の値で上書きできます。

```
WEBVIEW2_MAX_INSTANCES
```

Webview がインストールされたエッジに依存していて、それがアンインストールされると、次のエラーで失敗します。

```
ERROR_PRODUCT_UNINSTALLED
```

まず、Root を HKLM として、次に HKCU を確認します。 AppId は、最初に呼び出し元のプロセスのアプリケーションユーザーモデル ID に設定され、対応するレジストリキーがない場合、AppId は呼び出し元のプロセスの実行可能ファイル名に設定されます。それ以外の場合は、この値が ' * ' である必要があります。 上書きレジストリキーが見つかった場合は、browserExecutableFolder、userDataFolder、additionalBrowserArguments レジストリ値を CreateCoreWebView2EnvironmentWithOptions parameters の対応する値の代わりとして使います。

#### GetAvailableCoreWebView2BrowserVersionString 

> パブリック STDAPI [GetAvailableCoreWebView2BrowserVersionString](#getavailablecorewebview2browserversionstring)(PCWSTR browserExecutableFolder、LPWSTR * versionInfo)

安定したチャネルまたは埋め込みエッジでない場合は、チャネル名などのブラウザーのバージョン情報を取得します。

チャネル名は、β、dev、カナリアです。 BrowserExecutableFolder またはチャネルの優先順位に対して上書きが存在する場合、override が使用されます。 Override がない場合は、GetAvailableCoreWebView2BrowserVersionString に渡されたパラメーターが使われます。

