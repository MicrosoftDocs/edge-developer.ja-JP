---
description: スクリプトを実行するためのスクリプトコンテキストを作成します。
title: JsCreateContext 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateContext
helpviewer_keywords:
- JsCreateContext function
ms.assetid: aceca043-2c73-4029-a06c-8ad6695109cf
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 06bd4c4780a8c7610ebc95cfc0da058306ce5b78
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569376"
---
# JsCreateContext 関数
スクリプトを実行するためのスクリプトコンテキストを作成します。  
  
## 構文  
  
```cpp  
// Microsoft Edge mode signature  
STDAPI_(JsErrorCode) JsCreateContext(  
   _In_ JsRuntimeHandle runtime,  
   _Out_ JsContextRef *newContext);  
  
// Legacy mode signature  
STDAPI_(JsErrorCode) JsCreateContext(  
   _In_ JsRuntimeHandle runtime,  
   _In_ IDebugApplication *debugApplication,  
   _Out_ JsContextRef *newContext  
);  
```  
  
#### パラメーター  
 `runtime`  
 スクリプトコンテキストが作成されているランタイム。  
  
 `debugApplication`  
 デバッグに使用するデバッグアプリケーション。 このパラメーターは null でもかまいません。この場合、コンテキストに対してデバッグが有効になっていません。  
  
 `newContext`  
 作成されたスクリプトコンテキスト。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 各スクリプトコンテキストには、他のすべてのスクリプトコンテキストから分離された独自のグローバルオブジェクトがあります。  
  
 この `debugApplication` パラメーターは Microsoft Edge モードではサポートされていません。 Microsoft Edge モードでのこの API の使用について詳しくは、「 [Microsoft edge とレガシエンジンのターゲット](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)設定」をご覧ください。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)