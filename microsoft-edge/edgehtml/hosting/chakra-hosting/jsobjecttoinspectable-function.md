---
description: JavaScript オブジェクトのポインターの折り返しを `IInspectable` 解除します。
title: JsObjectToInspectable 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 1d15b0b8-516f-4fc6-95aa-2ddd65f8ab75
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 0d818f798805e2afad4dc87b308258464d31bf92
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234857"
---
# JsObjectToInspectable 関数

JavaScript オブジェクトのポインターの折り返しを `IInspectable` 解除します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsObjectToInspectable(  
   _In_ JsValueRef value,  
   _Out_ IInspectable  **inspectable  
);  
```  
  
#### パラメーター  
 `value`  
 投影する必要がある JavaScript 値 `IInspectable` 。  
  
 `inspectable`  
 オブジェクト `IInspectable` の値。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 ホストは COM スレッド ルールを適用する必要があります。  
  
 アクティブなスクリプト コンテキストが必要です。  
  
 この API は EdgeHTML モードでのみサポートされています。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
