---
description: スクリプトを実行するためのスクリプト コンテキストを作成します。
title: JsCreateContext 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateContext
helpviewer_keywords:
- JsCreateContext function
ms.assetid: aceca043-2c73-4029-a06c-8ad6695109cf
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5d6c8149b8a5e5fee7cbc8dac821713b1d9649ee
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234528"
---
# JsCreateContext 関数

スクリプトを実行するためのスクリプト コンテキストを作成します。  
  
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
 スクリプト コンテキストの作成中のランタイム。  
  
 `debugApplication`  
 デバッグに使用するデバッグ アプリケーション。 このパラメーターは null に設定できます。この場合、コンテキストに対してデバッグが有効になっていません。  
  
 `newContext`  
 作成されたスクリプト コンテキスト。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 各スクリプト コンテキストには、他のすべてのスクリプト コンテキストから分離された独自のグローバル オブジェクトがあります。  
  
 この `debugApplication` パラメーターは、Microsoft Edge モードではサポートされていません。 この API を Microsoft Edge モードで使用する方法の詳細については [、「Microsoft Edge](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)とレガシ エンジンのターゲット設定」を参照してください。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
