---
description: スクリプトの実行に関連するリソースが完了すると、ランタイムによって呼び出されます。 呼び出し元は、読み込まれた場合はソース、バイト コード、コンテキストを解放する必要があります。
title: JsSerializedScriptUnloadCallback typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 8d18c392-cca0-411e-9f2b-0d788b16161a
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5c63f2ff3faf21a19e31f2f6fd1692e21d59fc0b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235037"
---
# JsSerializedScriptUnloadCallback typedef

スクリプトの実行に関連するリソースが完了すると、ランタイムによって呼び出されます。 呼び出し元は、読み込まれた場合はソース、バイト コード、コンテキストを解放する必要があります。  
  
## 構文  
  
```cpp  
 typedef void (CALLBACK * JsSerializedScriptUnloadCallback)(  
  _In_ JsSourceContext sourceContext  
);  
```  
  
#### パラメーター  
 `sourceContext`  
 渡されるコンテキスト。または `JsParseSerializedScriptWithCallback` `JsRunSerializedScriptWithCallback` .  
  
## 注釈  
  
> [!WARNING]
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
