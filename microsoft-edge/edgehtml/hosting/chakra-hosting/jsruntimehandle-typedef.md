---
description: チャクラ ランタイムへのハンドル。
title: JsRuntimeHandle Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 69e59bfd-9b0e-4710-9aa8-fbd6844171bc
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: ab08243505b9699fe07ca2e80f7294adf9eb78ad
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234511"
---
# JsRuntimeHandle Typedef

チャクラ ランタイムへのハンドル。  
  
## 構文  
  
```cpp  
typedef void *JsRuntimeHandle;  
```  
  
## 注釈  
 各 Chakra ランタイムには、独自の独立した実行エンジン、JIT コンパイラ、ガベージ コレクションヒープがあります。 そのため、各ランタイムは他のランタイムから完全に分離されます。  
  
 ランタイムは任意のスレッドで使用できますが、実行時に呼び出しできるのは 1 つのスレッドのみです。  
  
> [!WARNING]
>  JsRuntimeHandle は、Chakra ホスティング API の他のオブジェクト参照とは異なり、ガベージ コレクションヒープ自体が含まれているので、ガベージ コレクションされません。 JsDisposeRuntime が呼び出されるまで、ランタイムは引き続き存在します。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
