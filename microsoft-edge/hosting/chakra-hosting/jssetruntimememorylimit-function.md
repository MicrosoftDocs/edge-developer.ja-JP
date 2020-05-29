---
description: ランタイムの現在のメモリの制限を設定します。
title: JsSetRuntimeMemoryLimit 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryLimit
helpviewer_keywords:
- JsSetRuntimeMemoryLimit function
ms.assetid: 74feb31f-19f6-43e3-b117-0694c59ac593
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: ec8d098c528ac813926797280541aa2c9c4fee79
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570274"
---
# JsSetRuntimeMemoryLimit 関数
ランタイムの現在のメモリの制限を設定します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsSetRuntimeMemoryLimit(  
   _In_ JsRuntimeHandle runtime,  
   _In_ size_t memoryLimit  
);  
```  
  
#### パラメーター  
 `runtime`  
 メモリの制限を設定するランタイム。  
  
 `memoryLimit`  
 メモリ制限なしの新しいランタイムメモリ制限 (バイト単位) または-1。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 メモリの制限により、"メモリ不足" というエラーが発生して、制限を超過する操作はすべて失敗します。 ランタイムのメモリ制限を-1 に設定することは、ランタイムにメモリの制限がないことを意味します。 新しいランタイムには、メモリ制限がない既定値が設定されています。 新しいメモリ制限が現在の使用量を超えている場合、その呼び出しは成功し、ランタイムのメモリ使用量が制限を下回るまで、このランタイムの以降の割り当ては失敗します。  
  
 ランタイムのメモリ制限は、他のスレッドでランタイムがアクティブになっているかどうかに関係なく、いつでも設定できます。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)