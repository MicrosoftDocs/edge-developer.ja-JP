---
description: Microsoft Edge WebView2 を使用してアプリをリリースするときの配布オプション
title: Microsoft Edge WebView2 アプリケーションの配布
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/21/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 7db610ff1133b1b5b380372422f1f2f10981e583
ms.sourcegitcommit: 24151cc65bad92d751a8e7a868c102e1121456e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "11052187"
---
# WebView2 を使用したアプリケーションの配布  

WebView2 アプリケーションを配布するときには、アプリが起動される前に、バッキング web プラットフォーム- [WebView2 Runtime](#understanding-the-webview2-runtime) が存在することを確認してください。  この記事では、開発者が WebView2 ランタイムをインストールする方法について説明し、WebView2 アプリケーション用の2つの配布モードを使用する方法について説明します。  [Evergreen](#evergreen-distribution-mode) と [Fixed バージョン](#fixed-version-distribution-mode)。  

## Evergreen 配布モード  

> [!NOTE]
> ほとんどの開発者は、Evergreen 配布モードをお勧めします。  

Evergreen 配布モードでは、アプリが最新の機能とセキュリティ更新プログラムを利用していることが保証されます。  次のような特徴があります。  

*   基礎となる web プラットフォーム \ (WebView2 Runtime) は、開発者による追加の作業を行わなくても自動的に更新されます。  
*   Evergreen 配布モードを使うすべてのアプリケーションでは、Evergreen WebView2 ランタイムの共有コピーを使用します。これにより、ディスク領域を節約できます。  

### WebView2 ランタイムについて  

WebView2 Runtime は再配布可能なランタイムであり、WebView2 アプリケーションのバッキング web プラットフォームとして機能します。  この概念は、C++/.NET アプリの VC + + または .NET ランタイムに似ています。  このように、ランタイムは、アプリケーションに合わせて微調整された Microsoft Edge \ (Chromium \) バイナリを変更します。  ランタイムは、インストール時にユーザーに表示されるブラウザーとしては表示されません。たとえば、ユーザーはブラウザーのデスクトップショートカットまたはスタートメニューエントリを持っていません。  

開発とテストのために、開発者は、このランタイム、またはバッキング web プラットフォーム用の非安定した Microsoft Edge \ (Chromium \) ブラウザーチャネルを使用できます。  運用環境では、開発者は、アプリケーションを起動する前に、ユーザーデバイスにランタイムが存在することを確認する必要があります。  アプリが運用環境のブラウザーに依存しないようにするために、Microsoft Edge の WebView2 の使用はできません。  

開発者は、次の理由により、ブラウザーに依存しないようにする必要があります。  

*   Microsoft Edge \ (Chromium \) は、すべてのユーザーデバイスに存在することが保証されていません。  たとえば、Windows Update から切断された、または Microsoft によって直接管理されていないデバイス (Enterprise/EDU market の大部分) には、ブラウザーが含まれていないことがあります。  開発者に WebView2 ランタイムの配布を許可することで、アプリの前提条件として、ブラウザーに依存することを回避できます。
*   ブラウザーやアプリにはさまざまなユースケースがあるため、ブラウザーで依存関係を取得すると、アプリに意図しない副次的な影響が生じる可能性があります。  たとえば、IT 管理者は、内部の web サイトとの互換性を維持するためにブラウザーをバージョン管理することができます。  WebView2 Runtime を使用すると、ブラウザーの更新がアクティブに管理されている間、アプリは evergreen を維持できます。  
*   ブラウザーとは異なり、ランタイムはアプリケーションシナリオ向けに開発およびテストされていますが、場合によっては、ブラウザーでまだバグ修正が用意されていないことがあります。  

Evergreen WebView2 Runtime は、Windows の将来のリリースで受信トレイを出荷する予定です。  ランタイムをより汎用的に使用できるようにするには、開発者が実行している運用アプリケーションと共にランタイムを展開することをお勧めします。  

### Evergreen WebView2 ランタイムの展開  

デバイス上のすべての Evergreen アプリには、1つの Evergreen WebView2 ランタイムのインストールのみが必要です。  [WebView2 runtime ダウンロードページ][Webview2Installer]には、次のような Evergreen ランタイムを展開するための開発者のために、いくつかのツールが用意されています。  

*   WebView2 Runtime ブートストラップ \ (まもなくリリースされます) は、わずか \ (約 2 MB \ 2 MB) のインストーラーです。  このインストーラーは、ユーザーのデバイスアーキテクチャと一致する Microsoft サーバーから Evergreen ランタイムをダウンロードしてインストールします。  
*   ブートストラップをダウンロードするためのリンク (すぐにリリースされる) は、ブートストラップをプログラムでダウンロードするための開発者向けのリンクです。
*   WebView2 Runtime Standalone Installer は、オフライン環境で Evergreen WebView2 ランタイムをインストールできる完全なインストーラーです。  

現時点では、ブートストラップとスタンドアロンインストーラーは両方ともコンピューターごとにインストールをサポートします。昇格が必要です。  昇格せずに実行すると、Windows ユーザーアカウント制御プロンプトが表示され、ユーザーにアクセス許可の昇格を要求します。  

アプリケーションが起動される前にランタイムが既にインストールされていることを確認するために、次のワークフローをお勧めします。  シナリオによっては、ワークフローを調整できます。  また、将来のサンプルコードも提供します。  

#### オンラインのみの展開  

エンドユーザーがインターネット接続を使用すると見なされるオンラインのみの展開シナリオがある場合は、次の手順を実行します。  

*   アプリケーションのセットアップ中に、次のいずれかの方法でランタイムが既にインストールされているかどうかを確認します。  
    *   `pv (REG_SZ)`、のいずれかでレジストリキーが存在するかどう `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\ClientState\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}` かを調べます。  
    *   WebView2 API [GetAvailableCoreWebView2BrowserVersionString](../reference/win32/0-9-622/webview2-idl.md#getavailablecorewebview2browserversionstring) を呼び出して、VERSIONINFO が NULL であるかどうかを確認します。  
*   ランタイムがインストールされていない場合は、リンクを使用してブートストラップをプログラムでダウンロードします。  
*   昇格したプロセスまたはコマンドプロンプトから、 `MicrosoftEdgeWebview2Setup.exe /silent /install` サイレントインストールのためにブートストラップを呼び出します。  

このワークフローでは、必要な場合にのみランタイムをインストールすることができます。そのためには、インストーラーをパッケージ化したり、ユーザーデバイスのアーキテクチャを検出したりする必要はありません。また、ランタイムをサイレントモードでインストールすることもできます。  必要に応じてブートストラップをプログラムでダウンロードする代わりに、アプリケーションと共にパッケージ化することもできます。  

#### オフライン展開  

アプリの展開がオフラインで動作する場合は、次の手順を実行します。  

*   [スタンドアロンインストーラー][Webview2Installer]をダウンロードします。  
*   アプリケーションのインストーラーまたはアップデーターにインストーラーを含めます。  
*   アプリケーションのセットアップ中に、次のいずれかの方法でランタイムが既にインストールされているかどうかを確認します。  
    *   `pv (REG_SZ)`、のいずれかでレジストリキーが存在するかどう `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\ClientState\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}` かを調べます。  
    *   WebView2 API [GetAvailableCoreWebView2BrowserVersionString](../reference/win32/0-9-622/webview2-idl.md#getavailablecorewebview2browserversionstring) を呼び出して、VERSIONINFO が NULL であるかどうかを確認します。  
*   ランタイムがインストールされていない場合は、昇格されたプロセスまたはコマンドプロンプトから、サイレントインストールのためにスタンドアロンインストーラーを起動し `MicrosoftEdgeWebView2RuntimeInstaller{X64/X86/ARM64}.exe /silent /install` ます。  

## 固定バージョンの配布モード  

> [!NOTE]
> 修正されたバージョンの配布モードはまだ使用できません。  

制約のある環境の場合は、以前のバージョンの配布モードという名前の固定されたバージョンをサポートする予定です。  修正済みのバージョンの配布モードでは、開発者は WebView2 ランタイムの特定のバージョンを選択してパッケージ化することができます。  修正されたバージョンの配布モードでは、どのバージョンの WebView2 ランタイムをアプリケーションで使うか、ユーザーコンピューターが更新されるタイミングを制御することができます。  固定バージョンの配布モードでは、自動更新は提供されません。開発者は、更新プログラムを適用することを計画しておく必要があります。  


<!-- links -->  

[ConceptsVersioning]: ./versioning.md "ブラウザーのバージョンと WebView2 についてMicrosoft ドキュメント"  
[ReferenceWin3209622WebviewIdl]: ../reference/win32/0-9-622/webview2-idl.md  "Globals |Microsoft ドキュメント"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 Installer"  
