---
description: 正しいスレッドで渡されたコンテキストで呼び出す必要がある JsRT `JsProjectionEnqueueCallback` コールバック。
title: JsProjectionCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 32f22d37-e57e-4196-b6cd-a3fc75bd0632
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 211325b536dc84340974b02973f1de9d5749a60a
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234855"
---
# JsProjectionCallback Typedef

正しいスレッドで渡されたコンテキストで呼び出す必要がある JsRT `JsProjectionEnqueueCallback` コールバック。  
  
## 構文  
  
```cpp  
typedef void (CALLBACK *JsProjectionCallback)(  
  _In_ JsProjectionCallbackContext jsContext  
);  
```  
  
#### パラメーター  
 `jsContext`  
 コールバックを受 `JsSetProjectionEnqueueCallback` け取る呼び出しが必要です。  
  
## 注釈  
 この API は EdgeHTML モードでのみサポートされています。  
  
## 要件  
 jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
