---
description: バックグラウンド作業項目のコールバック。
title: JsBackgroundWorkItemCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: e6db52e1-830c-46a2-b9f9-cc2d450a1da8
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d69306b334c2e0c9b27b96a5a417739ffdcd7dd7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234558"
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
 callbackData  
 スレッド サービスに渡されるデータ引数。  
  
## 注釈  
 これは、ホストのスレッド サービス (指定されている場合) に渡されます。これにより、ホストは選択したバックグラウンド スレッドで作業項目のコールバックを呼び出す可能性があります。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
