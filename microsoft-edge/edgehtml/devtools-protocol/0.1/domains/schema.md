---
description: スキーマ ドメインの DevTools プロトコル バージョン 0.1 (EdgeHTML) リファレンス。 プロトコル スキーマに関する情報を提供します。
title: スキーマ ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e89f4269b4984ee49e83a23fcab9679485c49040
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398862"
---
# <a name="schema-domain---devtools-protocol-version-01-edgehtml"></a>スキーマ ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)  

プロトコル スキーマに関する情報を提供します。  

| 分類 | Members |  
|:--- |:--- |  
| [メソッド](#methods) | [getDomains](#getdomains) |  
| [型](#types) | [ドメイン](#domain) |  

## <a name="methods"></a>メソッド  

### <a name="getdomains"></a>getDomains  

サポートされているドメインを返します。  

| 戻り値 | 型 | 詳細 |  
|:--- |:--- |:--- |  
| ドメイン | [Domain[]](#domain) | サポートされているドメインの一覧。 |  

---  

## <a name="types"></a>型  

### <a name="domain-object"></a>Domain オブジェクト  

<a name="domain"></a>  

プロトコル ドメインの説明。  

| プロパティ | 型 | 詳細 |  
|:--- |:--- |:--- |  
| name | `string` | ドメイン名。 |  
| version | `string` | ドメイン バージョン。 |  

---  
