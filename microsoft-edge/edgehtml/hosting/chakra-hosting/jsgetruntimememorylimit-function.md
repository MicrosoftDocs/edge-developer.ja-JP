---
description: ランタイムの現在のメモリ制限を取得します。
title: JsGetRuntimeMemoryLimit 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetRuntimeMemoryLimit
helpviewer_keywords:
- JsGetRuntimeMemoryLimit function
ms.assetid: ed81ca60-99fd-46b0-89ae-f6ac07926904
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: ed04a0fb921d22eea17eaf86ef7a0152fbf2a1d0
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235038"
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
 ランタイムの現在のメモリ制限 (バイト単位)、または制限が設定されていない場合は -1。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 ランタイムが別のスレッドでアクティブかどうかに関係なく、ランタイムのメモリ制限を常に取得できます。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
