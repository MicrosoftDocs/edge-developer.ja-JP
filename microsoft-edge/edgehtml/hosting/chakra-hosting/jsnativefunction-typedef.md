---
description: 関数コールバック。
title: JsNativeFunction Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 56ef6cdf-4ca9-4f7c-b953-e661addb1a8e
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 891fe55f776e8519a5d3c187104b2bc326336482
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234349"
---
# JsNativeFunction Typedef

関数コールバック。  
  
## 構文  
  
```cpp  
typedef _Ret_maybenull_ JsValueRef (CALLBACK * JsNativeFunction)(  
   _In_ JsValueRef callee,  
   _In_ bool isConstructCall,  
   _In_ JsValueRef *arguments,  
   _In_ unsigned short argumentCount  
);  
```  
  
#### パラメーター  
 呼び出し先  
 呼 `Function` び出される関数を表すオブジェクト。  
  
 isConstructCall  
 これが通常の通話か「新しい」呼び出しかを示します。  
  
 arguments  
 呼び出しの引数。  
  
 argumentCount  
 引数の数を指定します。  
  
## プロパティ値/戻り値  
 呼び出しの結果 (指定されている場合)。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
