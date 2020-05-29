---
description: 名前を指定して、新しい JavaScript 関数を作成します。
title: JsCreateNamedFunction 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 72f40d06-ab82-4fed-a632-68af6b4126c2
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: d963fe196b8e56394e22501ed3898a0d887a3d3b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569363"
---
# JsCreateNamedFunction 関数
名前を指定して、新しい JavaScript 関数を作成します。
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateNamedFunction(  
   _In_ JsValueRef name,  
   _In_ JsNativeFunction nativeFunction,  
   _In_opt_ void *callbackState,  
   _Out_ JsValueRef *function  
);  
```  
  
#### パラメーター  
 `name`  
 診断と stringification の目的で使用されるこの関数の名前。  
  
 `nativeFunction`  
 関数が呼び出されたときに呼び出すメソッド。  
  
 `callbackState`  
 コールバックに戻される、ユーザーによって指定された状態。  
  
 `function`  
 新しい関数オブジェクト。  
  
## 戻り値  
  
## 注釈  
 アクティブなスクリプトコンテキストが必要です。  
  
 この API は、Microsoft Edge モードでのみサポートされます。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)