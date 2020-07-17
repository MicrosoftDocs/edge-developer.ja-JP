---
description: Microsoft Edge DevTools プロトコルバージョン0.2 では、次のツールクライアントがサポートされています。
title: Microsoft Edge DevTools プロトコルバージョン0.2 クライアント (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 92976de257a73fd7206205622a4c79d1277b3950
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882892"
---
# Microsoft Edge DevTools プロトコルバージョン0.2 クライアント (EdgeHTML)  

> [!NOTE]
> Microsoft Edge DevTools プロトコルのバージョン0.2 は、 [windows 10 年 2018 10 月の更新プログラム](/windows/uwp/whats-new/windows-10-build-17763)以降の[windows Insider Preview](https://insider.windows.com/en-us/getting-started/)ビルドでのみ動作します。  

**Devtools プロトコル 0.2**では、次のツールクライアントがサポートされています。

[ ![ Microsoft Edge devtools](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [ ![ visual studio コード](../media/visual-studio-code.png)](#visual-studio-code)のプレビュー [ ![ microsoft visual studio 15.8](../media/visual-studio-2017.png)](#microsoft-visual-studio)

## Microsoft Edge DevTools プレビュー

Microsoft Store からスタンドアロンの[**Microsoft Edge DevTools Preview**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) Windows 10 アプリを使用して、microsoft Edge ([EdgeHTML 17](../../dev-guide.md)以降) を実行しているホストデバイスをリモートでデバッグできます。

DevTools プロトコルのバージョン0.2 には、バージョン0.1 で導入されたコアスクリプトのデバッグ機能に加えて、スタイルとレイアウトのデバッグとコンソール Api の新しいドメインが用意されています。 Edge の DevTools UI では、これは[**要素**](../../devtools-guide/elements.md)、[**コンソール**](../../devtools-guide/console.md)、[**デバッガー**](../../devtools-guide/debugger.md)パネルで利用できる機能に変換されます。 現在、Microsoft Edge リモートデバッグはデスクトップホストに制限されており、今後のリリースで登場する他の Windows 10 デバイスをサポートしています。

Microsoft Edge DevTools Preview アプリを使ったリモートデバッグのセットアップ方法は次のとおりです。 DevTools Protocol バージョン0.2 では、 [windows 10 年10月の2018更新プログラム](/windows/uwp/whats-new/windows-10-build-17763)またはホスト (debugee) コンピューター上の Windows Insider Preview ビルドが必要です。 (デバッガーコンピューターで使用される) Edge の DevTools プレビューアプリは、Windows 10 バージョン 16299 (Windows 10 は、作成者向け更新プログラム、10/2017) 以上で動作します。

**ホスト (debugee) マシンの場合...**

1. WiFi ネットワークを使用している場合は、ネットワークが [**ドメイン**] または [**プライベート**] に設定されていることを確認します。 これを確認するには、 [**Windows Defender セキュリティセンター**](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)アプリを開き、[**ファイアウォール & ネットワーク保護**] をクリックして、使用しているネットワークが*ドメインネットワーク*と*プライベートネットワーク*のどちらであるかを確認します。 

    *パブリック*として表示されている場合は、[**設定**  >  **ネットワーク & インターネット**  >  **wi-fi**] に移動して、ネットワークをクリックし、[*ネットワークプロファイル*] ボタンを [**プライベート**] に切り替えます。

2. Windows の [*設定*] (*開発*者を検索して [*開発者向け機能を使用*] をクリックします) の [**開発者向け**] コントロールパネルを開き、次の操作を行います。 

    a.  **開発者モード**で切り替えます。 これにより、*開発者モード*パッケージがインストールされ、デスクトップのリモートツールが有効になります。

    b.  [**Device Portal**](/windows/uwp/debug-test-perf/device-portal)を有効にする (*ローカルエリアネットワーク接続経由のリモート診断を有効*にする) と**デバイス検出**(*デバイスを USB 接続とローカルネットワークから認識できるよう*にします)。

    c.  **認証**を有効にして、ユーザー名とパスワードを入力します。

    d.  コンピューターの IP アドレスと接続ポート (50443) が表示されていることを確認します。

3. クライアントコンピューターからデバッグするタブを Microsoft Edge で開きます。

**クライアント (デバッガー) コンピューターで...**

1.  Microsoft Store からスタンドアロンの[Microsoft Edge DevTools プレビュー](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab)アプリをインストールして起動します。

2. **リモート**パネルを開き、ホストコンピューターのネットワークの場所 (URL とポート) を入力して、[**接続**] をクリックします。

3. 表示される [信頼されてい*ない証明書*] ダイアログからホストコンピューターの証明書を**インストール**します。

4. Device Portal の認証用に指定したユーザー名とパスワードを入力します。

5. *リモート*パネルでは、ホストコンピューター上のデバッグ可能なページターゲットの一覧が読み込まれます。 いずれかを選択してデバッグを開始します。

6. [**更新**] ボタンを使用して、ホストコンピューター上のリモートページターゲットの一覧を更新して再読み込みします。 [**切断**] ボタンをクリックして、[*リモートデバイスへの接続*] 画面に戻り、別のホストに接続します。

## Visual Studio Code

Microsoft Edge で実行されている Edge とコード拡張[用のデバッガー](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge)を使うと、Visual Studio コードで直接 Microsoft Edge で実行されているスクリプトをデバッグできます。 拡張機能を使用するには、web アプリケーションが localhost から提供されている必要があります。これは、コマンドラインまたは[タスク](https://code.visualstudio.com/docs/editor/tasks)から開始できます。

次の手順をお試しください。

1. Edge VS コード拡張[用のデバッガーを](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge)インストールします。

2. VS コードを再起動し、デバッグするプロジェクトが含まれているフォルダーを開き、コードにブレークポイントを設定します。

3. Localhost[起動タスク](https://code.visualstudio.com/docs/editor/debugging#_launch-configurations)を構成して、プロジェクトの目的のページを開きます。**デバッグ**:  >  **構成の追加...** 例えば：

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

    [*デバッガーの使用*](https://github.com/Microsoft/vscode-edge-debug2#using-the-debugger)について詳しくは、「起動構成の設定」をご覧ください。 

4. Localhost でサーバーを起動し、[**デバッグの開始**] (再生) ボタンを押すか、 `F5` Microsoft Edge を起動します。 ブレークポイントにヒットすると、VS コードにブレークし、そこからコードをさらに検査していくことができます。

詳細については、 [Microsoft Edge ドキュメントの VS コードデバッガーを](https://github.com/Microsoft/vscode-edge-debug2#----vs-code---debugger-for-microsoft-edge--)ご覧ください。

## Microsoft Visual Studio

[Windows 10 年 2018 10 月の更新プログラム](/windows/uwp/whats-new/windows-10-build-17763)で実行されている最新の[**visual Studio**](https://www.visualstudio.com)バージョン (visual studio 15.8 以降) を使用している場合は、ASP.NET または .net のコアプロジェクトの IDE で Microsoft Edge を起動してデバッグすることができます。

Visual Studio で Microsoft Edge のデバッグを設定する方法は次のとおりです。

1.  最新の[**Visual studio**](https://www.visualstudio.com/)をインストールして起動します (visual studio 15.8 以降)。

2. **Visual C#** .net テンプレートのいずれかを使用して、既存の ASP.NET または .net コアプロジェクトを開くか、**新しいプロジェクトを作成します。**

3. プロジェクト**ソリューションエクスプローラー**で、デバッグする JavaScript ファイルを開き、サーバー側コードの場合と同様に、IDE でブレークポイントを設定します。

4. を押して `F5` 、DevTools サーバーを実行している Microsoft Edge を起動します。 ブレークポイントにヒットすると、Visual Studio にブレークし、そこからコードをさらに調べていくことができます。
