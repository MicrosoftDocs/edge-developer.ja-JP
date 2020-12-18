---
description: 現在のコンテキストのヒープが列挙されているかどうかを示す値を返します。
title: JsIsEnumeratingHeap 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsIsEnumeratingHeap
helpviewer_keywords:
- JsIsEnumeratingHeap function
ms.assetid: 5d14518e-3153-43f2-9a9c-068580cbd54f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5b66fc70ea79d78029f6bc0c900ade1aae38e604
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234901"
---
# JsIsEnumeratingHeap 関数

現在のコンテキストのヒープが列挙されているかどうかを示す値を返します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsIsEnumeratingHeap(  
   _Out_ bool *isEnumeratingHeap  
);  
```  
  
#### パラメーター  
 `isEnumeratingHeap`  
 ヒープが列挙されているかどうかを示します。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 アクティブなスクリプト コンテキストが必要です。  
  
 この API はデスクトップ アプリでサポートされますが、ストア アプリではサポートされていません。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
