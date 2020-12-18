---
description: オブジェクトが外部データにインデックス付きプロパティを持つかどうかを指定します。
title: JsHasIndexedPropertiesExternalData 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: c676db20-3ef1-4f84-8b26-3e06fe0ab2bf
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e6395bacb15904bc3f2e74d22959844e8e0af373
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235026"
---
# JsHasIndexedPropertiesExternalData 関数

オブジェクトが外部データにインデックス付きプロパティを持つかどうかを指定します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsHasIndexedPropertiesExternalData(  
   _In_ JsValueRef object,  
   _Out_ bool* value  
);  
```  
  
#### パラメーター  
 `object`  
 オブジェクト。  
  
 `value`  
 オブジェクトが外部データにインデックス付きプロパティを持つかどうか。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 この API は、Microsoft Edge モードでのみサポートされています。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
