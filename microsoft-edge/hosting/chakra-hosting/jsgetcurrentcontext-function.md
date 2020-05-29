---
description: スレッド上の現在のスクリプトコンテキストを取得します。
title: JsGetCurrentContext 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetCurrentContext
helpviewer_keywords:
- JsGetCurrentContext function
ms.assetid: dd5fe0fa-d1e5-4af6-809e-e655a27519b5
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 78f04674aab8783c43f22516903669e0f9b7543b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569329"
---
# JsGetCurrentContext 関数
スレッド上の現在のスクリプトコンテキストを取得します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsGetCurrentContext(  
   _Out_ JsContextRef *currentContext  
);  
```  
  
#### パラメーター  
 `currentContext`  
 スレッドの現在のスクリプトコンテキスト。現在のスクリプトコンテキストが存在しない場合は null。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)