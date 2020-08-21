---
title: 非同期 Windows ランタイム メソッドからの特殊なエラー プロパティ
ms.custom: ''
ms.date: 07/29/2020
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.technology: windows-integration
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45155584-06d8-4e7f-93a6-8564a93f643d
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: a1fccf1cec811501b94e7da4aa20b69d93754f62
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942066"
---
# 非同期 Windows ランタイム方法からの特殊なエラー プロパティ  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

エラーが呼び出し先の場所からどこからでも発生する可能性があるため、JavaScript で非同期 Windows ランタイムメソッドをデバッグするのがわかりにくいことがあります。  JavaScript オブジェクトには、デバッグ モードで実行されているときに非同期 Windows ランタイム メソッドからエラーが発生した場合にのみ表示される追加プロパティ `Error` があります。  
  
## 特殊なエラー プロパティ  

デバッグ モードでの非同期操作で発生するエラー オブジェクトには、次の特殊なプロパティがあります。  

*   `asyncOpSource` \(Object\) は、エラーを発生した元の場所に関する情報を取得します。  プロパティ \(文字列\) は、非同期操作を元にしたユーザーのコード内の位置 `asyncOpSource.originatingCall` を表示します。  
*   asyncOpType \(文字列\) は、エラーを生じた非同期操作の種類の名前を取得します。  
    
非同期操作でのエラーの詳細については、次を参照してください。  
  
*   [エラーを誤りで処理する方法][PreviousVersionsWindowsAppsHh700337]  
*   [Windows ランタイム エラーのトラブルシューティング][PreviousVersionsWindowsAppsHh974350]  

<!-- links -->  

[PreviousVersionsWindowsAppsHh700337]: /previous-versions/windows/apps/hh700337(v=win.10) "エラーを誤って処理する方法 (HTML) |Microsoft ドキュメント"  
[PreviousVersionsWindowsAppsHh974350]: /previous-versions/windows/apps/hh974350(v=win.10) "Windows ランタイム エラー (HTML) のトラブルシューティング |Microsoft ドキュメント"  
