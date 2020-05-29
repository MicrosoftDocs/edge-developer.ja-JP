---
description: オブジェクトを収集する前に呼び出されるコールバック。
title: JsObjectBeforeCollectCallback Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: f21a064a-579f-44cb-9d21-76b62e8c18f5
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 27bbd1aed72cc751397ac4e6734f107612653b66
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569281"
---
# JsObjectBeforeCollectCallback Typedef
オブジェクトを収集する前に呼び出されるコールバック。  
  
## 構文  
  
```cpp  
typedef void (CALLBACK *JsObjectBeforeCollectCallback)(  
  _In_ JsRef ref,  
  _In_opt_ void *callbackState  
);  
```  
  
#### パラメーター  
 `ref`  
 収集されるオブジェクト。  
  
 `callbackState`  
 渡された状態 `JsSetObjectBeforeCollectCallback` 。  
  
## 注釈  
 この API は、EdgeHTML モードでのみサポートされます。  
  
## 要件  
 jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)