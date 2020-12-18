---
description: 現在のコンテキストのランタイムを例外状態にした例外を返し、そのランタイムの例外状態をリセットします。
title: JsGetAndClearException 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetAndClearException
helpviewer_keywords:
- JsGetAndClearException function
ms.assetid: 6aec8a88-41ee-47f6-b5f4-32f3cae6bb7b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cb296ea351d0466a856d5ac020550ebacc254ac9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234652"
---
# JsGetAndClearException 関数

現在のコンテキストのランタイムを例外状態にした例外を返し、そのランタイムの例外状態をリセットします。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsGetAndClearException(  
   _Out_ JsValueRef *exception  
);  
```  
  
#### パラメーター  
 `exception`  
 現在のコンテキストのランタイムの例外。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 現在のコンテキストのランタイムが例外状態ではない場合、この API は返します `JsErrorInvalidArgument` 。 ランタイムが無効になっている場合、スクリプトが終了したことを示す例外が返されますが、例外はクリアされません (ランタイムが使用して再び有効になっている場合、例外はクリアされます `JsEnableRuntimeExecution` )。  
  
 アクティブなスクリプト コンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
