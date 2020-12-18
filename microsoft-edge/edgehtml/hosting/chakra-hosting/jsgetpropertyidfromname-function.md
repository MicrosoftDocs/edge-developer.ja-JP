---
description: 名前に関連付けられているプロパティ ID を取得します。
title: JsGetPropertyIdFromName 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetPropertyIdFromName
helpviewer_keywords:
- JsGetPropertyIdFromName function
ms.assetid: 1674906f-746a-4c62-99cd-023276683a86
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: adc8de4d55fa0c74ad191b4621ceb3a54026d02d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234878"
---
# JsGetPropertyIdFromName 関数

名前に関連付けられているプロパティ ID を取得します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPropertyIdFromName(  
   _In_z_ const wchar_t *name,  
   _Out_ JsPropertyIdRef *propertyId  
);  
```  
  
#### パラメーター  
 `name`  
 取得または作成するプロパティ ID の名前。 名前は数字だけで構成できます。  
  
 `propertyId`  
 指定された名前のこのランタイムのプロパティ ID。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 プロパティの ID はコンテキストに固有の値であり、コンテキスト間では使用できません。  
  
 アクティブなスクリプト コンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
