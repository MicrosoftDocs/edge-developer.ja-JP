---
description: Windows 10 October 2018 Update の Microsoft Edge DevTools の新機能を確認する
title: Microsoft Edge DevTools の新機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, edgehtml 18
ms.custom: RS5, seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2f1d3c6fe5bf061186d5c6593a115a8b6794c0dd
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234811"
---
# 最新の Windows 10 更新プログラムの DevTools (EdgeHTML 18)

Microsoft Edge DevTools の最新の更新プログラムでは、UI とセキュリティの両方に多くの利便性が追加されています。たとえば、サービス[**](#storage-panel)ワーカーとストレージ[](#source-file-search-tools)用の新しい専用パネル、デバッガーのソース ファイル検索ツール、スタイル/レイアウトのデバッグとコンソール API 用の新しい[Edge DevTools プロトコル](#edge-devtools-protocol-updates)ドメインが含まれます。 [**](#service-workers-panel)

[Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) ([EdgeHTML 18)](https://aka.ms/devguide_edgehtml_18)で利用可能な最新の Microsoft Edge DevTools 機能を次に示します。 このすべてに加えて、多数のアクセシビリティ、信頼性、パフォーマンスのバグも修正して、基礎を改善しました。

## DevTools アプリ

スタンドアロンの Microsoft Edge [DevTools Preview アプリが更新されました](./index.md#microsoft-store-app)。 最新のリリースには、デバッガー、要素[**(読**](./elements.md)み取り専用操作[****](./debugger.md)用)、コンソール パネルのコア機能へのリモート デバッグ アクセスが[**含**](./console.md)まれています。

## [サービス ワーカー] パネル

サイトのサービス [**ワーカーを検査**](./service-workers.md) 、管理、およびデバッグするための専用のサービス ワーカー パネルが追加されました。 これにより、デバッガー パネルで以前と同じ機能が *提供されます* (現在は UI が少なめでした)。

![[サービス ワーカー] パネル](./media/service_worker.png)

## 記憶域パネル

また、デバッガーで以前にローカルストレージインスペクター (*ローカルおよび Sesion ストレージ、IndexedDB、Cookie、キャッシュ*) を** 独自の専用ストレージ[****](./storage.md)パネルに移動しました。

![記憶域パネル](./media/storage_cache.png)

## ソース ファイル検索ツール

デバッガー [**に**](./debugger.md) ソース ファイル [検索ウィンドウが表示](./debugger.md#file-search) されます。 ソースで検索*しようとしている*特定のコード文字列がある場合は、[ファイル内の検索] コマンド ( ) で開 `Ctrl` + `Shift` + `F` きます。 ツール バーには、正規表現など、さまざまな検索オプションがあります。 

![デバッガー ファイルの検索](./media/debugger_file_search.png)

読み込まれたソース ファイルは、[ファイルを開く( ) ] コマンド*ですばやく* `Ctrl` + `P` 開く方法があります。

![デバッガーの開いているファイル](./media/debugger_open_file.png)

## Edge DevTools プロトコルの更新プログラム

DevTools プロトコルのバージョン[0.2](../devtools-protocol/0.2/index.md)には、バージョン[0.1](../devtools-protocol/0.1/index.md)で導入されたコア スクリプトデバッグ機能に加えて、スタイルとレイアウト (読み取り専用) デバッグとコンソール API 用の新しいドメインが提供されています。 Edge DevTools UI では、これは要素[**(読**](../devtools-guide/elements.md)み取り専用操作用)、コンソール パネル、デバッガー パネルで利用可能な[**機能に**](../devtools-guide/console.md)[**変換**](../devtools-guide/debugger.md)されます。
