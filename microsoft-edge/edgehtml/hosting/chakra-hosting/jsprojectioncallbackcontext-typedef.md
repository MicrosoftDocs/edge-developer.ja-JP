---
description: JsRT からアプリケーション コールバック JsProjectionEnqueueCallback に渡されたコンテキストは、適切なスレッド上のアプリケーションによって、提供されたコールバックで JsRT に戻されます `JsProjectionCallback` 。
title: JsProjectionCallbackContext Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 50c705c5-664f-4a1a-92f6-4882fc718ab1
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7742b0186a49e99f2738b81357b9e55cfe00042b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234851"
---
# JsProjectionCallbackContext Typedef

JsRT からアプリケーション コールバック JsProjectionEnqueueCallback に渡されたコンテキストは、適切なスレッド上のアプリケーションによって、提供されたコールバックで JsRT に戻されます `JsProjectionCallback` 。  
  
## 構文  
  
```cpp  
typedef void *JsProjectionCallbackContext;  
```  
  
## 注釈  
 コールバックを受 `JsSetProjectionEnqueueCallback` け取る呼び出しが必要です。  
  
 この API は EdgeHTML モードでのみサポートされています。  
  
## 要件  
 jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
