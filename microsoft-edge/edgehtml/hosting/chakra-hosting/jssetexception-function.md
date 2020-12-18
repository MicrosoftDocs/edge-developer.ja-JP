---
description: 現在のコンテキストのランタイムを例外状態に設定します。
title: JsSetException 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetException
helpviewer_keywords:
- JsSetException function
ms.assetid: c528793a-2e1b-4ee1-bd2e-e63fd547dc40
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2c2e3840d2a831db23a525c5d8854b9b2fcfb8c9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234725"
---
# JsSetException 関数

現在のコンテキストのランタイムを例外状態に設定します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsSetException(  
   _In_ JsValueRef exception  
);  
```  
  
#### パラメーター  
 `exception`  
 現在のコンテキストのランタイムに設定する JavaScript 例外。  
  
## 戻り値  
 `JsNoError` エンジンが例外状態に設定されている場合、それ以外の場合はエラー コード。  
  
## 注釈  
 現在のコンテキストのランタイムが既に例外状態の場合、この API は返します `JsErrorInExceptionState` 。  
  
 アクティブなスクリプト コンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
