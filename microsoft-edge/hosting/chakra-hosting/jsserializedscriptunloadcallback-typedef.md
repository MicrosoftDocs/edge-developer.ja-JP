---
description: スクリプトの実行に関連するすべてのリソースが終了したときに、ランタイムによって呼び出されます。 この時点で、呼び出し元は、読み込み、バイトコード、コンテキストを解放する必要があります。
title: JsSerializedScriptUnloadCallback typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d18c392-cca0-411e-9f2b-0d788b16161a
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9555b3fd8c14c9629d17c13592e3c78a78be150e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570388"
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
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)