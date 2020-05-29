---
description: 2018年10月更新プログラムの Microsoft Edge DevTools の新機能を参照してください。
title: Microsoft Edge DevTools の新機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、edgehtml 18
ms.custom: RS5, seodec18
ms.openlocfilehash: 604419f4c77ccaaf2dfd3179273be803cde86fc8
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569641"
---
# 最新の Windows 10 更新プログラム (EdgeHTML 18) の DevTools

Microsoft Edge DevTools の最新の更新プログラムでは、[*サービス作業者*](#service-workers-panel)と[*ストレージ*](#storage-panel)のための新しい専用パネル、デバッガーのソース[ファイル検索](#source-file-search-tools)ツール、スタイル/レイアウトのデバッグとコンソール Api 用の新しい[エッジツールプロトコルドメイン](#edge-devtools-protocol-updates)が含まれています。

ここでは、 [Windows 10 年 2018 10 月の更新プログラム](/windows/uwp/whats-new/windows-10-build-17763)([EdgeHTML 18](https://aka.ms/devguide_edgehtml_18)) で現在利用できる最新の Microsoft Edge の devtools 機能を示します。 さらに、さまざまなアクセシビリティ、信頼性、およびパフォーマンスのバグも修正され、基本的な機能が向上しました。

## DevTools アプリ

スタンドアロンの[Microsoft Edge DevTools Preview アプリ](../devtools-guide.md#microsoft-store-app)が更新されました。 最新のリリースには、[**デバッガー**](./debugger.md)のコア機能へのリモートデバッグアクセス、[**要素**](./elements.md)(読み取り専用操作の場合)、[**コンソール**](./console.md)パネルが含まれています。

## Service Worker パネル

サイトのサービスワーカーを調査、管理、デバッグするための専用の[**サービスワーカー**](./service-workers.md)パネルが登場しました。 これにより、以前の*デバッガー*パネルでのものと同じ機能が提供されます (現在は、あまりに混雑している UI があります)。

![Service Worker パネル](./media/service_worker.png)

## ストレージパネル

また、*デバッガー*の前のローカルストレージ検査 (*Local と Sesion Storage、Indexeddb、cookie、キャッシュ*) も、独自の専用[**ストレージ**](./storage.md)パネルに移されました。

![ストレージパネル](./media/storage_cache.png)

## ソースファイルの検索ツール

これで、[**デバッガー**](./debugger.md)の[ソースファイル検索](./debugger.md#file-search)ウィンドウが表示されるようになりました。 *Find in files* `Ctrl` + `Shift` + `F` ソースで検索しようとしている特定のコードの文字列がある場合は、[ファイル内を検索] コマンド () を使用してアプリを開きます。 ツールバーには、正規表現などのさまざまな検索オプションが用意されています。 

![デバッガーファイルの検索](./media/debugger_file_search.png)

[*ファイルを開く*] () コマンドを使用して、読み込まれたすべてのソースファイルをすばやく開くこともでき `Ctrl` + `P` ます。

![デバッガファイルを開く](./media/debugger_open_file.png)

## Edge DevTools プロトコルの更新

DevTools プロトコルの[バージョン 0.2](../devtools-protocol/0.2/index.md)では、[バージョン 0.1](../devtools-protocol/0.1/index.md)で導入されたコアスクリプトのデバッグ機能に加えて、スタイルとレイアウト (読み取り専用) デバッグとコンソール api 用の新しいドメインが提供されています。 エッジ DevTools UI では、[**要素**](../devtools-guide/elements.md)(読み取り専用操作の場合)、[**本体**](../devtools-guide/console.md)、[**デバッガー**](../devtools-guide/debugger.md)パネルで利用できる機能に変換されます。
