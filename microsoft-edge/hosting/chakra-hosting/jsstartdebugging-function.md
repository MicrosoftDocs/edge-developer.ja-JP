---
description: 現在のコンテキストでデバッグを開始します。
title: JsStartDebugging 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsStartDebugging
helpviewer_keywords:
- JsStartDebugging function
ms.assetid: c48ba02d-6d47-466f-a970-02f087d525f3
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 2c94a6f36ad72bfb9354c85d98ae0b5b4e9c77fb
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570273"
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
 デバッグに使用するデバッグアプリケーション。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 `CoInitializeEx` `COINIT_MULTITHREADED` `COINIT_APARTMENTTHREADED` この API を使用するには、ホストが、または少なくとも1回呼び出されていることを確認する必要があります。  
  
 この `debugApplication` パラメーターは Microsoft Edge モードではサポートされていません。 Microsoft Edge モードでのこの API の使用について詳しくは、「 [Microsoft edge とレガシエンジンのターゲット](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)設定」をご覧ください。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)