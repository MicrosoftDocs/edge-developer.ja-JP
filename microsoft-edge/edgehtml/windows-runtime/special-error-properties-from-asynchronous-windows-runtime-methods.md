---
description: 非同期 Windows ランタイム メソッドからの特殊なエラー プロパティ
title: 非同期 Windows ランタイム メソッドからの特殊なエラー プロパティ
ms.custom: ''
ms.date: 11/03/2020
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
ms.assetid: 45155584-06d8-4e7f-93a6-8564a93f643d
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d9f2fdb007f00c2ab1d1a2050378af80f0075db6
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398841"
---
# <a name="special-error-properties-from-asynchronous-windows-runtime-methods"></a>非同期 Windows ランタイム メソッドからの特殊なエラー プロパティ  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

JavaScript の非同期 Windows ランタイム メソッドは、呼び出し履歴のどこかからエラーがスローされる可能性があります。  JavaScript オブジェクトには、アプリがデバッグ モードで実行されているときに非同期の Windows ランタイム メソッドからエラーがスローされた場合にのみ表示される追加の `Error` プロパティがあります。  
  
## <a name="special-error-properties"></a>特別なエラー プロパティ  

デバッグ モードで Windows ランタイムの非同期操作が失敗した場合のエラー オブジェクトには、次の特別なプロパティがあります。  

*   `asyncOpSource` \(Object\) エラーが発生した呼び出しが行われた元の場所に関する情報を取得します。  プロパティ `asyncOpSource.originatingCall` \(String\) は、非同期操作を発生したユーザーのコード内の場所を表示します。  
*   asyncOpType \(String\) エラーが発生した非同期操作の種類の名前を取得します。  
    
非同期操作のエラーの詳細については、以下を参照してください。  

*   [Promise でエラーを処理する方法][PreviousVersionsWindowsAppsHh700337]  
*   [Windows ランタイム エラーのトラブルシューティング][PreviousVersionsWindowsAppsHh974350]  
    
<!-- links -->  

[PreviousVersionsWindowsAppsHh700337]: /previous-versions/windows/apps/hh700337(v=win.10) "promises (HTML) を使用してエラーを処理する|Microsoft Docs"  
[PreviousVersionsWindowsAppsHh974350]: /previous-versions/windows/apps/hh974350(v=win.10) "Windows ランタイム エラー (HTML) のトラブルシューティング|Microsoft Docs"  
