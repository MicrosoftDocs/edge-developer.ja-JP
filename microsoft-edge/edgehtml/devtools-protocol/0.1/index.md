---
description: Microsoft Edge DevTools プロトコル バージョン 0.1 のリリース ノート
title: DevTools Protocol Version 0.1 リリース ノート
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 60e92cb3afa9b10b15c8ebdd520c0061fbb3b366
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234795"
---
# DevTools Protocol Version 0.1 リリース ノート

> [!NOTE]
> Microsoft Edge DevTools プロトコルは [、Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 以降の [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) ビルドでのみ動作します。

Microsoft **Edge DevTools プロトコル** のバージョン 0.1 は、新しいスタンドアロンの Microsoft Edge [DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) アプリで EdgeHTML インストルメンテーションと基本的なリモート デバッグをテストする初期プレビューを提供します。 そのため、Windows [10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 以降の Windows [Insider Preview](https://insider.windows.com/en-us/getting-started/) ビルドを実行している必要があります。

DevTools プロトコルの目標は次の 3 つあります。

 - Microsoft Edge にアタッチする DevTools アプリのパブリック API を提供する
 - DevTools 機能の外部ツール クライアントへのアクセスを拡張する
 - Microsoft Edge を実行しているさまざまな Windows 10 デバイスでリモート デバッグを有効にする 

この暫定的なリリースでは、ブレークポイントの設定、コードのステップ実行、スタック トレースの探索など、コア デバッグ機能が提供されます。 Edge DevTools UI では、これはデバッガー パネルで使用可能な[****](../../devtools-guide/debugger.md)機能 (Web ストレージ、サービス ワーカー、キャッシュ API、および IndexedDB の場合) からキャッシュ検査を差し引いた機能に変換されます。 

今後のリリースでは、デバッガーの機能がさらに追加され、その後に他の [DevTools](../index.md) パネルを起動するインストルメンテーションが追加されます。
