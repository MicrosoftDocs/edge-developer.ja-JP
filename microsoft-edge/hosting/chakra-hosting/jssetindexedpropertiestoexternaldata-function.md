---
description: オブジェクトのインデックス付きプロパティを外部データに設定します。 外部データは、オブジェクトのインデックス付きプロパティのバックストアとして使用され、型付き配列と同じようにアクセスされます。
title: JsSetIndexedPropertiesToExternalData 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: cee2d86d-ed42-4acb-86ef-95a67e63d0d6
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c1aed6e194b1dc1c35f403626a7b6c02a7752ffb
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570376"
---
# JsSetIndexedPropertiesToExternalData 関数
オブジェクトのインデックス付きプロパティを外部データに設定します。 外部データは、オブジェクトのインデックス付きプロパティのバックストアとして使用され、型付き配列と同じようにアクセスされます。  
  
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
 操作対象のオブジェクト。  
  
 `data`  
 オブジェクトのインデックス付きプロパティのバックストアとして使用する外部データ。  
  
 `arrayType`  
 外部データの配列要素の型。  
  
 `elementLength`  
 外部データの配列要素の数です。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 アクティブなスクリプトコンテキストが必要です。  
  
 この API は、EdgeHTML モードでのみサポートされます。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)