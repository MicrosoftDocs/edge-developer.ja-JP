---
description: 解析されたスクリプトを、再利用できるよりもバッファーにシリアル化します。
title: JsSerializeScript 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSerializeScript
helpviewer_keywords:
- JsSerializeScript function
ms.assetid: ca42c194-e1c1-407d-b542-b9d494e3ac4e
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 236cf40c91256e999d5390acd395b1e97fe538ad
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235036"
---
# JsSerializeScript 関数

解析されたスクリプトを、再利用できるよりもバッファーにシリアル化します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsSerializeScript(  
   _In_z_ const wchar_t *script,  
   _Out_writes_to_opt_(*bufferSize,  
   *bufferSize) BYTE *buffer,  
   _Inout_ unsigned long *bufferSize  
);  
```  
  
#### パラメーター  
 `script`  
 シリアル化するスクリプト。  
  
 `buffer`  
 シリアル化されたスクリプトを置くバッファー。 null を指定できます。  
  
 `bufferSize`  
 入力時のバッファーのサイズ (バイト単位)。が終了すると、シリアル化されたスクリプトを保持するために必要なバッファーのサイズ (バイト単位)。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 `JsSerializeScript` スクリプトを解析し、解析された形式のスクリプトをランタイムに依存しない形式で格納します。 シリアル化されたスクリプトは、スクリプトを再解析することなく、任意の実行時に逆シリアル化できます。  
  
 アクティブなスクリプト コンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
