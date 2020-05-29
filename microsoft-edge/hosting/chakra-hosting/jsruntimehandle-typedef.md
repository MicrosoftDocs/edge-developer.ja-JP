---
description: Chakra ランタイムへのハンドル。
title: JsRuntimeHandle Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 69e59bfd-9b0e-4710-9aa8-fbd6844171bc
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 4ccdcf39ec6062db47e1b9de249d75c8804de405
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570390"
---
# JsRuntimeHandle Typedef
Chakra ランタイムへのハンドル。  
  
## 構文  
  
```cpp  
typedef void *JsRuntimeHandle;  
```  
  
## 注釈  
 各 Chakra ランタイムには、独自の独立した実行エンジン、JIT コンパイラ、およびガベージコレクションヒープがあります。 このように、各ランタイムは、他のランタイムから完全に分離されます。  
  
 ランタイムはどのスレッドでも使うことができますが、ランタイムをいつでも呼び出すことができるスレッドは1つだけです。  
  
> [!WARNING]
>  JsRuntimeHandle は、Chakra ホスティング API の他のオブジェクト参照とは異なり、ガベージコレクションされたヒープ自体が含まれているため、ガベージコレクションされません。 JsDisposeRuntime が呼び出されるまで、ランタイムは引き続き存在します。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)