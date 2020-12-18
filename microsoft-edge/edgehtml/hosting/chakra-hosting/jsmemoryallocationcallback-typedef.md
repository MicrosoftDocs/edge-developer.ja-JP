---
description: メモリ割り当てイベント用のユーザー実装コールバック ルーチン。
title: JsMemoryAllocationCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 511babc7-3caa-4ee5-82a2-943bbd34db8d
caps.latest.revision: 7
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 22b5cc0fe5a2c8b49f71c91d28f95ba29af37849
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234526"
---
# JsMemoryAllocationCallback Typedef

メモリ割り当てイベント用のユーザー実装コールバック ルーチン。  
  
## 構文  
  
```cpp  
typedef bool (CALLBACK * JsMemoryAllocationCallback)(  
   _In_opt_ void *callbackState,  
   _In_ JsMemoryEventType allocationEvent,  
   _In_ size_t allocationSize  
);  
```  
  
#### パラメーター  
 callbackState  
 JsSetRuntimeMemoryAllocationCallback に渡された状態。  
  
 allocationEvent  
 型割り当てイベントの種類。  
  
 allocationSize  
 割り当てのサイズ。  
  
## プロパティ値/戻り値  
 JsMemoryAllocate イベントの場合、true を返す場合、ランタイムは割り当てを続行できます。 false を返す場合は、割り当て要求が拒否されます。 他の割り当てイベントの戻り値は無視されます。  
  
## 注釈  
 JsSetRuntimeMemoryAllocationCallback を使用して、このコールバックを登録します。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
