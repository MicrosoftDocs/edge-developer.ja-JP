---
description: 現在のコンテキストのランタイムが例外状態であるかどうかを判断します。
title: JsHasException 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsHasException
helpviewer_keywords:
- JsHasException function
ms.assetid: ac7da3ce-c746-4154-bbb8-bcb0859a8d5b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 25ddb8f9cc407dd414a6cd2210c315eb4dd7b141
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570431"
---
# JsHasException 関数
現在のコンテキストのランタイムが例外状態であるかどうかを判断します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsHasException(  
   _Out_ bool *hasException  
);  
```  
  
#### パラメーター  
 `hasException`  
 現在のコンテキストのランタイムが例外状態にあるかどうか。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 ランタイムへの呼び出しによって例外が発生した場合 (スクリプトを実行した場合、または変換エラーなどが原因である場合)、ランタイムは "例外の状態" に配置されます。 ランタイムによって作成されたコンテキスト (例外 Api を除く) へのすべての呼び出しは、 `JsErrorInExceptionState` 例外が消去されるまで失敗します。  
  
 コールバックがエンジンに返されたときに、現在のコンテキストのランタイムが例外状態にある場合、エンジンは例外を自動的に再スローします。  
  
 アクティブなスクリプトコンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)