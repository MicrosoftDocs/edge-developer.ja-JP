---
description: ガベージ コレクション オブジェクトへの参照を追加します。
title: JsAddRef 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsAddRef
helpviewer_keywords:
- JsAddRef function
ms.assetid: a7f3ed49-6a86-489a-abdf-c99428e79cae
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: fd397dbfeacafdf12728ef0ca2a98d97405f6592
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234560"
---
# JsAddRef 関数

ガベージ コレクション オブジェクトへの参照を追加します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsAddRef(  
   _In_ JsRef ref,  
   _Out_opt_ unsigned int *count  
);  
```  
  
#### パラメーター  
 `ref`  
 参照を追加するオブジェクトを指定します。  
  
 `count`  
 オブジェクトの新しい参照カウント (null を渡す場合があります)。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 これは、スタック上のどこかに格納されないハンドルでのみ呼び出 `JsRef` す必要があります。 呼 `JsAddRef` び出しは、参照元のオブジェクトが呼び出されるまで解放 `JsRef` `JsRelease` されません。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
