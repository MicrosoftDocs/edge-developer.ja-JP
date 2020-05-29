---
description: 'ランタイムの属性。 '
title: JsRuntimeAttributes 列挙 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsRuntimeAttributes
helpviewer_keywords:
- JsRuntimeAttributes enumeration
ms.assetid: f76d82e9-a695-4d6a-96c1-b3a4d27fed68
caps.latest.revision: 14
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9b8f6788f1de4988e3936701cfc742a564c92cfd
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570392"
---
# JsRuntimeAttributes 列挙
ランタイムの属性。  
  
## 構文  
  
```cpp  
enum JsRuntimeAttributes;  
```  
  
## Members  
  
### 値  
  
|名前|説明|  
|----------|-----------------|  
|`JsRuntimeAttributeAllowScriptInterrupt`|ランタイムは、信頼性の高いスクリプトの中断をサポートしている必要があります。 これにより、実行時のパフォーマンスがわずかな場合に、実行時にスクリプト割り込み要求がチェックされる場所の数が増えます。|  
|`JsRuntimeAttributeDisableBackgroundWork`|ランタイムは、バックグラウンドスレッドでの作業 (ガベージコレクションなど) を実行しません。|  
|`JsRuntimeAttributeDisableEval`|Using `eval` または `function` コンストラクターで例外がスローされます。|  
|`JsRuntimeAttributeDisableNativeCodeGeneration`|実行時にネイティブコードは生成されません。|  
|`JsRuntimeAttributeEnableExperimentalFeatures`|Runtime は、すべての実験的な機能を有効にします。|  
|`JsRuntimeAttributeEnableIdleProcessing`|ホストが通話 `JsIdle` を発信し、アイドル処理を有効にします。 そうしないと、ランタイムはメモリをやや積極的に管理します。|  
|`JsRuntimeAttributeDispatchSetExceptionsToDebugger`|呼び出しによって、例外が発生した `JsSetException` 場合にデバッガーに例外が発生する可能性があります (存在する場合)。|  
|`JsRuntimeAttributeNone`|特別な属性はありません。|  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)