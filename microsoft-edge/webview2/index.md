---
description: Microsoft Edge WebView 2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリの Microsoft Edge WebView 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: b1ec0c43b57fb107490ddb34b330bb6ec378ac41
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654267"
---
# Microsoft Edge WebView2 (開発者用プレビュー)

Microsoft Edge WebView2 コントロールでは、 [Microsoft edge (Chromium)](https://www.microsoftedgeinsider.com/)を使ってアプリケーションの web コンテンツをレンダリングエンジンとしてホストすることができます。

現在、WebView2 コントロールは、開発者プレビューに含まれていて、ソリューションのプロトタイプを作成し、フィードバックを共有して将来の安定した API を形成することができます。 プレビュー時に API を進化させるために、いくつかの変更が行われている可能性があります。この場合は、WebView2 SDK と Microsoft Edge (Chromium) ブラウザーの両方が更新されている必要があります。 互換性のある変更は、SDK の[リリースノート](./releasenotes.md)に記載されています。 これは、WebView2 がベータ版であり、安定しているため、ロックダウンされます。

## サポートされているプラットフォーム

開発者用プレビューは、windows 10、Windows 8.1、Windows 8、windows 7、windows server 2016、windows server 2012、または Windows Server 2008 R2 で、Win32 C/c + + および Windows フォームと WPF で利用できます。 3.0 4.6.2 以降では、 WinUI 3.0 の Alpha バージョンは、[ここで](https://docs.microsoft.com/uwp/toolkits/winui3/)利用できます。

## 作業の開始

WebView2 コントロールを使用してアプリケーションをビルドしてテストするには、 [Microsoft Edge (Chromium)](https://www.microsoftedgeinsider.com/download/)と[WebView2 SDK](https://aka.ms/webviewnuget)の両方をインストールする必要があります。 開始するには、次のいずれかのオプションを選択してください。

* [Win32 C/C + + の概要](./gettingstarted/win32.md)
* [WPF の概要](./gettingstarted/wpf.md)
* [Windows フォームの概要](./gettingstarted/winforms.md)

[WebView2 フィードバック](https://aka.ms/webviewfeedback)リポジトリにフィードバックをお寄せください。

## WebView2 サンプル

[WebView2 サンプル](https://github.com/MicrosoftEdge/WebView2Samples)リポジトリには、WebView2 SDK のすべての機能とその API 使用パターンを示すサンプルが含まれています。 WebView2 SDK にさらに機能を追加する際には、サンプルアプリケーションを定期的に更新します。

## アプリの配布

WebView2 コントロールは、Microsoft Edge (Chromium) ブラウザーを利用します。 アプリを配布するときは、アプリケーションが実行されるすべてのユーザーコンピューターに Edge ブラウザーがインストールされていることを確認することが重要です。 また、インストールされているバージョンとチャネル (たとえば、Stable、ベータ、Dev、またはカナリア) についても知っておく必要があります。 WebView2 コントローラーは、コンピューターにインストールしたときに、最も安定バージョンのブラウザーを使用します。

### 今後の予定変更

アプリケーションが実行されるすべてのユーザーコンピューターで Edge ブラウザーが利用できない場合や、Edge ブラウザーのインストールプロセスの制御が難しい場合があることを認識しています。 クライアントの Microsoft Edge ブラウザーのインストール状態に関係なく、すべてのコンピューターでアプリケーションが実行されるようにするには、Microsoft Edge WebView2 ランタイムを解放します。 WebView2 を更新して、インストールされているブラウザーのプレリリース版を検索する前に、安定バージョンのランタイムを検索します。

また、一部のアプリ開発者は、制約のある環境で動作するため、2つの配布オプション、evergreen、修正バージョンをサポートすることを目的としています。

Evergreen は、ほとんどの開発者に推奨される配布モデルです。 このモードでは、WebView2 ランタイムの更新プログラムは、アプリケーションを追加しなくても、自動的に最新の状態に保つことができます。 この自己更新モデルを使用すると、アプリが、ホストされた web コンテンツの最新機能とセキュリティ更新プログラムを利用できることが保証されます。

制限された環境では、固定バージョンの配布モデルもサポートします。 このモデルでは、アプリケーションで特定の WebView2 バージョンを選択してパッケージ化します。 WebView バージョンの更新はアプリケーションの責任となり、管理された Microsoft update メカニズムに依存しません。 このモデルは、ブラウザーのバージョンに対する完全な制御を可能にすることが重要である場合や、アプリケーションで利用されている更新時間を設定する必要がある場合に選びます。

## Microsoft Edge WebView2 ランタイム

Microsoft Edge WebView2 Runtime は、WebView2 アプリケーションで使用するために最適化されたブラウザーバイナリのパッケージです。 クライアント Edge ブラウザーをインストールすると、スタンドアロンとして、または並行して機能します。 実行時の1回のインストールでは、任意の数の WebView2 アプリケーションがサポートされます。 ランタイムのインストールは、ブラウザーからエンドユーザーへのインストールとしては表示されません。つまり、デスクトップショートカット、[スタート] メニューエントリ、またはプロトコル登録がありません。

WebView2 を利用するアプリケーションでは、Microsoft Edge WebView2 ランタイムのインストールが行われていることを確認する必要があります。 アプリケーションのインストール時には、現在のインストールの状態を確認する必要があります。これは、 [GetAvailableCoreWebView2BrowserVersionString](./reference/win32/0-9-488/webview2-idl.md#getavailablecorewebview2browserversionstring)を使用して確認できます。 WebView2 ランタイムが利用できない場合は、Microsoft Edge WebView2 ランタイムインストーラーをインストールフローにチェーンする必要があります。

## Microsoft Edge WebView2 SDK

アプリ内で WebView2 を使うには、アプリケーションに[WEBVIEW2 SDK](https://aka.ms/webviewnuget)をインストールして参照する必要があります。 NuGet リリースには、リリースバージョンとプレリリースバージョンの両方が含まれています。 リリースバージョンには、現在一般的な可用性にリリースする予定のパブリック Api が含まれています。

プレリリース版には、追加の[実験的な api](./reference/win32/0-9-488-reference-webview2.md#experimental)が含まれています。 これらは、評価する Api と機能であり、リリースバージョンに昇格する前にフィードバックをお[送り](https://aka.ms/webviewfeedback)します。

## 今後のバージョンに対する開発

開発のために、ベータ、Dev、またはカナリアをターゲットにして、将来のバージョンでアプリケーションが動作するようにしたり、今後の機能を利用したりすることができます。 プレリリース版のチャネルはすべて、インストールされているクライアントの Microsoft Edge ブラウザーによって提供されます。 これらのチャネルのいずれかをターゲットにするには、開発用コンピューターにインストールされている Edge ブラウザーが、必要なチャネルになっていることを確認します。 開発者は、レジストリキーまたは環境変数を使用して、最も安定性の低いバージョンの WebView2 を変更することができます。 詳細については、 [CreateCoreWebView2EnvironmentWithOptions](./reference/win32/0-9-488/webview2-idl.md#createcorewebview2environmentwithoptions)を参照してください。

## デバッグ WebView2

### DevTools

[Microsoft Edge (Chromium) 開発者ツール](https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium)を使用して、ブラウザーと同じように、WebView に表示されている web コンテンツをデバッグすることができます。 [WebView] ウィンドウにフォーカスが置かれた状態で、キーを押すか、また `F12` `Ctrl`  +  `Shift`  +  `I` は右クリックして、[ `Inspect` 開発者ツール] を開きます。

:::image type="complex" source="./media/f12.png" alt-text="F12":::
   F12
:::image-end:::  

<!--![F12](./media/f12.png)  -->  

**注: ネイティブデバッガーがアタッチされている Visual Studio でアプリケーションをデバッグすると、 `F12` 開発者ツールではなくネイティブデバッガーがトリガーされることがあります。 使用する `Ctrl`  +  `Shift`  +  `I` か、右クリックして、 `Inspect` 潜在的なホットキーの競合を回避します。**

### Visual Studio

Visual Studio 2019 (最小バージョン 16.4 Preview 2) でスクリプトデバッガーを使って、IDE から直接 WebView2 内でスクリプトをデバッグできます。 C++ ワークロード**を使用したデスクトップ開発**の**JavaScript 診断**コンポーネントがインストールされていることを確認します。

:::image type="complex" source="./media/vs-js-diagnostics.jpg" alt-text="Visual Studio JavaScript 診断ツール":::
   Visual Studio JavaScript 診断ツール
:::image-end:::  

<!--![vs-js-diagnostics](./media/vs-js-diagnostics.jpg)  -->  

プロジェクトを右クリックして、[**プロパティ**] を選択します。 [**構成プロパティ**  >  の**デバッグ**  >  **デバッガーの種類**] で、[ **JavaScript (WebView2)** ] オプションを選んで、WebView2 スクリプトのデバッグを有効にします。 詳細はこちらをご覧ください。

:::image type="complex" source="./media/vs-script-debugger.jpg" alt-text="Visual Studio スクリプトデバッガー":::
   Visual Studio スクリプトデバッガー
:::image-end:::  

<!--![vs-script-debugger](./media/vs-script-debugger.jpg)  -->  

### Visual Studio Code

Visual Studio コードを使って、IDE から直接 WebView2 のスクリプトをデバッグすることもできます。 詳細について[は、ここ](https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications)をクリックしてください。

## WebView2 チームと連絡を取り合う  

フィードバックを共有することで、より充実した WebView2 エクスペリエンスを構築できます。 [フィードバックリポジトリ](https://aka.ms/webviewfeedback)にアクセスして、機能のリクエストまたはバグレポートを送信します。

また、既知の問題を検索するのに適した場所です。
開発者向けプレビューでは、より優れた WebView を構築できるようにテレメトリデータを収集することもできます。 ユーザーは、ブラウザーで edge://settings/privacy に移動し、ブラウザーデータの収集をオフにすることで、WebView データの収集をオフにすることができます。
