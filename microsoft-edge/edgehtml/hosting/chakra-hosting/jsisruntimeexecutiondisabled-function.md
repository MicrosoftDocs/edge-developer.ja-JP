---
description: ランタイムでスクリプトの実行が無効になっているかどうかを示す値を返します。
title: JsIsRuntimeExecutionDisabled 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsIsRuntimeExecutionDisabled
helpviewer_keywords:
- JsIsRuntimeExecutionDisabled function
ms.assetid: 77490280-fb84-4614-a1f0-6ac31e3bd607
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 0ce59c77525abdb2dd6cac71dde1378264395e79
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234350"
---
# JsIsRuntimeExecutionDisabled 関数

ランタイムでスクリプトの実行が無効になっているかどうかを示す値を返します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsIsRuntimeExecutionDisabled(    _In_ JsRuntimeHandle runtime,    _Out_ bool *isDisabled);  
```  
  
#### パラメーター  
 `runtime`  
 実行が無効になっているか確認するランタイムを指定します。  
  
 `isDisabled`  
 `true` 実行が無効な場合、 `false` それ以外の場合。  
  
## 戻り値  
 `JsNoError` 操作が成功した場合は失敗コード。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
