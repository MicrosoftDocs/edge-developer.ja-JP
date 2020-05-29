---
description: 指定されたランタイムのメモリ割り当てのコールバックを設定します。
title: JsSetRuntimeMemoryAllocationCallback 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryAllocationCallback
helpviewer_keywords:
- JsSetRuntimeMemoryAllocationCallback function
ms.assetid: 6aa7d58d-6456-4df1-815f-1ba36fb4ae14
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 5c648761473023f00e894fbf75c794cfcc9422c5
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570275"
---
# JsSetRuntimeMemoryAllocationCallback 関数
指定されたランタイムのメモリ割り当てのコールバックを設定します。  
  
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
 割り当てのコールバックを登録するランタイム。  
  
 `callbackState`  
 コールバックに戻される、ユーザーによって指定された状態。  
  
 `allocationCallback`  
 メモリ割り当てイベントに対して呼び出すメモリ割り当てのコールバック。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 メモリ割り当てコールバックを登録すると、ランタイムは、メモリを取得したとき、または OS にメモリを解放するたびに、ホストにコールバックします。 ランタイムメモリマネージャーがメモリブロックを割り当てる前に、コールバックルーチンが呼び出されます。 コールバックが false を返すと、割り当ては拒否されます。 また、ランタイムメモリマネージャーは、メモリブロックを解放した後、割り当てエラーが発生した後に、コールバックルーチンも呼び出します。  
  
 コールバックは現在のランタイム実行スレッドで呼び出されるため、コールバックが完了するまで実行はブロックされます。  
  
 コールバックの戻り値は保存されません。以前に拒否された割り当てによって、新しいメモリの割り当てに対して、ランタイムは後で再びコールバックを呼び出すことができなくなります。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)