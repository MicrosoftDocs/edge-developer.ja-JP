---
description: スクリプト コンテキストへの参照。
title: JsContextRef Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 8586bfcc-bb24-430d-a6f2-1a3b3e34ec2e
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: c8a8fcbd67afb150d682cfc19321f0f13acfe3a6
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234547"
---
# JsContextRef Typedef

スクリプト コンテキストへの参照。  
  
## 構文  
  
```cpp  
typedef JsRef JsContextRef;  
```  
  
## 注釈  
 各スクリプト コンテキストには、他のスクリプト コンテキストのグローバル オブジェクトとは異なる、独自のグローバル オブジェクトが含まれる。  
  
 多くの Chakra ホスティング API には、使用して設定できる "アクティブな" スクリプト コンテキストが必要です `JsSetCurrentContext` 。 現在のコンテキストを設定する必要がある、Chakra ホスティング API は、ドキュメント内で明示的に注意してください。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
