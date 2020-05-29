---
description: 割り当てのコールバックイベントの種類。
title: JsMemoryEventType 列挙 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsMemoryEventType
helpviewer_keywords:
- JsMemoryEventType enumeration
ms.assetid: b4b176b6-b536-472e-8999-95b681a1df55
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1e9833777ed8fe5a19fd2a1487715296279f7351
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569286"
---
# JsMemoryEventType 列挙
割り当てのコールバックイベントの種類。  
  
## 構文  
  
```cpp  
enum JsMemoryEventType;  
```  
  
## Members  
  
### 値  
  
|名前|説明|  
|----------|-----------------|  
|`JsMemoryAllocate`|メモリの割り当て要求を示します。|  
|`JsMemoryFailure`|失敗した割り当てイベントを示します。|  
|`JsMemoryFree`|メモリ解放イベントを示します。|  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)