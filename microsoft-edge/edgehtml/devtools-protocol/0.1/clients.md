---
description: Microsoft Edge DevTools Protocol Version 0.1 は、次のツール クライアントをサポートしています。
title: DevTools プロトコル バージョン 0.1 クライアント (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cb7355524ec6dab5cf0275538c5b0c030891d4a9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234427"
---
# DevTools プロトコル バージョン 0.1 クライアント (EdgeHTML)  

> [!NOTE]
> Microsoft Edge DevTools プロトコルは [、Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 以降の [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) ビルドでのみ動作します。

**DevTools Protocol 0.1 は、次** のツール クライアントをサポートしています。

[ ![ Microsoft Edge DevTools Preview](../media/microsoft-edge-devtools.png)](#microsoft-edge-devtools-preview) [ ![ Microsoft Visual Studio 15.7 Preview 2](../media/visual-studio-2017.png)](#microsoft-visual-studio-preview)

## Microsoft Edge DevTools プレビュー

Microsoft Store からスタンドアロン [**の Microsoft Edge DevTools Preview**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) Windows 10 アプリを使用して、Microsoft Edge を実行しているホスト デバイス[(EdgeHTML 17](../../dev-guide/index.md) 以降) をリモートでデバッグできます。

DevTools プロトコルのこの暫定的なバージョン 0.1 リリースは、ブレークポイントの設定、コードのステップ実行、スタック トレースの探索など、コア デバッグ機能を提供します。 Edge DevTools UI では、これはデバッガー パネルで使用可能な[****](../../devtools-guide/debugger.md)機能 (Web ストレージ、サービス ワーカー、キャッシュ API、および IndexedDB の場合) からキャッシュ検査を差し引いた機能に変換されます。 現在、Microsoft Edge のリモート デバッグはデスクトップ ホストに限定されています。今後のリリースで予定されている他の Windows 10 デバイスもサポートされます。

Microsoft Edge DevTools Preview アプリを使ってリモート デバッグをセットアップする方法を次に示します。 DevTools プロトコルはプレビュー中であり、ホスト (デバッグ先) コンピューター上に [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 以降の Windows Insider Preview ビルドが必要です。 Edge DevTools Preview アプリ (デバッガー コンピューターで使用) は、Fall Creators Update (バージョン 1709) ビルドと Windows Insider Preview ビルドで実行されます。

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

## Microsoft Visual Studio Preview

最新の [**Visual Studio プレビュー**](https://www.visualstudio.com/vs/preview/) ビルド (Visual Studio 15.7 Preview 1 以降) を使用すると、任意の ASP.NET または .NET Core プロジェクトで IDE から Microsoft Edge を起動してデバッグできます。 DevTools プロトコルは現在プレビュー中であり [、Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) ビルドを実行する必要があります。

Microsoft Edge のデバッグをセットアップする方法を次に示Visual Studio。

1.  最新の Visual Studio [**プレビュー ビルド**](https://www.visualstudio.com/vs/preview/) (Visual Studio 15.7 Preview 1 以降) をインストールして起動します。

2. **Visual C#** .NET ASP.NETを使用して、既存**** のプロジェクトまたは .NET Core プロジェクトを開く、または新しいプロジェクトを作成します。

3. プロジェクト ソリューション エクスプローラー **で**、デバッグする JavaScript ファイルを開き、サーバー側コードと同様に IDE 内にブレークポイントを設定します。

4. `F5`DevTools Server を実行している Microsoft Edge を押して起動します。 ブレークポイントにヒットすると、ブレークポイントに分割Visual Studio、そこからコードをさらに検査してステップ実行できます。
