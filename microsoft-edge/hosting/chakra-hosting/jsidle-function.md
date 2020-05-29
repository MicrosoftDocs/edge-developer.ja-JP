---
description: 実行する必要があるアイドル処理をランタイムに指示します。
title: JsIdle 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsIdle
helpviewer_keywords:
- JsIdle function
ms.assetid: 372d1c62-8e19-4886-aa33-364cabc09bba
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 4da7148bf7daa3db983ab8f5bba622bfe0b19466
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570425"
---
# JsIdle 関数
実行する必要があるアイドル処理をランタイムに指示します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsIdle(  
   _Out_opt_ unsigned int *nextIdleTick  
);  
```  
  
#### パラメーター  
 `nextIdleTick`  
 次のシステムでは、アイドル作業がより多く発生する場合にオンになります。 Null を指定できます。 次のアイドル作業が存在しない場合は、タイマー刻みの最大値を返します。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 現在のランタイムでアイドル処理が有効になっている場合、呼び出し `JsIdle` は、ホストがアイドル状態であり、ランタイムがメモリクリーンアップタスクを実行できることを現在のランタイムに通知します。  
  
 `JsIdle` また、ランタイムが実行できるアイドル作業が増加するまで、システムのタイマー刻みの数を返すことができます。 `JsIdle`この数のタイマー刻みより前に通話を発信しても、動作はありません。  
  
 アクティブなスクリプトコンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)