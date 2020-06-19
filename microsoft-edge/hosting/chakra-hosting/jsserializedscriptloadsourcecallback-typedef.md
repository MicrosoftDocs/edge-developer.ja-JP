---
description: シリアル化されたスクリプトのソースコードを読み込むために、ランタイムによって呼び出されます。 呼び出し元は、の前に、スクリプトバッファーを有効な状態に維持する必要があり `JsSerializedScriptUnloadCallback` ます。
title: JsSerializedScriptLoadSourceCallback Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 9406c488-76ac-49e5-b305-39751f3412ea
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 571314145cc19513f04174a9a1c93822a5795b29
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752200"
---
# JsSerializedScriptLoadSourceCallback Typedef
シリアル化されたスクリプトのソースコードを読み込むために、ランタイムによって呼び出されます。 呼び出し元は、の前に、スクリプトバッファーを有効な状態に維持する必要があり `JsSerializedScriptUnloadCallback` ます。  
  
## 構文  
  
```cpp  
typedef bool (CALLBACK * JsSerializedScriptLoadSourceCallback)(  
  _In_ JsSourceContextsourceContext,  
  _Outptr_result_z_ const wchar_t** scriptBuffer  
);  
```  
  
#### パラメーター  
 `sourceContext`  
 またはに渡されたコンテキスト `JsParseSerializedScriptWithCallback` `JsRunSerializedScriptWithCallback` 。  
  
 `scriptBuffer`  
 スクリプトが返されました。  
  
## 注釈  
  
> [!WARNING]
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)