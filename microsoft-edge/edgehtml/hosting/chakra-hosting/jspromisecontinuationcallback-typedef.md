---
description: Promise 継続コールバック。
title: JsPromiseContinuationCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 51a3fd02-9668-4cf7-bb0b-e1fd03b2528f
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: da121d186cd9d0ab1a9770be08c9a92b52cf3366
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235088"
---
# JsPromiseContinuationCallback Typedef

Promise 継続コールバック。  
  
## 構文  
  
```cpp  
typedef void (CALLBACK *JsPromiseContinuationCallback)(  
  _In_ JsValueRef task,  
  _In_opt_ void *callbackState  
);  
```  
  
#### パラメーター  
 `task`  
  `callbackState`  
  
## 注釈  
 ホストは、promise 継続コールバックを指定できます `JsSetPromiseContinuationCallback` 。 スクリプトが後で実行するタスクを作成する場合は、promise 継続コールバックがタスクと一緒に呼び出され、タスクは、現在のスクリプトの実行が完了した時に実行される、FIFO キューに入れる必要があります。  
  
 この API は EdgeHTML モードでのみサポートされています。  
  
## 要件  
 jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
