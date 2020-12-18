---
description: プロパティ記述子から新しいオブジェクトの独自のプロパティを定義します。
title: JsDefineProperty 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsDefineProperty
helpviewer_keywords:
- JsDefineProperty function
ms.assetid: b2cf48d6-eb40-457c-aa8b-b16a50dc5d6a
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a35dd6214190fa558c50cbb743b0f2b92b5e00b3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234876"
---
# JsDefineProperty 関数

プロパティ記述子から新しいオブジェクトの独自のプロパティを定義します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsDefineProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _In_ JsValueRef propertyDescriptor,  
   _Out_ bool *result  
);  
```  
  
#### パラメーター  
 `object`  
 プロパティを持つオブジェクト。  
  
 `propertyId`  
 プロパティの ID。  
  
 `propertyDescriptor`  
 プロパティ記述子。  
  
 `result`  
 プロパティが定義されたかどうか。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 アクティブなスクリプト コンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
