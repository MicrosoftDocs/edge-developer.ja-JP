---
description: ガベージコレクションオブジェクトへの参照を追加します。
title: JsAddRef 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsAddRef
helpviewer_keywords:
- JsAddRef function
ms.assetid: a7f3ed49-6a86-489a-abdf-c99428e79cae
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: bd02dded6dc2877228f22b4d2800e41a78163467
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569404"
---
# JsAddRef 関数
ガベージコレクションオブジェクトへの参照を追加します。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsAddRef(  
   _In_ JsRef ref,  
   _Out_opt_ unsigned int *count  
);  
```  
  
#### パラメーター  
 `ref`  
 参照を追加する対象のオブジェクト。  
  
 `count`  
 オブジェクトの新しい参照カウント (null 値を渡すことができます)。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 これは `JsRef` 、スタックのどこかに保存されないハンドルでのみ呼び出す必要があります。 呼び出し `JsAddRef` によって、 `JsRef` が呼び出されるまで、参照先のオブジェクトは解放されません `JsRelease` 。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)