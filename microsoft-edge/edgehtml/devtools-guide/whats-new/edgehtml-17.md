---
description: Windows 10 April 2018 Update (EdgeHTML 17) で Microsoft Edge DevTools に追加された機能
title: EdgeHTML 17 の DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, edgehtml 17
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 937525f349a1db650b795db1efb983f1359fcaa5
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234806"
---
# Windows 10 April 2018 更新プログラムの DevTools (EdgeHTML 17)

DevTools の EdgeHTML 17 リリースには、Microsoft Edge 用の従来のブラウザー内 ( ) ツールと、Microsoft Store からスタンドアロン `F12` [の Windows 10](#microsoft-edge-devtools-app-preview) アプリとしてプレビューする 2 つの方法が含まれています。

このツールは、リモート デバッグの基本的なサポート (新しい[DevTools プロトコル](#devtools-protocol)経由[](../index.md#remote-debugging)[](#docking-to-the-right-in-microsoft-edge)[)、PWA](#pwa-debugging)デバッグ機能[、IndexedDB](#indexeddb-inspection)キャッシュ管理、垂直ドッキングなど、多くの主要な機能で更新されました。 また、パフォーマンスと信頼性 [に対](./edgehtml-16.md) する継続的な投資の一環として、最後のリリースで開始された全体的なリファクタリング作業も継続しました。

[Windows 10 April 2018 Update](/windows/uwp/whats-new/windows-10-build-17134) ([EdgeHTML 17)](https://aka.ms/devguide_edgehtml_17)にリリースされた最新の Microsoft Edge DevTools 機能を次に示します。

## Microsoft Edge DevTools アプリのプレビュー

![Microsoft Edge DevTools アプリ](../../devtools-protocol/media/microsoft-edge-devtools.png) 

Microsoft [Edge DevTools は](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj) 、Microsoft Store からスタンドアロンの Windows 10 アプリとしてプレビューできます。 ストア バージョンでは、ローカルとリモートのページ　ターゲットを開くために [*セレクター*] パネルが表示されます。これには、DevTools インスタンス間で簡単に切り替えられるようにタブ レイアウトが用意されています。 また、DevTools アプリ専用の機能は、アプリ \(Office、Cortana、EdgeHTML [Webview、Windows](../../hosting/webview/index.md)にインストールされた PAS のアドインなど) で Web コンテンツをデバッグする [機能](../../progressive-web-apps/windows-features.md)です。

Edge DevTools は、ブラウザー内から (選択パネルなしで) 引き続 `F12` き利用できます。

DevTools をブラウザーから切り離すには、次の UX とアーキテクチャ上の利点があります。

- DevTools は、Microsoft Edge とは別のアプリ コンテナー サンドボックスで実行され、両方の信頼性が向上します。
- アプリは、アクティブな DevTools インスタンスタブを簡単に切り替える機能を提供します (開いている Microsoft Edge タブを切り替える必要は不要です)。
- *EdgeHTML*ブラウザー エンジンをインストルメント化し、クロスブラウザー API を使用して大規模な devtools エコシステムに[開くこともできます](https://github.com/WICG/devtools-protocol/)。
- DevTools の更新プログラムは、Windows (および EdgeHTML) リリース サイクルとは独立して出荷できます。

*DevTools アプリを使った*ローカルデバッグとリモート デバッグの詳細については[、DevTools ガイドを参照してください](../index.md)。

## DevTools プロトコル

開発者ツールでは [**、Microsoft Edge DevTools プロトコルを使用**](../../devtools-protocol/index.md) して、Microsoft Edge ブラウザーを検査およびデバッグできます。 EdgeHTML エンジンインストルメンテーションの異なる [ドメイン](../../devtools-protocol/0.1/domains/index.md) に編成されたメソッドとイベントのセットを提供します。

 ツール クライアントは、これらのメソッドを呼び出し、Microsoft Edge または Windows Device Portal によってホストされる *DevTools Server* と交換される JSON Web ソケット メッセージを介してこれらのイベント [を監視できます](/windows/mixed-reality/using-the-windows-device-portal)。 
 
 Microsoft Edge DevTools は、[](../../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview)このプロトコルを使用して、Microsoft Store から利用できるスタンドアロン[の DevTools](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)クライアントから Microsoft Edge を実行しているホスト コンピューターのリモート デバッグを有効にします。 現在、このプレビュー サポートは、別のデスクトップ デバイスまたは VM 上の別の Edge の JS デバッグに限定されています。 時間の間に、すべての Windows 10 デバイス上の EdgeHTML インスタンスに対する DevTools の完全なセットのサポートが追加されます。  
 
 最新の [**Visual Studio プレビュー**](https://www.visualstudio.com/vs/preview/) ビルド (Visual Studio 15.7 Preview 1 以降) では、DevTools プロトコルを使用して、任意の ASP.NET または .NET Core プロジェクトの Visual Studio IDE 内から Microsoft Edge (JavaScript コード) の起動とデバッグを有効にします。

## IndexedDB 検査

[**デバッガー**](../debugger.md)の新機能このリリースは、オブジェクト ストアの検査と更新、個々のキー値エントリの削除をサポートする[IndexedDB](../storage.md#indexeddb-manager)マネージャーです。 今後のリリースでは、さらに多くの機能が期待されます。

## PWA デバッグ

段階的 Web アプリ (PAS) のデバッグのサポートが既定で有効にされ[****](../service-workers.md)、サービス ワーカー、キャッシュ[**API、**](../storage.md#cache-manager)[**および IndexedDB**](../storage.md#indexeddb-manager)管理のツール タブが提供されます。

さらに、[ネットワーク[](../network.md#toolbar)パネル] ツール バーには、**** すべてのネットワーク要求に対してサービス ワーカーをバイパスする新しいボタンがあります。このボタンを使用すると、登録済みのサービス ワーカーをネットワーク プロキシとしてオン/オフできます。

![[ネットワーク] ツール バー ボタン: すべてのネットワーク要求に対してサービス ワーカーをバイパスする](../media/network_toolbar_bypass_sw.png)

スタンドアロン[DevTools](../index.md#microsoft-store-app)アプリの選択ツールでローカル ターゲット (ブラウザー タブ/PWA/webview) の一覧から PWA を選択すると、インストール済み[Windows 10](../../progressive-web-apps/windows-features.md)アプリとして PWA をデバッグできます。 [****](../../progressive-web-apps/windows-features.md#debug-your-pwa-edgehtml-as-a-windows-app)  

## Microsoft Edge の右側へのドッキング

これで、Microsoft Edge 内からデバッグするページの右側に DevTools をドッキングできます。また、下部にドッキングしてブラウザー ウィンドウから DevTools をドッキング解除することもできます。 ドック `Ctrl+Shift+D` の下、ドック******の右**、およびドッキング解除の**** 位置、または DevTools の右上隅にあるアイコンを切り替える場合に使用します。

![DevTools (ドッキングされていない状態) のドッキング オプション](../media/docking_buttons.png) 
