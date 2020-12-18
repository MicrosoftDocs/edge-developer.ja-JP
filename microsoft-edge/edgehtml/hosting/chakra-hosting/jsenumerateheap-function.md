---
description: 現在のコンテキストのヒープを列挙します。
title: JsEnumerateHeap 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsEnumerateHeap
helpviewer_keywords:
- JsEnumerateHeap function
ms.assetid: 3e518e0b-b959-4686-899c-83e6b1946c9d
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: bb76b28f24b769f71827e59be691188e34e9e1a3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234875"
---
# JsEnumerateHeap 関数

現在のコンテキストのヒープを列挙します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsEnumerateHeap(  
   _Out_ IActiveScriptProfilerHeapEnum **enumerator  
);  
```  
  
#### パラメーター  
 `enumerator`  
 ヒープ列挙子。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 ヒープの列挙中は現在のコンテキストを削除できません。また、ヒープ列挙子が解放されるまで、コンテキストの状態を変更する呼び出しはすべて失敗します。  
  
 アクティブなスクリプト コンテキストが必要です。  
  
 この API はデスクトップ アプリでサポートされますが、ストア アプリではサポートされていません。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
