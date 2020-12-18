---
description: スレッド サービスコールバック。
title: JsThreadServiceCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: dbe67be5-418a-4f66-8b68-b38078a6d140
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a5f1fe416e158e9524bdd1caab847977a5dd21b8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234680"
---
# JsThreadServiceCallback Typedef

スレッド サービスコールバック。  
  
## 構文  
  
```cpp  
typedef bool (CALLBACK *JsThreadServiceCallback)(  
   _In_ JsBackgroundWorkItemCallback callback,  
   _In_opt_ void *callbackData  
);  
```  
  
#### パラメーター  
 callback  
 バックグラウンド作業項目のコールバック。  
  
 callbackData  
 コールバックに渡されるデータ引数。  
  
## 注釈  
 ホストは、JsCreateRuntime を呼び出す際にバックグラウンド スレッド サービスを指定できます。 指定した場合、バックグラウンド作業項目は、このコールバックを使用してホストに渡されます。 ホストは、バックグラウンド作業項目の実行を直ちに開始し、true を返す、または false を返す必要があります。ランタイムは作業項目をスレッド内で処理します。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
