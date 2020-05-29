---
description: スクリプトコンテキストへの参照。
title: JsContextRef Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 8586bfcc-bb24-430d-a6f2-1a3b3e34ec2e
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 80e4b5034079f4f0d26da070bd209aa41bf3475f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569390"
---
# JsContextRef Typedef
スクリプトコンテキストへの参照。  
  
## 構文  
  
```cpp  
typedef JsRef JsContextRef;  
```  
  
## 注釈  
 各スクリプトコンテキストには、他のスクリプトコンテキストのグローバルオブジェクトとは異なる、固有のグローバルオブジェクトが含まれています。  
  
 多くの Chakra ホスティング Api には、を使って設定できる "アクティブな" スクリプトコンテキストが必要 `JsSetCurrentContext` です。 現在のコンテキストを設定する必要がある Chakra ホスティング Api は、ドキュメントに明示的に含まれていることに注意してください。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)