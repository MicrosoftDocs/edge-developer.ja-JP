---
description: 'ランタイムの属性。 '
title: JsRuntimeAttributes 列挙 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsRuntimeAttributes
helpviewer_keywords:
- JsRuntimeAttributes enumeration
ms.assetid: f76d82e9-a695-4d6a-96c1-b3a4d27fed68
caps.latest.revision: 14
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: bbc5341c3214d9796278d334507e284989ff45dd
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234650"
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
|`JsRuntimeAttributeAllowScriptInterrupt`|ランタイムは、信頼性の高いスクリプト中断をサポートする必要があります。 これにより、ランタイムがスクリプト割り込み要求をチェックする場所の数が増加しますが、実行時のパフォーマンスは小さくてすみません。|  
|`JsRuntimeAttributeDisableBackgroundWork`|ランタイムは、バックグラウンド スレッドで (ガベージ コレクションなどの) 作業を一切実行しません。|  
|`JsRuntimeAttributeDisableEval`|使用 `eval` またはコンストラクター `function` は例外をスローします。|  
|`JsRuntimeAttributeDisableNativeCodeGeneration`|ランタイムはネイティブ コードを生成しない。|  
|`JsRuntimeAttributeEnableExperimentalFeatures`|ランタイムは、試験的な機能を有効にします。|  
|`JsRuntimeAttributeEnableIdleProcessing`|ホストが呼び `JsIdle` 出すので、アイドル処理が有効になります。 そうしないと、ランタイムはメモリを少し積極的に管理します。|  
|`JsRuntimeAttributeDispatchSetExceptionsToDebugger`|また `JsSetException` 、呼び出しは例外をスクリプト デバッガーにディスパッチし (その場合)、デバッガーが例外でブレークする機会を与える必要があります。|  
|`JsRuntimeAttributeNone`|特別な属性はありません。|  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
