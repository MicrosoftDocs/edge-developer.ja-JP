---
description: オブジェクトのすべてのシンボル プロパティのリストを取得します。
title: JsGetOwnPropertySymbols 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 57c431e3-de0b-4ed0-b750-87a86448daff
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d44da140f61a17d4cdc3a959c8fa7d017cbab1cc
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234894"
---
# JsGetOwnPropertySymbols 関数

オブジェクトのすべてのシンボル プロパティのリストを取得します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsGetOwnPropertySymbols(  
   _In_ JsValueRef object,  
   _Out_ JsValueRef *propertySymbols  
);  
```  
  
#### パラメーター  
 `object`  
 プロパティ シンボルを取得するオブジェクトを指定します。  
  
 `propertySymbols`  
 プロパティ 記号の配列。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 アクティブなスクリプト コンテキストが必要です。  
  
 この API は、Microsoft Edge モードでのみサポートされています。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
