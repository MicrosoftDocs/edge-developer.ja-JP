---
description: 'ガベージ コレクションの前にランタイムによって呼び出されるコールバック関数を設定します。 '
title: JsSetRuntimeBeforeCollectCallback 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeBeforeCollectCallback
helpviewer_keywords:
- JsSetRuntimeBeforeCollectCallback function
ms.assetid: 7b2fb911-6007-4ed9-a307-66cefe590ea4
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 94ad29fcfb778fc630d70664f917c6b5c2637dde
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234514"
---
# JsSetRuntimeBeforeCollectCallback 関数

ガベージ コレクションの前にランタイムによって呼び出されるコールバック関数を設定します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsSetRuntimeBeforeCollectCallback(  
   _In_ JsRuntimeHandle runtime,  
   _In_opt_ void *callbackState,  
   _In_ JsBeforeCollectCallback beforeCollectCallback  
);  
```  
  
#### パラメーター  
 `runtime`  
 割り当てコールバックを登録するランタイム。  
  
 `callbackState`  
 コールバックに戻されるユーザー指定の状態。  
  
 `beforeCollectCallback`  
 設定するコールバック関数。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 コールバックは現在のランタイム実行スレッドで呼び出されるため、コールバックが完了するまで実行はブロックされます。  
  
 コールバックは、ホストがガベージ コレクションを準備するために使用できます。 たとえば、Chakra オブジェクトに対する不要な参照を解放します。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
