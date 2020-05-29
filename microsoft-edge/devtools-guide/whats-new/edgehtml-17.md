---
description: Windows 10 年 4 2018 月の更新プログラム (EdgeHTML 17) で Microsoft Edge DevTools に追加された機能
title: EdgeHTML 17 の DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、edgehtml 17
ms.custom: seodec18
ms.openlocfilehash: cc110071422f858acf840c1eaf100696a6e3cf03
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569635"
---
# Windows 10 4 月の2018更新プログラム (EdgeHTML 17) の DevTools

DevTools の EdgeHTML 17 リリースは、Microsoft Edge 用の従来のブラウザー () ツールとして、 `F12` Microsoft Store からスタンドアロンの[Windows 10 アプリ](#microsoft-edge-devtools-app-preview)としてプレビューする、2つの方法で提供されています。

このツールは、[リモートデバッグ](../../devtools-guide.md#remote-debugging)の基本的なサポート (新しい[devtools プロトコル](#devtools-protocol)を使用)、 [PWA のデバッグ機能](#pwa-debugging)、 [indexeddb キャッシュ管理](#indexeddb-inspection)、[縦型のドッキング](#docking-to-the-right-in-microsoft-edge)など、さまざまな主要機能によって更新されています。 また、パフォーマンスと信頼性への継続的な投資の一環として、最後のリリースで行われた全体的な[リファクタリングの取り組み](./edgehtml-16.md)を継続しました。

[2018 年4月の更新プログラム](/windows/uwp/whats-new/windows-10-build-17134)([EdgeHTML 17](https://aka.ms/devguide_edgehtml_17)) で出荷された最新の Microsoft Edge の製品ツールの機能を次に示します。

## Microsoft Edge DevTools アプリのプレビュー

![Microsoft Edge DevTools アプリ](../../devtools-protocol/media/microsoft-edge-devtools.png) 

Microsoft [**Edge DevTools**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab)は、microsoft Store からスタンドアロンの Windows 10 アプリとしてプレビューできるようになりました。 ストアバージョンでは、ローカルとリモートのページターゲットを開くための*セレクター*パネルが用意されています。これには、devtools インスタンス間で簡単に切り替えるためのタブ付きレイアウトが用意されています。 また、DevTools アプリに限定されているのは、アプリ (Office、Cortana、EdgeHTML [webview](../../webview.md)、 [Windows にインストールされている pwas](../../progressive-web-apps-edgehtml/windows-features.md)アドインなど) の web コンテンツをデバッグする機能です。

また、Edge の DevTools は `F12` ブラウザー内から (セレクターパネルなしで) 利用できます。

ブラウザーから DevTools を分離すると、これらの UX と構造的な利点が得られます。

- DevTools は、Microsoft Edge から独立したアプリコンテナーサンドボックスで実行され、両方に対してより高い信頼性を実現します。
- アプリでは、アクティブな DevTools インスタンスタブ間を簡単に切り替えることができます (開いている Microsoft Edge タブを切り替える必要はありません)。
- *EdgeHTML*ブラウザーエンジンをインストルメント化し、[クロスブラウザー api](https://github.com/WICG/devtools-protocol/)を使用して、より大きな devtools エコシステムにそれを開くことができるようになりました。
- DevTools の更新プログラムは、Windows (および EdgeHTML) リリースサイクルから独立して提供することができます。

開発の詳細については、 [「devtools アプリを使ったローカルおよびリモートデバッグ](../../devtools-guide.md) *」* をご覧ください。

## DevTools プロトコル

開発者ツールでは、 [**Microsoft Edge DevTools プロトコル**](../../devtools-protocol/index.md)を使用して、microsoft edge ブラウザーを検査およびデバッグできます。 EdgeHTML engine インストルメンテーションのさまざまな[ドメイン](../../devtools-protocol/0.1/domains/index.md)で構成されている一連のメソッドとイベントを提供します。

 ツールクライアントは、これらのメソッドを呼び出し、Microsoft Edge または[Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal)でホストされている*devtools サーバー*との間でやり取りされる JSON web ソケットメッセージを通じてこれらのイベントを監視します。 
 
 Microsoft Edge DevTools では、microsoft Store から入手できる[スタンドアロンの devtools クライアント](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)から microsoft edge を実行しているホストコンピューターの[リモートデバッグ](../../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview)を有効にするために、このプロトコルが使用されています。 現在、このプレビューのサポートは、別のデスクトップデバイスまたは VM での別のエッジの JS デバッグに限定されています。 時間の経過と共に、Windows 10 デバイスの任意の EdgeHTML インスタンスに対するすべての DevTools のサポートを追加します。  
 
 最新の[**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/)ビルド (visual Studio 15.7 preview 1 以降) では、ASP.NET または .net コアプロジェクトの VISUAL studio IDE から Microsoft Edge (JavaScript コード) の起動とデバッグを行うことができます。

## IndexedDB 検査

[**デバッガー**](../debugger.md)の新機能このリリースは、オブジェクトストアの調査と更新をサポートする[Indexeddb Manager](../storage.md#indexeddb-manager)であり、個々のキー値エントリを削除します。 今後のリリースでは、さらに機能が期待できます。

## PWA のデバッグ

プログレッシブ Web アプリ (PWAs) のデバッグのサポートが既定で有効になりました。[**サービスワーカー**](../service-workers.md)、[**キャッシュ API**](../storage.md#cache-manager)、 [**indexeddb**](../storage.md#indexeddb-manager) management のツールタブが提供されます。

さらに、[[ネットワークパネル] ツールバー](../network.md#toolbar)には、[**すべてのネットワーク要求] の [サービスワーカー**を表示しない] があり、登録されているサービスワーカーをネットワークプロキシとしてオンまたはオフに切り替えることができます。

![ネットワークツールバーボタン: すべてのネットワーク要求についてサービスワーカーをバイパスする](../media/network_toolbar_bypass_sw.png)

[スタンドアロンの DevTools アプリ](../../devtools-guide.md#microsoft-store-app)のセレクターで、[**ローカル**](../../progressive-web-apps-edgehtml/windows-features.md#debug-your-pwa-edgehtml-as-a-windows-app)ターゲット (browser tab/PWA/webview) の一覧から PWA を選択することによって、[インストールされている Windows 10 アプリとして](../../progressive-web-apps-edgehtml/windows-features.md)デバッグできます。  

## Microsoft Edge での右へのドッキング

Microsoft Edge 内からデバッグしているページの右側に DevTools をドッキングできるようになりました。また、ブラウザーウィンドウから DevTools のドッキングを解除することもできます。 [ `Ctrl+Shift+D` Dock] の**下**、[**右揃え**]、[ドッキング**解除**] の間の切り替え、および devtools の右上隅のアイコンの切り替えに使用します。

![DevTools (非ドッキング状態) のドッキングオプション](../media/docking_buttons.png) 
