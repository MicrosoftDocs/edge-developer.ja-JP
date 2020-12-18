---
description: Microsoft Edge DevTools Protocol Version 0.2 は、次のツール クライアントをサポートしています。
title: Microsoft Edge DevTools プロトコル バージョン 0.2 クライアント (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b471ff5a4051411fc205a269d811524c38acac72
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234415"
---
# Microsoft Edge DevTools プロトコル バージョン 0.2 クライアント (EdgeHTML)  

> [!NOTE]
> Microsoft Edge DevTools プロトコルのバージョン 0.2 は [、Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) 以降の [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) ビルドでのみ動作します。  

**DevTools Protocol 0.2 は、次** のツール クライアントをサポートしています。

[ ![ Microsoft Edge DevTools Preview](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [ ![ Visual Studio Code](../media/visual-studio-code.png)](#visual-studio-code) Microsoft Visual Studio [ ![ 15.8](../media/visual-studio-2017.png)](#microsoft-visual-studio)

## Microsoft Edge DevTools プレビュー

Microsoft Store からスタンドアロン [**の Microsoft Edge DevTools Preview**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) Windows 10 アプリを使用して、Microsoft Edge を実行しているホスト デバイス[(EdgeHTML 17](../../dev-guide/index.md) 以降) をリモートでデバッグできます。

DevTools プロトコルのバージョン 0.2 には、バージョン 0.1 で導入されたコア スクリプト デバッグ機能に加えて、スタイルとレイアウトのデバッグとコンソール API 用の新しいドメインが提供されています。 Edge DevTools UI では、これは要素パネル、コンソール パネル[****](../../devtools-guide/elements.md)、デバッガー パネルで利用可能な[**機能**](../../devtools-guide/console.md)に[**変換**](../../devtools-guide/debugger.md)されます。 現在、Microsoft Edge のリモート デバッグはデスクトップ ホストに限定されています。今後のリリースで予定されている他の Windows 10 デバイスもサポートされます。

Microsoft Edge DevTools Preview アプリを使ってリモート デバッグをセットアップする方法を次に示します。 DevTools プロトコル バージョン 0.2 では、ホスト (デバッグ先) コンピューター上に [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) 以降の Windows Insider Preview ビルドが必要です。 Edge DevTools Preview アプリ (デバッガー コンピューターで使用) は、Windows 10 バージョン 16299 (Windows 10 Fall Creators Update、10/2017) 以上で実行されます。

**ホスト (デバッグ先) コンピューターで...**

1. WiFi ネットワークを使用している場合は、ネットワークがドメインまたはプライベートとして **マーク付け** されている必要 **があります**。 これを確認するには[**、Windows Defender**](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)セキュリティ センター アプリを開き、**ファイアウォール &** ネットワーク保護をクリックし、ネットワークがドメイン ネットワークまたはプライベート ネットワークとして** 一覧表示されるのか確認*します。* 

    If its listed as *Public,* go to **Settings**  >  **Network & Internet**  >  **Wi-Fi,** click on your network and toggle the Network *profile* button to **Private**.

2. *Windows*の**設定で [開発者**向け] コントロール** パネルを開き (開発者向けの検索を行い、[開発者向け機能の使用] をクリックします)、*次*の操作を行います。 

    a.  開発者モードを **切り替えます**。 これにより、開発者モード *パッケージがインストール* され、デスクトップ用のリモート ツールが有効になります。

    b.  [**Device Portal**](/windows/uwp/debug-test-perf/device-portal) (ローカル*エリア ネットワーク*接続でリモート診断を有効にする) とデバイス**検出を有効**にします (デバイスを USB 接続とローカル ネットワークに表示*します*)。

    c.  認証を **有効に** し、ユーザー名とパスワードを入力します。

    d.  コンピューターの IP アドレスと接続ポート (50443) が表示されます。

3. クライアント コンピューターからデバッグする Microsoft Edge のタブを開きます。

**クライアント (デバッガー) コンピューターで...**

1.  Microsoft Store からスタンドアロン [の Microsoft Edge DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) アプリをインストールして起動します。

2. リモート パネル **を開** き、ホスト マシンのネットワークの場所 (URL とポート) を入力し、[接続] をクリック **します**。

3. **[** 信頼されていない証明書] ダイアログボックスが表示 *されたら、ホスト コンピューターの* 証明書をインストールします。

4. Device Portal 認証用に指定したユーザー名/パスワードを指定します。

5. リモート *パネル* は、デバッグ可能なページ ターゲットの一覧をホスト コンピューターに読み込む。 デバッグを開始するには、1 つを選択します。

6. [更新 **] ボタン** を使用して、ホスト コンピューター上のリモート ページ ターゲットの一覧を更新して再読み込みします。 [切断 **]** ボタンをクリックして、リモート デバイスへの *接続画面に戻* り、別のホストに接続します。

## Visual Studio Code

Debugger [for Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) VS Code 拡張機能を使用すると、Microsoft Edge で実行されているスクリプトを、Visual Studio Code で直接デバッグできます。 この拡張機能では、localhost から Web アプリケーションを提供する必要があります。このサービスは、コマンドラインまたはタスクから開始 [できます](https://code.visualstudio.com/docs/editor/tasks)。

次の手順をお試しください。

1. Debugger [for Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) VS Code 拡張機能をインストールします。

2. VS Code を再起動し、デバッグするプロジェクトを含むフォルダーを開き、コードにブレークポイントを設定します。

3. localhost 起動タスク[を構成して](https://code.visualstudio.com/docs/editor/debugging#_launch-configurations)、プロジェクトの目的のページである [**デバッグ**構成の追加]  >  **を開きます**。例えば：

    ```json
    {
        "version": "0.2.0",
        "configurations": [

            {
                "name": "Launch localhost",
                "type": "edge",
                "request": "launch",
                "url": "http://localhost/mypage.html",
                "webRoot": "${workspaceFolder}/wwwroot"
            }
        ]
    }
    ```

    [*デバッガーの使用には、*](https://github.com/Microsoft/vscode-edge-debug2#using-the-debugger) 起動構成設定の詳細があります。 

4. localhost でサーバーを起動し、[デバッグの開始 **(再生** ) ボタンを押す、または Microsoft `F5` Edge を起動します。 ブレークポイントにヒットすると、VS Code に分割し、そこからさらにコードを検査してステップ実行できます。

詳細については [、MICROSOFT Edge のドキュメントの VS Code デバッガーを参照](https://github.com/Microsoft/vscode-edge-debug2#----vs-code---debugger-for-microsoft-edge--) してください。

## Microsoft Visual Studio

[Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763)で実行されている最新の[**Visual Studio**](https://www.visualstudio.com)バージョン (Visual Studio 15.8 以降) を使用すると、任意の ASP.NET または .NET Core プロジェクトで IDE から Microsoft Edge を起動してデバッグできます。

Microsoft Edge のデバッグをセットアップする方法を次に示Visual Studio。

1.  最新のバージョンをインストールして [**起動Visual Studio**](https://www.visualstudio.com/) (Visual Studio 15.8 以降)。

2. **Visual C#** .NET ASP.NETを使用して、既存**** のプロジェクトまたは .NET Core プロジェクトを開く、または新しいプロジェクトを作成します。

3. プロジェクト ソリューション エクスプローラー **で**、デバッグする JavaScript ファイルを開き、サーバー側コードと同様に IDE 内にブレークポイントを設定します。

4. `F5`DevTools Server を実行している Microsoft Edge を押して起動します。 ブレークポイントにヒットすると、ブレークポイントに分割Visual Studio、そこからコードをさらに検査してステップ実行できます。
