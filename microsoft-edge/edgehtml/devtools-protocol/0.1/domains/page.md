---
description: ページ ドメインの DevTools プロトコル バージョン 0.1 (EdgeHTML) リファレンス。 検査されたページに関連するアクションとイベントは、ページ ドメインに属します。
title: ページ ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b04b0685a6b465d40e999a2a48d370573a3058d8
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399149"
---
# <a name="page-domain---devtools-protocol-version-01-edgehtml"></a>ページ ドメイン - DevTools プロトコル バージョン 0.1 (EdgeHTML)  

検査されたページに関連するアクションとイベントは、ページ ドメインに属します。  

| 分類 | Members |  
|:--- |:--- |  
| [**メソッド**](#methods) | [有効にする](#enable)、[無効にする、](#disable)[移動する](#navigate) |  
| [**型**](#types) | [FrameId](#frameid) |  

## <a name="methods"></a>メソッド  

### <a name="enable"></a>[有効]  

ページ ドメイン通知を有効にします。  

&nbsp;  

---  

### <a name="disable"></a>[無効]  

ページ ドメイン通知を無効にします。  

&nbsp;  

---  

### <a name="navigate"></a>ナビゲート  

現在のページを特定の URL に移動します。  

| パラメーター | 型 | 詳細 |  
|:--- |:--- |:--- |  
| url | `string` | ページを移動する URL。 |  

| 戻り値 | 型 | 詳細 |  
|:--- |:--- |:--- |  
| frameId | [FrameId](#frameid) | **実験的な**.  移動するフレーム ID。 |  

---  

## <a name="types"></a>型  

### <a name="frameid-string"></a>FrameId 文字列  

<a name="frameid"></a>  

一意のフレーム識別子。  

&nbsp;  

---  
