---
description: 渡されたポインターによって投影された JavaScript 値を作成し `IInspectable` ます。
title: JsInspectableToObject 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: dd0ad567-2ba8-4a63-bee4-2c6ff5ce9fa9
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 26ce17eb3abcefcf9a1f0cc773e9fe4c3aaf05cd
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569300"
---
# JsInspectableToObject 関数
渡されたポインターによって投影された JavaScript 値を作成し `IInspectable` ます。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsInspectableToObject(  
        _In_ IInspectable  *inspectable,  
        _Out_ JsValueRef *value  
);  
```  
  
#### パラメーター  
 `inspectable`  
 `IInspectable`を投影します。  
  
 `value`  
 のプロジェクションである JavaScript 値 `IInspectable` 。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 射影された値は、スクリプトで WinRT オブジェクトを呼び出すために使うことができます。 ホストは、COM スレッドルールの強制を行います。  
  
 アクティブなスクリプトコンテキストが必要です。  
  
 この API は、EdgeHTML モードでのみサポートされます。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)