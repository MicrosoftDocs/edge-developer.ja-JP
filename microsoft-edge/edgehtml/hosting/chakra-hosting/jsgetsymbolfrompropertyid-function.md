---
description: プロパティ ID に関連付けられているシンボルを取得します。
title: JsGetSymbolFromPropertyId 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 0e822cb4-ba9e-44df-bf3a-fae97c354daa
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 472253aea228ca0374c42d99710a7a7ab528184c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235095"
---
# JsGetSymbolFromPropertyId 関数

プロパティ ID に関連付けられているシンボルを取得します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsGetSymbolFromPropertyId(  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ JsValueRef *symbol  
);  
```  
  
#### パラメーター  
 `propertyId`  
 シンボルを取得するプロパティ ID。  
  
 `symbol`  
 プロパティ ID に関連付けられている記号。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 アクティブなスクリプト コンテキストが必要です。  
  
 この API は、Microsoft Edge モードでのみサポートされています。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
