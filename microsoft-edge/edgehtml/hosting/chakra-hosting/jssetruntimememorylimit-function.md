---
description: ランタイムの現在のメモリ制限を設定します。
title: JsSetRuntimeMemoryLimit 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryLimit
helpviewer_keywords:
- JsSetRuntimeMemoryLimit function
ms.assetid: 74feb31f-19f6-43e3-b117-0694c59ac593
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 1c31d8bbbec4be22fc1af09e546ad4c95f8ec2bd
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234336"
---
# JsSetRuntimeMemoryLimit 関数

ランタイムの現在のメモリ制限を設定します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsSetRuntimeMemoryLimit(  
   _In_ JsRuntimeHandle runtime,  
   _In_ size_t memoryLimit  
);  
```  
  
#### パラメーター  
 `runtime`  
 メモリ制限を設定するランタイム。  
  
 `memoryLimit`  
 新しいランタイム メモリ制限 (バイト単位)、または -1 (メモリ制限なし)。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 メモリ制限により、制限を超える操作は "メモリ切れ" エラーで失敗します。 ランタイムのメモリ制限を -1 に設定すると、ランタイムにはメモリ制限はありません。 新しいランタイムでは、既定でメモリ制限はありません。 新しいメモリ制限が現在の使用量を超えると、呼び出しは成功し、ランタイムのメモリ使用量が制限を下回るまで、このランタイムでの今後の割り当ては失敗します。  
  
 ランタイムのメモリ制限は、ランタイムが別のスレッドでアクティブかどうかに関係なく、常に設定できます。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
