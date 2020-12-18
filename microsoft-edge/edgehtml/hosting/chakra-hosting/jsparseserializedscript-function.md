---
description: シリアル化されたスクリプトを解析し、スクリプトを表す関数を返します。
title: JsParseSerializedScript 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsParseSerializedScript
helpviewer_keywords:
- JsParseSerializedScript function
ms.assetid: 40d0c7c4-fd5b-46ed-9e65-38c2db2fc859
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 66ecabb9d96c3f339625f93858444f55d25fd4d7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234860"
---
# JsParseSerializedScript 関数

シリアル化されたスクリプトを解析し、スクリプトを表す関数を返します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsParseSerializedScript(  
   _In_z_ const wchar_t *script,  
   _In_ BYTE *buffer,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### パラメーター  
 `script`  
 解析するスクリプト。  
  
 `buffer`  
 シリアル化されたスクリプト。  
  
 `sourceContext`  
 デバッグ可能なスクリプト コンテキストで使用できるスクリプトを識別する Cookie。  
  
 `sourceUrl`  
 スクリプトの作成場所。  
  
 `result`  
 スクリプト コードを表す関数。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 アクティブなスクリプト コンテキストが必要です。  
  
 バッファーはスクリプト エンジンによってメモリ内に保持されないので、スクリプトの実行に使用される可能性がある限り、コードで有効な状態を維持する必要があります。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
