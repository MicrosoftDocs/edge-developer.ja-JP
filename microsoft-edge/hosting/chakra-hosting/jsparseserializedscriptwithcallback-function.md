---
description: シリアル化されたスクリプトを解析し、スクリプトを表す関数を返します。 必要な場合にのみ、スクリプトソースの遅延読み込み機能を提供します。
title: JsParseSerializedScriptWithCallback 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 0a93ecfb-4b82-4a85-b24c-6816db2332ea
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 0315fa82201671fc0ef0c950ef05a14a26be114e
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752242"
---
# JsParseSerializedScriptWithCallback 関数
シリアル化されたスクリプトを解析し、スクリプトを表す関数を返します。 必要な場合にのみ、スクリプトソースの遅延読み込み機能を提供します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsParseSerializedScriptWithCallback(  
  _In_ JsSerializedScriptLoadSourceCallback scriptLoadCallback,  
  _In_ JsSerializedScriptUnloadCallback scriptUnloadCallback,  
  _In_ BYTE *buffer,  
  _In_ JsSourceContext sourceContext,  
  _In_z_ const wchar_t *sourceUrl,  
  _Out_ JsValueRef * result  
);  
  
```  
  
#### パラメーター  
 `scriptLoadCallback`  
 スクリプトのソースコードを読み込む必要があるときに呼び出されます。  
  
 `scriptUnloadCallback`  
 シリアル化されたスクリプトとソースコードが不要になったときに呼び出されます。  
  
 `buffer`  
 シリアル化されたスクリプト。  
  
 `sourceContext`  
 デバッグ可能なスクリプトコンテキストによって使用できるスクリプトを識別する cookie。     このコンテキストは、scriptLoadCallback と scriptUnloadCallback に渡されます。  
  
 `sourceUrl`  
 スクリプトの取得元の場所。  
  
 `result`  
 スクリプトコードを表す関数。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
  
> [!NOTE]
>  この API は、ストアアプリではまだ利用できません。  
  
 アクティブなスクリプトコンテキストが必要です。  
  
 ランタイムは、バッファーから作成されたすべての関数のすべてのインスタンスがガベージコレクションされるまで、バッファーを保持します。  次に、scriptUnloadCallback を呼び出して、安全に解放できることを呼び出し元に通知します。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)