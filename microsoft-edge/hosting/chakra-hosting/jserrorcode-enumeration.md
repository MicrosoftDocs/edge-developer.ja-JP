---
description: Chakra ホスティング API から返されるエラーコード。
title: JsErrorCode 列挙 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsErrorCode
helpviewer_keywords:
- JsErrorCode enumeration
ms.assetid: 4902f3f3-47a5-4e74-9c29-f96eeecbcda9
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: e3d1a319872ac69b2acaf19997f3c38f9c04597b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570467"
---
# JsErrorCode 列挙
Chakra ホスティング API から返されるエラーコード。  
  
## 構文  
  
```cpp  
enum JsErrorCode : unsigned int;  
```  
  
## Members  
  
### 値  
  
|名前|説明|  
|----------|-----------------|  
|`JsErrorAlreadyDebuggingContext`|コンテキストは既にデバッグ状態であるため、デバッグ状態にすることはできません。|  
|`JsErrorAlreadyProfilingContext`|コンテキストは既にプロファイリングされているため、プロファイリングを開始できません。|  
|`JsErrorArgumentNotObject`|オブジェクト値を操作するホスティング API が、オブジェクト以外の値で呼び出されました。|  
|`JsErrorBadSerializedScript`|シリアル化されたスクリプトが無効になったか、シリアル化されたスクリプトが別のバージョンの Chakra エンジンによってシリアル化されました。|  
|`JsErrorCannotDisableExecution`|ランタイムは、信頼性の高いスクリプトの中断をサポートしていません。|  
|`JsErrorCannotSerializeDebugScript`|スクリプトは、デバッグコンテキストでシリアル化することはできません。|  
|`JsErrorCategoryEngine`|エンジン自体で発生するエラーに関連するエラーのカテゴリです。|  
|`JsErrorCategoryFatal`|致命的で、エンジンの障害を示すエラーのカテゴリ。|  
|`JsErrorCategoryScript`|スクリプトのエラーに関連するエラーのカテゴリ。|  
|`JsErrorCategoryUsage`|API 自体の不適切な使用に関連するエラーのカテゴリ。|  
|`JsErrorFatal`|エンジンの致命的なエラーが発生しました。|  
|`JsErrorHeapEnumInProgress`|ヒープ列挙は、現在スクリプトコンテキストで進行中です。|  
|`JsErrorIdleNotEnabled`|ホストがアイドル処理を有効にしなかったときに表示されるアイドル通知。|  
|`JsErrorInDisabledState`|ランタイムが無効な状態になっています。|  
|`JsErrorInExceptionState`|エンジンは例外状態であり、例外が消去されるまで Api を呼び出すことはできません。|  
|`JsErrorInObjectBeforeCollectCallback`|この操作は、コールバックを収集する前にオブジェクトでサポートされていません。<br /><br /> この列挙値は、Microsoft Edge モードでのみサポートされます。|  
|`JsErrorInProfileCallback`|スクリプトコンテキストは、プロファイルコールバックの途中にあります。|  
|`JsErrorInThreadServiceCallback`|スレッドサービスのコールバックは現在進行中です。|  
|`JsErrorInvalidArgument`|ホスティング API の引数が無効でした。|  
|`JsErrorNoCurrentContext`|ホスティング API では、コンテキストが最新である必要がありますが、現在のコンテキストは存在しません。|  
|`JsErrorNotImplemented`|ホスティング API はまだ実装されていません。|  
|`JsErrorNullArgument`|Null が許可されていないコンテキストでホスティング API の引数が null でした。|  
|`JsErrorObjectNotInspectable`|オブジェクトをポインターにラップ解除することはできません `IInspectable` 。<br /><br /> この列挙値は、Microsoft Edge モードでのみサポートされます。|  
|`JsErrorOutOfMemory`|Chakra エンジンでメモリが不足しています。|  
|`JsErrorPropertyNotSymbol`|シンボルプロパティ id に対して動作するが、シンボル以外のプロパティ id で呼び出されたホスト API。このエラーコードは、 `JsGetSymbolFromPropertyId` 関数がシンボル以外のプロパティ id で呼び出された場合に返されます。<br /><br /> この列挙値は、Microsoft Edge モードでのみサポートされます。|  
|`JsErrorPropertyNotString`|文字列プロパティ id に対して動作するが、文字列以外のプロパティ id を使って呼び出されたホスト API。このエラーコードは、 `JsGetPropertyNamefromId` 関数が文字列以外のプロパティ id で呼び出された場合に、既存のエラーコードを返します。<br /><br /> この列挙値は、Microsoft Edge モードでのみサポートされます。|  
|`JsErrorRuntimeInUse`|まだ使用されているランタイムを破棄することはできません。|  
|`JsErrorScriptCompile`|JavaScript のコンパイルに失敗しました。|  
|`JsErrorScriptEvalDisabled`|`eval`Or eval が無効にされたため、スクリプトは終了されました `function` 。|  
|`JsErrorScriptException`|スクリプトの実行中に JavaScript 例外が発生しました。|  
|`JsErrorScriptTerminated`|ランタイムの中断要求により、スクリプトが終了されました。|  
|`JsErrorWrongRuntime`|異なる JavaScript ランタイムで作成されたオブジェクトとのホスティング API が呼び出されました。|  
|`JsErrorWrongThread`|間違ったスレッドでホスト API が呼び出されました。|  
|`JsNoError`|成功エラーコード。|  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)