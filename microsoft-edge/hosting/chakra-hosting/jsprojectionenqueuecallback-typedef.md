---
description: プロジェクション API が元のスレッドとは別のスレッドで完了したときに、JsRT によって呼び出されるアプリケーションコールバック。
title: JsProjectionEnqueueCallback Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 19c1cefb-a7be-4196-b780-9fe6adf35ba5
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 064a7d1077ae5222e44ab08ebe0592bb97b1f2af
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569277"
---
# JsProjectionEnqueueCallback Typedef
プロジェクション API が元のスレッドとは別のスレッドで完了したときに、JsRT によって呼び出されるアプリケーションコールバック。  
  
## 構文  
  
```cpp  
typedef void (CALLBACK *JsProjectionEnqueueCallback)(  
  _In_ JsProjectionCallback jsCallback,  
  _In_ JsProjectionCallbackContext jsContext,  
  _In_opt_ void *callbackState  
);  
```  
  
#### パラメーター  
 `jsCallback`  
 元のスレッドで呼び出されるコールバック。  
  
 `jsContext`  
 アプリケーションのコンテキスト。  
  
 `callbackState`  
 JsRT コンテキストを渡す必要があり `jsCallback` ます。  
  
## 注釈  
 コールバックを受け取るには、JsSetProjectionEnqueueCallback を呼び出す必要があります。  
  
 この API は、EdgeHTML モードでのみサポートされます。  
  
## 要件  
 jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)