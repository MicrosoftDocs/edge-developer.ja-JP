---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2Environment
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2Environment。
ms.openlocfilehash: 79bc9908d0fd12d4606311b959cbc6bc0c384c2d
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878919"
---
# WebView2 クラス (CoreWebView2Environment クラス) 

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

これは、WebView2 環境を表します。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[この文字列](#browserversionstring) | CoreWebView2Environment が安定していない場合は、チャネル名を含む現在ののブラウザーバージョン情報。
[新機能をご利用いただけます](#newbrowserversionavailable) | 新しいバージョンの Edge ブラウザーがインストールされていて、WebView2 経由で使用できるようになったときに、Newfactorserver Available イベントが発生します。
[CompareBrowserVersions](#comparebrowserversions) | ブラウザーのバージョンを正しく比較して、どのバージョンがより新しいか、以前のバージョンであるかを確認します。
[CreateAsync](#createasync) | インストールされている Edge バージョンを使って、evergreen WebView2 環境を作成します。
[CreateCoreWebView2CompositionControllerAsync](#createcorewebview2compositioncontrollerasync) | ビジュアルホスティングで使用する新しい WebView を非同期的に作成します。
[CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync) | 新しい WebView を非同期的に作成します。
[CreateCoreWebView2PointerInfo](#createcorewebview2pointerinfo) | 空の CoreWebView2ExperimentalPointerInfo を作成します。
[CreateWebResourceResponse](#createwebresourceresponse) | 新しい web リソース応答オブジェクトを作成します。
[Getserverした文字列](#getavailablebrowserversionstring) | 安定したチャネルまたは埋め込みエッジでない場合は、チャネル名などのブラウザーのバージョン情報を取得します。
[GetProviderForHwnd](#getproviderforhwnd) | 指定された HWND に対応する CoreWebView2CompositionController の UI オートメーションプロバイダーを返します。

WebViews は、環境パラメーターと共に指定したブラウザープロセスで実行され、環境から作成されたオブジェクトを同じ環境で使う必要があります。 異なる環境での使用は、互換性が保証されるとは限りません。また、失敗する可能性があります。

## Members

#### この文字列 

CoreWebView2Environment が安定していない場合は、チャネル名を含む現在ののブラウザーバージョン情報。

> パブリック文字列の[文字列](#browserversionstring)

これは、GetAvailableCoreWebView2BrowserVersionString API の形式と一致します。 チャネル名は、"ベータ"、"dev"、"カナリア" のようになります。

#### 新機能をご利用いただけます 

新しいバージョンの Edge ブラウザーがインストールされていて、WebView2 経由で使用できるようになったときに、Newfactorserver Available イベントが発生します。

> パブリックイベント EventHandler< object > [New参照サーバーの使用可能](#newbrowserversionavailable)

新しいバージョンのブラウザーを使用するには、新しい環境と WebView を作成する必要があります。 このイベントは、コードが実行されているのと同じエッジチャネルから新しいバージョンの場合にのみ発生します。 インストールされている Edge で実行されていない場合、イベントは発生しません。

ユーザーデータフォルダーは一度に1つのブラウザープロセスでしか使用できないため、WebViews で新しいバージョンのブラウザーを使用して同じユーザーデータフォルダーを使用する場合は、最初に古いバージョンのブラウザーを使用している環境と WebViews を閉じる必要があります。 または、単に、アプリを再起動するようにユーザーに求めます。

#### CompareBrowserVersions 

ブラウザーのバージョンを正しく比較して、どのバージョンがより新しいか、以前のバージョンであるかを確認します。

> パブリック静的な int [CompareBrowserVersions](#comparebrowserversions)(文字列 version1、文字列 version2)

Version1 が version2 よりも小さいか、等しいか、または大きいかに応じて、-1、0、または1を返します。

##### パラメーター
* `version1` 比較するいずれかのバージョン文字列。 

* `version2` 比較する他のバージョン文字列。

#### CreateAsync 

インストールされている Edge バージョンを使って、evergreen WebView2 環境を作成します。

> パブリック静的非同期タスク< [CoreWebView2Environment](microsoft-web-webview2-core-corewebview2environment.md)  >  [createasync](#createasync)(string browserexecutablefolder、文字列 userdatafolder、CoreWebView2EnvironmentOptions options)

##### パラメーター
* `browserExecutableFolder` 埋め込まれた端を含むフォルダーの相対パス。 

* `userDataFolder` userDataFolder を指定して、WebView2 の既定のユーザーデータフォルダーの場所を変更できます。 

* `options` WebView2 環境の作成に使用するオプション。

#### CreateCoreWebView2CompositionControllerAsync 

> [!NOTE]
> これは、SDK バージョン[0.9.538-プレリリース](../../../releasenotes.md#09538)で出荷される[実験的な API](../../../concepts/versioning.md#experimental-apis)です。

ビジュアルホスティングで使用する新しい WebView を非同期的に作成します。

> パブリック async タスク< [CoreWebView2CompositionController](microsoft-web-webview2-core-corewebview2compositioncontroller.md)  >  [CreateCoreWebView2CompositionControllerAsync](#createcorewebview2compositioncontrollerasync)(IntPtr parentwindow)

parentWindow は、アプリが WebView のビジュアルツリーを接続する HWND です。 これは、WebView に対応するポインターまたはマウスの入力をアプリが受け取るようにする HWND です (そして、SendMouseInput/Sendpointer 入力を使って転送する必要があります)。 アプリが WebView ビジュアルツリーを別のウィンドウの下に移動する場合、ビジュアルツリーの新しい親 HWND を更新するために CoreWebView2CompositionController ウィンドウを設定する必要があります。

作成された CoreWebView2CompositionController で RootVisualTarget プロパティを設定して、ブラウザーのビジュアルツリーをホストするためのビジュアルを提供します。

アプリケーションは、プロセスまたはアプリケーションウィンドウのアプリケーションユーザーモデル ID を設定することをお勧めします。 何も設定されていない場合は、WebView の作成中に、生成されたアプリケーションユーザーモデル ID が parentWindow のルートウィンドウに設定されます。

#### CreateCoreWebView2ControllerAsync 

新しい WebView を非同期的に作成します。

> パブリック async タスク< [CoreWebView2Controller](microsoft-web-webview2-core-corewebview2controller.md)  >  [CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync)(IntPtr parentwindow)

parentWindow は、WebView を表示して入力を受け取る HWND です。 WebView は、WebView の作成中に、指定されたウィンドウに子ウィンドウを追加します。 兄弟ウィンドウの順序によって影響を受ける Z オーダーやその他の項目にも影響します。

アプリケーションは、プロセスまたはアプリケーションウィンドウのアプリケーションユーザーモデル ID を設定することをお勧めします。 何も設定されていない場合は、WebView の作成中に、生成されたアプリケーションユーザーモデル ID が parentWindow のルートウィンドウに設定されます。

#### CreateCoreWebView2PointerInfo 

> [!NOTE]
> これは、SDK バージョン[0.9.538-プレリリース](../../../releasenotes.md#09538)で出荷される[実験的な API](../../../concepts/versioning.md#experimental-apis)です。

空の CoreWebView2ExperimentalPointerInfo を作成します。

> パブリック[CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) [CreateCoreWebView2PointerInfo](#createcorewebview2pointerinfo)()

返された CoreWebView2ExperimentalPointerInfo には、Sendポインタ入力を呼び出す前に、関連するすべての情報を設定する必要があります。

#### CreateWebResourceResponse 

新しい web リソース応答オブジェクトを作成します。

> パブリック HttpResponseMessage [CreateWebResourceResponse](#createwebresourceresponse)(ストリームコンテンツ、int StatusCode、文字列の理由語句、文字列ヘッダー)

ヘッダーは、改行で区切られた直接応答ヘッダー文字列です。 空のヘッダー文字列を使ってこのオブジェクトを作成し、CoreWebView2HttpResponseHeaders を使用してヘッダー行を1行ずつ作成することもできます。 その他のパラメーターについては、「CoreWebView2WebResourceResponse」を参照してください。

#### Getserverした文字列 

安定したチャネルまたは埋め込みエッジでない場合は、チャネル名などのブラウザーのバージョン情報を取得します。

> パブリック静的な文字列[Getserverの](#getavailablebrowserversionstring)文字列 (String browserExecutableFolder)

##### パラメーター
* `browserExecutableFolder` 埋め込まれた端を含むフォルダーの相対パス。

#### GetProviderForHwnd 

> [!NOTE]
> これは、SDK バージョン[0.9.538-プレリリース](../../../releasenotes.md#09538)で出荷される[実験的な API](../../../concepts/versioning.md#experimental-apis)です。

指定された HWND に対応する CoreWebView2CompositionController の UI オートメーションプロバイダーを返します。

> パブリックオブジェクト[Getproviderforhwnd](#getproviderforhwnd)(IntPtr hwnd)

