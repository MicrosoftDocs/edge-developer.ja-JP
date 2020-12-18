---
description: 数値の `int` 値を取得します。
title: JsNumberToInt 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 8b9256d6-76ac-4c74-a97c-fbb16c13f5f5
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 928be9a7cc5cd3e26e8b8df99af1e08a6c50209c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234867"
---
# JsNumberToInt 関数

数値の `int` 値を取得します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsNumberToInt(  
      _In_ JsValueRef value,  
      _Out_ int *intValue  
);  
```  
  
#### パラメーター  
 `value`  
 値に変換する数値を指定 `int` します。  
  
 `intValue`  
 値 `int` を指定します。  
  
## 戻り値  
  
## 注釈  
 この関数は数値の値を取得し、値に変換 `int` します。 値の型が `JsErrorInvalidArgument` 数値ではない場合は失敗します。  
  
 アクティブなスクリプト コンテキストが必要です。  
  
 この API は EdgeHTML モードでのみサポートされています。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
