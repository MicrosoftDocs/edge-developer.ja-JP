---
description: Promise 継続コールバック。
title: JsPromiseContinuationCallback Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 51a3fd02-9668-4cf7-bb0b-e1fd03b2528f
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 023d88af5ff82056d8f57453e0a53b91b34565a6
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569271"
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
 ホストでは、で promise 継続コールバックを指定でき `JsSetPromiseContinuationCallback` ます。 スクリプトによって後で実行されるタスクが作成された場合、promise 継続コールバックはタスクと共に呼び出され、タスクは FIFO キューに入れて、現在のスクリプトの実行が完了したときに実行されるようにする必要があります。  
  
 この API は、EdgeHTML モードでのみサポートされます。  
  
## 要件  
 jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)