---
description: Javascript オブジェクトを作成 `DataView` します。
title: JsCreateDataView 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 161e59eb-d429-46f7-9a38-bbf2149ccf44
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1bf237458e8561b7070e4f3f0d4a14050f028375
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569373"
---
# JsCreateDataView 関数
Javascript オブジェクトを作成 `DataView` します。  
  
## 構文  
  
```cpp  
JsErrorCode  JsCreateDataView(  
   _In_ JsValueRef arrayBuffer,  
   _In_ unsigned int byteOffset,  
   _In_ unsigned int byteLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### パラメーター  
 `arrayBuffer`  
 `ArrayBuffer`Result オブジェクトの記憶域として使用する既存のオブジェクト `DataView` 。  
  
 `byteOffset`  
 結果を参照するための先頭からのバイト単位のオフセット `arrayBuffer` `DataView` 。  
  
 `byteLength`  
 Result DataView が参照する配列バッファーのバイト数。  
  
 `result`  
 新しい DataView オブジェクト。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 アクティブなスクリプトコンテキストが必要です。  
  
 この API は、Microsoft Edge モードでのみサポートされます。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)