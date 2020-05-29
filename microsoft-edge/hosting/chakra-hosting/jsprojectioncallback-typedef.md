---
description: 適切なスレッドで渡されたコンテキストで呼び出される JsRT callback `JsProjectionEnqueueCallback` 。
title: JsProjectionCallback Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 32f22d37-e57e-4196-b6cd-a3fc75bd0632
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: b30f9a7dc4671896eeacecbf58ef88f0383e9e7e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569278"
---
# JsProjectionCallback Typedef
適切なスレッドで渡されたコンテキストで呼び出される JsRT callback `JsProjectionEnqueueCallback` 。  
  
## 構文  
  
```cpp  
typedef void (CALLBACK *JsProjectionCallback)(  
  _In_ JsProjectionCallbackContext jsContext  
);  
```  
  
#### パラメーター  
 `jsContext`  
 `JsSetProjectionEnqueueCallback`コールバックを受け取るには、呼び出しを行う必要があります。  
  
## 注釈  
 この API は、EdgeHTML モードでのみサポートされます。  
  
## 要件  
 jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)