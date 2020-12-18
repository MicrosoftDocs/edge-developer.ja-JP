---
description: Javascript オブジェクトを作成 `DataView` します。
title: JsCreateDataView 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 161e59eb-d429-46f7-9a38-bbf2149ccf44
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 1d6d170d53f3bfaf885713b6f3abca0b066f8c1d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234524"
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
 結果オブジェクト `ArrayBuffer` のストレージとして使用する既存の `DataView` オブジェクト。  
  
 `byteOffset`  
 結果の開始から参照への `arrayBuffer` オフセットをバイト `DataView` 単位で指定します。  
  
 `byteLength`  
 結果 DataView が参照する ArrayBuffer のバイト数。  
  
 `result`  
 新しい DataView オブジェクト。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 アクティブなスクリプト コンテキストが必要です。  
  
 この API は、Microsoft Edge モードでのみサポートされています。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
