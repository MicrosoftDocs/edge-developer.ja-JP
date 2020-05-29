---
description: 文字列値の文字列ポインターを取得します。
title: JsStringToPointer 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsStringToPointer
helpviewer_keywords:
- JsStringToPointer function
ms.assetid: c7aa7a09-489d-4435-8f8a-aeb62f8875ae
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1f5997894c4ea479378a323b230492dde28ab177
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570271"
---
# JsStringToPointer 関数
文字列値の文字列ポインターを取得します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsStringToPointer(  
   _In_ JsValueRef value,  
   _Outptr_result_buffer_(*stringLength) const wchar_t **stringValue,  
   _Out_ size_t *stringLength  
);  
```  
  
#### パラメーター  
 `value`  
 文字列ポインターに変換する文字列値。  
  
 `stringValue`  
 文字列ポインター。  
  
 `stringLength`  
 文字列の長さ。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 この関数は、文字列値の文字列ポインターを取得します。 `JsErrorInvalidArgument`値の型が文字列でない場合は、エラーが発生します。 返される文字列の有効期間は、元の値の有効期間と同じになりますが、文字列ポインターは値への参照と見なされません (そのため、その値が収集されることはありません)。  
  
 アクティブなスクリプトコンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)