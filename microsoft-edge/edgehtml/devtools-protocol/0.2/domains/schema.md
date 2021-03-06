---
description: スキーマ ドメインの DevTools プロトコル バージョン 0.2 (EdgeHTML) リファレンス。 プロトコル スキーマに関する情報を提供します。
title: スキーマ ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 6844939f452bc96980d6d67d4652adcc7c078c7a
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398148"
---
# <a name="schema-domain---devtools-protocol-version-02-edgehtml"></a>スキーマ ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)  

プロトコル スキーマに関する情報を提供します。  

| 分類 | Members |  
|:--- |:--- |  
| [メソッド](#methods) | [getDomains](#getdomains) |  
| [型](#types) | [Domain オブジェクト](#domain) |  

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
