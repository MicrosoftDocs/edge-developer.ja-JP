---
description: オブジェクトのインデックス付きプロパティを外部データに設定します。 外部データは、オブジェクトのインデックス付きプロパティのバック ストアとして使用され、型指定された配列のようにアクセスされます。
title: JsSetIndexedPropertiesToExternalData 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: cee2d86d-ed42-4acb-86ef-95a67e63d0d6
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: fa0eba3659c20066913cd42a0a18dd5ffe5f857f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234512"
---
# JsSetIndexedPropertiesToExternalData 関数

オブジェクトのインデックス付きプロパティを外部データに設定します。 外部データは、オブジェクトのインデックス付きプロパティのバック ストアとして使用され、型指定された配列のようにアクセスされます。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsSetIndexedPropertiesToExternalData(  
   _In_ JsValueRef object,  
   _In_ void* data,  
   _In_ JsTypedArrayType arrayType,  
   _In_ unsigned int elementLength  
);  
```  
  
#### パラメーター  
 `object`  
 操作対象のオブジェクトを指定します。  
  
 `data`  
 オブジェクトのインデックス付きプロパティのバック ストアとして使用される外部データ。  
  
 `arrayType`  
 外部データの配列要素型。  
  
 `elementLength`  
 外部データ内の配列要素の数。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 アクティブなスクリプト コンテキストが必要です。  
  
 この API は EdgeHTML モードでのみサポートされています。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
