---
description: オブジェクトのガベージ コレクションの前にランタイムによって呼び出されるコールバック関数を設定します。
title: JsSetObjectBeforeCollectCallback 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: ea2cbd94-d8b0-4fa9-a4a1-c75a4e338eaf
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 4689184dccaf6bc9f98eeacda5f5a4b91a927d40
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234513"
---
# JsSetObjectBeforeCollectCallback 関数

オブジェクトのガベージ コレクションの前にランタイムによって呼び出されるコールバック関数を設定します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsSetObjectBeforeCollectCallback(  
   _In_ JsRef ref,  
   _In_opt_ void *callbackState,  
   _In_ JsObjectBeforeCollectCallback objectBeforeCollectCallback  
);  
```  
  
#### パラメーター  
 `ref`  
 コールバックを登録するオブジェクト。  
  
 `callbackState`  
 コールバックに戻されるユーザー指定の状態。  
  
 `objectBeforeCollectCallback`  
 設定するコールバック関数。 以前に登録したコールバックをクリアするには、null を使用します。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 コールバックは現在のランタイム実行スレッドで呼び出されるため、コールバックが完了するまで実行はブロックされます。  
  
 この API は EdgeHTML モードでのみサポートされています。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
