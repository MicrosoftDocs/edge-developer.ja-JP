---
description: 型指定された配列のよく使用されるプロパティを取得します。
title: JsGetTypedArrayInfo 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 992bc4e9-3d06-4ad2-8b6b-88a437360f81
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: fdc9a05a2aebdabfd0c8e95c848d3bd5f97e580a
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234893"
---
# JsGetTypedArrayInfo 関数

型指定された配列のよく使用されるプロパティを取得します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsGetTypedArrayInfo(  
  _In_ JsValueRef typedArray,  
  _Out_opt_ JsTypedArrayType *arrayType,  
  _Out_opt_ JsValueRef *arrayBuffer,  
  _Out_opt_ unsigned int *byteOffset,  
  _Out_opt_ unsigned int *byteLength  
);  
  
```  
  
#### パラメーター  
 `typedArray`  
 型指定された配列インスタンス。  
  
 `arrayType`  
 配列の種類を指定します。  
  
 `arrayBuffer`  
 配列 `ArrayBuffer` のバックストア。  
  
 `byteOffset`  
 配列によって参照される arrayBuffer の開始からのオフセット (バイト単位)。  
  
 `byteLength`  
 配列内のバイト数。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 アクティブなスクリプト コンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
