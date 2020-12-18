---
description: 文字列値の文字列ポインターを取得します。
title: JsStringToPointer 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsStringToPointer
helpviewer_keywords:
- JsStringToPointer function
ms.assetid: c7aa7a09-489d-4435-8f8a-aeb62f8875ae
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 77b8e16be41d8b5541129b50fa200b947f566342
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234682"
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
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 この関数は、文字列値の文字列ポインターを取得します。 値の型が `JsErrorInvalidArgument` 文字列ではない場合は失敗します。 返される文字列の有効期間は、取得元の値の有効期間と同じですが、文字列ポインターは値への参照とは見なされません (したがって、収集されません)。  
  
 アクティブなスクリプト コンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
