---
title: 非同期 Windows ランタイムメソッドからの特殊なエラープロパティ
ms.custom: ''
ms.date: 04/01/2020
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
ms.openlocfilehash: 5cf2604e26c84e769cf44e0879ee137cbfbe8b90
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570781"
---
# 非同期 Windows ランタイムメソッドからの特殊なエラープロパティ  

JavaScript での非同期 Windows ランタイムメソッドのデバッグは困難である可能性があります。これは、コールスタック内の深い場所からエラーがスローされる可能性があるためです。 JavaScript `Error` オブジェクトには、アプリがデバッグモードで実行されているときに、非同期 Windows ランタイムメソッドからエラーがスローされた場合にのみ表示される追加のプロパティがあります。  
  
## 特別なエラープロパティ  

デバッグモードでの Windows ランタイム非同期操作の失敗によるエラーオブジェクトには、次の特殊なプロパティがあります。  

*   `asyncOpSource` \ (オブジェクト \) エラーが発生した元の場所に関する情報を取得します。 プロパティ `asyncOpSource.originatingCall` \ (文字列 \) には、非同期操作を生成したユーザーのコード内の場所が表示されます。  
*   asyncOpType \ (文字列 \) エラーを発生させた非同期操作の型の名前を取得します。  
    
非同期操作のエラーの詳細については、以下を参照してください。  
  
*   [約束のエラーを処理する方法][PreviousVersionsWindowsAppsHh700337]  
*   [Windows ランタイムエラーのトラブルシューティング][PreviousVersionsWindowsAppsHh974350]  

<!-- image links -->  

<!-- links -->  

[PreviousVersionsWindowsAppsHh700337]: /previous-versions/windows/apps/hh700337(v=win.10) "約束のエラーを処理する方法 (HTML)"  
[PreviousVersionsWindowsAppsHh974350]: /previous-versions/windows/apps/hh974350(v=win.10) "Windows ランタイムエラー (HTML) のトラブルシューティング"  
