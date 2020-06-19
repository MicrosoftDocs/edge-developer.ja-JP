---
description: スクリプトの実行に関連するすべてのリソースが終了したときに、ランタイムによって呼び出されます。 この時点で、呼び出し元は、読み込み、バイトコード、コンテキストを解放する必要があります。
title: JsSerializedScriptUnloadCallback typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 8d18c392-cca0-411e-9f2b-0d788b16161a
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c3da27af18ebc7a1913980a865d926bac6a29d11
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10751941"
---
# JsSerializedScriptUnloadCallback typedef
スクリプトの実行に関連するすべてのリソースが終了したときに、ランタイムによって呼び出されます。 この時点で、呼び出し元は、読み込み、バイトコード、コンテキストを解放する必要があります。  
  
## 構文  
  
```cpp  
 typedef void (CALLBACK * JsSerializedScriptUnloadCallback)(  
  _In_ JsSourceContext sourceContext  
);  
```  
  
#### パラメーター  
 `sourceContext`  
 またはに渡されたコンテキスト `JsParseSerializedScriptWithCallback` `JsRunSerializedScriptWithCallback` 。  
  
## 注釈  
  
> [!WARNING]
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)