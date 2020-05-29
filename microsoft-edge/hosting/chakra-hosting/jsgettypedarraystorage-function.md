---
description: 型指定された配列によって使用される、基になるメモリ記憶域を取得します。
title: JsGetTypedArrayStorage 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 52e4ac5f-cc71-456d-95de-a48f7327503d
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: f03414d64fa819ac464217c8362d02e866d45296
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570444"
---
# JsGetTypedArrayStorage 関数
型指定された配列によって使用される、基になるメモリ記憶域を取得します。  
  
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
 型付き配列インスタンス。  
  
 `buffer`  
 配列のバッファー。 返されるバッファーの有効期間は、配列の有効期間と同じです。 バッファーポインターは、ガベージコレクションを目的として、配列への参照としてカウントされません。  
  
 `bufferLength`  
 バッファーのバイト数。  
  
 `arrayType`  
 配列の型。  
  
 `elementSize`  
 配列の要素のサイズ。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 アクティブなスクリプトコンテキストが必要です。  
  
 この API は、Microsoft Edge モードでのみサポートされます。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)