---
description: バックグラウンド作業項目のコールバック。
title: JsBackgroundWorkItemCallback Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: e6db52e1-830c-46a2-b9f9-cc2d450a1da8
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9bc1e5687d92d7286e1e6d4387bd6b69d95ceb68
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569403"
---
# JsBackgroundWorkItemCallback Typedef
バックグラウンド作業項目のコールバック。  
  
## 構文  
  
```cpp  
typedef void (CALLBACK *JsBackgroundWorkItemCallback)(  
   _In_opt_ void *callbackData  
);  
```  
  
#### パラメーター  
 "いいね" データ  
 スレッドサービスに渡されるデータ引数。  
  
## 注釈  
 これは、ホストのスレッドサービス (提供されている場合) に渡されます。これは、選択したバックグラウンドスレッドでホストが作業項目のコールバックを呼び出すことができるようにするためです。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)