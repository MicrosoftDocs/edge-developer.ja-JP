---
description: 名前を持つ新しい JavaScript 関数を作成します。
title: JsCreateNamedFunction 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 72f40d06-ab82-4fed-a632-68af6b4126c2
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b54add359422a9312a0ded641051fd04585f3d7e
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234666"
---
# JsCreateNamedFunction 関数

名前を持つ新しい JavaScript 関数を作成します。
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateNamedFunction(  
   _In_ JsValueRef name,  
   _In_ JsNativeFunction nativeFunction,  
   _In_opt_ void *callbackState,  
   _Out_ JsValueRef *function  
);  
```  
  
#### パラメーター  
 `name`  
 診断および文字列化の目的で使用されるこの関数の名前。  
  
 `nativeFunction`  
 関数が呼び出されると呼び出すメソッド。  
  
 `callbackState`  
 コールバックに戻されるユーザー指定の状態。  
  
 `function`  
 新しい関数オブジェクト。  
  
## 戻り値  
  
## 注釈  
 アクティブなスクリプト コンテキストが必要です。  
  
 この API は、Microsoft Edge モードでのみサポートされています。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
