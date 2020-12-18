---
description: 新しい JavaScript 関数を作成します。
title: JsCreateFunction 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateFunction
helpviewer_keywords:
- JsCreateFunction function
ms.assetid: b298a96a-5ef7-4203-a8c8-55f9bfc6d2bb
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f7e67e86e6d8055664bfb1b58e6d5653f6d75d1b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234885"
---
# JsCreateFunction 関数

新しい JavaScript 関数を作成します。
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateFunction(  
   _In_ JsNativeFunction nativeFunction,  
   _In_opt_ void *callbackState,  
   _Out_ JsValueRef *function  
);  
```  
  
#### パラメーター  
 `nativeFunction`  
 関数が呼び出されると呼び出すメソッド。  
  
 `callbackState`  
 コールバックに戻されるユーザー指定の状態。  
  
 `function`  
 新しい関数オブジェクト。  
  
## 戻り値  
 呼び出しの結果 (指定されている場合)。  
  
## 注釈  
 アクティブなスクリプト コンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
