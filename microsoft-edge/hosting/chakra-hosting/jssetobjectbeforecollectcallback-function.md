---
description: オブジェクトのガベージコレクションの前に、ランタイムによって呼び出されるコールバック関数を設定します。
title: JsSetObjectBeforeCollectCallback 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: ea2cbd94-d8b0-4fa9-a4a1-c75a4e338eaf
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 77a59c6ace96809c0b232c96aa9639555e7badcd
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570373"
---
# JsSetObjectBeforeCollectCallback 関数
オブジェクトのガベージコレクションの前に、ランタイムによって呼び出されるコールバック関数を設定します。  
  
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
 コールバックを登録する対象のオブジェクト。  
  
 `callbackState`  
 コールバックに戻される、ユーザーが指定した状態。  
  
 `objectBeforeCollectCallback`  
 設定されているコールバック関数。 以前に登録されたコールバックをクリアするには null を使用します。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 コールバックは現在のランタイム実行スレッドで呼び出されるため、コールバックが完了するまで実行はブロックされます。  
  
 この API は、EdgeHTML モードでのみサポートされます。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)