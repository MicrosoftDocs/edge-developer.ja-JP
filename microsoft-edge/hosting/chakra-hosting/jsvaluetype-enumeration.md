---
description: JsValueRef の JavaScript の型。
title: JsValueType 列挙 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsValueType
helpviewer_keywords:
- JsValueType enumeration
ms.assetid: 6645e723-e554-41fc-b622-ab54ee044b3d
caps.latest.revision: 16
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c42231525b55b49f0931a2ace33b373e0d4ae441
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569261"
---
# JsValueType 列挙
JsValueRef の JavaScript の型。  
  
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
|`JsUndefined`|値が値です `undefined` 。|  
|`JsNull`|値が値です `null` 。|  
|`JsNumber`|この値は JavaScript 番号の値です。|  
|`JsString`|この値は JavaScript の文字列値です。|  
|`JsBoolean`|この値は JavaScript のブール値です。|  
|`JsObject`|この値は JavaScript オブジェクトの値です。|  
|`JsFunction`|この値は JavaScript 関数オブジェクトの値です。|  
|`JsError`|この値は JavaScript のエラーオブジェクトの値です。|  
|`JsArray`|この値は、JavaScript 配列オブジェクトの値です。|  
|`JsSymbol`|この値は JavaScript の記号値です。<br /><br /> この列挙値は、Microsoft Edge モードでのみサポートされます。|  
|`JsArrayBuffer`|この値は JavaScript `ArrayBuffer` オブジェクトの値です。<br /><br /> この列挙値は、Microsoft Edge モードでのみサポートされます。|  
|`JsTypedArray`|この値は、JavaScript 型指定された配列オブジェクトの値です。<br /><br /> この列挙値は、Microsoft Edge モードでのみサポートされます。|  
|`JsDataView`|この値は JavaScript `DataView` オブジェクトの値です。<br /><br /> この列挙値は、Microsoft Edge モードでのみサポートされます。|  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)