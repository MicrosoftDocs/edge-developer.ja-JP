---
description: プロジェクション API が元のスレッドとは異なるスレッドで完了すると JsRT によって呼び出されるアプリケーション コールバック。
title: JsProjectionEnqueueCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 19c1cefb-a7be-4196-b780-9fe6adf35ba5
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 47527d5e32076e40a82ab5452c2e0f624e8a2818
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235090"
---
# JsProjectionEnqueueCallback Typedef

プロジェクション API が元のスレッドとは異なるスレッドで完了すると JsRT によって呼び出されるアプリケーション コールバック。  
  
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
 アプリケーション コンテキスト。  
  
 `callbackState`  
 に渡す必要がある JsRT コンテキスト `jsCallback` 。  
  
## 注釈  
 コールバックを受信するには、JsSetProjectionEnqueueCallback を呼び出す必要があります。  
  
 この API は EdgeHTML モードでのみサポートされています。  
  
## 要件  
 jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
