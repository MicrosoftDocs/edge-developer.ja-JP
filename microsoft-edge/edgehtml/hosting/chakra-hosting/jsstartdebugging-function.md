---
description: 現在のコンテキストでデバッグを開始します。
title: JsStartDebugging 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsStartDebugging
helpviewer_keywords:
- JsStartDebugging function
ms.assetid: c48ba02d-6d47-466f-a970-02f087d525f3
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 9685779911db8e3045986682b66d13e38c70fe8d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235021"
---
# JsStartDebugging 関数

現在のコンテキストでデバッグを開始します。  
  
## 構文  
  
```cpp  
// Microsoft Edge mode signature  
STDAPI_(JsErrorCode) JsStartDebugging();  
  
// Legacy mode signature  
STDAPI_(JsErrorCode)  JsStartDebugging(  
   _In_ IDebugApplication *debugApplication  
);  
```  
  
#### パラメーター  
 `debugApplication`  
 デバッグに使用するデバッグ アプリケーション。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 ホストは、この API を使用する前に、この API で呼び出されるのか、少なくとも `CoInitializeEx` `COINIT_MULTITHREADED` 1 回は呼 `COINIT_APARTMENTTHREADED` び出される必要があります。  
  
 この `debugApplication` パラメーターは、Microsoft Edge モードではサポートされていません。 この API を Microsoft Edge モードで使用する方法の詳細については [、「Microsoft Edge](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)とレガシ エンジンのターゲット設定」を参照してください。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
