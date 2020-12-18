---
description: 非同期 Windows ランタイム メソッドの特殊なエラー プロパティ。
title: 非同期 Windows ランタイム メソッドからの特殊なエラー プロパティ
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
ms.assetid: 45155584-06d8-4e7f-93a6-8564a93f643d
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 3557d0097d632f4058e46acbff748f7177d24ab1
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234645"
---
# 非同期 Windows ランタイム メソッドからの特殊なエラー プロパティ  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

JavaScript で非同期の Windows ランタイム メソッドをデバッグするのは困難な場合があります。これは、エラーが呼び出し履歴の深い場所からスローされる可能性があります。  JavaScript オブジェクトには、アプリがデバッグ モードで実行されているときに非同期の Windows ランタイム メソッドからエラーがスローされた場合にのみ表示される追加のプロパティ `Error` があります。  
  
## 特殊なエラー プロパティ  

デバッグ モードで Windows ランタイムの非同期操作が失敗した場合のエラー オブジェクトには、次の特別なプロパティがあります。  

*   `asyncOpSource` \(Object\) エラーを発生した呼び出しが行われた元の場所に関する情報を取得します。  プロパティ `asyncOpSource.originatingCall` \(String\) は、非同期操作を発生したユーザーのコード内の場所を表示します。  
*   asyncOpType \(String\) エラーが発生した非同期操作の種類の名前を取得します。  
    
非同期操作でのエラーの詳細については、以下を参照してください。  
  
*   [Promise を使用してエラーを処理する方法][PreviousVersionsWindowsAppsHh700337]  
*   [Windows ランタイム エラーのトラブルシューティング][PreviousVersionsWindowsAppsHh974350]  

<!-- links -->  

[PreviousVersionsWindowsAppsHh700337]: /previous-versions/windows/apps/hh700337(v=win.10) "Promise でエラーを処理する方法 (HTML) |Microsoft Docs"  
[PreviousVersionsWindowsAppsHh974350]: /previous-versions/windows/apps/hh974350(v=win.10) "Windows ランタイム エラーのトラブルシューティング (HTML) |Microsoft Docs"  
