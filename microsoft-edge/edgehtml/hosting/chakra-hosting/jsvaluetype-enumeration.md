---
description: JsValueRef の JavaScript 型。
title: JsValueType 列挙 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsValueType
helpviewer_keywords:
- JsValueType enumeration
ms.assetid: 6645e723-e554-41fc-b622-ab54ee044b3d
caps.latest.revision: 16
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 840afcde86d4df80490d463921a74c73e42ddfc2
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234676"
---
# JsValueType 列挙

JsValueRef の JavaScript 型。  
  
## 構文  
  
```cpp  
enum JsValueType {  
    JsUndefined      = 0,  
    JsNull           = 1,  
    JsNumber         = 2,  
    JsString         = 3,  
    JsBoolean        = 4,  
    JsObject         = 5,  
    JsFunction       = 6,  
    JsError          = 7,  
    JsArray          = 8,  
    JsSymbol         = 9,  
    JsArrayBuffer    = 10,  
    JsTypedArray     = 11,  
    JsDataView       = 12,  
};  
```  
  
## Members  
  
### 値  
  
|名前|説明|  
|----------|-----------------|  
|`JsUndefined`|値は値 `undefined` です。|  
|`JsNull`|値は値 `null` です。|  
|`JsNumber`|値は JavaScript 番号の値です。|  
|`JsString`|値は JavaScript 文字列値です。|  
|`JsBoolean`|値は JavaScript ブール値です。|  
|`JsObject`|値は JavaScript オブジェクト値です。|  
|`JsFunction`|値は JavaScript 関数オブジェクト値です。|  
|`JsError`|値は JavaScript エラー オブジェクト値です。|  
|`JsArray`|値は JavaScript 配列オブジェクト値です。|  
|`JsSymbol`|値は JavaScript シンボル値です。<br /><br /> この列挙値は、Microsoft Edge モードでのみサポートされます。|  
|`JsArrayBuffer`|値は JavaScript オブジェクト `ArrayBuffer` の値です。<br /><br /> この列挙値は、Microsoft Edge モードでのみサポートされます。|  
|`JsTypedArray`|値は、JavaScript 型指定された配列オブジェクト値です。<br /><br /> この列挙値は、Microsoft Edge モードでのみサポートされます。|  
|`JsDataView`|値は JavaScript オブジェクト `DataView` 値です。<br /><br /> この列挙値は、Microsoft Edge モードでのみサポートされます。|  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
