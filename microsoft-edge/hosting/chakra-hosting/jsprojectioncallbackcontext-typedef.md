---
description: JsRT からアプリケーションコールバックの JsProjectionEnqueueCallback に渡されたコンテキストが、指定されたコールバックで JsRT に渡された場合は、 `JsProjectionCallback` 正しいスレッド上のアプリケーションによって返されます。
title: JsProjectionCallbackContext Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 50c705c5-664f-4a1a-92f6-4882fc718ab1
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 58d4c74da13ae0dd269f3c101bbf3d2b95e77732
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569279"
---
# JsProjectionCallbackContext Typedef
JsRT からアプリケーションコールバックの JsProjectionEnqueueCallback に渡されたコンテキストが、指定されたコールバックで JsRT に渡された場合は、 `JsProjectionCallback` 正しいスレッド上のアプリケーションによって返されます。  
  
## 構文  
  
```cpp  
typedef void *JsProjectionCallbackContext;  
```  
  
## 注釈  
 `JsSetProjectionEnqueueCallback`コールバックを受け取るには、呼び出しを行う必要があります。  
  
 この API は、EdgeHTML モードでのみサポートされます。  
  
## 要件  
 jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)