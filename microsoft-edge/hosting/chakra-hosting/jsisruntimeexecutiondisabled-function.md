---
description: ランタイムでスクリプトの実行が無効になっているかどうかを示す値を返します。
title: JsIsRuntimeExecutionDisabled 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsIsRuntimeExecutionDisabled
helpviewer_keywords:
- JsIsRuntimeExecutionDisabled function
ms.assetid: 77490280-fb84-4614-a1f0-6ac31e3bd607
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 6968a31c9acab70589fe58c86cc566e631778c3c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569290"
---
# JsIsRuntimeExecutionDisabled 関数
ランタイムでスクリプトの実行が無効になっているかどうかを示す値を返します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsIsRuntimeExecutionDisabled(    _In_ JsRuntimeHandle runtime,    _Out_ bool *isDisabled);  
```  
  
#### パラメーター  
 `runtime`  
 実行が無効になっているかどうかを確認するランタイムを指定します。  
  
 `isDisabled`  
 `true` 実行され `false` ていない場合は、  
  
## 戻り値  
 `JsNoError` 操作に成功した場合は、エラーコードが返されます。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)