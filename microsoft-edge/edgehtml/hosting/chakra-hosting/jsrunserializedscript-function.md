---
description: シリアル化されたスクリプトを実行します。
title: JsRunSerializedScript 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsRunSerializedScript
helpviewer_keywords:
- JsRunSerializedScript function
ms.assetid: 3fd3f6f1-eb3e-4751-92a5-c93b1035f3b2
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 46f293d76bf0944c1cdedae917735c505798f4ad
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235023"
---
# JsRunSerializedScript 関数

シリアル化されたスクリプトを実行します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsRunSerializedScript(  
   _In_z_ const wchar_t *script,  
   _In_ BYTE *buffer,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### パラメーター  
 `script`  
 シリアル化されたスクリプトのソース コード。  
  
 `buffer`  
 シリアル化されたスクリプト。  
  
 `sourceContext`  
 デバッグ可能なスクリプト コンテキストで使用できるスクリプトを識別する Cookie。  
  
 `sourceUrl`  
 スクリプトの作成場所。  
  
 `result`  
 スクリプトを実行した結果 (スクリプトがある場合)。 このパラメーターは null に設定できます。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 アクティブなスクリプト コンテキストが必要です。  
  
 バッファーはスクリプト エンジンによってメモリ内に保持されないので、スクリプトの実行に使用される可能性がある限り、コードで有効な状態を維持する必要があります。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
