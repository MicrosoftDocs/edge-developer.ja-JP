---
description: 渡された引数を `VARIANT` JavaScript 値のプロジェクションとして初期化します。
title: JsValueToVariant 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsValueToVariant
helpviewer_keywords:
- JsValueToVariant function
ms.assetid: 070244be-a69d-4b78-971b-69c0579c03cf
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: d8748fddcc149cf09fbd46ad3ad489cd66200b71
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569262"
---
# JsValueToVariant 関数
渡された引数を `VARIANT` JavaScript 値のプロジェクションとして初期化します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsValueToVariant(  
   _In_ JsValueRef object,  
   _Out_ VARIANT *variant  
);  
```  
  
#### パラメーター  
 `object`  
 プロジェクトの JavaScript 値 `VARIANT` 。  
  
 `variant`  
 `VARIANT`プロジェクションとして初期化される構造体へのポインター。  
  
## 戻り値  
  
## 注釈  
 プロジェクション `VARIANT` を COM オートメーションクライアントで使って、投影された JavaScript オブジェクトを呼び出すことができます。  
  
 アクティブなスクリプトコンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)