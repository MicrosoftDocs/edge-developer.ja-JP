---
description: JavaScript の型指定された array オブジェクトを作成します。
title: JsCreateTypedArray 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 937a2a91-6f5f-4aaa-a018-d3089702bf36
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 57c5d15d76bf8b3ff29d10f7500fe41b3e959f68
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569348"
---
# JsCreateTypedArray 関数
JavaScript の型指定された array オブジェクトを作成します。  
  
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
 作成する配列の型。  
  
 `baseArray`  
 新しい配列のベース配列。 `JS_INVALID_REFERENCE`ベース配列がない場合に使用します。  
  
 `byteOffset`  
 `baseArray` `ArrayBuffer` 参照する結果型配列の先頭からのバイト単位のオフセット。 オブジェクトの場合にのみ適用 `baseArray` さ `ArrayBuffer` れます。 0以外の場合は、0を指定する必要があります。  
  
 `elementLength`  
 配列内の要素の数。 (Is) を使わずに、 `baseArray` `baseArray` またはオブジェクトの場合にのみ適用 `JS_INVALID_REFERENCE` `baseArray` さ `ArrayBuffer` れます。 0以外の場合は、0を指定する必要があります。  
  
 `result`  
 新しい型付き配列オブジェクト。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 は、、 `baseArray` `ArrayBuffer` 別の型付き配列、または JavaScript にすることができ `Array` ます。 返される型指定された配列は、それがの場合は、それ以外の場合は、 `baseArray` `ArrayBuffer` 基になるソース配列のコピーを作成して使用します。  
  
 アクティブなスクリプトコンテキストが必要です。  
  
 この API は、Microsoft Edge モードでのみサポートされます。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)