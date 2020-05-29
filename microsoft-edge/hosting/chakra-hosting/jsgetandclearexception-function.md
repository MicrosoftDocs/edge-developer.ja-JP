---
description: 現在のコンテキストのランタイムが例外の状態であり、そのランタイムの例外の状態をリセットした場合に発生する例外を返します。
title: JsGetAndClearException 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetAndClearException
helpviewer_keywords:
- JsGetAndClearException function
ms.assetid: 6aec8a88-41ee-47f6-b5f4-32f3cae6bb7b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: eb70b4b66b4bb270d9f26487708720efddc2effa
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570465"
---
# JsGetAndClearException 関数
現在のコンテキストのランタイムが例外の状態であり、そのランタイムの例外の状態をリセットした場合に発生する例外を返します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsGetAndClearException(  
   _Out_ JsValueRef *exception  
);  
```  
  
#### パラメーター  
 `exception`  
 現在のコンテキストのランタイムの例外。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 現在のコンテキストのランタイムが例外状態ではない場合は、この API から戻り `JsErrorInvalidArgument` ます。 ランタイムが無効になっている場合、スクリプトが終了されたことを示す例外が返されますが、例外は消去されません (ランタイムが再有効化されている場合、例外は消去され `JsEnableRuntimeExecution` ます)。  
  
 アクティブなスクリプトコンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)