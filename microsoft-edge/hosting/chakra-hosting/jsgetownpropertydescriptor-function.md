---
description: オブジェクト自体のプロパティのプロパティ記述子を取得します。
title: JsGetOwnPropertyDescriptor 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetOwnPropertyDescriptor
helpviewer_keywords:
- JsGetOwnPropertyDescriptor function
ms.assetid: 44c417ce-ab63-44eb-a0ab-19838e3ab34f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 6f500aec8b892cb2ad437bd7159ab14165a8bfb4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570457"
---
# JsGetOwnPropertyDescriptor 関数
オブジェクト自体のプロパティのプロパティ記述子を取得します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsGetOwnPropertyDescriptor(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ JsValueRef *propertyDescriptor  
);  
```  
  
#### パラメーター  
 `object`  
 プロパティが設定されているオブジェクト。  
  
 `propertyId`  
 プロパティの ID です。  
  
 `propertyDescriptor`  
 プロパティ記述子。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 アクティブなスクリプトコンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)