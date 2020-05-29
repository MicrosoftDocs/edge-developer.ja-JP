---
description: スレッドサービスのコールバック。
title: JsThreadServiceCallback Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: dbe67be5-418a-4f66-8b68-b38078a6d140
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 5eb9f2986c79db024f01f4d22050f79c9689400c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569269"
---
# JsThreadServiceCallback Typedef
スレッドサービスのコールバック。  
  
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
  
 "いいね" データ  
 コールバックに渡されるデータ引数。  
  
## 注釈  
 ホストでは、JsCreateRuntime を呼び出すときにバックグラウンドスレッドサービスを指定できます。 指定すると、このコールバックを使用して、バックグラウンド作業項目がホストに渡されます。 ホストは、バックグラウンド作業項目の実行を直ちに開始し、true を返すか false を返し、ランタイムがスレッド内の作業項目を処理することを前提としています。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)