---
description: シリアル化されたスクリプトを解析し、スクリプトを表す関数を返します。 必要な場合にのみスクリプト ソースを遅延読み込む機能を提供します。
title: JsParseSerializedScriptWithCallback 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 0a93ecfb-4b82-4a85-b24c-6816db2332ea
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b145f01a5c3459100d8402beae63b7cff55db7b8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234854"
---
# JsParseSerializedScriptWithCallback 関数

シリアル化されたスクリプトを解析し、スクリプトを表す関数を返します。 必要な場合にのみスクリプト ソースを遅延読み込む機能を提供します。  
  
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
 スクリプトのソース コードを読み込む必要があるときに呼び出されるコールバック。  
  
 `scriptUnloadCallback`  
 シリアル化されたスクリプトとソース コードが不要になったときに呼び出されるコールバック。  
  
 `buffer`  
 シリアル化されたスクリプト。  
  
 `sourceContext`  
 デバッグ可能なスクリプト コンテキストで使用できるスクリプトを識別する Cookie。     このコンテキストは、scriptLoadCallback と scriptUnloadCallback に渡されます。  
  
 `sourceUrl`  
 スクリプトの作成場所。  
  
 `result`  
 スクリプト コードを表す関数。  
  
## 戻り値  
 操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。  
  
## 注釈  
  
> [!NOTE]
>  この API は、ストア アプリではまだ利用できません。  
  
 アクティブなスクリプト コンテキストが必要です。  
  
 バッファーから作成された関数のすべてのインスタンスがガベージ コレクションされるまで、ランタイムはバッファーを保持します。  その後、scriptUnloadCallback を呼び出して、解放しても安全だと呼び出し元に通知します。  
  
## 要件  
 **ヘッダー:** jsrt.h  
  
## 関連項目  
 [リファレンス (JavaScript ランタイム)](../chakra-hosting/reference-javascript-runtime.md)
