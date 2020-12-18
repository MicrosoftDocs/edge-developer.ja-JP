---
description: 新しいランタイムを作成します。
title: JsCreateRuntime 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateRuntime
helpviewer_keywords:
- JsCreateRuntime function
ms.assetid: 92d09b89-6593-4d73-a562-88f9fec10228
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 3b893bd75725d6d9da56417ba83adfce18d77bac
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234747"
---
# JsCreateRuntime 関数

新しいランタイムを作成します。
  
## 構文  
  
```cpp  
// Microsoft Edge mode signature  
STDAPI_(JsErrorCode) JsCreateRuntime(  
   _In_ JsRuntimeAttributes attributes,  
   _In_opt_ JsThreadServiceCallback threadService,  
   _Out_ JsRuntimeHandle *runtime);  
  
// Legacy mode signature  
STDAPI_(JsErrorCode) JsCreateRuntime(  
   _In_ JsRuntimeAttributes attributes,  
   _In_ JsRuntimeVersion version,  
   _In_opt_ JsThreadServiceCallback threadService,  
   _Out_ JsRuntimeHandle *runtime  
);  
```  
  
#### パラメーター  
 `attributes`  
 作成するランタイムの属性。  
  
 `version`  
 作成するランタイムのバージョン。  
  
 `threadService`  
 ランタイムのスレッド サービス。 null を指定できます。  
  
 `runtime`  
 作成されたランタイム。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 この `version` パラメーターは、Microsoft Edge モードではサポートされていません。 この API を Microsoft Edge モードで使用する方法の詳細については [、「Microsoft Edge](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)とレガシ エンジンのターゲット設定」を参照してください。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
