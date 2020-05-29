---
description: 呼び出し元の要求されたスレッドへのプロジェクション完了を呼び出すために使用されるコールバックを設定します。
title: JsSetProjectionEnqueueCallback 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: c751ccef-20d2-4d41-9568-1c54adf47cdf
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 02da0238360b0dc6fff9bb86c9f5ab04d1ba7112
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570369"
---
# JsSetProjectionEnqueueCallback 関数
呼び出し元の要求されたスレッドへのプロジェクション完了を呼び出すために使用されるコールバックを設定します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsSetProjectionEnqueueCallback(  
   _In_ JsProjectionEnqueueCallback projectionEnqueueCallback,  
   _In_opt_ void *projectionEnqueueContext);  
  
```  
  
#### パラメーター  
 `projectionEnqueueContext`  
 バックグラウンドスレッドでプロジェクションの完了が発生するたびに呼び出されるコールバック。  
  
 `callbackState`  
 提供されるアプリケーションコンテキスト `projectionEnqueueContext` 。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 アクティブなスクリプトコンテキストが必要です。  
  
 呼び出しは、別の COM アパートメントから、または同じ MTA 内の別のスレッドから行う必要があります。  
  
 この API は、EdgeHTML モードでのみサポートされます。  
  
> [!CAUTION]
>  PInvoke は、この API では現在サポートされていません。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)