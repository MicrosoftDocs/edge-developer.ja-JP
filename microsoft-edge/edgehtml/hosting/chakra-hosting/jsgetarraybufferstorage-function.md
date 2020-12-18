---
description: ArrayBuffer で使用される基になるメモリ 記憶域を取得します。
title: JsGetArrayBufferStorage 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 712ae298-36a9-47ef-b089-e51835c056bc
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 64b031a81506e68322759eff49da7467cac6f219
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234653"
---
# JsGetArrayBufferStorage 関数

で使用される基になるメモリ 記憶域を取得します `ArrayBuffer` 。  
  
## 構文  
  
```cpp  
JsErrorCode STDAPI_ JsGetArrayBufferStorage(  
   _In_ JsValueRef arrayBuffer,  
   _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,  
   _Out_ unsigned int *bufferLength  
);  
```  
  
#### パラメーター  
 `arrayBuffer`  
 ArrayBuffer インスタンス。  
  
 `buffer`  
 ArrayBuffer のバッファー。 返されるバッファーの有効期間は、 `ArrayBuffer` バッファー ポインターは、ガベージ コレクションのために参照 `ArrayBuffer` としてカウントされません。  
  
 `bufferLength`  
 バッファー内のバイト数。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 アクティブなスクリプト コンテキストが必要です。  
  
 この API は、Microsoft Edge モードでのみサポートされています。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
