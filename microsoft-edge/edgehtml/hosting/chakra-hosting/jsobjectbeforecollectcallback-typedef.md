---
description: オブジェクトを収集する前に呼び出されるコールバック。
title: JsObjectBeforeCollectCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: f21a064a-579f-44cb-9d21-76b62e8c18f5
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 4c24385ec5e15919719ffb0ae71c8adf39c1724c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234865"
---
# JsObjectBeforeCollectCallback Typedef

オブジェクトを収集する前に呼び出されるコールバック。  
  
## 構文  
  
```cpp  
typedef void (CALLBACK *JsObjectBeforeCollectCallback)(  
  _In_ JsRef ref,  
  _In_opt_ void *callbackState  
);  
```  
  
#### パラメーター  
 `ref`  
 収集するオブジェクトを指定します。  
  
 `callbackState`  
 に渡された状態 `JsSetObjectBeforeCollectCallback` 。  
  
## 注釈  
 この API は EdgeHTML モードでのみサポートされています。  
  
## 要件  
 jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
