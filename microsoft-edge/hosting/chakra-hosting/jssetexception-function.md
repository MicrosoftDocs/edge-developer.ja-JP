---
description: 現在のコンテキストのランタイムを例外の状態に設定します。
title: JsSetException 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetException
helpviewer_keywords:
- JsSetException function
ms.assetid: c528793a-2e1b-4ee1-bd2e-e63fd547dc40
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 75d2895a725c622a0b46887d10154c3a0c56c7e9
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570382"
---
# JsSetException 関数
現在のコンテキストのランタイムを例外の状態に設定します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsSetException(  
   _In_ JsValueRef exception  
);  
```  
  
#### パラメーター  
 `exception`  
 現在のコンテキストの実行時に設定する JavaScript 例外。  
  
## 戻り値  
 `JsNoError` エンジンが例外状態に設定されていた場合は、エラーコードがありません。  
  
## 注釈  
 現在のコンテキストの実行時に既に例外状態になっている場合は、この API から戻り `JsErrorInExceptionState` ます。  
  
 アクティブなスクリプトコンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)