---
description: スクリプトの実行を中断し、実行時に実行中のスクリプトを終了します。
title: JsDisableRuntimeExecution 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsDisableRuntimeExecution
helpviewer_keywords:
- JsDisableRuntimeExecution function
ms.assetid: 4bd4670a-a9da-4f8c-b3fd-1fd366d915c3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 6a08e6a7f89c724f8cf1a73afd97d2cb23c0334e
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234729"
---
# JsDisableRuntimeExecution 関数

スクリプトの実行を中断し、実行時に実行中のスクリプトを終了します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsDisableRuntimeExecution(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### パラメーター  
 `runtime`  
 中断するランタイム。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 中断されたランタイムの呼び出しは、呼び出 `JsEnableRuntimeExecution` されるまで失敗します。  
  
 ランタイムがアクティブなスレッドでこの API を呼び出す必要はない。 ランタイムは中断状態に設定されますが、実行中のスクリプトはすぐには中断されない可能性があります。実行中のスクリプトは、できるだけ早くキャッチできない例外で終了されます。  
  
 既に中断されているランタイムでの実行の中断は、実行を中断しません。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
