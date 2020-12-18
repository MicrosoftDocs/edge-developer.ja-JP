---
description: 外部オブジェクトの外部データを設定します。
title: JsSetExternalData 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetExternalData
helpviewer_keywords:
- JsSetExternalData function
ms.assetid: 94e0ad34-67d7-4f7f-88a3-3b057ef5e4b9
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f2ebdce4448a14f145ce5aafe6ba412f7db26c17
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234842"
---
# JsSetExternalData 関数

外部オブジェクトの外部データを設定します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsSetExternalData(  
   _In_ JsValueRef object,  
   _In_opt_ void *externalData  
);  
```  
  
#### パラメーター  
 `object`  
 外部オブジェクト。  
  
 `externalData`  
 オブジェクトに格納されている外部データ。 オブジェクトに外部データが格納されな場合は null になります。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 アクティブなスクリプト コンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
