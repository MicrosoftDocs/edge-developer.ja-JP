---
description: シリアル化されたスクリプトのソース コードを読み込むランタイムによって呼び出されます。 呼び出し元は、スクリプト バッファーを有効な状態に保つ必要があります `JsSerializedScriptUnloadCallback` 。
title: JsSerializedScriptLoadSourceCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 9406c488-76ac-49e5-b305-39751f3412ea
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2bb30befc61003d20cdeaa293fd1fdfdc95b36f7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235087"
---
# JsSerializedScriptLoadSourceCallback Typedef

シリアル化されたスクリプトのソース コードを読み込むランタイムによって呼び出されます。 呼び出し元は、スクリプト バッファーを有効な状態に保つ必要があります `JsSerializedScriptUnloadCallback` 。  
  
## 構文  
  
```cpp  
typedef bool (CALLBACK * JsSerializedScriptLoadSourceCallback)(  
  _In_ JsSourceContextsourceContext,  
  _Outptr_result_z_ const wchar_t** scriptBuffer  
);  
```  
  
#### パラメーター  
 `sourceContext`  
 渡されるコンテキスト。または `JsParseSerializedScriptWithCallback` `JsRunSerializedScriptWithCallback` .  
  
 `scriptBuffer`  
 返されたスクリプト。  
  
## 注釈  
  
> [!WARNING]
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
