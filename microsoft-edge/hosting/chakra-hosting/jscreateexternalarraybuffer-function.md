---
description: '`ArrayBuffer`外部メモリにアクセスする Javascript オブジェクトを作成します。'
title: JsCreateExternalArrayBuffer 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a02aaec-0f67-4bf9-b37c-71cdb1410ca4
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 376eedda18393436d9dce340753586bf32599b21
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569367"
---
# JsCreateExternalArrayBuffer 関数
`ArrayBuffer`外部メモリにアクセスする Javascript オブジェクトを作成します。
  
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
 外部メモリのバイト数。  
  
 `finalizeCallback`  
 オブジェクトが完了するときのためのコールバック。 は null でもかまいません。  
  
 `callbackState`  
 FinalizeCallback に戻される、ユーザーによって指定された状態。  
  
 `result`  
 新しい `ArrayBuffer` オブジェクト。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 アクティブなスクリプトコンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)