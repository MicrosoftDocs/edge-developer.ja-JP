---
description: チャクラ ホスティング API から返されたエラー コード。
title: JsErrorCode 列挙 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsErrorCode
helpviewer_keywords:
- JsErrorCode enumeration
ms.assetid: 4902f3f3-47a5-4e74-9c29-f96eeecbcda9
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b0a4aa7b47070bd5c8c7fe48cdbecf0dbefa9aa5
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234664"
---
# JsErrorCode 列挙

チャクラ ホスティング API から返されたエラー コード。  
  
## 構文  
  
```cpp  
enum JsErrorCode : unsigned int;  
```  
  
## Members  
  
### 値  
  
|名前|説明|  
|----------|-----------------|  
|`JsErrorAlreadyDebuggingContext`|コンテキストは既にデバッグ状態なので、デバッグ状態にすることはできません。|  
|`JsErrorAlreadyProfilingContext`|コンテキストは既にプロファイリングを行っているので、プロファイリングを開始できません。|  
|`JsErrorArgumentNotObject`|オブジェクト値を操作するホスティング API が、オブジェクト以外の値で呼び出されました。|  
|`JsErrorBadSerializedScript`|シリアル化されたスクリプトが使用されていないか、シリアル化されたスクリプトが別のバージョンのチャクラ エンジンによってシリアル化されました。|  
|`JsErrorCannotDisableExecution`|ランタイムは、信頼性の高いスクリプト中断をサポートしていない。|  
|`JsErrorCannotSerializeDebugScript`|スクリプトはデバッグ コンテキストではシリアル化できません。|  
|`JsErrorCategoryEngine`|エンジン自体で発生するエラーに関連するエラーのカテゴリ。|  
|`JsErrorCategoryFatal`|致命的で、エンジンのエラーを示すエラーのカテゴリ。|  
|`JsErrorCategoryScript`|スクリプト内のエラーに関連するエラーのカテゴリ。|  
|`JsErrorCategoryUsage`|API 自体の不適切な使用に関連するエラーのカテゴリ。|  
|`JsErrorFatal`|エンジンで致命的なエラーが発生しました。|  
|`JsErrorHeapEnumInProgress`|現在、スクリプト コンテキストでヒープ列挙が進行中です。|  
|`JsErrorIdleNotEnabled`|ホストがアイドル処理を有効にしなかったときに発生するアイドル通知。|  
|`JsErrorInDisabledState`|ランタイムは無効な状態です。|  
|`JsErrorInExceptionState`|エンジンは例外状態であり、例外がクリアされるまで API は呼び出されません。|  
|`JsErrorInObjectBeforeCollectCallback`|この操作は、コールバックを収集する前のオブジェクトではサポートされていません。<br /><br /> この列挙値は、Microsoft Edge モードでのみサポートされます。|  
|`JsErrorInProfileCallback`|スクリプト コンテキストは、プロファイル コールバックの途中です。|  
|`JsErrorInThreadServiceCallback`|スレッド サービスコールバックは現在進行中です。|  
|`JsErrorInvalidArgument`|ホスティング API に対する引数が無効です。|  
|`JsErrorNoCurrentContext`|ホスティング API では、コンテキストが最新である必要がありますが、現在のコンテキストはありません。|  
|`JsErrorNotImplemented`|ホスティング API はまだ実装されていません。|  
|`JsErrorNullArgument`|ホスティング API に対する引数は、null が許可されていないコンテキストでは null でした。|  
|`JsErrorObjectNotInspectable`|オブジェクトをポインターに対して折り返 `IInspectable` し解除することはできません。<br /><br /> この列挙値は、Microsoft Edge モードでのみサポートされます。|  
|`JsErrorOutOfMemory`|チャクラ エンジンのメモリが使い切った。|  
|`JsErrorPropertyNotSymbol`|シンボル プロパティ ID で動作するが、シンボル以外のプロパティ ID で呼び出されたホスティング API。シンボル以外のプロパティ ID で関数が呼び出された場合、エラー `JsGetSymbolFromPropertyId` コードが返されます。<br /><br /> この列挙値は、Microsoft Edge モードでのみサポートされます。|  
|`JsErrorPropertyNotString`|文字列プロパティ ID を操作するが、文字列以外のプロパティ ID で呼び出されたホスティング API。文字列以外のプロパティ ID で関数が呼び出された場合は、既存のエラー `JsGetPropertyNamefromId` コードが返されます。<br /><br /> この列挙値は、Microsoft Edge モードでのみサポートされます。|  
|`JsErrorRuntimeInUse`|まだ使用されているランタイムは破棄できません。|  
|`JsErrorScriptCompile`|JavaScript のコンパイルに失敗しました。|  
|`JsErrorScriptEvalDisabled`|スクリプトが使用しようとしたか、または無効にされたため `eval` 、 `function` スクリプトは終了されました。|  
|`JsErrorScriptException`|スクリプトの実行中に JavaScript 例外が発生しました。|  
|`JsErrorScriptTerminated`|ランタイムを中断する要求が原因でスクリプトが終了しました。|  
|`JsErrorWrongRuntime`|異なる JavaScript ランタイムで作成されたオブジェクトを使用して、ホスティング API が呼び出されました。|  
|`JsErrorWrongThread`|ホスティング API が間違ったスレッドで呼び出されました。|  
|`JsNoError`|成功エラー コード。|  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
