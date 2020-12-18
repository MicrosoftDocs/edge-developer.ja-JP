---
description: Chakra ガーベジ コレクターが所有するオブジェクトへの参照。
title: JsRef Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 6aafc39f-6b9c-457f-8bf0-48831bffe9b8
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 69d13472b15b5d448908b5dafb2e3d7dc0ace7e4
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234352"
---
# JsRef Typedef

Chakra ガーベジ コレクターが所有するオブジェクトへの参照。  
  
## 構文  
  
```cpp  
typedef void *JsRef;  
```  
  
## 注釈  
 Chakra ランタイムは、ローカル変数またはパラメーター (つまりスタック上) に格納されている限り、JsRef 参照を自動的に追跡します。 スタック以外の場所に JsRef を格納するには、オブジェクトの有効期間を管理するために JsAddRef と JsRelease を呼び出す必要があります。そうしないと、ガベージ コレクターは、オブジェクトがまだ使用されている間、オブジェクトを解放する可能性があります。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
