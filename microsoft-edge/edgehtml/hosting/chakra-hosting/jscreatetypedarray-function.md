---
description: JavaScript 型指定された配列オブジェクトを作成します。
title: JsCreateTypedArray 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 937a2a91-6f5f-4aaa-a018-d3089702bf36
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 62f62296d81dafe6515f69a990e33ff5c00730e1
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234880"
---
# JsCreateTypedArray 関数

JavaScript 型指定された配列オブジェクトを作成します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateTypedArray(  
   _In_ JsTypedArrayType arrayType,  
   _In_ JsValueRef baseArray,  
   _In_ unsigned int byteOffset,  
   _In_ unsigned int elementLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### パラメーター  
 `arrayType`  
 作成する配列の型を指定します。  
  
 `baseArray`  
 新しい配列の基本配列を指定します。 ベース `JS_INVALID_REFERENCE` 配列がない場合に使用します。  
  
 `byteOffset`  
 結果の型指定された配列を参照する ( ) の開始からのオフセットをバイト `baseArray` `ArrayBuffer` 単位で指定します。 オブジェクトの場合 `baseArray` にのみ適用 `ArrayBuffer` されます。 それ以外の場合は 0 を指定する必要があります。  
  
 `elementLength`  
 配列内の要素の数。 新しい型指定された配列を作成するときにのみ適用できます。(is) を指定しない場合、または `baseArray` `baseArray` `JS_INVALID_REFERENCE` オブジェクト `baseArray` の場合 `ArrayBuffer` に適用されます。 それ以外の場合は 0 を指定する必要があります。  
  
 `result`  
 新しい型指定された配列オブジェクト。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 使用 `baseArray` できる値は、別 `ArrayBuffer` の型指定された配列、または JavaScript です `Array` 。 返される型指定された配列は、その配列が if である場合に使用します。それ以外の場合は、基になるソース配列のコピー `baseArray` `ArrayBuffer` を作成して使用します。  
  
 アクティブなスクリプト コンテキストが必要です。  
  
 この API は、Microsoft Edge モードでのみサポートされています。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
