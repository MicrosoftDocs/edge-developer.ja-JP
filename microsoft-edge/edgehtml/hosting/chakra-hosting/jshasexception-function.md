---
description: 現在のコンテキストのランタイムが例外状態であるかどうかを判別します。
title: JsHasException 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsHasException
helpviewer_keywords:
- JsHasException function
ms.assetid: ac7da3ce-c746-4154-bbb8-bcb0859a8d5b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 4f4abbd6c69a6b2b6414dae2f1de3a2acf21cc32
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234393"
---
# JsHasException 関数

現在のコンテキストのランタイムが例外状態であるかどうかを判別します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsHasException(  
   _Out_ bool *hasException  
);  
```  
  
#### パラメーター  
 `hasException`  
 現在のコンテキストのランタイムが例外状態であるかどうかを示します。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 ランタイムの呼び出しで例外が発生した場合 (スクリプトの実行結果、または変換エラーなどの理由により)、ランタイムは "例外状態" になります。 ランタイムによって作成されたコンテキストへのすべての呼び出し (例外 API を除く) は、例外がクリアされるまで `JsErrorInExceptionState` 失敗します。  
  
 コールバックがエンジンに戻る際に、現在のコンテキストのランタイムが例外状態にある場合、エンジンは自動的に例外を再スローします。  
  
 アクティブなスクリプト コンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
