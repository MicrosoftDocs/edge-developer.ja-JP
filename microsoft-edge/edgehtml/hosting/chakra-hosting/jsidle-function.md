---
description: 必要なアイドル処理を実行するランタイムに指示します。
title: JsIdle 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsIdle
helpviewer_keywords:
- JsIdle function
ms.assetid: 372d1c62-8e19-4886-aa33-364cabc09bba
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: ecba0aafb6b4dcccb4485c2956cae5ce4045355f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235039"
---
# JsIdle 関数

必要なアイドル処理を実行するランタイムに指示します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsIdle(  
   _Out_opt_ unsigned int *nextIdleTick  
);  
```  
  
#### パラメーター  
 `nextIdleTick`  
 アイドル状態の作業が多い場合は、次のシステム ティックが表示されます。 null を指定できます。 今後のアイドル状態の作業がない場合は、ティックの最大数を返します。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 現在のランタイムでアイドル処理が有効になっている場合、呼び出しは、ホストがアイドル状態であり、ランタイムがメモリ クリーンアップ タスクを実行できると現在のランタイム `JsIdle` に通知します。  
  
 `JsIdle` また、ランタイムが実行するアイドル状態の作業が増えるまで、システム ティックの数を返す場合があります。 この `JsIdle` 数のティックが渡される前に呼び出す操作は機能しません。  
  
 アクティブなスクリプト コンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
