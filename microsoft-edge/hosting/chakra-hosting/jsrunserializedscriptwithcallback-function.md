---
description: シリアル化されたスクリプトを実行します。 必要な場合にのみ、スクリプトソースの遅延読み込み機能を提供します。
title: JsRunSerializedScriptWithCallback 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 0608d778-f65b-4dc5-a745-364aac57ef59
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 84a74d3c1aa68469dfe2fe42fdee685faa4c358c
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752221"
---
# JsRunSerializedScriptWithCallback 関数
シリアル化されたスクリプトを実行します。 必要な場合にのみ、スクリプトソースの遅延読み込み機能を提供します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsRunSerializedScriptWithCallback(  
  _In_ JsSerializedScriptLoadSourceCallback scriptLoadCallback,  
  _In_ JsSerializedScriptUnloadCallback scriptUnloadCallback,  
  _In_ BYTE *buffer,  
  _In_ JsSourceContext sourceContext,  
  _In_z_ const wchar_t *sourceUrl,  
  _Out_opt_ JsValueRef *result  
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
 スクリプトを実行した結果 (存在する場合)。 このパラメーターは null にすることができます。  
  
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