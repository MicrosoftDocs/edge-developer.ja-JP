---
description: Microsoft Edge DevTools プロトコルバージョン0.1 では、次のツールクライアントがサポートされています。
title: DevTools プロトコルバージョン0.1 クライアント (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 5fdf375634bb63c944b3fe09d1c0cbd5a935dcd7
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882766"
---
# DevTools プロトコルバージョン0.1 クライアント (EdgeHTML)  

> [!NOTE]
> Microsoft Edge の DevTools プロトコルは、 [windows 10 年4月の2018更新プログラム](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97)以降の[windows Insider Preview](https://insider.windows.com/en-us/getting-started/)ビルドでのみ動作します。

**Devtools プロトコル 0.1**では、次のツールクライアントがサポートされています。

[ ![ Microsoft Edge devtools](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [ ![ microsoft Visual Studio 15.7 preview 2](../media/visual-studio-2017.png)](#microsoft-visual-studio-preview)のプレビュー

## Microsoft Edge DevTools プレビュー

Microsoft Store からスタンドアロンの[**Microsoft Edge DevTools Preview**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) Windows 10 アプリを使用して、microsoft Edge ([EdgeHTML 17](../../dev-guide.md)以降) を実行しているホストデバイスをリモートでデバッグできます。

DevTools プロトコルのこの暫定バージョン0.1 リリースでは、ブレークポイントの設定、コードのステップ実行、スタックトレースの表示など、基本的なデバッグ機能を提供します。 エッジ DevTools UI では、[**デバッガー**](../../devtools-guide/debugger.md)パネルで使用可能な機能、マイナスキャッシュ検査 (Web ストレージ、Service Worker、cache API、IndexedDB) に変換されます。 現在、Microsoft Edge リモートデバッグはデスクトップホストに制限されており、今後のリリースで登場する他の Windows 10 デバイスをサポートしています。

Microsoft Edge DevTools Preview アプリを使ったリモートデバッグのセットアップ方法は次のとおりです。 DevTools プロトコルは preview になっており、 [windows 10 年 4 2018 月の更新プログラム](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97)または、ホスト (debugee) コンピューター上の Windows Insider preview ビルドを後で行う必要があります。 (デバッガーコンピューターで使用されている) Edge の DevTools プレビューアプリは、アプリの作成者の更新 (バージョン 1709) および Windows Insider Preview ビルドで実行されます。

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

## Microsoft Visual Studio Preview

最新の[**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/)ビルド (visual Studio 15.7 preview 1 以降) を使用して、ASP.NET または .net コアプロジェクトの IDE から Microsoft Edge を起動してデバッグすることができます。 現在、DevTools プロトコルはプレビューに含まれており、 [Windows Insider preview](https://insider.windows.com/en-us/getting-started/)ビルドを実行している必要があります。

Visual Studio で Microsoft Edge のデバッグを設定する方法は次のとおりです。

1.  最新の[**Visual Studio preview**](https://www.visualstudio.com/vs/preview/)ビルド (visual Studio 15.7 preview 1 以降) をインストールして起動します。

2. **Visual C#** .net テンプレートのいずれかを使用して、既存の ASP.NET または .net コアプロジェクトを開くか、**新しいプロジェクトを作成します。**

3. プロジェクト**ソリューションエクスプローラー**で、デバッグする JavaScript ファイルを開き、サーバー側コードの場合と同様に、IDE でブレークポイントを設定します。

4. を押して `F5` 、DevTools サーバーを実行している Microsoft Edge を起動します。 ブレークポイントにヒットすると、Visual Studio にブレークし、そこからコードをさらに調べていくことができます。
