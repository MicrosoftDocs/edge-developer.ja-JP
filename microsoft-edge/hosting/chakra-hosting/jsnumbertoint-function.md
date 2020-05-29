---
description: '`int`数値の値を取得します。'
title: JsNumberToInt 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 8b9256d6-76ac-4c74-a97c-fbb16c13f5f5
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: cf4c8cb42c737cfb9efee5422fe6bb3c1389cbfd
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570423"
---
# JsNumberToInt 関数
`int`数値の値を取得します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsNumberToInt(  
      _In_ JsValueRef value,  
      _Out_ int *intValue  
);  
```  
  
#### パラメーター  
 `value`  
 値に変換する数値 `int` 。  
  
 `intValue`  
 `int`値。  
  
## 戻り値  
  
## 注釈  
 この関数は、数値の値を取得し、値に変換し `int` ます。 `JsErrorInvalidArgument`値の型が数値以外の場合は、エラーが発生します。  
  
 アクティブなスクリプトコンテキストが必要です。  
  
 この API は、EdgeHTML モードでのみサポートされます。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)