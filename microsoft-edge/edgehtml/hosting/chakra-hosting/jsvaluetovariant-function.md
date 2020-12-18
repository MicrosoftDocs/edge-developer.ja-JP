---
description: 渡されたメソッドを `VARIANT` JavaScript 値のプロジェクションとして初期化します。
title: JsValueToVariant 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsValueToVariant
helpviewer_keywords:
- JsValueToVariant function
ms.assetid: 070244be-a69d-4b78-971b-69c0579c03cf
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f383f2d8bc3aab70b4a361b370698cd71cb714d3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234678"
---
# JsValueToVariant 関数

渡されたメソッドを `VARIANT` JavaScript 値のプロジェクションとして初期化します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsValueToVariant(  
   _In_ JsValueRef object,  
   _Out_ VARIANT *variant  
);  
```  
  
#### パラメーター  
 `object`  
 A JavaScript value to project as a `VARIANT` .  
  
 `variant`  
 プロジェクションとして初期化 `VARIANT` される構造体へのポインター。  
  
## 戻り値  
  
## 注釈  
 プロジェクションは `VARIANT` 、COM オートメーション クライアントが投影された JavaScript オブジェクトを呼び出す場合に使用できます。  
  
 アクティブなスクリプト コンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
