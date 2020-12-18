---
description: 型指定された配列で使用される基になるメモリ 記憶域を取得します。
title: JsGetTypedArrayStorage 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 52e4ac5f-cc71-456d-95de-a48f7327503d
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 442727228433368de14bac528ea416fcc2a95fa8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234390"
---
# JsGetTypedArrayStorage 関数

型指定された配列で使用される基になるメモリ 記憶域を取得します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsGetTypedArrayStorage(  
   _In_ JsValueRef typedArray,  
   _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,  
   _Out_ unsigned int *bufferLength,  
   _Out_opt_ JsTypedArrayType *arrayType,  
   _Out_opt_ int *elementSize  
);  
```  
  
#### パラメーター  
 `typedArray`  
 型指定された配列インスタンス。  
  
 `buffer`  
 配列のバッファー。 返されるバッファーの有効期間は、配列の有効期間と同じです。 バッファー ポインターは、ガベージ コレクションのために配列への参照としてカウントされません。  
  
 `bufferLength`  
 バッファー内のバイト数。  
  
 `arrayType`  
 配列の種類を指定します。  
  
 `elementSize`  
 配列の要素のサイズ。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 アクティブなスクリプト コンテキストが必要です。  
  
 この API は、Microsoft Edge モードでのみサポートされています。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
