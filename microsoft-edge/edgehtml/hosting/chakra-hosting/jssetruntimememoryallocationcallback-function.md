---
description: 指定されたランタイムのメモリ割り当てコールバックを設定します。
title: JsSetRuntimeMemoryAllocationCallback 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryAllocationCallback
helpviewer_keywords:
- JsSetRuntimeMemoryAllocationCallback function
ms.assetid: 6aa7d58d-6456-4df1-815f-1ba36fb4ae14
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: ee2abf36e14c26ac58b90d48a6115fd6502307c9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234684"
---
# JsSetRuntimeMemoryAllocationCallback 関数

指定されたランタイムのメモリ割り当てコールバックを設定します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsSetRuntimeMemoryAllocationCallback(  
   _In_ JsRuntimeHandle runtime,  
   _In_opt_ void *callbackState,  
   _In_ JsMemoryAllocationCallback allocationCallback  
);  
```  
  
#### パラメーター  
 `runtime`  
 割り当てコールバックを登録するランタイム。  
  
 `callbackState`  
 コールバックに戻されるユーザー指定の状態。  
  
 `allocationCallback`  
 メモリ割り当てイベントに対して呼び出されるメモリ割り当てコールバック。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 メモリ割り当てコールバックを登録すると、ランタイムは、OS からメモリを取得または解放するたびにホストにコールバックします。 コールバック ルーチンは、ランタイム メモリ マネージャーがメモリ ブロックを割り当てる前に呼び出されます。 コールバックが false を返した場合、割り当ては拒否されます。 ランタイム メモリ マネージャーは、メモリブロックを解放した後、および割り当てエラーが発生した後もコールバック ルーチンを呼び出します。  
  
 コールバックは現在のランタイム実行スレッドで呼び出されるため、コールバックが完了するまで実行はブロックされます。  
  
 コールバックの戻り値は保存されません。以前に拒否された割り当てでは、ランタイムが後で新しいメモリ割り当てのためにコールバックを再び呼び出すのを妨げることはありません。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
