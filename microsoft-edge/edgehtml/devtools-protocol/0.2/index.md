---
description: Microsoft Edge DevTools プロトコル バージョン 0.2 のリリース ノート
title: Microsoft Edge DevTools プロトコル バージョン 0.2 リリース ノート
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 61d8f5b00dca3505594ca41db6c80c5ba4157092
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234400"
---
# DevTools Protocol Version 0.2 リリース ノート

> [!NOTE]
> Microsoft Edge DevTools プロトコルのバージョン 0.2 は [、Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) 以降の [Windows Insider Preview](https://insider.windows.com/getting-started/) ビルドでのみ動作します。

Microsoft **Edge DevTools プロトコル** のバージョン 0.2 では、新しいスタンドアロンの Microsoft Edge [DevTools Preview](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) アプリで EdgeHTML インストルメンテーションと基本的なリモート デバッグをテストするプレビューが提供されています。 そのため、Windows [10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) 以降の [Windows Insider Preview](https://insider.windows.com/getting-started/) ビルドを実行している必要があります。

DevTools プロトコルの目標は次の 3 つあります。

 - Microsoft Edge にアタッチする DevTools アプリのパブリック API を提供する
 - DevTools 機能の外部ツール クライアントへのアクセスを拡張する
 - Microsoft Edge を実行しているさまざまな Windows 10 デバイスでリモート デバッグを有効にする 

DevTools プロトコルのバージョン 0.2 には、バージョン 0.1 で導入されたコア スクリプトデバッグ機能に加えて、スタイルとレイアウト (読み取り専用) デバッグとコンソール API 用の新しいドメインが含まれています。 Edge DevTools UI では、これは要素パネル、コンソール パネル[****](../../devtools-guide/elements.md)、デバッガー パネルで利用可能な[**機能**](../../devtools-guide/console.md)に[**変換**](../../devtools-guide/debugger.md)されます。
