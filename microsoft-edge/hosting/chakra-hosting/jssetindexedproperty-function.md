---
description: 指定したオブジェクトのインデックスの値を設定します。
title: JsSetIndexedProperty 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetIndexedProperty
helpviewer_keywords:
- JsSetIndexedProperty function
ms.assetid: ccbc5bf4-d99b-485c-ab25-d2bd1ed2142e
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 893849c42d9cbf0de160846d3397fcd5d7c77b7b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570375"
---
# JsSetIndexedProperty 関数
指定したオブジェクトのインデックスの値を設定します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsSetIndexedProperty(  
   _In_ JsValueRef object,  
   _In_ JsValueRef index,  
   _In_ JsValueRef value  
);  
```  
  
#### パラメーター  
 `object`  
 操作対象のオブジェクト。  
  
 `index`  
 設定するインデックス。  
  
 `value`  
 設定する値。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 アクティブなスクリプトコンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)