---
description: 実行時にスクリプトの実行を中断し、実行中のスクリプトを終了します。
title: JsDisableRuntimeExecution 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsDisableRuntimeExecution
helpviewer_keywords:
- JsDisableRuntimeExecution function
ms.assetid: 4bd4670a-a9da-4f8c-b3fd-1fd366d915c3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 575947d3038eaa136e9d6ae62507501bc768eabe
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569339"
---
# JsDisableRuntimeExecution 関数
実行時にスクリプトの実行を中断し、実行中のスクリプトを終了します。  
  
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
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 中断されたランタイムへの呼び出しは、が呼び出されるまで失敗 `JsEnableRuntimeExecution` します。  
  
 この API は、ランタイムがアクティブになっているスレッドで呼び出される必要はありません。 ランタイムは中断状態に設定されますが、実行中のスクリプトはすぐに中断されない可能性があります。実行中のスクリプトは、できるだけ早く uncatchable 例外で終了します。  
  
 既に中断されているランタイムで実行を中断することは、何の操作でもありません。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)