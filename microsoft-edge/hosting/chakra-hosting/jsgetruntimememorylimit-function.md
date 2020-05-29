---
description: ランタイムの現在のメモリ制限を取得します。
title: JsGetRuntimeMemoryLimit 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetRuntimeMemoryLimit
helpviewer_keywords:
- JsGetRuntimeMemoryLimit function
ms.assetid: ed81ca60-99fd-46b0-89ae-f6ac07926904
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: e6b44bb1dc8ad5fb8c07248a225c10682f96c86a
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569310"
---
# JsGetRuntimeMemoryLimit 関数
ランタイムの現在のメモリ制限を取得します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsGetRuntimeMemoryLimit(  
   _In_ JsRuntimeHandle runtime,  
   _Out_ size_t *memoryLimit  
);  
```  
  
#### パラメーター  
 `runtime`  
 メモリ制限を取得するランタイム。  
  
 `memoryLimit`  
 ランタイムの現在のメモリ制限 (バイト単位)。または、制限が設定されていない場合は-1。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 ランタイムのメモリ制限は、他のスレッドでランタイムがアクティブになっているかどうかに関係なく、いつでも取得できます。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)