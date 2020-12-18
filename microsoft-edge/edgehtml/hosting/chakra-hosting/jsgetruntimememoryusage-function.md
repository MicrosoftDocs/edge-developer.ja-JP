---
description: ランタイムの現在のメモリ使用量を取得します。
title: JsGetRuntimeMemoryUsage 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetRuntimeMemoryUsage
helpviewer_keywords:
- JsGetRuntimeMemoryUsage function
ms.assetid: b9bd4146-bfbc-4cb1-a0e9-a0ded7fb09bd
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a9c8d59e8cf73ad178f539f2f9f0ed191ceb47fd
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235099"
---
# JsGetRuntimeMemoryUsage 関数

ランタイムの現在のメモリ使用量を取得します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsGetRuntimeMemoryUsage(  
   _In_ JsRuntimeHandle runtime,  
   _Out_ size_t *memoryUsage  
);  
```  
  
#### パラメーター  
 `runtime`  
 メモリ使用量を取得するランタイム。  
  
 `memoryUsage`  
 ランタイムの現在のメモリ使用量 (バイト単位)。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 ランタイムが別のスレッドでアクティブかどうかに関係なく、メモリ使用量は常に取得できます。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
