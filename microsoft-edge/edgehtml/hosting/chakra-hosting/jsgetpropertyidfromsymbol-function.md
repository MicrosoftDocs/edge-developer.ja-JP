---
description: シンボルに関連付けられているプロパティ ID を取得します。
title: JsGetPropertyIdFromSymbol 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 190fe4b9-352e-4b10-9d0e-6c6bbd6363e8
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d97f1fb517164d692cdd010f899dc40d2e3596ed
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234912"
---
# JsGetPropertyIdFromSymbol 関数

シンボルに関連付けられているプロパティ ID を取得します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPropertyIdFromSymbol(  
   _In_ JsValueRef symbol,  
   _Out_ JsPropertyIdRef *propertyId  
);  
```  
  
#### パラメーター  
 `symbol`  
 プロパティ ID が取得されるシンボル。  
  
 `propertyId`  
 指定されたシンボルのプロパティ ID。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 プロパティの ID はコンテキストに固有の値であり、コンテキスト間では使用できません。  
  
 アクティブなスクリプト コンテキストが必要です。  
  
 この API は、Microsoft Edge モードでのみサポートされています。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
