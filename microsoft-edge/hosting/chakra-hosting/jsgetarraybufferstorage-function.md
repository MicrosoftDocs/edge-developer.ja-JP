---
description: 配列バッファーによって使用される、基になるメモリ記憶域を取得します。
title: JsGetArrayBufferStorage 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 712ae298-36a9-47ef-b089-e51835c056bc
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1e8d265f3e81015ba9f5d0547b6b1c7246c23ce5
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570464"
---
# JsGetArrayBufferStorage 関数
によって使用される、基になるメモリ記憶域を取得 `ArrayBuffer` します。  
  
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
 ArrayBuffer のバッファー。 返されるバッファーの有効期間は、の有効期間と同じです `ArrayBuffer` 。 バッファーポインターは、 `ArrayBuffer` ガベージコレクションの目的で、への参照としてカウントされません。  
  
 `bufferLength`  
 バッファーのバイト数。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 アクティブなスクリプトコンテキストが必要です。  
  
 この API は、Microsoft Edge モードでのみサポートされます。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)