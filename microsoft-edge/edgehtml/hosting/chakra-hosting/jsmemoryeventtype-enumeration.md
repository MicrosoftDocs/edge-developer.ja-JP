---
description: 割り当てコールバック イベントの種類。
title: JsMemoryEventType 列挙 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsMemoryEventType
helpviewer_keywords:
- JsMemoryEventType enumeration
ms.assetid: b4b176b6-b536-472e-8999-95b681a1df55
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a28010f908285098cf652b497b6d6c272bc763fc
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234335"
---
# JsMemoryEventType 列挙

割り当てコールバック イベントの種類。  
  
## 構文  
  
```cpp  
enum JsMemoryEventType;  
```  
  
## Members  
  
### 値  
  
|名前|説明|  
|----------|-----------------|  
|`JsMemoryAllocate`|メモリ割り当ての要求を示します。|  
|`JsMemoryFailure`|失敗した割り当てイベントを示します。|  
|`JsMemoryFree`|メモリ解放イベントを示します。|  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
