---
description: 後で実行するためにタスクをキューに入れる必要があるときに、コンテキストによって呼び出される promise 継続コールバック関数を設定します。
title: JsSetPromiseContinuationCallback 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 6ef0faf4-1500-4bd9-aeca-c208492af8ea
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9438bf05d879b0c2014c0a4d49d374d26eff3fb4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570370"
---
# JsSetPromiseContinuationCallback 関数
後で実行するためにタスクをキューに入れる必要があるときに、コンテキストによって呼び出される promise 継続コールバック関数を設定します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsSetPromiseContinuationCallback(  
   _In_ JsPromiseContinuationCallback promiseContinuationCallback,  
   _In_opt_ void *callbackState  
);  
```  
  
#### パラメーター  
 `promiseContinuationCallback`  
 設定されているコールバック関数。  
  
 `callbackState`  
 コールバックに戻される、ユーザーによって指定された状態。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 アクティブなスクリプトコンテキストが必要です。  
  
 この API は、EdgeHTML モードでのみサポートされます。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)