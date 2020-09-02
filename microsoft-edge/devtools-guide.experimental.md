---
description: Microsoft Edge 開発者ツールについて理解する
title: Microsoft Edge 開発者ツール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/20/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: edgehtml
keywords: microsoft edge、web 開発、f12 ツール、devtools
experimental: false
experiment_id: 51fe4b97-3e55-41
ms.openlocfilehash: 3aee2ab67c6e703a0a31b58b5bf985a23fcbb481
ms.sourcegitcommit: b88d2a55a59db8373ff2bac275d3730977bf19c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986221"
---
# Microsoft Edge 開発者ツール  

> [!NOTE]
> Microsoft Edge の DevTools は、web 開発者が web サイトを構築およびテストするのに役立ちます。  作成ツールを誤って開いた場合は、そのまま押して `F12` 閉じます。  

Microsoft Edge の DevTools は、新しいフロントエンドワークフローに最適化された[オープンソース](https://github.com/Microsoft/ChakraCore)を使用した[TypeScript](https://www.typescriptlang.org/)で構築され、microsoft Store で[スタンドアロンの Windows 10 アプリ](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)として利用できるようになりました。

最新機能の詳細については、「 [*Windows 10 の最新の更新プログラム (EdgeHTML 17) での Devtools」*](./devtools-guide/whats-new.md)を参照してください。

## コア ツール

![Microsoft Edge DevTools](./devtools-guide/media/devtools.png)

Microsoft Edge の DevTools には以下のものがあります。

 - HTML と CSS の編集、アクセシビリティプロパティの検査、イベントリスナーの表示、DOM 変異のブレークポイントの設定を行うための [**要素**](./devtools-guide/elements.md) パネル
 - ログメッセージを表示してフィルター処理し、JavaScript オブジェクトと DOM ノードを検査し、選択したウィンドウまたはフレームのコンテキストで JavaScript を実行する[**本体**](./devtools-guide/console.md)
 - コードをステップ実行して、ウォッチとブレークポイントを設定し、コードをリアルタイムで編集し、web ストレージと cookie キャッシュを検査する[**デバッガー**](./devtools-guide/debugger.md)
 - ネットワークとブラウザーのキャッシュから要求と応答を監視および検査するための [**ネットワーク**](./devtools-guide/network.md) パネル 
 - サイトで必要な時間とシステムリソースをプロファイルするための [**パフォーマンス**](./devtools-guide/performance.md) パネル
 - メモリリソースの使用を測定し、コード実行のさまざまな状態でヒープスナップショットを比較するための [**メモリ**](./devtools-guide/memory.md) パネル
 - さまざまなブラウザープロファイル、画面解像度、GPS 位置座標を使ってサイトをテストする [**エミュレーション**](./devtools-guide/emulation.md) パネル

[フィードバックと機能のリクエストを](#getting-in-touch-with-the-microsoft-edge-devtools-team)送信してください。

> [!TIP]
> **[どのブラウザーからでも、Microsoft edge で無料でテスト](https://developer.microsoft.com/microsoft-edge/tools/remote/)** できます。 [browserstack](https://www.browserstack.com/test-on-microsoft-edge-browser#live-cloud) と提携して、microsoft edge で無料のライブおよび自動テストを提供します。

## Microsoft ストア アプリ

**Microsoft Edge DevTools**は、ブラウザー内 () のツールエクスペリエンスに加えて、 [microsoft Store からスタンドアロンの Windows 10 アプリ](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab)として[プレビューできるようになりました](./devtools-guide/whats-new.md) `F12` 。 ストア バージョンでは、ローカルとリモートのページ　ターゲットを開くために [*セレクター*] パネルが表示されます。これには、DevTools インスタンス間で簡単に切り替えられるようにタブ レイアウトが用意されています。

### ローカル デバッグ

ページをローカルでデバッグするには、 *Microsoft Edge DevTools* アプリを起動するだけです。 セレクターの **ローカル** パネルには、開いている [Edge browser] タブ、実行中の [pwas](./progressive-web-apps-edgehtml/index.md) (*WWAHost.exe* プロセス)、 [webview](./webview.md) コントロールなど、アクティブなすべての EdgeHTML コンテンツプロセスが表示されます。 目的のターゲットをクリックして、DevTools の新しいタブインスタンスを添付して開きます。

![DevTools アプリ ローカル パネル](./devtools-guide/media/chooser_local.png)

### リモート デバッグ

*Microsoft Edge devtools*アプリは、新しくリリースされた[**devtools プロトコル**](./devtools-protocol/index.md)を使ってリモートコンピューター上のページをデバッグするための基本的なサポートを提供します。 このリリースでは、 [**デバッガー**](./devtools-guide/debugger.md) パネルのマイナスキャッシュ検査 (Web Storage、Service Worker、cache API、IndexedDB の場合) へのリモートアクセスが可能になります。 リモートデバッグは、*デスクトップ*ホストを実行している*Microsoft Edge*に限定され、将来のリリースで使用される他の EdgeHTML ホストと Windows 10 デバイスをサポートします。

始めるには、[*Microsoft Edge DevTools*](./devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview) の [DevTools プロトコル](./devtools-protocol/index.md) ドキュメントにあるセクションを確認してください。

![DevTools アプリのリモート パネル](./devtools-guide/media/chooser_remote.png)

## 一般的なショートカット

これらのショートカットは、メインの [DevTools] ウィンドウを制御するか、すべてのツールで動作します。

操作 | ショートカット
:------------ | :-------------
DevTools の表示/非表示 (最後に表示したパネルに表示されます) | F12、Ctrl + Shift + I
ドッキングの切り替え (ドッキング/ボトム/右) | Ctrl + Shift + D 
デバッガーで編集不可の HTML ソース コードを表示する | Ctrl + U
他のツールの下部にあるコンソールの表示/非表示  | Ctrl +**`**
要素に切り替える (DOM Explorer) | Ctrl + 1
コンソールに切り替える |  Ctrl + 2
デバッガーに切り替える | Ctrl + 3
ネットワークに切り替える | Ctrl + 4
パフォーマンスに切り替える | Ctrl + 5
メモリに切り替える | Ctrl + 6
エミュレーションに切り替える | Ctrl + 7
ヘルプ ドキュメント | F1
次のツール | Ctrl + F6
前のツール | Ctrl + Shift + F6
前のツール (履歴から) | Ctrl + Shift + [
次のツール (履歴から) | Ctrl + Shift +]
次のサブフレーム    | F6
前のサブフレーム | Shift + F6
[検索] ボックス内の次の一致 | F3
[検索] ボックス内の前の一致 | Shift + F3
[検索] ボックス内の検索 | Ctrl + F
一番下にある [コンソール] にフォーカスを移動する | Alt + Shift + I
ドッキング/ドッキング解除ツール (ドッキングの切り替え) | Ctrl + P  
コンソールに DevTools を起動する | Ctrl + Shift + J
ページを最新の情報に更新してください。 **注:** ブレークポイントでデバッグと一時停止を行っている場合は、まず実行を再開します。 | Ctrl + Shift + F5 または Ctrl + R

## Microsoft Edge DevTools チームと連絡を取り合う  

[!INCLUDE [contact DevTools team note](./devtools-guide-chromium/includes/contact-devtools-team-note.md)]  
