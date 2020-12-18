---
description: 値から数値を作成 `int` します。
title: JsIntToNumber 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 1393c4ac-7189-4e9c-8e54-b0e041c22112
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 24e861d1535ae79843fb35de8a047031a479fe16
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234909"
---
# JsIntToNumber 関数

値から数値を作成 `int` します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsIntToNumber(  
   _In_ int intValue,  
   _Out_ JsValueRef *value  
);  
```  
  
#### パラメーター  
 `intValue`  
 数値 `int` に変換する値を指定します。  
  
 `value`  
 新しい数値を指定します。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 アクティブなスクリプト コンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
