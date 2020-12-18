---
description: 外部メモリにアクセスする Javascript `ArrayBuffer` オブジェクトを作成します。
title: JsCreateExternalArrayBuffer 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: article
ms.assetid: 4a02aaec-0f67-4bf9-b37c-71cdb1410ca4
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 78c0d3c8b298876358f247c86a488b6f10e52c6d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234917"
---
# JsCreateExternalArrayBuffer 関数

外部メモリにアクセスする Javascript `ArrayBuffer` オブジェクトを作成します。
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateExternalArrayBuffer(  
  _Pre_maybenull_ _Pre_writable_byte_size_(byteLength) void *data,  
  _In_ unsigned int byteLength,  
  _In_opt_ JsFinalizeCallback finalizeCallback,  
  _In_opt_ void *callbackState,  
  _Out_ JsValueRef *result  
);  
  
```  
  
#### パラメーター  
 `data`  
 外部メモリへのポインター。  
  
 `byteLength`  
 外部メモリ内のバイト数。  
  
 `finalizeCallback`  
 オブジェクトが最終処理される場合のコールバック。 null の場合があります。  
  
 `callbackState`  
 finalizeCallback に戻されるユーザー指定の状態。  
  
 `result`  
 新しい `ArrayBuffer` オブジェクトを指定します。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 アクティブなスクリプト コンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
