---
description: 渡されたポインターのプロジェクションである JavaScript 値を作成 `IInspectable` します。
title: JsInspectableToObject 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: dd0ad567-2ba8-4a63-bee4-2c6ff5ce9fa9
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a5d3d91b38c9db5de2eb8fb02526f6072f0f5147
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234910"
---
# JsInspectableToObject 関数

渡されたポインターのプロジェクションである JavaScript 値を作成 `IInspectable` します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsInspectableToObject(  
        _In_ IInspectable  *inspectable,  
        _Out_ JsValueRef *value  
);  
```  
  
#### パラメーター  
 `inspectable`  
 投影 `IInspectable` される A。  
  
 `value`  
 のプロジェクションである JavaScript 値 `IInspectable` 。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 投影された値は、スクリプトで WinRT オブジェクトを呼び出す場合に使用できます。 ホストは COM スレッド ルールを適用する必要があります。  
  
 アクティブなスクリプト コンテキストが必要です。  
  
 この API は EdgeHTML モードでのみサポートされています。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
