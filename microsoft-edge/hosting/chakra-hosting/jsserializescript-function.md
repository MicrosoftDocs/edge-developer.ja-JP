---
description: 解析されたスクリプトを再利用可能なバッファーにシリアル化します。
title: JsSerializeScript 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSerializeScript
helpviewer_keywords:
- JsSerializeScript function
ms.assetid: ca42c194-e1c1-407d-b542-b9d494e3ac4e
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1b45067fddb7ea4dff02e527e460db1270011c61
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570386"
---
# JsSerializeScript 関数
解析されたスクリプトを再利用可能なバッファーにシリアル化します。  
  
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
 シリアル化されたスクリプトを格納するバッファー。 Null を指定できます。  
  
 `bufferSize`  
 エントリの場合は、バッファーのサイズ (バイト単位)。終了時に、シリアル化されたスクリプトを保持するために必要なバッファーのサイズ (バイト単位)。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 `JsSerializeScript` スクリプトを解析し、実行時に依存しない形式でスクリプトの解析された形式を保存します。 シリアル化されたスクリプトは、スクリプトを再解析する必要なく、任意のランタイムで逆シリアル化することができます。  
  
 アクティブなスクリプトコンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)