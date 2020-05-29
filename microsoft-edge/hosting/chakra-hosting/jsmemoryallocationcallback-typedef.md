---
description: メモリ割り当てイベントのコールバックルーチンが実装されています。
title: JsMemoryAllocationCallback Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 511babc7-3caa-4ee5-82a2-943bbd34db8d
caps.latest.revision: 7
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: b11b3d076c01dbfcae190fd665528323d6f8b987
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569289"
---
# JsMemoryAllocationCallback Typedef
メモリ割り当てイベントのコールバックルーチンが実装されています。  
  
## 構文  
  
```cpp  
typedef bool (CALLBACK * JsMemoryAllocationCallback)(  
   _In_opt_ void *callbackState,  
   _In_ JsMemoryEventType allocationEvent,  
   _In_ size_t allocationSize  
);  
```  
  
#### パラメーター  
 /ステータス  
 JsSetRuntimeMemoryAllocationCallback に渡される状態。  
  
 ・イベント  
 型割り当てイベントの型。  
  
 割り当てサイズ  
 割り当てのサイズ。  
  
## プロパティ値/戻り値  
 JsMemoryAllocate イベントの場合、true を返すことで、ランタイムは割り当てを続行できます。 False を返すと、割り当て要求は拒否されます。 他の割り当てイベントでは、戻り値は無視されます。  
  
## 注釈  
 このコールバックを登録するには、JsSetRuntimeMemoryAllocationCallback を使用します。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)