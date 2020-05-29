---
description: Chakra ガーベジコレクターによって所有されているオブジェクトへの参照。
title: JsRef Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 6aafc39f-6b9c-457f-8bf0-48831bffe9b8
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: f5ce1ada67a4530ba57345b90c0b7deba6954c7c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570407"
---
# JsRef Typedef
Chakra ガーベジコレクターによって所有されているオブジェクトへの参照。  
  
## 構文  
  
```cpp  
typedef void *JsRef;  
```  
  
## 注釈  
 Chakra ランタイムは、ローカル変数またはパラメーター (スタック上) に保存されている限り、JsRef 参照を自動的に追跡します。 スタック以外の場所に JsRef を保存するには、JsAddRef と JsRelease を呼び出してオブジェクトの有効期間を管理する必要があります。そうでない場合、ガベージコレクターは、まだ使用中にオブジェクトを解放できます。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)