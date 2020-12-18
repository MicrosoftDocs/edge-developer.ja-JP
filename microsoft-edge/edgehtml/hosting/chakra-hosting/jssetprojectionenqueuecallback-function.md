---
description: 呼び出し元に必要なスレッドにプロジェクション完了を呼び出す際に使用するコールバックを設定します。
title: JsSetProjectionEnqueueCallback 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: c751ccef-20d2-4d41-9568-1c54adf47cdf
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7dfedfeb1df5a97159a211795a2dd072d239bb35
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234509"
---
# JsSetProjectionEnqueueCallback 関数

呼び出し元に必要なスレッドにプロジェクション完了を呼び出す際に使用するコールバックを設定します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsSetProjectionEnqueueCallback(  
   _In_ JsProjectionEnqueueCallback projectionEnqueueCallback,  
   _In_opt_ void *projectionEnqueueContext);  
  
```  
  
#### パラメーター  
 `projectionEnqueueContext`  
 バックグラウンド スレッドでプロジェクション完了が発生するといつでも呼び出されるコールバック。  
  
 `callbackState`  
 に提供されるアプリケーション コンテキスト `projectionEnqueueContext` 。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
 アクティブなスクリプト コンテキストが必要です。  
  
 呼び出しは、別の COM アパートメントまたは同じ MTA 内の別のスレッドから行う必要があります。  
  
 この API は EdgeHTML モードでのみサポートされています。  
  
> [!CAUTION]
>  現在、PInvoke は、この API ではサポートされていません。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
